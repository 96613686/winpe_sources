# CngRsa32Compat_MD5Final

- ea: `0x18000b958`
- end: `0x18000b996`
- name: `CngRsa32Compat_MD5Final`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009fe8`

## callees

- `0x18000b958`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18000b983`
- `bcrypt!BCryptDestroyHash` at `0x18000b983`
- `bcrypt!BCryptFinishHash` at `0x18000b96f`
- `bcrypt!BCryptFinishHash` at `0x18000b96f`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_MD5Final(__int64 a1)
{
  NTSTATUS result; // eax

  if ( BCryptFinishHash(*(BCRYPT_HASH_HANDLE *)a1, (PUCHAR)(a1 + 8), 0x10u, 0) < 0 )
    __fastfail(7u);
  result = BCryptDestroyHash(*(BCRYPT_HASH_HANDLE *)a1);
  *(_QWORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000b958  push    rbx
0x18000b95a  sub     rsp, 20h
0x18000b95e  xor     r9d, r9d; dwFlags
0x18000b961  lea     rdx, [rcx+8]; pbOutput
0x18000b965  mov     rbx, rcx
0x18000b968  mov     rcx, [rcx]; hHash
0x18000b96b  lea     r8d, [r9+10h]; cbOutput
0x18000b96f  call    cs:__imp_BCryptFinishHash
0x18000b975  test    eax, eax
0x18000b977  jns     short loc_18000B980
0x18000b979  mov     ecx, 7
0x18000b97e  int     29h; Win8: RtlFailFast(ecx)
0x18000b980  mov     rcx, [rbx]; hHash
0x18000b983  call    cs:__imp_BCryptDestroyHash
0x18000b989  mov     qword ptr [rbx], 0
0x18000b990  add     rsp, 20h
0x18000b994  pop     rbx
0x18000b995  retn
```
