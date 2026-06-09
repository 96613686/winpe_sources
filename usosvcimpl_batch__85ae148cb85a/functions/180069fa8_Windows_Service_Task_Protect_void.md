# Windows::Service::Task::Protect(void)

- ea: `0x180069fa8`
- end: `0x18006a171`
- name: `?Protect@Task@Service@Windows@@AEAAXXZ`
- size: `457`
- prototype: `void __fastcall(Windows::Service::Task *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180069948`

## callees

- `0x1800112d0`
- `0x180069fa8`
- `0x18006d974`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180069ff7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180069ff7`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a100`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a0cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a0de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a0ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a0cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a0de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a0ef`

## string_xrefs

- `0x18006a134`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18006a084`: `Microsoft\Windows\UpdateOrchestrator`
- `0x18006a149`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006a15e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Windows::Service::Task::Protect(__int64 **this)
{
  HRESULT v2; // eax
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  const WCHAR *v6; // rdx
  int v7; // eax
  const char *v8; // r9
  int ppv; // [rsp+20h] [rbp-58h]
  BSTR bstrString; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v12; // [rsp+48h] [rbp-30h] BYREF
  HSTRING v13; // [rsp+50h] [rbp-28h] BYREF
  LPVOID v14; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v14 = 0;
  v2 = CoCreateInstance(
         &GUID_9ea82395_e31b_41ca_8df7_ec1cee7194df,
         0,
         4u,
         &GUID_e4dc719b_fe77_414f_9dbe_3e4ffea7a7a5,
         &v14);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C96,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v2,
        ppv);
    bstrString = 0;
    v3 = *this;
    v4 = **this;
    bstrString = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v4 + 152))(v3, &bstrString);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v5,
        ppv);
    v13 = 0;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v13,
      bstrString);
    v12 = 0;
    v6 = (const WCHAR *)(this + 1);
    if ( (unsigned __int64)this[4] > 7 )
      v6 = *(const WCHAR **)v6;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v12,
      v6);
    string = 0;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &string,
      L"Microsoft\\Windows\\UpdateOrchestrator");
    v7 = (*(__int64 (__fastcall **)(LPVOID, HSTRING, HSTRING, HSTRING))(*(_QWORD *)v14 + 24LL))(v14, v12, string, v13);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    if ( string )
      WindowsDeleteString(string);
    if ( v12 )
      WindowsDeleteString(v12);
    if ( v13 )
      WindowsDeleteString(v13);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v14 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x11A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      v8);
  }
}

```

## disassembly

```asm
0x180069fa8  push    rbx
0x180069faa  sub     rsp, 70h
0x180069fae  mov     rax, cs:__security_cookie
0x180069fb5  xor     rax, rsp
0x180069fb8  mov     [rsp+78h+var_18], rax
0x180069fbd  mov     rbx, rcx
0x180069fc0  mov     [rsp+78h+var_48], 0
0x180069fc8  mov     [rsp+78h+var_48], 2
0x180069fd0  mov     [rsp+78h+var_20], 0
0x180069fd9  lea     rax, [rsp+78h+var_20]
0x180069fde  mov     qword ptr [rsp+78h+ppv], rax; int
0x180069fe3  lea     r9, _GUID_e4dc719b_fe77_414f_9dbe_3e4ffea7a7a5; riid
0x180069fea  xor     edx, edx; pUnkOuter
0x180069fec  lea     r8d, [rdx+4]; dwClsContext
0x180069ff0  lea     rcx, _GUID_9ea82395_e31b_41ca_8df7_ec1cee7194df; rclsid
0x180069ff7  call    cs:__imp_CoCreateInstance
0x180069ffd  mov     rcx, [rsp+78h]; this
0x18006a002  test    eax, eax
0x18006a004  js      loc_18006A131
0x18006a00a  mov     [rsp+78h+bstrString], 0
0x18006a013  mov     rcx, [rbx]
0x18006a016  mov     rax, [rcx]
0x18006a019  mov     [rsp+78h+bstrString], 0
0x18006a022  lea     rdx, [rsp+78h+bstrString]
0x18006a027  mov     rax, [rax+98h]
0x18006a02e  call    _guard_dispatch_icall
0x18006a033  mov     rcx, [rsp+78h]; this
0x18006a038  test    eax, eax
0x18006a03a  js      loc_18006A146
0x18006a040  mov     [rsp+78h+var_28], 0
0x18006a049  mov     rdx, [rsp+78h+bstrString]; sourceString
0x18006a04e  lea     rcx, [rsp+78h+var_28]; string
0x18006a053  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18006a058  nop
0x18006a059  mov     [rsp+78h+var_30], 0
0x18006a062  lea     rdx, [rbx+8]
0x18006a066  cmp     qword ptr [rdx+18h], 7
0x18006a06b  jbe     short loc_18006A070
0x18006a06d  mov     rdx, [rdx]; sourceString
0x18006a070  lea     rcx, [rsp+78h+var_30]; string
0x18006a075  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18006a07a  nop
0x18006a07b  mov     [rsp+78h+string], 0
0x18006a084  lea     rdx, sourceString; "Microsoft\\Windows\\UpdateOrchestrator"
0x18006a08b  lea     rcx, [rsp+78h+string]; string
0x18006a090  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18006a095  nop
0x18006a096  mov     rcx, [rsp+78h+var_20]
0x18006a09b  mov     rax, [rcx]
0x18006a09e  mov     r9, [rsp+78h+var_28]
0x18006a0a3  mov     r8, [rsp+78h+string]
0x18006a0a8  mov     rdx, [rsp+78h+var_30]
0x18006a0ad  mov     rax, [rax+18h]
0x18006a0b1  call    _guard_dispatch_icall
0x18006a0b6  mov     rcx, [rsp+78h]; this
0x18006a0bb  test    eax, eax
0x18006a0bd  js      loc_18006A15B
0x18006a0c3  mov     rcx, [rsp+78h+string]; string
0x18006a0c8  test    rcx, rcx
0x18006a0cb  jz      short loc_18006A0D4
0x18006a0cd  call    cs:__imp_WindowsDeleteString
0x18006a0d3  nop
0x18006a0d4  mov     rcx, [rsp+78h+var_30]; string
0x18006a0d9  test    rcx, rcx
0x18006a0dc  jz      short loc_18006A0E5
0x18006a0de  call    cs:__imp_WindowsDeleteString
0x18006a0e4  nop
0x18006a0e5  mov     rcx, [rsp+78h+var_28]; string
0x18006a0ea  test    rcx, rcx
0x18006a0ed  jz      short loc_18006A0F6
0x18006a0ef  call    cs:__imp_WindowsDeleteString
0x18006a0f5  nop
0x18006a0f6  mov     rcx, [rsp+78h+bstrString]; bstrString
0x18006a0fb  test    rcx, rcx
0x18006a0fe  jz      short loc_18006A107
0x18006a100  call    cs:__imp_SysFreeString
0x18006a106  nop
0x18006a107  mov     rcx, [rsp+78h+var_20]
0x18006a10c  test    rcx, rcx
0x18006a10f  jz      short loc_18006A11E
0x18006a111  mov     rax, [rcx]
0x18006a114  mov     rax, [rax+10h]
0x18006a118  call    _guard_dispatch_icall
0x18006a11d  nop
0x18006a11e  mov     rcx, [rsp+78h+var_18]
0x18006a123  xor     rcx, rsp; StackCookie
0x18006a126  call    __security_check_cookie
0x18006a12b  add     rsp, 70h
0x18006a12f  pop     rbx
0x18006a130  retn
0x18006a131  mov     r9d, eax; char *
0x18006a134  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18006a13b  mov     edx, 1C96h; void *
0x18006a140  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a146  mov     r9d, eax; char *
0x18006a149  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a150  mov     edx, 10Dh; void *
0x18006a155  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a15b  mov     r9d, eax; char *
0x18006a15e  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a165  mov     edx, 118h; void *
0x18006a16a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
