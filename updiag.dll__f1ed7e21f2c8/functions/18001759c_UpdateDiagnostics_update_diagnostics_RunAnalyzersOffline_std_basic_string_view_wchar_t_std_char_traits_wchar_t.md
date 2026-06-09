# UpdateDiagnostics::update_diagnostics::RunAnalyzersOffline(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::span<std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const,-1>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18001759c`
- end: `0x180017753`
- name: `?RunAnalyzersOffline@update_diagnostics@UpdateDiagnostics@@QEAA?AUhstring_view@2@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@5@00@Z`
- size: `439`
- prototype: `HSTRING __fastcall(__int64, HSTRING, __int64, __int128 *, __int128 *, __int128 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18000f290`

## callees

- `0x180009548`
- `0x180017344`
- `0x180017450`
- `0x180017504`
- `0x18001759c`
- `0x18008fe00`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001760f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001760f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800176d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800176e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800176f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800176d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800176e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800176f8`

## pseudocode

```c
HSTRING __fastcall UpdateDiagnostics::update_diagnostics::RunAnalyzersOffline(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        __int128 *a4,
        __int128 *a5,
        __int128 *a6)
{
  HRESULT v10; // eax
  int v11; // ebx
  __int64 v12; // rcx
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64, HSTRING); // r10
  int v14; // eax
  __int64 v15; // rax
  int v17; // [rsp+20h] [rbp-69h]
  __int128 v18; // [rsp+40h] [rbp-49h] BYREF
  __int64 v19; // [rsp+58h] [rbp-31h]
  HSTRING string; // [rsp+60h] [rbp-29h] BYREF
  HSTRING v21; // [rsp+68h] [rbp-21h] BYREF
  HSTRING v22; // [rsp+70h] [rbp-19h] BYREF
  __int128 v23; // [rsp+78h] [rbp-11h] BYREF
  __int64 v24; // [rsp+88h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  v21 = a2;
  v23 = 0;
  v24 = 0;
  v18 = *a4;
  UpdateDiagnostics::update_diagnostics::_CreateHStringArray(&v23, &v18);
  string = 0;
  v10 = WindowsCreateString(*(PCNZWCH *)a3, *(_DWORD *)(a3 + 8), &string);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x15A,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
      (const char *)(unsigned int)v10,
      v17);
  v21 = 0;
  v18 = *a5;
  v11 = UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(&v18, &v21);
  v22 = 0;
  v18 = *a6;
  UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(&v18, &v22);
  v19 = 0;
  v12 = *(_QWORD *)(a1 + 8);
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, HSTRING))(*(_QWORD *)v12 + 72LL);
  v19 = 0;
  v14 = v13(
          v12,
          v23 & ((unsigned __int128)-(__int128)*((unsigned __int64 *)a4 + 1) >> 64),
          (__int64)(*((_QWORD *)&v23 + 1) - v23) >> 3,
          string);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
      (const char *)(unsigned int)v14,
      v11);
  v15 = v19;
  v19 = 0;
  *(_QWORD *)a2 = v15;
  if ( v22 )
    WindowsDeleteString(v22);
  if ( v21 )
    WindowsDeleteString(v21);
  if ( string )
    WindowsDeleteString(string);
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v23);
  return a2;
}

```

## disassembly

```asm
0x18001759c  push    rbp
0x18001759e  push    rbx
0x18001759f  push    rsi
0x1800175a0  push    rdi
0x1800175a1  push    r12
0x1800175a3  push    r14
0x1800175a5  push    r15
0x1800175a7  lea     rbp, [rsp-17h]
0x1800175ac  sub     rsp, 0A0h
0x1800175b3  mov     rax, cs:__security_cookie
0x1800175ba  xor     rax, rsp
0x1800175bd  mov     [rbp+47h+var_40], rax
0x1800175c1  mov     rsi, r9
0x1800175c4  mov     rbx, r8
0x1800175c7  mov     rdi, rdx
0x1800175ca  mov     r14, rcx
0x1800175cd  mov     [rbp+47h+var_68], rdx
0x1800175d1  mov     r15, [rbp+47h+arg_20]
0x1800175d5  mov     r12, [rbp+47h+arg_28]
0x1800175d9  xorps   xmm0, xmm0
0x1800175dc  xor     eax, eax
0x1800175de  movups  [rbp+47h+var_58], xmm0
0x1800175e2  mov     [rbp+47h+var_48], rax
0x1800175e6  movaps  xmm0, xmmword ptr [r9]
0x1800175ea  movdqa  [rbp+47h+var_90], xmm0
0x1800175ef  lea     rdx, [rbp+47h+var_90]
0x1800175f3  lea     rcx, [rbp+47h+var_58]
0x1800175f7  call    ?_CreateHStringArray@update_diagnostics@UpdateDiagnostics@@CA?AV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@4@@Z; UpdateDiagnostics::update_diagnostics::_CreateHStringArray(std::span<std::wstring_view const,-1>)
0x1800175fc  nop
0x1800175fd  mov     [rbp+47h+string], 0
0x180017605  lea     r8, [rbp+47h+string]; string
0x180017609  mov     edx, [rbx+8]; length
0x18001760c  mov     rcx, [rbx]; sourceString
0x18001760f  call    cs:__imp_WindowsCreateString
0x180017615  mov     rcx, [rbp+4Fh]; this
0x180017619  test    eax, eax
0x18001761b  js      loc_18001773E
0x180017621  mov     [rbp+47h+var_68], 0
0x180017629  movaps  xmm0, xmmword ptr [r15]
0x18001762d  movdqa  [rbp+47h+var_90], xmm0
0x180017632  lea     rdx, [rbp+47h+var_68]
0x180017636  lea     rcx, [rbp+47h+var_90]
0x18001763a  call    ?_CreateOptionalHString@update_diagnostics@UpdateDiagnostics@@CAPEAUHSTRING__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18001763f  mov     rbx, rax
0x180017642  mov     [rbp+47h+var_60], 0
0x18001764a  movaps  xmm0, xmmword ptr [r12]
0x18001764f  movdqa  [rbp+47h+var_90], xmm0
0x180017654  lea     rdx, [rbp+47h+var_60]
0x180017658  lea     rcx, [rbp+47h+var_90]
0x18001765c  call    ?_CreateOptionalHString@update_diagnostics@UpdateDiagnostics@@CAPEAUHSTRING__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UpdateDiagnostics::update_diagnostics::_CreateOptionalHString(std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180017661  mov     r9, rax
0x180017664  mov     [rbp+47h+var_78], 0
0x18001766c  mov     rcx, [r14+8]
0x180017670  mov     rax, [rcx]
0x180017673  mov     r10, [rax+48h]
0x180017677  mov     [rbp+47h+var_78], 0
0x18001767f  mov     r8, qword ptr [rbp+47h+var_58+8]
0x180017683  sub     r8, qword ptr [rbp+47h+var_58]
0x180017687  sar     r8, 3
0x18001768b  mov     rax, [rsi+8]
0x18001768f  neg     rax
0x180017692  sbb     rdx, rdx
0x180017695  and     rdx, qword ptr [rbp+47h+var_58]
0x180017699  lea     rax, [rbp+47h+var_78]
0x18001769d  mov     [rsp+0D0h+var_A0], rax
0x1800176a2  mov     [rsp+0D0h+var_A8], r9
0x1800176a7  mov     qword ptr [rsp+0D0h+var_B0], rbx; int
0x1800176ac  mov     r9, [rbp+47h+string]
0x1800176b0  mov     rax, r10
0x1800176b3  call    _guard_dispatch_icall
0x1800176b8  mov     rcx, [rbp+4Fh]; this
0x1800176bc  test    eax, eax
0x1800176be  js      short loc_180017729
0x1800176c0  mov     rax, [rbp+47h+var_78]
0x1800176c4  mov     [rbp+47h+var_78], 0
0x1800176cc  mov     [rdi], rax
0x1800176cf  mov     rcx, [rbp+47h+var_60]; string
0x1800176d3  test    rcx, rcx
0x1800176d6  jz      short loc_1800176DF
0x1800176d8  call    cs:__imp_WindowsDeleteString
0x1800176de  nop
0x1800176df  mov     rcx, [rbp+47h+var_68]; string
0x1800176e3  test    rcx, rcx
0x1800176e6  jz      short loc_1800176EF
0x1800176e8  call    cs:__imp_WindowsDeleteString
0x1800176ee  nop
0x1800176ef  mov     rcx, [rbp+47h+string]; string
0x1800176f3  test    rcx, rcx
0x1800176f6  jz      short loc_1800176FF
0x1800176f8  call    cs:__imp_WindowsDeleteString
0x1800176fe  nop
0x1800176ff  lea     rcx, [rbp+47h+var_58]
0x180017703  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180017708  mov     rax, rdi
0x18001770b  mov     rcx, [rbp+47h+var_40]
0x18001770f  xor     rcx, rsp; StackCookie
0x180017712  call    __security_check_cookie
0x180017717  add     rsp, 0A0h
0x18001771e  pop     r15
0x180017720  pop     r14
0x180017722  pop     r12
0x180017724  pop     rdi
0x180017725  pop     rsi
0x180017726  pop     rbx
0x180017727  pop     rbp
0x180017728  retn
0x180017729  mov     r9d, eax; char *
0x18001772c  lea     r8, aCW1SSrcCalliop_0; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x180017733  mov     edx, 169h; void *
0x180017738  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001773e  mov     r9d, eax; char *
0x180017741  lea     r8, aCW1SSrcCalliop_0; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x180017748  mov     edx, 15Ah; void *
0x18001774d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
