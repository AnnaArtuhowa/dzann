```mermaid
classDiagram
    direction LR

    class AppleSlice {
    }

    class AppleSliceIterator {
    }

    class AppleAggregate {  
    }

AppleAggregate o-- "0..*" AppleSlice : Contains

