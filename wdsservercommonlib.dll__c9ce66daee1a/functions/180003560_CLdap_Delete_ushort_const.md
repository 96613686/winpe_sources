# CLdap::Delete(ushort const *)

- ea: `0x180003560`
- end: `0x180003594`
- name: `?Delete@CLdap@@QEAAKPEBG@Z`
- size: `52`
- prototype: `unsigned int __fastcall(CLdap *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180004344`
- `0x1800139d0`

## import_xrefs

- `WLDAP32!__imp_ldap_delete_sW` at `0x18000356c`
- `WLDAP32!__imp_ldap_delete_sW` at `0x18000356c`

## pseudocode

```c
unsigned int __fastcall CLdap::Delete(LDAP **this, WCHAR *a2)
{
  ULONG v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // eax

  v3 = ldap_delete_sW(*this, a2);
  v6 = ElValidateWin32(v3, v4, v5, 436);
  return CLdap::GetLdapErrorCode((CLdap *)this, v6);
}

```

## disassembly

```asm
0x180003560  push    rbx
0x180003562  sub     rsp, 20h
0x180003566  mov     rbx, rcx
0x180003569  mov     rcx, [rcx]; ld
0x18000356c  call    cs:__imp_ldap_delete_sW
0x180003573  nop     dword ptr [rax+rax+00h]
0x180003578  mov     ecx, eax
0x18000357a  mov     r9d, 1B4h
0x180003580  call    ElValidateWin32
0x180003585  mov     edx, eax; unsigned int
0x180003587  mov     rcx, rbx; this
0x18000358a  add     rsp, 20h
0x18000358e  pop     rbx
0x18000358f  jmp     ?GetLdapErrorCode@CLdap@@AEAAKK@Z; CLdap::GetLdapErrorCode(ulong)
```
