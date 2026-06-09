# CSecurityAttribute::SecurityAttributeBuild(void)

- ea: `0x140012818`
- end: `0x140012a7a`
- name: `?SecurityAttributeBuild@CSecurityAttribute@@AEAAJXZ`
- size: `610`
- prototype: `__int64 __fastcall(CSecurityAttribute *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011dcc`

## callees

- `0x140001264`
- `0x140001a63`
- `0x14000e280`
- `0x140011d18`
- `0x1400121f0`
- `0x140012320`
- `0x14001259c`
- `0x140012818`
- `0x140013490`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x14001294a`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14001294a`
- `ADVAPI32!InitializeAcl` at `0x140012965`
- `ADVAPI32!InitializeAcl` at `0x140012965`
- `ADVAPI32!AddAccessAllowedAce` at `0x140012982`
- `ADVAPI32!AddAccessAllowedAce` at `0x14001299f`
- `ADVAPI32!AddAccessAllowedAce` at `0x1400129bc`
- `ADVAPI32!AddAccessAllowedAce` at `0x140012982`
- `ADVAPI32!AddAccessAllowedAce` at `0x14001299f`
- `ADVAPI32!AddAccessAllowedAce` at `0x1400129bc`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1400129d5`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1400129d5`
- `KERNEL32!LocalFree` at `0x140012a67`
- `KERNEL32!LocalFree` at `0x140012a67`
- `KERNEL32!GetLastError` at `0x1400129e3`
- `KERNEL32!GetLastError` at `0x1400129e3`

## string_xrefs

- `0x1400129fa`: `Failed to build security attributes, error code %u`
- `0x140012837`: `Failed to allocate memory for ACL`
- `0x140012843`: `CSecurityAttribute::SecurityAttributeBuild`
- `0x1400128f8`: `CSecurityAttribute::SecurityAttributeBuild`
- `0x140012a06`: `CSecurityAttribute::SecurityAttributeBuild`
- `0x140012a53`: `CSecurityAttribute::SecurityAttributeBuild`
- `0x14001287a`: `Failed to allocate memory for security descriptor`
- `0x1400128aa`: `Failed to allocate memory for security attributes`
- `0x1400128ec`: `Failed to get administrator sid`
- `0x140012917`: `Failed to get owner sid`
- `0x140012933`: `Failed to get user sid`

## pseudocode

```c
__int64 __fastcall CSecurityAttribute::SecurityAttributeBuild(CSecurityAttribute *this)
{
  void *v2; // rax
  signed int AdminSid; // ebx
  _OWORD *v4; // rax
  _QWORD *v5; // rax
  signed int LastError; // eax
  HLOCAL v7; // rdi
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  v2 = operator new(*((int *)this + 12));
  *((_QWORD *)this + 4) = v2;
  if ( !v2 )
  {
    WusaLogDebugEventA(L"CSecurityAttribute::SecurityAttributeBuild", 270, "Failed to allocate memory for ACL");
LABEL_3:
    AdminSid = -2147024882;
    goto LABEL_26;
  }
  memset_0(v2, 0, *((int *)this + 12));
  v4 = operator new(0x28u);
  *((_QWORD *)this + 5) = v4;
  if ( !v4 )
  {
    WusaLogDebugEventA(
      L"CSecurityAttribute::SecurityAttributeBuild",
      274,
      "Failed to allocate memory for security descriptor");
    goto LABEL_3;
  }
  *v4 = 0;
  v4[1] = 0;
  *((_QWORD *)v4 + 4) = 0;
  v5 = operator new(0x18u);
  *(_QWORD *)this = v5;
  if ( !v5 )
  {
    WusaLogDebugEventA(
      L"CSecurityAttribute::SecurityAttributeBuild",
      278,
      "Failed to allocate memory for security attributes");
    goto LABEL_3;
  }
  *(_OWORD *)v5 = 0;
  v5[2] = 0;
  **(_DWORD **)this = 24;
  *(_QWORD *)(*(_QWORD *)this + 8LL) = *((_QWORD *)this + 5);
  *(_DWORD *)(*(_QWORD *)this + 16LL) = 0;
  AdminSid = CSecurityAttribute::GetAdminSid(this);
  if ( AdminSid >= 0 )
  {
    AdminSid = CSecurityAttribute::GetOwnerSid(this);
    if ( AdminSid >= 0 )
    {
      AdminSid = CSecurityAttribute::GetUserSid(this);
      if ( AdminSid >= 0 )
      {
        if ( InitializeSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)this + 5), 1u)
          && InitializeAcl(*((PACL *)this + 4), *((_DWORD *)this + 12), 2u)
          && AddAccessAllowedAce(*((PACL *)this + 4), 2u, 0x10000000u, *((PSID *)this + 1))
          && AddAccessAllowedAce(*((PACL *)this + 4), 2u, 0x10000000u, *((PSID *)this + 2))
          && AddAccessAllowedAce(*((PACL *)this + 4), 2u, 0x10000000u, *((PSID *)this + 3))
          && SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 5), 1, *((PACL *)this + 4), 0) )
        {
          return (unsigned int)AdminSid;
        }
        LastError = GetLastError();
        AdminSid = LastError;
        if ( LastError > 0 )
          AdminSid = (unsigned __int16)LastError | 0x80070000;
        if ( AdminSid >= 0 )
          AdminSid = -2147467259;
        WusaLogDebugEventA(
          L"CSecurityAttribute::SecurityAttributeBuild",
          308,
          "Failed to build security attributes, error code %u",
          (unsigned int)AdminSid);
      }
      else
      {
        WusaLogDebugEventA(L"CSecurityAttribute::SecurityAttributeBuild", 296, "Failed to get user sid");
      }
    }
    else
    {
      WusaLogDebugEventA(L"CSecurityAttribute::SecurityAttributeBuild", 293, "Failed to get owner sid");
    }
  }
  else
  {
    WusaLogDebugEventA(L"CSecurityAttribute::SecurityAttributeBuild", 290, "Failed to get administrator sid");
  }
LABEL_26:
  CSecurityAttribute::Clean(this);
  hMem = 0;
  WusaGetErrorMessage(AdminSid, (unsigned __int16 **)&hMem);
  v7 = hMem;
  WusaLogDebugEventA(
    L"CSecurityAttribute::SecurityAttributeBuild",
    318,
    "Exit with error code 0X%x (%ls)",
    AdminSid,
    (const wchar_t *)hMem);
  if ( v7 )
    LocalFree(v7);
  return (unsigned int)AdminSid;
}

```

## disassembly

```asm
0x140012818  mov     [rsp+arg_8], rbx
0x14001281d  push    rdi
0x14001281e  sub     rsp, 30h
0x140012822  mov     rdi, rcx
0x140012825  movsxd  rcx, dword ptr [rcx+30h]; Size
0x140012829  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001282e  mov     [rdi+20h], rax
0x140012832  test    rax, rax
0x140012835  jnz     short loc_140012859
0x140012837  lea     r8, aFailedToAlloca_16; "Failed to allocate memory for ACL"
0x14001283e  mov     edx, 10Eh
0x140012843  lea     rcx, aCsecurityattri_3; "CSecurityAttribute::SecurityAttributeBu"...
0x14001284a  call    WusaLogDebugEventA
0x14001284f  mov     ebx, 8007000Eh
0x140012854  jmp     loc_140012A1D
0x140012859  movsxd  r8, dword ptr [rdi+30h]; Size
0x14001285d  xor     edx, edx; Val
0x14001285f  mov     rcx, rax; void *
0x140012862  call    memset_0
0x140012867  mov     ecx, 28h ; '('; Size
0x14001286c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012871  mov     [rdi+28h], rax
0x140012875  test    rax, rax
0x140012878  jnz     short loc_140012888
0x14001287a  lea     r8, aFailedToAlloca_0; "Failed to allocate memory for security "...
0x140012881  mov     edx, 112h
0x140012886  jmp     short loc_140012843
0x140012888  xor     ecx, ecx
0x14001288a  xorps   xmm0, xmm0
0x14001288d  movups  xmmword ptr [rax], xmm0
0x140012890  movups  xmmword ptr [rax+10h], xmm0
0x140012894  lea     ebx, [rcx+18h]
0x140012897  mov     [rax+20h], rcx
0x14001289b  mov     ecx, ebx; Size
0x14001289d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400128a2  mov     [rdi], rax
0x1400128a5  test    rax, rax
0x1400128a8  jnz     short loc_1400128B8
0x1400128aa  lea     r8, aFailedToAlloca_11; "Failed to allocate memory for security "...
0x1400128b1  mov     edx, 116h
0x1400128b6  jmp     short loc_140012843
0x1400128b8  xor     ecx, ecx
0x1400128ba  xorps   xmm0, xmm0
0x1400128bd  movups  xmmword ptr [rax], xmm0
0x1400128c0  mov     [rax+10h], rcx
0x1400128c4  mov     rax, [rdi]
0x1400128c7  mov     [rax], ebx
0x1400128c9  mov     rcx, [rdi]
0x1400128cc  mov     rax, [rdi+28h]
0x1400128d0  mov     [rcx+8], rax
0x1400128d4  mov     rcx, rdi; this
0x1400128d7  mov     rax, [rdi]
0x1400128da  mov     dword ptr [rax+10h], 0
0x1400128e1  call    ?GetAdminSid@CSecurityAttribute@@AEAAJXZ; CSecurityAttribute::GetAdminSid(void)
0x1400128e6  mov     ebx, eax
0x1400128e8  test    eax, eax
0x1400128ea  jns     short loc_140012909
0x1400128ec  lea     r8, aFailedToGetAdm; "Failed to get administrator sid"
0x1400128f3  mov     edx, 122h
0x1400128f8  lea     rcx, aCsecurityattri_3; "CSecurityAttribute::SecurityAttributeBu"...
0x1400128ff  call    WusaLogDebugEventA
0x140012904  jmp     loc_140012A1D
0x140012909  mov     rcx, rdi; this
0x14001290c  call    ?GetOwnerSid@CSecurityAttribute@@AEAAJXZ; CSecurityAttribute::GetOwnerSid(void)
0x140012911  mov     ebx, eax
0x140012913  test    eax, eax
0x140012915  jns     short loc_140012925
0x140012917  lea     r8, aFailedToGetOwn_0; "Failed to get owner sid"
0x14001291e  mov     edx, 125h
0x140012923  jmp     short loc_1400128F8
0x140012925  mov     rcx, rdi; this
0x140012928  call    ?GetUserSid@CSecurityAttribute@@AEAAJXZ; CSecurityAttribute::GetUserSid(void)
0x14001292d  mov     ebx, eax
0x14001292f  test    eax, eax
0x140012931  jns     short loc_140012941
0x140012933  lea     r8, aFailedToGetUse; "Failed to get user sid"
0x14001293a  mov     edx, 128h
0x14001293f  jmp     short loc_1400128F8
0x140012941  mov     rcx, [rdi+28h]; pSecurityDescriptor
0x140012945  mov     edx, 1; dwRevision
0x14001294a  call    cs:__imp_InitializeSecurityDescriptor
0x140012950  test    eax, eax
0x140012952  jz      loc_1400129E3
0x140012958  mov     edx, [rdi+30h]; nAclLength
0x14001295b  mov     r8d, 2; dwAclRevision
0x140012961  mov     rcx, [rdi+20h]; pAcl
0x140012965  call    cs:__imp_InitializeAcl
0x14001296b  test    eax, eax
0x14001296d  jz      short loc_1400129E3
0x14001296f  mov     r9, [rdi+8]; pSid
0x140012973  mov     edx, 2; dwAceRevision
0x140012978  mov     rcx, [rdi+20h]; pAcl
0x14001297c  mov     r8d, 10000000h; AccessMask
0x140012982  call    cs:__imp_AddAccessAllowedAce
0x140012988  test    eax, eax
0x14001298a  jz      short loc_1400129E3
0x14001298c  mov     r9, [rdi+10h]; pSid
0x140012990  mov     edx, 2; dwAceRevision
0x140012995  mov     rcx, [rdi+20h]; pAcl
0x140012999  mov     r8d, 10000000h; AccessMask
0x14001299f  call    cs:__imp_AddAccessAllowedAce
0x1400129a5  test    eax, eax
0x1400129a7  jz      short loc_1400129E3
0x1400129a9  mov     r9, [rdi+18h]; pSid
0x1400129ad  mov     edx, 2; dwAceRevision
0x1400129b2  mov     rcx, [rdi+20h]; pAcl
0x1400129b6  mov     r8d, 10000000h; AccessMask
0x1400129bc  call    cs:__imp_AddAccessAllowedAce
0x1400129c2  test    eax, eax
0x1400129c4  jz      short loc_1400129E3
0x1400129c6  mov     r8, [rdi+20h]; pDacl
0x1400129ca  xor     r9d, r9d; bDaclDefaulted
0x1400129cd  mov     rcx, [rdi+28h]; pSecurityDescriptor
0x1400129d1  lea     edx, [r9+1]; bDaclPresent
0x1400129d5  call    cs:__imp_SetSecurityDescriptorDacl
0x1400129db  test    eax, eax
0x1400129dd  jnz     loc_140012A6D
0x1400129e3  call    cs:__imp_GetLastError
0x1400129e9  mov     ebx, eax
0x1400129eb  test    eax, eax
0x1400129ed  jle     short loc_1400129F8
0x1400129ef  movzx   ebx, ax
0x1400129f2  or      ebx, 80070000h
0x1400129f8  test    ebx, ebx
0x1400129fa  lea     r8, aFailedToBuildS_2; "Failed to build security attributes, er"...
0x140012a01  mov     eax, 80004005h
0x140012a06  lea     rcx, aCsecurityattri_3; "CSecurityAttribute::SecurityAttributeBu"...
0x140012a0d  cmovns  ebx, eax
0x140012a10  mov     edx, 134h
0x140012a15  mov     r9d, ebx
0x140012a18  call    WusaLogDebugEventA
0x140012a1d  mov     rcx, rdi; this
0x140012a20  call    ?Clean@CSecurityAttribute@@AEAAXXZ; CSecurityAttribute::Clean(void)
0x140012a25  lea     rdx, [rsp+38h+hMem]; unsigned __int16 **
0x140012a2a  mov     [rsp+38h+hMem], 0
0x140012a33  mov     ecx, ebx; dwMessageId
0x140012a35  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140012a3a  mov     rdi, [rsp+38h+hMem]
0x140012a3f  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140012a46  mov     r9d, ebx
0x140012a49  mov     [rsp+38h+var_18], rdi
0x140012a4e  mov     edx, 13Eh
0x140012a53  lea     rcx, aCsecurityattri_3; "CSecurityAttribute::SecurityAttributeBu"...
0x140012a5a  call    WusaLogDebugEventA
0x140012a5f  test    rdi, rdi
0x140012a62  jz      short loc_140012A6D
0x140012a64  mov     rcx, rdi; hMem
0x140012a67  call    cs:__imp_LocalFree
0x140012a6d  mov     eax, ebx
0x140012a6f  mov     rbx, [rsp+38h+arg_8]
0x140012a74  add     rsp, 30h
0x140012a78  pop     rdi
0x140012a79  retn
```
