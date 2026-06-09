# cxl::tp2::WorkItem::Join(ulong)

- ea: `0x180019ce0`
- end: `0x180019db5`
- name: `?Join@WorkItem@tp2@cxl@@UEAAXK@Z`
- size: `213`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002ae0`
- `0x18000ca34`
- `0x18000d618`
- `0x18000d6dc`
- `0x180010ca4`
- `0x180014dc0`
- `0x18001677c`
- `0x180019bb8`
- `0x180019ce0`
- `0x180019ff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d0c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180019d89`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180019d89`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019d59`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019d59`

## pseudocode

```c
void __fastcall cxl::tp2::WorkItem::Join(PTP_WORK *this)
{
  const WCHAR *v2; // rax
  int v3; // [rsp+28h] [rbp-11h]
  unsigned int LastError; // [rsp+40h] [rbp+7h] BYREF
  int v5; // [rsp+44h] [rbp+Bh] BYREF
  _QWORD v6[4]; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v7[32]; // [rsp+68h] [rbp+2Fh] BYREF

  if ( cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack((cxl::tp2::WorkItem *)this) )
  {
    LastError = GetLastError();
    std::wstring::wstring(v7);
    cxl::StringWriter::StringWriter(v6, v7);
    v5 = 964;
    cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [25],unsigned long>(
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
  if ( *((_DWORD *)this + 6) != 3 )
  {
    WaitForThreadpoolWorkCallbacks(this[11], 0);
    cxl::tp2::WorkItemBase::MoveToIdle((cxl::tp2::WorkItemBase *)this);
  }
}

```

## disassembly

```asm
0x180019ce0  mov     [rsp-8+arg_8], rbx
0x180019ce5  push    rbp
0x180019ce6  lea     rbp, [rsp-57h]
0x180019ceb  sub     rsp, 90h
0x180019cf2  mov     rax, cs:__security_cookie
0x180019cf9  xor     rax, rsp
0x180019cfc  mov     [rbp+57h+var_8], rax
0x180019d00  mov     rbx, rcx
0x180019d03  call    ?IsCurrentThreadExecutingCallBack@WorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(void)
0x180019d08  test    al, al
0x180019d0a  jz      short loc_180019D7B
0x180019d0c  call    cs:__imp_GetLastError
0x180019d12  mov     [rbp+57h+var_50], eax
0x180019d15  lea     rcx, [rbp+57h+var_28]
0x180019d19  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019d1e  lea     rdx, [rbp+57h+var_28]
0x180019d22  lea     rcx, [rbp+57h+var_4C+4]
0x180019d26  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180019d2b  mov     dword ptr [rbp+57h+var_4C], 3C4h
0x180019d32  lea     rax, [rbp+57h+var_50]
0x180019d36  mov     [rsp+90h+var_60], rax; __int64
0x180019d3b  lea     rax, [rbp+57h+var_4C]
0x180019d3f  mov     [rsp+90h+var_70], rax; __int64
0x180019d44  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x180019d48  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0BJ@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0BJ@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [25],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[25],ulong const &)
0x180019d4d  lea     rcx, [rbp+57h+var_28]
0x180019d51  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019d56  mov     rcx, rax; lpOutputString
0x180019d59  call    cs:__imp_OutputDebugStringW
0x180019d5f  mov     ecx, [rbp+57h+var_50]; unsigned int
0x180019d62  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x180019d67  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x180019d6e  mov     [rbp+57h+var_4C+4], rax
0x180019d72  lea     rcx, [rbp+57h+var_28]
0x180019d76  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d7b  mov     eax, [rbx+18h]
0x180019d7e  cmp     eax, 3
0x180019d81  jz      short loc_180019D98
0x180019d83  xor     edx, edx; fCancelPendingCallbacks
0x180019d85  mov     rcx, [rbx+58h]; pwk
0x180019d89  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180019d8f  mov     rcx, rbx; this
0x180019d92  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x180019d97  nop
0x180019d98  mov     rcx, [rbp+57h+var_8]
0x180019d9c  xor     rcx, rsp; StackCookie
0x180019d9f  call    __security_check_cookie
0x180019da4  mov     rbx, [rsp+90h+arg_8]
0x180019dac  add     rsp, 90h
0x180019db3  pop     rbp
0x180019db4  retn
```
