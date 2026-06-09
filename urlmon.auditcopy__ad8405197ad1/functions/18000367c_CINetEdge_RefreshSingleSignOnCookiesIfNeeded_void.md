# CINetEdge::RefreshSingleSignOnCookiesIfNeeded(void)

- ea: `0x18000367c`
- end: `0x180003bd7`
- name: `?RefreshSingleSignOnCookiesIfNeeded@CINetEdge@@AEAAXXZ`
- size: `1371`
- prototype: `void __fastcall(CINetEdge *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009b550`

## callees

- `0x18000367c`
- `0x180003be0`
- `0x180003d8c`
- `0x180003e28`
- `0x180004040`
- `0x1800041d4`
- `0x180004384`
- `0x18000523c`
- `0x18000b2e0`
- `0x18000b490`
- `0x180018bfc`
- `0x180028410`
- `0x1800de218`
- `0x18012250c`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180003979`
- `msvcrt!wcsstr` at `0x180003979`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800039fa`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003ac5`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800039fa`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003ac5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800036ce`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180003950`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800039a0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800039b9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800036ce`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180003950`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800039a0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800039b9`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800039d6`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800039d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003759`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003759`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000372c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000372c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800038f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800038f4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800037b7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800037b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003908`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003908`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800037d0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800037d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003843`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003843`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x1800036e4`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x1800036e4`

## pseudocode

```c
void __fastcall CINetEdge::RefreshSingleSignOnCookiesIfNeeded(CINetEdge *this)
{
  CINetEdge *v2; // rcx
  ProofOfPossessionTokenProvider *v3; // rsi
  const wchar_t *SingleSignOnLoginUrl; // rax
  const WCHAR *v5; // r14
  CINetEdge *v6; // rcx
  const unsigned __int16 *AadSingleSignOnLoginUrls; // rax
  const unsigned __int16 *v8; // r8
  char *AadLoginUrlMatch; // rbx
  bool v10; // r15
  char v11; // r13
  wchar_t *v12; // r12
  HRESULT Instance; // r15d
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r12
  void *v16; // rcx
  int DWORD; // eax
  HRESULT v18; // eax
  unsigned int *v19; // rcx
  void *v20; // rcx
  HRESULT v21; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-A5h] BYREF
  unsigned int *v23; // [rsp+38h] [rbp-A1h] BYREF
  unsigned int *v24; // [rsp+40h] [rbp-99h] BYREF
  struct IEUserBroker *v25; // [rsp+48h] [rbp-91h] BYREF
  CINetEdge *v26; // [rsp+50h] [rbp-89h] BYREF
  char v27; // [rsp+58h] [rbp-81h]
  _QWORD v28[3]; // [rsp+60h] [rbp-79h] BYREF
  bool v29; // [rsp+78h] [rbp-61h]
  GUID pguid; // [rsp+80h] [rbp-59h] BYREF
  OLECHAR sz; // [rsp+90h] [rbp-49h] BYREF
  unsigned __int16 v32[39]; // [rsp+92h] [rbp-47h] BYREF

  v26 = this;
  v27 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 300);
  if ( CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v26) )
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(268435481) )
      IEConfiguration_GetBool(268435482);
    v21 = CoInitialize(0);
    if ( v21 >= 0 )
    {
      v3 = (ProofOfPossessionTokenProvider *)*((_QWORD *)this + 43);
      v22 = 0;
      if ( !v3 )
        v3 = (ProofOfPossessionTokenProvider *)*((_QWORD *)this + 23);
      SingleSignOnLoginUrl = CINetEdge::GetSingleSignOnLoginUrl(v2);
      v5 = SingleSignOnLoginUrl;
      if ( SingleSignOnLoginUrl && wcsstr((const wchar_t *)v3, SingleSignOnLoginUrl) )
      {
        AadLoginUrlMatch = 0;
        v11 = 1;
        v10 = 0;
      }
      else
      {
        EnterCriticalSection(&g_mxsSession);
        AadSingleSignOnLoginUrls = CINetEdge::GetAadSingleSignOnLoginUrls(v6);
        AadLoginUrlMatch = ProofOfPossessionTokenProvider::GetAadLoginUrlMatch(v3, AadSingleSignOnLoginUrls, v8);
        v10 = AadLoginUrlMatch != 0;
        LeaveCriticalSection(&g_mxsSession);
        if ( !AadLoginUrlMatch || (v11 = 0, !*((_QWORD *)this + 47)) )
        {
LABEL_28:
          CoUninitialize();
          if ( AadLoginUrlMatch )
            CoTaskMemFree(AadLoginUrlMatch);
          goto LABEL_30;
        }
      }
      v12 = 0;
      v29 = v10;
      v28[0] = 0;
      v28[1] = &v22;
      v28[2] = &v21;
      memset_0(&sz, 0, 0x4Eu);
      pguid = 0;
      CoCreateGuid(&pguid);
      if ( StringFromGUID2(&pguid, &sz, 39) > 0 )
      {
        v32[36] = 0;
        v28[0] = OLESTRDuplicate(v32);
        v12 = (wchar_t *)v28[0];
        if ( v28[0] )
        {
          if ( v10 )
            BrowserTelemetry::SingleSignOnGetCookiesAadStarted<unsigned short const * &>();
          else
            BrowserTelemetry::SingleSignOnGetCookiesMsaStarted<unsigned short const * &>();
        }
      }
      if ( !(unsigned int)IsABrowserApp()
        || !(unsigned __int8)IEConfiguration_GetBool(536870916)
        || (unsigned __int8)IEConfiguration_GetBool(536870913) )
      {
        v23 = 0;
        *(_QWORD *)&pguid.Data1 = 0;
        Instance = CoCreateInstance(
                     &GUID_a9927f85_a304_4390_8b23_a75f1c668600,
                     0,
                     1u,
                     &GUID_cdaece56_4edf_43df_b113_88e4556fa1bb,
                     (LPVOID *)&pguid);
        if ( Instance >= 0 )
        {
          v14 = AddCorrelationIdParameter((const unsigned __int16 *)v3, v12);
          v15 = v14;
          if ( v14 )
            v3 = (ProofOfPossessionTokenProvider *)v14;
          Instance = (*(__int64 (__fastcall **)(_QWORD, ProofOfPossessionTokenProvider *, unsigned int *, unsigned int **))(**(_QWORD **)&pguid.Data1 + 24LL))(
                       *(_QWORD *)&pguid.Data1,
                       v3,
                       &v22,
                       &v23);
          if ( v15 )
            CoTaskMemFree(v15);
        }
        if ( *(_QWORD *)&pguid.Data1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pguid.Data1 + 16LL))(*(_QWORD *)&pguid.Data1);
        v21 = Instance;
        if ( Instance >= 0 && v22 )
        {
          if ( v11 )
          {
            v16 = 0;
          }
          else
          {
            v16 = (void *)*((_QWORD *)this + 47);
            v5 = (const WCHAR *)AadLoginUrlMatch;
          }
          ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(v16, v5, v22, v23);
        }
        goto LABEL_27;
      }
      *(_QWORD *)&pguid.Data1 = 0;
      DWORD = IEConfiguration_GetDWORD(268435501);
      v25 = 0;
      if ( DWORD == 2 )
      {
        v23 = 0;
        v21 = CoCreateUserBroker(&v25);
        if ( v21 < 0 )
          goto LABEL_27;
        v24 = 0;
        v21 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, unsigned int **))(*(_QWORD *)v25 + 48LL))(
                v25,
                &CLSID_CEdgeManagerBroker,
                &IID_IUnknown,
                &v24);
        if ( v21 >= 0 )
        {
          v21 = (**(__int64 (__fastcall ***)(unsigned int *, GUID *, unsigned int **))v24)(
                  v24,
                  &GUID_26ea2529_1012_4dd2_8a8b_3d2de75d3529,
                  &v23);
          (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v24 + 16LL))(v24);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v25 + 16LL))(v25);
        if ( v21 < 0 )
          goto LABEL_27;
        v18 = (*(__int64 (__fastcall **)(unsigned int *, ProofOfPossessionTokenProvider *, wchar_t *, unsigned int *, GUID *))(*(_QWORD *)v23 + 72LL))(
                v23,
                v3,
                v12,
                &v22,
                &pguid);
        v19 = v23;
      }
      else
      {
        v24 = 0;
        v21 = CoCreateUserBroker(&v25);
        if ( v21 < 0 )
          goto LABEL_27;
        v23 = 0;
        v21 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, unsigned int **))(*(_QWORD *)v25 + 48LL))(
                v25,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v23);
        if ( v21 >= 0 )
        {
          v21 = (**(__int64 (__fastcall ***)(unsigned int *, GUID *, unsigned int **))v23)(
                  v23,
                  &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                  &v24);
          (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v23 + 16LL))(v23);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v25 + 16LL))(v25);
        if ( v21 < 0 )
          goto LABEL_27;
        v18 = (*(__int64 (__fastcall **)(unsigned int *, ProofOfPossessionTokenProvider *, wchar_t *, unsigned int *, GUID *))(*(_QWORD *)v24 + 1152LL))(
                v24,
                v3,
                v12,
                &v22,
                &pguid);
        v19 = v24;
      }
      v21 = v18;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v21 >= 0 && v22 )
      {
        if ( v11 )
        {
          v20 = 0;
        }
        else
        {
          v20 = (void *)*((_QWORD *)this + 47);
          v5 = (const WCHAR *)AadLoginUrlMatch;
        }
        ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<_IEProofOfPossessionToken>(
          v20,
          v5,
          v22,
          *(unsigned int **)&pguid.Data1);
      }
LABEL_27:
      SingleSignonTelemetryHelper::~SingleSignonTelemetryHelper((SingleSignonTelemetryHelper *)v28);
      goto LABEL_28;
    }
  }
LABEL_30:
  CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v26);
}

```

## disassembly

```asm
0x18000367c  push    rbp
0x18000367e  push    rbx
0x18000367f  push    rsi
0x180003680  push    rdi
0x180003681  push    r12
0x180003683  push    r13
0x180003685  push    r14
0x180003687  push    r15
0x180003689  lea     rbp, [rsp-1Fh]
0x18000368e  sub     rsp, 0F8h
0x180003695  mov     rax, cs:__security_cookie
0x18000369c  xor     rax, rsp
0x18000369f  mov     [rbp+57h+var_50], rax
0x1800036a3  mov     rdi, rcx
0x1800036a6  mov     [rsp+130h+var_E0], rcx
0x1800036ab  mov     [rsp+130h+var_D8], 0
0x1800036b0  lock inc dword ptr [rcx+4B0h]
0x1800036b7  lea     rcx, [rsp+130h+var_E0]; this
0x1800036bc  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x1800036c1  test    al, al
0x1800036c3  jz      loc_180003914
0x1800036c9  mov     ecx, 10000019h
0x1800036ce  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800036d5  nop     dword ptr [rax+rax+00h]
0x1800036da  test    al, al
0x1800036dc  jz      loc_18000394B
0x1800036e2  xor     ecx, ecx; pvReserved
0x1800036e4  call    cs:__imp_CoInitialize
0x1800036eb  nop     dword ptr [rax+rax+00h]
0x1800036f0  mov     [rsp+130h+var_100], eax
0x1800036f4  test    eax, eax
0x1800036f6  js      loc_180003914
0x1800036fc  mov     rsi, [rdi+158h]
0x180003703  mov     [rsp+130h+var_FC], 0
0x18000370b  test    rsi, rsi
0x18000370e  jz      loc_18000393F
0x180003714  call    ?GetSingleSignOnLoginUrl@CINetEdge@@IEAAPEBGXZ; CINetEdge::GetSingleSignOnLoginUrl(void)
0x180003719  mov     r14, rax
0x18000371c  test    rax, rax
0x18000371f  jnz     loc_180003973
0x180003725  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x18000372c  call    cs:__imp_EnterCriticalSection
0x180003733  nop     dword ptr [rax+rax+00h]
0x180003738  call    ?GetAadSingleSignOnLoginUrls@CINetEdge@@AEAAPEBGXZ; CINetEdge::GetAadSingleSignOnLoginUrls(void)
0x18000373d  mov     rdx, rax; unsigned __int16 *
0x180003740  mov     rcx, rsi; this
0x180003743  call    ?GetAadLoginUrlMatch@ProofOfPossessionTokenProvider@@YAPEAGPEBG0@Z; ProofOfPossessionTokenProvider::GetAadLoginUrlMatch(ushort const *,ushort const *)
0x180003748  test    rax, rax
0x18000374b  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x180003752  mov     rbx, rax
0x180003755  setnz   r15b
0x180003759  call    cs:__imp_LeaveCriticalSection
0x180003760  nop     dword ptr [rax+rax+00h]
0x180003765  test    rbx, rbx
0x180003768  jz      loc_1800038F4
0x18000376e  xor     r13b, r13b
0x180003771  cmp     qword ptr [rdi+178h], 0
0x180003779  jz      loc_1800038F4
0x18000377f  xor     r12d, r12d
0x180003782  mov     [rbp+57h+var_B8], r15b
0x180003786  lea     rax, [rsp+130h+var_FC]
0x18000378b  mov     [rbp+57h+var_D0], r12
0x18000378f  mov     [rbp+57h+var_C8], rax
0x180003793  lea     rcx, [rbp+57h+sz]; void *
0x180003797  lea     rax, [rsp+130h+var_100]
0x18000379c  xor     edx, edx; Val
0x18000379e  lea     r8d, [r12+4Eh]; Size
0x1800037a3  mov     [rbp+57h+var_C0], rax
0x1800037a7  call    memset_0
0x1800037ac  xorps   xmm0, xmm0
0x1800037af  lea     rcx, [rbp+57h+pguid]; pguid
0x1800037b3  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800037b7  call    cs:__imp_CoCreateGuid
0x1800037be  nop     dword ptr [rax+rax+00h]
0x1800037c3  lea     r8d, [r12+27h]; cchMax
0x1800037c8  lea     rdx, [rbp+57h+sz]; lpsz
0x1800037cc  lea     rcx, [rbp+57h+pguid]; rguid
0x1800037d0  call    cs:__imp_StringFromGUID2
0x1800037d7  nop     dword ptr [rax+rax+00h]
0x1800037dc  test    eax, eax
0x1800037de  jle     short loc_18000380D
0x1800037e0  xor     eax, eax
0x1800037e2  lea     rcx, [rbp+57h+var_9E]; unsigned __int16 *
0x1800037e6  mov     [rbp+57h+var_56], ax
0x1800037ea  call    ?OLESTRDuplicate@@YAPEAGPEBG@Z; OLESTRDuplicate(ushort const *)
0x1800037ef  mov     [rbp+57h+var_D0], rax
0x1800037f3  mov     r12, rax
0x1800037f6  test    rax, rax
0x1800037f9  jz      short loc_18000380D
0x1800037fb  lea     rcx, [rbp+57h+var_D0]
0x1800037ff  test    r15b, r15b
0x180003802  jz      loc_180003969
0x180003808  call    ??$SingleSignOnGetCookiesAadStarted@AEAPEBG@BrowserTelemetry@@SAXAEAPEBG@Z; BrowserTelemetry::SingleSignOnGetCookiesAadStarted<ushort const * &>(ushort const * &)
0x18000380d  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x180003812  xor     r15d, r15d
0x180003815  test    eax, eax
0x180003817  jnz     loc_18000399B
0x18000381d  xor     edx, edx; pUnkOuter
0x18000381f  mov     [rsp+130h+var_F8], r15
0x180003824  lea     rax, [rbp+57h+pguid]
0x180003828  mov     qword ptr [rbp+57h+pguid.Data1], r15
0x18000382c  lea     r9, _GUID_cdaece56_4edf_43df_b113_88e4556fa1bb; riid
0x180003833  mov     [rsp+130h+ppv], rax; ppv
0x180003838  lea     rcx, _GUID_a9927f85_a304_4390_8b23_a75f1c668600; rclsid
0x18000383f  lea     r8d, [rdx+1]; dwClsContext
0x180003843  call    cs:__imp_CoCreateInstance
0x18000384a  nop     dword ptr [rax+rax+00h]
0x18000384f  mov     r15d, eax
0x180003852  test    eax, eax
0x180003854  js      short loc_18000389F
0x180003856  mov     rdx, r12; wchar_t *
0x180003859  mov     rcx, rsi; Source
0x18000385c  call    ?AddCorrelationIdParameter@@YAPEAGPEBG0@Z; AddCorrelationIdParameter(ushort const *,ushort const *)
0x180003861  mov     rcx, qword ptr [rbp+57h+pguid.Data1]
0x180003865  lea     r9, [rsp+130h+var_F8]
0x18000386a  mov     r12, rax
0x18000386d  lea     r8, [rsp+130h+var_FC]
0x180003872  test    r12, r12
0x180003875  mov     rdx, [rcx]
0x180003878  cmovnz  rsi, r12
0x18000387c  mov     rax, [rdx+18h]
0x180003880  mov     rdx, rsi
0x180003883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003888  mov     r15d, eax
0x18000388b  test    r12, r12
0x18000388e  jz      short loc_18000389F
0x180003890  mov     rcx, r12; pv
0x180003893  call    cs:__imp_CoTaskMemFree
0x18000389a  nop     dword ptr [rax+rax+00h]
0x18000389f  mov     rcx, qword ptr [rbp+57h+pguid.Data1]
0x1800038a3  test    rcx, rcx
0x1800038a6  jz      short loc_1800038B4
0x1800038a8  mov     rax, [rcx]
0x1800038ab  mov     rax, [rax+10h]
0x1800038af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b4  mov     [rsp+130h+var_100], r15d
0x1800038b9  test    r15d, r15d
0x1800038bc  js      short loc_1800038EB
0x1800038be  mov     r8d, [rsp+130h+var_FC]
0x1800038c3  xor     r15d, r15d
0x1800038c6  test    r8d, r8d
0x1800038c9  jz      short loc_1800038EB
0x1800038cb  test    r13b, r13b
0x1800038ce  jnz     loc_180003961
0x1800038d4  mov     rcx, [rdi+178h]
0x1800038db  mov     r14, rbx
0x1800038de  mov     r9, [rsp+130h+var_F8]
0x1800038e3  mov     rdx, r14
0x1800038e6  call    ??$SetCookiesAndFreeTokens@UProofOfPossessionCookieInfo@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAUProofOfPossessionCookieInfo@@@Z; ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(void *,ushort const *,ulong,ProofOfPossessionCookieInfo *)
0x1800038eb  lea     rcx, [rbp+57h+var_D0]; this
0x1800038ef  call    ??1SingleSignonTelemetryHelper@@QEAA@XZ; SingleSignonTelemetryHelper::~SingleSignonTelemetryHelper(void)
0x1800038f4  call    cs:__imp_CoUninitialize
0x1800038fb  nop     dword ptr [rax+rax+00h]
0x180003900  test    rbx, rbx
0x180003903  jz      short loc_180003914
0x180003905  mov     rcx, rbx; pv
0x180003908  call    cs:__imp_CoTaskMemFree
0x18000390f  nop     dword ptr [rax+rax+00h]
0x180003914  lea     rcx, [rsp+130h+var_E0]; this
0x180003919  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x18000391e  mov     rcx, [rbp+57h+var_50]
0x180003922  xor     rcx, rsp; StackCookie
0x180003925  call    __security_check_cookie
0x18000392a  add     rsp, 0F8h
0x180003931  pop     r15
0x180003933  pop     r14
0x180003935  pop     r13
0x180003937  pop     r12
0x180003939  pop     rdi
0x18000393a  pop     rsi
0x18000393b  pop     rbx
0x18000393c  pop     rbp
0x18000393d  retn
0x18000393f  mov     rsi, [rdi+0B8h]
0x180003946  jmp     loc_180003714
0x18000394b  mov     ecx, 1000001Ah
0x180003950  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180003957  nop     dword ptr [rax+rax+00h]
0x18000395c  jmp     loc_1800036E2
0x180003961  mov     rcx, r15
0x180003964  jmp     loc_1800038DE
0x180003969  call    ??$SingleSignOnGetCookiesMsaStarted@AEAPEBG@BrowserTelemetry@@SAXAEAPEBG@Z; BrowserTelemetry::SingleSignOnGetCookiesMsaStarted<ushort const * &>(ushort const * &)
0x18000396e  jmp     loc_18000380D
0x180003973  mov     rdx, rax; SubStr
0x180003976  mov     rcx, rsi; Str
0x180003979  call    cs:__imp_wcsstr
0x180003980  nop     dword ptr [rax+rax+00h]
0x180003985  test    rax, rax
0x180003988  jz      loc_180003725
0x18000398e  xor     ebx, ebx
0x180003990  mov     r13b, 1
0x180003993  xor     r15b, r15b
0x180003996  jmp     loc_18000377F
0x18000399b  mov     ecx, 20000004h
0x1800039a0  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800039a7  nop     dword ptr [rax+rax+00h]
0x1800039ac  test    al, al
0x1800039ae  jz      loc_18000381D
0x1800039b4  mov     ecx, 20000001h
0x1800039b9  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800039c0  nop     dword ptr [rax+rax+00h]
0x1800039c5  test    al, al
0x1800039c7  jnz     loc_18000381D
0x1800039cd  mov     ecx, 1000002Dh
0x1800039d2  mov     qword ptr [rbp+57h+pguid.Data1], r15
0x1800039d6  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1800039dd  nop     dword ptr [rax+rax+00h]
0x1800039e2  mov     [rsp+130h+var_E8], r15
0x1800039e7  lea     rcx, [rsp+130h+var_E8]
0x1800039ec  cmp     eax, 2
0x1800039ef  jnz     loc_180003AC0
0x1800039f5  mov     [rsp+130h+var_F8], r15
0x1800039fa  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180003a01  nop     dword ptr [rax+rax+00h]
0x180003a06  mov     [rsp+130h+var_100], eax
0x180003a0a  test    eax, eax
0x180003a0c  js      loc_1800038EB
0x180003a12  mov     rcx, [rsp+130h+var_E8]
0x180003a17  lea     r9, [rsp+130h+var_F0]
0x180003a1c  mov     [rsp+130h+var_F0], r15
0x180003a21  lea     r8, IID_IUnknown
0x180003a28  lea     rdx, CLSID_CEdgeManagerBroker
0x180003a2f  mov     rax, [rcx]
0x180003a32  mov     rax, [rax+30h]
0x180003a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a3b  mov     [rsp+130h+var_100], eax
0x180003a3f  test    eax, eax
0x180003a41  js      short loc_180003A74
0x180003a43  mov     rcx, [rsp+130h+var_F0]
0x180003a48  lea     r8, [rsp+130h+var_F8]
0x180003a4d  lea     rdx, _GUID_26ea2529_1012_4dd2_8a8b_3d2de75d3529
0x180003a54  mov     rax, [rcx]
0x180003a57  mov     rax, [rax]
0x180003a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5f  mov     rcx, [rsp+130h+var_F0]
0x180003a64  mov     [rsp+130h+var_100], eax
0x180003a68  mov     rax, [rcx]
0x180003a6b  mov     rax, [rax+10h]
0x180003a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a74  mov     rcx, [rsp+130h+var_E8]
0x180003a79  mov     rax, [rcx]
0x180003a7c  mov     rax, [rax+10h]
0x180003a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a85  mov     eax, [rsp+130h+var_100]
0x180003a89  test    eax, eax
0x180003a8b  js      loc_1800038EB
0x180003a91  mov     rcx, [rsp+130h+var_F8]
0x180003a96  lea     rdx, [rbp+57h+pguid]
0x180003a9a  mov     [rsp+130h+ppv], rdx
0x180003a9f  lea     r9, [rsp+130h+var_FC]
0x180003aa4  mov     r8, r12
0x180003aa7  mov     rdx, rsi
0x180003aaa  mov     rax, [rcx]
0x180003aad  mov     rax, [rax+48h]
0x180003ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab6  mov     rcx, [rsp+130h+var_F8]
0x180003abb  jmp     loc_180003B89
0x180003ac0  mov     [rsp+130h+var_F0], r15
0x180003ac5  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180003acc  nop     dword ptr [rax+rax+00h]
0x180003ad1  mov     [rsp+130h+var_100], eax
0x180003ad5  test    eax, eax
0x180003ad7  js      loc_1800038EB
0x180003add  mov     rcx, [rsp+130h+var_E8]
0x180003ae2  lea     r9, [rsp+130h+var_F8]
0x180003ae7  mov     [rsp+130h+var_F8], r15
0x180003aec  lea     r8, IID_IUnknown
0x180003af3  lea     rdx, CLSID_CShdocvwBroker
0x180003afa  mov     rax, [rcx]
0x180003afd  mov     rax, [rax+30h]
0x180003b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b06  mov     [rsp+130h+var_100], eax
0x180003b0a  test    eax, eax
0x180003b0c  js      short loc_180003B3F
0x180003b0e  mov     rcx, [rsp+130h+var_F8]
0x180003b13  lea     r8, [rsp+130h+var_F0]
0x180003b18  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180003b1f  mov     rax, [rcx]
0x180003b22  mov     rax, [rax]
0x180003b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b2a  mov     rcx, [rsp+130h+var_F8]
0x180003b2f  mov     [rsp+130h+var_100], eax
0x180003b33  mov     rax, [rcx]
0x180003b36  mov     rax, [rax+10h]
0x180003b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b3f  mov     rcx, [rsp+130h+var_E8]
0x180003b44  mov     rax, [rcx]
0x180003b47  mov     rax, [rax+10h]
0x180003b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b50  mov     eax, [rsp+130h+var_100]
0x180003b54  test    eax, eax
0x180003b56  js      loc_1800038EB
0x180003b5c  mov     rcx, [rsp+130h+var_F0]
0x180003b61  lea     rdx, [rbp+57h+pguid]
0x180003b65  mov     [rsp+130h+ppv], rdx
0x180003b6a  lea     r9, [rsp+130h+var_FC]
0x180003b6f  mov     r8, r12
0x180003b72  mov     rdx, rsi
0x180003b75  mov     rax, [rcx]
0x180003b78  mov     rax, [rax+480h]
  ... truncated ...
```
