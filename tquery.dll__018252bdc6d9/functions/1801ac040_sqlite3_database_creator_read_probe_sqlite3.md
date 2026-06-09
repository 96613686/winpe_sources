# sqlite3_database_creator::read_probe(sqlite3 *)

- ea: `0x1801ac040`
- end: `0x1801ac18a`
- name: `?read_probe@sqlite3_database_creator@@CA_NPEAUsqlite3@@@Z`
- size: `330`
- prototype: `bool __fastcall(struct sqlite3 *)`
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0x18012d020`
- `0x1801aa4b0`
- `0x1801aab18`
- `0x1801abaa4`
- `0x180221b88`

## callees

- `0x180098390`
- `0x1800996e4`
- `0x18009ab50`
- `0x18009e1dc`
- `0x1801480fc`
- `0x1801484b0`
- `0x18014a9e8`
- `0x180188d90`
- `0x180189cda`
- `0x1801a7e4c`
- `0x1801ac040`

## import_xrefs

- `SearchIndexerCore!sqlite3_step` at `0x1801ac0a6`
- `SearchIndexerCore!sqlite3_step` at `0x1801ac0a6`
- `SearchIndexerCore!sqlite3_free` at `0x1801ac0ef`
- `SearchIndexerCore!sqlite3_free` at `0x1801ac0ef`
- `SearchIndexerCore!sqlite3_malloc` at `0x1801ac0e1`
- `SearchIndexerCore!sqlite3_malloc` at `0x1801ac0e1`
- `SearchIndexerCore!sqlite3_errmsg` at `0x1801ac134`
- `SearchIndexerCore!sqlite3_errmsg` at `0x1801ac134`
- `SearchIndexerCore!sqlite3_extended_errcode` at `0x1801ac140`
- `SearchIndexerCore!sqlite3_extended_errcode` at `0x1801ac140`

## string_xrefs

- `0x1801ac166`: `failed to read database`
- `0x1801ac14e`: `Failed to read database with error code %d: %s`

## pseudocode

```c

```
