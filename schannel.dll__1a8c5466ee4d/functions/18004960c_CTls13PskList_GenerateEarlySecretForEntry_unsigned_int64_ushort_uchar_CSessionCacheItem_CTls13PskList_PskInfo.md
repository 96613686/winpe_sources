# CTls13PskList::GenerateEarlySecretForEntry(unsigned __int64,ushort,uchar,CSessionCacheItem *,CTls13PskList::_PskInfo *)

- ea: `0x18004960c`
- end: `0x180049820`
- name: `?GenerateEarlySecretForEntry@CTls13PskList@@IEAAK_KGEPEAVCSessionCacheItem@@PEAU_PskInfo@1@@Z`
- size: `532`
- prototype: `unsigned int(CTls13PskList *__hidden this, unsigned __int64, unsigned __int16, unsigned __int8, struct CSessionCacheItem *, struct CTls13PskList::_PskInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180049030`
- `0x180080478`

## callees

- `0x180021da8`
- `0x18004960c`
- `0x180074de4`
- `0x180091010`

## import_xrefs

- `ncrypt!SslExtractEarlyKey` at `0x1800497ac`
- `ncrypt!SslExtractEarlyKey` at `0x1800497ac`
- `ncrypt!SslFreeObject` at `0x180049659`
- `ncrypt!SslFreeObject` at `0x1800497f8`
- `ncrypt!SslFreeObject` at `0x180049659`
- `ncrypt!SslFreeObject` at `0x1800497f8`
- `ncrypt!SslImportKey` at `0x180049709`
- `ncrypt!SslImportKey` at `0x180049709`

## pseudocode

```c

```
