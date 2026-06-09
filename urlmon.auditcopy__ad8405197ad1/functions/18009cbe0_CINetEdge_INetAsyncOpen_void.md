# CINetEdge::INetAsyncOpen(void)

- ea: `0x18009cbe0`
- end: `0x18009d042`
- name: `?INetAsyncOpen@CINetEdge@@MEAAJXZ`
- size: `1122`
- prototype: `__int64 __fastcall(CINetEdge *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008610`
- `0x180008b2c`
- `0x18000b2e0`
- `0x18000b490`
- `0x18000e494`
- `0x18000e7f0`
- `0x180012350`
- `0x180018bfc`
- `0x18001a6e0`
- `0x18004e8e4`
- `0x18006894c`
- `0x180075c38`
- `0x180075d88`
- `0x1800786e8`
- `0x180080ba4`
- `0x180081228`
- `0x180082e9c`
- `0x1800898bc`
- `0x18008d050`
- `0x180098850`
- `0x18009cbe0`
- `0x1800fd4e0`
- `0x180117994`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18009ce01`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18009ce01`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18009cdf1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18009cdf1`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18009cddc`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18009cddc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cfcf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cfcf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009cc9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009cc9b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18009ccf4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18009ccf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cd3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cd3f`
- `WININET!InternetSetStatusCallbackA` at `0x18009ce34`
- `WININET!InternetSetStatusCallbackA` at `0x18009ce34`
- `WININET!InternetSetOptionA` at `0x18009cda9`
- `WININET!InternetSetOptionA` at `0x18009cdcb`
- `WININET!InternetSetOptionA` at `0x18009ce1e`
- `WININET!InternetSetOptionA` at `0x18009ce4d`
- `WININET!InternetSetOptionA` at `0x18009ce6d`
- `WININET!InternetSetOptionA` at `0x18009ce9c`
- `WININET!InternetSetOptionA` at `0x18009cebe`
- `WININET!InternetSetOptionA` at `0x18009cee0`
- `WININET!InternetSetOptionA` at `0x18009cf0e`
- `WININET!InternetSetOptionA` at `0x18009cf4f`
- `WININET!InternetSetOptionA` at `0x18009cf78`
- `WININET!InternetSetOptionA` at `0x18009cfa3`
- `WININET!InternetSetOptionA` at `0x18009cda9`
- `WININET!InternetSetOptionA` at `0x18009cdcb`
- `WININET!InternetSetOptionA` at `0x18009ce1e`
- `WININET!InternetSetOptionA` at `0x18009ce4d`
- `WININET!InternetSetOptionA` at `0x18009ce6d`
- `WININET!InternetSetOptionA` at `0x18009ce9c`
- `WININET!InternetSetOptionA` at `0x18009cebe`
- `WININET!InternetSetOptionA` at `0x18009cee0`
- `WININET!InternetSetOptionA` at `0x18009cf0e`
- `WININET!InternetSetOptionA` at `0x18009cf4f`
- `WININET!InternetSetOptionA` at `0x18009cf78`
- `WININET!InternetSetOptionA` at `0x18009cfa3`
- `WININET!InternetOpenW` at `0x18009cd2b`
- `WININET!InternetOpenW` at `0x18009cd2b`

## pseudocode

```c
__int64 __fastcall CINetEdge::INetAsyncOpen(CINetEdge *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // r15d
  int v6; // edi
  struct IInternetBindInfo *RefCountedBindInfo; // rax
  CINetEdge *v8; // rcx
  const WCHAR *UserAgentString; // rsi
  void *v10; // rsi
  DWORD LastError; // eax
  int v12; // eax
  CINetEdge *v13; // rcx
  unsigned int v14; // eax
  CINetEdge *v16; // [rsp+30h] [rbp-18h] BYREF
  char v17; // [rsp+38h] [rbp-10h]
  CINetEdge *Buffer; // [rsp+80h] [rbp+38h] BYREF
  int v19; // [rsp+88h] [rbp+40h] BYREF
  BOOL v20; // [rsp+90h] [rbp+48h] BYREF
  struct IInternetBindInfo *v21; // [rsp+98h] [rbp+50h] BYREF

  if ( (unsigned int)dword_180166000 > 5 && tlgKeywordOn((__int64)&dword_180166000, 32) )
  {
    Buffer = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v2,
      (unsigned __int8 *)&word_18015230E,
      v3,
      v4,
      (__int64)&Buffer);
  }
  v5 = -2147467259;
  v16 = this;
  v17 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 300);
  if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v16) )
  {
    v6 = 2;
    goto LABEL_46;
  }
  v6 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 1);
  if ( v6 != 1 )
  {
LABEL_46:
    v14 = CINetEdge::CheckTransitionStatusAndDispatchAbort((unsigned int *)this, v6, v5);
    goto LABEL_47;
  }
  if ( !g_hSession )
  {
    v21 = 0;
    RefCountedBindInfo = CINetEdge::GetRefCountedBindInfo(this);
    Microsoft::WRL::ComPtr<IServiceProvider>::Attach((__int64 *)&v21, (__int64)RefCountedBindInfo);
    EnterCriticalSection(&g_mxsSession);
    v8 = this;
    if ( !g_hSession )
    {
      CINetEdge::SetINetState((__int64)this, 2);
      UserAgentString = CINetEdge::GetUserAgentString(this, v21);
      if ( !UserAgentString )
        UserAgentString = GetCommonDefaultUserAgentW();
      InitOnceExecuteOnce(&stru_18016BB00, (PINIT_ONCE_FN)InitOnceDeviceFamily, 0, 0);
      if ( !byte_18016AF34 )
        CINetEdge::s_SetTransportTimeoutsAndMaxConnections();
      CINetEdge::CheckAndSetINetEdgeState((__int64)this, 2);
      v10 = InternetOpenW(UserAgentString, 0, 0, 0, 0x10000000u);
      if ( !v10 )
      {
        LastError = GetLastError();
        v5 = -2146697213;
        *((_DWORD *)this + 31) = -2146697213;
        CINetEdge::SetBindResult(this, LastError, -2146697213);
        v12 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 4);
LABEL_40:
        v6 = v12;
        LeaveCriticalSection(&g_mxsSession);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v21);
        goto LABEL_42;
      }
      LODWORD(Buffer) = 0x2000;
      g_fDoNotTrack = IsDoNotTrackEnabled();
      if ( g_fDoNotTrack )
        g_fDoNotTrackAllowExceptions = AreDoNotTrackExceptionsAllowed();
      InternetSetOptionA(0, 0x7Bu, &g_fDoNotTrack, 4u);
      if ( IsSpartanApp() )
        InternetSetOptionA(0, 0xAFu, 0, 0);
      if ( ((unsigned int)IEConfiguration_GetDWORD(268435501) != 2 || (unsigned __int8)IEConfiguration_GetBool(536870914))
        && LCIEIsCurrentProcessInPrivate() )
      {
        InternetSetOptionA(0, 0xA4u, 0, 0);
      }
      InternetSetStatusCallbackA(v10, (INTERNET_STATUS_CALLBACK)CINetEdge::CINetCallback);
      InternetSetOptionA(v10, 0x6Cu, 0, 0);
      InternetSetOptionA(v10, 0x2Du, (LPVOID)&g_dwMagicContext, 8u);
      if ( (int)CFeatureControlKey::_CoInternetFeatureValueInternal(
                  (CFeatureControlKey *)&FCK::FEATURE_URLMON_IQDA_SIZE,
                  (unsigned int *)&Buffer) >= 0 )
        InternetSetOptionA(v10, 0x8Cu, &Buffer, 4u);
      if ( CINetEdge::s_IsInsecureSSL3FallbackDisabled() )
        InternetSetOptionA(0, 0xA0u, 0, 0);
      if ( IsBlockWeakCryptoEnabled() )
        InternetSetOptionA(0, 0xB0u, 0, 0);
      if ( CINetEdge::IsHTTP2EnabledForProcess(v13) )
      {
        CINetEdge::s_fEnableHTTP2 = 1;
        v19 = 2;
        InternetSetOptionA(v10, 0x94u, &v19, 4u);
      }
      if ( (unsigned int)IsABrowserApp() || g_enableHSTSForAppsInEdgeMode )
      {
        g_fHSTSEnabled = 1;
        InternetSetOptionA(v10, 0x9Du, &g_fHSTSEnabled, 4u);
      }
      else
      {
        g_fHSTSEnabled = 0;
      }
      v20 = g_experimentalNetworkFeatures;
      if ( g_experimentalNetworkFeatures )
        InternetSetOptionA(v10, 0xB4u, &v20, 4u);
      if ( g_enableEdgeCookies )
      {
        v19 = 1;
        InternetSetOptionA(v10, 0xA6u, &v19, 4u);
      }
      g_hSession = v10;
      v8 = this;
    }
    v12 = CINetEdge::CheckAndSetINetEdgeState((__int64)v8, 3);
    LOBYTE(v10) = 1;
    goto LABEL_40;
  }
  v6 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 3);
  LOBYTE(v10) = 1;
LABEL_42:
  if ( v6 != 1 )
    goto LABEL_46;
  if ( (_BYTE)v10 )
  {
    v14 = (*(__int64 (__fastcall **)(CINetEdge *))(*(_QWORD *)this + 232LL))(this);
LABEL_47:
    v5 = v14;
  }
  CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v16);
  return v5;
}

```

## disassembly

```asm
0x18009cbe0  push    rbp
0x18009cbe2  push    rbx
0x18009cbe3  push    rsi
0x18009cbe4  push    rdi
0x18009cbe5  push    r14
0x18009cbe7  push    r15
0x18009cbe9  mov     rbp, rsp
0x18009cbec  sub     rsp, 48h
0x18009cbf0  mov     eax, cs:dword_180166000
0x18009cbf6  mov     rbx, rcx
0x18009cbf9  cmp     eax, 5
0x18009cbfc  jbe     short loc_18009CC2C
0x18009cbfe  mov     edx, 20h ; ' '
0x18009cc03  lea     rcx, dword_180166000
0x18009cc0a  call    _tlgKeywordOn
0x18009cc0f  test    al, al
0x18009cc11  jz      short loc_18009CC2C
0x18009cc13  lea     rax, [rbp+Buffer]
0x18009cc17  mov     [rbp+Buffer], rbx
0x18009cc1b  lea     rdx, word_18015230E
0x18009cc22  mov     qword ptr [rsp+48h+dwFlags], rax
0x18009cc27  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18009cc2c  mov     r15d, 80004005h
0x18009cc32  mov     [rbp+var_18], rbx
0x18009cc36  mov     [rbp+var_10], 0
0x18009cc3a  lock inc dword ptr [rbx+4B0h]
0x18009cc41  lea     rcx, [rbp+var_18]; this
0x18009cc45  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x18009cc4a  test    al, al
0x18009cc4c  jz      loc_18009D013
0x18009cc52  mov     edx, 1
0x18009cc57  mov     rcx, rbx
0x18009cc5a  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009cc5f  mov     edi, eax
0x18009cc61  cmp     eax, 1
0x18009cc64  jnz     loc_18009D018
0x18009cc6a  cmp     cs:?g_hSession@@3PEAXEA, 0; void * g_hSession
0x18009cc72  mov     rcx, rbx; this
0x18009cc75  jnz     loc_18009CFE6
0x18009cc7b  mov     [rbp+arg_18], 0
0x18009cc83  call    ?GetRefCountedBindInfo@CINetEdge@@IEAAPEAUIInternetBindInfo@@_N@Z; CINetEdge::GetRefCountedBindInfo(bool)
0x18009cc88  mov     rdx, rax
0x18009cc8b  lea     rcx, [rbp+arg_18]
0x18009cc8f  call    ?Attach@?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@QEAAXPEAUIServiceProvider@@@Z; Microsoft::WRL::ComPtr<IServiceProvider>::Attach(IServiceProvider *)
0x18009cc94  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x18009cc9b  call    cs:__imp_EnterCriticalSection
0x18009cca2  nop     dword ptr [rax+rax+00h]
0x18009cca7  cmp     cs:?g_hSession@@3PEAXEA, 0; void * g_hSession
0x18009ccaf  mov     rcx, rbx
0x18009ccb2  jnz     loc_18009CFB9
0x18009ccb8  mov     edi, 2
0x18009ccbd  mov     edx, edi
0x18009ccbf  call    ?SetINetState@CINetEdge@@IEAA?AW4INetState@@W42@@Z; CINetEdge::SetINetState(INetState)
0x18009ccc4  mov     rdx, [rbp+arg_18]; struct IInternetBindInfo *
0x18009ccc8  mov     rcx, rbx; this
0x18009cccb  call    ?GetUserAgentString@CINetEdge@@IEAAPEAGPEAUIInternetBindInfo@@@Z; CINetEdge::GetUserAgentString(IInternetBindInfo *)
0x18009ccd0  mov     rsi, rax
0x18009ccd3  test    rax, rax
0x18009ccd6  jnz     short loc_18009CCE0
0x18009ccd8  call    ?GetCommonDefaultUserAgentW@@YAPEBGXZ; GetCommonDefaultUserAgentW(void)
0x18009ccdd  mov     rsi, rax
0x18009cce0  xor     r9d, r9d; Context
0x18009cce3  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18009ccea  xor     r8d, r8d; Parameter
0x18009cced  lea     rcx, stru_18016BB00; InitOnce
0x18009ccf4  call    cs:__imp_InitOnceExecuteOnce
0x18009ccfb  nop     dword ptr [rax+rax+00h]
0x18009cd00  cmp     cs:byte_18016AF34, 0
0x18009cd07  jnz     short loc_18009CD0E
0x18009cd09  call    ?s_SetTransportTimeoutsAndMaxConnections@CINetEdge@@SAXXZ; CINetEdge::s_SetTransportTimeoutsAndMaxConnections(void)
0x18009cd0e  mov     edx, edi
0x18009cd10  mov     rcx, rbx
0x18009cd13  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009cd18  xor     r9d, r9d; lpszProxyBypass
0x18009cd1b  mov     [rsp+48h+dwFlags], 10000000h; dwFlags
0x18009cd23  xor     r8d, r8d; lpszProxy
0x18009cd26  xor     edx, edx; dwAccessType
0x18009cd28  mov     rcx, rsi; lpszAgent
0x18009cd2b  call    cs:__imp_InternetOpenW
0x18009cd32  nop     dword ptr [rax+rax+00h]
0x18009cd37  mov     rsi, rax
0x18009cd3a  test    rax, rax
0x18009cd3d  jnz     short loc_18009CD72
0x18009cd3f  call    cs:__imp_GetLastError
0x18009cd46  nop     dword ptr [rax+rax+00h]
0x18009cd4b  mov     r15d, 800C0003h
0x18009cd51  mov     rcx, rbx; this
0x18009cd54  mov     r8d, r15d; int
0x18009cd57  mov     [rbx+7Ch], r15d
0x18009cd5b  mov     edx, eax; unsigned int
0x18009cd5d  call    ?SetBindResult@CINetEdge@@MEAAJKJ@Z; CINetEdge::SetBindResult(ulong,long)
0x18009cd62  lea     edx, [rsi+4]
0x18009cd65  mov     rcx, rbx
0x18009cd68  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009cd6d  jmp     loc_18009CFC6
0x18009cd72  mov     dword ptr [rbp+Buffer], 2000h
0x18009cd79  call    ?IsDoNotTrackEnabled@@YAHXZ; IsDoNotTrackEnabled(void)
0x18009cd7e  mov     cs:?g_fDoNotTrack@@3HA, eax; int g_fDoNotTrack
0x18009cd84  test    eax, eax
0x18009cd86  jz      short loc_18009CD93
0x18009cd88  call    ?AreDoNotTrackExceptionsAllowed@@YAHXZ; AreDoNotTrackExceptionsAllowed(void)
0x18009cd8d  mov     cs:?g_fDoNotTrackAllowExceptions@@3HA, eax; int g_fDoNotTrackAllowExceptions
0x18009cd93  mov     r14d, 4
0x18009cd99  lea     r8, ?g_fDoNotTrack@@3HA; lpBuffer
0x18009cda0  mov     r9d, r14d; dwBufferLength
0x18009cda3  xor     ecx, ecx; hInternet
0x18009cda5  lea     edx, [r14+77h]; dwOption
0x18009cda9  call    cs:__imp_InternetSetOptionA
0x18009cdb0  nop     dword ptr [rax+rax+00h]
0x18009cdb5  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x18009cdba  test    eax, eax
0x18009cdbc  jz      short loc_18009CDD7
0x18009cdbe  xor     r9d, r9d; dwBufferLength
0x18009cdc1  xor     r8d, r8d; lpBuffer
0x18009cdc4  mov     edx, 0AFh; dwOption
0x18009cdc9  xor     ecx, ecx; hInternet
0x18009cdcb  call    cs:__imp_InternetSetOptionA
0x18009cdd2  nop     dword ptr [rax+rax+00h]
0x18009cdd7  mov     ecx, 1000002Dh
0x18009cddc  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18009cde3  nop     dword ptr [rax+rax+00h]
0x18009cde8  cmp     eax, edi
0x18009cdea  jnz     short loc_18009CE01
0x18009cdec  mov     ecx, 20000002h
0x18009cdf1  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18009cdf8  nop     dword ptr [rax+rax+00h]
0x18009cdfd  test    al, al
0x18009cdff  jz      short loc_18009CE2A
0x18009ce01  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x18009ce08  nop     dword ptr [rax+rax+00h]
0x18009ce0d  test    al, al
0x18009ce0f  jz      short loc_18009CE2A
0x18009ce11  xor     r9d, r9d; dwBufferLength
0x18009ce14  xor     r8d, r8d; lpBuffer
0x18009ce17  mov     edx, 0A4h; dwOption
0x18009ce1c  xor     ecx, ecx; hInternet
0x18009ce1e  call    cs:__imp_InternetSetOptionA
0x18009ce25  nop     dword ptr [rax+rax+00h]
0x18009ce2a  lea     rdx, ?CINetCallback@CINetEdge@@KAXPEAX_KK0K@Z; lpfnInternetCallback
0x18009ce31  mov     rcx, rsi; hInternet
0x18009ce34  call    cs:__imp_InternetSetStatusCallbackA
0x18009ce3b  nop     dword ptr [rax+rax+00h]
0x18009ce40  xor     r9d, r9d; dwBufferLength
0x18009ce43  xor     r8d, r8d; lpBuffer
0x18009ce46  mov     rcx, rsi; hInternet
0x18009ce49  lea     edx, [r9+6Ch]; dwOption
0x18009ce4d  call    cs:__imp_InternetSetOptionA
0x18009ce54  nop     dword ptr [rax+rax+00h]
0x18009ce59  mov     r9d, 8; dwBufferLength
0x18009ce5f  lea     r8, ?g_dwMagicContext@@3_KB; lpBuffer
0x18009ce66  mov     rcx, rsi; hInternet
0x18009ce69  lea     edx, [r9+25h]; dwOption
0x18009ce6d  call    cs:__imp_InternetSetOptionA
0x18009ce74  nop     dword ptr [rax+rax+00h]
0x18009ce79  lea     rdx, [rbp+Buffer]; unsigned int *
0x18009ce7d  lea     rcx, ?FEATURE_URLMON_IQDA_SIZE@FCK@@3VCFeatureControlKey@@A; this
0x18009ce84  call    ?_CoInternetFeatureValueInternal@CFeatureControlKey@@QEAAJPEAK@Z; CFeatureControlKey::_CoInternetFeatureValueInternal(ulong *)
0x18009ce89  test    eax, eax
0x18009ce8b  js      short loc_18009CEA8
0x18009ce8d  mov     r9d, r14d; dwBufferLength
0x18009ce90  lea     r8, [rbp+Buffer]; lpBuffer
0x18009ce94  mov     edx, 8Ch; dwOption
0x18009ce99  mov     rcx, rsi; hInternet
0x18009ce9c  call    cs:__imp_InternetSetOptionA
0x18009cea3  nop     dword ptr [rax+rax+00h]
0x18009cea8  call    ?s_IsInsecureSSL3FallbackDisabled@CINetEdge@@KA_NXZ; CINetEdge::s_IsInsecureSSL3FallbackDisabled(void)
0x18009cead  test    al, al
0x18009ceaf  jz      short loc_18009CECA
0x18009ceb1  xor     r9d, r9d; dwBufferLength
0x18009ceb4  xor     r8d, r8d; lpBuffer
0x18009ceb7  mov     edx, 0A0h; dwOption
0x18009cebc  xor     ecx, ecx; hInternet
0x18009cebe  call    cs:__imp_InternetSetOptionA
0x18009cec5  nop     dword ptr [rax+rax+00h]
0x18009ceca  call    ?IsBlockWeakCryptoEnabled@@YA_NXZ; IsBlockWeakCryptoEnabled(void)
0x18009cecf  test    al, al
0x18009ced1  jz      short loc_18009CEEC
0x18009ced3  xor     r9d, r9d; dwBufferLength
0x18009ced6  xor     r8d, r8d; lpBuffer
0x18009ced9  mov     edx, 0B0h; dwOption
0x18009cede  xor     ecx, ecx; hInternet
0x18009cee0  call    cs:__imp_InternetSetOptionA
0x18009cee7  nop     dword ptr [rax+rax+00h]
0x18009ceec  call    ?IsHTTP2EnabledForProcess@CINetEdge@@IEAA_NXZ; CINetEdge::IsHTTP2EnabledForProcess(void)
0x18009cef1  test    al, al
0x18009cef3  jz      short loc_18009CF1A
0x18009cef5  mov     r9d, r14d; dwBufferLength
0x18009cef8  mov     cs:?s_fEnableHTTP2@CINetEdge@@1_NA, 1; bool CINetEdge::s_fEnableHTTP2
0x18009ceff  lea     r8, [rbp+arg_8]; lpBuffer
0x18009cf03  mov     [rbp+arg_8], edi
0x18009cf06  mov     edx, 94h; dwOption
0x18009cf0b  mov     rcx, rsi; hInternet
0x18009cf0e  call    cs:__imp_InternetSetOptionA
0x18009cf15  nop     dword ptr [rax+rax+00h]
0x18009cf1a  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x18009cf1f  test    eax, eax
0x18009cf21  jnz     short loc_18009CF33
0x18009cf23  cmp     cs:?g_enableHSTSForAppsInEdgeMode@@3_NA, al; bool g_enableHSTSForAppsInEdgeMode
0x18009cf29  jnz     short loc_18009CF33
0x18009cf2b  mov     cs:?g_fHSTSEnabled@@3HA, eax; int g_fHSTSEnabled
0x18009cf31  jmp     short loc_18009CF5B
0x18009cf33  mov     r9d, r14d; dwBufferLength
0x18009cf36  mov     cs:?g_fHSTSEnabled@@3HA, 1; int g_fHSTSEnabled
0x18009cf40  lea     r8, ?g_fHSTSEnabled@@3HA; lpBuffer
0x18009cf47  mov     edx, 9Dh; dwOption
0x18009cf4c  mov     rcx, rsi; hInternet
0x18009cf4f  call    cs:__imp_InternetSetOptionA
0x18009cf56  nop     dword ptr [rax+rax+00h]
0x18009cf5b  movzx   eax, cs:?g_experimentalNetworkFeatures@@3_NA; bool g_experimentalNetworkFeatures
0x18009cf62  mov     [rbp+arg_10], eax
0x18009cf65  test    eax, eax
0x18009cf67  jz      short loc_18009CF84
0x18009cf69  mov     r9d, r14d; dwBufferLength
0x18009cf6c  lea     r8, [rbp+arg_10]; lpBuffer
0x18009cf70  mov     edx, 0B4h; dwOption
0x18009cf75  mov     rcx, rsi; hInternet
0x18009cf78  call    cs:__imp_InternetSetOptionA
0x18009cf7f  nop     dword ptr [rax+rax+00h]
0x18009cf84  cmp     cs:?g_enableEdgeCookies@@3_NA, 0; bool g_enableEdgeCookies
0x18009cf8b  jz      short loc_18009CFAF
0x18009cf8d  mov     r9d, r14d; dwBufferLength
0x18009cf90  mov     [rbp+arg_8], 1
0x18009cf97  lea     r8, [rbp+arg_8]; lpBuffer
0x18009cf9b  mov     edx, 0A6h; dwOption
0x18009cfa0  mov     rcx, rsi; hInternet
0x18009cfa3  call    cs:__imp_InternetSetOptionA
0x18009cfaa  nop     dword ptr [rax+rax+00h]
0x18009cfaf  mov     cs:?g_hSession@@3PEAXEA, rsi; void * g_hSession
0x18009cfb6  mov     rcx, rbx
0x18009cfb9  mov     edx, 3
0x18009cfbe  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009cfc3  mov     sil, 1
0x18009cfc6  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x18009cfcd  mov     edi, eax
0x18009cfcf  call    cs:__imp_LeaveCriticalSection
0x18009cfd6  nop     dword ptr [rax+rax+00h]
0x18009cfdb  lea     rcx, [rbp+arg_18]
0x18009cfdf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009cfe4  jmp     short loc_18009CFF5
0x18009cfe6  mov     edx, 3
0x18009cfeb  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009cff0  mov     edi, eax
0x18009cff2  mov     sil, 1
0x18009cff5  cmp     edi, 1
0x18009cff8  jnz     short loc_18009D018
0x18009cffa  test    sil, sil
0x18009cffd  jz      short loc_18009D028
0x18009cfff  mov     rax, [rbx]
0x18009d002  mov     rcx, rbx
0x18009d005  mov     rax, [rax+0E8h]
0x18009d00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d011  jmp     short loc_18009D025
0x18009d013  mov     edi, 2
0x18009d018  mov     r8d, r15d
0x18009d01b  mov     edx, edi
0x18009d01d  mov     rcx, rbx
0x18009d020  call    ?CheckTransitionStatusAndDispatchAbort@CINetEdge@@IEAAJW4INetEdgeStateTransition@@J@Z; CINetEdge::CheckTransitionStatusAndDispatchAbort(INetEdgeStateTransition,long)
0x18009d025  mov     r15d, eax
0x18009d028  lea     rcx, [rbp+var_18]; this
0x18009d02c  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x18009d031  mov     eax, r15d
0x18009d034  add     rsp, 48h
0x18009d038  pop     r15
0x18009d03a  pop     r14
0x18009d03c  pop     rdi
0x18009d03d  pop     rsi
0x18009d03e  pop     rbx
0x18009d03f  pop     rbp
0x18009d040  retn
```
