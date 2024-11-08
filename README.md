```mermaid
classDiagram
    direction LR

    class AppleSlice {
        + int number
        + __str__()
    }

    class AppleSliceIterator {
        + List<AppleSlice> _apple
        + int _index
        + bool _reverse
        + __next__()
    }

    class AppleAggregate {
        + List<AppleSlice> _slices
        + amount_slices()
        + __iter__()
        + get_reverse_iterator()
    }

    AppleSliceIterator --|> Iterator : Inherits
    AppleAggregate --|> Iterable : Inherits
    AppleAggregate o-- "0..*" AppleSlice : Contains
    AppleAggregate --> AppleSliceIterator : Uses
    AppleSliceIterator --> AppleSlice : Iterates

