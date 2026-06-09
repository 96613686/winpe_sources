# Diagnostics::CliAnalyze::PrintAnalyzerTitle(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18001046c`
- end: `0x1800105f6`
- name: `?PrintAnalyzerTitle@CliAnalyze@Diagnostics@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000f290`

## callees

- `0x180009548`
- `0x18001046c`
- `0x1800106e8`
- `0x18001095c`
- `0x180011be4`
- `0x18008fe00`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800104d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800104d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001059b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001059b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001055f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001055f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Diagnostics::CliAnalyze::PrintAnalyzerTitle(__int64 a1, __m128i *a2)
{
  __m128i v4; // xmm1
  HRESULT v5; // eax
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  HSTRING v9; // rbx
  PCWSTR StringRawBuffer; // rsi
  unsigned int v11; // edi
  __int64 v12; // rax
  int v14; // [rsp+20h] [rbp-28h]
  HSTRING v15; // [rsp+28h] [rbp-20h] BYREF
  HSTRING string; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(
    (__int64)&std::wcout,
    a2->m128i_i64[0],
    _mm_srli_si128(*a2, 8).m128i_u64[0]);
  v4 = *a2;
  string = 0;
  v5 = WindowsCreateString((PCNZWCH)v4.m128i_i64[0], _mm_srli_si128(v4, 8).m128i_u32[0], &string);
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
        (const char *)(unsigned int)v5,
        v14);
    v15 = 0;
    v6 = *(__int64 **)(a1 + 616);
    v7 = *v6;
    v15 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v7 + 48))(v6, string, &v15);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xFB,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
        (const char *)(unsigned int)v8,
        v14);
    v9 = v15;
    v15 = 0;
    if ( string )
      WindowsDeleteString(string);
    if ( v9 )
    {
      LODWORD(v15) = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(v9, (UINT32 *)&v15);
      v11 = (unsigned int)v15;
      if ( (_DWORD)v15 )
      {
        v12 = std::operator<<<wchar_t,std::char_traits<wchar_t>>((__int64)&std::wcout, (__int64)L" - ");
        std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v12, (__int64)StringRawBuffer, v11);
      }
    }
    if ( v9 )
      WindowsDeleteString(v9);
  }
  catch ( ... )
  {
  }
  return std::endl<wchar_t,std::char_traits<wchar_t>>(&std::wcout);
}

```

## disassembly

```asm
0x18001046c  mov     [rsp+arg_10], rbx
0x180010471  mov     [rsp+arg_18], rsi
0x180010476  push    rdi
0x180010477  sub     rsp, 40h
0x18001047b  mov     rax, cs:__security_cookie
0x180010482  xor     rax, rsp
0x180010485  mov     [rsp+48h+var_10], rax
0x18001048a  mov     rbx, rdx
0x18001048d  mov     rdi, rcx
0x180010490  movaps  xmm1, xmmword ptr [rdx]
0x180010493  movdqa  xmm0, xmm1
0x180010497  psrldq  xmm0, 8
0x18001049c  movq    r8, xmm0
0x1800104a1  movq    rdx, xmm1
0x1800104a6  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x1800104ad  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x1800104b2  nop
0x1800104b3  movaps  xmm1, xmmword ptr [rbx]
0x1800104b6  mov     [rsp+48h+string], 0
0x1800104bf  lea     r8, [rsp+48h+string]; string
0x1800104c4  movdqa  xmm0, xmm1
0x1800104c8  psrldq  xmm0, 8
0x1800104cd  movq    rdx, xmm0; length
0x1800104d2  movq    rcx, xmm1; sourceString
0x1800104d7  call    cs:__imp_WindowsCreateString
0x1800104dd  mov     rcx, [rsp+48h]; this
0x1800104e2  test    eax, eax
0x1800104e4  js      loc_1800105CB
0x1800104ea  mov     [rsp+48h+var_20], 0
0x1800104f3  mov     rcx, [rdi+268h]
0x1800104fa  mov     rax, [rcx]
0x1800104fd  mov     [rsp+48h+var_20], 0
0x180010506  lea     r8, [rsp+48h+var_20]
0x18001050b  mov     rdx, [rsp+48h+string]
0x180010510  mov     rax, [rax+30h]
0x180010514  call    _guard_dispatch_icall
0x180010519  mov     rcx, [rsp+48h]; this
0x18001051e  test    eax, eax
0x180010520  js      loc_1800105E0
0x180010526  mov     rbx, [rsp+48h+var_20]
0x18001052b  mov     [rsp+48h+var_20], 0
0x180010534  mov     [rsp+48h+var_28], rbx
0x180010539  mov     rcx, [rsp+48h+string]; string
0x18001053e  test    rcx, rcx
0x180010541  jz      short loc_18001054A
0x180010543  call    cs:__imp_WindowsDeleteString
0x180010549  nop
0x18001054a  test    rbx, rbx
0x18001054d  jz      short loc_180010593
0x18001054f  mov     dword ptr [rsp+48h+var_20], 0
0x180010557  lea     rdx, [rsp+48h+var_20]; length
0x18001055c  mov     rcx, rbx; string
0x18001055f  call    cs:__imp_WindowsGetStringRawBuffer
0x180010565  mov     rsi, rax
0x180010568  mov     edi, dword ptr [rsp+48h+var_20]
0x18001056c  test    rdi, rdi
0x18001056f  jz      short loc_180010593
0x180010571  lea     rdx, asc_1800A3200; " - "
0x180010578  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x18001057f  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180010584  mov     r8d, edi
0x180010587  mov     rdx, rsi
0x18001058a  mov     rcx, rax
0x18001058d  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180010592  nop
0x180010593  test    rbx, rbx
0x180010596  jz      short loc_1800105A2
0x180010598  mov     rcx, rbx; string
0x18001059b  call    cs:__imp_WindowsDeleteString
0x1800105a1  nop
0x1800105a2  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x1800105a9  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x1800105ae  mov     rcx, [rsp+48h+var_10]
0x1800105b3  xor     rcx, rsp; StackCookie
0x1800105b6  call    __security_check_cookie
0x1800105bb  mov     rbx, [rsp+48h+arg_10]
0x1800105c0  mov     rsi, [rsp+48h+arg_18]
0x1800105c5  add     rsp, 40h
0x1800105c9  pop     rdi
0x1800105ca  retn
0x1800105cb  mov     r9d, eax; char *
0x1800105ce  lea     r8, aCW1SSrcCalliop_0; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x1800105d5  mov     edx, 0F9h; void *
0x1800105da  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800105e0  mov     r9d, eax; char *
0x1800105e3  lea     r8, aCW1SSrcCalliop_0; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x1800105ea  mov     edx, 0FBh; void *
0x1800105ef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
