---
title: "Hashing"
date: 2018-11-12T20:55:46-06:00
description: "Notes about different hashing techniques"
type: "notes"
draft: false
---
[Cmu hashing notes](http://www.cs.cmu.edu/afs/cs/academic/class/15210-f13/www/lectures/lecture24.pdf)


## Separate Chaining
* The idea is to maintain an array of linked lists
* All keys that hash to the same loc are just added to the linked list. Could maybe optimize these linked lists by having an lru cache implemntation or another data structure ..
* Cost of these operations is related to the average len of a chain.
* Disadvantage - costly allocation, and memory for the pointers.. O(n) worst case. The advantage is that it is not sensitive to the size of the table


## Open address hash tables:
No linked lists, stores key in the array. Fewer cache misses, since typically all locations are checked on the same cache line.
Basic idea is to maintain an array that is a constant factor larger than the number of keys, and store cells directly in the array.


## Linear probing
```h(k,i) = (h(k)+i)```

* Ordered sequences of locations. If collision, iterate until an empty spot.
* Leads to primary clustering where it just keeps growing larger and larger as it takes up space. Keys tend to cluster, adds to cluster size.
* Performance degrades when load factor increases


## Quadratic probing:
```h(k,i) = (h(k)+i^2)```

* Avoids primary clustering, still has secondary clusters. When two hash to same location, have same probe sequence.
* One prob is that it does not probe all locations in the table


## Double Hashing
_Separate hash function for the jump_

``` h(k,i) = (h(k)+i*h(k))```

* Keys that hash to same loc, are likely to hash to a diff jump size.
* Double hashing avoids secondary clustering by providing much more probe sequences m^2.
Better when load factor is almost full
* Allows for smaller tables (high load factors), but ofc high costs for next probe


## Conclusion
Hashing is an example of a space-time tradeoff. Increase the space so table operations are faster, decrease the space but table operation are slower


Open addressing more space efficient. Linear probing, has small constants and works well with caches. suffers badly from clustering. Quadratic hashing requires rehashing when load reaches 50%.
Double hashing reduces clustering, but finding suitable pairs of hash functions is difficult and increases the cost of a probe.
