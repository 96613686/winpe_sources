# KEDecryptDataWithAES

- ea: `0x1800b5fdc`
- end: `0x1800b61f8`
- name: `KEDecryptDataWithAES`
- size: `540`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, PUCHAR pbSecret, ULONG cbSecret, __int64, ULONG *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18009e42c`
- `0x1800b6248`

## callees

- `0x18002cd80`
- `0x1800b5fdc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b613b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b613b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b61a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b61a3`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800b60e3`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800b60e3`
- `bcrypt!BCryptDestroyKey` at `0x1800b61b8`
- `bcrypt!BCryptDestroyKey` at `0x1800b61b8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b604e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b604e`
- `bcrypt!BCryptGetProperty` at `0x1800b608a`
- `bcrypt!BCryptGetProperty` at `0x1800b608a`
- `bcrypt!BCryptSetProperty` at `0x1800b60ba`
- `bcrypt!BCryptSetProperty` at `0x1800b60ba`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b61c9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b61c9`
- `bcrypt!BCryptDecrypt` at `0x1800b6127`
- `bcrypt!BCryptDecrypt` at `0x1800b6183`
- `bcrypt!BCryptDecrypt` at `0x1800b6127`
- `bcrypt!BCryptDecrypt` at `0x1800b6183`

## pseudocode

```c

```
