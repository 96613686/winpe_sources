# BCryptCreateHash

- ea: `0x140016974`
- end: `0x14001697b`
- name: `BCryptCreateHash`
- size: `7`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_HASH_HANDLE *phHash, PUCHAR pbHashObject, ULONG cbHashObject, PUCHAR pbSecret, ULONG cbSecret, ULONG dwFlags)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000338c`
- `0x140004e34`

## import_xrefs

- `cng!BCryptCreateHash` at `0x140016974`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall BCryptCreateHash(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_HASH_HANDLE *phHash,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        PUCHAR pbSecret,
        ULONG cbSecret,
        ULONG dwFlags)
{
  return __imp_BCryptCreateHash(hAlgorithm, phHash, pbHashObject, cbHashObject, pbSecret, cbSecret, dwFlags);
}

```

## disassembly

```asm
0x140016974  jmp     cs:__imp_BCryptCreateHash
```
