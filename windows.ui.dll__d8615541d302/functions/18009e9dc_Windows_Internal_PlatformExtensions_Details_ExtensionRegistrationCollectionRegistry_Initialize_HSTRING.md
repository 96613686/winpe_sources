# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(HSTRING__ *)

- ea: `0x18009e9dc`
- end: `0x18009eab4`
- name: `?Initialize@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `216`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18009e0ac`

## callees

- `0x180014754`
- `0x180033f08`
- `0x18009c6a4`
- `0x18009e9dc`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009ea81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009ea81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ea06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ea06`

## string_xrefs

- `0x18009ea33`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *this,
        HSTRING a2)
{
  PCWSTR StringRawBuffer; // rax
  int v4; // eax
  unsigned int v5; // ebx
  int phkResult; // [rsp+20h] [rbp-148h]
  char *v8; // [rsp+30h] [rbp-138h] BYREF
  HKEY v9; // [rsp+38h] [rbp-130h] BYREF
  char v10; // [rsp+40h] [rbp-128h]
  WCHAR SubKey[128]; // [rsp+50h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v4 = StringCchPrintfW(SubKey, 0x80u, L"SOFTWARE\\Classes\\OneCoreContracts\\%s", StringRawBuffer);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v9 = 0;
    v8 = (char *)this + 8;
    v10 = 1;
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v9);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v8);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v4,
      phkResult);
    return v5;
  }
}

```

## disassembly

```asm
0x18009e9dc  mov     [rsp+arg_0], rbx
0x18009e9e1  push    rdi
0x18009e9e2  sub     rsp, 160h
0x18009e9e9  mov     rax, cs:__security_cookie
0x18009e9f0  xor     rax, rsp
0x18009e9f3  mov     [rsp+168h+var_18], rax
0x18009e9fb  mov     rax, rdx
0x18009e9fe  mov     rdi, rcx
0x18009ea01  mov     rcx, rax; string
0x18009ea04  xor     edx, edx; length
0x18009ea06  call    cs:__imp_WindowsGetStringRawBuffer
0x18009ea0c  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\OneCoreContracts\\%s"
0x18009ea13  mov     edx, 80h; unsigned __int64
0x18009ea18  mov     r9, rax
0x18009ea1b  lea     rcx, [rsp+168h+SubKey]; unsigned __int16 *
0x18009ea20  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009ea25  mov     ebx, eax
0x18009ea27  test    eax, eax
0x18009ea29  jns     short loc_18009EA4B
0x18009ea2b  mov     rcx, [rsp+168h]; this
0x18009ea33  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18009ea3a  mov     r9d, eax; char *
0x18009ea3d  mov     edx, 129h; void *
0x18009ea42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ea47  mov     eax, ebx
0x18009ea49  jmp     short loc_18009EA93
0x18009ea4b  lea     rax, [rdi+8]
0x18009ea4f  mov     [rsp+168h+var_130], 0
0x18009ea58  mov     [rsp+168h+var_138], rax
0x18009ea5d  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x18009ea62  lea     rax, [rsp+168h+var_130]
0x18009ea67  mov     [rsp+168h+var_128], 1
0x18009ea6c  mov     r9d, 20019h; samDesired
0x18009ea72  mov     qword ptr [rsp+168h+phkResult], rax; phkResult
0x18009ea77  xor     r8d, r8d; ulOptions
0x18009ea7a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009ea81  call    cs:__imp_RegOpenKeyExW
0x18009ea87  lea     rcx, [rsp+168h+var_138]
0x18009ea8c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009ea91  xor     eax, eax
0x18009ea93  mov     rcx, [rsp+168h+var_18]
0x18009ea9b  xor     rcx, rsp; StackCookie
0x18009ea9e  call    __security_check_cookie
0x18009eaa3  mov     rbx, [rsp+168h+arg_0]
0x18009eaab  add     rsp, 160h
0x18009eab2  pop     rdi
0x18009eab3  retn
```
