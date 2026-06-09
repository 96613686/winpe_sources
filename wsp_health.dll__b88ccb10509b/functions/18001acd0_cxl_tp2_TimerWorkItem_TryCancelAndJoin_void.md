# cxl::tp2::TimerWorkItem::TryCancelAndJoin(void)

- ea: `0x18001acd0`
- end: `0x18001adbe`
- name: `?TryCancelAndJoin@TimerWorkItem@tp2@cxl@@UEAAXXZ`
- size: `238`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
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
- `0x1800168d8`
- `0x180019b94`
- `0x180019ff0`
- `0x18001acd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ad83`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ad83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ad92`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ad92`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ad55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ad55`

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
0x18001acd0  mov     [rsp-8+arg_8], rbx
0x18001acd5  push    rbp
0x18001acd6  lea     rbp, [rsp-57h]
0x18001acdb  sub     rsp, 90h
0x18001ace2  mov     rax, cs:__security_cookie
0x18001ace9  xor     rax, rsp
0x18001acec  mov     [rbp+57h+var_8], rax
0x18001acf0  mov     rbx, rcx
0x18001acf3  mov     eax, [rcx+18h]
0x18001acf6  cmp     eax, 3
0x18001acf9  jz      loc_18001ADA1
0x18001acff  call    ?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001ad04  test    al, al
0x18001ad06  jz      short loc_18001AD77
0x18001ad08  call    cs:__imp_GetLastError
0x18001ad0e  mov     [rbp+57h+var_50], eax
0x18001ad11  lea     rcx, [rbp+57h+var_28]
0x18001ad15  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ad1a  lea     rdx, [rbp+57h+var_28]
0x18001ad1e  lea     rcx, [rbp+57h+var_4C+4]
0x18001ad22  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001ad27  mov     dword ptr [rbp+57h+var_4C], 4C0h
0x18001ad2e  lea     rax, [rbp+57h+var_50]
0x18001ad32  mov     [rsp+90h+var_60], rax; __int64
0x18001ad37  lea     rax, [rbp+57h+var_4C]
0x18001ad3b  mov     [rsp+90h+var_70], rax; __int64
0x18001ad40  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001ad44  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0CK@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0CK@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [42],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[42],ulong const &)
0x18001ad49  lea     rcx, [rbp+57h+var_28]
0x18001ad4d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ad52  mov     rcx, rax; lpOutputString
0x18001ad55  call    cs:__imp_OutputDebugStringW
0x18001ad5b  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001ad5e  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001ad63  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001ad6a  mov     [rbp+57h+var_4C+4], rax
0x18001ad6e  lea     rcx, [rbp+57h+var_28]
0x18001ad72  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ad77  xor     r9d, r9d; msWindowLength
0x18001ad7a  xor     r8d, r8d; msPeriod
0x18001ad7d  xor     edx, edx; pftDueTime
0x18001ad7f  mov     rcx, [rbx+38h]; pti
0x18001ad83  call    cs:__imp_SetThreadpoolTimer
0x18001ad89  mov     edx, 1; fCancelPendingCallbacks
0x18001ad8e  mov     rcx, [rbx+38h]; pti
0x18001ad92  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ad98  mov     rcx, rbx; this
0x18001ad9b  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001ada0  nop
0x18001ada1  mov     rcx, [rbp+57h+var_8]
0x18001ada5  xor     rcx, rsp; StackCookie
0x18001ada8  call    __security_check_cookie
0x18001adad  mov     rbx, [rsp+90h+arg_8]
0x18001adb5  add     rsp, 90h
0x18001adbc  pop     rbp
0x18001adbd  retn
```
