# cxl::tp2::TimerWorkItem::TryCancelAndJoin(void)

- ea: `0x18001ddb0`
- end: `0x18001de9e`
- name: `?TryCancelAndJoin@TimerWorkItem@tp2@cxl@@UEAAXXZ`
- size: `238`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
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
- `0x1800199e0`
- `0x18001cc74`
- `0x18001d0d0`
- `0x18001ddb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dde8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dde8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001de63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001de63`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001de72`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001de72`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001de35`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001de35`

## pseudocode

```c
void __fastcall cxl::tp2::TimerWorkItem::TryCancelAndJoin(PTP_TIMER *this)
{
  const WCHAR *v2; // rax
  int v3; // [rsp+28h] [rbp-11h]
  unsigned int LastError; // [rsp+40h] [rbp+7h] BYREF
  int v5; // [rsp+44h] [rbp+Bh] BYREF
  _QWORD v6[4]; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v7[32]; // [rsp+68h] [rbp+2Fh] BYREF

  if ( *((_DWORD *)this + 6) != 3 )
  {
    if ( cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack((cxl::tp2::TimerWorkItem *)this) )
    {
      LastError = GetLastError();
      std::wstring::wstring(v7);
      cxl::StringWriter::StringWriter(v6, v7);
      v5 = 1216;
      cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [42],unsigned long>(
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
    SetThreadpoolTimer(this[7], 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(this[7], 1);
    cxl::tp2::WorkItemBase::MoveToIdle((cxl::tp2::WorkItemBase *)this);
  }
}

```

## disassembly

```asm
0x18001ddb0  mov     [rsp-8+arg_8], rbx
0x18001ddb5  push    rbp
0x18001ddb6  lea     rbp, [rsp-57h]
0x18001ddbb  sub     rsp, 90h
0x18001ddc2  mov     rax, cs:__security_cookie
0x18001ddc9  xor     rax, rsp
0x18001ddcc  mov     [rbp+57h+var_8], rax
0x18001ddd0  mov     rbx, rcx
0x18001ddd3  mov     eax, [rcx+18h]
0x18001ddd6  cmp     eax, 3
0x18001ddd9  jz      loc_18001DE81
0x18001dddf  call    ?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001dde4  test    al, al
0x18001dde6  jz      short loc_18001DE57
0x18001dde8  call    cs:__imp_GetLastError
0x18001ddee  mov     [rbp+57h+var_50], eax
0x18001ddf1  lea     rcx, [rbp+57h+var_28]
0x18001ddf5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ddfa  lea     rdx, [rbp+57h+var_28]
0x18001ddfe  lea     rcx, [rbp+57h+var_4C+4]
0x18001de02  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001de07  mov     dword ptr [rbp+57h+var_4C], 4C0h
0x18001de0e  lea     rax, [rbp+57h+var_50]
0x18001de12  mov     [rsp+90h+var_60], rax; __int64
0x18001de17  lea     rax, [rbp+57h+var_4C]
0x18001de1b  mov     [rsp+90h+var_70], rax; __int64
0x18001de20  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001de24  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0CK@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0CK@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [42],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[42],ulong const &)
0x18001de29  lea     rcx, [rbp+57h+var_28]
0x18001de2d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001de32  mov     rcx, rax; lpOutputString
0x18001de35  call    cs:__imp_OutputDebugStringW
0x18001de3b  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001de3e  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001de43  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001de4a  mov     [rbp+57h+var_4C+4], rax
0x18001de4e  lea     rcx, [rbp+57h+var_28]
0x18001de52  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001de57  xor     r9d, r9d; msWindowLength
0x18001de5a  xor     r8d, r8d; msPeriod
0x18001de5d  xor     edx, edx; pftDueTime
0x18001de5f  mov     rcx, [rbx+38h]; pti
0x18001de63  call    cs:__imp_SetThreadpoolTimer
0x18001de69  mov     edx, 1; fCancelPendingCallbacks
0x18001de6e  mov     rcx, [rbx+38h]; pti
0x18001de72  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001de78  mov     rcx, rbx; this
0x18001de7b  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001de80  nop
0x18001de81  mov     rcx, [rbp+57h+var_8]
0x18001de85  xor     rcx, rsp; StackCookie
0x18001de88  call    __security_check_cookie
0x18001de8d  mov     rbx, [rsp+90h+arg_8]
0x18001de95  add     rsp, 90h
0x18001de9c  pop     rbp
0x18001de9d  retn
```
