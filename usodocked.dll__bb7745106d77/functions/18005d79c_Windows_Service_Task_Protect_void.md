# Windows::Service::Task::Protect(void)

- ea: `0x18005d79c`
- end: `0x18005d93c`
- name: `?Protect@Task@Service@Windows@@AEAAXXZ`
- size: `416`
- prototype: `void __fastcall(__int64 **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005d944`

## callees

- `0x1800209fc`
- `0x18005af50`
- `0x18005d79c`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005d8d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d8d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d7da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d7da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d8a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d8b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d8a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d8b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d8c7`

## string_xrefs

- `0x18005d8ff`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005d914`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d929`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Service::Task::Protect(__int64 **this)
{
  HRESULT v2; // eax
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  const WCHAR *v6; // rdx
  const WCHAR *v7; // rdx
  int v8; // eax
  const char *v9; // r9
  int ppv; // [rsp+20h] [rbp-38h]
  HSTRING string; // [rsp+30h] [rbp-28h] BYREF
  HSTRING v12; // [rsp+38h] [rbp-20h] BYREF
  HSTRING v13; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  BSTR bstrString; // [rsp+70h] [rbp+18h] BYREF
  LPVOID v16; // [rsp+78h] [rbp+20h] BYREF

  v16 = 0;
  v2 = CoCreateInstance(
         &GUID_9ea82395_e31b_41ca_8df7_ec1cee7194df,
         0,
         4u,
         &GUID_e4dc719b_fe77_414f_9dbe_3e4ffea7a7a5,
         &v16);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
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
        (void *)0xF7,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v5,
        ppv);
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v13,
      bstrString);
    v6 = (const WCHAR *)(this + 1);
    if ( (unsigned __int64)this[4] > 7 )
      v6 = *(const WCHAR **)v6;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v12,
      v6);
    v7 = (const WCHAR *)&Windows::Service::Task::c_taskFolder;
    if ( (unsigned __int64)qword_180097688 > 7 )
      v7 = Windows::Service::Task::c_taskFolder;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &string,
      v7);
    v8 = (*(__int64 (__fastcall **)(LPVOID, HSTRING, HSTRING, HSTRING))(*(_QWORD *)v16 + 24LL))(v16, v12, string, v13);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v8,
        ppv);
    if ( string )
      WindowsDeleteString(string);
    if ( v12 )
      WindowsDeleteString(v12);
    if ( v13 )
      WindowsDeleteString(v13);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      v9);
  }
}

```

## disassembly

```asm
0x18005d79c  mov     rax, rsp
0x18005d79f  push    rbx
0x18005d7a0  sub     rsp, 50h
0x18005d7a4  mov     rbx, rcx
0x18005d7a7  mov     dword ptr [rax+10h], 0
0x18005d7ae  mov     dword ptr [rax+10h], 2
0x18005d7b5  mov     qword ptr [rax+20h], 0
0x18005d7bd  lea     rax, [rax+20h]
0x18005d7c1  mov     qword ptr [rsp+58h+ppv], rax; int
0x18005d7c6  lea     r9, _GUID_e4dc719b_fe77_414f_9dbe_3e4ffea7a7a5; riid
0x18005d7cd  xor     edx, edx; pUnkOuter
0x18005d7cf  lea     r8d, [rdx+4]; dwClsContext
0x18005d7d3  lea     rcx, _GUID_9ea82395_e31b_41ca_8df7_ec1cee7194df; rclsid
0x18005d7da  call    cs:__imp_CoCreateInstance
0x18005d7e0  mov     rcx, [rsp+58h]; this
0x18005d7e5  test    eax, eax
0x18005d7e7  js      loc_18005D8FC
0x18005d7ed  mov     [rsp+58h+bstrString], 0
0x18005d7f6  mov     rcx, [rbx]
0x18005d7f9  mov     rax, [rcx]
0x18005d7fc  mov     [rsp+58h+bstrString], 0
0x18005d805  lea     rdx, [rsp+58h+bstrString]
0x18005d80a  mov     rax, [rax+98h]
0x18005d811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d816  mov     rcx, [rsp+58h]; this
0x18005d81b  test    eax, eax
0x18005d81d  js      loc_18005D911
0x18005d823  mov     rdx, [rsp+58h+bstrString]; sourceString
0x18005d828  lea     rcx, [rsp+58h+var_18]; string
0x18005d82d  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005d832  nop
0x18005d833  lea     rdx, [rbx+8]
0x18005d837  cmp     qword ptr [rdx+18h], 7
0x18005d83c  jbe     short loc_18005D841
0x18005d83e  mov     rdx, [rdx]; sourceString
0x18005d841  lea     rcx, [rsp+58h+var_20]; string
0x18005d846  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005d84b  nop
0x18005d84c  lea     rdx, ?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_taskFolder
0x18005d853  cmp     cs:qword_180097688, 7
0x18005d85b  cmova   rdx, cs:?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; sourceString
0x18005d863  lea     rcx, [rsp+58h+string]; string
0x18005d868  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005d86d  nop
0x18005d86e  mov     rcx, [rsp+58h+arg_18]
0x18005d873  mov     rax, [rcx]
0x18005d876  mov     r9, [rsp+58h+var_18]
0x18005d87b  mov     r8, [rsp+58h+string]
0x18005d880  mov     rdx, [rsp+58h+var_20]
0x18005d885  mov     rax, [rax+18h]
0x18005d889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d88e  mov     rcx, [rsp+58h]; this
0x18005d893  test    eax, eax
0x18005d895  js      loc_18005D926
0x18005d89b  mov     rcx, [rsp+58h+string]; string
0x18005d8a0  test    rcx, rcx
0x18005d8a3  jz      short loc_18005D8AC
0x18005d8a5  call    cs:__imp_WindowsDeleteString
0x18005d8ab  nop
0x18005d8ac  mov     rcx, [rsp+58h+var_20]; string
0x18005d8b1  test    rcx, rcx
0x18005d8b4  jz      short loc_18005D8BD
0x18005d8b6  call    cs:__imp_WindowsDeleteString
0x18005d8bc  nop
0x18005d8bd  mov     rcx, [rsp+58h+var_18]; string
0x18005d8c2  test    rcx, rcx
0x18005d8c5  jz      short loc_18005D8CE
0x18005d8c7  call    cs:__imp_WindowsDeleteString
0x18005d8cd  nop
0x18005d8ce  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18005d8d3  test    rcx, rcx
0x18005d8d6  jz      short loc_18005D8DF
0x18005d8d8  call    cs:__imp_SysFreeString
0x18005d8de  nop
0x18005d8df  mov     rcx, [rsp+58h+arg_18]
0x18005d8e4  test    rcx, rcx
0x18005d8e7  jz      short loc_18005D8F6
0x18005d8e9  mov     rax, [rcx]
0x18005d8ec  mov     rax, [rax+10h]
0x18005d8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8f5  nop
0x18005d8f6  add     rsp, 50h
0x18005d8fa  pop     rbx
0x18005d8fb  retn
0x18005d8fc  mov     r9d, eax; char *
0x18005d8ff  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005d906  mov     edx, 1CBEh; void *
0x18005d90b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d911  mov     r9d, eax; char *
0x18005d914  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005d91b  mov     edx, 0F7h; void *
0x18005d920  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d926  mov     r9d, eax; char *
0x18005d929  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005d930  mov     edx, 102h; void *
0x18005d935  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
