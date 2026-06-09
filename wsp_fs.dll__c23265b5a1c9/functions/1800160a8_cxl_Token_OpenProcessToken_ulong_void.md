# cxl::Token::OpenProcessToken(ulong,void *)

- ea: `0x1800160a8`
- end: `0x180016211`
- name: `?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z`
- size: `361`
- prototype: `void(cxl::Token *__hidden this, unsigned int, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18001cabc`
- `0x180020f6c`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000aa10`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000e14c`
- `0x18000f120`
- `0x1800124ac`
- `0x18001584c`
- `0x180015be4`
- `0x1800160a8`
- `0x180016fb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800160e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800160e0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001615d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001615d`

## string_xrefs

- `0x1800161a4`: `OpenProcessToken failed`

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
0x1800160a8  mov     [rsp-8+arg_18], rbx
0x1800160ad  push    rbp
0x1800160ae  push    rsi
0x1800160af  push    rdi
0x1800160b0  lea     rbp, [rsp-10h]
0x1800160b5  sub     rsp, 110h
0x1800160bc  mov     rax, cs:__security_cookie
0x1800160c3  xor     rax, rsp
0x1800160c6  mov     [rbp+20h+var_20], rax
0x1800160ca  mov     rsi, r8
0x1800160cd  mov     edi, edx
0x1800160cf  mov     rbx, rcx
0x1800160d2  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x1800160d7  lea     r8, [rbx+8]; TokenHandle
0x1800160db  mov     edx, edi; DesiredAccess
0x1800160dd  mov     rcx, rsi; ProcessHandle
0x1800160e0  call    cs:__imp_OpenProcessToken
0x1800160e7  nop     dword ptr [rax+rax+00h]
0x1800160ec  test    eax, eax
0x1800160ee  jnz     loc_1800161F1
0x1800160f4  cmp     qword ptr [rbx+8], 0
0x1800160f9  jz      loc_180016189
0x1800160ff  call    cs:__imp_GetLastError
0x180016106  nop     dword ptr [rax+rax+00h]
0x18001610b  mov     [rsp+120h+var_E0], eax
0x18001610f  lea     rcx, [rsp+120h+var_D0]
0x180016114  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016119  nop
0x18001611a  lea     rdx, [rsp+120h+var_D0]
0x18001611f  lea     rcx, [rsp+120h+var_B0]
0x180016124  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180016129  nop
0x18001612a  mov     dword ptr [rsp+120h+var_DC], 0FAh
0x180016132  lea     rax, [rsp+120h+var_E0]
0x180016137  mov     [rsp+120h+var_F0], rax; __int64
0x18001613c  lea     rax, [rsp+120h+var_DC]
0x180016141  mov     [rsp+120h+var_100], rax; __int64
0x180016146  lea     rcx, [rsp+120h+var_B0]; struct cxl::TextWriter *
0x18001614b  call    ??$WriteLine@D$$BY0L@D$$BY0CM@DH$$BY0BN@DK@TextWriter@cxl@@QEAAXPEBDAEAY0L@$$CBDAEAY0CM@$$CBDAEBHAEAY0BN@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [11],char [44],int,char [29],ulong>(char const *,char const (&)[11],char const (&)[44],int const &,char const (&)[29],ulong const &)
0x180016150  lea     rcx, [rsp+120h+var_D0]
0x180016155  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001615a  mov     rcx, rax; lpOutputString
0x18001615d  call    cs:__imp_OutputDebugStringW
0x180016164  nop     dword ptr [rax+rax+00h]
0x180016169  mov     ecx, [rsp+120h+var_E0]; unsigned int
0x18001616d  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x180016172  nop
0x180016173  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001617a  mov     [rsp+120h+var_B0], rax
0x18001617f  lea     rcx, [rsp+120h+var_D0]
0x180016184  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016189  lea     rcx, [rsp+120h+var_B0]
0x18001618e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016193  nop
0x180016194  lea     rdx, [rsp+120h+var_B0]
0x180016199  lea     rcx, [rsp+120h+var_D0]
0x18001619e  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800161a3  nop
0x1800161a4  lea     rdx, aOpenprocesstok; "OpenProcessToken failed"
0x1800161ab  lea     rcx, [rsp+120h+var_D0]
0x1800161b0  call    ??$WriteFmt@$0BI@@TextWriter@cxl@@QEAAAEAV01@AEAY0BI@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<24>(char const (&)[24],cxl::Format const &)
0x1800161b5  call    cs:__imp_GetLastError
0x1800161bc  nop     dword ptr [rax+rax+00h]
0x1800161c1  mov     dword ptr [rsp+120h+var_DC], eax
0x1800161c5  mov     dword ptr [rsp+120h+var_DC+4], 0
0x1800161cd  lea     r8, [rsp+120h+var_B0]
0x1800161d2  lea     rdx, [rsp+120h+var_DC]
0x1800161d7  lea     rcx, [rbp+20h+pExceptionObject]
0x1800161db  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800161e0  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800161e7  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x1800161eb  call    _CxxThrowException_0
0x1800161f1  mov     rcx, [rbp+20h+var_20]
0x1800161f5  xor     rcx, rsp; StackCookie
0x1800161f8  call    __security_check_cookie
0x1800161fd  mov     rbx, [rsp+120h+arg_18]
0x180016205  add     rsp, 110h
0x18001620c  pop     rdi
0x18001620d  pop     rsi
0x18001620e  pop     rbp
0x18001620f  retn
```
