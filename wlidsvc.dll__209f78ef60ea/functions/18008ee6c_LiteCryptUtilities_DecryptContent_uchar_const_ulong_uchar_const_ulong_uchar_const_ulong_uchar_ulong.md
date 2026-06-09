# LiteCryptUtilities::DecryptContent(uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x18008ee6c`
- end: `0x18008f19b`
- name: `?DecryptContent@LiteCryptUtilities@@YAJPEBEK0K0KPEAPEAEPEAK@Z`
- size: `815`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbIV, ULONG cbIV, PUCHAR pbInput, ULONG cbInput, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18010eb40`

## callees

- `0x180009e98`
- `0x18000a354`
- `0x18000a36c`
- `0x18000a45c`
- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180039b00`
- `0x18008ee6c`
- `0x180112338`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f088`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f088`
- `bcrypt!BCryptSetProperty` at `0x18008efa0`
- `bcrypt!BCryptSetProperty` at `0x18008efa0`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18008efea`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18008efea`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008ef3c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008ef3c`
- `bcrypt!BCryptDecrypt` at `0x18008f051`
- `bcrypt!BCryptDecrypt` at `0x18008f0fe`
- `bcrypt!BCryptDecrypt` at `0x18008f051`
- `bcrypt!BCryptDecrypt` at `0x18008f0fe`

## string_xrefs

- `0x18008ef56`: `hr = HRESULT_FROM_WIN32(::BCryptOpenAlgorithmProvider( &spAlgorithm, BCRYPT_AES_ALGORITHM, nullptr, 0))`

## pseudocode

```c

```
