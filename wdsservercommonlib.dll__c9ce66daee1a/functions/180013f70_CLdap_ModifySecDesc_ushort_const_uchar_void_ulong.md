# CLdap::ModifySecDesc(ushort const *,uchar,void *,ulong)

- ea: `0x180013f70`
- end: `0x18001406c`
- name: `?ModifySecDesc@CLdap@@QEAAKPEBGEPEAXK@Z`
- size: `252`
- prototype: `unsigned int __usercall@<eax>(CLdap *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int8@<r8b>, void *@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800139d0`
- `0x180014800`
- `0x18002f3e0`

## import_xrefs

- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x18001402b`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x18001402b`

## string_xrefs

- `0x180013fea`: `ntSecurityDescriptor`

## pseudocode

```c
unsigned int __fastcall CLdap::ModifySecDesc(LDAP **this, WCHAR *a2, char a3, void *a4, unsigned int a5)
{
  LDAP *v6; // rcx
  ULONG v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // eax
  _QWORD v12[3]; // [rsp+30h] [rbp-41h] BYREF
  char v13; // [rsp+48h] [rbp-29h]
  int v14; // [rsp+49h] [rbp-28h]
  __int16 v15; // [rsp+4Dh] [rbp-24h]
  char v16; // [rsp+4Fh] [rbp-22h]
  _DWORD v17[2]; // [rsp+50h] [rbp-21h] BYREF
  void *v18; // [rsp+58h] [rbp-19h]
  _QWORD v19[3]; // [rsp+60h] [rbp-11h] BYREF
  _QWORD v20[2]; // [rsp+78h] [rbp+7h] BYREF
  PLDAPControlW ServerControls[2]; // [rsp+88h] [rbp+17h] BYREF
  LDAPModW *mods[2]; // [rsp+98h] [rbp+27h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+37h] BYREF

  v18 = a4;
  v19[0] = 130;
  v23 = 0;
  mods[0] = (LDAPModW *)v19;
  mods[1] = 0;
  v20[0] = v17;
  v12[0] = L"1.2.840.113556.1.4.801";
  v12[2] = &v23;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  ServerControls[0] = (PLDAPControlW)v12;
  v17[0] = a5;
  v19[1] = L"ntSecurityDescriptor";
  v17[1] = 0;
  v20[1] = 0;
  ServerControls[1] = 0;
  BYTE4(v23) = a3;
  v6 = *this;
  v19[2] = v20;
  v12[1] = 5;
  v13 = 1;
  LODWORD(v23) = 16909104;
  v7 = ldap_modify_ext_sW(v6, a2, mods, ServerControls, 0);
  v10 = ElValidateWin32_5(v7, v8, v9, 0x3B6u);
  return CLdap::GetLdapErrorCode((CLdap *)this, v10);
}

```

## disassembly

```asm
0x180013f70  mov     [rsp-8+arg_10], rbx
0x180013f75  push    rbp
0x180013f76  lea     rbp, [rsp-4Fh]
0x180013f7b  sub     rsp, 0C0h
0x180013f82  mov     rax, cs:__security_cookie
0x180013f89  xor     rax, rsp
0x180013f8c  mov     [rbp+4Fh+var_10], rax
0x180013f90  mov     rbx, rcx
0x180013f93  mov     [rbp+4Fh+var_68], r9
0x180013f97  xor     ecx, ecx
0x180013f99  mov     [rbp+4Fh+var_60], 82h
0x180013fa1  mov     [rbp+4Fh+var_18], rcx
0x180013fa5  lea     rax, [rbp+4Fh+var_60]
0x180013fa9  mov     [rbp+4Fh+mods], rax
0x180013fad  lea     r9, [rbp+4Fh+ServerControls]; ServerControls
0x180013fb1  lea     rax, [rbp+4Fh+var_70]
0x180013fb5  mov     [rbp+4Fh+var_20], rcx
0x180013fb9  mov     [rbp+4Fh+var_48], rax
0x180013fbd  lea     rax, a12840113556148; "1.2.840.113556.1.4.801"
0x180013fc4  mov     [rbp+4Fh+var_90], rax
0x180013fc8  lea     rax, [rbp+4Fh+var_18]
0x180013fcc  mov     [rbp+4Fh+var_80], rax
0x180013fd0  xor     eax, eax
0x180013fd2  mov     [rbp+4Fh+var_77], eax
0x180013fd5  mov     [rbp+4Fh+var_73], ax
0x180013fd9  mov     [rbp+4Fh+var_71], al
0x180013fdc  lea     rax, [rbp+4Fh+var_90]
0x180013fe0  mov     [rbp+4Fh+ServerControls], rax
0x180013fe4  mov     eax, [rbp+4Fh+arg_20]
0x180013fe7  mov     [rbp+4Fh+var_70], eax
0x180013fea  lea     rax, aNtsecuritydesc; "ntSecurityDescriptor"
0x180013ff1  mov     [rbp+4Fh+var_58], rax
0x180013ff5  lea     rax, [rbp+4Fh+var_48]
0x180013ff9  mov     [rbp+4Fh+var_6C], ecx
0x180013ffc  mov     [rbp+4Fh+var_40], rcx
0x180014000  mov     [rbp+4Fh+var_30], rcx
0x180014004  mov     byte ptr [rbp+4Fh+var_18+4], r8b
0x180014008  lea     r8, [rbp+4Fh+mods]; mods
0x18001400c  mov     [rsp+0C0h+ClientControls], rcx; ClientControls
0x180014011  mov     rcx, [rbx]; ld
0x180014014  mov     [rbp+4Fh+var_50], rax
0x180014018  mov     [rbp+4Fh+var_88], 5
0x180014020  mov     [rbp+4Fh+var_78], 1
0x180014024  mov     dword ptr [rbp+4Fh+var_18], 1020330h
0x18001402b  call    cs:__imp_ldap_modify_ext_sW
0x180014032  nop     dword ptr [rax+rax+00h]
0x180014037  mov     ecx, eax
0x180014039  mov     r9d, 3B6h
0x18001403f  call    ElValidateWin32_5
0x180014044  mov     edx, eax; unsigned int
0x180014046  mov     rcx, rbx; this
0x180014049  call    ?GetLdapErrorCode@CLdap@@AEAAKK@Z; CLdap::GetLdapErrorCode(ulong)
0x18001404e  mov     rcx, [rbp+4Fh+var_10]
0x180014052  xor     rcx, rsp; StackCookie
0x180014055  call    __security_check_cookie
0x18001405a  mov     rbx, [rsp+0C0h+arg_10]
0x180014062  add     rsp, 0C0h
0x180014069  pop     rbp
0x18001406a  retn
```
