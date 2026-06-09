# CngRsa32Compat_rc4_key

- ea: `0x180007d88`
- end: `0x180007df5`
- name: `CngRsa32Compat_rc4_key`
- size: `109`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *phKey)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007e00`
- `0x180009a34`
- `0x180009fe8`

## callees

- `0x180007d88`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x180007daa`
- `bcrypt!BCryptDestroyKey` at `0x180007daa`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180007dd9`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180007dd9`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_rc4_key(BCRYPT_KEY_HANDLE *phKey, __int64 a2, UCHAR *a3)
{
  BCRYPT_KEY_HANDLE v5; // rcx
  NTSTATUS result; // eax

  if ( !phKey )
    __fastfail(7u);
  v5 = *phKey;
  if ( *phKey )
  {
    BCryptDestroyKey(v5);
    *phKey = 0;
  }
  result = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x71, phKey, 0, 0, a3, 0x10u, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x180007d88  mov     [rsp+arg_0], rbx
0x180007d8d  push    rdi
0x180007d8e  sub     rsp, 40h
0x180007d92  mov     rdi, r8
0x180007d95  mov     rbx, rcx
0x180007d98  test    rcx, rcx
0x180007d9b  jnz     short loc_180007DA2
0x180007d9d  lea     ecx, [rbx+7]
0x180007da0  int     29h; Win8: RtlFailFast(ecx)
0x180007da2  mov     rcx, [rbx]; hKey
0x180007da5  test    rcx, rcx
0x180007da8  jz      short loc_180007DB7
0x180007daa  call    cs:__imp_BCryptDestroyKey
0x180007db0  mov     qword ptr [rbx], 0
0x180007db7  xor     r9d, r9d; cbKeyObject
0x180007dba  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180007dc2  mov     [rsp+48h+cbSecret], 10h; cbSecret
0x180007dca  xor     r8d, r8d; pbKeyObject
0x180007dcd  mov     rdx, rbx; phKey
0x180007dd0  mov     [rsp+48h+pbSecret], rdi; pbSecret
0x180007dd5  lea     ecx, [r9+71h]; hAlgorithm
0x180007dd9  call    cs:__imp_BCryptGenerateSymmetricKey
0x180007ddf  test    eax, eax
0x180007de1  jns     short loc_180007DEA
0x180007de3  mov     ecx, 7
0x180007de8  int     29h; Win8: RtlFailFast(ecx)
0x180007dea  mov     rbx, [rsp+48h+arg_0]
0x180007def  add     rsp, 40h
0x180007df3  pop     rdi
0x180007df4  retn
```
