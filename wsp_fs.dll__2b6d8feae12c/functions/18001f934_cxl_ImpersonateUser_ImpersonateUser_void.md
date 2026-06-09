# cxl::ImpersonateUser::~ImpersonateUser(void)

- ea: `0x18001f934`
- end: `0x18001f9fc`
- name: `??1ImpersonateUser@cxl@@QEAA@XZ`
- size: `200`
- prototype: `void __fastcall(cxl::ImpersonateUser *__hidden this)`
- caller_count: `12`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18001ec28`
- `0x18005ba54`
- `0x180060e9c`
- `0x180065030`
- `0x180065f54`
- `0x1800667cc`
- `0x180066b84`
- `0x18009b0de`
- `0x1800a3a35`
- `0x1800a418d`
- `0x1800a43a8`
- `0x1800a4480`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000d298`
- `0x18000dd74`
- `0x180012028`
- `0x1800154e0`
- `0x180016830`
- `0x18001edbc`
- `0x18001f934`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f967`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f95d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f95d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f9b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f9b4`

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
0x18001f934  mov     [rsp-8+arg_8], rbx
0x18001f939  push    rbp
0x18001f93a  lea     rbp, [rsp-57h]
0x18001f93f  sub     rsp, 90h
0x18001f946  mov     rax, cs:__security_cookie
0x18001f94d  xor     rax, rsp
0x18001f950  mov     [rbp+57h+var_8], rax
0x18001f954  mov     rbx, rcx
0x18001f957  mov     rdx, [rcx+8]; Token
0x18001f95b  xor     ecx, ecx; Thread
0x18001f95d  call    cs:__imp_SetThreadToken
0x18001f963  test    eax, eax
0x18001f965  jnz     short loc_18001F9D6
0x18001f967  call    cs:__imp_GetLastError
0x18001f96d  mov     [rbp+57h+var_50], eax
0x18001f970  lea     rcx, [rbp+57h+var_28]
0x18001f974  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f979  lea     rdx, [rbp+57h+var_28]
0x18001f97d  lea     rcx, [rbp+57h+var_4C+4]
0x18001f981  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001f986  mov     dword ptr [rbp+57h+var_4C], 2F6h
0x18001f98d  lea     rax, [rbp+57h+var_50]
0x18001f991  mov     [rsp+90h+var_60], rax; __int64
0x18001f996  lea     rax, [rbp+57h+var_4C]
0x18001f99a  mov     [rsp+90h+var_70], rax; __int64
0x18001f99f  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001f9a3  call    ??$WriteLine@D$$BY0DA@D$$BY0DJ@DH$$BY0CH@DK@TextWriter@cxl@@QEAAXPEBDAEAY0DA@$$CBDAEAY0DJ@$$CBDAEBHAEAY0CH@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [48],char [57],int,char [39],ulong>(char const *,char const (&)[48],char const (&)[57],int const &,char const (&)[39],ulong const &)
0x18001f9a8  lea     rcx, [rbp+57h+var_28]
0x18001f9ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001f9b1  mov     rcx, rax; lpOutputString
0x18001f9b4  call    cs:__imp_OutputDebugStringW
0x18001f9ba  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001f9bd  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001f9c2  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001f9c9  mov     [rbp+57h+var_4C+4], rax
0x18001f9cd  lea     rcx, [rbp+57h+var_28]
0x18001f9d1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f9d6  mov     rcx, rbx; this
0x18001f9d9  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001f9de  nop
0x18001f9df  mov     rcx, [rbp+57h+var_8]
0x18001f9e3  xor     rcx, rsp; StackCookie
0x18001f9e6  call    __security_check_cookie
0x18001f9eb  mov     rbx, [rsp+90h+arg_8]
0x18001f9f3  add     rsp, 90h
0x18001f9fa  pop     rbp
0x18001f9fb  retn
```
