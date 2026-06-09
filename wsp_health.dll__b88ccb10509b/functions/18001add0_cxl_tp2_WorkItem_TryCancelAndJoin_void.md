# cxl::tp2::WorkItem::TryCancelAndJoin(void)

- ea: `0x18001add0`
- end: `0x18001aea8`
- name: `?TryCancelAndJoin@WorkItem@tp2@cxl@@UEAAXXZ`
- size: `216`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
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
- `0x180016864`
- `0x180019bb8`
- `0x180019ff0`
- `0x18001add0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adfc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001ae7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001ae7c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ae49`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ae49`

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
0x18001add0  mov     [rsp-8+arg_8], rbx
0x18001add5  push    rbp
0x18001add6  lea     rbp, [rsp-57h]
0x18001addb  sub     rsp, 90h
0x18001ade2  mov     rax, cs:__security_cookie
0x18001ade9  xor     rax, rsp
0x18001adec  mov     [rbp+57h+var_8], rax
0x18001adf0  mov     rbx, rcx
0x18001adf3  call    ?IsCurrentThreadExecutingCallBack@WorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001adf8  test    al, al
0x18001adfa  jz      short loc_18001AE6B
0x18001adfc  call    cs:__imp_GetLastError
0x18001ae02  mov     [rbp+57h+var_50], eax
0x18001ae05  lea     rcx, [rbp+57h+var_28]
0x18001ae09  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ae0e  lea     rdx, [rbp+57h+var_28]
0x18001ae12  lea     rcx, [rbp+57h+var_4C+4]
0x18001ae16  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001ae1b  mov     dword ptr [rbp+57h+var_4C], 3D4h
0x18001ae22  lea     rax, [rbp+57h+var_50]
0x18001ae26  mov     [rsp+90h+var_60], rax; __int64
0x18001ae2b  lea     rax, [rbp+57h+var_4C]
0x18001ae2f  mov     [rsp+90h+var_70], rax; __int64
0x18001ae34  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001ae38  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0CF@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0CF@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [37],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[37],ulong const &)
0x18001ae3d  lea     rcx, [rbp+57h+var_28]
0x18001ae41  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ae46  mov     rcx, rax; lpOutputString
0x18001ae49  call    cs:__imp_OutputDebugStringW
0x18001ae4f  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001ae52  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001ae57  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001ae5e  mov     [rbp+57h+var_4C+4], rax
0x18001ae62  lea     rcx, [rbp+57h+var_28]
0x18001ae66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ae6b  mov     eax, [rbx+18h]
0x18001ae6e  cmp     eax, 3
0x18001ae71  jz      short loc_18001AE8B
0x18001ae73  mov     edx, 1; fCancelPendingCallbacks
0x18001ae78  mov     rcx, [rbx+58h]; pwk
0x18001ae7c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001ae82  mov     rcx, rbx; this
0x18001ae85  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001ae8a  nop
0x18001ae8b  mov     rcx, [rbp+57h+var_8]
0x18001ae8f  xor     rcx, rsp; StackCookie
0x18001ae92  call    __security_check_cookie
0x18001ae97  mov     rbx, [rsp+90h+arg_8]
0x18001ae9f  add     rsp, 90h
0x18001aea6  pop     rbp
0x18001aea7  retn
```
