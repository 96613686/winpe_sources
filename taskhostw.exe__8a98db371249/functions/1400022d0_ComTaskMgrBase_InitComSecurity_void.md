# ComTaskMgrBase::InitComSecurity(void)

- ea: `0x1400022d0`
- end: `0x14000289f`
- name: `?InitComSecurity@ComTaskMgrBase@@CAJXZ`
- size: `1487`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140001968`

## callees

- `0x140001fb0`
- `0x140002040`
- `0x1400022d0`
- `0x1400028b0`
- `0x140002970`
- `0x140002b40`
- `0x140002c50`
- `0x140002ce0`
- `0x140002df0`
- `0x140003130`
- `0x1400068f0`
- `0x140007298`
- `0x1400072bc`
- `0x140007468`
- `0x140009430`
- `0x14000a2d0`
- `0x14000c010`

## import_xrefs

- `msvcrt!free` at `0x1400023a4`
- `msvcrt!free` at `0x14000242d`
- `msvcrt!free` at `0x1400024d8`
- `msvcrt!free` at `0x140002561`
- `msvcrt!free` at `0x1400026d1`
- `msvcrt!free` at `0x140002777`
- `msvcrt!free` at `0x140002789`
- `msvcrt!free` at `0x1400027da`
- `msvcrt!free` at `0x1400027ff`
- `msvcrt!free` at `0x14000284d`
- `msvcrt!free` at `0x14000287b`
- `msvcrt!free` at `0x1400023a4`
- `msvcrt!free` at `0x14000242d`
- `msvcrt!free` at `0x1400024d8`
- `msvcrt!free` at `0x140002561`
- `msvcrt!free` at `0x1400026d1`
- `msvcrt!free` at `0x140002777`
- `msvcrt!free` at `0x140002789`
- `msvcrt!free` at `0x1400027da`
- `msvcrt!free` at `0x1400027ff`
- `msvcrt!free` at `0x14000284d`
- `msvcrt!free` at `0x14000287b`
- `msvcrt!malloc` at `0x140002375`
- `msvcrt!malloc` at `0x1400023e6`
- `msvcrt!malloc` at `0x1400024a9`
- `msvcrt!malloc` at `0x14000251a`
- `msvcrt!malloc` at `0x1400026a2`
- `msvcrt!malloc` at `0x14000270f`
- `msvcrt!malloc` at `0x140002375`
- `msvcrt!malloc` at `0x1400023e6`
- `msvcrt!malloc` at `0x1400024a9`
- `msvcrt!malloc` at `0x14000251a`
- `msvcrt!malloc` at `0x1400026a2`
- `msvcrt!malloc` at `0x14000270f`
- `msvcrt!memcpy_s` at `0x140002736`
- `msvcrt!memcpy_s` at `0x140002736`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400023ca`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400024fe`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400023ca`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400024fe`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x140002360`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x140002360`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400023dc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002510`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400023dc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002510`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140002494`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140002494`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x14000254e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x14000254e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14000268d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14000268d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140002763`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140002763`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14000238e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400024c2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400026bb`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14000238e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400024c2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400026bb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140002401`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140002535`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140002401`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140002535`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140002623`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140002623`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x14000241a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x14000241a`
- `ntdll!RtlIsMultiSessionSku` at `0x140002601`
- `ntdll!RtlIsMultiSessionSku` at `0x140002601`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400027be`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400027be`

## pseudocode

```c
__int64 ComTaskMgrBase::InitComSecurity(void)
{
  BOOL v0; // ebx
  void *v1; // rax
  signed int Error; // ebx
  size_t LengthSid; // rsi
  void *v4; // rax
  void *v5; // rdi
  PSECURITY_DESCRIPTOR v6; // rcx
  void *v7; // rax
  signed int v8; // ebx
  size_t v9; // rsi
  void *v10; // rax
  void *v11; // rdi
  const unsigned __int16 *v12; // r8
  PSECURITY_DESCRIPTOR v13; // rcx
  void *v14; // rax
  signed int v15; // ebx
  unsigned int Length; // esi
  struct _ACL *v17; // rdi
  const struct _ACL *PACL; // rax
  errno_t v19; // eax
  signed int v20; // ebx
  unsigned int v21; // ebx
  signed int v23; // ebx
  signed int v24; // ebx
  WINBOOL bOwnerDefaulted; // [rsp+50h] [rbp-B0h] BYREF
  void **v26; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+60h] [rbp-A0h]
  PSID pOwner; // [rsp+68h] [rbp-98h] BYREF
  void **v29; // [rsp+70h] [rbp-90h] BYREF
  void *Block; // [rsp+78h] [rbp-88h]
  char v31; // [rsp+80h] [rbp-80h]
  int v32; // [rsp+84h] [rbp-7Ch]
  __int128 v33; // [rsp+88h] [rbp-78h] BYREF
  __int64 v34; // [rsp+98h] [rbp-68h]
  int v35; // [rsp+A0h] [rbp-60h]
  PACL pDacl; // [rsp+A8h] [rbp-58h] BYREF
  struct _SID v37; // [rsp+B0h] [rbp-50h] BYREF
  char v38; // [rsp+FCh] [rbp-4h]
  _BYTE v39[128]; // [rsp+130h] [rbp+30h] BYREF

  v26 = &ATL::CSecurityDesc::`vftable';
  pSecurityDescriptor = 0;
  v0 = 1;
  ATL::CSid::CSid((ATL::CSid *)&v37, (struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority, 1u, 10);
  pOwner = 0;
  v1 = malloc(0x28u);
  pSecurityDescriptor = v1;
  if ( !v1 )
    goto LABEL_51;
  if ( !InitializeSecurityDescriptor(v1, 1u) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(pSecurityDescriptor);
    pSecurityDescriptor = 0;
    ATL::PrivateAtlThrow(Error);
  }
  pOwner = 0;
  if ( !v38 || !IsValidSid(v37.SubAuthority) )
    ATL::PrivateAtlThrow(-2147467259);
  LengthSid = GetLengthSid(v37.SubAuthority);
  v4 = malloc(LengthSid);
  v5 = v4;
  if ( !v4 )
LABEL_51:
    ATL::PrivateAtlThrow(-2147024882);
  if ( !CopySid(LengthSid, v4, v37.SubAuthority) || !SetSecurityDescriptorOwner(pSecurityDescriptor, v5, 0) )
  {
    v24 = ATL::AtlHresultFromLastError();
    free(v5);
    ATL::PrivateAtlThrow(v24);
  }
  free(pOwner);
  ATL::CSid::~CSid((ATL::CSid *)&v37);
  ATL::CSid::CSid((ATL::CSid *)&v37, (struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority, 2u, 32, 544);
  v6 = pSecurityDescriptor;
  if ( pSecurityDescriptor )
  {
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)&v26);
    v6 = pSecurityDescriptor;
  }
  pOwner = 0;
  if ( v6 )
  {
    bOwnerDefaulted = 0;
    if ( !GetSecurityDescriptorGroup(v6, &pOwner, &bOwnerDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    v7 = malloc(0x28u);
    pSecurityDescriptor = v7;
    if ( !v7 )
      goto LABEL_48;
    if ( !InitializeSecurityDescriptor(v7, 1u) )
    {
      v8 = ATL::AtlHresultFromLastError();
      free(pSecurityDescriptor);
      pSecurityDescriptor = 0;
      ATL::PrivateAtlThrow(v8);
    }
    pOwner = 0;
  }
  if ( !v38 || !IsValidSid(v37.SubAuthority) )
    ATL::PrivateAtlThrow(-2147467259);
  v9 = GetLengthSid(v37.SubAuthority);
  v10 = malloc(v9);
  v11 = v10;
  if ( !v10 )
LABEL_48:
    ATL::PrivateAtlThrow(-2147024882);
  if ( !CopySid(v9, v10, v37.SubAuthority) || !SetSecurityDescriptorGroup(pSecurityDescriptor, v11, 0) )
  {
    v23 = ATL::AtlHresultFromLastError();
    free(v11);
    ATL::PrivateAtlThrow(v23);
  }
  free(pOwner);
  ATL::CSid::~CSid((ATL::CSid *)&v37);
  Block = 0;
  v31 = 0;
  v32 = 2;
  v29 = &ATL::CDacl::`vftable';
  v33 = 0;
  v34 = 0;
  v35 = 0;
  ATL::CSid::CSid((ATL::CSid *)&v37, (struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority, 1u, 10);
  ATL::CDacl::AddAllowedAce((ATL::CDacl *)&v29, (const struct ATL::CSid *)&v37);
  ATL::CSid::~CSid((ATL::CSid *)&v37);
  ATL::CSid::CSid((ATL::CSid *)&v37, (struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority, 1u, 18);
  ATL::CDacl::AddAllowedAce((ATL::CDacl *)&v29, (const struct ATL::CSid *)&v37);
  ATL::CSid::~CSid((ATL::CSid *)&v37);
  if ( !(unsigned __int8)RtlIsMultiSessionSku() )
  {
    bOwnerDefaulted = 68;
    if ( CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, &v37, (DWORD *)&bOwnerDefaulted) )
    {
      ATL::CSid::CSid((ATL::CSid *)v39, &v37, v12);
      ATL::CDacl::AddAllowedAce((ATL::CDacl *)&v29, (const struct ATL::CSid *)v39);
      ATL::CSid::~CSid((ATL::CSid *)v39);
    }
  }
  v13 = pSecurityDescriptor;
  if ( pSecurityDescriptor )
  {
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)&v26);
    v13 = pSecurityDescriptor;
  }
  pDacl = 0;
  if ( v13 )
  {
    bOwnerDefaulted = 0;
    LODWORD(pOwner) = 0;
    if ( !GetSecurityDescriptorDacl(v13, (LPBOOL)&pOwner, &pDacl, &bOwnerDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    v14 = malloc(0x28u);
    pSecurityDescriptor = v14;
    if ( !v14 )
      goto LABEL_45;
    if ( !InitializeSecurityDescriptor(v14, 1u) )
    {
      v15 = ATL::AtlHresultFromLastError();
      free(pSecurityDescriptor);
      pSecurityDescriptor = 0;
      ATL::PrivateAtlThrow(v15);
    }
  }
  if ( v31 || !((unsigned int (__fastcall *)(void ***))v29[1])(&v29) )
  {
    v17 = 0;
    goto LABEL_39;
  }
  Length = ATL::CAcl::GetLength((ATL::CAcl *)&v29);
  v17 = (struct _ACL *)malloc(Length);
  if ( !v17 )
LABEL_45:
    ATL::PrivateAtlThrow(-2147024882);
  PACL = ATL::CAcl::GetPACL((ATL::CAcl *)&v29);
  v19 = memcpy_s(v17, Length, PACL, Length);
  ATL::AtlCrtErrorCheck(v19);
LABEL_39:
  if ( !v31 && !v17 )
    v0 = 0;
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, v0, v17, 0) )
  {
    v20 = ATL::AtlHresultFromLastError();
    free(v17);
    ATL::PrivateAtlThrow(v20);
  }
  free(pDacl);
  v21 = CoInitializeSecurity(pSecurityDescriptor, -1, 0, 0, 6u, 2u, 0, 0, 0);
  v29 = &ATL::CDacl::`vftable';
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::SetCount(&v33);
  free(Block);
  Block = 0;
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>((__int64)&v33);
  v29 = &ATL::CAcl::`vftable';
  free(Block);
  v26 = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v26);
  return v21;
}

```

## disassembly

```asm
0x1400022d0  push    rbp
0x1400022d2  push    rbx
0x1400022d3  push    rsi
0x1400022d4  push    rdi
0x1400022d5  push    r12
0x1400022d7  push    r14
0x1400022d9  push    r15
0x1400022db  lea     rbp, [rsp-0C0h]
0x1400022e3  sub     rsp, 1C0h
0x1400022ea  mov     rax, cs:__security_cookie
0x1400022f1  xor     rax, rsp
0x1400022f4  mov     [rbp+0F0h+var_40], rax
0x1400022fb  xor     r14d, r14d
0x1400022fe  lea     r15, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x140002305  mov     [rsp+1F0h+var_198], r15
0x14000230a  mov     [rsp+1F0h+pSecurityDescriptor], r14
0x14000230f  mov     ebx, 1
0x140002314  mov     r9d, 0Ah
0x14000231a  mov     r8d, ebx; unsigned __int8
0x14000231d  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x140002324  lea     rcx, [rbp+0F0h+var_140]; this
0x140002328  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x14000232d  nop
0x14000232e  mov     rcx, [rsp+1F0h+pSecurityDescriptor]
0x140002333  test    rcx, rcx
0x140002336  jz      short loc_140002347
0x140002338  lea     rcx, [rsp+1F0h+var_198]; this
0x14000233d  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x140002342  mov     rcx, [rsp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x140002347  mov     [rsp+1F0h+pOwner], r14
0x14000234c  test    rcx, rcx
0x14000234f  jz      short loc_140002370
0x140002351  mov     [rsp+1F0h+bOwnerDefaulted], r14d
0x140002356  lea     r8, [rsp+1F0h+bOwnerDefaulted]; lpbOwnerDefaulted
0x14000235b  lea     rdx, [rsp+1F0h+pOwner]; pOwner
0x140002360  call    cs:__imp_GetSecurityDescriptorOwner
0x140002366  test    eax, eax
0x140002368  jnz     short loc_1400023BC
0x14000236a  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140002370  mov     ecx, 28h ; '('; Size
0x140002375  call    cs:__imp_malloc
0x14000237b  mov     [rsp+1F0h+pSecurityDescriptor], rax
0x140002380  test    rax, rax
0x140002383  jz      loc_140002894
0x140002389  mov     edx, ebx; dwRevision
0x14000238b  mov     rcx, rax; pSecurityDescriptor
0x14000238e  call    cs:__imp_InitializeSecurityDescriptor
0x140002394  test    eax, eax
0x140002396  jnz     short loc_1400023B7
0x140002398  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000239d  mov     ebx, eax
0x14000239f  mov     rcx, [rsp+1F0h+pSecurityDescriptor]; Block
0x1400023a4  call    cs:__imp_free
0x1400023aa  mov     [rsp+1F0h+pSecurityDescriptor], r14
0x1400023af  mov     ecx, ebx; int
0x1400023b1  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1400023b7  mov     [rsp+1F0h+pOwner], r14
0x1400023bc  cmp     [rbp+0F0h+var_F4], 0
0x1400023c0  jz      loc_140002889
0x1400023c6  lea     rcx, [rbp+0F0h+var_140.SubAuthority]; pSid
0x1400023ca  call    cs:__imp_IsValidSid
0x1400023d0  test    eax, eax
0x1400023d2  jz      loc_140002889
0x1400023d8  lea     rcx, [rbp+0F0h+var_140.SubAuthority]; pSid
0x1400023dc  call    cs:__imp_GetLengthSid
0x1400023e2  mov     esi, eax
0x1400023e4  mov     ecx, eax; Size
0x1400023e6  call    cs:__imp_malloc
0x1400023ec  mov     rdi, rax
0x1400023ef  test    rax, rax
0x1400023f2  jz      loc_140002894
0x1400023f8  lea     r8, [rbp+0F0h+var_140.SubAuthority]; pSourceSid
0x1400023fc  mov     rdx, rax; pDestinationSid
0x1400023ff  mov     ecx, esi; nDestinationSidLength
0x140002401  call    cs:__imp_CopySid
0x140002407  test    eax, eax
0x140002409  jz      loc_140002871
0x14000240f  xor     r8d, r8d; bOwnerDefaulted
0x140002412  mov     rdx, rdi; pOwner
0x140002415  mov     rcx, [rsp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x14000241a  call    cs:__imp_SetSecurityDescriptorOwner
0x140002420  test    eax, eax
0x140002422  jz      loc_140002871
0x140002428  mov     rcx, [rsp+1F0h+pOwner]; Block
0x14000242d  call    cs:__imp_free
0x140002433  nop
0x140002434  lea     rcx, [rbp+0F0h+var_140]; this
0x140002438  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000243d  mov     [rsp+1F0h+dwAuthnLevel], 220h
0x140002445  mov     r9d, 20h ; ' '
0x14000244b  mov     r8d, 2; unsigned __int8
0x140002451  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x140002458  lea     rcx, [rbp+0F0h+var_140]; this
0x14000245c  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x140002461  nop
0x140002462  mov     rcx, [rsp+1F0h+pSecurityDescriptor]
0x140002467  test    rcx, rcx
0x14000246a  jz      short loc_14000247B
0x14000246c  lea     rcx, [rsp+1F0h+var_198]; this
0x140002471  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x140002476  mov     rcx, [rsp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x14000247b  mov     [rsp+1F0h+pOwner], r14
0x140002480  test    rcx, rcx
0x140002483  jz      short loc_1400024A4
0x140002485  mov     [rsp+1F0h+bOwnerDefaulted], r14d
0x14000248a  lea     r8, [rsp+1F0h+bOwnerDefaulted]; lpbGroupDefaulted
0x14000248f  lea     rdx, [rsp+1F0h+pOwner]; pGroup
0x140002494  call    cs:__imp_GetSecurityDescriptorGroup
0x14000249a  test    eax, eax
0x14000249c  jnz     short loc_1400024F0
0x14000249e  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1400024a4  mov     ecx, 28h ; '('; Size
0x1400024a9  call    cs:__imp_malloc
0x1400024af  mov     [rsp+1F0h+pSecurityDescriptor], rax
0x1400024b4  test    rax, rax
0x1400024b7  jz      loc_140002866
0x1400024bd  mov     edx, ebx; dwRevision
0x1400024bf  mov     rcx, rax; pSecurityDescriptor
0x1400024c2  call    cs:__imp_InitializeSecurityDescriptor
0x1400024c8  test    eax, eax
0x1400024ca  jnz     short loc_1400024EB
0x1400024cc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400024d1  mov     ebx, eax
0x1400024d3  mov     rcx, [rsp+1F0h+pSecurityDescriptor]; Block
0x1400024d8  call    cs:__imp_free
0x1400024de  mov     [rsp+1F0h+pSecurityDescriptor], r14
0x1400024e3  mov     ecx, ebx; int
0x1400024e5  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1400024eb  mov     [rsp+1F0h+pOwner], r14
0x1400024f0  cmp     [rbp+0F0h+var_F4], 0
0x1400024f4  jz      loc_14000285B
0x1400024fa  lea     rcx, [rbp+0F0h+var_140.SubAuthority]; pSid
0x1400024fe  call    cs:__imp_IsValidSid
0x140002504  test    eax, eax
0x140002506  jz      loc_14000285B
0x14000250c  lea     rcx, [rbp+0F0h+var_140.SubAuthority]; pSid
0x140002510  call    cs:__imp_GetLengthSid
0x140002516  mov     esi, eax
0x140002518  mov     ecx, eax; Size
0x14000251a  call    cs:__imp_malloc
0x140002520  mov     rdi, rax
0x140002523  test    rax, rax
0x140002526  jz      loc_140002866
0x14000252c  lea     r8, [rbp+0F0h+var_140.SubAuthority]; pSourceSid
0x140002530  mov     rdx, rax; pDestinationSid
0x140002533  mov     ecx, esi; nDestinationSidLength
0x140002535  call    cs:__imp_CopySid
0x14000253b  test    eax, eax
0x14000253d  jz      loc_140002843
0x140002543  xor     r8d, r8d; bGroupDefaulted
0x140002546  mov     rdx, rdi; pGroup
0x140002549  mov     rcx, [rsp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x14000254e  call    cs:__imp_SetSecurityDescriptorGroup
0x140002554  test    eax, eax
0x140002556  jz      loc_140002843
0x14000255c  mov     rcx, [rsp+1F0h+pOwner]; Block
0x140002561  call    cs:__imp_free
0x140002567  nop
0x140002568  lea     rcx, [rbp+0F0h+var_140]; this
0x14000256c  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140002571  mov     [rsp+1F0h+Block], r14
0x140002576  mov     [rbp+0F0h+var_170], 0
0x14000257a  mov     [rbp+0F0h+var_16C], 2
0x140002581  lea     r12, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x140002588  mov     [rsp+1F0h+var_180], r12
0x14000258d  xorps   xmm0, xmm0
0x140002590  movdqu  [rbp+0F0h+var_168], xmm0
0x140002595  mov     [rbp+0F0h+var_158], r14
0x140002599  mov     [rbp+0F0h+var_150], r14d
0x14000259d  mov     r9d, 0Ah
0x1400025a3  mov     r8d, ebx; unsigned __int8
0x1400025a6  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x1400025ad  lea     rcx, [rbp+0F0h+var_140]; this
0x1400025b1  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x1400025b6  nop
0x1400025b7  lea     rdx, [rbp+0F0h+var_140]; struct ATL::CSid *
0x1400025bb  lea     rcx, [rsp+1F0h+var_180]; this
0x1400025c0  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x1400025c5  nop
0x1400025c6  lea     rcx, [rbp+0F0h+var_140]; this
0x1400025ca  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1400025cf  mov     r9d, 12h
0x1400025d5  mov     r8d, ebx; unsigned __int8
0x1400025d8  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x1400025df  lea     rcx, [rbp+0F0h+var_140]; this
0x1400025e3  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x1400025e8  nop
0x1400025e9  lea     rdx, [rbp+0F0h+var_140]; struct ATL::CSid *
0x1400025ed  lea     rcx, [rsp+1F0h+var_180]; this
0x1400025f2  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x1400025f7  nop
0x1400025f8  lea     rcx, [rbp+0F0h+var_140]; this
0x1400025fc  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140002601  call    cs:__imp_RtlIsMultiSessionSku
0x140002607  test    al, al
0x140002609  jnz     short loc_140002653
0x14000260b  mov     [rsp+1F0h+bOwnerDefaulted], 44h ; 'D'
0x140002613  lea     r9, [rsp+1F0h+bOwnerDefaulted]; cbSid
0x140002618  lea     r8, [rbp+0F0h+var_140]; pSid
0x14000261c  xor     edx, edx; DomainSid
0x14000261e  mov     ecx, 6Fh ; 'o'; WellKnownSidType
0x140002623  call    cs:__imp_CreateWellKnownSid
0x140002629  test    eax, eax
0x14000262b  jz      short loc_140002653
0x14000262d  lea     rdx, [rbp+0F0h+var_140]; struct _SID *
0x140002631  lea     rcx, [rbp+0F0h+var_C0]; this
0x140002635  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x14000263a  nop
0x14000263b  lea     rdx, [rbp+0F0h+var_C0]; struct ATL::CSid *
0x14000263f  lea     rcx, [rsp+1F0h+var_180]; this
0x140002644  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x140002649  nop
0x14000264a  lea     rcx, [rbp+0F0h+var_C0]; this
0x14000264e  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140002653  mov     rcx, [rsp+1F0h+pSecurityDescriptor]
0x140002658  test    rcx, rcx
0x14000265b  jz      short loc_14000266C
0x14000265d  lea     rcx, [rsp+1F0h+var_198]; this
0x140002662  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x140002667  mov     rcx, [rsp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x14000266c  mov     [rbp+0F0h+pDacl], r14
0x140002670  test    rcx, rcx
0x140002673  jz      short loc_14000269D
0x140002675  mov     [rsp+1F0h+bOwnerDefaulted], r14d
0x14000267a  mov     dword ptr [rsp+1F0h+pOwner], r14d
0x14000267f  lea     r9, [rsp+1F0h+bOwnerDefaulted]; lpbDaclDefaulted
0x140002684  lea     r8, [rbp+0F0h+pDacl]; pDacl
0x140002688  lea     rdx, [rsp+1F0h+pOwner]; lpbDaclPresent
0x14000268d  call    cs:__imp_GetSecurityDescriptorDacl
0x140002693  test    eax, eax
0x140002695  jnz     short loc_1400026E4
0x140002697  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x14000269d  mov     ecx, 28h ; '('; Size
0x1400026a2  call    cs:__imp_malloc
0x1400026a8  mov     [rsp+1F0h+pSecurityDescriptor], rax
0x1400026ad  test    rax, rax
0x1400026b0  jz      loc_140002838
0x1400026b6  mov     edx, ebx; dwRevision
0x1400026b8  mov     rcx, rax; pSecurityDescriptor
0x1400026bb  call    cs:__imp_InitializeSecurityDescriptor
0x1400026c1  test    eax, eax
0x1400026c3  jnz     short loc_1400026E4
0x1400026c5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400026ca  mov     ebx, eax
0x1400026cc  mov     rcx, [rsp+1F0h+pSecurityDescriptor]; Block
0x1400026d1  call    cs:__imp_free
0x1400026d7  mov     [rsp+1F0h+pSecurityDescriptor], r14
0x1400026dc  mov     ecx, ebx; int
0x1400026de  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1400026e4  cmp     [rbp+0F0h+var_170], 0
0x1400026e8  jnz     short loc_140002745
0x1400026ea  mov     rax, [rsp+1F0h+var_180]
0x1400026ef  lea     rcx, [rsp+1F0h+var_180]
0x1400026f4  mov     rax, [rax+8]
0x1400026f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026fd  test    eax, eax
0x1400026ff  jz      short loc_140002745
0x140002701  lea     rcx, [rsp+1F0h+var_180]; this
0x140002706  call    ?GetLength@CAcl@ATL@@QEBAIXZ; ATL::CAcl::GetLength(void)
0x14000270b  mov     esi, eax
0x14000270d  mov     ecx, eax; Size
0x14000270f  call    cs:__imp_malloc
0x140002715  mov     rdi, rax
0x140002718  test    rax, rax
0x14000271b  jz      loc_140002838
0x140002721  lea     rcx, [rsp+1F0h+var_180]; this
0x140002726  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x14000272b  mov     r9d, esi; SourceSize
0x14000272e  mov     r8, rax; Source
0x140002731  mov     edx, esi; DestinationSize
0x140002733  mov     rcx, rdi; Destination
0x140002736  call    cs:__imp_memcpy_s
0x14000273c  mov     ecx, eax; int
0x14000273e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140002743  jmp     short loc_140002748
0x140002745  mov     rdi, r14
0x140002748  cmp     [rbp+0F0h+var_170], 0
0x14000274c  jnz     short loc_140002756
0x14000274e  test    rdi, rdi
0x140002751  jnz     short loc_140002756
0x140002753  mov     ebx, r14d
0x140002756  xor     r9d, r9d; bDaclDefaulted
0x140002759  mov     r8, rdi; pDacl
0x14000275c  mov     edx, ebx; bDaclPresent
0x14000275e  mov     rcx, [rsp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x140002763  call    cs:__imp_SetSecurityDescriptorDacl
0x140002769  test    eax, eax
0x14000276b  jnz     short loc_140002785
0x14000276d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140002772  mov     ebx, eax
0x140002774  mov     rcx, rdi; Block
0x140002777  call    cs:__imp_free
0x14000277d  mov     ecx, ebx; int
0x14000277f  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x140002785  mov     rcx, [rbp+0F0h+pDacl]; Block
0x140002789  call    cs:__imp_free
0x14000278f  mov     [rsp+1F0h+pReserved3], r14; pReserved3
0x140002794  mov     [rsp+1F0h+dwCapabilities], r14d; dwCapabilities
0x140002799  mov     [rsp+1F0h+pAuthList], r14; pAuthList
0x14000279e  mov     [rsp+1F0h+dwImpLevel], 2; dwImpLevel
  ... truncated ...
```
