# AvhdUtilities::CopyFileAcl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14006596c`
- end: `0x140065ab0`
- name: `?CopyFileAcl@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `324`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140094a00`

## callees

- `0x14006596c`
- `0x140065ab8`
- `0x14011ea40`
- `0x1401aaecc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140065a81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140065a81`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1400659e7`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1400659e7`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x140065a5c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x140065a5c`

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
0x14006596c  mov     [rsp+arg_10], rbx
0x140065971  mov     [rsp+arg_18], rsi
0x140065976  push    r14
0x140065978  sub     rsp, 70h
0x14006597c  mov     rax, cs:__security_cookie
0x140065983  xor     rax, rsp
0x140065986  mov     [rsp+78h+var_10], rax
0x14006598b  mov     rax, rdx
0x14006598e  mov     r14, rcx
0x140065991  mov     rsi, rcx
0x140065994  mov     [rsp+78h+var_30], rcx
0x140065999  xorps   xmm0, xmm0
0x14006599c  movups  xmmword ptr [rsp+78h+hMem], xmm0
0x1400659a1  mov     [rsp+78h+hMem], 0
0x1400659aa  cmp     qword ptr [rdx+18h], 7
0x1400659af  jbe     short loc_1400659B4
0x1400659b1  mov     rax, [rdx]
0x1400659b4  lea     rcx, [rsp+78h+hMem]
0x1400659b9  mov     [rsp+78h+ppSecurityDescriptor], rcx; ppSecurityDescriptor
0x1400659be  mov     [rsp+78h+ppSacl], 0; ppSacl
0x1400659c7  mov     [rsp+78h+ppDacl], 0; ppDacl
0x1400659d0  mov     [rsp+78h+ppsidGroup], 0; ppsidGroup
0x1400659d9  xor     r9d, r9d; ppsidOwner
0x1400659dc  lea     edx, [r9+1]; ObjectType
0x1400659e0  lea     r8d, [r9+4]; SecurityInfo
0x1400659e4  mov     rcx, rax; pObjectName
0x1400659e7  call    cs:__imp_GetNamedSecurityInfoW
0x1400659ee  nop     dword ptr [rax+rax+00h]
0x1400659f3  mov     ebx, eax
0x1400659f5  test    eax, eax
0x1400659f7  jle     short loc_140065A02
0x1400659f9  movzx   ebx, ax
0x1400659fc  or      ebx, 80070000h
0x140065a02  test    ebx, ebx
0x140065a04  js      short loc_140065A77
0x140065a06  lea     rcx, [rsp+78h+hMem]; this
0x140065a0b  call    ?MakeSelfRelative@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeSelfRelative(void)
0x140065a10  nop
0x140065a11  jmp     short loc_140065A23
0x140065a13  mov     ebx, [rsp+78h+var_38]
0x140065a17  test    ebx, ebx
0x140065a19  js      short loc_140065A77
0x140065a1b  mov     rsi, [rsp+78h+var_30]
0x140065a20  mov     r14, rsi
0x140065a23  lea     rcx, [rsp+78h+hMem]; this
0x140065a28  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x140065a2d  cmp     qword ptr [rsi+18h], 7
0x140065a32  jbe     short loc_140065A37
0x140065a34  mov     rsi, [r14]
0x140065a37  mov     [rsp+78h+ppSacl], 0; pSacl
0x140065a40  mov     [rsp+78h+ppDacl], rax; pDacl
0x140065a45  mov     [rsp+78h+ppsidGroup], 0; psidGroup
0x140065a4e  xor     r9d, r9d; psidOwner
0x140065a51  lea     edx, [r9+1]; ObjectType
0x140065a55  lea     r8d, [r9+4]; SecurityInfo
0x140065a59  mov     rcx, rsi; pObjectName
0x140065a5c  call    cs:__imp_SetNamedSecurityInfoW
0x140065a63  nop     dword ptr [rax+rax+00h]
0x140065a68  mov     ebx, eax
0x140065a6a  test    eax, eax
0x140065a6c  jle     short loc_140065A77
0x140065a6e  movzx   ebx, ax
0x140065a71  or      ebx, 80070000h
0x140065a77  mov     rcx, [rsp+78h+hMem]; hMem
0x140065a7c  test    rcx, rcx
0x140065a7f  jz      short loc_140065A8D
0x140065a81  call    cs:__imp_LocalFree
0x140065a88  nop     dword ptr [rax+rax+00h]
0x140065a8d  mov     eax, ebx
0x140065a8f  mov     rcx, [rsp+78h+var_10]
0x140065a94  xor     rcx, rsp; StackCookie
0x140065a97  call    __security_check_cookie
0x140065a9c  lea     r11, [rsp+78h+var_8]
0x140065aa1  mov     rbx, [r11+20h]
0x140065aa5  mov     rsi, [r11+28h]
0x140065aa9  mov     rsp, r11
0x140065aac  pop     r14
0x140065aae  retn
```
