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
    AppleAggregate --> AppleSliceIterator : Uses
    AppleSliceIterator --> AppleSlice : Iterates over
    AppleSliceIterator --|> Iterator : Inherits
    AppleAggregate --|> Iterable : Inherits
