+-------------------+       +-------------------------+
|  AppleAggregate   |<>-----|      AppleSliceIterator  |
+-------------------+       +-------------------------+
| - _slices: List   |       | - _apple: List           |
|                   |       | - _index: int            |
| + amount_slices() |       | - _reverse: bool         |
| + __iter__()      |       | + __next__()             |
| + get_reverse_iterator()| +-------------------------+
+-------------------+        
         |      
         |  * 
+-------------------+        
|    AppleSlice     |        
+-------------------+        
| - number: int     |        
| + __str__()       |        
+-------------------+        
