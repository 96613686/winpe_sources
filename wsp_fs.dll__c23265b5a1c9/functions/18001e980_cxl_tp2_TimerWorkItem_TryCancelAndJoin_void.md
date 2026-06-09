# cxl::tp2::TimerWorkItem::TryCancelAndJoin(void)

- ea: `0x18001e980`
- end: `0x18001ea87`
- name: `?TryCancelAndJoin@TimerWorkItem@tp2@cxl@@UEAAXXZ`
- size: `263`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
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
- `0x18001a410`
- `0x18001d784`
- `0x18001dc20`
- `0x18001e980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ea3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ea3f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ea54`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ea54`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ea0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ea0b`

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
0x18001e980  mov     [rsp-8+arg_8], rbx
0x18001e985  push    rbp
0x18001e986  lea     rbp, [rsp-57h]
0x18001e98b  sub     rsp, 90h
0x18001e992  mov     rax, cs:__security_cookie
0x18001e999  xor     rax, rsp
0x18001e99c  mov     [rbp+57h+var_8], rax
0x18001e9a0  mov     rbx, rcx
0x18001e9a3  mov     eax, [rcx+18h]
0x18001e9a6  cmp     eax, 3
0x18001e9a9  jz      loc_18001EA69
0x18001e9af  call    ?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001e9b4  test    al, al
0x18001e9b6  jz      short loc_18001EA33
0x18001e9b8  call    cs:__imp_GetLastError
0x18001e9bf  nop     dword ptr [rax+rax+00h]
0x18001e9c4  mov     [rbp+57h+var_50], eax
0x18001e9c7  lea     rcx, [rbp+57h+var_28]
0x18001e9cb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e9d0  lea     rdx, [rbp+57h+var_28]
0x18001e9d4  lea     rcx, [rbp+57h+var_4C+4]
0x18001e9d8  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001e9dd  mov     dword ptr [rbp+57h+var_4C], 4C0h
0x18001e9e4  lea     rax, [rbp+57h+var_50]
0x18001e9e8  mov     [rsp+90h+var_60], rax; __int64
0x18001e9ed  lea     rax, [rbp+57h+var_4C]
0x18001e9f1  mov     [rsp+90h+var_70], rax; __int64
0x18001e9f6  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001e9fa  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0CK@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0CK@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [42],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[42],ulong const &)
0x18001e9ff  lea     rcx, [rbp+57h+var_28]
0x18001ea03  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ea08  mov     rcx, rax; lpOutputString
0x18001ea0b  call    cs:__imp_OutputDebugStringW
0x18001ea12  nop     dword ptr [rax+rax+00h]
0x18001ea17  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001ea1a  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001ea1f  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001ea26  mov     [rbp+57h+var_4C+4], rax
0x18001ea2a  lea     rcx, [rbp+57h+var_28]
0x18001ea2e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ea33  xor     r9d, r9d; msWindowLength
0x18001ea36  xor     r8d, r8d; msPeriod
0x18001ea39  xor     edx, edx; pftDueTime
0x18001ea3b  mov     rcx, [rbx+38h]; pti
0x18001ea3f  call    cs:__imp_SetThreadpoolTimer
0x18001ea46  nop     dword ptr [rax+rax+00h]
0x18001ea4b  mov     edx, 1; fCancelPendingCallbacks
0x18001ea50  mov     rcx, [rbx+38h]; pti
0x18001ea54  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ea5b  nop     dword ptr [rax+rax+00h]
0x18001ea60  mov     rcx, rbx; this
0x18001ea63  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001ea68  nop
0x18001ea69  mov     rcx, [rbp+57h+var_8]
0x18001ea6d  xor     rcx, rsp; StackCookie
0x18001ea70  call    __security_check_cookie
0x18001ea75  mov     rbx, [rsp+90h+arg_8]
0x18001ea7d  add     rsp, 90h
0x18001ea84  pop     rbp
0x18001ea85  retn
```
