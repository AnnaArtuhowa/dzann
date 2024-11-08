```mermaid
classDiagram
    direction LR

    class AppleSlice
    class AppleSliceIterator
    class AppleAggregate
    class Iterator
    class Iterable

    AppleSliceIterator --|> Iterator : Inherits
    AppleAggregate --|> Iterable : Inherits
    AppleAggregate o-- "0..*" AppleSlice : Contains
    AppleAggregate --> AppleSliceIterator : Uses
    AppleSliceIterator --> AppleSlice : Iterates
