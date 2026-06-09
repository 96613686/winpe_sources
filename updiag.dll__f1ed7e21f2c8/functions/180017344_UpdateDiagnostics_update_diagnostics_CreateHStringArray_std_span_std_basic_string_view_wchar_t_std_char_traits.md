# UpdateDiagnostics::update_diagnostics::_CreateHStringArray(std::span<std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const,-1>)

- ea: `0x180017344`
- end: `0x18001744a`
- name: `?_CreateHStringArray@update_diagnostics@UpdateDiagnostics@@CA?AV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@4@@Z`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180016e7c`
- `0x18001759c`

## callees

- `0x180009548`
- `0x180016fe0`
- `0x1800171e8`
- `0x180017344`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800173c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800173c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017406`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall UpdateDiagnostics::update_diagnostics::_CreateHStringArray(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rsi
  __int64 v5; // rsi
  HRESULT v6; // eax
  HSTRING *v7; // rdx
  HSTRING v8; // rcx
  HSTRING string; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *a2;
  *(_OWORD *)a1 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v4 = a2[1];
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reserve(
    a1,
    v4);
  v5 = v2 + 16 * v4;
  while ( v2 != v5 )
  {
    if ( *(_QWORD *)(v2 + 8) )
    {
      string = 0;
      v6 = WindowsCreateString(*(PCNZWCH *)v2, *(_DWORD *)(v2 + 8), &string);
      if ( v6 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
          (const char *)(unsigned int)v6,
          1);
      v7 = (HSTRING *)a1[1];
      if ( v7 == (HSTRING *)a1[2] )
      {
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
          a1,
          v7,
          (__int64 *)&string);
        v8 = string;
      }
      else
      {
        *v7 = string;
        v8 = 0;
        string = 0;
        a1[1] += 8LL;
      }
      if ( v8 )
        WindowsDeleteString(v8);
    }
    v2 += 16;
  }
  return a1;
}

```

## disassembly

```asm
0x180017344  mov     [rsp+arg_10], rbx
0x180017349  mov     [rsp+arg_18], rsi
0x18001734e  push    rdi
0x18001734f  sub     rsp, 40h
0x180017353  mov     rax, cs:__security_cookie
0x18001735a  xor     rax, rsp
0x18001735d  mov     [rsp+48h+var_10], rax
0x180017362  mov     rbx, [rdx]
0x180017365  mov     rdi, rcx
0x180017368  mov     [rsp+48h+var_20], rcx
0x18001736d  mov     [rsp+48h+var_28], 0
0x180017375  xorps   xmm0, xmm0
0x180017378  xor     eax, eax
0x18001737a  movups  xmmword ptr [rcx], xmm0
0x18001737d  mov     [rcx], rax
0x180017380  mov     [rcx+8], rax
0x180017384  mov     [rcx+10h], rax
0x180017388  mov     [rsp+48h+var_28], 1
0x180017390  mov     rsi, [rdx+8]
0x180017394  mov     rdx, rsi
0x180017397  call    ?reserve@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX_K@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x18001739c  shl     rsi, 4
0x1800173a0  add     rsi, rbx
0x1800173a3  jmp     short loc_180017410
0x1800173a5  cmp     qword ptr [rbx+8], 0
0x1800173aa  jz      short loc_18001740C
0x1800173ac  mov     [rsp+48h+string], 0
0x1800173b5  lea     r8, [rsp+48h+string]; string
0x1800173ba  mov     edx, [rbx+8]; length
0x1800173bd  mov     rcx, [rbx]; sourceString
0x1800173c0  call    cs:__imp_WindowsCreateString
0x1800173c6  mov     rcx, [rsp+48h]; this
0x1800173cb  test    eax, eax
0x1800173cd  js      short loc_180017435
0x1800173cf  mov     rdx, [rdi+8]
0x1800173d3  cmp     rdx, [rdi+10h]
0x1800173d7  jz      short loc_1800173EF
0x1800173d9  mov     rax, [rsp+48h+string]
0x1800173de  mov     [rdx], rax
0x1800173e1  xor     ecx, ecx
0x1800173e3  mov     [rsp+48h+string], rcx
0x1800173e8  add     qword ptr [rdi+8], 8
0x1800173ed  jmp     short loc_180017401
0x1800173ef  lea     r8, [rsp+48h+string]
0x1800173f4  mov     rcx, rdi
0x1800173f7  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x1800173fc  mov     rcx, [rsp+48h+string]; string
0x180017401  test    rcx, rcx
0x180017404  jz      short loc_18001740C
0x180017406  call    cs:__imp_WindowsDeleteString
0x18001740c  add     rbx, 10h
0x180017410  cmp     rbx, rsi
0x180017413  jnz     short loc_1800173A5
0x180017415  mov     rax, rdi
0x180017418  mov     rcx, [rsp+48h+var_10]
0x18001741d  xor     rcx, rsp; StackCookie
0x180017420  call    __security_check_cookie
0x180017425  mov     rbx, [rsp+48h+arg_10]
0x18001742a  mov     rsi, [rsp+48h+arg_18]
0x18001742f  add     rsp, 40h
0x180017433  pop     rdi
0x180017434  retn
0x180017435  mov     r9d, eax; char *
0x180017438  lea     r8, aCW1SSrcCalliop_0; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x18001743f  mov     edx, 1AEh; void *
0x180017444  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
