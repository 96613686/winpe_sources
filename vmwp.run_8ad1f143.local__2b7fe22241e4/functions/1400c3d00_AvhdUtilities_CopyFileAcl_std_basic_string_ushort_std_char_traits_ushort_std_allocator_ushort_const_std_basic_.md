# AvhdUtilities::CopyFileAcl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400c3d00`
- end: `0x1400c3e44`
- name: `?CopyFileAcl@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `324`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140083dc0`

## callees

- `0x1400c3d00`
- `0x1400c3e4c`
- `0x140132960`
- `0x1401bbdec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3e15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3e15`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1400c3d7b`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1400c3d7b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1400c3df0`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1400c3df0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AvhdUtilities::CopyFileAcl(LPWSTR *pObjectName, const WCHAR *a2)
{
  const WCHAR *v2; // rax
  LPWSTR *v3; // r14
  LPWSTR v4; // rsi
  signed int NamedSecurityInfoW; // eax
  signed int v6; // ebx
  const char *v7; // r9
  struct _ACL *Dacl; // rax
  signed int v9; // eax
  int v11; // [rsp+40h] [rbp-38h]
  PSECURITY_DESCRIPTOR hMem[2]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = a2;
  v3 = pObjectName;
  v4 = (LPWSTR)pObjectName;
  *(_OWORD *)hMem = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v2 = *(const WCHAR **)a2;
  NamedSecurityInfoW = GetNamedSecurityInfoW(v2, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, hMem);
  v6 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    v6 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( v6 >= 0 )
  {
    try
    {
      Vml::VmSecurityDescriptor::MakeSelfRelative((Vml::VmSecurityDescriptor *)hMem);
    }
    catch ( ... )
    {
      v11 = wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x21F,
              (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
              v7);
      v6 = v11;
      if ( v11 < 0 )
        goto LABEL_13;
      v4 = (LPWSTR)pObjectName;
      v3 = pObjectName;
    }
    Dacl = (struct _ACL *)Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)hMem);
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *v3;
    v9 = SetNamedSecurityInfoW(v4, SE_FILE_OBJECT, 4u, 0, 0, Dacl, 0);
    v6 = v9;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
  }
LABEL_13:
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400c3d00  mov     [rsp+arg_10], rbx
0x1400c3d05  mov     [rsp+arg_18], rsi
0x1400c3d0a  push    r14
0x1400c3d0c  sub     rsp, 70h
0x1400c3d10  mov     rax, cs:__security_cookie
0x1400c3d17  xor     rax, rsp
0x1400c3d1a  mov     [rsp+78h+var_10], rax
0x1400c3d1f  mov     rax, rdx
0x1400c3d22  mov     r14, rcx
0x1400c3d25  mov     rsi, rcx
0x1400c3d28  mov     [rsp+78h+var_30], rcx
0x1400c3d2d  xorps   xmm0, xmm0
0x1400c3d30  movups  xmmword ptr [rsp+78h+hMem], xmm0
0x1400c3d35  mov     [rsp+78h+hMem], 0
0x1400c3d3e  cmp     qword ptr [rdx+18h], 7
0x1400c3d43  jbe     short loc_1400C3D48
0x1400c3d45  mov     rax, [rdx]
0x1400c3d48  lea     rcx, [rsp+78h+hMem]
0x1400c3d4d  mov     [rsp+78h+ppSecurityDescriptor], rcx; ppSecurityDescriptor
0x1400c3d52  mov     [rsp+78h+ppSacl], 0; ppSacl
0x1400c3d5b  mov     [rsp+78h+ppDacl], 0; ppDacl
0x1400c3d64  mov     [rsp+78h+ppsidGroup], 0; ppsidGroup
0x1400c3d6d  xor     r9d, r9d; ppsidOwner
0x1400c3d70  lea     edx, [r9+1]; ObjectType
0x1400c3d74  lea     r8d, [r9+4]; SecurityInfo
0x1400c3d78  mov     rcx, rax; pObjectName
0x1400c3d7b  call    cs:__imp_GetNamedSecurityInfoW
0x1400c3d82  nop     dword ptr [rax+rax+00h]
0x1400c3d87  mov     ebx, eax
0x1400c3d89  test    eax, eax
0x1400c3d8b  jle     short loc_1400C3D96
0x1400c3d8d  movzx   ebx, ax
0x1400c3d90  or      ebx, 80070000h
0x1400c3d96  test    ebx, ebx
0x1400c3d98  js      short loc_1400C3E0B
0x1400c3d9a  lea     rcx, [rsp+78h+hMem]; this
0x1400c3d9f  call    ?MakeSelfRelative@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeSelfRelative(void)
0x1400c3da4  nop
0x1400c3da5  jmp     short loc_1400C3DB7
0x1400c3da7  mov     ebx, [rsp+78h+var_38]
0x1400c3dab  test    ebx, ebx
0x1400c3dad  js      short loc_1400C3E0B
0x1400c3daf  mov     rsi, [rsp+78h+var_30]
0x1400c3db4  mov     r14, rsi
0x1400c3db7  lea     rcx, [rsp+78h+hMem]; this
0x1400c3dbc  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400c3dc1  cmp     qword ptr [rsi+18h], 7
0x1400c3dc6  jbe     short loc_1400C3DCB
0x1400c3dc8  mov     rsi, [r14]
0x1400c3dcb  mov     [rsp+78h+ppSacl], 0; pSacl
0x1400c3dd4  mov     [rsp+78h+ppDacl], rax; pDacl
0x1400c3dd9  mov     [rsp+78h+ppsidGroup], 0; psidGroup
0x1400c3de2  xor     r9d, r9d; psidOwner
0x1400c3de5  lea     edx, [r9+1]; ObjectType
0x1400c3de9  lea     r8d, [r9+4]; SecurityInfo
0x1400c3ded  mov     rcx, rsi; pObjectName
0x1400c3df0  call    cs:__imp_SetNamedSecurityInfoW
0x1400c3df7  nop     dword ptr [rax+rax+00h]
0x1400c3dfc  mov     ebx, eax
0x1400c3dfe  test    eax, eax
0x1400c3e00  jle     short loc_1400C3E0B
0x1400c3e02  movzx   ebx, ax
0x1400c3e05  or      ebx, 80070000h
0x1400c3e0b  mov     rcx, [rsp+78h+hMem]; hMem
0x1400c3e10  test    rcx, rcx
0x1400c3e13  jz      short loc_1400C3E21
0x1400c3e15  call    cs:__imp_LocalFree
0x1400c3e1c  nop     dword ptr [rax+rax+00h]
0x1400c3e21  mov     eax, ebx
0x1400c3e23  mov     rcx, [rsp+78h+var_10]
0x1400c3e28  xor     rcx, rsp; StackCookie
0x1400c3e2b  call    __security_check_cookie
0x1400c3e30  lea     r11, [rsp+78h+var_8]
0x1400c3e35  mov     rbx, [r11+20h]
0x1400c3e39  mov     rsi, [r11+28h]
0x1400c3e3d  mov     rsp, r11
0x1400c3e40  pop     r14
0x1400c3e42  retn
```
