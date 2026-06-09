# IsValidWebViewKey(HKEY__ *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x18045dfcc`
- end: `0x18045e28c`
- name: `?IsValidWebViewKey@@YA_NPEAUHKEY__@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18045cb3c`

## callees

- `0x180025264`
- `0x180026860`
- `0x18007abb0`
- `0x180130a98`
- `0x18015cb00`
- `0x18045dbd8`
- `0x18045dfcc`
- `0x18045f5c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18045e18d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18045e18d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18045e125`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18045e125`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18045e224`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18045e224`

## string_xrefs

- `0x18045e001`: `ProcessId`
- `0x18045e0ed`: `ProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall IsValidWebViewKey(HKEY hKey, WCHAR *lpSubKey)
{
  WCHAR *v2; // rdi
  char v4; // bl
  bool v5; // r14
  DWORD VolatileRegistryKeyDWORDValue; // ebx
  HANDLE v7; // rdx
  void *v8; // rcx
  BOOL ProcessTimes; // eax
  bool v10; // bl
  const char *v11; // r9
  bool result; // al
  struct _FILETIME ExitTime; // [rsp+30h] [rbp-B8h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-B0h] BYREF
  struct _FILETIME CreationTime; // [rsp+40h] [rbp-A8h] BYREF
  struct _FILETIME UserTime; // [rsp+48h] [rbp-A0h] BYREF
  struct _FILETIME KernelTime; // [rsp+50h] [rbp-98h] BYREF
  LPCWSTR v18; // [rsp+58h] [rbp-90h]
  WCHAR ValueName[16]; // [rsp+60h] [rbp-88h] BYREF
  _QWORD v20[4]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v21[32]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v2 = lpSubKey;
  v18 = lpSubKey;
  std::wstring::wstring(ValueName, L"ProcessId");
  v4 = 1;
  ExitTime.dwLowDateTime = 1;
  v5 = 0;
  if ( (unsigned __int8)RegistryHelpers::VolatileRegistryKeyValueExists(hKey, v2) )
  {
    std::wstring::wstring(v21, L"ProcessStartTimeLow");
    v4 = 3;
    ExitTime.dwLowDateTime = 3;
    if ( (unsigned __int8)RegistryHelpers::VolatileRegistryKeyValueExists(hKey, v2) )
    {
      std::wstring::wstring(v20, L"ProcessStartTimeHigh");
      v4 = 7;
      if ( (unsigned __int8)RegistryHelpers::VolatileRegistryKeyValueExists(hKey, v2) )
        v5 = 1;
    }
  }
  if ( (v4 & 4) != 0 )
  {
    v4 &= ~4u;
    std::filesystem::path::~path((std::filesystem::path *)v20);
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    std::filesystem::path::~path((std::filesystem::path *)v21);
  }
  if ( (v4 & 1) != 0 )
    std::filesystem::path::~path((std::filesystem::path *)ValueName);
  if ( !v5 )
    goto LABEL_20;
  std::wstring::wstring(ValueName, L"ProcessId");
  VolatileRegistryKeyDWORDValue = RegistryHelpers::GetVolatileRegistryKeyDWORDValue(hKey, v2, ValueName);
  std::filesystem::path::~path((std::filesystem::path *)ValueName);
  v7 = OpenProcess(0x1000u, 0, VolatileRegistryKeyDWORDValue);
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
    v20,
    v7);
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  if ( v20[0] )
    v8 = *(void **)v20[0];
  else
    v8 = 0;
  ProcessTimes = GetProcessTimes(v8, &CreationTime, &ExitTime, &KernelTime, &UserTime);
  if ( !ProcessTimes || ExitTime.dwHighDateTime || ExitTime.dwLowDateTime )
  {
LABEL_19:
    std::shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>::~shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>(v20);
LABEL_20:
    std::filesystem::path::~path((std::filesystem::path *)v2);
    return 0;
  }
  try
  {
    FileTime2 = 0;
    std::wstring::wstring(ValueName, L"ProcessStartTimeLow");
    FileTime2.dwLowDateTime = RegistryHelpers::GetVolatileRegistryKeyDWORDValue(hKey, v2, ValueName);
    std::filesystem::path::~path((std::filesystem::path *)ValueName);
    std::wstring::wstring(ValueName, L"ProcessStartTimeHigh");
    FileTime2.dwHighDateTime = RegistryHelpers::GetVolatileRegistryKeyDWORDValue(hKey, v2, ValueName);
    std::filesystem::path::~path((std::filesystem::path *)ValueName);
    v10 = CompareFileTime(&CreationTime, &FileTime2) == 0;
    std::shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>::~shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>(v20);
    std::filesystem::path::~path((std::filesystem::path *)v2);
    result = v10;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xF1,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.web.webview2\\sharedwebviewenvironmentmanager.cpp",
      v11);
    v2 = (WCHAR *)v18;
    goto LABEL_19;
  }
  return result;
}

```

## disassembly

```asm
0x18045dfcc  mov     [rsp+arg_10], rbx
0x18045dfd1  push    rsi
0x18045dfd2  push    rdi
0x18045dfd3  push    r14
0x18045dfd5  sub     rsp, 0D0h
0x18045dfdc  mov     rax, cs:__security_cookie
0x18045dfe3  xor     rax, rsp
0x18045dfe6  mov     [rsp+0E8h+var_28], rax
0x18045dfee  mov     rdi, rdx
0x18045dff1  mov     rsi, rcx
0x18045dff4  mov     [rsp+0E8h+var_90], rdx
0x18045dff9  mov     [rsp+0E8h+ExitTime.dwLowDateTime], 0
0x18045e001  lea     rdx, aProcessid; "ProcessId"
0x18045e008  lea     rcx, [rsp+0E8h+ValueName]
0x18045e00d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18045e012  nop
0x18045e013  mov     ebx, 1
0x18045e018  mov     [rsp+0E8h+ExitTime.dwLowDateTime], ebx
0x18045e01c  lea     r9d, [rbx+3]
0x18045e020  lea     r8, [rsp+0E8h+ValueName]
0x18045e025  mov     rdx, rdi; lpSubKey
0x18045e028  mov     rcx, rsi; hKey
0x18045e02b  call    RegistryHelpers__VolatileRegistryKeyValueExists
0x18045e030  test    al, al
0x18045e032  jz      short loc_18045E0A6
0x18045e034  lea     rdx, aProcessstartti_0; "ProcessStartTimeLow"
0x18045e03b  lea     rcx, [rsp+0E8h+var_48]
0x18045e043  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18045e048  nop
0x18045e049  mov     ebx, 3
0x18045e04e  mov     [rsp+0E8h+ExitTime.dwLowDateTime], ebx
0x18045e052  lea     r9d, [rbx+1]
0x18045e056  lea     r8, [rsp+0E8h+var_48]
0x18045e05e  mov     rdx, rdi; lpSubKey
0x18045e061  mov     rcx, rsi; hKey
0x18045e064  call    RegistryHelpers__VolatileRegistryKeyValueExists
0x18045e069  test    al, al
0x18045e06b  jz      short loc_18045E0A6
0x18045e06d  lea     rdx, aProcessstartti; "ProcessStartTimeHigh"
0x18045e074  lea     rcx, [rsp+0E8h+var_68]
0x18045e07c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18045e081  mov     ebx, 7
0x18045e086  lea     r9d, [rbx-3]
0x18045e08a  lea     r8, [rsp+0E8h+var_68]
0x18045e092  mov     rdx, rdi; lpSubKey
0x18045e095  mov     rcx, rsi; hKey
0x18045e098  call    RegistryHelpers__VolatileRegistryKeyValueExists
0x18045e09d  test    al, al
0x18045e09f  jz      short loc_18045E0A6
0x18045e0a1  mov     r14b, 1
0x18045e0a4  jmp     short loc_18045E0A9
0x18045e0a6  xor     r14b, r14b
0x18045e0a9  test    bl, 4
0x18045e0ac  jz      short loc_18045E0BF
0x18045e0ae  and     ebx, 0FFFFFFFBh
0x18045e0b1  lea     rcx, [rsp+0E8h+var_68]; this
0x18045e0b9  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18045e0be  nop
0x18045e0bf  test    bl, 2
0x18045e0c2  jz      short loc_18045E0D5
0x18045e0c4  and     ebx, 0FFFFFFFDh
0x18045e0c7  lea     rcx, [rsp+0E8h+var_48]; this
0x18045e0cf  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18045e0d4  nop
0x18045e0d5  test    bl, 1
0x18045e0d8  jz      short loc_18045E0E4
0x18045e0da  lea     rcx, [rsp+0E8h+ValueName]; this
0x18045e0df  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18045e0e4  test    r14b, r14b
0x18045e0e7  jz      loc_18045E25E
0x18045e0ed  lea     rdx, aProcessid; "ProcessId"
0x18045e0f4  lea     rcx, [rsp+0E8h+ValueName]
0x18045e0f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18045e0fe  nop
0x18045e0ff  lea     r8, [rsp+0E8h+ValueName]; lpValueName
0x18045e104  mov     rdx, rdi; lpSubKey
0x18045e107  mov     rcx, rsi; hKey
0x18045e10a  call    RegistryHelpers__GetVolatileRegistryKeyDWORDValue
0x18045e10f  mov     ebx, eax
0x18045e111  lea     rcx, [rsp+0E8h+ValueName]; this
0x18045e116  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18045e11b  mov     r8d, ebx; dwProcessId
0x18045e11e  xor     edx, edx; bInheritHandle
0x18045e120  mov     ecx, 1000h; dwDesiredAccess
0x18045e125  call    cs:__imp_OpenProcess
0x18045e12b  mov     rdx, rax
0x18045e12e  lea     rcx, [rsp+0E8h+var_68]
0x18045e136  call    ??0?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@PEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void *)
0x18045e13b  nop
0x18045e13c  mov     qword ptr [rsp+0E8h+CreationTime.dwLowDateTime], 0
0x18045e145  mov     qword ptr [rsp+0E8h+ExitTime.dwLowDateTime], 0
0x18045e14e  mov     qword ptr [rsp+0E8h+KernelTime.dwLowDateTime], 0
0x18045e157  mov     qword ptr [rsp+0E8h+UserTime.dwLowDateTime], 0
0x18045e160  mov     rax, [rsp+0E8h+var_68]
0x18045e168  test    rax, rax
0x18045e16b  jz      short loc_18045E172
0x18045e16d  mov     rcx, [rax]
0x18045e170  jmp     short loc_18045E174
0x18045e172  xor     ecx, ecx; hProcess
0x18045e174  lea     rax, [rsp+0E8h+UserTime]
0x18045e179  mov     [rsp+0E8h+lpUserTime], rax; lpUserTime
0x18045e17e  lea     r9, [rsp+0E8h+KernelTime]; lpKernelTime
0x18045e183  lea     r8, [rsp+0E8h+ExitTime]; lpExitTime
0x18045e188  lea     rdx, [rsp+0E8h+CreationTime]; lpCreationTime
0x18045e18d  call    cs:__imp_GetProcessTimes
0x18045e193  test    eax, eax
0x18045e195  jz      loc_18045E249
0x18045e19b  cmp     [rsp+0E8h+ExitTime.dwHighDateTime], 0
0x18045e1a0  jnz     loc_18045E249
0x18045e1a6  cmp     [rsp+0E8h+ExitTime.dwLowDateTime], 0
0x18045e1ab  jnz     loc_18045E249
0x18045e1b1  mov     qword ptr [rsp+0E8h+FileTime2.dwLowDateTime], 0
0x18045e1ba  lea     rdx, aProcessstartti_0; "ProcessStartTimeLow"
0x18045e1c1  lea     rcx, [rsp+0E8h+ValueName]
0x18045e1c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18045e1cb  nop
0x18045e1cc  lea     r8, [rsp+0E8h+ValueName]; lpValueName
0x18045e1d1  mov     rdx, rdi; lpSubKey
0x18045e1d4  mov     rcx, rsi; hKey
0x18045e1d7  call    RegistryHelpers__GetVolatileRegistryKeyDWORDValue
0x18045e1dc  mov     [rsp+0E8h+FileTime2.dwLowDateTime], eax
0x18045e1e0  lea     rcx, [rsp+0E8h+ValueName]; this
0x18045e1e5  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18045e1ea  lea     rdx, aProcessstartti; "ProcessStartTimeHigh"
0x18045e1f1  lea     rcx, [rsp+0E8h+ValueName]
0x18045e1f6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18045e1fb  nop
0x18045e1fc  lea     r8, [rsp+0E8h+ValueName]; lpValueName
0x18045e201  mov     rdx, rdi; lpSubKey
0x18045e204  mov     rcx, rsi; hKey
0x18045e207  call    RegistryHelpers__GetVolatileRegistryKeyDWORDValue
0x18045e20c  mov     [rsp+0E8h+FileTime2.dwHighDateTime], eax
0x18045e210  lea     rcx, [rsp+0E8h+ValueName]; this
0x18045e215  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18045e21a  lea     rdx, [rsp+0E8h+FileTime2]; lpFileTime2
0x18045e21f  lea     rcx, [rsp+0E8h+CreationTime]; lpFileTime1
0x18045e224  call    cs:__imp_CompareFileTime
0x18045e22a  test    eax, eax
0x18045e22c  setz    bl
0x18045e22f  lea     rcx, [rsp+0E8h+var_68]
0x18045e237  call    ??1?$shared_ptr@VUserRegistryReaderWriter@implementation@Text@Input@UI@WindowsUdk@winrt@@@std@@QEAA@XZ; std::shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>::~shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>(void)
0x18045e23c  nop
0x18045e23d  mov     rcx, rdi; this
0x18045e240  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18045e245  mov     al, bl
0x18045e247  jmp     short loc_18045E268
0x18045e249  jmp     short loc_18045E250
0x18045e24b  mov     rdi, [rsp+0E8h+var_90]
0x18045e250  lea     rcx, [rsp+0E8h+var_68]
0x18045e258  call    ??1?$shared_ptr@VUserRegistryReaderWriter@implementation@Text@Input@UI@WindowsUdk@winrt@@@std@@QEAA@XZ; std::shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>::~shared_ptr<winrt::WindowsUdk::UI::Input::Text::implementation::UserRegistryReaderWriter>(void)
0x18045e25d  nop
0x18045e25e  mov     rcx, rdi; this
0x18045e261  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18045e266  xor     al, al
0x18045e268  mov     rcx, [rsp+0E8h+var_28]
0x18045e270  xor     rcx, rsp; StackCookie
0x18045e273  call    __security_check_cookie
0x18045e278  mov     rbx, [rsp+0E8h+arg_10]
0x18045e280  add     rsp, 0D0h
0x18045e287  pop     r14
0x18045e289  pop     rdi
0x18045e28a  pop     rsi
0x18045e28b  retn
```
