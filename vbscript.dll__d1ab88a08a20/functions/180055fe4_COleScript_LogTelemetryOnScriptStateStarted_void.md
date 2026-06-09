# COleScript::LogTelemetryOnScriptStateStarted(void)

- ea: `0x180055fe4`
- end: `0x180056554`
- name: `?LogTelemetryOnScriptStateStarted@COleScript@@QEAAXXZ`
- size: `1392`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180041cf0`

## callees

- `0x1800010d4`
- `0x1800011f4`
- `0x180001370`
- `0x18003e2a4`
- `0x180053370`
- `0x180055fe4`
- `0x180057de8`
- `0x180068a14`
- `0x180068cf4`
- `0x180068e7c`
- `0x180069410`
- `0x180079436`
- `0x180079490`
- `0x180079520`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18005640c`
- `msvcrt!swprintf_s` at `0x18005642f`
- `msvcrt!swprintf_s` at `0x180056455`
- `msvcrt!swprintf_s` at `0x180056479`
- `msvcrt!swprintf_s` at `0x18005640c`
- `msvcrt!swprintf_s` at `0x18005642f`
- `msvcrt!swprintf_s` at `0x180056455`
- `msvcrt!swprintf_s` at `0x180056479`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800560da`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180056217`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800560da`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180056217`
- `ADVAPI32!ReportEventW` at `0x180056503`
- `ADVAPI32!ReportEventW` at `0x180056503`
- `ADVAPI32!RegisterEventSourceW` at `0x1800564c5`
- `ADVAPI32!RegisterEventSourceW` at `0x1800564c5`
- `ADVAPI32!DeregisterEventSource` at `0x180056512`
- `ADVAPI32!DeregisterEventSource` at `0x180056512`

## string_xrefs

- `0x180056485`: `VBScript is scheduled for deprecation. Our telemetry indicates that your system is currently utilizing VBScript.\nWe strongly recommend identifying and migrating away from any VBScript dependencies at the earliest.\n\nThe following process has been detected as using VBScript. The associated process tree and call stack are provided below to assist in identifying the scenario in which VBScript was invoked.\n`

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
      if ( (unsigned int)dword_18008FE60 > 5 && (unsigned __int8)tlgKeywordOn() )
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
          (unsigned int)&word_1800862F6,
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
    else if ( (unsigned int)dword_18008FE60 > 5 && (unsigned __int8)tlgKeywordOn() )
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
        (unsigned int)byte_180086261,
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
0x180055fe4  push    rbp
0x180055fe6  push    rbx
0x180055fe7  push    rsi
0x180055fe8  push    rdi
0x180055fe9  push    r14
0x180055feb  push    r15
0x180055fed  lea     rbp, [rsp-69D8h]
0x180055ff5  mov     eax, 6AD8h
0x180055ffa  call    _alloca_probe
0x180055fff  sub     rsp, rax
0x180056002  mov     rax, cs:__security_cookie
0x180056009  xor     rax, rsp
0x18005600c  mov     [rbp+6A00h+var_40], rax
0x180056013  cmp     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 0; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x18005601a  mov     rsi, rcx
0x18005601d  jnz     loc_180056534
0x180056023  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl(void)'::`2'::impl
0x18005602a  mov     rcx, r14
0x18005602d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x180056032  test    al, al
0x180056034  mov     edi, 5
0x180056039  mov     eax, cs:dword_18008FE60
0x18005603f  jnz     loc_18005613C
0x180056045  cmp     eax, edi
0x180056047  jbe     loc_18005651E
0x18005604d  call    _tlgKeywordOn
0x180056052  test    al, al
0x180056054  jz      loc_18005651E
0x18005605a  mov     rbx, cs:g_pTraceLoggingClient
0x180056061  cmp     dword ptr [rbx+1B64h], 0
0x180056068  jnz     short loc_180056085
0x18005606a  mov     rcx, r14
0x18005606d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x180056072  mov     rcx, rbx; this
0x180056075  test    al, al
0x180056077  jz      short loc_180056080
0x180056079  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x18005607e  jmp     short loc_180056085
0x180056080  call    ?IdentifyCurrentProcessTree@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTree(void)
0x180056085  mov     rax, [rbx+1B48h]
0x18005608c  mov     rcx, cs:g_pTraceLoggingClient; this
0x180056093  mov     [rsp+6B00h+var_6A88], rax
0x180056098  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x18005609d  mov     rcx, gs:58h
0x1800560a6  mov     edx, cs:_tls_index
0x1800560ac  mov     [rbp+6A00h+var_6A80], rax
0x1800560b0  mov     rax, [rsi+0B0h]
0x1800560b7  mov     [rbp+6A00h+var_6A78], rax
0x1800560bb  mov     eax, 10h
0x1800560c0  add     rax, [rcx+rdx*8]
0x1800560c4  mov     ecx, 10000003h
0x1800560c9  mov     [rbp+6A00h+var_6A68], rax
0x1800560cd  mov     [rbp+6A00h+var_6A70], 2000000h
0x1800560d5  mov     [rsp+6B00h+var_6A90], 1
0x1800560da  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800560e1  nop     dword ptr [rax+rax+00h]
0x1800560e6  mov     [rbp+6A00h+var_6A60], rax
0x1800560ea  lea     rdx, byte_180086261
0x1800560f1  lea     rax, [rsp+6B00h+var_6A88]
0x1800560f6  mov     [rsp+6B00h+var_6AB0], rax
0x1800560fb  lea     rax, [rbp+6A00h+var_6A80]
0x1800560ff  mov     [rsp+6B00h+var_6AB8], rax
0x180056104  lea     rax, [rbp+6A00h+var_6A78]
0x180056108  mov     [rsp+6B00h+lpRawData], rax
0x18005610d  lea     rax, [rbp+6A00h+var_6A70]
0x180056111  mov     [rsp+6B00h+lpStrings], rax
0x180056116  lea     rax, [rsp+6B00h+var_6A90]
0x18005611b  mov     qword ptr [rsp+6B00h+dwDataSize], rax
0x180056120  lea     rax, [rbp+6A00h+var_6A68]
0x180056124  mov     qword ptr [rsp+6B00h+wNumStrings], rax
0x180056129  lea     rax, [rbp+6A00h+var_6A60]
0x18005612d  mov     [rsp+6B00h+lpUserSid], rax
0x180056132  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180056137  jmp     loc_18005651E
0x18005613c  cmp     eax, edi
0x18005613e  jbe     loc_180056286
0x180056144  call    _tlgKeywordOn
0x180056149  test    al, al
0x18005614b  jz      loc_180056286
0x180056151  mov     rbx, cs:g_pTraceLoggingClient
0x180056158  cmp     dword ptr [rbx+1B68h], 0
0x18005615f  jnz     short loc_180056169
0x180056161  mov     rcx, rbx; this
0x180056164  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x180056169  mov     rax, [rbx+1B50h]
0x180056170  mov     rbx, cs:g_pTraceLoggingClient
0x180056177  mov     [rbp+6A00h+var_6A60], rax
0x18005617b  cmp     dword ptr [rbx+1B6Ch], 0
0x180056182  jnz     short loc_18005618C
0x180056184  mov     rcx, rbx; this
0x180056187  call    ?IdentifyCurrentCallStack@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentCallStack(void)
0x18005618c  mov     rax, [rbx+1B58h]
0x180056193  mov     rbx, cs:g_pTraceLoggingClient
0x18005619a  mov     [rbp+6A00h+var_6A68], rax
0x18005619e  cmp     dword ptr [rbx+1B64h], 0
0x1800561a5  jnz     short loc_1800561C2
0x1800561a7  mov     rcx, r14
0x1800561aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x1800561af  mov     rcx, rbx; this
0x1800561b2  test    al, al
0x1800561b4  jz      short loc_1800561BD
0x1800561b6  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x1800561bb  jmp     short loc_1800561C2
0x1800561bd  call    ?IdentifyCurrentProcessTree@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTree(void)
0x1800561c2  mov     rax, [rbx+1B48h]
0x1800561c9  mov     rcx, cs:g_pTraceLoggingClient; this
0x1800561d0  mov     [rbp+6A00h+var_6A70], rax
0x1800561d4  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x1800561d9  mov     rcx, gs:58h
0x1800561e2  mov     edx, cs:_tls_index
0x1800561e8  mov     [rbp+6A00h+var_6A78], rax
0x1800561ec  mov     rax, [rsi+0B0h]
0x1800561f3  mov     [rbp+6A00h+var_6A80], rax
0x1800561f7  mov     eax, 10h
0x1800561fc  add     rax, [rcx+rdx*8]
0x180056200  mov     ecx, 10000003h
0x180056205  mov     [rbp+6A00h+var_6A58], rax
0x180056209  mov     [rsp+6B00h+var_6A88], 2000000h
0x180056212  mov     [rsp+6B00h+var_6A90], 1
0x180056217  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18005621e  nop     dword ptr [rax+rax+00h]
0x180056223  mov     [rbp+6A00h+var_6A50], rax
0x180056227  lea     rdx, word_1800862F6
0x18005622e  lea     rax, [rbp+6A00h+var_6A60]
0x180056232  mov     [rsp+6B00h+var_6AA0], rax
0x180056237  lea     rax, [rbp+6A00h+var_6A68]
0x18005623b  mov     [rsp+6B00h+var_6AA8], rax
0x180056240  lea     rax, [rbp+6A00h+var_6A70]
0x180056244  mov     [rsp+6B00h+var_6AB0], rax
0x180056249  lea     rax, [rbp+6A00h+var_6A78]
0x18005624d  mov     [rsp+6B00h+var_6AB8], rax
0x180056252  lea     rax, [rbp+6A00h+var_6A80]
0x180056256  mov     [rsp+6B00h+lpRawData], rax
0x18005625b  lea     rax, [rsp+6B00h+var_6A88]
0x180056260  mov     [rsp+6B00h+lpStrings], rax
0x180056265  lea     rax, [rsp+6B00h+var_6A90]
0x18005626a  mov     qword ptr [rsp+6B00h+dwDataSize], rax
0x18005626f  lea     rax, [rbp+6A00h+var_6A58]
0x180056273  mov     qword ptr [rsp+6B00h+wNumStrings], rax
0x180056278  lea     rax, [rbp+6A00h+var_6A50]
0x18005627c  mov     [rsp+6B00h+lpUserSid], rax
0x180056281  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180056286  mov     ebx, 208h
0x18005628b  lea     rcx, [rbp+6A00h+var_6A20]; void *
0x18005628f  mov     r8d, ebx; Size
0x180056292  xor     edx, edx; Val
0x180056294  call    memset_0
0x180056299  mov     r8d, ebx; Size
0x18005629c  lea     rcx, [rbp+6A00h+var_6810]; void *
0x1800562a3  xor     edx, edx; Val
0x1800562a5  call    memset_0
0x1800562aa  xor     edx, edx; Val
0x1800562ac  lea     rcx, [rbp+6A00h+var_6120]; void *
0x1800562b3  mov     r8d, 1000h; Size
0x1800562b9  call    memset_0
0x1800562be  xor     edx, edx; Val
0x1800562c0  lea     rcx, [rbp+6A00h+var_40B0]; void *
0x1800562c7  mov     r8d, 2000h; Size
0x1800562cd  call    memset_0
0x1800562d2  mov     ebx, 26Ch
0x1800562d7  lea     rcx, [rbp+6A00h+Buffer]; void *
0x1800562de  mov     r8d, ebx; Size
0x1800562e1  xor     edx, edx; Val
0x1800562e3  call    memset_0
0x1800562e8  mov     r8d, ebx; Size
0x1800562eb  lea     rcx, [rbp+6A00h+var_6390]; void *
0x1800562f2  xor     edx, edx; Val
0x1800562f4  call    memset_0
0x1800562f9  xor     edx, edx; Val
0x1800562fb  lea     rcx, [rbp+6A00h+var_5120]; void *
0x180056302  mov     r8d, 1068h; Size
0x180056308  call    memset_0
0x18005630d  xor     edx, edx; Val
0x18005630f  lea     rcx, [rbp+6A00h+var_20B0]; void *
0x180056316  mov     r8d, 206Ch; Size
0x18005631c  call    memset_0
0x180056321  mov     rcx, cs:g_pTraceLoggingClient; this
0x180056328  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x18005632d  mov     rbx, cs:g_pTraceLoggingClient
0x180056334  mov     r15, rax
0x180056337  cmp     dword ptr [rbx+1B64h], 0
0x18005633e  jnz     short loc_18005635B
0x180056340  mov     rcx, r14
0x180056343  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x180056348  mov     rcx, rbx; this
0x18005634b  test    al, al
0x18005634d  jz      short loc_180056356
0x18005634f  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x180056354  jmp     short loc_18005635B
0x180056356  call    ?IdentifyCurrentProcessTree@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTree(void)
0x18005635b  mov     r14, [rbx+1B48h]
0x180056362  mov     rbx, cs:g_pTraceLoggingClient
0x180056369  cmp     dword ptr [rbx+1B6Ch], 0
0x180056370  jnz     short loc_18005637A
0x180056372  mov     rcx, rbx; this
0x180056375  call    ?IdentifyCurrentCallStack@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentCallStack(void)
0x18005637a  mov     rsi, [rbx+1B58h]
0x180056381  mov     rbx, cs:g_pTraceLoggingClient
0x180056388  cmp     dword ptr [rbx+1B68h], 0
0x18005638f  jnz     short loc_180056399
0x180056391  mov     rcx, rbx; this
0x180056394  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x180056399  mov     rbx, [rbx+1B50h]
0x1800563a0  lea     r8, [rbp+6A00h+var_6A20]
0x1800563a4  mov     r9d, 104h
0x1800563aa  mov     rdx, r15
0x1800563ad  call    _lambda_d296e3bd5bdb2e2e2e105be685639fa9___operator__
0x1800563b2  mov     r9d, 104h
0x1800563b8  lea     r8, [rbp+6A00h+var_6810]
0x1800563bf  mov     rdx, r14
0x1800563c2  call    _lambda_d296e3bd5bdb2e2e2e105be685639fa9___operator__
0x1800563c7  mov     r9d, 800h
0x1800563cd  lea     r8, [rbp+6A00h+var_6120]
0x1800563d4  mov     rdx, rsi
0x1800563d7  call    _lambda_d296e3bd5bdb2e2e2e105be685639fa9___operator__
0x1800563dc  mov     esi, 1000h
0x1800563e1  lea     r8, [rbp+6A00h+var_40B0]
0x1800563e8  mov     r9d, esi
0x1800563eb  mov     rdx, rbx
0x1800563ee  call    _lambda_d296e3bd5bdb2e2e2e105be685639fa9___operator__
0x1800563f3  mov     ebx, 136h
0x1800563f8  lea     r9, [rbp+6A00h+var_6A20]
0x1800563fc  mov     edx, ebx; BufferCount
0x1800563fe  lea     r8, aProcessnameS; "ProcessName = \"%s\""
0x180056405  lea     rcx, [rbp+6A00h+Buffer]; Buffer
0x18005640c  call    cs:__imp_swprintf_s
0x180056413  nop     dword ptr [rax+rax+00h]
0x180056418  lea     r9, [rbp+6A00h+var_6810]
0x18005641f  mov     edx, ebx; BufferCount
0x180056421  lea     r8, aProcesstreeS; "ProcessTree = \"%s\""
0x180056428  lea     rcx, [rbp+6A00h+var_6390]; Buffer
0x18005642f  call    cs:__imp_swprintf_s
0x180056436  nop     dword ptr [rax+rax+00h]
0x18005643b  lea     r9, [rbp+6A00h+var_6120]
0x180056442  mov     edx, 834h; BufferCount
0x180056447  lea     r8, aCallstackS; "CallStack = \"%s\""
0x18005644e  lea     rcx, [rbp+6A00h+var_5120]; Buffer
0x180056455  call    cs:__imp_swprintf_s
0x18005645c  nop     dword ptr [rax+rax+00h]
0x180056461  lea     r9, [rbp+6A00h+var_40B0]
0x180056468  lea     r8, aProcesstreeenh; "ProcessTreeEnhanced = \"%s\""
0x18005646f  lea     edx, [rsi+36h]; BufferCount
0x180056472  lea     rcx, [rbp+6A00h+var_20B0]; Buffer
0x180056479  call    cs:__imp_swprintf_s
0x180056480  nop     dword ptr [rax+rax+00h]
0x180056485  lea     rax, aVbscriptIsSche; "VBScript is scheduled for deprecation. "...
0x18005648c  xor     ecx, ecx; lpUNCServerName
0x18005648e  mov     [rbp+6A00h+Strings], rax
0x180056492  lea     rdx, SourceName; "VBScriptDeprecationAlert"
0x180056499  lea     rax, [rbp+6A00h+Buffer]
0x1800564a0  mov     [rbp+6A00h+var_6A40], rax
0x1800564a4  lea     rax, [rbp+6A00h+var_6390]
0x1800564ab  mov     [rbp+6A00h+var_6A38], rax
0x1800564af  lea     rax, [rbp+6A00h+var_5120]
0x1800564b6  mov     [rbp+6A00h+var_6A30], rax
0x1800564ba  lea     rax, [rbp+6A00h+var_20B0]
0x1800564c1  mov     [rbp+6A00h+var_6A28], rax
0x1800564c5  call    cs:__imp_RegisterEventSourceW
0x1800564cc  nop     dword ptr [rax+rax+00h]
0x1800564d1  mov     rbx, rax
0x1800564d4  test    rax, rax
0x1800564d7  jz      short loc_18005651E
0x1800564d9  xor     r8d, r8d; wCategory
0x1800564dc  lea     rax, [rbp+6A00h+Strings]
0x1800564e0  mov     [rsp+6B00h+lpRawData], r8; lpRawData
0x1800564e5  mov     r9d, esi; dwEventID
0x1800564e8  mov     [rsp+6B00h+lpStrings], rax; lpStrings
0x1800564ed  mov     rcx, rbx; hEventLog
0x1800564f0  mov     [rsp+6B00h+dwDataSize], r8d; dwDataSize
0x1800564f5  lea     edx, [r8+2]; wType
0x1800564f9  mov     [rsp+6B00h+wNumStrings], di; wNumStrings
0x1800564fe  mov     [rsp+6B00h+lpUserSid], r8; lpUserSid
0x180056503  call    cs:__imp_ReportEventW
0x18005650a  nop     dword ptr [rax+rax+00h]
0x18005650f  mov     rcx, rbx; hEventLog
0x180056512  call    cs:__imp_DeregisterEventSource
0x180056519  nop     dword ptr [rax+rax+00h]
0x18005651e  mov     rcx, cs:g_pTraceLoggingClient; this
0x180056525  call    ?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z; RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)
0x18005652a  mov     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x180056534  mov     rcx, [rbp+6A00h+var_40]
0x18005653b  xor     rcx, rsp; StackCookie
0x18005653e  call    __security_check_cookie
0x180056543  add     rsp, 6AD8h
0x18005654a  pop     r15
0x18005654c  pop     r14
0x18005654e  pop     rdi
0x18005654f  pop     rsi
0x180056550  pop     rbx
0x180056551  pop     rbp
0x180056552  retn
```
