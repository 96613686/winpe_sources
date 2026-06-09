# CngRsa32Compat_MD5Init

- ea: `0x18000b99c`
- end: `0x18000b9dc`
- name: `CngRsa32Compat_MD5Init`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009fe8`

## callees

- `0x18000b99c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000b9c6`
- `bcrypt!BCryptCreateHash` at `0x18000b9c6`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_MD5Init(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x18000b99c  sub     rsp, 48h
0x18000b9a0  xor     r9d, r9d; cbHashObject
0x18000b9a3  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18000b9ab  mov     rdx, rcx; phHash
0x18000b9ae  mov     [rsp+48h+cbSecret], 0; cbSecret
0x18000b9b6  xor     r8d, r8d; pbHashObject
0x18000b9b9  mov     [rsp+48h+pbSecret], 0; pbSecret
0x18000b9c2  lea     ecx, [r9+21h]; hAlgorithm
0x18000b9c6  call    cs:__imp_BCryptCreateHash
0x18000b9cc  test    eax, eax
0x18000b9ce  jns     short loc_18000B9D7
0x18000b9d0  mov     ecx, 7
0x18000b9d5  int     29h; Win8: RtlFailFast(ecx)
0x18000b9d7  add     rsp, 48h
0x18000b9db  retn
```
