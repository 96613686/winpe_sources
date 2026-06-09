# SecurityManager::Sha256HashData(uchar *,uint,uchar * const)

- ea: `0x1402748ac`
- end: `0x140274989`
- name: `?Sha256HashData@SecurityManager@@AEAAJPEAEIQEAE@Z`
- size: `221`
- prototype: `int(SecurityManager *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400de650`
- `0x140273bd0`

## callees

- `0x140132960`
- `0x1402748ac`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x140274944`
- `bcrypt!BCryptFinishHash` at `0x140274944`
- `bcrypt!BCryptDestroyHash` at `0x140274964`
- `bcrypt!BCryptDestroyHash` at `0x140274964`
- `bcrypt!BCryptHashData` at `0x140274921`
- `bcrypt!BCryptHashData` at `0x140274921`
- `bcrypt!BCryptCreateHash` at `0x140274901`
- `bcrypt!BCryptCreateHash` at `0x140274901`

## pseudocode

```c

```
