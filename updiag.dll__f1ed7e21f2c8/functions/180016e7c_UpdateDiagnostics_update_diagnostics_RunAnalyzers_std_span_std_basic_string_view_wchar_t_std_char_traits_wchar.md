# UpdateDiagnostics::update_diagnostics::RunAnalyzers(std::span<std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const,-1>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180016e7c`
- end: `0x180016fd9`
- name: `?RunAnalyzers@update_diagnostics@UpdateDiagnostics@@QEAA?AUhstring_view@2@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18000f290`

## callees

- `0x180009548`
- `0x180016e7c`
- `0x180017344`
- `0x180017450`
- `0x180017504`
- `0x18008fe00`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016f95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016f95`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HSTRING __fastcall UpdateDiagnostics::update_diagnostics::RunAnalyzers(
        __int64 a1,
        HSTRING a2,
        __int128 *a3,
        __int128 *a4,
        __int128 *a5)
{
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // rcx
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64, __int64); // r10
  int v13; // eax
  __int64 v14; // rax
  int v16; // [rsp+20h] [rbp-51h]
  __int128 v17; // [rsp+40h] [rbp-31h] BYREF
  __int64 v18; // [rsp+58h] [rbp-19h]
  HSTRING v19; // [rsp+60h] [rbp-11h] BYREF
  HSTRING string; // [rsp+68h] [rbp-9h] BYREF
  __int128 v21; // [rsp+70h] [rbp-1h] BYREF
  __int64 v22; // [rsp+80h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v19 = a2;
  v21 = 0;
  v22 = 0;
  v17 = *a3;
  UpdateDiagnostics::update_diagnostics::_CreateHStringArray(&v21, &v17);
  v19 = 0;
  v17 = *a4;
  v9 = UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(&v17, &v19);
  string = 0;
  v17 = *a5;
  v10 = UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(&v17, &string);
  v18 = 0;
  v11 = *(_QWORD *)(a1 + 8);
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v11 + 64LL);
  v18 = 0;
  v16 = v10;
  v13 = v12(
          v11,
          v21 & ((unsigned __int128)-(__int128)*((unsigned __int64 *)a3 + 1) >> 64),
          (__int64)(*((_QWORD *)&v21 + 1) - v21) >> 3,
          v9);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
      (const char *)(unsigned int)v13,
      v16);
  v14 = v18;
  v18 = 0;
  *(_QWORD *)a2 = v14;
  if ( string )
    WindowsDeleteString(string);
  if ( v19 )
    WindowsDeleteString(v19);
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>((__int64)&v21);
  return a2;
}

```

## disassembly

```asm
0x180016e7c  push    rbp
0x180016e7e  push    rbx
0x180016e7f  push    rsi
0x180016e80  push    rdi
0x180016e81  push    r14
0x180016e83  push    r15
0x180016e85  lea     rbp, [rsp-27h]
0x180016e8a  sub     rsp, 98h
0x180016e91  mov     rax, cs:__security_cookie
0x180016e98  xor     rax, rsp
0x180016e9b  mov     [rbp+4Fh+var_38], rax
0x180016e9f  mov     rdi, r9
0x180016ea2  mov     r14, r8
0x180016ea5  mov     r15, rdx
0x180016ea8  mov     rsi, rcx
0x180016eab  mov     [rbp+4Fh+var_60], rdx
0x180016eaf  mov     rbx, [rbp+4Fh+arg_20]
0x180016eb3  xorps   xmm0, xmm0
0x180016eb6  xor     eax, eax
0x180016eb8  movups  [rbp+4Fh+var_50], xmm0
0x180016ebc  mov     [rbp+4Fh+var_40], rax
0x180016ec0  movaps  xmm0, xmmword ptr [r8]
0x180016ec4  movdqa  [rbp+4Fh+var_80], xmm0
0x180016ec9  lea     rdx, [rbp+4Fh+var_80]
0x180016ecd  lea     rcx, [rbp+4Fh+var_50]
0x180016ed1  call    ?_CreateHStringArray@update_diagnostics@UpdateDiagnostics@@CA?AV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@4@@Z; UpdateDiagnostics::update_diagnostics::_CreateHStringArray(std::span<std::wstring_view const,-1>)
0x180016ed6  nop
0x180016ed7  mov     [rbp+4Fh+var_60], 0
0x180016edf  movaps  xmm0, xmmword ptr [rdi]
0x180016ee2  movdqa  [rbp+4Fh+var_80], xmm0
0x180016ee7  lea     rdx, [rbp+4Fh+var_60]
0x180016eeb  lea     rcx, [rbp+4Fh+var_80]
0x180016eef  call    ?_CreateOptionalHString@update_diagnostics@UpdateDiagnostics@@CAPEAUHSTRING__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180016ef4  mov     rdi, rax
0x180016ef7  mov     [rbp+4Fh+string], 0
0x180016eff  movaps  xmm0, xmmword ptr [rbx]
0x180016f02  movdqa  [rbp+4Fh+var_80], xmm0
0x180016f07  lea     rdx, [rbp+4Fh+string]
0x180016f0b  lea     rcx, [rbp+4Fh+var_80]
0x180016f0f  call    ?_CreateOptionalHString@update_diagnostics@UpdateDiagnostics@@CAPEAUHSTRING__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180016f14  mov     r9, rax
0x180016f17  mov     [rbp+4Fh+var_68], 0
0x180016f1f  mov     rcx, [rsi+8]
0x180016f23  mov     rax, [rcx]
0x180016f26  mov     r10, [rax+40h]
0x180016f2a  mov     [rbp+4Fh+var_68], 0
0x180016f32  mov     r8, qword ptr [rbp+4Fh+var_50+8]
0x180016f36  sub     r8, qword ptr [rbp+4Fh+var_50]
0x180016f3a  sar     r8, 3
0x180016f3e  mov     rax, [r14+8]
0x180016f42  neg     rax
0x180016f45  sbb     rdx, rdx
0x180016f48  and     rdx, qword ptr [rbp+4Fh+var_50]
0x180016f4c  lea     rax, [rbp+4Fh+var_68]
0x180016f50  mov     [rsp+0C0h+var_98], rax
0x180016f55  mov     qword ptr [rsp+0C0h+var_A0], r9; int
0x180016f5a  mov     r9, rdi
0x180016f5d  mov     rax, r10
0x180016f60  call    _guard_dispatch_icall
0x180016f65  mov     rcx, [rbp+57h]; this
0x180016f69  test    eax, eax
0x180016f6b  js      short loc_180016FC4
0x180016f6d  mov     rax, [rbp+4Fh+var_68]
0x180016f71  mov     [rbp+4Fh+var_68], 0
0x180016f79  mov     [r15], rax
0x180016f7c  mov     rcx, [rbp+4Fh+string]; string
0x180016f80  test    rcx, rcx
0x180016f83  jz      short loc_180016F8C
0x180016f85  call    cs:__imp_WindowsDeleteString
0x180016f8b  nop
0x180016f8c  mov     rcx, [rbp+4Fh+var_60]; string
0x180016f90  test    rcx, rcx
0x180016f93  jz      short loc_180016F9C
0x180016f95  call    cs:__imp_WindowsDeleteString
0x180016f9b  nop
0x180016f9c  lea     rcx, [rbp+4Fh+var_50]
0x180016fa0  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180016fa5  mov     rax, r15
0x180016fa8  mov     rcx, [rbp+4Fh+var_38]
0x180016fac  xor     rcx, rsp; StackCookie
0x180016faf  call    __security_check_cookie
0x180016fb4  add     rsp, 98h
0x180016fbb  pop     r15
0x180016fbd  pop     r14
0x180016fbf  pop     rdi
0x180016fc0  pop     rsi
0x180016fc1  pop     rbx
0x180016fc2  pop     rbp
0x180016fc3  retn
0x180016fc4  mov     r9d, eax; char *
0x180016fc7  lea     r8, aCW1SSrcCalliop_0; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x180016fce  mov     edx, 138h; void *
0x180016fd3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
