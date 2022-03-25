### Record & Replay Debugging
Memory addresses are maintained accross runs - GREAT for non-deterministic issues 

Use for non-deterministic bugs
- single threaded
- shared memory
- eliminates some optimizations (BDSL)
- causes a performance hit so avoid on prod & staging


### JSON-RPC API (Programmatic Debugging)

- need to stop program (client.Hault()) before setting breakpoints (using api package)


Tab-completion is called fuzzy search