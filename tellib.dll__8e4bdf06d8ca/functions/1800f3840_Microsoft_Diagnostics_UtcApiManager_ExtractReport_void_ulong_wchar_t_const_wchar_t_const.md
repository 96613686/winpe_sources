# Microsoft::Diagnostics::UtcApiManager::ExtractReport(void *,ulong,wchar_t const *,wchar_t const *)

- ea: `0x1800f3840`
- end: `0x1800f3b78`
- name: `?ExtractReport@UtcApiManager@Diagnostics@Microsoft@@UEAAJPEAXKPEB_W1@Z`
- size: `824`
- prototype: `int(Microsoft::Diagnostics::UtcApiManager *__hidden this, void *, unsigned int, const wchar_t *, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180026ecc`
- `0x180034d94`
- `0x1800f3840`
- `0x1800f3b80`
- `0x1800f3ba8`
- `0x18015f810`
- `0x1801deafc`
- `0x1801e3e2c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f38e9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f3976`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f3a1d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f3ab3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f3b0b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f38e9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f3976`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f3a1d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f3ab3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f3b0b`
- `ext-ms-win-wer-reporting-l1-1-1!WerStoreOpen` at `0x1800f3932`
- `ext-ms-win-wer-reporting-l1-1-1!WerStoreOpen` at `0x1800f3932`
- `wer!WerpExtractReportFiles` at `0x1800f3a65`
- `wer!WerpExtractReportFiles` at `0x1800f3a65`
- `wer!WerpLoadReport` at `0x1800f39cf`
- `wer!WerpLoadReport` at `0x1800f39cf`

## string_xrefs

- `0x1800f3869`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f38c9`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f38fe`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f394c`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f398b`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f39e9`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f3a32`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f3a7f`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f3ac8`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f3b20`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1800f3b4d`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::ExtractReport(
        Microsoft::Diagnostics::UtcApiManager *this,
        void *a2,
        REPORT_STORE_TYPES a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  int ApiSession; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  int v12; // eax
  unsigned int v13; // ebx
  const char *v14; // r9
  HRESULT v15; // eax
  const char *v16; // r9
  int Report; // eax
  const char *v18; // r9
  int ReportFiles; // eax
  const char *v20; // r9
  const char *v21; // r9
  int v22; // [rsp+20h] [rbp-48h]
  __int64 v23; // [rsp+30h] [rbp-38h] BYREF
  PVOID phReportStore; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-28h] BYREF
  char v26; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    ApiSession = Microsoft::Diagnostics::UtcApiManager::ValidateDiagnosticDataQueryApiSession(this, a2);
    v9 = ApiSession;
    if ( ApiSession < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14DD,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)ApiSession,
        v22);
      return v9;
    }
    if ( a4 && a5 )
    {
      v23 = 0;
      v25[1] = &v23;
      v26 = 1;
      v12 = Microsoft::Diagnostics::UtcApiManager::ImpersonateIfNonAdmin(v8, &v23);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14F6,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)(unsigned int)v12,
          v22);
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x14F2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            v14);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
        return v13;
      }
      phReportStore = 0;
      v15 = WerStoreOpen(a3, &phReportStore);
      v13 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14F9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)(unsigned int)v15,
          v22);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportStore);
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x14F2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            v16);
        goto LABEL_22;
      }
      v25[0] = 0;
      Report = WerpLoadReport(phReportStore, a4, v25, 0);
      v13 = Report;
      if ( Report < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14FC,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)(unsigned int)Report,
          0);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v25);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportStore);
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x14F2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            v18);
        goto LABEL_22;
      }
      ReportFiles = WerpExtractReportFiles(v25[0], a5, 0);
      v13 = ReportFiles;
      if ( ReportFiles < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14FD,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)(unsigned int)ReportFiles,
          0);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v25);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportStore);
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x14F2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            v20);
        goto LABEL_22;
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v25);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportStore);
      if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x14F2,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          v21);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14E1,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)0x80070057LL,
        v22);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1501,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800f3840  mov     [rsp+arg_0], rbx
0x1800f3845  mov     [rsp+arg_8], rsi
0x1800f384a  push    r14
0x1800f384c  sub     rsp, 60h
0x1800f3850  mov     rsi, r9
0x1800f3853  mov     r14d, r8d
0x1800f3856  call    ?ValidateDiagnosticDataQueryApiSession@UtcApiManager@Diagnostics@Microsoft@@AEAAJQEAX@Z; Microsoft::Diagnostics::UtcApiManager::ValidateDiagnosticDataQueryApiSession(void * const)
0x1800f385b  mov     ebx, eax
0x1800f385d  test    eax, eax
0x1800f385f  jns     short loc_1800F3881
0x1800f3861  mov     rcx, [rsp+68h]; this
0x1800f3866  mov     r9d, eax; char *
0x1800f3869  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f3870  mov     edx, 14DDh; void *
0x1800f3875  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f387a  mov     eax, ebx
0x1800f387c  jmp     loc_1800F3B66
0x1800f3881  test    rsi, rsi
0x1800f3884  jz      loc_1800F3B40
0x1800f388a  cmp     [rsp+68h+arg_20], 0
0x1800f3893  jz      loc_1800F3B40
0x1800f3899  mov     [rsp+68h+var_38], 0
0x1800f38a2  lea     rax, [rsp+68h+var_38]
0x1800f38a7  mov     [rsp+68h+var_20], rax
0x1800f38ac  mov     [rsp+68h+var_18], 1
0x1800f38b1  lea     rdx, [rsp+68h+var_38]
0x1800f38b6  call    ?ImpersonateIfNonAdmin@UtcApiManager@Diagnostics@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Diagnostics::UtcApiManager::ImpersonateIfNonAdmin(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1800f38bb  mov     ebx, eax
0x1800f38bd  test    eax, eax
0x1800f38bf  jns     short loc_1800F3921
0x1800f38c1  mov     rcx, [rsp+68h]; this
0x1800f38c6  mov     r9d, eax; char *
0x1800f38c9  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f38d0  mov     edx, 14F6h; void *
0x1800f38d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f38da  nop
0x1800f38db  mov     rcx, [rsp+68h+var_38]
0x1800f38e0  dec     rcx
0x1800f38e3  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800f38e7  ja      short loc_1800F3910
0x1800f38e9  call    cs:__imp_RevertToSelf
0x1800f38f0  nop     dword ptr [rax+rax+00h]
0x1800f38f5  mov     rcx, [rsp+68h]; this
0x1800f38fa  test    eax, eax
0x1800f38fc  jnz     short loc_1800F3910
0x1800f38fe  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f3905  mov     edx, 14F2h; void *
0x1800f390a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f3910  lea     rcx, [rsp+68h+var_38]
0x1800f3915  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f391a  mov     eax, ebx
0x1800f391c  jmp     loc_1800F3B66
0x1800f3921  mov     [rsp+68h+phReportStore], 0
0x1800f392a  lea     rdx, [rsp+68h+phReportStore]; phReportStore
0x1800f392f  mov     ecx, r14d; repStoreType
0x1800f3932  call    cs:__imp_WerStoreOpen
0x1800f3939  nop     dword ptr [rax+rax+00h]
0x1800f393e  mov     ebx, eax
0x1800f3940  test    eax, eax
0x1800f3942  jns     short loc_1800F39AE
0x1800f3944  mov     rcx, [rsp+68h]; this
0x1800f3949  mov     r9d, eax; char *
0x1800f394c  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f3953  mov     edx, 14F9h; void *
0x1800f3958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f395d  lea     rcx, [rsp+68h+phReportStore]
0x1800f3962  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?WerStoreClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f3967  nop
0x1800f3968  mov     rcx, [rsp+68h+var_38]
0x1800f396d  dec     rcx
0x1800f3970  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800f3974  ja      short loc_1800F399D
0x1800f3976  call    cs:__imp_RevertToSelf
0x1800f397d  nop     dword ptr [rax+rax+00h]
0x1800f3982  mov     rcx, [rsp+68h]; this
0x1800f3987  test    eax, eax
0x1800f3989  jnz     short loc_1800F399D
0x1800f398b  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f3992  mov     edx, 14F2h; void *
0x1800f3997  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f399d  lea     rcx, [rsp+68h+var_38]
0x1800f39a2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f39a7  mov     eax, ebx
0x1800f39a9  jmp     loc_1800F3B66
0x1800f39ae  mov     [rsp+68h+var_28], 0
0x1800f39b7  mov     [rsp+68h+var_48], 0; int
0x1800f39bf  xor     r9d, r9d
0x1800f39c2  lea     r8, [rsp+68h+var_28]
0x1800f39c7  mov     rdx, rsi
0x1800f39ca  mov     rcx, [rsp+68h+phReportStore]
0x1800f39cf  call    cs:__imp_WerpLoadReport
0x1800f39d6  nop     dword ptr [rax+rax+00h]
0x1800f39db  mov     ebx, eax
0x1800f39dd  test    eax, eax
0x1800f39df  jns     short loc_1800F3A55
0x1800f39e1  mov     rcx, [rsp+68h]; this
0x1800f39e6  mov     r9d, eax; char *
0x1800f39e9  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f39f0  mov     edx, 14FCh; void *
0x1800f39f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f39fa  lea     rcx, [rsp+68h+var_28]
0x1800f39ff  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f3a04  lea     rcx, [rsp+68h+phReportStore]
0x1800f3a09  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?WerStoreClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f3a0e  nop
0x1800f3a0f  mov     rax, [rsp+68h+var_38]
0x1800f3a14  dec     rax
0x1800f3a17  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f3a1b  ja      short loc_1800F3A44
0x1800f3a1d  call    cs:__imp_RevertToSelf
0x1800f3a24  nop     dword ptr [rax+rax+00h]
0x1800f3a29  mov     rcx, [rsp+68h]; this
0x1800f3a2e  test    eax, eax
0x1800f3a30  jnz     short loc_1800F3A44
0x1800f3a32  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f3a39  mov     edx, 14F2h; void *
0x1800f3a3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f3a44  lea     rcx, [rsp+68h+var_38]
0x1800f3a49  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f3a4e  mov     eax, ebx
0x1800f3a50  jmp     loc_1800F3B66
0x1800f3a55  xor     r8d, r8d
0x1800f3a58  mov     rdx, [rsp+68h+arg_20]
0x1800f3a60  mov     rcx, [rsp+68h+var_28]
0x1800f3a65  call    cs:__imp_WerpExtractReportFiles
0x1800f3a6c  nop     dword ptr [rax+rax+00h]
0x1800f3a71  mov     ebx, eax
0x1800f3a73  test    eax, eax
0x1800f3a75  jns     short loc_1800F3AE8
0x1800f3a77  mov     rcx, [rsp+68h]; this
0x1800f3a7c  mov     r9d, eax; char *
0x1800f3a7f  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f3a86  mov     edx, 14FDh; void *
0x1800f3a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3a90  lea     rcx, [rsp+68h+var_28]
0x1800f3a95  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f3a9a  lea     rcx, [rsp+68h+phReportStore]
0x1800f3a9f  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?WerStoreClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f3aa4  nop
0x1800f3aa5  mov     rax, [rsp+68h+var_38]
0x1800f3aaa  dec     rax
0x1800f3aad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f3ab1  ja      short loc_1800F3ADA
0x1800f3ab3  call    cs:__imp_RevertToSelf
0x1800f3aba  nop     dword ptr [rax+rax+00h]
0x1800f3abf  mov     rcx, [rsp+68h]; this
0x1800f3ac4  test    eax, eax
0x1800f3ac6  jnz     short loc_1800F3ADA
0x1800f3ac8  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f3acf  mov     edx, 14F2h; void *
0x1800f3ad4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f3ada  lea     rcx, [rsp+68h+var_38]
0x1800f3adf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f3ae4  mov     eax, ebx
0x1800f3ae6  jmp     short loc_1800F3B66
0x1800f3ae8  lea     rcx, [rsp+68h+var_28]
0x1800f3aed  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f3af2  lea     rcx, [rsp+68h+phReportStore]
0x1800f3af7  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?WerStoreClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f3afc  nop
0x1800f3afd  mov     rax, [rsp+68h+var_38]
0x1800f3b02  dec     rax
0x1800f3b05  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f3b09  ja      short loc_1800F3B32
0x1800f3b0b  call    cs:__imp_RevertToSelf
0x1800f3b12  nop     dword ptr [rax+rax+00h]
0x1800f3b17  mov     rcx, [rsp+68h]; this
0x1800f3b1c  test    eax, eax
0x1800f3b1e  jnz     short loc_1800F3B32
0x1800f3b20  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f3b27  mov     edx, 14F2h; void *
0x1800f3b2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f3b32  lea     rcx, [rsp+68h+var_38]
0x1800f3b37  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f3b3c  xor     eax, eax
0x1800f3b3e  jmp     short loc_1800F3B66
0x1800f3b40  mov     rcx, [rsp+68h]; this
0x1800f3b45  mov     ebx, 80070057h
0x1800f3b4a  mov     r9d, ebx; char *
0x1800f3b4d  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1800f3b54  mov     edx, 14E1h; void *
0x1800f3b59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3b5e  mov     eax, ebx
0x1800f3b60  jmp     short loc_1800F3B66
0x1800f3b62  mov     eax, dword ptr [rsp+68h+var_38]
0x1800f3b66  mov     rbx, [rsp+68h+arg_0]
0x1800f3b6b  mov     rsi, [rsp+68h+arg_8]
0x1800f3b70  add     rsp, 60h
0x1800f3b74  pop     r14
0x1800f3b76  retn
```
