# tree-rs

## Description
Rewrite `tree` in rust.

## Framing
Limit the implementation to how `tree` works when no options are passed. Maybe 
just `-a` for hidden files.

**Output example:**
```shell
foo@bar:~$  tree-rs
.
├── Cargo.toml
├── LICENSE
├── README.md
└── src
    └── main.rs

1 directory, 4 files
```

When this is ready, a `--raw` parameter could be implemented, that returns the 
tree structure data for another application to consume. 
A faster alternative to `json` could be nice for bigger directory structures.

**`json` example:**
```shell
foo@bar:~$ tree-rs --raw
[
  {"type":"directory","name":".","contents":[
    {"type":"file","name":"Cargo.toml"},
    {"type":"file","name":"LICENSE"},
    {"type":"file","name":"README.md"},
    {"type":"directory","name":"src","contents":[
      {"type":"file","name":"main.rs"}
    ]},
  ]},
  {"type":"report","directories":1,"files":4}
]
```

