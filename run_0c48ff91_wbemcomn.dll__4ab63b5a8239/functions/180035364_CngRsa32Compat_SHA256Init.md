# CngRsa32Compat_SHA256Init

- ea: `0x180035364`
- end: `0x1800353a4`
- name: `CngRsa32Compat_SHA256Init`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001f0e0`

## callees

- `0x180035364`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18003538e`
- `bcrypt!BCryptCreateHash` at `0x18003538e`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHA256Init(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x180035364  sub     rsp, 48h
0x180035368  xor     r9d, r9d; cbHashObject
0x18003536b  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180035373  mov     rdx, rcx; phHash
0x180035376  mov     [rsp+48h+cbSecret], 0; cbSecret
0x18003537e  xor     r8d, r8d; pbHashObject
0x180035381  mov     [rsp+48h+pbSecret], 0; pbSecret
0x18003538a  lea     ecx, [r9+41h]; hAlgorithm
0x18003538e  call    cs:__imp_BCryptCreateHash
0x180035394  test    eax, eax
0x180035396  jns     short loc_18003539F
0x180035398  mov     ecx, 7
0x18003539d  int     29h; Win8: RtlFailFast(ecx)
0x18003539f  add     rsp, 48h
0x1800353a3  retn
```
