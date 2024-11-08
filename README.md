from graphviz import Digraph

def create_uml():
    dot = Digraph(comment='Apple Classes UML Diagram')

    # AppleAggregate class
    dot.node('A', 'AppleAggregate\n- _slices: List[AppleSlice]\n+ amount_slices()\n+ __iter__()\n+ get_reverse_iterator()')

    # AppleSlice class
    dot.node('B', 'AppleSlice\n- number: int\n+ __str__()')

    # AppleSliceIterator class
    dot.node('C', 'AppleSliceIterator\n- _apple: List[AppleSlice]\n- _index: int\n- _reverse: bool\n+ __next__()')

    # Relationships
    dot.edge('A', 'B', label='has-a')
    dot.edge('A', 'C', label='uses')
    dot.edge('C', 'B', label='iterates over')

    return dot

uml_diagram = create_uml()
uml_diagram.render('apple_classes_uml', format='png', view=True)
