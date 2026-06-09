# cxl::ImpersonateUser::~ImpersonateUser(void)

- ea: `0x180020578`
- end: `0x180020653`
- name: `??1ImpersonateUser@cxl@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(cxl::ImpersonateUser *__hidden this)`
- caller_count: `12`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18001f84c`
- `0x18005cb90`
- `0x1800620cc`
- `0x180066300`
- `0x180067238`
- `0x180067a9c`
- `0x180067e54`
- `0x18009d585`
- `0x1800a5c37`
- `0x1800a639d`
- `0x1800a65a6`
- `0x1800a667f`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000d600`
- `0x18000e14c`
- `0x1800124ac`
- `0x180015be4`
- `0x180016fb8`
- `0x18001f9e4`
- `0x180020578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205b1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800205a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800205a1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020604`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020604`

## pseudocode

```c
void __fastcall cxl::ImpersonateUser::~ImpersonateUser(HANDLE *this)
{
  const WCHAR *v2; // rax
  int v3; // [rsp+28h] [rbp-11h]
  unsigned int LastError; // [rsp+40h] [rbp+7h] BYREF
  int v5; // [rsp+44h] [rbp+Bh] BYREF
  _QWORD v6[4]; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v7[32]; // [rsp+68h] [rbp+2Fh] BYREF

  if ( !SetThreadToken(0, this[1]) )
  {
    LastError = GetLastError();
    std::wstring::wstring(v7);
    cxl::StringWriter::StringWriter(v6, v7);
    v5 = 758;
    cxl::TextWriter::WriteLine<char,char [48],char [57],int,char [39],unsigned long>(
      (struct cxl::TextWriter *)v6,
      (__int64)&v5,
      v3,
      (__int64)&LastError);
    v2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7);
    OutputDebugStringW(v2);
    cxl::Debug::StopIfIsDebuggedOrCrash(LastError);
    v6[0] = &cxl::RefCounted::`vftable';
    std::wstring::_Tidy_deallocate(v7);
  }
  cxl::Token::Clear((cxl::Token *)this);
}

```

## disassembly

```asm
0x180020578  mov     [rsp-8+arg_8], rbx
0x18002057d  push    rbp
0x18002057e  lea     rbp, [rsp-57h]
0x180020583  sub     rsp, 90h
0x18002058a  mov     rax, cs:__security_cookie
0x180020591  xor     rax, rsp
0x180020594  mov     [rbp+57h+var_8], rax
0x180020598  mov     rbx, rcx
0x18002059b  mov     rdx, [rcx+8]; Token
0x18002059f  xor     ecx, ecx; Thread
0x1800205a1  call    cs:__imp_SetThreadToken
0x1800205a8  nop     dword ptr [rax+rax+00h]
0x1800205ad  test    eax, eax
0x1800205af  jnz     short loc_18002062C
0x1800205b1  call    cs:__imp_GetLastError
0x1800205b8  nop     dword ptr [rax+rax+00h]
0x1800205bd  mov     [rbp+57h+var_50], eax
0x1800205c0  lea     rcx, [rbp+57h+var_28]
0x1800205c4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800205c9  lea     rdx, [rbp+57h+var_28]
0x1800205cd  lea     rcx, [rbp+57h+var_4C+4]
0x1800205d1  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800205d6  mov     dword ptr [rbp+57h+var_4C], 2F6h
0x1800205dd  lea     rax, [rbp+57h+var_50]
0x1800205e1  mov     [rsp+90h+var_60], rax; __int64
0x1800205e6  lea     rax, [rbp+57h+var_4C]
0x1800205ea  mov     [rsp+90h+var_70], rax; __int64
0x1800205ef  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x1800205f3  call    ??$WriteLine@D$$BY0DA@D$$BY0DJ@DH$$BY0CH@DK@TextWriter@cxl@@QEAAXPEBDAEAY0DA@$$CBDAEAY0DJ@$$CBDAEBHAEAY0CH@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [48],char [57],int,char [39],ulong>(char const *,char const (&)[48],char const (&)[57],int const &,char const (&)[39],ulong const &)
0x1800205f8  lea     rcx, [rbp+57h+var_28]
0x1800205fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020601  mov     rcx, rax; lpOutputString
0x180020604  call    cs:__imp_OutputDebugStringW
0x18002060b  nop     dword ptr [rax+rax+00h]
0x180020610  mov     ecx, [rbp+57h+var_50]; unsigned int
0x180020613  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x180020618  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18002061f  mov     [rbp+57h+var_4C+4], rax
0x180020623  lea     rcx, [rbp+57h+var_28]
0x180020627  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002062c  mov     rcx, rbx; this
0x18002062f  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180020634  nop
0x180020635  mov     rcx, [rbp+57h+var_8]
0x180020639  xor     rcx, rsp; StackCookie
0x18002063c  call    __security_check_cookie
0x180020641  mov     rbx, [rsp+90h+arg_8]
0x180020649  add     rsp, 90h
0x180020650  pop     rbp
0x180020651  retn
```
