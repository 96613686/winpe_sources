# SecurityManager::Sha256HashData(uchar *,uint,uchar * const)

- ea: `0x14027a8bc`
- end: `0x14027a999`
- name: `?Sha256HashData@SecurityManager@@AEAAJPEAEIQEAE@Z`
- size: `221`
- prototype: `int(SecurityManager *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400ce6d0`
- `0x140279be0`

## callees

- `0x14011ea40`
- `0x14027a8bc`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x14027a954`
- `bcrypt!BCryptFinishHash` at `0x14027a954`
- `bcrypt!BCryptDestroyHash` at `0x14027a974`
- `bcrypt!BCryptDestroyHash` at `0x14027a974`
- `bcrypt!BCryptHashData` at `0x14027a931`
- `bcrypt!BCryptHashData` at `0x14027a931`
- `bcrypt!BCryptCreateHash` at `0x14027a911`
- `bcrypt!BCryptCreateHash` at `0x14027a911`

## pseudocode

```c

```
