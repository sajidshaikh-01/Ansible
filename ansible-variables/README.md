Where Can You Define Variables?

| Type | Location                  | Priority |
| ---- | ------------------------- | -------- |
| 1    | Command line              | Highest  |
| 2    | Playbook vars             | High     |
| 3    | vars_files                | High     |
| 4    | Host Vars (`host_vars`)   | Medium   |
| 5    | Group Vars (`group_vars`) | Medium   |
| 6    | Inventory vars            | Low      |
| 7    | Default var in roles      | Lowest   |
