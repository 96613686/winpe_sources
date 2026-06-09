# cxl::tp2::WorkItem::Join(ulong)

- ea: `0x18001cdc0`
- end: `0x18001ce95`
- name: `?Join@WorkItem@tp2@cxl@@UEAAXK@Z`
- size: `213`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000d298`
- `0x18000dd74`
- `0x180012028`
- `0x180016830`
- `0x180019884`
- `0x18001cc98`
- `0x18001cdc0`
- `0x18001d0d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001ce69`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001ce69`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ce39`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ce39`

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
0x18001cdc0  mov     [rsp-8+arg_8], rbx
0x18001cdc5  push    rbp
0x18001cdc6  lea     rbp, [rsp-57h]
0x18001cdcb  sub     rsp, 90h
0x18001cdd2  mov     rax, cs:__security_cookie
0x18001cdd9  xor     rax, rsp
0x18001cddc  mov     [rbp+57h+var_8], rax
0x18001cde0  mov     rbx, rcx
0x18001cde3  call    ?IsCurrentThreadExecutingCallBack@WorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001cde8  test    al, al
0x18001cdea  jz      short loc_18001CE5B
0x18001cdec  call    cs:__imp_GetLastError
0x18001cdf2  mov     [rbp+57h+var_50], eax
0x18001cdf5  lea     rcx, [rbp+57h+var_28]
0x18001cdf9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001cdfe  lea     rdx, [rbp+57h+var_28]
0x18001ce02  lea     rcx, [rbp+57h+var_4C+4]
0x18001ce06  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001ce0b  mov     dword ptr [rbp+57h+var_4C], 3C4h
0x18001ce12  lea     rax, [rbp+57h+var_50]
0x18001ce16  mov     [rsp+90h+var_60], rax; __int64
0x18001ce1b  lea     rax, [rbp+57h+var_4C]
0x18001ce1f  mov     [rsp+90h+var_70], rax; __int64
0x18001ce24  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001ce28  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0BJ@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0BJ@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [25],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[25],ulong const &)
0x18001ce2d  lea     rcx, [rbp+57h+var_28]
0x18001ce31  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ce36  mov     rcx, rax; lpOutputString
0x18001ce39  call    cs:__imp_OutputDebugStringW
0x18001ce3f  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001ce42  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001ce47  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001ce4e  mov     [rbp+57h+var_4C+4], rax
0x18001ce52  lea     rcx, [rbp+57h+var_28]
0x18001ce56  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ce5b  mov     eax, [rbx+18h]
0x18001ce5e  cmp     eax, 3
0x18001ce61  jz      short loc_18001CE78
0x18001ce63  xor     edx, edx; fCancelPendingCallbacks
0x18001ce65  mov     rcx, [rbx+58h]; pwk
0x18001ce69  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001ce6f  mov     rcx, rbx; this
0x18001ce72  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001ce77  nop
0x18001ce78  mov     rcx, [rbp+57h+var_8]
0x18001ce7c  xor     rcx, rsp; StackCookie
0x18001ce7f  call    __security_check_cookie
0x18001ce84  mov     rbx, [rsp+90h+arg_8]
0x18001ce8c  add     rsp, 90h
0x18001ce93  pop     rbp
0x18001ce94  retn
```
