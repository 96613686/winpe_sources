# cxl::ImpersonateUser::~ImpersonateUser(void)

- ea: `0x18001d234`
- end: `0x18001d30f`
- name: `??1ImpersonateUser@cxl@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(cxl::ImpersonateUser *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18001c578`
- `0x18007d22c`
- `0x180087644`
- `0x18008cb17`

## callees

- `0x180002b50`
- `0x18000cde0`
- `0x18000da34`
- `0x18000daf8`
- `0x180011184`
- `0x180014620`
- `0x180015578`
- `0x18001c70c`
- `0x18001d234`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d26d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d26d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001d25d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001d25d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d2c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d2c0`

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
0x18001d234  mov     [rsp-8+arg_8], rbx
0x18001d239  push    rbp
0x18001d23a  lea     rbp, [rsp-57h]
0x18001d23f  sub     rsp, 90h
0x18001d246  mov     rax, cs:__security_cookie
0x18001d24d  xor     rax, rsp
0x18001d250  mov     [rbp+57h+var_8], rax
0x18001d254  mov     rbx, rcx
0x18001d257  mov     rdx, [rcx+8]; Token
0x18001d25b  xor     ecx, ecx; Thread
0x18001d25d  call    cs:__imp_SetThreadToken
0x18001d264  nop     dword ptr [rax+rax+00h]
0x18001d269  test    eax, eax
0x18001d26b  jnz     short loc_18001D2E8
0x18001d26d  call    cs:__imp_GetLastError
0x18001d274  nop     dword ptr [rax+rax+00h]
0x18001d279  mov     [rbp+57h+var_50], eax
0x18001d27c  lea     rcx, [rbp+57h+var_28]
0x18001d280  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d285  lea     rdx, [rbp+57h+var_28]
0x18001d289  lea     rcx, [rbp+57h+var_4C+4]
0x18001d28d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001d292  mov     dword ptr [rbp+57h+var_4C], 2F6h
0x18001d299  lea     rax, [rbp+57h+var_50]
0x18001d29d  mov     [rsp+90h+var_60], rax; __int64
0x18001d2a2  lea     rax, [rbp+57h+var_4C]
0x18001d2a6  mov     [rsp+90h+var_70], rax; __int64
0x18001d2ab  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001d2af  call    ??$WriteLine@D$$BY0DA@D$$BY0DJ@DH$$BY0CH@DK@TextWriter@cxl@@QEAAXPEBDAEAY0DA@$$CBDAEAY0DJ@$$CBDAEBHAEAY0CH@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [48],char [57],int,char [39],ulong>(char const *,char const (&)[48],char const (&)[57],int const &,char const (&)[39],ulong const &)
0x18001d2b4  lea     rcx, [rbp+57h+var_28]
0x18001d2b8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d2bd  mov     rcx, rax; lpOutputString
0x18001d2c0  call    cs:__imp_OutputDebugStringW
0x18001d2c7  nop     dword ptr [rax+rax+00h]
0x18001d2cc  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001d2cf  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001d2d4  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001d2db  mov     [rbp+57h+var_4C+4], rax
0x18001d2df  lea     rcx, [rbp+57h+var_28]
0x18001d2e3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d2e8  mov     rcx, rbx; this
0x18001d2eb  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001d2f0  nop
0x18001d2f1  mov     rcx, [rbp+57h+var_8]
0x18001d2f5  xor     rcx, rsp; StackCookie
0x18001d2f8  call    __security_check_cookie
0x18001d2fd  mov     rbx, [rsp+90h+arg_8]
0x18001d305  add     rsp, 90h
0x18001d30c  pop     rbp
0x18001d30d  retn
```
