# cxl::tp2::WorkItem::Join(ulong)

- ea: `0x18001a720`
- end: `0x18001a808`
- name: `?Join@WorkItem@tp2@cxl@@UEAAXK@Z`
- size: `232`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002b50`
- `0x18000cde0`
- `0x18000da34`
- `0x18000daf8`
- `0x180011184`
- `0x180015578`
- `0x1800170ac`
- `0x18001a5cc`
- `0x18001a720`
- `0x18001aa40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a74c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a74c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001a7d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001a7d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a79f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a79f`

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
0x18001a720  mov     [rsp-8+arg_8], rbx
0x18001a725  push    rbp
0x18001a726  lea     rbp, [rsp-57h]
0x18001a72b  sub     rsp, 90h
0x18001a732  mov     rax, cs:__security_cookie
0x18001a739  xor     rax, rsp
0x18001a73c  mov     [rbp+57h+var_8], rax
0x18001a740  mov     rbx, rcx
0x18001a743  call    ?IsCurrentThreadExecutingCallBack@WorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001a748  test    al, al
0x18001a74a  jz      short loc_18001A7C7
0x18001a74c  call    cs:__imp_GetLastError
0x18001a753  nop     dword ptr [rax+rax+00h]
0x18001a758  mov     [rbp+57h+var_50], eax
0x18001a75b  lea     rcx, [rbp+57h+var_28]
0x18001a75f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a764  lea     rdx, [rbp+57h+var_28]
0x18001a768  lea     rcx, [rbp+57h+var_4C+4]
0x18001a76c  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001a771  mov     dword ptr [rbp+57h+var_4C], 3C4h
0x18001a778  lea     rax, [rbp+57h+var_50]
0x18001a77c  mov     [rsp+90h+var_60], rax; __int64
0x18001a781  lea     rax, [rbp+57h+var_4C]
0x18001a785  mov     [rsp+90h+var_70], rax; __int64
0x18001a78a  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001a78e  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0BJ@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0BJ@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [25],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[25],ulong const &)
0x18001a793  lea     rcx, [rbp+57h+var_28]
0x18001a797  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a79c  mov     rcx, rax; lpOutputString
0x18001a79f  call    cs:__imp_OutputDebugStringW
0x18001a7a6  nop     dword ptr [rax+rax+00h]
0x18001a7ab  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001a7ae  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001a7b3  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001a7ba  mov     [rbp+57h+var_4C+4], rax
0x18001a7be  lea     rcx, [rbp+57h+var_28]
0x18001a7c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a7c7  mov     eax, [rbx+18h]
0x18001a7ca  cmp     eax, 3
0x18001a7cd  jz      short loc_18001A7EA
0x18001a7cf  xor     edx, edx; fCancelPendingCallbacks
0x18001a7d1  mov     rcx, [rbx+58h]; pwk
0x18001a7d5  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001a7dc  nop     dword ptr [rax+rax+00h]
0x18001a7e1  mov     rcx, rbx; this
0x18001a7e4  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001a7e9  nop
0x18001a7ea  mov     rcx, [rbp+57h+var_8]
0x18001a7ee  xor     rcx, rsp; StackCookie
0x18001a7f1  call    __security_check_cookie
0x18001a7f6  mov     rbx, [rsp+90h+arg_8]
0x18001a7fe  add     rsp, 90h
0x18001a805  pop     rbp
0x18001a806  retn
```
