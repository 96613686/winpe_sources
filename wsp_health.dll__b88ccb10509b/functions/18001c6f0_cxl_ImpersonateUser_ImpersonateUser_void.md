# cxl::ImpersonateUser::~ImpersonateUser(void)

- ea: `0x18001c6f0`
- end: `0x18001c7b8`
- name: `??1ImpersonateUser@cxl@@QEAA@XZ`
- size: `200`
- prototype: `void __fastcall(cxl::ImpersonateUser *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18001ba54`
- `0x18007b094`
- `0x18008521e`
- `0x18008a5be`

## callees

- `0x180002ae0`
- `0x18000ca34`
- `0x18000d618`
- `0x18000d6dc`
- `0x180010ca4`
- `0x180013ec0`
- `0x180014dc0`
- `0x18001bbe4`
- `0x18001c6f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c723`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001c719`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001c719`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001c770`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001c770`

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
0x18001c6f0  mov     [rsp-8+arg_8], rbx
0x18001c6f5  push    rbp
0x18001c6f6  lea     rbp, [rsp-57h]
0x18001c6fb  sub     rsp, 90h
0x18001c702  mov     rax, cs:__security_cookie
0x18001c709  xor     rax, rsp
0x18001c70c  mov     [rbp+57h+var_8], rax
0x18001c710  mov     rbx, rcx
0x18001c713  mov     rdx, [rcx+8]; Token
0x18001c717  xor     ecx, ecx; Thread
0x18001c719  call    cs:__imp_SetThreadToken
0x18001c71f  test    eax, eax
0x18001c721  jnz     short loc_18001C792
0x18001c723  call    cs:__imp_GetLastError
0x18001c729  mov     [rbp+57h+var_50], eax
0x18001c72c  lea     rcx, [rbp+57h+var_28]
0x18001c730  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001c735  lea     rdx, [rbp+57h+var_28]
0x18001c739  lea     rcx, [rbp+57h+var_4C+4]
0x18001c73d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001c742  mov     dword ptr [rbp+57h+var_4C], 2F6h
0x18001c749  lea     rax, [rbp+57h+var_50]
0x18001c74d  mov     [rsp+90h+var_60], rax; __int64
0x18001c752  lea     rax, [rbp+57h+var_4C]
0x18001c756  mov     [rsp+90h+var_70], rax; __int64
0x18001c75b  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001c75f  call    ??$WriteLine@D$$BY0DA@D$$BY0DJ@DH$$BY0CH@DK@TextWriter@cxl@@QEAAXPEBDAEAY0DA@$$CBDAEAY0DJ@$$CBDAEBHAEAY0CH@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [48],char [57],int,char [39],ulong>(char const *,char const (&)[48],char const (&)[57],int const &,char const (&)[39],ulong const &)
0x18001c764  lea     rcx, [rbp+57h+var_28]
0x18001c768  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c76d  mov     rcx, rax; lpOutputString
0x18001c770  call    cs:__imp_OutputDebugStringW
0x18001c776  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001c779  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001c77e  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001c785  mov     [rbp+57h+var_4C+4], rax
0x18001c789  lea     rcx, [rbp+57h+var_28]
0x18001c78d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c792  mov     rcx, rbx; this
0x18001c795  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001c79a  nop
0x18001c79b  mov     rcx, [rbp+57h+var_8]
0x18001c79f  xor     rcx, rsp; StackCookie
0x18001c7a2  call    __security_check_cookie
0x18001c7a7  mov     rbx, [rsp+90h+arg_8]
0x18001c7af  add     rsp, 90h
0x18001c7b6  pop     rbp
0x18001c7b7  retn
```
