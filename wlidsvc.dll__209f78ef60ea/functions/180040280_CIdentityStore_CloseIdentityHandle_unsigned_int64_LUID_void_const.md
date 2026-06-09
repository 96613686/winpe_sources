# CIdentityStore::CloseIdentityHandle(unsigned __int64,_LUID &,void * const)

- ea: `0x180040280`
- end: `0x1800406a0`
- name: `?CloseIdentityHandle@CIdentityStore@@QEAAJ_KAEAU_LUID@@QEAX@Z`
- size: `1056`
- prototype: `__int64 __fastcall(CIdentityStore *__hidden this, unsigned __int64, struct _LUID *, void *const)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180040084`
- `0x1800b10d0`

## callees

- `0x18000c050`
- `0x18000cfac`
- `0x18000ed04`
- `0x18000ed3c`
- `0x18000fd04`
- `0x180013fb4`
- `0x180014850`
- `0x1800151c4`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001cf20`
- `0x180021c80`
- `0x180039d60`
- `0x18003b044`
- `0x18003ba08`
- `0x18003c814`
- `0x18003ee14`
- `0x180040280`
- `0x180048004`
- `0x18004aff8`
- `0x18005136c`
- `0x180051f3c`
- `0x18007c38c`
- `0x1800e3f68`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004040d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004040d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040425`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040425`

## string_xrefs

- `0x1800402fd`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x1800404a0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x180040637`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x18004061e`: `m_mapHandles.RemoveKey(handle)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIdentityStore::CloseIdentityHandle(
        struct _RTL_CRITICAL_SECTION *this,
        int a2,
        struct _LUID *a3,
        void *const a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // r15
  __int64 Node; // rax
  int v10; // r9d
  const char *v11; // rax
  unsigned int v12; // r8d
  char v13; // si
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v16; // eax
  bool v17; // di
  CSingleIdentity *v18; // rbx
  __int64 v19; // rdi
  __int64 *v20; // rax
  unsigned int i; // r15d
  CSingleIdentity **v22; // rax
  CSingleIdentity **v23; // rax
  CPassportClientLibrary *v24; // rbx
  _QWORD *v25; // rax
  void *v26; // rdx
  unsigned int v27; // ebx
  __int64 v29; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v30[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v31; // [rsp+68h] [rbp-21h] BYREF
  __int128 v32; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v33[8]; // [rsp+80h] [rbp-9h] BYREF
  const char *v34[11]; // [rsp+88h] [rbp-1h] BYREF
  int v35; // [rsp+F0h] [rbp+67h] BYREF
  const void *v36; // [rsp+100h] [rbp+77h] BYREF

  v35 = 0;
  v32 = 0u;
  v29 = 0;
  CTraceFuncW<long>::CTraceFuncW<long>(
    v34,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
    860,
    (const char *)&v35,
    "CIdentityStore::CloseIdentityHandle",
    L"LogonId.LowPart='%d, LogonId.HighPart='%d, handle=%p",
    a3->LowPart,
    a3->HighPart,
    a4);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
    (__int64)v30,
    this,
    1);
  v8 = this + 1;
  LODWORD(v31) = 0;
  LODWORD(v36) = 0;
  Node = ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::GetNode(
           (int)this + 40,
           (_DWORD)a4,
           (unsigned int)&v31,
           (unsigned int)&v36,
           (__int64)v33);
  if ( !Node )
  {
    v35 = -2147188724;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
      "CIdentityStore::CloseIdentityHandle",
      0x363u,
      -2147188724,
      "pPair != nullptr");
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v30);
    goto LABEL_43;
  }
  v29 = *(_QWORD *)(Node + 8);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v30);
  if ( !v29 )
  {
    v10 = -2147418113;
    v11 = "pContext != nullptr";
    v12 = 872;
LABEL_5:
    v35 = v10;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
      "CIdentityStore::CloseIdentityHandle",
      v12,
      v10,
      v11);
    goto LABEL_43;
  }
  if ( *(_BYTE *)(v29 + 52)
    && (a3->LowPart != *(_DWORD *)(v29 + 8) || a3->HighPart != *(_DWORD *)(v29 + 12))
    && (a3->LowPart || a3->HighPart) )
  {
    v10 = -2147188724;
    v11 = "WLIDEqualLuid(&logonId, &pContext->m_LogonId) || WLIDEqualLuid(&logonId, &EmptyLuid)";
    v12 = 876;
    goto LABEL_5;
  }
  v13 = 0;
  CAutoRefPtr<CSingleIdentity>::operator=(&v32);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, (PHANDLE)&v32 + 1) )
  {
    v17 = a3->LowPart || a3->HighPart;
  }
  else
  {
    if ( GetLastError() != 1008 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v35 = LastError;
      goto LABEL_43;
    }
    if ( *(_QWORD *)(v29 + 24) )
    {
      if ( !ATL::CAccessToken::ImpersonateLoggedOnUser((ATL::CAccessToken *)(v29 + 16)) )
      {
        v16 = GetLastError();
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        v35 = v16;
        if ( v16 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
            "CIdentityStore::CloseIdentityHandle",
            0x380u,
            v16,
            "hr = HRESULT_FROM_WIN32(GetLastError())");
          goto LABEL_43;
        }
      }
      v13 = 1;
    }
    v17 = v13;
  }
  if ( *(_QWORD *)(v29 + 56) )
  {
    v30[0] = &v29;
    v30[1] = a3;
    lambda_6424070e0f31c982db47ffed3b6697bb_::operator()(v30);
  }
  v18 = (CSingleIdentity *)v32;
  if ( ((*(_QWORD *)&a2 & 0x10000LL) == 0 || g_lShutdownInProgress <= 0) && v17 )
  {
    CSingleIdentity::SaveExtProperties((CSingleIdentity *)v32);
    v19 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v18 + 8LL))(v18);
    v20 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&v36,
            L"ps:password");
    if ( (unsigned __int8)CIdentityCredentialBag::HasPersistedCredential(v19, v20) == 1 )
    {
      CSingleIdentity::PersistServiceTokens(v18);
      CSingleIdentity::PersistCertificates(v18);
      for ( i = 0; (unsigned __int64)i < *((_QWORD *)v18 + 72); ++i )
      {
        v22 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                    (char *)v18 + 568,
                                    i);
        CSingleIdentity::PersistServiceTokens(*v22);
        v23 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                    (char *)v18 + 568,
                                    i);
        CSingleIdentity::PersistCertificates(*v23);
      }
      v8 = this + 1;
    }
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v36,
    L"%p",
    v18);
  v24 = g_pPPCRL;
  v25 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v31,
          &v36);
  CCertManager::FlushCert((char *)v24 + 1376, v25);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
  if ( v13 )
    ATL::CAccessToken::Revert((ATL::CAccessToken *)(v29 + 16), v26);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
    (__int64)v30,
    this,
    1);
  if ( !(unsigned __int8)ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::RemoveKey(
                           v8,
                           a4) )
  {
    v35 = -2147188724;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
      "CIdentityStore::CloseIdentityHandle",
      0x3DAu,
      -2147188724,
      "m_mapHandles.RemoveKey(handle)");
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v30);
LABEL_43:
  if ( *((_QWORD *)&v32 + 1) )
    CloseHandle(*((HANDLE *)&v32 + 1));
  v27 = v35;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v34);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v32);
  return v27;
}

```

## disassembly

```asm
0x180040280  mov     [rsp-8+arg_8], rbx
0x180040285  push    rbp
0x180040286  push    rsi
0x180040287  push    rdi
0x180040288  push    r12
0x18004028a  push    r13
0x18004028c  push    r14
0x18004028e  push    r15
0x180040290  lea     rbp, [rsp-27h]
0x180040295  sub     rsp, 0B0h
0x18004029c  mov     r12, r9
0x18004029f  mov     rbx, r8
0x1800402a2  mov     r14, rdx
0x1800402a5  mov     r13, rcx
0x1800402a8  mov     [rbp+57h+arg_0], 0
0x1800402af  mov     qword ptr [rbp+57h+var_70], 0
0x1800402b7  mov     [rbp+57h+var_90], 0
0x1800402bf  mov     qword ptr [rbp+57h+var_70+8], 0
0x1800402c7  mov     [rsp+0E0h+var_A0], r9
0x1800402cc  mov     eax, [r8+4]
0x1800402d0  mov     [rsp+0E0h+var_A8], eax
0x1800402d4  mov     eax, [r8]
0x1800402d7  mov     [rsp+0E0h+var_B0], eax
0x1800402db  lea     rax, aLogonidLowpart_0; "LogonId.LowPart='%d, LogonId.HighPart='"...
0x1800402e2  mov     [rsp+0E0h+var_B8], rax
0x1800402e7  lea     rdi, aCidentitystore_0; "CIdentityStore::CloseIdentityHandle"
0x1800402ee  mov     [rsp+0E0h+var_C0], rdi
0x1800402f3  lea     r9, [rbp+57h+arg_0]
0x1800402f7  mov     r8d, 35Ch
0x1800402fd  lea     rsi, aOnecoreuapDsEx_92; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180040304  mov     rdx, rsi
0x180040307  lea     rcx, [rbp+57h+var_58]
0x18004030b  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x180040310  nop
0x180040311  mov     r8b, 1
0x180040314  mov     rdx, r13
0x180040317  lea     rcx, [rbp+57h+var_88]
0x18004031b  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x180040320  lea     r15, [r13+28h]
0x180040324  mov     dword ptr [rbp+57h+var_78], 0
0x18004032b  mov     dword ptr [rbp+57h+arg_10], 0
0x180040332  lea     rax, [rbp+57h+var_60]
0x180040336  mov     [rsp+0E0h+var_C0], rax
0x18004033b  lea     r9, [rbp+57h+arg_10]
0x18004033f  lea     r8, [rbp+57h+var_78]
0x180040343  mov     rdx, r12
0x180040346  mov     rcx, r15
0x180040349  call    ?GetNode@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDContext@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDContext@@@2@@ATL@@AEBAPEAVCNode@12@PEAXAEAI1AEAPEAV312@@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::GetNode(void *,uint &,uint &,ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::CNode * &)
0x18004034e  test    rax, rax
0x180040351  jnz     short loc_180040388
0x180040353  mov     r9d, 8004800Ch; int
0x180040359  mov     [rbp+57h+arg_0], r9d
0x18004035d  lea     rax, aPpairNullptr; "pPair != nullptr"
0x180040364  mov     [rsp+0E0h+var_C0], rax; char *
0x180040369  mov     r8d, 363h; unsigned int
0x18004036f  mov     rdx, rdi; char *
0x180040372  mov     rcx, rsi; char *
0x180040375  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18004037a  lea     rcx, [rbp+57h+var_88]
0x18004037e  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180040383  jmp     loc_18004065E
0x180040388  mov     rax, [rax+8]
0x18004038c  mov     [rbp+57h+var_90], rax
0x180040390  lea     rcx, [rbp+57h+var_88]
0x180040394  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180040399  mov     rdx, [rbp+57h+var_90]
0x18004039d  test    rdx, rdx
0x1800403a0  jnz     short loc_1800403CE
0x1800403a2  mov     r9d, 8000FFFFh; int
0x1800403a8  lea     rax, aPcontextNullpt_0; "pContext != nullptr"
0x1800403af  mov     r8d, 368h; unsigned int
0x1800403b5  mov     [rsp+0E0h+var_C0], rax; char *
0x1800403ba  mov     [rbp+57h+arg_0], r9d
0x1800403be  mov     rcx, rsi; char *
0x1800403c1  mov     rdx, rdi; char *
0x1800403c4  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800403c9  jmp     loc_18004065E
0x1800403ce  cmp     byte ptr [rdx+34h], 0
0x1800403d2  jz      short loc_180040401
0x1800403d4  mov     ecx, [rbx]
0x1800403d6  cmp     ecx, [rdx+8]
0x1800403d9  jnz     short loc_1800403E3
0x1800403db  mov     eax, [rdx+0Ch]
0x1800403de  cmp     [rbx+4], eax
0x1800403e1  jz      short loc_180040401
0x1800403e3  test    ecx, ecx
0x1800403e5  jnz     short loc_1800403EC
0x1800403e7  cmp     [rbx+4], ecx
0x1800403ea  jz      short loc_180040401
0x1800403ec  mov     r9d, 8004800Ch
0x1800403f2  lea     rax, aWlidequalluidL_1; "WLIDEqualLuid(&logonId, &pContext->m_Lo"...
0x1800403f9  mov     r8d, 36Ch
0x1800403ff  jmp     short loc_1800403B5
0x180040401  xor     sil, sil
0x180040404  lea     rcx, [rbp+57h+var_70]
0x180040408  call    ??4?$CAutoRefPtr@VCSingleIdentity@@@@QEAAAEAV0@AEBV0@@Z; CAutoRefPtr<CSingleIdentity>::operator=(CAutoRefPtr<CSingleIdentity> const &)
0x18004040d  call    cs:__imp_GetCurrentThread
0x180040413  mov     rcx, rax; ThreadHandle
0x180040416  lea     r9, [rbp+57h+var_70+8]; TokenHandle
0x18004041a  mov     edx, 0F01FFh; DesiredAccess
0x18004041f  mov     r8d, 1; OpenAsSelf
0x180040425  call    cs:__imp_OpenThreadToken
0x18004042b  test    eax, eax
0x18004042d  jnz     loc_1800404B4
0x180040433  call    cs:__imp_GetLastError
0x180040439  cmp     eax, 3F0h
0x18004043e  jz      short loc_18004045A
0x180040440  call    cs:__imp_GetLastError
0x180040446  test    eax, eax
0x180040448  jle     short loc_180040452
0x18004044a  movzx   eax, ax
0x18004044d  or      eax, 80070000h
0x180040452  mov     [rbp+57h+arg_0], eax
0x180040455  jmp     loc_18004065E
0x18004045a  mov     rcx, [rbp+57h+var_90]
0x18004045e  add     rcx, 10h; this
0x180040462  cmp     qword ptr [rcx+8], 0
0x180040467  jz      short loc_1800404AF
0x180040469  call    ?ImpersonateLoggedOnUser@CAccessToken@ATL@@QEBA_NXZ; ATL::CAccessToken::ImpersonateLoggedOnUser(void)
0x18004046e  test    al, al
0x180040470  jnz     short loc_1800404AC
0x180040472  call    cs:__imp_GetLastError
0x180040478  test    eax, eax
0x18004047a  jle     short loc_180040484
0x18004047c  movzx   eax, ax
0x18004047f  or      eax, 80070000h
0x180040484  mov     [rbp+57h+arg_0], eax
0x180040487  test    eax, eax
0x180040489  jns     short loc_1800404AC
0x18004048b  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180040492  mov     [rsp+0E0h+var_C0], rcx
0x180040497  mov     r9d, eax
0x18004049a  mov     r8d, 380h
0x1800404a0  lea     rcx, aOnecoreuapDsEx_92; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800404a7  jmp     loc_1800403C1
0x1800404ac  mov     sil, 1
0x1800404af  mov     dil, sil
0x1800404b2  jmp     short loc_1800404C7
0x1800404b4  cmp     dword ptr [rbx], 0
0x1800404b7  jnz     short loc_1800404C4
0x1800404b9  cmp     dword ptr [rbx+4], 0
0x1800404bd  jnz     short loc_1800404C4
0x1800404bf  xor     dil, dil
0x1800404c2  jmp     short loc_1800404C7
0x1800404c4  mov     dil, 1
0x1800404c7  mov     rax, [rbp+57h+var_90]
0x1800404cb  cmp     qword ptr [rax+38h], 0
0x1800404d0  jz      short loc_1800404E7
0x1800404d2  lea     rax, [rbp+57h+var_90]
0x1800404d6  mov     [rbp+57h+var_88], rax
0x1800404da  mov     [rbp+57h+var_80], rbx
0x1800404de  lea     rcx, [rbp+57h+var_88]
0x1800404e2  call    _lambda_6424070e0f31c982db47ffed3b6697bb___operator__
0x1800404e7  mov     rbx, qword ptr [rbp+57h+var_70]
0x1800404eb  bt      r14, 10h
0x1800404f0  jnb     short loc_1800404FF
0x1800404f2  cmp     cs:?g_lShutdownInProgress@@3JA, 0; long g_lShutdownInProgress
0x1800404f9  jg      loc_180040597
0x1800404ff  test    dil, dil
0x180040502  jz      loc_180040597
0x180040508  mov     rcx, rbx; this
0x18004050b  call    ?SaveExtProperties@CSingleIdentity@@QEAAJXZ; CSingleIdentity::SaveExtProperties(void)
0x180040510  mov     rax, [rbx]
0x180040513  mov     rcx, rbx
0x180040516  mov     rax, [rax+8]
0x18004051a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004051f  mov     rdi, rax
0x180040522  lea     rdx, aPsPassword_0; "ps:password"
0x180040529  lea     rcx, [rbp+57h+arg_10]
0x18004052d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180040532  mov     rdx, rax
0x180040535  mov     rcx, rdi
0x180040538  call    ?HasPersistedCredential@CIdentityCredentialBag@@QEAA_NV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CIdentityCredentialBag::HasPersistedCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18004053d  cmp     al, 1
0x18004053f  jnz     short loc_180040597
0x180040541  mov     rcx, rbx; this
0x180040544  call    ?PersistServiceTokens@CSingleIdentity@@QEAAJXZ; CSingleIdentity::PersistServiceTokens(void)
0x180040549  mov     rcx, rbx; this
0x18004054c  call    ?PersistCertificates@CSingleIdentity@@QEAAJXZ; CSingleIdentity::PersistCertificates(void)
0x180040551  lea     r14, [rbx+238h]
0x180040558  xor     r15d, r15d
0x18004055b  cmp     [r14+8], r15
0x18004055f  jbe     short loc_180040593
0x180040561  mov     edx, r15d
0x180040564  mov     rcx, r14
0x180040567  call    ??A?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAAAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](unsigned __int64)
0x18004056c  mov     rcx, [rax]; this
0x18004056f  call    ?PersistServiceTokens@CSingleIdentity@@QEAAJXZ; CSingleIdentity::PersistServiceTokens(void)
0x180040574  mov     edx, r15d
0x180040577  mov     rcx, r14
0x18004057a  call    ??A?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAAAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](unsigned __int64)
0x18004057f  mov     rcx, [rax]; this
0x180040582  call    ?PersistCertificates@CSingleIdentity@@QEAAJXZ; CSingleIdentity::PersistCertificates(void)
0x180040587  inc     r15d
0x18004058a  mov     eax, r15d
0x18004058d  cmp     rax, [r14+8]
0x180040591  jb      short loc_180040561
0x180040593  lea     r15, [r13+28h]
0x180040597  lea     rcx, [rbp+57h+arg_10]
0x18004059b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800405a0  nop
0x1800405a1  mov     r8, rbx
0x1800405a4  lea     rdx, aP; "%p"
0x1800405ab  lea     rcx, [rbp+57h+arg_10]
0x1800405af  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800405b4  mov     rbx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x1800405bb  lea     rdx, [rbp+57h+arg_10]
0x1800405bf  lea     rcx, [rbp+57h+var_78]
0x1800405c3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800405c8  mov     rdx, rax
0x1800405cb  lea     rcx, [rbx+560h]
0x1800405d2  call    ?FlushCert@CCertManager@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CCertManager::FlushCert(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x1800405d7  nop
0x1800405d8  lea     rcx, [rbp+57h+arg_10]
0x1800405dc  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800405e1  test    sil, sil
0x1800405e4  jz      short loc_1800405F6
0x1800405e6  mov     rcx, [rbp+57h+var_90]
0x1800405ea  add     rcx, 10h; this
0x1800405ee  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x1800405f3  xor     sil, sil
0x1800405f6  mov     r8b, 1
0x1800405f9  mov     rdx, r13
0x1800405fc  lea     rcx, [rbp+57h+var_88]
0x180040600  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x180040605  mov     rdx, r12
0x180040608  mov     rcx, r15
0x18004060b  call    ?RemoveKey@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDContext@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDContext@@@2@@ATL@@QEAA_NPEAX@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::RemoveKey(void *)
0x180040610  test    al, al
0x180040612  jnz     short loc_180040643
0x180040614  mov     r9d, 8004800Ch; int
0x18004061a  mov     [rbp+57h+arg_0], r9d
0x18004061e  lea     rax, aMMaphandlesRem; "m_mapHandles.RemoveKey(handle)"
0x180040625  mov     [rsp+0E0h+var_C0], rax; char *
0x18004062a  mov     r8d, 3DAh; unsigned int
0x180040630  lea     rdx, aCidentitystore_0; "CIdentityStore::CloseIdentityHandle"
0x180040637  lea     rcx, aOnecoreuapDsEx_92; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004063e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180040643  lea     rcx, [rbp+57h+var_88]
0x180040647  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18004064c  test    sil, sil
0x18004064f  jz      short loc_18004065E
0x180040651  mov     rcx, [rbp+57h+var_90]
0x180040655  add     rcx, 10h; this
0x180040659  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x18004065e  mov     rcx, qword ptr [rbp+57h+var_70+8]; hObject
0x180040662  test    rcx, rcx
0x180040665  jz      short loc_18004066D
0x180040667  call    cs:__imp_CloseHandle
0x18004066d  mov     ebx, [rbp+57h+arg_0]
0x180040670  lea     rcx, [rbp+57h+var_58]
0x180040674  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180040679  nop
0x18004067a  lea     rcx, [rbp+57h+var_70]
0x18004067e  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x180040683  mov     eax, ebx
0x180040685  mov     rbx, [rsp+0E0h+arg_8]
0x18004068d  add     rsp, 0B0h
0x180040694  pop     r15
0x180040696  pop     r14
0x180040698  pop     r13
0x18004069a  pop     r12
0x18004069c  pop     rdi
0x18004069d  pop     rsi
0x18004069e  pop     rbp
0x18004069f  retn
```
