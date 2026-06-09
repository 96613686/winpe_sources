# winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::EnsureRecordDefaultProperties(void)

- ea: `0x18014924c`
- end: `0x180149509`
- name: `?EnsureRecordDefaultProperties@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@AEAAXXZ`
- size: `701`
- prototype: `void __fastcall(winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800dffc8`
- `0x18045e528`
- `0x18045e5fc`
- `0x18045ef88`

## callees

- `0x180025264`
- `0x180025348`
- `0x180026860`
- `0x180137f7c`
- `0x18014924c`
- `0x180149510`
- `0x1801495b0`
- `0x1801496c8`
- `0x1801588c4`
- `0x18015cb00`
- `0x18015d868`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180149330`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180149330`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180149284`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18014937e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180149284`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18014937e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1801493c4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1801493c4`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1801492ad`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1801492ad`

## string_xrefs

- `0x18014931f`: `shellcommon\undockeddevkit\libs\windowsudk.web.webview2\sharedwebviewenvironmentmanager.cpp`
- `0x1801493d5`: `shellcommon\undockeddevkit\libs\windowsudk.web.webview2\sharedwebviewenvironmentmanager.cpp`
- `0x180149338`: `ProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::EnsureRecordDefaultProperties(
        winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager *this)
{
  HANDLE CurrentProcess; // rbx
  const char *v3; // r9
  __int64 v4; // rbx
  const WCHAR *InstanceInfoPath; // rax
  __int64 v6; // rcx
  DWORD CurrentProcessId; // ebx
  const WCHAR *v8; // rax
  __int64 v9; // rcx
  HANDLE v10; // rax
  const char *v11; // r9
  const WCHAR *v12; // rax
  __int64 v13; // rcx
  const WCHAR *v14; // rax
  __int64 v15; // rcx
  const wchar_t *v16; // rax
  __int64 v17; // rbx
  const WCHAR *v18; // rax
  __int64 v19; // rcx
  struct _FILETIME CreationTime; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME ExitTime; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME UserTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME KernelTime; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR v24[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR BaseName[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  if ( !*((_BYTE *)this + 112) )
  {
    CurrentProcess = GetCurrentProcess();
    memset_0(BaseName, 0, 0x208u);
    if ( K32GetModuleBaseNameW(CurrentProcess, 0, BaseName, 0x104u) )
    {
      ExitTime = (struct _FILETIME)v26;
      v4 = std::wstring::wstring(v26, BaseName);
      std::wstring::wstring(v24, L"ProcessName");
      InstanceInfoPath = (const WCHAR *)winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(
                                          this,
                                          v25);
      RegistryHelpers::SetVolatileRegistryKeyStringValue(v6, InstanceInfoPath, v24, v4);
      std::filesystem::path::~path((std::filesystem::path *)v25);
      std::filesystem::path::~path((std::filesystem::path *)v24);
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x306,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.web.webview2\\sharedwebviewenvironmentmanager.cpp",
        v3);
    }
    CurrentProcessId = GetCurrentProcessId();
    std::wstring::wstring(v24, L"ProcessId");
    v8 = (const WCHAR *)winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(
                          this,
                          v25);
    RegistryHelpers::SetVolatileRegistryKeyDWORDValue(v9, v8, v24, CurrentProcessId);
    std::filesystem::path::~path((std::filesystem::path *)v25);
    std::filesystem::path::~path((std::filesystem::path *)v24);
    v10 = GetCurrentProcess();
    CreationTime = 0;
    ExitTime = 0;
    KernelTime = 0;
    UserTime = 0;
    if ( !GetProcessTimes(v10, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB5,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.web.webview2\\sharedwebviewenvironmentmanager.cpp",
        v11);
    std::wstring::wstring(v24, L"ProcessStartTimeLow");
    v12 = (const WCHAR *)winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(
                           this,
                           v25);
    RegistryHelpers::SetVolatileRegistryKeyDWORDValue(v13, v12, v24, CreationTime.dwLowDateTime);
    std::filesystem::path::~path((std::filesystem::path *)v25);
    std::filesystem::path::~path((std::filesystem::path *)v24);
    std::wstring::wstring(v24, L"ProcessStartTimeHigh");
    v14 = (const WCHAR *)winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(
                           this,
                           v25);
    RegistryHelpers::SetVolatileRegistryKeyDWORDValue(v15, v14, v24, CreationTime.dwHighDateTime);
    std::filesystem::path::~path((std::filesystem::path *)v25);
    std::filesystem::path::~path((std::filesystem::path *)v24);
    ExitTime = (struct _FILETIME)v25;
    v16 = winrt::hstring::c_str((winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager *)((char *)this + 152));
    v17 = std::wstring::wstring(v25, v16);
    std::wstring::wstring(v24, L"Identity");
    v18 = (const WCHAR *)winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(
                           this,
                           v26);
    RegistryHelpers::SetVolatileRegistryKeyStringValue(v19, v18, v24, v17);
    std::filesystem::path::~path((std::filesystem::path *)v26);
    std::filesystem::path::~path((std::filesystem::path *)v24);
    *((_BYTE *)this + 112) = 1;
  }
}

```

## disassembly

```asm
0x18014924c  mov     [rsp-8+arg_8], rbx
0x180149251  mov     [rsp-8+arg_10], rdi
0x180149256  push    rbp
0x180149257  lea     rbp, [rsp-1D0h]
0x18014925f  sub     rsp, 2D0h
0x180149266  mov     rax, cs:__security_cookie
0x18014926d  xor     rax, rsp
0x180149270  mov     [rbp+1D0h+var_10], rax
0x180149277  mov     rdi, rcx
0x18014927a  cmp     byte ptr [rcx+70h], 0
0x18014927e  jnz     loc_1801494E5
0x180149284  call    cs:__imp_GetCurrentProcess
0x18014928a  mov     rbx, rax
0x18014928d  xor     edx, edx; Val
0x18014928f  mov     r8d, 208h; Size
0x180149295  lea     rcx, [rbp+1D0h+BaseName]; void *
0x180149299  call    memset_0
0x18014929e  mov     r9d, 104h; nSize
0x1801492a4  lea     r8, [rbp+1D0h+BaseName]; lpBaseName
0x1801492a8  xor     edx, edx; hModule
0x1801492aa  mov     rcx, rbx; hProcess
0x1801492ad  call    cs:__imp_K32GetModuleBaseNameW
0x1801492b3  test    eax, eax
0x1801492b5  jz      short loc_180149318
0x1801492b7  lea     rax, [rbp+1D0h+var_240]
0x1801492bb  mov     qword ptr [rsp+2D0h+ExitTime.dwLowDateTime], rax
0x1801492c0  lea     rdx, [rbp+1D0h+BaseName]
0x1801492c4  lea     rcx, [rbp+1D0h+var_240]
0x1801492c8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801492cd  mov     rbx, rax
0x1801492d0  lea     rdx, aProcessname; "ProcessName"
0x1801492d7  lea     rcx, [rsp+2D0h+var_280]
0x1801492dc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801492e1  nop
0x1801492e2  lea     rdx, [rsp+2D0h+var_260]
0x1801492e7  mov     rcx, rdi
0x1801492ea  call    ?GetInstanceInfoPath@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(void)
0x1801492ef  nop
0x1801492f0  mov     r9, rbx
0x1801492f3  lea     r8, [rsp+2D0h+var_280]
0x1801492f8  mov     rdx, rax
0x1801492fb  call    RegistryHelpers__SetVolatileRegistryKeyStringValue
0x180149300  nop
0x180149301  lea     rcx, [rsp+2D0h+var_260]; this
0x180149306  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18014930b  nop
0x18014930c  lea     rcx, [rsp+2D0h+var_280]; this
0x180149311  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180149316  jmp     short loc_180149330
0x180149318  mov     rcx, [rbp+1D8h]; this
0x18014931f  lea     r8, aShellcommonUnd_123; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180149326  mov     edx, 306h; void *
0x18014932b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180149330  call    cs:__imp_GetCurrentProcessId
0x180149336  mov     ebx, eax
0x180149338  lea     rdx, aProcessid; "ProcessId"
0x18014933f  lea     rcx, [rsp+2D0h+var_280]
0x180149344  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180149349  nop
0x18014934a  lea     rdx, [rsp+2D0h+var_260]
0x18014934f  mov     rcx, rdi
0x180149352  call    ?GetInstanceInfoPath@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(void)
0x180149357  nop
0x180149358  mov     r9d, ebx
0x18014935b  lea     r8, [rsp+2D0h+var_280]
0x180149360  mov     rdx, rax
0x180149363  call    RegistryHelpers__SetVolatileRegistryKeyDWORDValue
0x180149368  nop
0x180149369  lea     rcx, [rsp+2D0h+var_260]; this
0x18014936e  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180149373  nop
0x180149374  lea     rcx, [rsp+2D0h+var_280]; this
0x180149379  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18014937e  call    cs:__imp_GetCurrentProcess
0x180149384  mov     qword ptr [rsp+2D0h+CreationTime.dwLowDateTime], 0
0x18014938d  mov     qword ptr [rsp+2D0h+ExitTime.dwLowDateTime], 0
0x180149396  mov     qword ptr [rsp+2D0h+KernelTime.dwLowDateTime], 0
0x18014939f  mov     qword ptr [rsp+2D0h+UserTime.dwLowDateTime], 0
0x1801493a8  lea     rcx, [rsp+2D0h+UserTime]
0x1801493ad  mov     [rsp+2D0h+lpUserTime], rcx; lpUserTime
0x1801493b2  lea     r9, [rsp+2D0h+KernelTime]; lpKernelTime
0x1801493b7  lea     r8, [rsp+2D0h+ExitTime]; lpExitTime
0x1801493bc  lea     rdx, [rsp+2D0h+CreationTime]; lpCreationTime
0x1801493c1  mov     rcx, rax; hProcess
0x1801493c4  call    cs:__imp_GetProcessTimes
0x1801493ca  mov     rcx, [rbp+1D8h]; this
0x1801493d1  test    eax, eax
0x1801493d3  jnz     short loc_1801493E7
0x1801493d5  lea     r8, aShellcommonUnd_123; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1801493dc  mov     edx, 0B5h; void *
0x1801493e1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801493e7  lea     rdx, aProcessstartti_0; "ProcessStartTimeLow"
0x1801493ee  lea     rcx, [rsp+2D0h+var_280]
0x1801493f3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801493f8  nop
0x1801493f9  lea     rdx, [rsp+2D0h+var_260]
0x1801493fe  mov     rcx, rdi
0x180149401  call    ?GetInstanceInfoPath@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(void)
0x180149406  nop
0x180149407  mov     r9d, [rsp+2D0h+CreationTime.dwLowDateTime]
0x18014940c  lea     r8, [rsp+2D0h+var_280]
0x180149411  mov     rdx, rax
0x180149414  call    RegistryHelpers__SetVolatileRegistryKeyDWORDValue
0x180149419  nop
0x18014941a  lea     rcx, [rsp+2D0h+var_260]; this
0x18014941f  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180149424  nop
0x180149425  lea     rcx, [rsp+2D0h+var_280]; this
0x18014942a  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18014942f  lea     rdx, aProcessstartti; "ProcessStartTimeHigh"
0x180149436  lea     rcx, [rsp+2D0h+var_280]
0x18014943b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180149440  nop
0x180149441  lea     rdx, [rsp+2D0h+var_260]
0x180149446  mov     rcx, rdi
0x180149449  call    ?GetInstanceInfoPath@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(void)
0x18014944e  nop
0x18014944f  mov     r9d, [rsp+2D0h+CreationTime.dwHighDateTime]
0x180149454  lea     r8, [rsp+2D0h+var_280]
0x180149459  mov     rdx, rax
0x18014945c  call    RegistryHelpers__SetVolatileRegistryKeyDWORDValue
0x180149461  nop
0x180149462  lea     rcx, [rsp+2D0h+var_260]; this
0x180149467  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18014946c  nop
0x18014946d  lea     rcx, [rsp+2D0h+var_280]; this
0x180149472  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180149477  lea     rax, [rsp+2D0h+var_260]
0x18014947c  mov     qword ptr [rsp+2D0h+ExitTime.dwLowDateTime], rax
0x180149481  lea     rcx, [rdi+98h]; this
0x180149488  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18014948d  mov     rdx, rax
0x180149490  lea     rcx, [rsp+2D0h+var_260]
0x180149495  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18014949a  mov     rbx, rax
0x18014949d  lea     rdx, aIdentity; "Identity"
0x1801494a4  lea     rcx, [rsp+2D0h+var_280]
0x1801494a9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801494ae  nop
0x1801494af  lea     rdx, [rbp+1D0h+var_240]
0x1801494b3  mov     rcx, rdi
0x1801494b6  call    ?GetInstanceInfoPath@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::GetInstanceInfoPath(void)
0x1801494bb  nop
0x1801494bc  mov     r9, rbx
0x1801494bf  lea     r8, [rsp+2D0h+var_280]
0x1801494c4  mov     rdx, rax
0x1801494c7  call    RegistryHelpers__SetVolatileRegistryKeyStringValue
0x1801494cc  nop
0x1801494cd  lea     rcx, [rbp+1D0h+var_240]; this
0x1801494d1  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1801494d6  nop
0x1801494d7  lea     rcx, [rsp+2D0h+var_280]; this
0x1801494dc  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1801494e1  mov     byte ptr [rdi+70h], 1
0x1801494e5  mov     rcx, [rbp+1D0h+var_10]
0x1801494ec  xor     rcx, rsp; StackCookie
0x1801494ef  call    __security_check_cookie
0x1801494f4  lea     r11, [rsp+2D0h+var_s0]
0x1801494fc  mov     rbx, [r11+18h]
0x180149500  mov     rdi, [r11+20h]
0x180149504  mov     rsp, r11
0x180149507  pop     rbp
0x180149508  retn
```
