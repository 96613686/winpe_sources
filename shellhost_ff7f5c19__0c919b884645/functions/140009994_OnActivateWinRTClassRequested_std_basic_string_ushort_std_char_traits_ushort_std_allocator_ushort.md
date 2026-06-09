# OnActivateWinRTClassRequested(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140009994`
- end: `0x140009a80`
- name: `?OnActivateWinRTClassRequested@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005ccc0`

## callees

- `0x140009994`
- `0x140009a88`
- `0x140009b14`
- `0x140009b38`
- `0x140009b7c`
- `0x140009b9c`
- `0x140009d6c`
- `0x14000f7e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140009a02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140009a02`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140009a20`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140009a20`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OnActivateWinRTClassRequested(_QWORD *sourceString)
{
  _QWORD *v2; // rax
  const WCHAR *v3; // rcx
  __int64 v4; // rdx
  _QWORD *v5; // rax
  _QWORD *v7; // [rsp+20h] [rbp-30h] BYREF
  int ActivationFactory; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v10; // [rsp+38h] [rbp-18h] BYREF

  v10 = sourceString;
  if ( sourceString[3] <= 7u )
    v2 = sourceString;
  else
    v2 = (_QWORD *)*sourceString;
  v7 = v2;
  ShellHostTelemetry::ActivateWinRTClassRequested<unsigned short const *>(&v7);
  winrt::impl::call_factory_cast<void (*)(winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics const &),winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics,_lambda_997cb0a4227bb4d575528ed52484f71c_>();
  if ( sourceString[3] <= 7u )
    v3 = (const WCHAR *)sourceString;
  else
    v3 = (const WCHAR *)*sourceString;
  v4 = -1;
  do
    ++v4;
  while ( v3[v4] );
  string = 0;
  WindowsCreateString(v3, v4, &string);
  if ( string )
  {
    v7 = 0;
    ActivationFactory = RoGetActivationFactory(string, &GUID_00000000_0000_0000_c000_000000000046, &v7);
    if ( sourceString[3] <= 7u )
      v5 = sourceString;
    else
      v5 = (_QWORD *)*sourceString;
    v10 = v5;
    ShellHostTelemetry::ActivateWinRTClassCompleted<unsigned short const *,long &>(&v10, &ActivationFactory);
    wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v7);
  }
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  return std::wstring::~wstring(sourceString);
}

```

## disassembly

```asm
0x140009994  mov     [rsp-8+arg_8], rbx
0x140009999  mov     [rsp-8+arg_10], rdi
0x14000999e  push    rbp
0x14000999f  mov     rbp, rsp
0x1400099a2  sub     rsp, 50h
0x1400099a6  mov     rax, cs:__security_cookie
0x1400099ad  xor     rax, rsp
0x1400099b0  mov     [rbp+var_10], rax
0x1400099b4  mov     rbx, rcx
0x1400099b7  mov     [rbp+var_18], rcx
0x1400099bb  cmp     qword ptr [rcx+18h], 7
0x1400099c0  jbe     short loc_1400099C7
0x1400099c2  mov     rax, [rcx]
0x1400099c5  jmp     short loc_1400099CA
0x1400099c7  mov     rax, rbx
0x1400099ca  mov     [rbp+var_30], rax
0x1400099ce  lea     rcx, [rbp+var_30]
0x1400099d2  call    ??$ActivateWinRTClassRequested@PEBG@ShellHostTelemetry@@SAX$$QEAPEBG@Z; ShellHostTelemetry::ActivateWinRTClassRequested<ushort const *>(ushort const * &&)
0x1400099d7  call    ??$call_factory_cast@P6AXAEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@ZUAppExtension@2345@U12345@V_lambda_997cb0a4227bb4d575528ed52484f71c_@@@impl@winrt@@YA?A_P$$QEAV_lambda_997cb0a4227bb4d575528ed52484f71c_@@@Z
0x1400099dc  cmp     qword ptr [rbx+18h], 7
0x1400099e1  jbe     short loc_1400099E8
0x1400099e3  mov     rcx, [rbx]
0x1400099e6  jmp     short loc_1400099EB
0x1400099e8  mov     rcx, rbx; sourceString
0x1400099eb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400099ef  xor     edi, edi
0x1400099f1  inc     rdx; length
0x1400099f4  cmp     [rcx+rdx*2], di
0x1400099f8  jnz     short loc_1400099F1
0x1400099fa  mov     [rbp+string], rdi
0x1400099fe  lea     r8, [rbp+string]; string
0x140009a02  call    cs:__imp_WindowsCreateString
0x140009a08  mov     rcx, [rbp+string]
0x140009a0c  test    rcx, rcx
0x140009a0f  jz      short loc_140009A52
0x140009a11  mov     [rbp+var_30], rdi
0x140009a15  lea     r8, [rbp+var_30]
0x140009a19  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140009a20  call    cs:__imp_RoGetActivationFactory
0x140009a26  mov     [rbp+var_28], eax
0x140009a29  cmp     qword ptr [rbx+18h], 7
0x140009a2e  jbe     short loc_140009A35
0x140009a30  mov     rax, [rbx]
0x140009a33  jmp     short loc_140009A38
0x140009a35  mov     rax, rbx
0x140009a38  mov     [rbp+var_18], rax
0x140009a3c  lea     rdx, [rbp+var_28]
0x140009a40  lea     rcx, [rbp+var_18]
0x140009a44  call    ??$ActivateWinRTClassCompleted@PEBGAEAJ@ShellHostTelemetry@@SAX$$QEAPEBGAEAJ@Z; ShellHostTelemetry::ActivateWinRTClassCompleted<ushort const *,long &>(ushort const * &&,long &)
0x140009a49  lea     rcx, [rbp+var_30]
0x140009a4d  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x140009a52  lea     rcx, [rbp+string]
0x140009a56  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x140009a5b  nop
0x140009a5c  mov     rcx, rbx
0x140009a5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009a64  mov     rcx, [rbp+var_10]
0x140009a68  xor     rcx, rsp; StackCookie
0x140009a6b  call    __security_check_cookie
0x140009a70  mov     rbx, [rsp+50h+arg_8]
0x140009a75  mov     rdi, [rsp+50h+arg_10]
0x140009a7a  add     rsp, 50h
0x140009a7e  pop     rbp
0x140009a7f  retn
```
