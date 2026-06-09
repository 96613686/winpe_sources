# Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Initialize(bool)

- ea: `0x18009be24`
- end: `0x18009c33c`
- name: `?Initialize@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@QEAAJ_N@Z`
- size: `1304`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcDecoderHostApiWrapper *__hidden this, bool)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802cea74`
- `0x180318b2c`

## callees

- `0x18001d160`
- `0x180026ecc`
- `0x180035698`
- `0x180048ff4`
- `0x18005b050`
- `0x180086c3c`
- `0x180086e5c`
- `0x180086e78`
- `0x180087044`
- `0x180089d90`
- `0x18008bd1c`
- `0x18009be24`
- `0x18009c900`
- `0x18009d380`
- `0x1800a2004`
- `0x1800d0d9c`
- `0x180112c8c`
- `0x18012de40`
- `0x18012eb08`
- `0x180161298`
- `0x18019e8d0`
- `0x1802d979c`
- `0x1803188c0`
- `0x180318c90`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x18009c050`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x18009c06f`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x18009c050`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x18009c06f`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x18009c0c0`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x18009c0c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009be5b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009be5b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18009beb3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18009c277`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18009beb3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18009c277`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c1fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c1fd`
- `api-ms-win-security-isolationapi-l1-2-0!CreateIsolatedProcess` at `0x18009c17e`
- `api-ms-win-security-isolationapi-l1-2-0!CreateIsolatedProcess` at `0x18009c17e`

## string_xrefs

- `0x18009be8f`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x18009becb`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x18009bef1`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x18009bfac`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x18009c1a5`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x18009c20d`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x18009c25e`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x18009c28f`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Initialize(
        Microsoft::Diagnostics::UtcDecoderHostApiWrapper *this,
        char a2)
{
  HANDLE *v4; // rsi
  void *v5; // rcx
  bool v6; // al
  const char *v8; // r9
  int v9; // eax
  void *v10; // rdx
  void **v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD *v19; // rax
  WCHAR *v20; // rcx
  int IsolatedProcess; // ebx
  const char *v22; // r9
  unsigned int LastError; // ebx
  const char *v24; // r9
  __int64 v25; // rdx
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-2B8h]
  int v28; // [rsp+20h] [rbp-2B8h]
  unsigned int v29; // [rsp+40h] [rbp-298h] BYREF
  unsigned int v30[2]; // [rsp+48h] [rbp-290h] BYREF
  __int64 v31; // [rsp+50h] [rbp-288h] BYREF
  __int64 v32; // [rsp+58h] [rbp-280h] BYREF
  __int64 v33; // [rsp+60h] [rbp-278h]
  __int64 v34; // [rsp+68h] [rbp-270h]
  HANDLE hObject[2]; // [rsp+70h] [rbp-268h]
  __int64 v36; // [rsp+80h] [rbp-258h]
  int v37[4]; // [rsp+88h] [rbp-250h] BYREF
  __int128 v38; // [rsp+98h] [rbp-240h]
  __int64 v39; // [rsp+A8h] [rbp-230h]
  _BYTE v40[16]; // [rsp+B0h] [rbp-228h] BYREF
  _BYTE v41[240]; // [rsp+C0h] [rbp-218h] BYREF
  WCHAR Src[4]; // [rsp+1B0h] [rbp-128h] BYREF
  unsigned __int64 v43; // [rsp+1C8h] [rbp-110h]
  _OWORD v44[2]; // [rsp+1D0h] [rbp-108h] BYREF
  _BYTE v45[72]; // [rsp+1F0h] [rbp-E8h] BYREF
  int v46; // [rsp+238h] [rbp-A0h]
  int v47; // [rsp+23Ch] [rbp-9Ch]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v4 = (HANDLE *)((char *)this + 16);
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
    v6 = WaitForSingleObject(v5, 0) == 258;
  else
    v6 = 0;
  if ( a2 )
  {
    if ( v6 && !TerminateProcess(*v4, 1u) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
        v8);
    v9 = Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Unbind(this);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
        (const char *)(unsigned int)v9,
        v27);
  }
  else if ( v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
      (const char *)0x8000FFFFLL,
      v27);
    return 2147549183LL;
  }
  v32 = 24;
  v33 = 0;
  v34 = 1;
  v31 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (unsigned int)&v31,
    0,
    0,
    (unsigned int)&v32,
    0);
  v33 = 0;
  LODWORD(v34) = 0;
  if ( !*((_QWORD *)this + 1) )
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (_DWORD)this + 8,
      0,
      0,
      (unsigned int)&v32,
      0);
  *(_QWORD *)v30 = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    v30,
    0);
  v12 = Microsoft::Diagnostics::DuplicateInheritable(*((HANDLE *)this + 1), v10, (unsigned int)v30, v11);
  v13 = v12;
  if ( v12 >= 0 )
  {
    *(_OWORD *)hObject = 0;
    v36 = 0;
    std::wstring::wstring((__int64)Src, &Microsoft::Diagnostics::UtcDecoderHostApiWrapper::k_utcDecoderHostBinaryPath);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src, 1, 0);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v40);
    v14 = std::operator<<<wchar_t>(v41, Src);
    v15 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v14, L" ");
    v16 = std::wostream::operator<<(v15, v31);
    v17 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v16, L" ");
    std::wostream::operator<<(v17, *(_QWORD *)v30);
    v29 = 0;
    v44[0] = *(_OWORD *)&off_1803692B0;
    if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v44, &v29) )
    {
      v18 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v41, L" ");
      std::wostream::operator<<(v18, v29);
    }
    *(_OWORD *)v37 = 0;
    v38 = 0;
    v39 = 0;
    memset_0(v45, 0, 0xD0u);
    v47 = 134218752;
    v46 = 1;
    v19 = (_QWORD *)std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v40, v44);
    if ( v19[3] > 7u )
      v19 = (_QWORD *)*v19;
    v20 = Src;
    if ( v43 > 7 )
      v20 = *(WCHAR **)Src;
    IsolatedProcess = CreateIsolatedProcess(
                        v20,
                        Microsoft::Diagnostics::UtcDecoderHostApiWrapper::k_utcDecoderHostIsolationContainerName,
                        Microsoft::Diagnostics::UtcDecoderHostApiWrapper::k_utcDecoderHostIsolationContainerName,
                        v19);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v44);
    if ( IsolatedProcess )
    {
      if ( !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
          v24);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v4,
        hObject[0]);
      v25 = 2000;
      if ( v29 )
        v25 = v29;
      if ( (unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                              &v31,
                              v25) )
      {
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v40);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
        return Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Bind((RPC_BINDING_HANDLE *)this);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
          (const char *)0x8000FFFFLL,
          (int)v37);
        if ( !TerminateProcess(*v4, 1u) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0xA9,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
            v26);
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v40);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
        return 2147549183LL;
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xA2,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
                    v22);
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v40);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
      (const char *)(unsigned int)v12,
      v28);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
    return v13;
  }
}

```

## disassembly

```asm
0x18009be24  mov     [rsp+arg_8], rbx
0x18009be29  mov     [rsp+arg_10], rsi
0x18009be2e  push    rdi
0x18009be2f  sub     rsp, 2D0h
0x18009be36  mov     rax, cs:__security_cookie
0x18009be3d  xor     rax, rsp
0x18009be40  mov     [rsp+2D8h+var_18], rax
0x18009be48  mov     bl, dl
0x18009be4a  mov     rdi, rcx
0x18009be4d  lea     rsi, [rcx+10h]
0x18009be51  mov     rcx, [rsi]; hHandle
0x18009be54  test    rcx, rcx
0x18009be57  jz      short loc_18009BE71
0x18009be59  xor     edx, edx; dwMilliseconds
0x18009be5b  call    cs:__imp_WaitForSingleObject
0x18009be62  nop     dword ptr [rax+rax+00h]
0x18009be67  cmp     eax, 102h
0x18009be6c  setz    al
0x18009be6f  jmp     short loc_18009BE73
0x18009be71  xor     al, al
0x18009be73  test    bl, bl
0x18009be75  jnz     short loc_18009BEA7
0x18009be77  test    al, al
0x18009be79  jz      loc_18009BF02
0x18009be7f  mov     rcx, [rsp+2D8h]; this
0x18009be87  mov     ebx, 8000FFFFh
0x18009be8c  mov     r9d, ebx; char *
0x18009be8f  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x18009be96  mov     edx, 60h ; '`'; void *
0x18009be9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009bea0  mov     eax, ebx
0x18009bea2  jmp     loc_18009C316
0x18009bea7  test    al, al
0x18009bea9  jz      short loc_18009BEDA
0x18009beab  mov     edx, 1; uExitCode
0x18009beb0  mov     rcx, [rsi]; hProcess
0x18009beb3  call    cs:__imp_TerminateProcess
0x18009beba  nop     dword ptr [rax+rax+00h]
0x18009bebf  mov     rcx, [rsp+2D8h]; this
0x18009bec7  test    eax, eax
0x18009bec9  jnz     short loc_18009BEDA
0x18009becb  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x18009bed2  lea     edx, [rax+66h]; void *
0x18009bed5  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18009beda  mov     rcx, rdi; this
0x18009bedd  call    ?Unbind@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Unbind(void)
0x18009bee2  mov     rcx, [rsp+2D8h]; this
0x18009beea  test    eax, eax
0x18009beec  jns     short loc_18009BF02
0x18009beee  mov     r9d, eax; char *
0x18009bef1  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x18009bef8  mov     edx, 68h ; 'h'; void *
0x18009befd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009bf02  mov     [rsp+2D8h+var_280], 18h
0x18009bf0b  mov     [rsp+2D8h+var_278], 0
0x18009bf14  mov     [rsp+2D8h+var_270], 1
0x18009bf1d  mov     [rsp+2D8h+var_288], 0
0x18009bf26  mov     qword ptr [rsp+2D8h+var_2B8], 0
0x18009bf2f  lea     r9, [rsp+2D8h+var_280]
0x18009bf34  xor     r8d, r8d
0x18009bf37  xor     edx, edx
0x18009bf39  lea     rcx, [rsp+2D8h+var_288]
0x18009bf3e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18009bf43  mov     [rsp+2D8h+var_278], 0
0x18009bf4c  mov     dword ptr [rsp+2D8h+var_270], 0
0x18009bf54  lea     rbx, [rdi+8]
0x18009bf58  cmp     qword ptr [rbx], 0
0x18009bf5c  jnz     short loc_18009BF79
0x18009bf5e  mov     qword ptr [rsp+2D8h+var_2B8], 0; int
0x18009bf67  lea     r9, [rsp+2D8h+var_280]
0x18009bf6c  xor     r8d, r8d
0x18009bf6f  xor     edx, edx
0x18009bf71  mov     rcx, rbx
0x18009bf74  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18009bf79  mov     qword ptr [rsp+2D8h+var_290], 0
0x18009bf82  xor     edx, edx
0x18009bf84  lea     rcx, [rsp+2D8h+var_290]
0x18009bf89  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18009bf8e  lea     r8, [rsp+2D8h+var_290]; unsigned int
0x18009bf93  mov     rcx, [rbx]; hSourceHandle
0x18009bf96  call    ?DuplicateInheritable@Diagnostics@Microsoft@@YAJPEAXKPEAPEAX@Z; Microsoft::Diagnostics::DuplicateInheritable(void *,ulong,void * *)
0x18009bf9b  mov     ebx, eax
0x18009bf9d  test    eax, eax
0x18009bf9f  jns     short loc_18009BFDA
0x18009bfa1  mov     rcx, [rsp+2D8h]; this
0x18009bfa9  mov     r9d, eax; char *
0x18009bfac  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x18009bfb3  mov     edx, 80h; void *
0x18009bfb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009bfbd  nop
0x18009bfbe  lea     rcx, [rsp+2D8h+var_290]
0x18009bfc3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009bfc8  nop
0x18009bfc9  lea     rcx, [rsp+2D8h+var_288]
0x18009bfce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009bfd3  mov     eax, ebx
0x18009bfd5  jmp     loc_18009C316
0x18009bfda  xorps   xmm0, xmm0
0x18009bfdd  xor     eax, eax
0x18009bfdf  movups  xmmword ptr [rsp+2D8h+hObject], xmm0
0x18009bfe4  mov     [rsp+2D8h+var_258], rax
0x18009bfec  lea     rdx, ?k_utcDecoderHostBinaryPath@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcDecoderHostApiWrapper::k_utcDecoderHostBinaryPath
0x18009bff3  lea     rcx, [rsp+2D8h+Src]
0x18009bffb  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18009c000  nop
0x18009c001  xor     r8d, r8d
0x18009c004  mov     dl, 1
0x18009c006  lea     rcx, [rsp+2D8h+Src]; lpSrc
0x18009c00e  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18009c013  lea     rcx, [rsp+2D8h+var_228]
0x18009c01b  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x18009c020  nop
0x18009c021  lea     rdx, [rsp+2D8h+Src]
0x18009c029  lea     rcx, [rsp+2D8h+var_218]
0x18009c031  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x18009c036  lea     rbx, asc_18039A33C; " "
0x18009c03d  mov     rdx, rbx
0x18009c040  mov     rcx, rax
0x18009c043  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18009c048  mov     rdx, [rsp+2D8h+var_288]
0x18009c04d  mov     rcx, rax
0x18009c050  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x18009c057  nop     dword ptr [rax+rax+00h]
0x18009c05c  mov     rdx, rbx
0x18009c05f  mov     rcx, rax
0x18009c062  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18009c067  mov     rdx, qword ptr [rsp+2D8h+var_290]
0x18009c06c  mov     rcx, rax
0x18009c06f  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x18009c076  nop     dword ptr [rax+rax+00h]
0x18009c07b  mov     [rsp+2D8h+var_298], 0
0x18009c083  movups  xmm0, xmmword ptr cs:off_1803692B0; "DecoderHostStartupDelay"
0x18009c08a  movdqu  [rsp+2D8h+var_108], xmm0
0x18009c093  lea     rdx, [rsp+2D8h+var_298]
0x18009c098  lea     rcx, [rsp+2D8h+var_108]
0x18009c0a0  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAK@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view,ulong &)
0x18009c0a5  test    al, al
0x18009c0a7  jz      short loc_18009C0CC
0x18009c0a9  mov     rdx, rbx
0x18009c0ac  lea     rcx, [rsp+2D8h+var_218]
0x18009c0b4  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18009c0b9  mov     edx, [rsp+2D8h+var_298]
0x18009c0bd  mov     rcx, rax
0x18009c0c0  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x18009c0c7  nop     dword ptr [rax+rax+00h]
0x18009c0cc  xorps   xmm0, xmm0
0x18009c0cf  xor     eax, eax
0x18009c0d1  movups  xmmword ptr [rsp+2D8h+var_250], xmm0
0x18009c0d9  movups  [rsp+2D8h+var_240], xmm0
0x18009c0e1  mov     [rsp+2D8h+var_230], rax
0x18009c0e9  xor     edx, edx; Val
0x18009c0eb  mov     r8d, 0D0h; Size
0x18009c0f1  lea     rcx, [rsp+2D8h+var_E8]; void *
0x18009c0f9  call    memset_0
0x18009c0fe  mov     [rsp+2D8h+var_9C], 8000400h
0x18009c109  mov     [rsp+2D8h+var_A0], 1
0x18009c114  lea     rdx, [rsp+2D8h+var_108]
0x18009c11c  lea     rcx, [rsp+2D8h+var_228]
0x18009c124  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x18009c129  cmp     qword ptr [rax+18h], 7
0x18009c12e  jbe     short loc_18009C133
0x18009c130  mov     rax, [rax]
0x18009c133  mov     rdx, cs:?k_utcDecoderHostIsolationContainerName@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcDecoderHostApiWrapper::k_utcDecoderHostIsolationContainerName
0x18009c13a  lea     rcx, [rsp+2D8h+Src]
0x18009c142  cmp     [rsp+2D8h+var_110], 7
0x18009c14b  cmova   rcx, qword ptr [rsp+2D8h+Src]
0x18009c154  lea     r8, [rsp+2D8h+hObject]
0x18009c159  mov     [rsp+2D8h+var_2A8], r8
0x18009c15e  lea     r8, [rsp+2D8h+var_E8]
0x18009c166  mov     [rsp+2D8h+var_2B0], r8
0x18009c16b  lea     r8, [rsp+2D8h+var_250]
0x18009c173  mov     qword ptr [rsp+2D8h+var_2B8], r8; int
0x18009c178  mov     r9, rax
0x18009c17b  mov     r8, rdx
0x18009c17e  call    cs:__imp_CreateIsolatedProcess
0x18009c185  nop     dword ptr [rax+rax+00h]
0x18009c18a  mov     ebx, eax
0x18009c18c  lea     rcx, [rsp+2D8h+var_108]; this
0x18009c194  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18009c199  test    ebx, ebx
0x18009c19b  jnz     short loc_18009C1F0
0x18009c19d  mov     rcx, [rsp+2D8h]; this
0x18009c1a5  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x18009c1ac  mov     edx, 0A2h; void *
0x18009c1b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009c1b6  mov     ebx, eax
0x18009c1b8  lea     rcx, [rsp+2D8h+var_228]
0x18009c1c0  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x18009c1c5  nop
0x18009c1c6  lea     rcx, [rsp+2D8h+Src]; this
0x18009c1ce  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18009c1d3  nop
0x18009c1d4  lea     rcx, [rsp+2D8h+var_290]
0x18009c1d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009c1de  nop
0x18009c1df  lea     rcx, [rsp+2D8h+var_288]
0x18009c1e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009c1e9  mov     eax, ebx
0x18009c1eb  jmp     loc_18009C316
0x18009c1f0  mov     rbx, [rsp+2D8h]
0x18009c1f8  mov     rcx, [rsp+2D8h+hObject+8]; hObject
0x18009c1fd  call    cs:__imp_CloseHandle
0x18009c204  nop     dword ptr [rax+rax+00h]
0x18009c209  test    eax, eax
0x18009c20b  jnz     short loc_18009C221
0x18009c20d  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x18009c214  mov     edx, 0A4h; void *
0x18009c219  mov     rcx, rbx; this
0x18009c21c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18009c221  mov     rdx, [rsp+2D8h+hObject]
0x18009c226  mov     rcx, rsi
0x18009c229  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009c22e  mov     edx, 7D0h
0x18009c233  mov     eax, [rsp+2D8h+var_298]
0x18009c237  test    eax, eax
0x18009c239  cmovnz  edx, eax
0x18009c23c  lea     rcx, [rsp+2D8h+var_288]
0x18009c241  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x18009c246  test    al, al
0x18009c248  jnz     loc_18009C2D6
0x18009c24e  mov     rcx, [rsp+2D8h]; this
0x18009c256  mov     ebx, 8000FFFFh
0x18009c25b  mov     r9d, ebx; char *
0x18009c25e  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x18009c265  mov     edx, 0ADh; void *
0x18009c26a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c26f  mov     edx, 1; uExitCode
0x18009c274  mov     rcx, [rsi]; hProcess
0x18009c277  call    cs:__imp_TerminateProcess
0x18009c27e  nop     dword ptr [rax+rax+00h]
0x18009c283  mov     rcx, [rsp+2D8h]; this
0x18009c28b  test    eax, eax
0x18009c28d  jnz     short loc_18009C2A1
0x18009c28f  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x18009c296  mov     edx, 0A9h; void *
0x18009c29b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18009c2a0  nop
0x18009c2a1  lea     rcx, [rsp+2D8h+var_228]
0x18009c2a9  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x18009c2ae  nop
0x18009c2af  lea     rcx, [rsp+2D8h+Src]; this
0x18009c2b7  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18009c2bc  nop
0x18009c2bd  lea     rcx, [rsp+2D8h+var_290]
0x18009c2c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009c2c7  nop
0x18009c2c8  lea     rcx, [rsp+2D8h+var_288]
0x18009c2cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009c2d2  mov     eax, ebx
0x18009c2d4  jmp     short loc_18009C316
0x18009c2d6  lea     rcx, [rsp+2D8h+var_228]
0x18009c2de  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x18009c2e3  nop
0x18009c2e4  lea     rcx, [rsp+2D8h+Src]; this
0x18009c2ec  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18009c2f1  nop
0x18009c2f2  lea     rcx, [rsp+2D8h+var_290]
0x18009c2f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009c2fc  nop
0x18009c2fd  lea     rcx, [rsp+2D8h+var_288]
0x18009c302  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009c307  nop
0x18009c308  mov     rcx, rdi; Binding
0x18009c30b  call    ?Bind@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Bind(void)
0x18009c310  jmp     short loc_18009C316
0x18009c312  mov     eax, [rsp+2D8h+var_298]
0x18009c316  mov     rcx, [rsp+2D8h+var_18]
0x18009c31e  xor     rcx, rsp; StackCookie
0x18009c321  call    __security_check_cookie
0x18009c326  lea     r11, [rsp+2D8h+var_8]
0x18009c32e  mov     rbx, [r11+18h]
0x18009c332  mov     rsi, [r11+20h]
0x18009c336  mov     rsp, r11
0x18009c339  pop     rdi
0x18009c33a  retn
```
