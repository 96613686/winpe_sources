# Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)

- ea: `0x18004b9d0`
- end: `0x18004ba93`
- name: `?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z`
- size: `195`
- prototype: `void __fastcall(Vml::VmAcl *__hidden this, void *, unsigned int, unsigned int, enum _ACCESS_MODE)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004ba9c`

## callees

- `0x180002f50`
- `0x180022d10`
- `0x18004b9d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba56`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004ba37`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004ba37`

## string_xrefs

- `0x18004ba7e`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmAcl::UpdateAccess(struct _ACL **this, WCHAR *a2, DWORD a3, DWORD a4, enum _ACCESS_MODE a5)
{
  struct _ACL *v6; // r8
  DWORD v7; // eax
  struct _ACL *v8; // rcx
  PACL NewAcl; // [rsp+20h] [rbp-40h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+28h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  pListOfExplicitEntries.grfAccessPermissions = a3;
  v6 = *this;
  pListOfExplicitEntries.grfInheritance = a4;
  pListOfExplicitEntries.Trustee.ptstrName = a2;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 28);
  pListOfExplicitEntries.grfAccessMode = a5;
  NewAcl = 0;
  v7 = SetEntriesInAclW(1u, &pListOfExplicitEntries, v6, &NewAcl);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1713,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)v7,
      (unsigned int)NewAcl);
  v8 = *this;
  *this = NewAcl;
  if ( v8 )
    LocalFree(v8);
}

```

## disassembly

```asm
0x18004b9d0  mov     [rsp-8+arg_8], rbx
0x18004b9d5  push    rbp
0x18004b9d6  mov     rbp, rsp
0x18004b9d9  sub     rsp, 60h
0x18004b9dd  mov     rax, cs:__security_cookie
0x18004b9e4  xor     rax, rsp
0x18004b9e7  mov     [rbp+var_8], rax
0x18004b9eb  mov     eax, [rbp+arg_20]
0x18004b9ee  mov     rbx, rcx
0x18004b9f1  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], r8d
0x18004b9f5  mov     r8, [rcx]; OldAcl
0x18004b9f8  mov     ecx, 1; cCountOfExplicitEntries
0x18004b9fd  mov     [rbp+pListOfExplicitEntries.grfInheritance], r9d
0x18004ba01  lea     r9, [rbp+NewAcl]; NewAcl
0x18004ba05  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rdx
0x18004ba09  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004ba0d  mov     dword ptr [rbp+pListOfExplicitEntries+0Ch], 0
0x18004ba14  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 0
0x18004ba1c  mov     [rbp+pListOfExplicitEntries.grfAccessMode], eax
0x18004ba1f  mov     [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], 0
0x18004ba27  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], 0
0x18004ba2f  mov     [rbp+NewAcl], 0
0x18004ba37  call    cs:__imp_SetEntriesInAclW
0x18004ba3e  nop     dword ptr [rax+rax+00h]
0x18004ba43  test    eax, eax
0x18004ba45  jnz     short loc_18004BA7A
0x18004ba47  mov     rcx, [rbx]; hMem
0x18004ba4a  mov     rax, [rbp+NewAcl]
0x18004ba4e  mov     [rbx], rax
0x18004ba51  test    rcx, rcx
0x18004ba54  jz      short loc_18004BA62
0x18004ba56  call    cs:__imp_LocalFree
0x18004ba5d  nop     dword ptr [rax+rax+00h]
0x18004ba62  mov     rcx, [rbp+var_8]
0x18004ba66  xor     rcx, rsp; StackCookie
0x18004ba69  call    __security_check_cookie
0x18004ba6e  mov     rbx, [rsp+60h+arg_8]
0x18004ba73  add     rsp, 60h
0x18004ba77  pop     rbp
0x18004ba78  retn
0x18004ba7a  mov     rcx, [rbp+8]; this
0x18004ba7e  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18004ba85  mov     r9d, eax; char *
0x18004ba88  mov     edx, 1713h; void *
0x18004ba8d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
