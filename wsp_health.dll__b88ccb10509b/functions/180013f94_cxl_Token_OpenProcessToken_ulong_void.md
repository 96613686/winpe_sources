# cxl::Token::OpenProcessToken(ulong,void *)

- ea: `0x180013f94`
- end: `0x1800140e0`
- name: `?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z`
- size: `332`
- prototype: `void(cxl::Token *__hidden this, unsigned int, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180018f1c`
- `0x18001d094`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000ca34`
- `0x18000cad8`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e640`
- `0x180010ca4`
- `0x180013be4`
- `0x180013ec0`
- `0x180013f94`
- `0x180014dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001408b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001408b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013fcc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013fcc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014039`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014039`

## string_xrefs

- `0x18001407a`: `OpenProcessToken failed`

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
0x180013f94  mov     [rsp-8+arg_18], rbx
0x180013f99  push    rbp
0x180013f9a  push    rsi
0x180013f9b  push    rdi
0x180013f9c  lea     rbp, [rsp-10h]
0x180013fa1  sub     rsp, 110h
0x180013fa8  mov     rax, cs:__security_cookie
0x180013faf  xor     rax, rsp
0x180013fb2  mov     [rbp+20h+var_20], rax
0x180013fb6  mov     rsi, r8
0x180013fb9  mov     edi, edx
0x180013fbb  mov     rbx, rcx
0x180013fbe  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180013fc3  lea     r8, [rbx+8]; TokenHandle
0x180013fc7  mov     edx, edi; DesiredAccess
0x180013fc9  mov     rcx, rsi; ProcessHandle
0x180013fcc  call    cs:__imp_OpenProcessToken
0x180013fd2  test    eax, eax
0x180013fd4  jnz     loc_1800140C1
0x180013fda  cmp     qword ptr [rbx+8], 0
0x180013fdf  jz      short loc_18001405F
0x180013fe1  call    cs:__imp_GetLastError
0x180013fe7  mov     [rsp+120h+var_E0], eax
0x180013feb  lea     rcx, [rsp+120h+var_D0]
0x180013ff0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013ff5  nop
0x180013ff6  lea     rdx, [rsp+120h+var_D0]
0x180013ffb  lea     rcx, [rsp+120h+var_B0]
0x180014000  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180014005  nop
0x180014006  mov     dword ptr [rsp+120h+var_DC], 0FAh
0x18001400e  lea     rax, [rsp+120h+var_E0]
0x180014013  mov     [rsp+120h+var_F0], rax; __int64
0x180014018  lea     rax, [rsp+120h+var_DC]
0x18001401d  mov     [rsp+120h+var_100], rax; __int64
0x180014022  lea     rcx, [rsp+120h+var_B0]; struct cxl::TextWriter *
0x180014027  call    ??$WriteLine@D$$BY0L@D$$BY0CM@DH$$BY0BN@DK@TextWriter@cxl@@QEAAXPEBDAEAY0L@$$CBDAEAY0CM@$$CBDAEBHAEAY0BN@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [11],char [44],int,char [29],ulong>(char const *,char const (&)[11],char const (&)[44],int const &,char const (&)[29],ulong const &)
0x18001402c  lea     rcx, [rsp+120h+var_D0]
0x180014031  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180014036  mov     rcx, rax; lpOutputString
0x180014039  call    cs:__imp_OutputDebugStringW
0x18001403f  mov     ecx, [rsp+120h+var_E0]; unsigned int
0x180014043  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x180014048  nop
0x180014049  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x180014050  mov     [rsp+120h+var_B0], rax
0x180014055  lea     rcx, [rsp+120h+var_D0]
0x18001405a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001405f  lea     rcx, [rsp+120h+var_B0]
0x180014064  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014069  nop
0x18001406a  lea     rdx, [rsp+120h+var_B0]
0x18001406f  lea     rcx, [rsp+120h+var_D0]
0x180014074  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180014079  nop
0x18001407a  lea     rdx, aOpenprocesstok; "OpenProcessToken failed"
0x180014081  lea     rcx, [rsp+120h+var_D0]
0x180014086  call    ??$WriteFmt@$0BI@@TextWriter@cxl@@QEAAAEAV01@AEAY0BI@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<24>(char const (&)[24],cxl::Format const &)
0x18001408b  call    cs:__imp_GetLastError
0x180014091  mov     dword ptr [rsp+120h+var_DC], eax
0x180014095  mov     dword ptr [rsp+120h+var_DC+4], 0
0x18001409d  lea     r8, [rsp+120h+var_B0]
0x1800140a2  lea     rdx, [rsp+120h+var_DC]
0x1800140a7  lea     rcx, [rbp+20h+pExceptionObject]
0x1800140ab  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800140b0  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800140b7  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x1800140bb  call    _CxxThrowException_0
0x1800140c1  mov     rcx, [rbp+20h+var_20]
0x1800140c5  xor     rcx, rsp; StackCookie
0x1800140c8  call    __security_check_cookie
0x1800140cd  mov     rbx, [rsp+120h+arg_18]
0x1800140d5  add     rsp, 110h
0x1800140dc  pop     rdi
0x1800140dd  pop     rsi
0x1800140de  pop     rbp
0x1800140df  retn
```
