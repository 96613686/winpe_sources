# LiteCryptUtilities::ImportRawKeyIntoCSP(unsigned __int64,uchar const *,ulong,uint,ulong,unsigned __int64 *)

- ea: `0x1800598fc`
- end: `0x180059b0a`
- name: `?ImportRawKeyIntoCSP@LiteCryptUtilities@@YAJ_KPEBEKIKPEA_K@Z`
- size: `526`
- prototype: `__int64 __usercall@<rax>(HCRYPTPROV hProv@<rcx>, void *Source@<rdx>, rsize_t DestinationSize@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180058be8`
- `0x18005934c`

## callees

- `0x18000a1a8`
- `0x18000cc9c`
- `0x18000e870`
- `0x180021a64`
- `0x180021a90`
- `0x180051250`
- `0x1800512f8`
- `0x180053890`
- `0x1800598fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800599ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800599ba`
- `CRYPTSP!CryptImportKey` at `0x180059a46`
- `CRYPTSP!CryptImportKey` at `0x180059a46`

## string_xrefs

- `0x180059a8f`: `hr = SafeCopyMemory(spKeyBlob, keyBlobSize, &bhKey, sizeof(BLOBHEADER))`
- `0x180059a80`: `hr = SafeCopyMemory(spKeyBlob + sizeof(BLOBHEADER) + sizeof(DWORD), rawKeyLength, pRawKey, rawKeyLength)`

## pseudocode

```c

```
