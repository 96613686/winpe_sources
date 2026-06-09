# InitializeApp

- ea: `0x180031560`
- end: `0x180031a89`
- name: `InitializeApp`
- size: `1321`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180031a90`

## callees

- `0x180002da0`
- `0x1800032dc`
- `0x18000a914`
- `0x18000ba8c`
- `0x18000c270`
- `0x18000c354`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x180012240`
- `0x180012654`
- `0x180016c74`
- `0x180019db0`
- `0x18002285c`
- `0x180022a48`
- `0x1800238c8`
- `0x180026180`
- `0x18002663c`
- `0x18002918c`
- `0x180031560`
- `0x180033c80`
- `0x18003b7f8`
- `0x18004d78c`
- `0x180052e48`
- `0x1800530e4`
- `0x180054c00`
- `0x1800570d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003198c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031a5f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003198c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031a5f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003181d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003181d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180031685`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180031685`

## string_xrefs

- `0x1800316e2`: `msidcrl version is %ls`
- `0x180031848`: `GetWlidUxModulePath failed. hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall InitializeApp(unsigned __int16 *a1, int a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  int v7; // ebx
  unsigned __int64 v9; // rdx
  unsigned __int8 v10; // dl
  PPTraceStatus *v11; // rcx
  CClientPassportClientLibrary *v12; // rax
  LPCWSTR v13; // rdi
  CClientPassportClientLibrary *v14; // rbx
  int WlidUxModulePath; // eax
  CReadWriteLockEx *v16; // rax
  int v17; // ebx
  struct _WLIDInitialSettings *v18; // rbx
  CClientPassportClientLibrary *v19; // rcx
  int v20; // eax
  unsigned int v21; // edx
  unsigned int v22; // ebx
  int bIgnoreCaseb; // [rsp+20h] [rbp-1A8h]
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-1A8h]
  struct IDCRL::IDCRL_OPTIONS *bIgnoreCasea; // [rsp+20h] [rbp-1A8h]
  int v27; // [rsp+60h] [rbp-168h] BYREF
  char v28; // [rsp+64h] [rbp-164h]
  LPCWSTR lpwstrFilename; // [rsp+68h] [rbp-160h] BYREF
  int v30; // [rsp+70h] [rbp-158h]
  CClientPassportClientLibrary *v31; // [rsp+78h] [rbp-150h] BYREF
  struct _WLIDInitialSettings *v32; // [rsp+80h] [rbp-148h] BYREF
  char *v33[5]; // [rsp+88h] [rbp-140h] BYREF
  _DWORD v34[2]; // [rsp+B0h] [rbp-118h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-110h]
  _BYTE v36[24]; // [rsp+D8h] [rbp-F0h] BYREF
  void *Block; // [rsp+F0h] [rbp-D8h] BYREF
  _BYTE v38[136]; // [rsp+F8h] [rbp-D0h] BYREF

  v7 = a2;
  v30 = a2;
  v34[1] = 0;
  v32 = 0;
  v28 = 0;
  v35 = a4;
  v34[0] = a5;
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
    (__int64)v36,
    (__int64)CPassportClientLibraryAbstract::m_csPPCRL,
    1);
  lpwstrFilename = 0;
  v27 = StringCchLengthW(a1, v9, (unsigned __int64 *)&lpwstrFilename);
  if ( v27 < 0 || !lpwstrFilename )
  {
    v27 = -2147188710;
    goto LABEL_39;
  }
  if ( !g_pPPCRL )
  {
    v12 = (CClientPassportClientLibrary *)operator new(0x3A0u, (const struct std::nothrow_t *)&std::nothrow);
    v31 = v12;
    if ( v12 )
      v12 = CClientPassportClientLibrary::CClientPassportClientLibrary(v12);
    g_pPPCRL = (HINSTANCE)v12;
    if ( !v12 )
    {
      v27 = -2147024882;
      goto LABEL_39;
    }
  }
  LOBYTE(v11) = 2;
  if ( PPTraceStatus::TraceOnFlag(v11, v10) )
  {
    ATL::CTime::GetTickCount(&v31);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&lpwstrFilename);
    bIgnoreCaseb = GetUserDefaultUILanguage();
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
      0x100u,
      L"User Default LangID is 0x%x",
      bIgnoreCaseb);
    if ( (int)GetMSIDCRLPath(&lpwstrFilename) < 0 )
    {
      v13 = lpwstrFilename;
    }
    else
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v31);
      v13 = lpwstrFilename;
      GetDisplayFileVersion(lpwstrFilename);
      v14 = v31;
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x106u,
        L"msidcrl version is %ls",
        v31);
      ATL::CStringData::Release((CClientPassportClientLibrary *)((char *)v14 - 24));
      v7 = v30;
    }
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
  }
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v33,
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
    0x10Au,
    (char *)&v27,
    "IDCRL::InitializeApp",
    L"AppId=%ls, IDCRLVersion=%d, dwflags=0x%x, pOptions=0x%p, dwOptions=%d",
    a1,
    v7,
    a3,
    a4,
    a5);
  if ( (a3 & 0xFFFFFFE0) != 0 )
  {
    v27 = -2147186577;
    bIgnoreCase[0] = -2147186577;
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
      0x113u,
      L"Invalid Flags HR=0x%x",
      *(_QWORD *)bIgnoreCase);
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v33);
    goto LABEL_39;
  }
  if ( !IsSameServiceEnvironment((struct IDCRL::IDCRL_OPTIONS *)v34) )
  {
    v27 = -2147188694;
    bIgnoreCase[0] = -2147188694;
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
      0x11Au,
      L"Initialize with a different environment. hr = 0x%x",
      *(_QWORD *)bIgnoreCase);
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v33);
    goto LABEL_39;
  }
  if ( CompareStringOrdinal(a1, -1, L"{9317BCB6-314B-442f-A5DA-9BC2BEBC271D}", -1, 1) == 2 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&lpwstrFilename);
    WlidUxModulePath = CUxpDllWrapper::GetWlidUxModulePath(&lpwstrFilename);
    v27 = WlidUxModulePath;
    if ( WlidUxModulePath < 0 )
    {
      LODWORD(bIgnoreCasea) = WlidUxModulePath;
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x126u,
        L"GetWlidUxModulePath failed. hr = 0x%x",
        bIgnoreCasea);
      if ( v27 == -2147024894 )
        v27 = -2147186574;
      ATL::CStringData::Release((ATL::CStringData *)(lpwstrFilename - 12));
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v33);
      goto LABEL_39;
    }
    ATL::CStringData::Release((ATL::CStringData *)(lpwstrFilename - 12));
  }
  v16 = (CReadWriteLockEx *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v16 )
  {
    v17 = 0;
    CStringSrv::m_pRWLock = CReadWriteLockEx::CReadWriteLockEx(v16);
    if ( CStringSrv::m_pRWLock )
      goto LABEL_28;
  }
  else
  {
    CStringSrv::m_pRWLock = 0;
  }
  v17 = -2147024882;
LABEL_28:
  v27 = v17;
  if ( v17 < 0 )
    goto LABEL_36;
  v27 = WLIDCInitializeEx(a1, &v32);
  if ( v27 )
    goto LABEL_36;
  v18 = v32;
  Block = v38;
  ATL::CW2AEX<128>::Init(&Block, a1, 65001);
  v20 = CClientPassportClientLibrary::Initialize(v19, (const char *)Block, v30, a3, bIgnoreCasea, v18);
  v27 = v20;
  if ( Block != v38 )
  {
    free(Block);
    v20 = v27;
  }
  if ( v20 || (v28 = 1, a4) && a5 && (v27 = SetIdcrlOptions(a4, a5, 0), v27 < 0) )
  {
LABEL_36:
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v33);
  }
  else
  {
    g_fInitialized = 1;
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v33);
  }
LABEL_39:
  if ( !g_fInitialized && g_pPPCRL )
  {
    if ( v28 )
      CClientPassportClientLibrary::Uninitialize((CClientPassportClientLibrary *)g_pPPCRL);
    CStringSrv::UninitializeGlobals();
    if ( g_pPPCRL )
      CClientPassportClientLibrary::`scalar deleting destructor'((CClientPassportClientLibrary *)g_pPPCRL, v21);
    g_pPPCRL = 0;
  }
  v22 = v27;
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v36);
  if ( v32 )
    free(v32);
  return v22;
}

```

## disassembly

```asm
0x180031560  mov     r11, rsp
0x180031563  push    rbx
0x180031564  push    rdi
0x180031565  push    r12
0x180031567  push    r13
0x180031569  push    r14
0x18003156b  push    r15
0x18003156d  sub     rsp, 198h
0x180031574  mov     rax, cs:__security_cookie
0x18003157b  xor     rax, rsp
0x18003157e  mov     [rsp+1C8h+var_48], rax
0x180031586  mov     r15, r9
0x180031589  mov     r13d, r8d
0x18003158c  mov     ebx, edx
0x18003158e  mov     [rsp+1C8h+var_158], edx
0x180031592  mov     r14, rcx
0x180031595  mov     r12d, [rsp+1C8h+arg_20]
0x18003159d  mov     [rsp+1C8h+var_168], 0
0x1800315a5  mov     [rsp+1C8h+var_114], 0
0x1800315b0  mov     qword ptr [r11-148h], 0
0x1800315bb  mov     [rsp+1C8h+var_164], 0
0x1800315c0  mov     [r11-110h], r9
0x1800315c7  mov     [r11-118h], r12d
0x1800315ce  mov     r8b, 1
0x1800315d1  lea     rdx, ?m_csPPCRL@CPassportClientLibraryAbstract@@1VCThreadProtected@@A; CThreadProtected CPassportClientLibraryAbstract::m_csPPCRL
0x1800315d8  lea     rcx, [r11-0F0h]
0x1800315df  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x1800315e4  nop
0x1800315e5  mov     [rsp+1C8h+lpwstrFilename], 0
0x1800315ee  lea     r8, [rsp+1C8h+lpwstrFilename]; unsigned __int64 *
0x1800315f3  mov     rcx, r14; unsigned __int16 *
0x1800315f6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800315fb  mov     [rsp+1C8h+var_168], eax
0x1800315ff  test    eax, eax
0x180031601  js      loc_1800319F6
0x180031607  cmp     [rsp+1C8h+lpwstrFilename], 0
0x18003160d  jz      loc_1800319F6
0x180031613  cmp     cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA, 0; CClientPassportClientLibrary * g_pPPCRL
0x18003161b  jnz     short loc_18003165B
0x18003161d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031624  mov     ecx, 3A0h; unsigned __int64
0x180031629  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003162e  mov     [rsp+1C8h+var_150], rax
0x180031633  test    rax, rax
0x180031636  jz      short loc_180031641
0x180031638  mov     rcx, rax; this
0x18003163b  call    ??0CClientPassportClientLibrary@@QEAA@XZ; CClientPassportClientLibrary::CClientPassportClientLibrary(void)
0x180031640  nop
0x180031641  mov     cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA, rax; CClientPassportClientLibrary * g_pPPCRL
0x180031648  test    rax, rax
0x18003164b  jnz     short loc_18003165B
0x18003164d  mov     ebx, 8007000Eh
0x180031652  mov     [rsp+1C8h+var_168], ebx
0x180031656  jmp     loc_1800319FE
0x18003165b  mov     edi, 2
0x180031660  mov     cl, dil; this
0x180031663  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180031668  test    al, al
0x18003166a  jz      loc_180031723
0x180031670  lea     rcx, [rsp+1C8h+var_150]
0x180031675  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x18003167a  lea     rcx, [rsp+1C8h+lpwstrFilename]
0x18003167f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180031684  nop
0x180031685  call    cs:__imp_GetUserDefaultUILanguage
0x18003168b  movzx   eax, ax
0x18003168e  mov     [rsp+1C8h+bIgnoreCase], eax
0x180031692  lea     r9, aUserDefaultLan; "User Default LangID is 0x%x"
0x180031699  mov     r8d, 100h; unsigned int
0x18003169f  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x1800316a6  mov     ecx, edi; unsigned __int8
0x1800316a8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800316ad  lea     rcx, [rsp+1C8h+lpwstrFilename]
0x1800316b2  call    ?GetMSIDCRLPath@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetMSIDCRLPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800316b7  test    eax, eax
0x1800316b9  js      short loc_180031710
0x1800316bb  lea     rcx, [rsp+1C8h+var_150]
0x1800316c0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800316c5  nop
0x1800316c6  lea     rdx, [rsp+1C8h+var_150]
0x1800316cb  mov     rdi, [rsp+1C8h+lpwstrFilename]
0x1800316d0  mov     rcx, rdi; lpwstrFilename
0x1800316d3  call    ?GetDisplayFileVersion@@YAXPEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetDisplayFileVersion(ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800316d8  mov     rbx, [rsp+1C8h+var_150]
0x1800316dd  mov     qword ptr [rsp+1C8h+bIgnoreCase], rbx
0x1800316e2  lea     r9, aMsidcrlVersion; "msidcrl version is %ls"
0x1800316e9  mov     r8d, 106h; unsigned int
0x1800316ef  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x1800316f6  mov     ecx, 2; unsigned __int8
0x1800316fb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180031700  nop
0x180031701  lea     rcx, [rbx-18h]; this
0x180031705  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003170a  mov     ebx, [rsp+1C8h+var_158]
0x18003170e  jmp     short loc_180031715
0x180031710  mov     rdi, [rsp+1C8h+lpwstrFilename]
0x180031715  lea     rcx, [rdi-18h]; this
0x180031719  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003171e  mov     edi, 2
0x180031723  mov     [rsp+1C8h+var_178], r12d
0x180031728  mov     [rsp+1C8h+var_180], r15
0x18003172d  mov     [rsp+1C8h+var_188], r13d
0x180031732  mov     [rsp+1C8h+var_190], ebx
0x180031736  mov     [rsp+1C8h+var_198], r14
0x18003173b  lea     rax, aAppidLsIdcrlve; "AppId=%ls, IDCRLVersion=%d, dwflags=0x%"...
0x180031742  mov     [rsp+1C8h+var_1A0], rax
0x180031747  lea     rax, aIdcrlInitializ; "IDCRL::InitializeApp"
0x18003174e  mov     qword ptr [rsp+1C8h+bIgnoreCase], rax
0x180031753  lea     r9, [rsp+1C8h+var_168]
0x180031758  mov     r8d, 10Ah
0x18003175e  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180031765  lea     rcx, [rsp+1C8h+var_140]
0x18003176d  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x180031772  nop
0x180031773  test    r13d, 0FFFFFFE0h
0x18003177a  jz      short loc_1800317B8
0x18003177c  mov     eax, 8004886Fh
0x180031781  mov     [rsp+1C8h+var_168], eax
0x180031785  mov     [rsp+1C8h+bIgnoreCase], eax
0x180031789  lea     r9, aInvalidFlagsHr; "Invalid Flags HR=0x%x"
0x180031790  mov     r8d, 113h; unsigned int
0x180031796  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003179d  mov     ecx, edi; unsigned __int8
0x18003179f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800317a4  nop
0x1800317a5  lea     rcx, [rsp+1C8h+var_140]
0x1800317ad  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800317b2  nop
0x1800317b3  jmp     loc_1800319FE
0x1800317b8  lea     rcx, [rsp+1C8h+var_118]; struct IDCRL::IDCRL_OPTIONS *
0x1800317c0  call    ?IsSameServiceEnvironment@@YA_NPEAUIDCRL_OPTIONS@IDCRL@@@Z; IsSameServiceEnvironment(IDCRL::IDCRL_OPTIONS *)
0x1800317c5  test    al, al
0x1800317c7  jnz     short loc_180031805
0x1800317c9  mov     eax, 8004802Ah
0x1800317ce  mov     [rsp+1C8h+var_168], eax
0x1800317d2  mov     [rsp+1C8h+bIgnoreCase], eax
0x1800317d6  lea     r9, aInitializeWith; "Initialize with a different environment"...
0x1800317dd  mov     r8d, 11Ah; unsigned int
0x1800317e3  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x1800317ea  mov     ecx, edi; unsigned __int8
0x1800317ec  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800317f1  nop
0x1800317f2  lea     rcx, [rsp+1C8h+var_140]
0x1800317fa  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800317ff  nop
0x180031800  jmp     loc_1800319FE
0x180031805  mov     [rsp+1C8h+bIgnoreCase], 1; struct IDCRL::IDCRL_OPTIONS *
0x18003180d  or      edx, 0FFFFFFFFh; cchCount1
0x180031810  mov     r9d, edx; cchCount2
0x180031813  lea     r8, a9317bcb6314b44; "{9317BCB6-314B-442f-A5DA-9BC2BEBC271D}"
0x18003181a  mov     rcx, r14; lpString1
0x18003181d  call    cs:__imp_CompareStringOrdinal
0x180031823  cmp     eax, edi
0x180031825  jnz     short loc_1800318A6
0x180031827  lea     rcx, [rsp+1C8h+lpwstrFilename]
0x18003182c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180031831  nop
0x180031832  lea     rcx, [rsp+1C8h+lpwstrFilename]
0x180031837  call    ?GetWlidUxModulePath@CUxpDllWrapper@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CUxpDllWrapper::GetWlidUxModulePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003183c  mov     [rsp+1C8h+var_168], eax
0x180031840  test    eax, eax
0x180031842  jns     short loc_180031897
0x180031844  mov     [rsp+1C8h+bIgnoreCase], eax
0x180031848  lea     r9, aGetwliduxmodul; "GetWlidUxModulePath failed. hr = 0x%x"
0x18003184f  mov     r8d, 126h; unsigned int
0x180031855  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003185c  mov     ecx, edi; unsigned __int8
0x18003185e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180031863  cmp     [rsp+1C8h+var_168], 80070002h
0x18003186b  jnz     short loc_180031875
0x18003186d  mov     [rsp+1C8h+var_168], 80048872h
0x180031875  mov     rcx, [rsp+1C8h+lpwstrFilename]
0x18003187a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003187e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031883  nop
0x180031884  lea     rcx, [rsp+1C8h+var_140]
0x18003188c  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180031891  nop
0x180031892  jmp     loc_1800319FE
0x180031897  mov     rcx, [rsp+1C8h+lpwstrFilename]
0x18003189c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800318a0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800318a5  nop
0x1800318a6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800318ad  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800318b2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800318b7  test    rax, rax
0x1800318ba  jz      short loc_1800318D4
0x1800318bc  xor     ebx, ebx
0x1800318be  mov     rcx, rax; this
0x1800318c1  call    ??0CReadWriteLockEx@@QEAA@XZ; CReadWriteLockEx::CReadWriteLockEx(void)
0x1800318c6  mov     cs:?m_pRWLock@CStringSrv@@0PEAVCReadWriteLockEx@@EA, rax; CReadWriteLockEx * CStringSrv::m_pRWLock
0x1800318cd  test    rax, rax
0x1800318d0  jnz     short loc_1800318E4
0x1800318d2  jmp     short loc_1800318DF
0x1800318d4  mov     cs:?m_pRWLock@CStringSrv@@0PEAVCReadWriteLockEx@@EA, 0; CReadWriteLockEx * CStringSrv::m_pRWLock
0x1800318df  mov     ebx, 8007000Eh
0x1800318e4  mov     [rsp+1C8h+var_168], ebx
0x1800318e8  test    ebx, ebx
0x1800318ea  jns     short loc_1800318FF
0x1800318ec  lea     rcx, [rsp+1C8h+var_140]
0x1800318f4  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800318f9  nop
0x1800318fa  jmp     loc_1800319FE
0x1800318ff  lea     rdx, [rsp+1C8h+var_148]; struct _WLIDInitialSettings **
0x180031907  mov     rcx, r14; unsigned __int16 *
0x18003190a  call    ?WLIDCInitializeEx@@YAJPEBGPEAPEAU_WLIDInitialSettings@@@Z; WLIDCInitializeEx(ushort const *,_WLIDInitialSettings * *)
0x18003190f  mov     [rsp+1C8h+var_168], eax
0x180031913  test    eax, eax
0x180031915  jz      short loc_18003192A
0x180031917  lea     rcx, [rsp+1C8h+var_140]
0x18003191f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180031924  nop
0x180031925  jmp     loc_1800319FE
0x18003192a  mov     rbx, [rsp+1C8h+var_148]
0x180031932  lea     rax, [rsp+1C8h+var_D0]
0x18003193a  mov     [rsp+1C8h+Block], rax
0x180031942  mov     r8d, 0FDE9h
0x180031948  mov     rdx, r14
0x18003194b  lea     rcx, [rsp+1C8h+Block]
0x180031953  call    ?Init@?$CW2AEX@$0IA@@ATL@@AEAAXPEBGI@Z; ATL::CW2AEX<128>::Init(ushort const *,uint)
0x180031958  nop
0x180031959  mov     [rsp+1C8h+var_1A0], rbx; struct _WLIDInitialSettings *
0x18003195e  mov     r9d, r13d; unsigned int
0x180031961  mov     r8d, [rsp+1C8h+var_158]; int
0x180031966  mov     rdx, [rsp+1C8h+Block]; char *
0x18003196e  call    ?Initialize@CClientPassportClientLibrary@@QEAAJPEBDJKPEAUIDCRL_OPTIONS@IDCRL@@PEAU_WLIDInitialSettings@@@Z; CClientPassportClientLibrary::Initialize(char const *,long,ulong,IDCRL::IDCRL_OPTIONS *,_WLIDInitialSettings *)
0x180031973  mov     [rsp+1C8h+var_168], eax
0x180031977  mov     rcx, [rsp+1C8h+Block]; Block
0x18003197f  lea     rdx, [rsp+1C8h+var_D0]
0x180031987  cmp     rcx, rdx
0x18003198a  jz      short loc_180031996
0x18003198c  call    cs:__imp_free
0x180031992  mov     eax, [rsp+1C8h+var_168]
0x180031996  test    eax, eax
0x180031998  jz      short loc_1800319AA
0x18003199a  lea     rcx, [rsp+1C8h+var_140]
0x1800319a2  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800319a7  nop
0x1800319a8  jmp     short loc_1800319FE
0x1800319aa  mov     [rsp+1C8h+var_164], 1
0x1800319af  test    r15, r15
0x1800319b2  jz      short loc_1800319DF
0x1800319b4  test    r12d, r12d
0x1800319b7  jz      short loc_1800319DF
0x1800319b9  xor     r8d, r8d
0x1800319bc  mov     edx, r12d
0x1800319bf  mov     rcx, r15
0x1800319c2  call    SetIdcrlOptions
0x1800319c7  mov     [rsp+1C8h+var_168], eax
0x1800319cb  test    eax, eax
0x1800319cd  jns     short loc_1800319DF
0x1800319cf  lea     rcx, [rsp+1C8h+var_140]
0x1800319d7  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800319dc  nop
0x1800319dd  jmp     short loc_1800319FE
0x1800319df  mov     cs:?g_fInitialized@@3_NA, 1; bool g_fInitialized
0x1800319e6  lea     rcx, [rsp+1C8h+var_140]
0x1800319ee  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800319f3  nop
0x1800319f4  jmp     short loc_1800319FE
0x1800319f6  mov     [rsp+1C8h+var_168], 8004801Ah
0x1800319fe  cmp     cs:?g_fInitialized@@3_NA, 0; bool g_fInitialized
0x180031a05  jnz     short loc_180031A40
0x180031a07  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; this
0x180031a0e  test    rcx, rcx
0x180031a11  jz      short loc_180031A40
0x180031a13  cmp     [rsp+1C8h+var_164], 0
0x180031a18  jz      short loc_180031A1F
0x180031a1a  call    ?Uninitialize@CClientPassportClientLibrary@@QEAAJXZ; CClientPassportClientLibrary::Uninitialize(void)
0x180031a1f  call    ?UninitializeGlobals@CStringSrv@@SAXXZ; CStringSrv::UninitializeGlobals(void)
0x180031a24  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; this
0x180031a2b  test    rcx, rcx
0x180031a2e  jz      short loc_180031A35
0x180031a30  call    ??_GCClientPassportClientLibrary@@QEAAPEAXI@Z; CClientPassportClientLibrary::`scalar deleting destructor'(uint)
0x180031a35  mov     cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA, 0; CClientPassportClientLibrary * g_pPPCRL
0x180031a40  mov     ebx, [rsp+1C8h+var_168]
0x180031a44  lea     rcx, [rsp+1C8h+var_F0]
0x180031a4c  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180031a51  nop
0x180031a52  mov     rcx, [rsp+1C8h+var_148]; Block
0x180031a5a  test    rcx, rcx
0x180031a5d  jz      short loc_180031A65
0x180031a5f  call    cs:__imp_free
0x180031a65  mov     eax, ebx
0x180031a67  mov     rcx, [rsp+1C8h+var_48]
0x180031a6f  xor     rcx, rsp; StackCookie
0x180031a72  call    __security_check_cookie
0x180031a77  add     rsp, 198h
0x180031a7e  pop     r15
0x180031a80  pop     r14
0x180031a82  pop     r13
0x180031a84  pop     r12
0x180031a86  pop     rdi
0x180031a87  pop     rbx
0x180031a88  retn
```
