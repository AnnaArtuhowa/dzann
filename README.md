classDiagram
    direction TB

    class AppleSlice {
        -int number
        +__str__()
    }

    class AppleSliceIterator {
        -List<AppleSlice> _apple
        -int _index
        -bool _reverse
        +__next__()
    }

    class AppleAggregate {
        -List<AppleSlice> _slices
        +amount_slices()
        +__iter__()
        +get_reverse_iterator()
    }

    AppleAggregate "1" --> "0..*" AppleSlice : contains
    AppleAggregate "1" --> "1" AppleSliceIterator : uses
    AppleSliceIterator "1" --> "0..*" AppleSlice : iterates over
    AppleSliceIterator ..|> Iterator : inherits
    AppleAggregate ..|> Iterable : inherits
