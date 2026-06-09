# cxl::tp2::WorkItem::TryCancelAndJoin(void)

- ea: `0x18001deb0`
- end: `0x18001df88`
- name: `?TryCancelAndJoin@WorkItem@tp2@cxl@@UEAAXXZ`
- size: `216`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
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
- `0x18001996c`
- `0x18001cc98`
- `0x18001d0d0`
- `0x18001deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dedc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dedc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001df5c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001df5c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001df29`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001df29`

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
0x18001deb0  mov     [rsp-8+arg_8], rbx
0x18001deb5  push    rbp
0x18001deb6  lea     rbp, [rsp-57h]
0x18001debb  sub     rsp, 90h
0x18001dec2  mov     rax, cs:__security_cookie
0x18001dec9  xor     rax, rsp
0x18001decc  mov     [rbp+57h+var_8], rax
0x18001ded0  mov     rbx, rcx
0x18001ded3  call    ?IsCurrentThreadExecutingCallBack@WorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::WorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001ded8  test    al, al
0x18001deda  jz      short loc_18001DF4B
0x18001dedc  call    cs:__imp_GetLastError
0x18001dee2  mov     [rbp+57h+var_50], eax
0x18001dee5  lea     rcx, [rbp+57h+var_28]
0x18001dee9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001deee  lea     rdx, [rbp+57h+var_28]
0x18001def2  lea     rcx, [rbp+57h+var_4C+4]
0x18001def6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001defb  mov     dword ptr [rbp+57h+var_4C], 3D4h
0x18001df02  lea     rax, [rbp+57h+var_50]
0x18001df06  mov     [rsp+90h+var_60], rax; __int64
0x18001df0b  lea     rax, [rbp+57h+var_4C]
0x18001df0f  mov     [rsp+90h+var_70], rax; __int64
0x18001df14  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001df18  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0CF@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0CF@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [37],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[37],ulong const &)
0x18001df1d  lea     rcx, [rbp+57h+var_28]
0x18001df21  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001df26  mov     rcx, rax; lpOutputString
0x18001df29  call    cs:__imp_OutputDebugStringW
0x18001df2f  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001df32  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001df37  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001df3e  mov     [rbp+57h+var_4C+4], rax
0x18001df42  lea     rcx, [rbp+57h+var_28]
0x18001df46  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001df4b  mov     eax, [rbx+18h]
0x18001df4e  cmp     eax, 3
0x18001df51  jz      short loc_18001DF6B
0x18001df53  mov     edx, 1; fCancelPendingCallbacks
0x18001df58  mov     rcx, [rbx+58h]; pwk
0x18001df5c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001df62  mov     rcx, rbx; this
0x18001df65  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001df6a  nop
0x18001df6b  mov     rcx, [rbp+57h+var_8]
0x18001df6f  xor     rcx, rsp; StackCookie
0x18001df72  call    __security_check_cookie
0x18001df77  mov     rbx, [rsp+90h+arg_8]
0x18001df7f  add     rsp, 90h
0x18001df86  pop     rbp
0x18001df87  retn
```
