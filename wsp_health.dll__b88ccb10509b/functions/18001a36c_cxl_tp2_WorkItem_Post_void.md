# cxl::tp2::WorkItem::Post(void)

- ea: `0x18001a36c`
- end: `0x18001a436`
- name: `?Post@WorkItem@tp2@cxl@@QEAAXXZ`
- size: `202`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18001a2b8`
- `0x18001d43c`

## callees

- `0x180002ae0`
- `0x18000ca34`
- `0x18000d618`
- `0x18000d6dc`
- `0x180010ca4`
- `0x180014dc0`
- `0x1800169c0`
- `0x18001a010`
- `0x18001a36c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a397`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001a412`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001a412`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a3e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a3e4`

## pseudocode

```c
void __fastcall cxl::tp2::WorkItem::Post(cxl::tp2::WorkItem *this)
{
  const WCHAR *v2; // rax
  int v3; // [rsp+28h] [rbp-11h]
  unsigned int LastError; // [rsp+40h] [rbp+7h] BYREF
  int v5; // [rsp+44h] [rbp+Bh] BYREF
  _QWORD v6[4]; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v7[32]; // [rsp+68h] [rbp+2Fh] BYREF

  if ( *((_DWORD *)this + 6) == 3 )
  {
    LastError = GetLastError();
    std::wstring::wstring(v7);
    cxl::StringWriter::StringWriter(v6, v7);
    v5 = 950;
    cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [25],unsigned long>(
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
  cxl::tp2::WorkItemBase::MoveToWaiting(this);
  SubmitThreadpoolWork(*((PTP_WORK *)this + 11));
}

```

## disassembly

```asm
0x18001a36c  mov     [rsp-8+arg_8], rbx
0x18001a371  push    rbp
0x18001a372  lea     rbp, [rsp-57h]
0x18001a377  sub     rsp, 90h
0x18001a37e  mov     rax, cs:__security_cookie
0x18001a385  xor     rax, rsp
0x18001a388  mov     [rbp+57h+var_8], rax
0x18001a38c  mov     rbx, rcx
0x18001a38f  mov     eax, [rcx+18h]
0x18001a392  cmp     eax, 3
0x18001a395  jnz     short loc_18001A406
0x18001a397  call    cs:__imp_GetLastError
0x18001a39d  mov     [rbp+57h+var_50], eax
0x18001a3a0  lea     rcx, [rbp+57h+var_28]
0x18001a3a4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a3a9  lea     rdx, [rbp+57h+var_28]
0x18001a3ad  lea     rcx, [rbp+57h+var_4C+4]
0x18001a3b1  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001a3b6  mov     dword ptr [rbp+57h+var_4C], 3B6h
0x18001a3bd  lea     rax, [rbp+57h+var_50]
0x18001a3c1  mov     [rsp+90h+var_60], rax; __int64
0x18001a3c6  lea     rax, [rbp+57h+var_4C]
0x18001a3ca  mov     [rsp+90h+var_70], rax; __int64
0x18001a3cf  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001a3d3  call    ??$WriteLine@D$$BY0M@D$$BY0DM@DH$$BY0BJ@DK@TextWriter@cxl@@QEAAXPEBDAEAY0M@$$CBDAEAY0DM@$$CBDAEBHAEAY0BJ@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [25],ulong>(char const *,char const (&)[12],char const (&)[60],int const &,char const (&)[25],ulong const &)
0x18001a3d8  lea     rcx, [rbp+57h+var_28]
0x18001a3dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a3e1  mov     rcx, rax; lpOutputString
0x18001a3e4  call    cs:__imp_OutputDebugStringW
0x18001a3ea  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001a3ed  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001a3f2  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001a3f9  mov     [rbp+57h+var_4C+4], rax
0x18001a3fd  lea     rcx, [rbp+57h+var_28]
0x18001a401  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a406  mov     rcx, rbx; this
0x18001a409  call    ?MoveToWaiting@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToWaiting(void)
0x18001a40e  mov     rcx, [rbx+58h]; pwk
0x18001a412  call    cs:__imp_SubmitThreadpoolWork
0x18001a418  nop
0x18001a419  mov     rcx, [rbp+57h+var_8]
0x18001a41d  xor     rcx, rsp; StackCookie
0x18001a420  call    __security_check_cookie
0x18001a425  mov     rbx, [rsp+90h+arg_8]
0x18001a42d  add     rsp, 90h
0x18001a434  pop     rbp
0x18001a435  retn
```
