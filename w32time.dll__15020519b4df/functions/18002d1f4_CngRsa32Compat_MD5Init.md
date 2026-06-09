# CngRsa32Compat_MD5Init

- ea: `0x18002d1f4`
- end: `0x18002d23d`
- name: `CngRsa32Compat_MD5Init`
- size: `73`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002439c`
- `0x1800586cc`

## callees

- `0x18002d1f4`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18002d21e`
- `bcrypt!BCryptCreateHash` at `0x18002d21e`

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
0x18002d1f4  sub     rsp, 48h
0x18002d1f8  xor     r9d, r9d; cbHashObject
0x18002d1fb  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18002d203  mov     rdx, rcx; phHash
0x18002d206  mov     [rsp+48h+cbSecret], 0; cbSecret
0x18002d20e  xor     r8d, r8d; pbHashObject
0x18002d211  mov     [rsp+48h+pbSecret], 0; pbSecret
0x18002d21a  lea     ecx, [r9+21h]; hAlgorithm
0x18002d21e  call    cs:__imp_BCryptCreateHash
0x18002d225  nop     dword ptr [rax+rax+00h]
0x18002d22a  test    eax, eax
0x18002d22c  js      short loc_18002D234
0x18002d22e  add     rsp, 48h
0x18002d232  retn
0x18002d234  mov     ecx, 7
0x18002d239  int     29h; Win8: RtlFailFast(ecx)
0x18002d23b  jmp     short loc_18002D22E
```
