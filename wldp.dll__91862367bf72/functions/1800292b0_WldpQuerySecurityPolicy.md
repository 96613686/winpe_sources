# WldpQuerySecurityPolicy

- ea: `0x1800292b0`
- end: `0x180029302`
- name: `WldpQuerySecurityPolicy`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800292b0`

## import_xrefs

- `ntdll!NtQuerySecurityPolicy` at `0x1800292e1`
- `ntdll!NtQuerySecurityPolicy` at `0x1800292e1`

## pseudocode

```c
__int64 __fastcall WldpQuerySecurityPolicy(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  int SecurityPolicy; // edx
  __int64 result; // rax

  if ( !a1 || !a2 || !a3 || !a4 || !a6 )
    return 2147942487LL;
  SecurityPolicy = NtQuerySecurityPolicy(a1, a2, a3, a4, a5, a6);
  result = 0;
  if ( SecurityPolicy < 0 )
    return SecurityPolicy | 0x10000000u;
  return result;
}

```

## disassembly

```asm
0x1800292b0  sub     rsp, 38h
0x1800292b4  test    rcx, rcx
0x1800292b7  jz      short loc_1800292F8
0x1800292b9  test    rdx, rdx
0x1800292bc  jz      short loc_1800292F8
0x1800292be  test    r8, r8
0x1800292c1  jz      short loc_1800292F8
0x1800292c3  test    r9, r9
0x1800292c6  jz      short loc_1800292F8
0x1800292c8  mov     rax, [rsp+38h+arg_28]
0x1800292cd  test    rax, rax
0x1800292d0  jz      short loc_1800292F8
0x1800292d2  mov     [rsp+38h+var_10], rax
0x1800292d7  mov     rax, [rsp+38h+arg_20]
0x1800292dc  mov     [rsp+38h+var_18], rax
0x1800292e1  call    cs:__imp_NtQuerySecurityPolicy
0x1800292e7  mov     ecx, eax
0x1800292e9  mov     edx, eax
0x1800292eb  bts     ecx, 1Ch
0x1800292ef  xor     eax, eax
0x1800292f1  test    edx, edx
0x1800292f3  cmovs   eax, ecx
0x1800292f6  jmp     short loc_1800292FD
0x1800292f8  mov     eax, 80070057h
0x1800292fd  add     rsp, 38h
0x180029301  retn
```
