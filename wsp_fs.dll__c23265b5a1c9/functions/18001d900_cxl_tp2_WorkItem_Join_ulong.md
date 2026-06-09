# cxl::tp2::WorkItem::Join(ulong)

- ea: `0x18001d900`
- end: `0x18001d9e8`
- name: `?Join@WorkItem@tp2@cxl@@UEAAXK@Z`
- size: `232`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000d600`
- `0x18000e14c`
- `0x1800124ac`
- `0x180016fb8`
- `0x18001a2a8`
- `0x18001d7ac`
- `0x18001d900`
- `0x18001dc20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d92c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d92c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001d9b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001d9b5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d97f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d97f`

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
0x18001d900  mov     [rsp-8+arg_8], rbx
0x18001d905  push    rbp
0x18001d906  lea     rbp, [rsp-57h]
0x18001d90b  sub     rsp, 90h
0x18001d912  mov     rax, cs:__security_cookie
0x18001d919  xor     rax, rsp
0x18001d91c  mov     [rbp+57h+var_8], rax
0x18001d920  mov     rbx, rcx
0x18001d923  call    ?IsCurrentThreadExecutingCallBack@WorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001d928  test    al, al
0x18001d92a  jz      short loc_18001D9A7
0x18001d92c  call    cs:__imp_GetLastError
0x18001d933  nop     dword ptr [rax+rax+00h]
0x18001d938  mov     [rbp+57h+var_50], eax
0x18001d93b  lea     rcx, [rbp+57h+var_28]
0x18001d93f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d944  lea     rdx, [rbp+57h+var_28]
0x18001d948  lea     rcx, [rbp+57h+var_4C+4]
0x18001d94c  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001d951  mov     dword ptr [rbp+57h+var_4C], 3C4h
0x18001d958  lea     rax, [rbp+57h+var_50]
0x18001d95c  mov     [rsp+90h+var_60], rax; __int64
0x18001d961  lea     rax, [rbp+57h+var_4C]
0x18001d965  mov     [rsp+90h+var_70], rax; __int64
0x18001d96a  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001d96e  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0BJ@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0BJ@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [25],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[25],ulong const &)
0x18001d973  lea     rcx, [rbp+57h+var_28]
0x18001d977  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d97c  mov     rcx, rax; lpOutputString
0x18001d97f  call    cs:__imp_OutputDebugStringW
0x18001d986  nop     dword ptr [rax+rax+00h]
0x18001d98b  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001d98e  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001d993  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001d99a  mov     [rbp+57h+var_4C+4], rax
0x18001d99e  lea     rcx, [rbp+57h+var_28]
0x18001d9a2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d9a7  mov     eax, [rbx+18h]
0x18001d9aa  cmp     eax, 3
0x18001d9ad  jz      short loc_18001D9CA
0x18001d9af  xor     edx, edx; fCancelPendingCallbacks
0x18001d9b1  mov     rcx, [rbx+58h]; pwk
0x18001d9b5  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001d9bc  nop     dword ptr [rax+rax+00h]
0x18001d9c1  mov     rcx, rbx; this
0x18001d9c4  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001d9c9  nop
0x18001d9ca  mov     rcx, [rbp+57h+var_8]
0x18001d9ce  xor     rcx, rsp; StackCookie
0x18001d9d1  call    __security_check_cookie
0x18001d9d6  mov     rbx, [rsp+90h+arg_8]
0x18001d9de  add     rsp, 90h
0x18001d9e5  pop     rbp
0x18001d9e6  retn
```
