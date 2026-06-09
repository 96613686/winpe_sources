# SrvAdminValidatePackedRelativeSecurityDescriptor

- ea: `0x1400537e8`
- end: `0x140053829`
- name: `SrvAdminValidatePackedRelativeSecurityDescriptor`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004d30`

## callees

- `0x1400537e8`

## import_xrefs

- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14005380f`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14005380f`

## pseudocode

```c
BOOLEAN __fastcall SrvAdminValidatePackedRelativeSecurityDescriptor(__int64 a1, unsigned int a2, unsigned __int64 a3)
{
  if ( !a3 )
    return 1;
  if ( a3 > 0xFFFFFFFF || (unsigned int)a3 >= a2 )
    return 0;
  return RtlValidRelativeSecurityDescriptor((PSECURITY_DESCRIPTOR)(a1 + (unsigned int)a3), a2 - a3, 0);
}

```

## disassembly

```asm
0x1400537e8  sub     rsp, 28h
0x1400537ec  mov     rax, rcx
0x1400537ef  test    r8, r8
0x1400537f2  jz      short loc_140053821
0x1400537f4  mov     ecx, 0FFFFFFFFh
0x1400537f9  cmp     r8, rcx
0x1400537fc  ja      short loc_140053825
0x1400537fe  cmp     r8d, edx
0x140053801  jnb     short loc_140053825
0x140053803  mov     ecx, r8d
0x140053806  sub     edx, r8d; SecurityDescriptorLength
0x140053809  add     rcx, rax; SecurityDescriptorInput
0x14005380c  xor     r8d, r8d; RequiredInformation
0x14005380f  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x140053816  nop     dword ptr [rax+rax+00h]
0x14005381b  add     rsp, 28h
0x14005381f  retn
0x140053821  mov     al, 1
0x140053823  jmp     short loc_14005381B
0x140053825  xor     al, al
0x140053827  jmp     short loc_14005381B
```
