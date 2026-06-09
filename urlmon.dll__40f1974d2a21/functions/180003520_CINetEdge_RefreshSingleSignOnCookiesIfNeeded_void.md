# CINetEdge::RefreshSingleSignOnCookiesIfNeeded(void)

- ea: `0x180003520`
- end: `0x180003a0d`
- name: `?RefreshSingleSignOnCookiesIfNeeded@CINetEdge@@AEAAXXZ`
- size: `1261`
- prototype: `void __fastcall(CINetEdge *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180094ea0`

## callees

- `0x180003520`
- `0x180003a14`
- `0x180003b8c`
- `0x180003c28`
- `0x180003e0c`
- `0x180003f6c`
- `0x1800040ec`
- `0x180004df0`
- `0x18000a110`
- `0x18000a270`
- `0x18001063c`
- `0x1800214d0`
- `0x1800d511c`
- `0x18011606c`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800037d3`
- `msvcrt!wcsstr` at `0x1800037d3`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18000383c`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003901`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18000383c`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003901`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180003572`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800037b3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800037f4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180003807`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180003572`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800037b3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800037f4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180003807`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18000381e`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18000381e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800035c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800035c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003764`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003764`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180003643`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180003643`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000370d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000370d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003772`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003656`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003656`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800036c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800036c3`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180003582`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180003582`

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
            BrowserTelemetry::SingleSignOnGetCookiesAadStarted<unsigned short const * &>((__int64)v28);
          else
            BrowserTelemetry::SingleSignOnGetCookiesMsaStarted<unsigned short const * &>((__int64)v28);
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
0x180003520  push    rbp
0x180003522  push    rbx
0x180003523  push    rsi
0x180003524  push    rdi
0x180003525  push    r12
0x180003527  push    r13
0x180003529  push    r14
0x18000352b  push    r15
0x18000352d  lea     rbp, [rsp-1Fh]
0x180003532  sub     rsp, 0F8h
0x180003539  mov     rax, cs:__security_cookie
0x180003540  xor     rax, rsp
0x180003543  mov     [rbp+57h+var_50], rax
0x180003547  mov     rdi, rcx
0x18000354a  mov     [rsp+130h+var_E0], rcx
0x18000354f  mov     [rsp+130h+var_D8], 0
0x180003554  lock inc dword ptr [rcx+4B0h]
0x18000355b  lea     rcx, [rsp+130h+var_E0]; this
0x180003560  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x180003565  test    al, al
0x180003567  jz      loc_180003778
0x18000356d  mov     ecx, 10000019h
0x180003572  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180003578  test    al, al
0x18000357a  jz      loc_1800037AE
0x180003580  xor     ecx, ecx; pvReserved
0x180003582  call    cs:__imp_CoInitialize
0x180003588  mov     [rsp+130h+var_100], eax
0x18000358c  test    eax, eax
0x18000358e  js      loc_180003778
0x180003594  mov     rsi, [rdi+158h]
0x18000359b  mov     [rsp+130h+var_FC], 0
0x1800035a3  test    rsi, rsi
0x1800035a6  jz      loc_1800037A2
0x1800035ac  call    ?GetSingleSignOnLoginUrl@CINetEdge@@IEAAPEBGXZ; CINetEdge::GetSingleSignOnLoginUrl(void)
0x1800035b1  mov     r14, rax
0x1800035b4  test    rax, rax
0x1800035b7  jnz     loc_1800037CD
0x1800035bd  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x1800035c4  call    cs:__imp_EnterCriticalSection
0x1800035ca  call    ?GetAadSingleSignOnLoginUrls@CINetEdge@@AEAAPEBGXZ; CINetEdge::GetAadSingleSignOnLoginUrls(void)
0x1800035cf  mov     rdx, rax; unsigned __int16 *
0x1800035d2  mov     rcx, rsi; this
0x1800035d5  call    ?GetAadLoginUrlMatch@ProofOfPossessionTokenProvider@@YAPEAGPEBG0@Z; ProofOfPossessionTokenProvider::GetAadLoginUrlMatch(ushort const *,ushort const *)
0x1800035da  test    rax, rax
0x1800035dd  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x1800035e4  mov     rbx, rax
0x1800035e7  setnz   r15b
0x1800035eb  call    cs:__imp_LeaveCriticalSection
0x1800035f1  test    rbx, rbx
0x1800035f4  jz      loc_180003764
0x1800035fa  xor     r13b, r13b
0x1800035fd  cmp     qword ptr [rdi+178h], 0
0x180003605  jz      loc_180003764
0x18000360b  xor     r12d, r12d
0x18000360e  mov     [rbp+57h+var_B8], r15b
0x180003612  lea     rax, [rsp+130h+var_FC]
0x180003617  mov     [rbp+57h+var_D0], r12
0x18000361b  mov     [rbp+57h+var_C8], rax
0x18000361f  lea     rcx, [rbp+57h+sz]; void *
0x180003623  lea     rax, [rsp+130h+var_100]
0x180003628  xor     edx, edx; Val
0x18000362a  lea     r8d, [r12+4Eh]; Size
0x18000362f  mov     [rbp+57h+var_C0], rax
0x180003633  call    memset_0
0x180003638  xorps   xmm0, xmm0
0x18000363b  lea     rcx, [rbp+57h+pguid]; pguid
0x18000363f  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180003643  call    cs:__imp_CoCreateGuid
0x180003649  lea     r8d, [r12+27h]; cchMax
0x18000364e  lea     rdx, [rbp+57h+sz]; lpsz
0x180003652  lea     rcx, [rbp+57h+pguid]; rguid
0x180003656  call    cs:__imp_StringFromGUID2
0x18000365c  test    eax, eax
0x18000365e  jle     short loc_18000368D
0x180003660  xor     eax, eax
0x180003662  lea     rcx, [rbp+57h+var_9E]; unsigned __int16 *
0x180003666  mov     [rbp+57h+var_56], ax
0x18000366a  call    ?OLESTRDuplicate@@YAPEAGPEBG@Z; OLESTRDuplicate(ushort const *)
0x18000366f  mov     [rbp+57h+var_D0], rax
0x180003673  mov     r12, rax
0x180003676  test    rax, rax
0x180003679  jz      short loc_18000368D
0x18000367b  lea     rcx, [rbp+57h+var_D0]
0x18000367f  test    r15b, r15b
0x180003682  jz      loc_1800037C3
0x180003688  call    ??$SingleSignOnGetCookiesAadStarted@AEAPEBG@BrowserTelemetry@@SAXAEAPEBG@Z; BrowserTelemetry::SingleSignOnGetCookiesAadStarted<ushort const * &>(ushort const * &)
0x18000368d  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x180003692  xor     r15d, r15d
0x180003695  test    eax, eax
0x180003697  jnz     loc_1800037EF
0x18000369d  xor     edx, edx; pUnkOuter
0x18000369f  mov     [rsp+130h+var_F8], r15
0x1800036a4  lea     rax, [rbp+57h+pguid]
0x1800036a8  mov     qword ptr [rbp+57h+pguid.Data1], r15
0x1800036ac  lea     r9, _GUID_cdaece56_4edf_43df_b113_88e4556fa1bb; riid
0x1800036b3  mov     [rsp+130h+ppv], rax; ppv
0x1800036b8  lea     rcx, _GUID_a9927f85_a304_4390_8b23_a75f1c668600; rclsid
0x1800036bf  lea     r8d, [rdx+1]; dwClsContext
0x1800036c3  call    cs:__imp_CoCreateInstance
0x1800036c9  mov     r15d, eax
0x1800036cc  test    eax, eax
0x1800036ce  js      short loc_180003713
0x1800036d0  mov     rdx, r12; wchar_t *
0x1800036d3  mov     rcx, rsi; Source
0x1800036d6  call    ?AddCorrelationIdParameter@@YAPEAGPEBG0@Z; AddCorrelationIdParameter(ushort const *,ushort const *)
0x1800036db  mov     rcx, qword ptr [rbp+57h+pguid.Data1]
0x1800036df  lea     r9, [rsp+130h+var_F8]
0x1800036e4  mov     r12, rax
0x1800036e7  lea     r8, [rsp+130h+var_FC]
0x1800036ec  test    r12, r12
0x1800036ef  mov     rdx, [rcx]
0x1800036f2  cmovnz  rsi, r12
0x1800036f6  mov     rax, [rdx+18h]
0x1800036fa  mov     rdx, rsi
0x1800036fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003702  mov     r15d, eax
0x180003705  test    r12, r12
0x180003708  jz      short loc_180003713
0x18000370a  mov     rcx, r12; pv
0x18000370d  call    cs:__imp_CoTaskMemFree
0x180003713  mov     rcx, qword ptr [rbp+57h+pguid.Data1]
0x180003717  test    rcx, rcx
0x18000371a  jz      short loc_180003728
0x18000371c  mov     rax, [rcx]
0x18000371f  mov     rax, [rax+10h]
0x180003723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003728  mov     [rsp+130h+var_100], r15d
0x18000372d  test    r15d, r15d
0x180003730  js      short loc_18000375B
0x180003732  mov     r8d, [rsp+130h+var_FC]
0x180003737  xor     r15d, r15d
0x18000373a  test    r8d, r8d
0x18000373d  jz      short loc_18000375B
0x18000373f  test    r13b, r13b
0x180003742  jnz     short loc_1800037BE
0x180003744  mov     rcx, [rdi+178h]
0x18000374b  mov     r14, rbx
0x18000374e  mov     r9, [rsp+130h+var_F8]
0x180003753  mov     rdx, r14
0x180003756  call    ??$SetCookiesAndFreeTokens@UProofOfPossessionCookieInfo@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAUProofOfPossessionCookieInfo@@@Z; ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(void *,ushort const *,ulong,ProofOfPossessionCookieInfo *)
0x18000375b  lea     rcx, [rbp+57h+var_D0]; this
0x18000375f  call    ??1SingleSignonTelemetryHelper@@QEAA@XZ; SingleSignonTelemetryHelper::~SingleSignonTelemetryHelper(void)
0x180003764  call    cs:__imp_CoUninitialize
0x18000376a  test    rbx, rbx
0x18000376d  jz      short loc_180003778
0x18000376f  mov     rcx, rbx; pv
0x180003772  call    cs:__imp_CoTaskMemFree
0x180003778  lea     rcx, [rsp+130h+var_E0]; this
0x18000377d  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x180003782  mov     rcx, [rbp+57h+var_50]
0x180003786  xor     rcx, rsp; StackCookie
0x180003789  call    __security_check_cookie
0x18000378e  add     rsp, 0F8h
0x180003795  pop     r15
0x180003797  pop     r14
0x180003799  pop     r13
0x18000379b  pop     r12
0x18000379d  pop     rdi
0x18000379e  pop     rsi
0x18000379f  pop     rbx
0x1800037a0  pop     rbp
0x1800037a1  retn
0x1800037a2  mov     rsi, [rdi+0B8h]
0x1800037a9  jmp     loc_1800035AC
0x1800037ae  mov     ecx, 1000001Ah
0x1800037b3  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800037b9  jmp     loc_180003580
0x1800037be  mov     rcx, r15
0x1800037c1  jmp     short loc_18000374E
0x1800037c3  call    ??$SingleSignOnGetCookiesMsaStarted@AEAPEBG@BrowserTelemetry@@SAXAEAPEBG@Z; BrowserTelemetry::SingleSignOnGetCookiesMsaStarted<ushort const * &>(ushort const * &)
0x1800037c8  jmp     loc_18000368D
0x1800037cd  mov     rdx, rax; SubStr
0x1800037d0  mov     rcx, rsi; Str
0x1800037d3  call    cs:__imp_wcsstr
0x1800037d9  test    rax, rax
0x1800037dc  jz      loc_1800035BD
0x1800037e2  xor     ebx, ebx
0x1800037e4  mov     r13b, 1
0x1800037e7  xor     r15b, r15b
0x1800037ea  jmp     loc_18000360B
0x1800037ef  mov     ecx, 20000004h
0x1800037f4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800037fa  test    al, al
0x1800037fc  jz      loc_18000369D
0x180003802  mov     ecx, 20000001h
0x180003807  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18000380d  test    al, al
0x18000380f  jnz     loc_18000369D
0x180003815  mov     ecx, 1000002Dh
0x18000381a  mov     qword ptr [rbp+57h+pguid.Data1], r15
0x18000381e  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180003824  mov     [rsp+130h+var_E8], r15
0x180003829  lea     rcx, [rsp+130h+var_E8]
0x18000382e  cmp     eax, 2
0x180003831  jnz     loc_1800038FC
0x180003837  mov     [rsp+130h+var_F8], r15
0x18000383c  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180003842  mov     [rsp+130h+var_100], eax
0x180003846  test    eax, eax
0x180003848  js      loc_18000375B
0x18000384e  mov     rcx, [rsp+130h+var_E8]
0x180003853  lea     r9, [rsp+130h+var_F0]
0x180003858  mov     [rsp+130h+var_F0], r15
0x18000385d  lea     r8, IID_IUnknown
0x180003864  lea     rdx, CLSID_CEdgeManagerBroker
0x18000386b  mov     rax, [rcx]
0x18000386e  mov     rax, [rax+30h]
0x180003872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003877  mov     [rsp+130h+var_100], eax
0x18000387b  test    eax, eax
0x18000387d  js      short loc_1800038B0
0x18000387f  mov     rcx, [rsp+130h+var_F0]
0x180003884  lea     r8, [rsp+130h+var_F8]
0x180003889  lea     rdx, _GUID_26ea2529_1012_4dd2_8a8b_3d2de75d3529
0x180003890  mov     rax, [rcx]
0x180003893  mov     rax, [rax]
0x180003896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000389b  mov     rcx, [rsp+130h+var_F0]
0x1800038a0  mov     [rsp+130h+var_100], eax
0x1800038a4  mov     rax, [rcx]
0x1800038a7  mov     rax, [rax+10h]
0x1800038ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b0  mov     rcx, [rsp+130h+var_E8]
0x1800038b5  mov     rax, [rcx]
0x1800038b8  mov     rax, [rax+10h]
0x1800038bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c1  mov     eax, [rsp+130h+var_100]
0x1800038c5  test    eax, eax
0x1800038c7  js      loc_18000375B
0x1800038cd  mov     rcx, [rsp+130h+var_F8]
0x1800038d2  lea     rdx, [rbp+57h+pguid]
0x1800038d6  mov     [rsp+130h+ppv], rdx
0x1800038db  lea     r9, [rsp+130h+var_FC]
0x1800038e0  mov     r8, r12
0x1800038e3  mov     rdx, rsi
0x1800038e6  mov     rax, [rcx]
0x1800038e9  mov     rax, [rax+48h]
0x1800038ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f2  mov     rcx, [rsp+130h+var_F8]
0x1800038f7  jmp     loc_1800039BF
0x1800038fc  mov     [rsp+130h+var_F0], r15
0x180003901  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180003907  mov     [rsp+130h+var_100], eax
0x18000390b  test    eax, eax
0x18000390d  js      loc_18000375B
0x180003913  mov     rcx, [rsp+130h+var_E8]
0x180003918  lea     r9, [rsp+130h+var_F8]
0x18000391d  mov     [rsp+130h+var_F8], r15
0x180003922  lea     r8, IID_IUnknown
0x180003929  lea     rdx, CLSID_CShdocvwBroker
0x180003930  mov     rax, [rcx]
0x180003933  mov     rax, [rax+30h]
0x180003937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000393c  mov     [rsp+130h+var_100], eax
0x180003940  test    eax, eax
0x180003942  js      short loc_180003975
0x180003944  mov     rcx, [rsp+130h+var_F8]
0x180003949  lea     r8, [rsp+130h+var_F0]
0x18000394e  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180003955  mov     rax, [rcx]
0x180003958  mov     rax, [rax]
0x18000395b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003960  mov     rcx, [rsp+130h+var_F8]
0x180003965  mov     [rsp+130h+var_100], eax
0x180003969  mov     rax, [rcx]
0x18000396c  mov     rax, [rax+10h]
0x180003970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003975  mov     rcx, [rsp+130h+var_E8]
0x18000397a  mov     rax, [rcx]
0x18000397d  mov     rax, [rax+10h]
0x180003981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003986  mov     eax, [rsp+130h+var_100]
0x18000398a  test    eax, eax
0x18000398c  js      loc_18000375B
0x180003992  mov     rcx, [rsp+130h+var_F0]
0x180003997  lea     rdx, [rbp+57h+pguid]
0x18000399b  mov     [rsp+130h+ppv], rdx
0x1800039a0  lea     r9, [rsp+130h+var_FC]
0x1800039a5  mov     r8, r12
0x1800039a8  mov     rdx, rsi
0x1800039ab  mov     rax, [rcx]
0x1800039ae  mov     rax, [rax+480h]
0x1800039b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ba  mov     rcx, [rsp+130h+var_F0]
0x1800039bf  mov     [rsp+130h+var_100], eax
0x1800039c3  mov     rax, [rcx]
0x1800039c6  mov     rax, [rax+10h]
0x1800039ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039cf  cmp     [rsp+130h+var_100], r15d
0x1800039d4  jl      loc_18000375B
0x1800039da  mov     r8d, [rsp+130h+var_FC]
0x1800039df  test    r8d, r8d
0x1800039e2  jz      loc_18000375B
0x1800039e8  test    r13b, r13b
0x1800039eb  jz      short loc_1800039F2
0x1800039ed  mov     rcx, r15
0x1800039f0  jmp     short loc_1800039FC
0x1800039f2  mov     rcx, [rdi+178h]
0x1800039f9  mov     r14, rbx
  ... truncated ...
```
