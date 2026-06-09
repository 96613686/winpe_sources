# KEEncryptDataWithAES

- ea: `0x1800b65a0`
- end: `0x1800b67bd`
- name: `KEEncryptDataWithAES`
- size: `541`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, PUCHAR pbSecret, int, __int64, ULONG *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b67c4`

## callees

- `0x18002cd80`
- `0x1800b65a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6700`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6768`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6768`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800b66a8`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800b66a8`
- `bcrypt!BCryptDestroyKey` at `0x1800b677d`
- `bcrypt!BCryptDestroyKey` at `0x1800b677d`
- `bcrypt!BCryptEncrypt` at `0x1800b66ec`
- `bcrypt!BCryptEncrypt` at `0x1800b6748`
- `bcrypt!BCryptEncrypt` at `0x1800b66ec`
- `bcrypt!BCryptEncrypt` at `0x1800b6748`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b6612`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b6612`
- `bcrypt!BCryptGetProperty` at `0x1800b664e`
- `bcrypt!BCryptGetProperty` at `0x1800b664e`
- `bcrypt!BCryptSetProperty` at `0x1800b667e`
- `bcrypt!BCryptSetProperty` at `0x1800b667e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b678e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b678e`

## pseudocode

```c

```
