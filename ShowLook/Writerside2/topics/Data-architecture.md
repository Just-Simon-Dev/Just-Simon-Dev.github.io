# Data Architecture

## Postgres Data Architecture

### Settings Table (Future)

### ML table

```mermaid
classDiagram
    ML --|> Generation
    ML: +int Id
    ML: +json Model
    ML: +int NumberOfRatedOutfits
    ML: +int Grade
    ML: +bool IsActualGeneration
    ML: +bool IsFinished
    ML: +Predict()
    ML: -PrepareData()
    
```

### Generation table

```mermaid
classDiagram 
    Generation <|-- ML
    Generation: +int Id
    Generation: +int Iteration
    Generation: +int NumberOfModels
    Generation: +int FinishedModels
    Generation: +ML BestModel
    Generation: +bool IsActualGeneration
    Generation: +FinishGeneration()
    Generation: -CreateNewGeneration()
    Generation: -SetActualGenerationToFalse()
    Generation: -IsAllModelsFinished()
    
```

### Outfits Data Analysis Table

## Apache Casandra Architecture

## S3 Minio Architecture