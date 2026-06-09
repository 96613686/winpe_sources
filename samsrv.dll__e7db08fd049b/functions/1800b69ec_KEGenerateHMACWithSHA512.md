# KEGenerateHMACWithSHA512

- ea: `0x1800b69ec`
- end: `0x1800b6bb5`
- name: `KEGenerateHMACWithSHA512`
- size: `457`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18009e42c`

## callees

- `0x1800b69ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6a84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6ae3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6a84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6ae3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6b70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6b94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6b70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6b94`
- `bcrypt!BCryptCreateHash` at `0x1800b6b15`
- `bcrypt!BCryptCreateHash` at `0x1800b6b15`
- `bcrypt!BCryptHashData` at `0x1800b6b30`
- `bcrypt!BCryptHashData` at `0x1800b6b30`
- `bcrypt!BCryptDestroyHash` at `0x1800b6b86`
- `bcrypt!BCryptDestroyHash` at `0x1800b6b86`
- `bcrypt!BCryptFinishHash` at `0x1800b6b4a`
- `bcrypt!BCryptFinishHash` at `0x1800b6b4a`
- `bcrypt!BCryptGetProperty` at `0x1800b6a64`
- `bcrypt!BCryptGetProperty` at `0x1800b6ac1`
- `bcrypt!BCryptGetProperty` at `0x1800b6a64`
- `bcrypt!BCryptGetProperty` at `0x1800b6ac1`

## pseudocode

```c

```
