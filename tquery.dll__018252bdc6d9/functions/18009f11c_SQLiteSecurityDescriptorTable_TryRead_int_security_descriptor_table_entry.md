# SQLiteSecurityDescriptorTable::TryRead(int,security_descriptor_table_entry &)

- ea: `0x18009f11c`
- end: `0x18009f2cb`
- name: `?TryRead@SQLiteSecurityDescriptorTable@@QEAA_NHAEAUsecurity_descriptor_table_entry@@@Z`
- size: `431`
- prototype: `bool(SQLiteSecurityDescriptorTable *__hidden this, int, struct security_descriptor_table_entry *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009f38c`

## callees

- `0x180048e48`
- `0x1800996e4`
- `0x18009a170`
- `0x18009aa44`
- `0x18009aac8`
- `0x18009b77c`
- `0x18009ca10`
- `0x18009dcd8`
- `0x18009e1dc`
- `0x18009f11c`
- `0x18009fcac`
- `0x18009fd74`
- `0x18013e868`
- `0x18014aa24`
- `0x18015d2fc`
- `0x180188d90`
- `0x180189cda`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18009f252`
- `msvcp_win!_Mtx_unlock` at `0x18009f280`
- `msvcp_win!_Mtx_unlock` at `0x18009f252`
- `msvcp_win!_Mtx_unlock` at `0x18009f280`
- `SearchIndexerCore!sqlite3_column_bytes` at `0x18009f1c2`
- `SearchIndexerCore!sqlite3_column_bytes` at `0x18009f1c2`
- `SearchIndexerCore!sqlite3_column_text` at `0x18009f1a5`
- `SearchIndexerCore!sqlite3_column_text` at `0x18009f1a5`

## string_xrefs

- `0x18009f155`: `SELECT Value, EnterpriseIds from SecurityDescriptor WHERE Id = ?;`

## pseudocode

```c

```
