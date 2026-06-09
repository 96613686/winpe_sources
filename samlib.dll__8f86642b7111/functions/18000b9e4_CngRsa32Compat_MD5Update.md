# CngRsa32Compat_MD5Update

- ea: `0x18000b9e4`
- end: `0x18000ba08`
- name: `CngRsa32Compat_MD5Update`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009fe8`

## callees

- `0x18000b9e4`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000b9f2`
- `bcrypt!BCryptHashData` at `0x18000b9f2`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_MD5Update(BCRYPT_HASH_HANDLE *a1, UCHAR *a2)
{
  NTSTATUS result; // eax

  result = BCryptHashData(*a1, a2, 0x10u, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x18000b9e4  sub     rsp, 28h
0x18000b9e8  mov     rcx, [rcx]; hHash
0x18000b9eb  xor     r9d, r9d; dwFlags
0x18000b9ee  lea     r8d, [r9+10h]; cbInput
0x18000b9f2  call    cs:__imp_BCryptHashData
0x18000b9f8  test    eax, eax
0x18000b9fa  jns     short loc_18000BA03
0x18000b9fc  mov     ecx, 7
0x18000ba01  int     29h; Win8: RtlFailFast(ecx)
0x18000ba03  add     rsp, 28h
0x18000ba07  retn
```
