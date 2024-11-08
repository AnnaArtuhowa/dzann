```mermaid
classDiagram
    class AppleSlice {
        - int number
        + __str__() str
    }

    class AppleSliceIterator {
        - List~AppleSlice~ _apple
        - int _index
        - bool _reverse
        + __next__() AppleSlice
    }

    class AppleAggregate {
        - List~AppleSlice~ _slices
        + amount_slices() int
        + __iter__() AppleSliceIterator
        + get_reverse_iterator() AppleSliceIterator
    }

    %% Взаємозв'язки між класами
    AppleAggregate o-- AppleSlice : композиція
    AppleAggregate --> AppleSliceIterator : створює
    AppleSliceIterator --> AppleSlice : агрегація
