# cxl::tp2::WorkItem::Post(void)

- ea: `0x18001dfb4`
- end: `0x18001e091`
- name: `?Post@WorkItem@tp2@cxl@@QEAAXXZ`
- size: `221`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18001df00`
- `0x180021320`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000d600`
- `0x18000e14c`
- `0x1800124ac`
- `0x180016fb8`
- `0x18001a500`
- `0x18001dc40`
- `0x18001dfb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfdf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e066`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e066`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e032`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e032`

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
0x18001dfb4  mov     [rsp-8+arg_8], rbx
0x18001dfb9  push    rbp
0x18001dfba  lea     rbp, [rsp-57h]
0x18001dfbf  sub     rsp, 90h
0x18001dfc6  mov     rax, cs:__security_cookie
0x18001dfcd  xor     rax, rsp
0x18001dfd0  mov     [rbp+57h+var_8], rax
0x18001dfd4  mov     rbx, rcx
0x18001dfd7  mov     eax, [rcx+18h]
0x18001dfda  cmp     eax, 3
0x18001dfdd  jnz     short loc_18001E05A
0x18001dfdf  call    cs:__imp_GetLastError
0x18001dfe6  nop     dword ptr [rax+rax+00h]
0x18001dfeb  mov     [rbp+57h+var_50], eax
0x18001dfee  lea     rcx, [rbp+57h+var_28]
0x18001dff2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001dff7  lea     rdx, [rbp+57h+var_28]
0x18001dffb  lea     rcx, [rbp+57h+var_4C+4]
0x18001dfff  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001e004  mov     dword ptr [rbp+57h+var_4C], 3B6h
0x18001e00b  lea     rax, [rbp+57h+var_50]
0x18001e00f  mov     [rsp+90h+var_60], rax; __int64
0x18001e014  lea     rax, [rbp+57h+var_4C]
0x18001e018  mov     [rsp+90h+var_70], rax; __int64
0x18001e01d  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001e021  call    ??$WriteLine@D$$BY0M@D$$BY0DM@DH$$BY0BJ@DK@TextWriter@cxl@@QEAAXPEBDAEAY0M@$$CBDAEAY0DM@$$CBDAEBHAEAY0BJ@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [25],ulong>(char const *,char const (&)[12],char const (&)[60],int const &,char const (&)[25],ulong const &)
0x18001e026  lea     rcx, [rbp+57h+var_28]
0x18001e02a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e02f  mov     rcx, rax; lpOutputString
0x18001e032  call    cs:__imp_OutputDebugStringW
0x18001e039  nop     dword ptr [rax+rax+00h]
0x18001e03e  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001e041  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001e046  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001e04d  mov     [rbp+57h+var_4C+4], rax
0x18001e051  lea     rcx, [rbp+57h+var_28]
0x18001e055  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e05a  mov     rcx, rbx; this
0x18001e05d  call    ?MoveToWaiting@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToWaiting(void)
0x18001e062  mov     rcx, [rbx+58h]; pwk
0x18001e066  call    cs:__imp_SubmitThreadpoolWork
0x18001e06d  nop     dword ptr [rax+rax+00h]
0x18001e072  nop
0x18001e073  mov     rcx, [rbp+57h+var_8]
0x18001e077  xor     rcx, rsp; StackCookie
0x18001e07a  call    __security_check_cookie
0x18001e07f  mov     rbx, [rsp+90h+arg_8]
0x18001e087  add     rsp, 90h
0x18001e08e  pop     rbp
0x18001e08f  retn
```
