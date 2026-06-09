# cxl::tp2::TimerWorkItem::Join(ulong)

- ea: `0x18001a600`
- end: `0x18001a70f`
- name: `?Join@TimerWorkItem@tp2@cxl@@UEAAXK@Z`
- size: `271`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this, DWORD dwMilliseconds)`
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
- `0x180017124`
- `0x18001a5a4`
- `0x18001a600`
- `0x18001aa40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a63f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a6d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a6d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a692`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a692`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a6c4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a6c4`

## pseudocode

```c
void __fastcall cxl::tp2::TimerWorkItem::Join(PTP_TIMER *this, DWORD dwMilliseconds)
{
  const WCHAR *v4; // rax
  int v5; // [rsp+28h] [rbp-11h]
  unsigned int LastError; // [rsp+40h] [rbp+7h] BYREF
  int v7; // [rsp+44h] [rbp+Bh] BYREF
  _QWORD v8[4]; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v9[32]; // [rsp+68h] [rbp+2Fh] BYREF

  if ( *((_DWORD *)this + 6) != 3 )
  {
    if ( cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack((cxl::tp2::TimerWorkItem *)this) )
    {
      LastError = GetLastError();
      std::wstring::wstring(v9);
      cxl::StringWriter::StringWriter(v8, v9);
      v7 = 1195;
      cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [30],unsigned long>(
        (struct cxl::TextWriter *)v8,
        (__int64)&v7,
        v5,
        (__int64)&LastError);
      v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
      OutputDebugStringW(v4);
      cxl::Debug::StopIfIsDebuggedOrCrash(LastError);
      v8[0] = &cxl::RefCounted::`vftable';
      std::wstring::_Tidy_deallocate(v9);
    }
    while ( *((_DWORD *)this + 6) == 1 )
      Sleep(dwMilliseconds);
    WaitForThreadpoolTimerCallbacks(this[7], 0);
    cxl::tp2::WorkItemBase::MoveToIdle((cxl::tp2::WorkItemBase *)this);
  }
}

```

## disassembly

```asm
0x18001a600  mov     [rsp-8+arg_10], rbx
0x18001a605  mov     [rsp-8+arg_18], rdi
0x18001a60a  push    rbp
0x18001a60b  lea     rbp, [rsp-57h]
0x18001a610  sub     rsp, 90h
0x18001a617  mov     rax, cs:__security_cookie
0x18001a61e  xor     rax, rsp
0x18001a621  mov     [rbp+57h+var_8], rax
0x18001a625  mov     edi, edx
0x18001a627  mov     rbx, rcx
0x18001a62a  mov     eax, [rcx+18h]
0x18001a62d  cmp     eax, 3
0x18001a630  jz      loc_18001A6ED
0x18001a636  call    ?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001a63b  test    al, al
0x18001a63d  jz      short loc_18001A6BA
0x18001a63f  call    cs:__imp_GetLastError
0x18001a646  nop     dword ptr [rax+rax+00h]
0x18001a64b  mov     [rbp+57h+var_50], eax
0x18001a64e  lea     rcx, [rbp+57h+var_28]
0x18001a652  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a657  lea     rdx, [rbp+57h+var_28]
0x18001a65b  lea     rcx, [rbp+57h+var_4C+4]
0x18001a65f  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001a664  mov     dword ptr [rbp+57h+var_4C], 4ABh
0x18001a66b  lea     rax, [rbp+57h+var_50]
0x18001a66f  mov     [rsp+90h+var_60], rax; __int64
0x18001a674  lea     rax, [rbp+57h+var_4C]
0x18001a678  mov     [rsp+90h+var_70], rax; __int64
0x18001a67d  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001a681  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0BO@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0BO@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [30],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[30],ulong const &)
0x18001a686  lea     rcx, [rbp+57h+var_28]
0x18001a68a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a68f  mov     rcx, rax; lpOutputString
0x18001a692  call    cs:__imp_OutputDebugStringW
0x18001a699  nop     dword ptr [rax+rax+00h]
0x18001a69e  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001a6a1  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001a6a6  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001a6ad  mov     [rbp+57h+var_4C+4], rax
0x18001a6b1  lea     rcx, [rbp+57h+var_28]
0x18001a6b5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a6ba  mov     eax, [rbx+18h]
0x18001a6bd  cmp     eax, 1
0x18001a6c0  jnz     short loc_18001A6D2
0x18001a6c2  mov     ecx, edi; dwMilliseconds
0x18001a6c4  call    cs:__imp_Sleep
0x18001a6cb  nop     dword ptr [rax+rax+00h]
0x18001a6d0  jmp     short loc_18001A6BA
0x18001a6d2  xor     edx, edx; fCancelPendingCallbacks
0x18001a6d4  mov     rcx, [rbx+38h]; pti
0x18001a6d8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001a6df  nop     dword ptr [rax+rax+00h]
0x18001a6e4  mov     rcx, rbx; this
0x18001a6e7  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001a6ec  nop
0x18001a6ed  mov     rcx, [rbp+57h+var_8]
0x18001a6f1  xor     rcx, rsp; StackCookie
0x18001a6f4  call    __security_check_cookie
0x18001a6f9  lea     r11, [rsp+90h+var_s0]
0x18001a701  mov     rbx, [r11+20h]
0x18001a705  mov     rdi, [r11+28h]
0x18001a709  mov     rsp, r11
0x18001a70c  pop     rbp
0x18001a70d  retn
```
