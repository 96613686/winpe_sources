# cxl::tp2::TimerWorkItem::TryCancelAndJoin(void)

- ea: `0x18001b7a0`
- end: `0x18001b8a7`
- name: `?TryCancelAndJoin@TimerWorkItem@tp2@cxl@@UEAAXXZ`
- size: `263`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
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
- `0x180017214`
- `0x18001a5a4`
- `0x18001aa40`
- `0x18001b7a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b7d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b85f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b85f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b874`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b874`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b82b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b82b`

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
0x18001b7a0  mov     [rsp-8+arg_8], rbx
0x18001b7a5  push    rbp
0x18001b7a6  lea     rbp, [rsp-57h]
0x18001b7ab  sub     rsp, 90h
0x18001b7b2  mov     rax, cs:__security_cookie
0x18001b7b9  xor     rax, rsp
0x18001b7bc  mov     [rbp+57h+var_8], rax
0x18001b7c0  mov     rbx, rcx
0x18001b7c3  mov     eax, [rcx+18h]
0x18001b7c6  cmp     eax, 3
0x18001b7c9  jz      loc_18001B889
0x18001b7cf  call    ?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001b7d4  test    al, al
0x18001b7d6  jz      short loc_18001B853
0x18001b7d8  call    cs:__imp_GetLastError
0x18001b7df  nop     dword ptr [rax+rax+00h]
0x18001b7e4  mov     [rbp+57h+var_50], eax
0x18001b7e7  lea     rcx, [rbp+57h+var_28]
0x18001b7eb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b7f0  lea     rdx, [rbp+57h+var_28]
0x18001b7f4  lea     rcx, [rbp+57h+var_4C+4]
0x18001b7f8  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001b7fd  mov     dword ptr [rbp+57h+var_4C], 4C0h
0x18001b804  lea     rax, [rbp+57h+var_50]
0x18001b808  mov     [rsp+90h+var_60], rax; __int64
0x18001b80d  lea     rax, [rbp+57h+var_4C]
0x18001b811  mov     [rsp+90h+var_70], rax; __int64
0x18001b816  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001b81a  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0CK@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0CK@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [42],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[42],ulong const &)
0x18001b81f  lea     rcx, [rbp+57h+var_28]
0x18001b823  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b828  mov     rcx, rax; lpOutputString
0x18001b82b  call    cs:__imp_OutputDebugStringW
0x18001b832  nop     dword ptr [rax+rax+00h]
0x18001b837  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001b83a  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001b83f  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001b846  mov     [rbp+57h+var_4C+4], rax
0x18001b84a  lea     rcx, [rbp+57h+var_28]
0x18001b84e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b853  xor     r9d, r9d; msWindowLength
0x18001b856  xor     r8d, r8d; msPeriod
0x18001b859  xor     edx, edx; pftDueTime
0x18001b85b  mov     rcx, [rbx+38h]; pti
0x18001b85f  call    cs:__imp_SetThreadpoolTimer
0x18001b866  nop     dword ptr [rax+rax+00h]
0x18001b86b  mov     edx, 1; fCancelPendingCallbacks
0x18001b870  mov     rcx, [rbx+38h]; pti
0x18001b874  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001b87b  nop     dword ptr [rax+rax+00h]
0x18001b880  mov     rcx, rbx; this
0x18001b883  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001b888  nop
0x18001b889  mov     rcx, [rbp+57h+var_8]
0x18001b88d  xor     rcx, rsp; StackCookie
0x18001b890  call    __security_check_cookie
0x18001b895  mov     rbx, [rsp+90h+arg_8]
0x18001b89d  add     rsp, 90h
0x18001b8a4  pop     rbp
0x18001b8a5  retn
```
