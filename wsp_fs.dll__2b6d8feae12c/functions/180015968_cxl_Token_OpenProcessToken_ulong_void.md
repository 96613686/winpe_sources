# cxl::Token::OpenProcessToken(ulong,void *)

- ea: `0x180015968`
- end: `0x180015ab4`
- name: `?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z`
- size: `332`
- prototype: `void(cxl::Token *__hidden this, unsigned int, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18001bffc`
- `0x1800202e4`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000a6dc`
- `0x18000d298`
- `0x18000d33c`
- `0x18000dd74`
- `0x18000ece0`
- `0x180012028`
- `0x180015154`
- `0x1800154e0`
- `0x180015968`
- `0x180016830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a5f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800159a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800159a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015a0d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015a0d`

## string_xrefs

- `0x180015a4e`: `OpenProcessToken failed`

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
    cxl::TextWriter::WriteFmt<24>((__int64)v10, (__int64)"OpenProcessToken failed");
    v9 = GetLastError();
    cxl::Exception::Exception(pExceptionObject, &v9, v11);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180015968  mov     [rsp-8+arg_18], rbx
0x18001596d  push    rbp
0x18001596e  push    rsi
0x18001596f  push    rdi
0x180015970  lea     rbp, [rsp-10h]
0x180015975  sub     rsp, 110h
0x18001597c  mov     rax, cs:__security_cookie
0x180015983  xor     rax, rsp
0x180015986  mov     [rbp+20h+var_20], rax
0x18001598a  mov     rsi, r8
0x18001598d  mov     edi, edx
0x18001598f  mov     rbx, rcx
0x180015992  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180015997  lea     r8, [rbx+8]; TokenHandle
0x18001599b  mov     edx, edi; DesiredAccess
0x18001599d  mov     rcx, rsi; ProcessHandle
0x1800159a0  call    cs:__imp_OpenProcessToken
0x1800159a6  test    eax, eax
0x1800159a8  jnz     loc_180015A95
0x1800159ae  cmp     qword ptr [rbx+8], 0
0x1800159b3  jz      short loc_180015A33
0x1800159b5  call    cs:__imp_GetLastError
0x1800159bb  mov     [rsp+120h+var_E0], eax
0x1800159bf  lea     rcx, [rsp+120h+var_D0]
0x1800159c4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800159c9  nop
0x1800159ca  lea     rdx, [rsp+120h+var_D0]
0x1800159cf  lea     rcx, [rsp+120h+var_B0]
0x1800159d4  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800159d9  nop
0x1800159da  mov     dword ptr [rsp+120h+var_DC], 0FAh
0x1800159e2  lea     rax, [rsp+120h+var_E0]
0x1800159e7  mov     [rsp+120h+var_F0], rax; __int64
0x1800159ec  lea     rax, [rsp+120h+var_DC]
0x1800159f1  mov     [rsp+120h+var_100], rax; __int64
0x1800159f6  lea     rcx, [rsp+120h+var_B0]; struct cxl::TextWriter *
0x1800159fb  call    ??$WriteLine@D$$BY0L@D$$BY0CM@DH$$BY0BN@DK@TextWriter@cxl@@QEAAXPEBDAEAY0L@$$CBDAEAY0CM@$$CBDAEBHAEAY0BN@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [11],char [44],int,char [29],ulong>(char const *,char const (&)[11],char const (&)[44],int const &,char const (&)[29],ulong const &)
0x180015a00  lea     rcx, [rsp+120h+var_D0]
0x180015a05  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180015a0a  mov     rcx, rax; lpOutputString
0x180015a0d  call    cs:__imp_OutputDebugStringW
0x180015a13  mov     ecx, [rsp+120h+var_E0]; unsigned int
0x180015a17  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x180015a1c  nop
0x180015a1d  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x180015a24  mov     [rsp+120h+var_B0], rax
0x180015a29  lea     rcx, [rsp+120h+var_D0]
0x180015a2e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015a33  lea     rcx, [rsp+120h+var_B0]
0x180015a38  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015a3d  nop
0x180015a3e  lea     rdx, [rsp+120h+var_B0]
0x180015a43  lea     rcx, [rsp+120h+var_D0]
0x180015a48  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180015a4d  nop
0x180015a4e  lea     rdx, aOpenprocesstok; "OpenProcessToken failed"
0x180015a55  lea     rcx, [rsp+120h+var_D0]
0x180015a5a  call    ??$WriteFmt@$0BI@@TextWriter@cxl@@QEAAAEAV01@AEAY0BI@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<24>(char const (&)[24],cxl::Format const &)
0x180015a5f  call    cs:__imp_GetLastError
0x180015a65  mov     dword ptr [rsp+120h+var_DC], eax
0x180015a69  mov     dword ptr [rsp+120h+var_DC+4], 0
0x180015a71  lea     r8, [rsp+120h+var_B0]
0x180015a76  lea     rdx, [rsp+120h+var_DC]
0x180015a7b  lea     rcx, [rbp+20h+pExceptionObject]
0x180015a7f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180015a84  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180015a8b  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x180015a8f  call    _CxxThrowException_0
0x180015a95  mov     rcx, [rbp+20h+var_20]
0x180015a99  xor     rcx, rsp; StackCookie
0x180015a9c  call    __security_check_cookie
0x180015aa1  mov     rbx, [rsp+120h+arg_18]
0x180015aa9  add     rsp, 110h
0x180015ab0  pop     rdi
0x180015ab1  pop     rsi
0x180015ab2  pop     rbp
0x180015ab3  retn
```
