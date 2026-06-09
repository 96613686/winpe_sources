# CSecurityInformation::ReadObjectSecurity(ushort const *,ulong,void * *)

- ea: `0x18000c6a0`
- end: `0x18000c704`
- name: `?ReadObjectSecurity@CSecurityInformation@@MEAAJPEBGKPEAPEAX@Z`
- size: `100`
- prototype: `int __fastcall(SE_OBJECT_TYPE *this, const unsigned __int16 *, SECURITY_INFORMATION, void **ppSecurityDescriptor)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000c6a0`

## import_xrefs

- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000c6e6`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000c6e6`

## pseudocode

```c
int __fastcall CSecurityInformation::ReadObjectSecurity(
        SE_OBJECT_TYPE *this,
        const unsigned __int16 *a2,
        SECURITY_INFORMATION a3,
        void **ppSecurityDescriptor)
{
  int result; // eax

  if ( !ppSecurityDescriptor || !a2 )
    return -2147467261;
  if ( !a3 )
    return -2147024809;
  result = GetNamedSecurityInfoW(a2, this[13], a3, 0, 0, 0, 0, ppSecurityDescriptor);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000c6a0  sub     rsp, 48h
0x18000c6a4  mov     rax, rdx
0x18000c6a7  test    r9, r9
0x18000c6aa  jz      short loc_18000C6FA
0x18000c6ac  test    rax, rax
0x18000c6af  jz      short loc_18000C6FA
0x18000c6b1  test    r8d, r8d
0x18000c6b4  jnz     short loc_18000C6BD
0x18000c6b6  mov     eax, 80070057h
0x18000c6bb  jmp     short loc_18000C6FF
0x18000c6bd  mov     edx, [rcx+34h]; ObjectType
0x18000c6c0  mov     rcx, rax; pObjectName
0x18000c6c3  mov     [rsp+48h+ppSecurityDescriptor], r9; ppSecurityDescriptor
0x18000c6c8  xor     r9d, r9d; ppsidOwner
0x18000c6cb  mov     [rsp+48h+ppSacl], 0; ppSacl
0x18000c6d4  mov     [rsp+48h+ppDacl], 0; ppDacl
0x18000c6dd  mov     [rsp+48h+ppsidGroup], 0; ppsidGroup
0x18000c6e6  call    cs:__imp_GetNamedSecurityInfoW
0x18000c6ec  test    eax, eax
0x18000c6ee  jle     short loc_18000C6FF
0x18000c6f0  movzx   eax, ax
0x18000c6f3  or      eax, 80070000h
0x18000c6f8  jmp     short loc_18000C6FF
0x18000c6fa  mov     eax, 80004003h
0x18000c6ff  add     rsp, 48h
0x18000c703  retn
```
