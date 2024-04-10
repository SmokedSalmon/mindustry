# Armory Logistic

[draft-3.mlog](draft-3.mlog) is the logic for a single processor that reads all the factories' building sequence and determine the ratio of all required material  
It then puts in a memory cell in <resource Id>-<count> pair and let the download-stream processor consume it

[draft-2.mlog](draft-2.mlog) is a processor that controls the unloader next to a core to output material stream according to a tuned ratio  
It can read the output of [draft-3.mlog]

At the current design, draft-3's processor lives within armories schematics, but the memory cell does NOT

## How to build
- build `draft-3`'s and `draft-2`'s schematics separately
- put a single memory cell at overlapped area of both processors, serving as the shared state
- connects unloader of `draft-2` to feed material to armory complex of `draft-3`

## Debug
Put message node for each processor, you should see the material list and quantities for factories' building sequence