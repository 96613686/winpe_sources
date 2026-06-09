# COleScript::LogTelemetryOnScriptStateStarted(void)

- ea: `0x1800546d4`
- end: `0x180054c0d`
- name: `?LogTelemetryOnScriptStateStarted@COleScript@@QEAAXXZ`
- size: `1337`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180040610`

## callees

- `0x1800010cc`
- `0x1800011ec`
- `0x180001368`
- `0x18003d114`
- `0x180051b80`
- `0x1800546d4`
- `0x180056438`
- `0x180066adc`
- `0x180066d6c`
- `0x180066ec4`
- `0x1800673bc`
- `0x180076746`
- `0x1800767a0`
- `0x180076830`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180054af0`
- `msvcrt!swprintf_s` at `0x180054b0d`
- `msvcrt!swprintf_s` at `0x180054b2d`
- `msvcrt!swprintf_s` at `0x180054b4b`
- `msvcrt!swprintf_s` at `0x180054af0`
- `msvcrt!swprintf_s` at `0x180054b0d`
- `msvcrt!swprintf_s` at `0x180054b2d`
- `msvcrt!swprintf_s` at `0x180054b4b`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800547ca`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180054901`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800547ca`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180054901`
- `ADVAPI32!ReportEventW` at `0x180054bc9`
- `ADVAPI32!ReportEventW` at `0x180054bc9`
- `ADVAPI32!RegisterEventSourceW` at `0x180054b91`
- `ADVAPI32!RegisterEventSourceW` at `0x180054b91`
- `ADVAPI32!DeregisterEventSource` at `0x180054bd2`
- `ADVAPI32!DeregisterEventSource` at `0x180054bd2`

## string_xrefs

- `0x180054b51`: `VBScript is scheduled for deprecation. Our telemetry indicates that your system is currently utilizing VBScript.\nWe strongly recommend identifying and migrating away from any VBScript dependencies at the earliest.\n\nThe following process has been detected as using VBScript. The associated process tree and call stack are provided below to assist in identifying the scenario in which VBScript was invoked.\n`

## pseudocode

```c
void __fastcall COleScript::LogTelemetryOnScriptStateStarted(COleScript *this)
{
  const char *v2; // rdx
  RegistryBasedThrottle *v3; // rbx
  char *v4; // rax
  _QWORD *v5; // rcx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  RegistryBasedThrottle *v9; // rbx
  __int64 v10; // rax
  RegistryBasedThrottle *v11; // rbx
  __int64 v12; // rax
  RegistryBasedThrottle *v13; // rbx
  char *CurrentProcessName; // rax
  _QWORD *ThreadLocalStoragePointer; // rcx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  char *v19; // rax
  __int64 v20; // rcx
  RegistryBasedThrottle *v21; // rbx
  char *v22; // r15
  __int64 v23; // r14
  RegistryBasedThrottle *v24; // rbx
  __int64 v25; // rsi
  RegistryBasedThrottle *v26; // rbx
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  HANDLE v31; // rbx
  char v32[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h] BYREF
  char *v34; // [rsp+80h] [rbp-80h] BYREF
  char *v35; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h] BYREF
  __int64 CLSID; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR Strings[5]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v42[528]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v43[528]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Buffer[312]; // [rsp+500h] [rbp+400h] BYREF
  wchar_t v45[312]; // [rsp+770h] [rbp+670h] BYREF
  _BYTE v46[4096]; // [rsp+9E0h] [rbp+8E0h] BYREF
  wchar_t v47[2104]; // [rsp+19E0h] [rbp+18E0h] BYREF
  _BYTE v48[8192]; // [rsp+2A50h] [rbp+2950h] BYREF
  wchar_t v49[4152]; // [rsp+4A50h] [rbp+4950h] BYREF

  if ( !COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned int)dword_18008CE60 > 5 && (unsigned __int8)tlgKeywordOn() )
      {
        v9 = g_pTraceLoggingClient;
        if ( !*((_DWORD *)g_pTraceLoggingClient + 1754) )
          RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(g_pTraceLoggingClient);
        v10 = *((_QWORD *)v9 + 874);
        v11 = g_pTraceLoggingClient;
        v38 = v10;
        if ( !*((_DWORD *)g_pTraceLoggingClient + 1755) )
          RegistryBasedThrottle::IdentifyCurrentCallStack(g_pTraceLoggingClient);
        v12 = *((_QWORD *)v11 + 875);
        v13 = g_pTraceLoggingClient;
        v37 = v12;
        if ( !*((_DWORD *)g_pTraceLoggingClient + 1753) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl'::`2'::impl) )
            RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(v13);
          else
            RegistryBasedThrottle::IdentifyCurrentProcessTree(v13);
        }
        v36 = *((_QWORD *)v13 + 873);
        CurrentProcessName = RegistryBasedThrottle::GetCurrentProcessName(g_pTraceLoggingClient);
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v35 = CurrentProcessName;
        v34 = (char *)*((_QWORD *)this + 22);
        v39 = ThreadLocalStoragePointer[tls_index] + 16LL;
        v33 = 0x2000000;
        v32[0] = 1;
        CLSID = IEConfiguration_GetCLSID(268435459);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v16,
          (unsigned int)&word_1800832F6,
          v17,
          v18,
          (__int64)&CLSID,
          (__int64)&v39,
          (__int64)v32,
          (__int64)&v33,
          (__int64)&v34,
          (__int64)&v35,
          (__int64)&v36,
          (__int64)&v37,
          (__int64)&v38);
      }
      memset_0(v42, 0, 0x208u);
      memset_0(v43, 0, 0x208u);
      memset_0(v46, 0, sizeof(v46));
      memset_0(v48, 0, sizeof(v48));
      memset_0(Buffer, 0, 0x26Cu);
      memset_0(v45, 0, 0x26Cu);
      memset_0(v47, 0, 0x1068u);
      memset_0(v49, 0, 0x206Cu);
      v19 = RegistryBasedThrottle::GetCurrentProcessName(g_pTraceLoggingClient);
      v21 = g_pTraceLoggingClient;
      v22 = v19;
      if ( !*((_DWORD *)g_pTraceLoggingClient + 1753) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl'::`2'::impl) )
          RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(v21);
        else
          RegistryBasedThrottle::IdentifyCurrentProcessTree(v21);
      }
      v23 = *((_QWORD *)v21 + 873);
      v24 = g_pTraceLoggingClient;
      if ( !*((_DWORD *)g_pTraceLoggingClient + 1755) )
        RegistryBasedThrottle::IdentifyCurrentCallStack(g_pTraceLoggingClient);
      v25 = *((_QWORD *)v24 + 875);
      v26 = g_pTraceLoggingClient;
      if ( !*((_DWORD *)g_pTraceLoggingClient + 1754) )
        RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(g_pTraceLoggingClient);
      v27 = *((_QWORD *)v26 + 874);
      lambda_d296e3bd5bdb2e2e2e105be685639fa9_::operator()(v20, v22, v42, 260);
      lambda_d296e3bd5bdb2e2e2e105be685639fa9_::operator()(v28, v23, v43, 260);
      lambda_d296e3bd5bdb2e2e2e105be685639fa9_::operator()(v29, v25, v46, 2048);
      lambda_d296e3bd5bdb2e2e2e105be685639fa9_::operator()(v30, v27, v48, 4096);
      swprintf_s(Buffer, 0x136u, L"ProcessName = \"%s\"", v42);
      swprintf_s(v45, 0x136u, L"ProcessTree = \"%s\"", v43);
      swprintf_s(v47, 0x834u, L"CallStack = \"%s\"", v46);
      swprintf_s(v49, 0x1036u, L"ProcessTreeEnhanced = \"%s\"", v48);
      Strings[0] = L"VBScript is scheduled for deprecation. Our telemetry indicates that your system is currently utilizin"
                    "g VBScript.\n"
                    "We strongly recommend identifying and migrating away from any VBScript dependencies at the earliest."
                    "\n"
                    "\n"
                    "The following process has been detected as using VBScript. The associated process tree and call stac"
                    "k are provided below to assist in identifying the scenario in which VBScript was invoked.\n";
      Strings[1] = Buffer;
      Strings[2] = v45;
      Strings[3] = v47;
      Strings[4] = v49;
      v31 = RegisterEventSourceW(0, L"VBScriptDeprecationAlert");
      if ( v31 )
      {
        ReportEventW(v31, 2u, 0, 0x1000u, 0, 5u, 0, Strings, 0);
        DeregisterEventSource(v31);
      }
    }
    else if ( (unsigned int)dword_18008CE60 > 5 && (unsigned __int8)tlgKeywordOn() )
    {
      v3 = g_pTraceLoggingClient;
      if ( !*((_DWORD *)g_pTraceLoggingClient + 1753) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl'::`2'::impl) )
          RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(v3);
        else
          RegistryBasedThrottle::IdentifyCurrentProcessTree(v3);
      }
      v33 = *((_QWORD *)v3 + 873);
      v4 = RegistryBasedThrottle::GetCurrentProcessName(g_pTraceLoggingClient);
      v5 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v34 = v4;
      v35 = (char *)*((_QWORD *)this + 22);
      v37 = v5[tls_index] + 16LL;
      v36 = 0x2000000;
      v32[0] = 1;
      v38 = IEConfiguration_GetCLSID(268435459);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)byte_180083261,
        v7,
        v8,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)v32,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33);
    }
    RegistryBasedThrottle::WriteLoggingLocalTickCount(g_pTraceLoggingClient, v2);
    COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted = 1;
  }
}

```

## disassembly

```asm
0x1800546d4  push    rbp
0x1800546d6  push    rbx
0x1800546d7  push    rsi
0x1800546d8  push    rdi
0x1800546d9  push    r14
0x1800546db  push    r15
0x1800546dd  lea     rbp, [rsp-69D8h]
0x1800546e5  mov     eax, 6AD8h
0x1800546ea  call    _alloca_probe
0x1800546ef  sub     rsp, rax
0x1800546f2  mov     rax, cs:__security_cookie
0x1800546f9  xor     rax, rsp
0x1800546fc  mov     [rbp+6A00h+var_40], rax
0x180054703  cmp     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 0; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x18005470a  mov     rsi, rcx
0x18005470d  jnz     loc_180054BEE
0x180054713  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl(void)'::`2'::impl
0x18005471a  mov     rcx, r14
0x18005471d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x180054722  test    al, al
0x180054724  mov     edi, 5
0x180054729  mov     eax, cs:dword_18008CE60
0x18005472f  jnz     loc_180054826
0x180054735  cmp     eax, edi
0x180054737  jbe     loc_180054BD8
0x18005473d  call    _tlgKeywordOn
0x180054742  test    al, al
0x180054744  jz      loc_180054BD8
0x18005474a  mov     rbx, cs:g_pTraceLoggingClient
0x180054751  cmp     dword ptr [rbx+1B64h], 0
0x180054758  jnz     short loc_180054775
0x18005475a  mov     rcx, r14
0x18005475d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x180054762  mov     rcx, rbx; this
0x180054765  test    al, al
0x180054767  jz      short loc_180054770
0x180054769  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x18005476e  jmp     short loc_180054775
0x180054770  call    ?IdentifyCurrentProcessTree@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTree(void)
0x180054775  mov     rax, [rbx+1B48h]
0x18005477c  mov     rcx, cs:g_pTraceLoggingClient; this
0x180054783  mov     [rsp+6B00h+var_6A88], rax
0x180054788  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x18005478d  mov     rcx, gs:58h
0x180054796  mov     edx, cs:_tls_index
0x18005479c  mov     [rbp+6A00h+var_6A80], rax
0x1800547a0  mov     rax, [rsi+0B0h]
0x1800547a7  mov     [rbp+6A00h+var_6A78], rax
0x1800547ab  mov     eax, 10h
0x1800547b0  add     rax, [rcx+rdx*8]
0x1800547b4  mov     ecx, 10000003h
0x1800547b9  mov     [rbp+6A00h+var_6A68], rax
0x1800547bd  mov     [rbp+6A00h+var_6A70], 2000000h
0x1800547c5  mov     [rsp+6B00h+var_6A90], 1
0x1800547ca  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800547d0  mov     [rbp+6A00h+var_6A60], rax
0x1800547d4  lea     rdx, byte_180083261
0x1800547db  lea     rax, [rsp+6B00h+var_6A88]
0x1800547e0  mov     [rsp+6B00h+var_6AB0], rax
0x1800547e5  lea     rax, [rbp+6A00h+var_6A80]
0x1800547e9  mov     [rsp+6B00h+var_6AB8], rax
0x1800547ee  lea     rax, [rbp+6A00h+var_6A78]
0x1800547f2  mov     [rsp+6B00h+lpRawData], rax
0x1800547f7  lea     rax, [rbp+6A00h+var_6A70]
0x1800547fb  mov     [rsp+6B00h+lpStrings], rax
0x180054800  lea     rax, [rsp+6B00h+var_6A90]
0x180054805  mov     qword ptr [rsp+6B00h+dwDataSize], rax
0x18005480a  lea     rax, [rbp+6A00h+var_6A68]
0x18005480e  mov     qword ptr [rsp+6B00h+wNumStrings], rax
0x180054813  lea     rax, [rbp+6A00h+var_6A60]
0x180054817  mov     [rsp+6B00h+lpUserSid], rax
0x18005481c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180054821  jmp     loc_180054BD8
0x180054826  cmp     eax, edi
0x180054828  jbe     loc_18005496A
0x18005482e  call    _tlgKeywordOn
0x180054833  test    al, al
0x180054835  jz      loc_18005496A
0x18005483b  mov     rbx, cs:g_pTraceLoggingClient
0x180054842  cmp     dword ptr [rbx+1B68h], 0
0x180054849  jnz     short loc_180054853
0x18005484b  mov     rcx, rbx; this
0x18005484e  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x180054853  mov     rax, [rbx+1B50h]
0x18005485a  mov     rbx, cs:g_pTraceLoggingClient
0x180054861  mov     [rbp+6A00h+var_6A60], rax
0x180054865  cmp     dword ptr [rbx+1B6Ch], 0
0x18005486c  jnz     short loc_180054876
0x18005486e  mov     rcx, rbx; this
0x180054871  call    ?IdentifyCurrentCallStack@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentCallStack(void)
0x180054876  mov     rax, [rbx+1B58h]
0x18005487d  mov     rbx, cs:g_pTraceLoggingClient
0x180054884  mov     [rbp+6A00h+var_6A68], rax
0x180054888  cmp     dword ptr [rbx+1B64h], 0
0x18005488f  jnz     short loc_1800548AC
0x180054891  mov     rcx, r14
0x180054894  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x180054899  mov     rcx, rbx; this
0x18005489c  test    al, al
0x18005489e  jz      short loc_1800548A7
0x1800548a0  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x1800548a5  jmp     short loc_1800548AC
0x1800548a7  call    ?IdentifyCurrentProcessTree@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTree(void)
0x1800548ac  mov     rax, [rbx+1B48h]
0x1800548b3  mov     rcx, cs:g_pTraceLoggingClient; this
0x1800548ba  mov     [rbp+6A00h+var_6A70], rax
0x1800548be  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x1800548c3  mov     rcx, gs:58h
0x1800548cc  mov     edx, cs:_tls_index
0x1800548d2  mov     [rbp+6A00h+var_6A78], rax
0x1800548d6  mov     rax, [rsi+0B0h]
0x1800548dd  mov     [rbp+6A00h+var_6A80], rax
0x1800548e1  mov     eax, 10h
0x1800548e6  add     rax, [rcx+rdx*8]
0x1800548ea  mov     ecx, 10000003h
0x1800548ef  mov     [rbp+6A00h+var_6A58], rax
0x1800548f3  mov     [rsp+6B00h+var_6A88], 2000000h
0x1800548fc  mov     [rsp+6B00h+var_6A90], 1
0x180054901  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180054907  mov     [rbp+6A00h+var_6A50], rax
0x18005490b  lea     rdx, word_1800832F6
0x180054912  lea     rax, [rbp+6A00h+var_6A60]
0x180054916  mov     [rsp+6B00h+var_6AA0], rax
0x18005491b  lea     rax, [rbp+6A00h+var_6A68]
0x18005491f  mov     [rsp+6B00h+var_6AA8], rax
0x180054924  lea     rax, [rbp+6A00h+var_6A70]
0x180054928  mov     [rsp+6B00h+var_6AB0], rax
0x18005492d  lea     rax, [rbp+6A00h+var_6A78]
0x180054931  mov     [rsp+6B00h+var_6AB8], rax
0x180054936  lea     rax, [rbp+6A00h+var_6A80]
0x18005493a  mov     [rsp+6B00h+lpRawData], rax
0x18005493f  lea     rax, [rsp+6B00h+var_6A88]
0x180054944  mov     [rsp+6B00h+lpStrings], rax
0x180054949  lea     rax, [rsp+6B00h+var_6A90]
0x18005494e  mov     qword ptr [rsp+6B00h+dwDataSize], rax
0x180054953  lea     rax, [rbp+6A00h+var_6A58]
0x180054957  mov     qword ptr [rsp+6B00h+wNumStrings], rax
0x18005495c  lea     rax, [rbp+6A00h+var_6A50]
0x180054960  mov     [rsp+6B00h+lpUserSid], rax
0x180054965  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005496a  mov     ebx, 208h
0x18005496f  lea     rcx, [rbp+6A00h+var_6A20]; void *
0x180054973  mov     r8d, ebx; Size
0x180054976  xor     edx, edx; Val
0x180054978  call    memset_0
0x18005497d  mov     r8d, ebx; Size
0x180054980  lea     rcx, [rbp+6A00h+var_6810]; void *
0x180054987  xor     edx, edx; Val
0x180054989  call    memset_0
0x18005498e  xor     edx, edx; Val
0x180054990  lea     rcx, [rbp+6A00h+var_6120]; void *
0x180054997  mov     r8d, 1000h; Size
0x18005499d  call    memset_0
0x1800549a2  xor     edx, edx; Val
0x1800549a4  lea     rcx, [rbp+6A00h+var_40B0]; void *
0x1800549ab  mov     r8d, 2000h; Size
0x1800549b1  call    memset_0
0x1800549b6  mov     ebx, 26Ch
0x1800549bb  lea     rcx, [rbp+6A00h+Buffer]; void *
0x1800549c2  mov     r8d, ebx; Size
0x1800549c5  xor     edx, edx; Val
0x1800549c7  call    memset_0
0x1800549cc  mov     r8d, ebx; Size
0x1800549cf  lea     rcx, [rbp+6A00h+var_6390]; void *
0x1800549d6  xor     edx, edx; Val
0x1800549d8  call    memset_0
0x1800549dd  xor     edx, edx; Val
0x1800549df  lea     rcx, [rbp+6A00h+var_5120]; void *
0x1800549e6  mov     r8d, 1068h; Size
0x1800549ec  call    memset_0
0x1800549f1  xor     edx, edx; Val
0x1800549f3  lea     rcx, [rbp+6A00h+var_20B0]; void *
0x1800549fa  mov     r8d, 206Ch; Size
0x180054a00  call    memset_0
0x180054a05  mov     rcx, cs:g_pTraceLoggingClient; this
0x180054a0c  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x180054a11  mov     rbx, cs:g_pTraceLoggingClient
0x180054a18  mov     r15, rax
0x180054a1b  cmp     dword ptr [rbx+1B64h], 0
0x180054a22  jnz     short loc_180054A3F
0x180054a24  mov     rcx, r14
0x180054a27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x180054a2c  mov     rcx, rbx; this
0x180054a2f  test    al, al
0x180054a31  jz      short loc_180054A3A
0x180054a33  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x180054a38  jmp     short loc_180054A3F
0x180054a3a  call    ?IdentifyCurrentProcessTree@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTree(void)
0x180054a3f  mov     r14, [rbx+1B48h]
0x180054a46  mov     rbx, cs:g_pTraceLoggingClient
0x180054a4d  cmp     dword ptr [rbx+1B6Ch], 0
0x180054a54  jnz     short loc_180054A5E
0x180054a56  mov     rcx, rbx; this
0x180054a59  call    ?IdentifyCurrentCallStack@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentCallStack(void)
0x180054a5e  mov     rsi, [rbx+1B58h]
0x180054a65  mov     rbx, cs:g_pTraceLoggingClient
0x180054a6c  cmp     dword ptr [rbx+1B68h], 0
0x180054a73  jnz     short loc_180054A7D
0x180054a75  mov     rcx, rbx; this
0x180054a78  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x180054a7d  mov     rbx, [rbx+1B50h]
0x180054a84  lea     r8, [rbp+6A00h+var_6A20]
0x180054a88  mov     r9d, 104h
0x180054a8e  mov     rdx, r15
0x180054a91  call    _lambda_d296e3bd5bdb2e2e2e105be685639fa9___operator__
0x180054a96  mov     r9d, 104h
0x180054a9c  lea     r8, [rbp+6A00h+var_6810]
0x180054aa3  mov     rdx, r14
0x180054aa6  call    _lambda_d296e3bd5bdb2e2e2e105be685639fa9___operator__
0x180054aab  mov     r9d, 800h
0x180054ab1  lea     r8, [rbp+6A00h+var_6120]
0x180054ab8  mov     rdx, rsi
0x180054abb  call    _lambda_d296e3bd5bdb2e2e2e105be685639fa9___operator__
0x180054ac0  mov     esi, 1000h
0x180054ac5  lea     r8, [rbp+6A00h+var_40B0]
0x180054acc  mov     r9d, esi
0x180054acf  mov     rdx, rbx
0x180054ad2  call    _lambda_d296e3bd5bdb2e2e2e105be685639fa9___operator__
0x180054ad7  mov     ebx, 136h
0x180054adc  lea     r9, [rbp+6A00h+var_6A20]
0x180054ae0  mov     edx, ebx; BufferCount
0x180054ae2  lea     r8, aProcessnameS; "ProcessName = \"%s\""
0x180054ae9  lea     rcx, [rbp+6A00h+Buffer]; Buffer
0x180054af0  call    cs:__imp_swprintf_s
0x180054af6  lea     r9, [rbp+6A00h+var_6810]
0x180054afd  mov     edx, ebx; BufferCount
0x180054aff  lea     r8, aProcesstreeS; "ProcessTree = \"%s\""
0x180054b06  lea     rcx, [rbp+6A00h+var_6390]; Buffer
0x180054b0d  call    cs:__imp_swprintf_s
0x180054b13  lea     r9, [rbp+6A00h+var_6120]
0x180054b1a  mov     edx, 834h; BufferCount
0x180054b1f  lea     r8, aCallstackS; "CallStack = \"%s\""
0x180054b26  lea     rcx, [rbp+6A00h+var_5120]; Buffer
0x180054b2d  call    cs:__imp_swprintf_s
0x180054b33  lea     r9, [rbp+6A00h+var_40B0]
0x180054b3a  lea     r8, aProcesstreeenh; "ProcessTreeEnhanced = \"%s\""
0x180054b41  lea     edx, [rsi+36h]; BufferCount
0x180054b44  lea     rcx, [rbp+6A00h+var_20B0]; Buffer
0x180054b4b  call    cs:__imp_swprintf_s
0x180054b51  lea     rax, aVbscriptIsSche; "VBScript is scheduled for deprecation. "...
0x180054b58  xor     ecx, ecx; lpUNCServerName
0x180054b5a  mov     [rbp+6A00h+Strings], rax
0x180054b5e  lea     rdx, SourceName; "VBScriptDeprecationAlert"
0x180054b65  lea     rax, [rbp+6A00h+Buffer]
0x180054b6c  mov     [rbp+6A00h+var_6A40], rax
0x180054b70  lea     rax, [rbp+6A00h+var_6390]
0x180054b77  mov     [rbp+6A00h+var_6A38], rax
0x180054b7b  lea     rax, [rbp+6A00h+var_5120]
0x180054b82  mov     [rbp+6A00h+var_6A30], rax
0x180054b86  lea     rax, [rbp+6A00h+var_20B0]
0x180054b8d  mov     [rbp+6A00h+var_6A28], rax
0x180054b91  call    cs:__imp_RegisterEventSourceW
0x180054b97  mov     rbx, rax
0x180054b9a  test    rax, rax
0x180054b9d  jz      short loc_180054BD8
0x180054b9f  xor     r8d, r8d; wCategory
0x180054ba2  lea     rax, [rbp+6A00h+Strings]
0x180054ba6  mov     [rsp+6B00h+lpRawData], r8; lpRawData
0x180054bab  mov     r9d, esi; dwEventID
0x180054bae  mov     [rsp+6B00h+lpStrings], rax; lpStrings
0x180054bb3  mov     rcx, rbx; hEventLog
0x180054bb6  mov     [rsp+6B00h+dwDataSize], r8d; dwDataSize
0x180054bbb  lea     edx, [r8+2]; wType
0x180054bbf  mov     [rsp+6B00h+wNumStrings], di; wNumStrings
0x180054bc4  mov     [rsp+6B00h+lpUserSid], r8; lpUserSid
0x180054bc9  call    cs:__imp_ReportEventW
0x180054bcf  mov     rcx, rbx; hEventLog
0x180054bd2  call    cs:__imp_DeregisterEventSource
0x180054bd8  mov     rcx, cs:g_pTraceLoggingClient; this
0x180054bdf  call    ?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z; RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)
0x180054be4  mov     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x180054bee  mov     rcx, [rbp+6A00h+var_40]
0x180054bf5  xor     rcx, rsp; StackCookie
0x180054bf8  call    __security_check_cookie
0x180054bfd  add     rsp, 6AD8h
0x180054c04  pop     r15
0x180054c06  pop     r14
0x180054c08  pop     rdi
0x180054c09  pop     rsi
0x180054c0a  pop     rbx
0x180054c0b  pop     rbp
0x180054c0c  retn
```
