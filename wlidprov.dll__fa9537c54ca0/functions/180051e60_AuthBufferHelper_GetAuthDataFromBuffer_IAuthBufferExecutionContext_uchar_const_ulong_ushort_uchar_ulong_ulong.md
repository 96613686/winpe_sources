# AuthBufferHelper::GetAuthDataFromBuffer(IAuthBufferExecutionContext *,uchar const *,ulong,ushort * *,uchar * *,ulong *,ulong *)

- ea: `0x180051e60`
- end: `0x1800521e9`
- name: `?GetAuthDataFromBuffer@AuthBufferHelper@@UEAAJPEAVIAuthBufferExecutionContext@@PEBEKPEAPEAGPEAPEAEPEAK4@Z`
- size: `905`
- prototype: `int(AuthBufferHelper *__hidden this, struct IAuthBufferExecutionContext *, const unsigned __int8 *, unsigned int, unsigned __int16 **, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180004824`
- `0x180004910`
- `0x180004b2c`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18001173c`
- `0x180015d2c`
- `0x18001abbe`
- `0x18001ac3c`
- `0x180051e60`
- `0x1800535d8`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005210d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005214f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005215d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005210d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005214f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005215d`

## string_xrefs

- `0x180052128`: `hr = SafeCopyMemory(spAuthData, authDataSizeBytes, pCredUICredentials->AuthInfo.ByteArrayOffset + reinterpret_cast<const BYTE*>(pCredUICredentials), authDataSizeBytes)`
- `0x180052178`: `hr = SafeCopyMemory(spUsername, usernameSizeBytes, reinterpret_cast<const BYTE*>(pCredEx2) + pCredEx2->UserOffset, pCredEx2->UserLength)`

## pseudocode

```c

```
