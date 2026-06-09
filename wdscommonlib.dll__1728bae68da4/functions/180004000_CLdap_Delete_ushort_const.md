# CLdap::Delete(ushort const *)

- ea: `0x180004000`
- end: `0x180004034`
- name: `?Delete@CLdap@@QEAAKPEBG@Z`
- size: `52`
- prototype: `unsigned int __fastcall(CLdap *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180004df4`
- `0x180014690`

## import_xrefs

- `WLDAP32!__imp_ldap_delete_sW` at `0x18000400c`
- `WLDAP32!__imp_ldap_delete_sW` at `0x18000400c`

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
0x180004000  push    rbx
0x180004002  sub     rsp, 20h
0x180004006  mov     rbx, rcx
0x180004009  mov     rcx, [rcx]; ld
0x18000400c  call    cs:__imp_ldap_delete_sW
0x180004013  nop     dword ptr [rax+rax+00h]
0x180004018  mov     ecx, eax
0x18000401a  mov     r9d, 1B4h
0x180004020  call    ElValidateWin32
0x180004025  mov     edx, eax; unsigned int
0x180004027  mov     rcx, rbx; this
0x18000402a  add     rsp, 20h
0x18000402e  pop     rbx
0x18000402f  jmp     ?GetLdapErrorCode@CLdap@@AEAAKK@Z; CLdap::GetLdapErrorCode(ulong)
```
