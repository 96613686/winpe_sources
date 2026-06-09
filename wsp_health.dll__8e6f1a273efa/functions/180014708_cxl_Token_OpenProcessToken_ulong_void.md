# cxl::Token::OpenProcessToken(ulong,void *)

- ea: `0x180014708`
- end: `0x180014871`
- name: `?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z`
- size: `361`
- prototype: `void(cxl::Token *__hidden this, unsigned int, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800198ec`
- `0x18001dc2c`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cde0`
- `0x18000ce84`
- `0x18000da34`
- `0x18000daf8`
- `0x18000ead0`
- `0x180011184`
- `0x18001432c`
- `0x180014620`
- `0x180014708`
- `0x180015578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001475f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001475f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014815`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014740`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014740`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800147bd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800147bd`

## string_xrefs

- `0x180014804`: `OpenProcessToken failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall cxl::Token::OpenProcessToken(void **this, DWORD a2, void *a3)
{
  const WCHAR *v6; // rax
  int v7; // [rsp+28h] [rbp-D8h]
  unsigned int LastError; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v10[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v11[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+90h] [rbp-70h] BYREF

  cxl::Token::Clear((cxl::Token *)this);
  if ( !OpenProcessToken(a3, a2, this + 1) )
  {
    if ( this[1] )
    {
      LastError = GetLastError();
      std::wstring::wstring(v10);
      cxl::StringWriter::StringWriter(v11, v10);
      LODWORD(v9) = 250;
      cxl::TextWriter::WriteLine<char,char [11],char [44],int,char [29],unsigned long>(
        (struct cxl::TextWriter *)v11,
        (__int64)&v9,
        v7,
        (__int64)&LastError);
      v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v10);
      OutputDebugStringW(v6);
      cxl::Debug::StopIfIsDebuggedOrCrash(LastError);
      v11[0] = &cxl::RefCounted::`vftable';
      std::wstring::_Tidy_deallocate(v10);
    }
    std::wstring::wstring(v11);
    cxl::StringWriter::StringWriter(v10, v11);
    cxl::TextWriter::WriteFmt<24>(v10, "OpenProcessToken failed");
    v9 = GetLastError();
    cxl::Exception::Exception(pExceptionObject, &v9, v11);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180014708  mov     [rsp-8+arg_18], rbx
0x18001470d  push    rbp
0x18001470e  push    rsi
0x18001470f  push    rdi
0x180014710  lea     rbp, [rsp-10h]
0x180014715  sub     rsp, 110h
0x18001471c  mov     rax, cs:__security_cookie
0x180014723  xor     rax, rsp
0x180014726  mov     [rbp+20h+var_20], rax
0x18001472a  mov     rsi, r8
0x18001472d  mov     edi, edx
0x18001472f  mov     rbx, rcx
0x180014732  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180014737  lea     r8, [rbx+8]; TokenHandle
0x18001473b  mov     edx, edi; DesiredAccess
0x18001473d  mov     rcx, rsi; ProcessHandle
0x180014740  call    cs:__imp_OpenProcessToken
0x180014747  nop     dword ptr [rax+rax+00h]
0x18001474c  test    eax, eax
0x18001474e  jnz     loc_180014851
0x180014754  cmp     qword ptr [rbx+8], 0
0x180014759  jz      loc_1800147E9
0x18001475f  call    cs:__imp_GetLastError
0x180014766  nop     dword ptr [rax+rax+00h]
0x18001476b  mov     [rsp+120h+var_E0], eax
0x18001476f  lea     rcx, [rsp+120h+var_D0]
0x180014774  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014779  nop
0x18001477a  lea     rdx, [rsp+120h+var_D0]
0x18001477f  lea     rcx, [rsp+120h+var_B0]
0x180014784  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180014789  nop
0x18001478a  mov     dword ptr [rsp+120h+var_DC], 0FAh
0x180014792  lea     rax, [rsp+120h+var_E0]
0x180014797  mov     [rsp+120h+var_F0], rax; __int64
0x18001479c  lea     rax, [rsp+120h+var_DC]
0x1800147a1  mov     [rsp+120h+var_100], rax; __int64
0x1800147a6  lea     rcx, [rsp+120h+var_B0]; struct cxl::TextWriter *
0x1800147ab  call    ??$WriteLine@D$$BY0L@D$$BY0CM@DH$$BY0BN@DK@TextWriter@cxl@@QEAAXPEBDAEAY0L@$$CBDAEAY0CM@$$CBDAEBHAEAY0BN@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [11],char [44],int,char [29],ulong>(char const *,char const (&)[11],char const (&)[44],int const &,char const (&)[29],ulong const &)
0x1800147b0  lea     rcx, [rsp+120h+var_D0]
0x1800147b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800147ba  mov     rcx, rax; lpOutputString
0x1800147bd  call    cs:__imp_OutputDebugStringW
0x1800147c4  nop     dword ptr [rax+rax+00h]
0x1800147c9  mov     ecx, [rsp+120h+var_E0]; unsigned int
0x1800147cd  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x1800147d2  nop
0x1800147d3  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x1800147da  mov     [rsp+120h+var_B0], rax
0x1800147df  lea     rcx, [rsp+120h+var_D0]
0x1800147e4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800147e9  lea     rcx, [rsp+120h+var_B0]
0x1800147ee  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800147f3  nop
0x1800147f4  lea     rdx, [rsp+120h+var_B0]
0x1800147f9  lea     rcx, [rsp+120h+var_D0]
0x1800147fe  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180014803  nop
0x180014804  lea     rdx, aOpenprocesstok; "OpenProcessToken failed"
0x18001480b  lea     rcx, [rsp+120h+var_D0]
0x180014810  call    ??$WriteFmt@$0BI@@TextWriter@cxl@@QEAAAEAV01@AEAY0BI@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<24>(char const (&)[24],cxl::Format const &)
0x180014815  call    cs:__imp_GetLastError
0x18001481c  nop     dword ptr [rax+rax+00h]
0x180014821  mov     dword ptr [rsp+120h+var_DC], eax
0x180014825  mov     dword ptr [rsp+120h+var_DC+4], 0
0x18001482d  lea     r8, [rsp+120h+var_B0]
0x180014832  lea     rdx, [rsp+120h+var_DC]
0x180014837  lea     rcx, [rbp+20h+pExceptionObject]
0x18001483b  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180014840  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180014847  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18001484b  call    _CxxThrowException_0
0x180014851  mov     rcx, [rbp+20h+var_20]
0x180014855  xor     rcx, rsp; StackCookie
0x180014858  call    __security_check_cookie
0x18001485d  mov     rbx, [rsp+120h+arg_18]
0x180014865  add     rsp, 110h
0x18001486c  pop     rdi
0x18001486d  pop     rsi
0x18001486e  pop     rbp
0x18001486f  retn
```
