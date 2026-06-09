# AuthIdentityToServiceInternal(IDCRL::_tagPIH *,ushort const *,ushort const *,_PolicyEncoding,ulong,ushort * *,ushort * *,ulong *,uchar * *,ulong *)

- ea: `0x180023fe4`
- end: `0x18002470f`
- name: `?AuthIdentityToServiceInternal@@YAJPEAU_tagPIH@IDCRL@@PEBG1W4_PolicyEncoding@@KPEAPEAG3PEAKPEAPEAE4@Z`
- size: `1835`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64, int, int, unsigned __int16 **, unsigned __int16 **, int *, void **, _DWORD *)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180029830`
- `0x18002fd30`

## callees

- `0x18000a1a8`
- `0x18000a914`
- `0x18000ba8c`
- `0x18000c354`
- `0x18000c538`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x180010eec`
- `0x1800114b0`
- `0x18001c3c0`
- `0x18001c6ec`
- `0x18001dd50`
- `0x18001e1f8`
- `0x18001e36c`
- `0x18001e388`
- `0x18001e664`
- `0x18002126c`
- `0x180023fe4`
- `0x180025e40`
- `0x180028940`
- `0x18002932c`
- `0x180029788`
- `0x1800530e4`
- `0x180055758`
- `0x1800558c0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800246c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800246c1`

## string_xrefs

- `0x18002402e`: `ExternalIdentity=0x%p, szServiceTarget='%ls', szServicePolicy='%ls', dwTokenRequestFlags=0x%x`
- `0x18002403a`: `AuthIdentityToServiceInternal`
- `0x180024358`: `Service token is expired`
- `0x1800243af`: `Service token for request is:\n%ls\n `
- `0x180024521`: `Internal token type: %d`

## pseudocode

```c
__int64 __fastcall AuthIdentityToServiceInternal(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        int a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        int *a8,
        void **a9,
        _DWORD *a10)
{
  unsigned int v13; // r14d
  void **v14; // r13
  _DWORD *v15; // r12
  __int64 v16; // r8
  CClientSingleIdentity *v17; // rbx
  const unsigned __int16 *v18; // r9
  int v19; // esi
  int v20; // edx
  _QWORD *Token; // rax
  HINSTANCE v22; // rbx
  const unsigned __int16 **v23; // rax
  unsigned __int16 *v24; // rbx
  ATL::CStringData *v25; // rcx
  unsigned int v26; // ebx
  int v27; // esi
  rsize_t v28; // rbx
  unsigned int v29; // ebx
  unsigned int v31[2]; // [rsp+20h] [rbp-298h]
  unsigned __int16 *v32; // [rsp+50h] [rbp-268h] BYREF
  char *v33; // [rsp+58h] [rbp-260h] BYREF
  char v34; // [rsp+60h] [rbp-258h]
  rsize_t DestinationSize; // [rsp+68h] [rbp-250h] BYREF
  void *Source; // [rsp+70h] [rbp-248h]
  __int64 v37; // [rsp+78h] [rbp-240h]
  CClientSingleIdentity *v38[2]; // [rsp+80h] [rbp-238h] BYREF
  __int64 v39; // [rsp+90h] [rbp-228h] BYREF
  int v40; // [rsp+98h] [rbp-220h] BYREF
  const unsigned __int16 *v41; // [rsp+A0h] [rbp-218h]
  __int64 v42; // [rsp+A8h] [rbp-210h]
  __int64 v43; // [rsp+B0h] [rbp-208h]
  int v44; // [rsp+B8h] [rbp-200h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-1F8h]
  int v46; // [rsp+C8h] [rbp-1F0h]
  int v47; // [rsp+D0h] [rbp-1E8h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-1E0h]
  int v49; // [rsp+E0h] [rbp-1D8h]
  _BYTE v50[24]; // [rsp+F0h] [rbp-1C8h] BYREF
  unsigned int v51; // [rsp+108h] [rbp-1B0h]
  int v52; // [rsp+118h] [rbp-1A0h]
  unsigned __int16 *v53; // [rsp+128h] [rbp-190h]
  unsigned int v54; // [rsp+178h] [rbp-140h]
  unsigned __int8 *v55; // [rsp+180h] [rbp-138h]
  __int64 v56; // [rsp+1A0h] [rbp-118h]
  char *v57[4]; // [rsp+1C0h] [rbp-F8h] BYREF
  _BYTE v58[176]; // [rsp+1E0h] [rbp-D8h] BYREF
  int IdentityFromExternalHandle_Internal; // [rsp+2C8h] [rbp+10h] BYREF
  int v60; // [rsp+2D8h] [rbp+20h]

  v60 = a4;
  IdentityFromExternalHandle_Internal = 0;
  v13 = a5;
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v57,
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
    0xADDu,
    (char *)&IdentityFromExternalHandle_Internal,
    "AuthIdentityToServiceInternal",
    L"ExternalIdentity=0x%p, szServiceTarget='%ls', szServicePolicy='%ls', dwTokenRequestFlags=0x%x",
    a1,
    a2,
    a3,
    a5);
  CPPCRLToken::CPPCRLToken((CPPCRLToken *)v58);
  v56 = 0;
  v48 = 0;
  v47 = 0;
  v49 = 0;
  v45 = 0;
  v44 = 0;
  v46 = 0;
  v38[0] = 0;
  LOBYTE(v60) = 0;
  if ( !a2 )
  {
    IdentityFromExternalHandle_Internal = -2147467261;
    goto LABEL_57;
  }
  if ( a8 )
    *a8 = 0;
  v14 = a9;
  if ( a9 )
    *a9 = 0;
  v15 = a10;
  if ( a10 )
    *a10 = 0;
  if ( !v14 )
  {
    if ( !v15 )
      goto LABEL_14;
LABEL_13:
    IdentityFromExternalHandle_Internal = -2147024809;
    goto LABEL_57;
  }
  if ( !v15 )
    goto LABEL_13;
LABEL_14:
  if ( (v13 & 0x30000) == 0x30000 )
  {
    IdentityFromExternalHandle_Internal = -2147024809;
    goto LABEL_57;
  }
  IdentityFromExternalHandle_Internal = VerifyInitialized();
  if ( IdentityFromExternalHandle_Internal < 0 )
    goto LABEL_54;
  LOBYTE(v16) = 1;
  IdentityFromExternalHandle_Internal = CClientIdentityStore::GetIdentityFromExternalHandle_Internal(
                                          g_pPPCRL + 8,
                                          a1,
                                          v16,
                                          v38);
  if ( IdentityFromExternalHandle_Internal < 0 )
    goto LABEL_54;
  v17 = v38[0];
  if ( !v38[0] )
  {
    IdentityFromExternalHandle_Internal = -2147188704;
    goto LABEL_57;
  }
  CPPCRLToken::CPPCRLToken((CPPCRLToken *)v50);
  HIDWORD(DestinationSize) = 0;
  v37 = 0;
  v33 = (char *)v17 + 16;
  v34 = 0;
  IdentityFromExternalHandle_Internal = CComCritSecLockWTry<CComAutoCriticalSectionWTry>::TryLock(&v33);
  if ( IdentityFromExternalHandle_Internal < 0 )
    goto LABEL_25;
  v40 = 32;
  v41 = a2;
  v42 = a3;
  v43 = 0;
  LODWORD(DestinationSize) = 1;
  Source = &v40;
  CClientSingleIdentity::ResetCancelRequestEvent(v17);
  v19 = v13 & 0x10000;
  if ( (v13 & 0x10000) == 0 )
  {
    IdentityFromExternalHandle_Internal = CClientSingleIdentity::RequestServiceTokenEx(
                                            v17,
                                            (v13 >> 8) & 0x200,
                                            (struct IDCRL::_MultiRSTParams *const)&DestinationSize,
                                            v18);
    if ( IdentityFromExternalHandle_Internal < 0 || CClientSingleIdentity::IsAsync(v17) )
      goto LABEL_25;
  }
  IdentityFromExternalHandle_Internal = CClientSingleIdentity::GetServiceToken(v17, a2, (struct CPPCRLToken *)v50, 0, 0);
  if ( IdentityFromExternalHandle_Internal < 0 )
  {
LABEL_25:
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
    CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v50);
    goto LABEL_54;
  }
  if ( v52 )
  {
    if ( !v19 )
    {
      IdentityFromExternalHandle_Internal = -2147186590;
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
      CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v50);
      goto LABEL_54;
    }
    goto LABEL_30;
  }
  if ( v19 )
  {
LABEL_30:
    if ( v51 )
    {
      v32 = v53;
      if ( CClientTokenInfo::IsExpired((struct ATL::CTime *)&v32, v20) )
      {
        IdentityFromExternalHandle_Internal = -2147186590;
        TracePrintW(
          5u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
          0xB56u,
          L"Service token is expired");
        CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
        CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v50);
        goto LABEL_54;
      }
    }
  }
  Token = (_QWORD *)CPPCRLToken::GetToken(v50, &v32);
  TracePrintW(
    5u,
    "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
    0xB5Bu,
    L"Service token for request is:\n%ls\n ",
    *Token);
  ATL::CStringData::Release((ATL::CStringData *)(v32 - 12));
  if ( !a6
    || (v22 = g_pPPCRL,
        v23 = (const unsigned __int16 **)CPPCRLToken::GetToken(v50, &v39),
        LODWORD(v22) = CExternalMemoryManager::AllocateStringForExternal((CExternalMemoryManager *)(v22 + 58), *v23, a6),
        IdentityFromExternalHandle_Internal = (int)v22,
        ATL::CStringData::Release((ATL::CStringData *)(v39 - 24)),
        (int)v22 >= 0) )
  {
    if ( a7 )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v32);
      IdentityFromExternalHandle_Internal = CPPCRLToken::GetAuthzToken(v50, &v32);
      if ( IdentityFromExternalHandle_Internal < 0 )
      {
        ATL::CStringData::Release((ATL::CStringData *)(v32 - 12));
        CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
        CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v50);
        goto LABEL_54;
      }
      v24 = v32;
      IdentityFromExternalHandle_Internal = CExternalMemoryManager::AllocateStringForExternal(
                                              (CExternalMemoryManager *)(g_pPPCRL + 58),
                                              v32,
                                              a7);
      v25 = (ATL::CStringData *)(v24 - 12);
      if ( IdentityFromExternalHandle_Internal < 0 )
      {
        ATL::CStringData::Release(v25);
        CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
        CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v50);
        goto LABEL_54;
      }
      ATL::CStringData::Release(v25);
    }
    v26 = v51;
    v31[0] = v51;
    TracePrintW(
      5u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
      0xB76u,
      L"Internal token type: %d",
      *(_QWORD *)v31);
    v27 = (v26 == 1) + 1;
    if ( v14 && v15 )
    {
      Source = 0;
      LODWORD(DestinationSize) = 0;
      LODWORD(v37) = 0;
      CBytePtr::Attach((CBytePtr *)&DestinationSize, v55, v54, 0);
      v28 = (unsigned int)DestinationSize;
      if ( (_DWORD)DestinationSize )
      {
        IdentityFromExternalHandle_Internal = CExternalMemoryManager::Allocate(
                                                (CExternalMemoryManager *)(g_pPPCRL + 58),
                                                (unsigned int)DestinationSize,
                                                v14);
        if ( IdentityFromExternalHandle_Internal < 0 )
        {
          CBytePtr::Empty((CBytePtr *)&DestinationSize);
          CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
          CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v50);
          goto LABEL_54;
        }
        if ( memcpy_s_0(*v14, v28, Source, v28) )
        {
          IdentityFromExternalHandle_Internal = -2147418113;
          CBytePtr::Empty((CBytePtr *)&DestinationSize);
          CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
          CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v50);
          goto LABEL_54;
        }
        IdentityFromExternalHandle_Internal = 0;
        *v15 = v28;
      }
      else
      {
        LOBYTE(v60) = 1;
      }
      CBytePtr::Empty((CBytePtr *)&DestinationSize);
    }
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
    CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v50);
    if ( a8 )
      *a8 = v27;
    goto LABEL_54;
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v33);
  CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v50);
LABEL_54:
  if ( IdentityFromExternalHandle_Internal >= 0 && (_BYTE)v60 )
    IdentityFromExternalHandle_Internal = 297057;
LABEL_57:
  v29 = IdentityFromExternalHandle_Internal;
  CAutoRefPtr<CAuthContext>::Deinit(v38);
  CBytePtr::Empty((CBytePtr *)&v44);
  CBytePtr::Empty((CBytePtr *)&v47);
  SysFreeString(0);
  CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v58);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v57);
  return v29;
}

```

## disassembly

```asm
0x180023fe4  mov     r11, rsp
0x180023fe7  mov     [r11+8], rbx
0x180023feb  mov     [r11+18h], rsi
0x180023fef  mov     [r11+20h], r9d
0x180023ff3  push    rdi
0x180023ff4  push    r12
0x180023ff6  push    r13
0x180023ff8  push    r14
0x180023ffa  push    r15
0x180023ffc  sub     rsp, 290h
0x180024003  mov     rsi, r8
0x180024006  mov     r15, rdx
0x180024009  mov     rbx, rcx
0x18002400c  xor     edi, edi
0x18002400e  mov     [r11+10h], edi
0x180024012  mov     r14d, [rsp+2B8h+arg_20]
0x18002401a  mov     [rsp+2B8h+var_270], r14d
0x18002401f  mov     [rsp+2B8h+var_278], r8
0x180024024  mov     [rsp+2B8h+var_280], rdx
0x180024029  mov     [rsp+2B8h+var_288], rcx
0x18002402e  lea     rax, aExternalidenti_4; "ExternalIdentity=0x%p, szServiceTarget="...
0x180024035  mov     [rsp+2B8h+var_290], rax
0x18002403a  lea     rax, aAuthidentityto_2; "AuthIdentityToServiceInternal"
0x180024041  mov     qword ptr [rsp+2B8h+var_298], rax
0x180024046  lea     r9, [r11+10h]
0x18002404a  mov     r8d, 0ADDh
0x180024050  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180024057  lea     rcx, [r11-0F8h]
0x18002405e  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x180024063  nop
0x180024064  lea     rcx, [rsp+2B8h+var_D8]; this
0x18002406c  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x180024071  nop
0x180024072  mov     [rsp+2B8h+var_118], rdi
0x18002407a  mov     [rsp+2B8h+var_1E0], rdi
0x180024082  mov     [rsp+2B8h+var_1E8], edi
0x180024089  mov     [rsp+2B8h+var_1D8], edi
0x180024090  mov     [rsp+2B8h+var_1F8], rdi
0x180024098  mov     [rsp+2B8h+var_200], edi
0x18002409f  mov     [rsp+2B8h+var_1F0], edi
0x1800240a6  mov     [rsp+2B8h+var_238], rdi
0x1800240ae  mov     byte ptr [rsp+2B8h+arg_18], dil
0x1800240b6  test    r15, r15
0x1800240b9  jnz     short loc_1800240CB
0x1800240bb  mov     [rsp+2B8h+arg_8], 80004003h
0x1800240c6  jmp     loc_18002468E
0x1800240cb  mov     rax, [rsp+2B8h+arg_38]
0x1800240d3  test    rax, rax
0x1800240d6  jz      short loc_1800240DA
0x1800240d8  mov     [rax], edi
0x1800240da  mov     r13, [rsp+2B8h+arg_40]
0x1800240e2  test    r13, r13
0x1800240e5  jz      short loc_1800240EB
0x1800240e7  mov     [r13+0], rdi
0x1800240eb  mov     r12, [rsp+2B8h+arg_48]
0x1800240f3  test    r12, r12
0x1800240f6  jz      short loc_1800240FC
0x1800240f8  mov     [r12], edi
0x1800240fc  test    r13, r13
0x1800240ff  jz      short loc_180024108
0x180024101  test    r12, r12
0x180024104  jz      short loc_18002410D
0x180024106  jmp     short loc_18002411D
0x180024108  test    r12, r12
0x18002410b  jz      short loc_18002411D
0x18002410d  mov     [rsp+2B8h+arg_8], 80070057h
0x180024118  jmp     loc_18002468E
0x18002411d  mov     eax, r14d
0x180024120  mov     ecx, 30000h
0x180024125  and     eax, ecx
0x180024127  cmp     eax, ecx
0x180024129  jnz     short loc_18002413B
0x18002412b  mov     [rsp+2B8h+arg_8], 80070057h
0x180024136  jmp     loc_18002468E
0x18002413b  call    ?VerifyInitialized@@YAJXZ; VerifyInitialized(void)
0x180024140  mov     [rsp+2B8h+arg_8], eax
0x180024147  test    eax, eax
0x180024149  jns     short loc_180024150
0x18002414b  jmp     loc_180024670
0x180024150  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x180024157  add     rcx, 20h ; ' '
0x18002415b  lea     r9, [rsp+2B8h+var_238]
0x180024163  mov     r8b, 1
0x180024166  mov     rdx, rbx
0x180024169  call    ?GetIdentityFromExternalHandle_Internal@CClientIdentityStore@@QEAAJPEAU_tagPIH@IDCRL@@_NAEAV?$CAutoRefPtr@VCClientSingleIdentity@@@@@Z; CClientIdentityStore::GetIdentityFromExternalHandle_Internal(IDCRL::_tagPIH *,bool,CAutoRefPtr<CClientSingleIdentity> &)
0x18002416e  mov     [rsp+2B8h+arg_8], eax
0x180024175  test    eax, eax
0x180024177  jns     short loc_18002417E
0x180024179  jmp     loc_180024670
0x18002417e  mov     rbx, [rsp+2B8h+var_238]
0x180024186  test    rbx, rbx
0x180024189  jnz     short loc_18002419B
0x18002418b  mov     [rsp+2B8h+arg_8], 80048020h
0x180024196  jmp     loc_18002468E
0x18002419b  lea     rcx, [rsp+2B8h+var_1C8]; this
0x1800241a3  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x1800241a8  nop
0x1800241a9  mov     dword ptr [rsp+2B8h+DestinationSize+4], edi
0x1800241ad  mov     [rsp+2B8h+var_240], rdi
0x1800241b2  lea     rax, [rbx+10h]
0x1800241b6  mov     [rsp+2B8h+var_260], rax
0x1800241bb  mov     [rsp+2B8h+var_258], dil
0x1800241c0  lea     rcx, [rsp+2B8h+var_260]
0x1800241c5  call    ?TryLock@?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAAJXZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::TryLock(void)
0x1800241ca  mov     [rsp+2B8h+arg_8], eax
0x1800241d1  test    eax, eax
0x1800241d3  jns     short loc_1800241F3
0x1800241d5  lea     rcx, [rsp+2B8h+var_260]
0x1800241da  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800241df  nop
0x1800241e0  lea     rcx, [rsp+2B8h+var_1C8]; this
0x1800241e8  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x1800241ed  nop
0x1800241ee  jmp     loc_180024670
0x1800241f3  mov     [rsp+2B8h+var_220], 20h ; ' '
0x1800241fe  mov     [rsp+2B8h+var_218], r15
0x180024206  mov     [rsp+2B8h+var_210], rsi
0x18002420e  mov     [rsp+2B8h+var_208], rdi
0x180024216  mov     dword ptr [rsp+2B8h+DestinationSize], 1
0x18002421e  lea     rax, [rsp+2B8h+var_220]
0x180024226  mov     [rsp+2B8h+Source], rax
0x18002422b  mov     rcx, rbx; this
0x18002422e  call    ?ResetCancelRequestEvent@CClientSingleIdentity@@QEAAXXZ; CClientSingleIdentity::ResetCancelRequestEvent(void)
0x180024233  mov     esi, r14d
0x180024236  and     esi, 10000h
0x18002423c  jnz     short loc_1800242AC
0x18002423e  shr     r14d, 8
0x180024242  and     r14d, 200h
0x180024249  lea     r8, [rsp+2B8h+DestinationSize]; struct IDCRL::_MultiRSTParams *
0x18002424e  mov     edx, r14d; unsigned int
0x180024251  mov     rcx, rbx; this
0x180024254  call    ?RequestServiceTokenEx@CClientSingleIdentity@@QEAAJKQEAU_MultiRSTParams@IDCRL@@PEBG@Z; CClientSingleIdentity::RequestServiceTokenEx(ulong,IDCRL::_MultiRSTParams * const,ushort const *)
0x180024259  mov     [rsp+2B8h+arg_8], eax
0x180024260  test    eax, eax
0x180024262  jns     short loc_180024282
0x180024264  lea     rcx, [rsp+2B8h+var_260]
0x180024269  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18002426e  nop
0x18002426f  lea     rcx, [rsp+2B8h+var_1C8]; this
0x180024277  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x18002427c  nop
0x18002427d  jmp     loc_180024670
0x180024282  mov     rcx, rbx; this
0x180024285  call    ?IsAsync@CClientSingleIdentity@@QEAA_NXZ; CClientSingleIdentity::IsAsync(void)
0x18002428a  test    al, al
0x18002428c  jz      short loc_1800242AC
0x18002428e  lea     rcx, [rsp+2B8h+var_260]
0x180024293  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180024298  nop
0x180024299  lea     rcx, [rsp+2B8h+var_1C8]; this
0x1800242a1  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x1800242a6  nop
0x1800242a7  jmp     loc_180024670
0x1800242ac  mov     [rsp+2B8h+var_298], edi; unsigned int
0x1800242b0  xor     r9d, r9d; int
0x1800242b3  lea     r8, [rsp+2B8h+var_1C8]; struct CPPCRLToken *
0x1800242bb  mov     rdx, r15; unsigned __int16 *
0x1800242be  mov     rcx, rbx; this
0x1800242c1  call    ?GetServiceToken@CClientSingleIdentity@@QEAAJPEBGAEAVCPPCRLToken@@HK@Z; CClientSingleIdentity::GetServiceToken(ushort const *,CPPCRLToken &,int,ulong)
0x1800242c6  mov     [rsp+2B8h+arg_8], eax
0x1800242cd  test    eax, eax
0x1800242cf  jns     short loc_1800242EF
0x1800242d1  lea     rcx, [rsp+2B8h+var_260]
0x1800242d6  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800242db  nop
0x1800242dc  lea     rcx, [rsp+2B8h+var_1C8]; this
0x1800242e4  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x1800242e9  nop
0x1800242ea  jmp     loc_180024670
0x1800242ef  cmp     [rsp+2B8h+var_1A0], edi
0x1800242f6  jz      short loc_180024325
0x1800242f8  test    esi, esi
0x1800242fa  jnz     short loc_180024329
0x1800242fc  mov     [rsp+2B8h+arg_8], 80048862h
0x180024307  lea     rcx, [rsp+2B8h+var_260]
0x18002430c  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180024311  nop
0x180024312  lea     rcx, [rsp+2B8h+var_1C8]; this
0x18002431a  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x18002431f  nop
0x180024320  jmp     loc_180024670
0x180024325  test    esi, esi
0x180024327  jz      short loc_180024395
0x180024329  cmp     [rsp+2B8h+var_1B0], edi
0x180024330  jz      short loc_180024395
0x180024332  mov     rax, [rsp+2B8h+var_190]
0x18002433a  mov     [rsp+2B8h+var_268], rax
0x18002433f  lea     rcx, [rsp+2B8h+var_268]; struct ATL::CTime *
0x180024344  call    ?IsExpired@CClientTokenInfo@@SA_NAEAVCTime@ATL@@H@Z; CClientTokenInfo::IsExpired(ATL::CTime &,int)
0x180024349  test    al, al
0x18002434b  jz      short loc_180024395
0x18002434d  mov     [rsp+2B8h+arg_8], 80048862h
0x180024358  lea     r9, aServiceTokenIs; "Service token is expired"
0x18002435f  mov     r8d, 0B56h; unsigned int
0x180024365  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002436c  mov     ecx, 5; unsigned __int8
0x180024371  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180024376  nop
0x180024377  lea     rcx, [rsp+2B8h+var_260]
0x18002437c  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180024381  nop
0x180024382  lea     rcx, [rsp+2B8h+var_1C8]; this
0x18002438a  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x18002438f  nop
0x180024390  jmp     loc_180024670
0x180024395  lea     rdx, [rsp+2B8h+var_268]
0x18002439a  lea     rcx, [rsp+2B8h+var_1C8]
0x1800243a2  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x1800243a7  mov     rax, [rax]
0x1800243aa  mov     qword ptr [rsp+2B8h+var_298], rax
0x1800243af  lea     r9, aServiceTokenFo; "Service token for request is:\n%ls\n "
0x1800243b6  mov     r8d, 0B5Bh; unsigned int
0x1800243bc  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x1800243c3  mov     ecx, 5; unsigned __int8
0x1800243c8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800243cd  mov     rcx, [rsp+2B8h+var_268]
0x1800243d2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800243d6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800243db  cmp     [rsp+2B8h+arg_28], rdi
0x1800243e3  jz      short loc_180024458
0x1800243e5  mov     rbx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x1800243ec  lea     rdx, [rsp+2B8h+var_228]
0x1800243f4  lea     rcx, [rsp+2B8h+var_1C8]
0x1800243fc  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x180024401  nop
0x180024402  mov     r8, [rsp+2B8h+arg_28]; unsigned __int16 **
0x18002440a  mov     rdx, [rax]; unsigned __int16 *
0x18002440d  lea     rcx, [rbx+0E8h]; this
0x180024414  call    ?AllocateStringForExternal@CExternalMemoryManager@@QEAAJPEBGPEAPEAG@Z; CExternalMemoryManager::AllocateStringForExternal(ushort const *,ushort * *)
0x180024419  mov     ebx, eax
0x18002441b  mov     [rsp+2B8h+arg_8], eax
0x180024422  mov     rcx, [rsp+2B8h+var_228]
0x18002442a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002442e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024433  shr     ebx, 1Fh
0x180024436  test    bl, bl
0x180024438  jz      short loc_180024458
0x18002443a  lea     rcx, [rsp+2B8h+var_260]
0x18002443f  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180024444  nop
0x180024445  lea     rcx, [rsp+2B8h+var_1C8]; this
0x18002444d  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x180024452  nop
0x180024453  jmp     loc_180024670
0x180024458  cmp     [rsp+2B8h+arg_30], rdi
0x180024460  jz      loc_180024516
0x180024466  lea     rcx, [rsp+2B8h+var_268]
0x18002446b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180024470  nop
0x180024471  lea     rdx, [rsp+2B8h+var_268]
0x180024476  lea     rcx, [rsp+2B8h+var_1C8]
0x18002447e  call    ?GetAuthzToken@CPPCRLToken@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CPPCRLToken::GetAuthzToken(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180024483  mov     [rsp+2B8h+arg_8], eax
0x18002448a  test    eax, eax
0x18002448c  jns     short loc_1800244BB
0x18002448e  mov     rcx, [rsp+2B8h+var_268]
0x180024493  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180024497  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002449c  nop
0x18002449d  lea     rcx, [rsp+2B8h+var_260]
0x1800244a2  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800244a7  nop
0x1800244a8  lea     rcx, [rsp+2B8h+var_1C8]; this
0x1800244b0  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x1800244b5  nop
0x1800244b6  jmp     loc_180024670
0x1800244bb  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x1800244c2  add     rcx, 0E8h; this
0x1800244c9  mov     r8, [rsp+2B8h+arg_30]; unsigned __int16 **
0x1800244d1  mov     rbx, [rsp+2B8h+var_268]
0x1800244d6  mov     rdx, rbx; unsigned __int16 *
0x1800244d9  call    ?AllocateStringForExternal@CExternalMemoryManager@@QEAAJPEBGPEAPEAG@Z; CExternalMemoryManager::AllocateStringForExternal(ushort const *,ushort * *)
0x1800244de  mov     [rsp+2B8h+arg_8], eax
0x1800244e5  lea     rcx, [rbx-18h]; this
0x1800244e9  test    eax, eax
0x1800244eb  jns     short loc_180024511
0x1800244ed  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800244f2  nop
0x1800244f3  lea     rcx, [rsp+2B8h+var_260]
0x1800244f8  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800244fd  nop
0x1800244fe  lea     rcx, [rsp+2B8h+var_1C8]; this
0x180024506  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x18002450b  nop
0x18002450c  jmp     loc_180024670
0x180024511  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024516  mov     ebx, [rsp+2B8h+var_1B0]
0x18002451d  mov     [rsp+2B8h+var_298], ebx
0x180024521  lea     r9, aInternalTokenT; "Internal token type: %d"
0x180024528  mov     r8d, 0B76h; unsigned int
0x18002452e  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180024535  mov     ecx, 5; unsigned __int8
0x18002453a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002453f  mov     esi, edi
0x180024541  cmp     ebx, 1
0x180024544  setz    sil
0x180024548  inc     esi
0x18002454a  test    r13, r13
0x18002454d  jz      loc_180024645
0x180024553  test    r12, r12
  ... truncated ...
```
