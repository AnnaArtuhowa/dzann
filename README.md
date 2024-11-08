```mermaid
classDiagram
    direction LR

    class AppleSlice {
        + number: int
        + __str__()
    }

    class AppleSliceIterator {
        + _apple: List<AppleSlice>
        + _index: int
        + _reverse: bool
        + __next__()
    }

    class AppleAggregate {
        
        + amount_slices(): int
        + __iter__()
        + get_reverse_iterator()
    }

    AppleAggregate o-- "0..*" AppleSlice : Contains
    AppleAggregate --> AppleSliceIterator : Uses
    AppleSliceIterator --> AppleSlice : Iterates over
    AppleSliceIterator --|> Iterator : Inherits
    AppleAggregate --|> Iterable : Inherits
