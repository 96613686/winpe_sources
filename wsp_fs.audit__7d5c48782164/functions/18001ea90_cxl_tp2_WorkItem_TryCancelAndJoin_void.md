# cxl::tp2::WorkItem::TryCancelAndJoin(void)

- ea: `0x18001ea90`
- end: `0x18001eb7b`
- name: `?TryCancelAndJoin@WorkItem@tp2@cxl@@UEAAXXZ`
- size: `235`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
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
- `0x18001a398`
- `0x18001d7ac`
- `0x18001dc20`
- `0x18001ea90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eabc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001eb48`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001eb48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001eb0f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001eb0f`

## pseudocode

```c
void __fastcall cxl::tp2::WorkItem::TryCancelAndJoin(PTP_WORK *this)
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
    v5 = 980;
    cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [37],unsigned long>(
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
    WaitForThreadpoolWorkCallbacks(this[11], 1);
    cxl::tp2::WorkItemBase::MoveToIdle((cxl::tp2::WorkItemBase *)this);
  }
}

```

## disassembly

```asm
0x18001ea90  mov     [rsp-8+arg_8], rbx
0x18001ea95  push    rbp
0x18001ea96  lea     rbp, [rsp-57h]
0x18001ea9b  sub     rsp, 90h
0x18001eaa2  mov     rax, cs:__security_cookie
0x18001eaa9  xor     rax, rsp
0x18001eaac  mov     [rbp+57h+var_8], rax
0x18001eab0  mov     rbx, rcx
0x18001eab3  call    ?IsCurrentThreadExecutingCallBack@WorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001eab8  test    al, al
0x18001eaba  jz      short loc_18001EB37
0x18001eabc  call    cs:__imp_GetLastError
0x18001eac3  nop     dword ptr [rax+rax+00h]
0x18001eac8  mov     [rbp+57h+var_50], eax
0x18001eacb  lea     rcx, [rbp+57h+var_28]
0x18001eacf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ead4  lea     rdx, [rbp+57h+var_28]
0x18001ead8  lea     rcx, [rbp+57h+var_4C+4]
0x18001eadc  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001eae1  mov     dword ptr [rbp+57h+var_4C], 3D4h
0x18001eae8  lea     rax, [rbp+57h+var_50]
0x18001eaec  mov     [rsp+90h+var_60], rax; __int64
0x18001eaf1  lea     rax, [rbp+57h+var_4C]
0x18001eaf5  mov     [rsp+90h+var_70], rax; __int64
0x18001eafa  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001eafe  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0CF@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0CF@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [37],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[37],ulong const &)
0x18001eb03  lea     rcx, [rbp+57h+var_28]
0x18001eb07  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001eb0c  mov     rcx, rax; lpOutputString
0x18001eb0f  call    cs:__imp_OutputDebugStringW
0x18001eb16  nop     dword ptr [rax+rax+00h]
0x18001eb1b  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001eb1e  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001eb23  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001eb2a  mov     [rbp+57h+var_4C+4], rax
0x18001eb2e  lea     rcx, [rbp+57h+var_28]
0x18001eb32  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eb37  mov     eax, [rbx+18h]
0x18001eb3a  cmp     eax, 3
0x18001eb3d  jz      short loc_18001EB5D
0x18001eb3f  mov     edx, 1; fCancelPendingCallbacks
0x18001eb44  mov     rcx, [rbx+58h]; pwk
0x18001eb48  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001eb4f  nop     dword ptr [rax+rax+00h]
0x18001eb54  mov     rcx, rbx; this
0x18001eb57  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001eb5c  nop
0x18001eb5d  mov     rcx, [rbp+57h+var_8]
0x18001eb61  xor     rcx, rsp; StackCookie
0x18001eb64  call    __security_check_cookie
0x18001eb69  mov     rbx, [rsp+90h+arg_8]
0x18001eb71  add     rsp, 90h
0x18001eb78  pop     rbp
0x18001eb79  retn
```
