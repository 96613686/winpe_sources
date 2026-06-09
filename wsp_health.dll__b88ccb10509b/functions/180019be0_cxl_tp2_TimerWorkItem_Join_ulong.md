# cxl::tp2::TimerWorkItem::Join(ulong)

- ea: `0x180019be0`
- end: `0x180019cd6`
- name: `?Join@TimerWorkItem@tp2@cxl@@UEAAXK@Z`
- size: `246`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this, DWORD dwMilliseconds)`
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
- `0x1800167f0`
- `0x180019b94`
- `0x180019be0`
- `0x180019ff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019ca6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019ca6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019c6c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019c6c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019c98`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019c98`

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
0x180019be0  mov     [rsp-8+arg_10], rbx
0x180019be5  mov     [rsp-8+arg_18], rdi
0x180019bea  push    rbp
0x180019beb  lea     rbp, [rsp-57h]
0x180019bf0  sub     rsp, 90h
0x180019bf7  mov     rax, cs:__security_cookie
0x180019bfe  xor     rax, rsp
0x180019c01  mov     [rbp+57h+var_8], rax
0x180019c05  mov     edi, edx
0x180019c07  mov     rbx, rcx
0x180019c0a  mov     eax, [rcx+18h]
0x180019c0d  cmp     eax, 3
0x180019c10  jz      loc_180019CB5
0x180019c16  call    ?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)
0x180019c1b  test    al, al
0x180019c1d  jz      short loc_180019C8E
0x180019c1f  call    cs:__imp_GetLastError
0x180019c25  mov     [rbp+57h+var_50], eax
0x180019c28  lea     rcx, [rbp+57h+var_28]
0x180019c2c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019c31  lea     rdx, [rbp+57h+var_28]
0x180019c35  lea     rcx, [rbp+57h+var_4C+4]
0x180019c39  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180019c3e  mov     dword ptr [rbp+57h+var_4C], 4ABh
0x180019c45  lea     rax, [rbp+57h+var_50]
0x180019c49  mov     [rsp+90h+var_60], rax; __int64
0x180019c4e  lea     rax, [rbp+57h+var_4C]
0x180019c52  mov     [rsp+90h+var_70], rax; __int64
0x180019c57  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x180019c5b  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0BO@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0BO@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [30],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[30],ulong const &)
0x180019c60  lea     rcx, [rbp+57h+var_28]
0x180019c64  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019c69  mov     rcx, rax; lpOutputString
0x180019c6c  call    cs:__imp_OutputDebugStringW
0x180019c72  mov     ecx, [rbp+57h+var_50]; unsigned int
0x180019c75  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x180019c7a  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x180019c81  mov     [rbp+57h+var_4C+4], rax
0x180019c85  lea     rcx, [rbp+57h+var_28]
0x180019c89  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019c8e  mov     eax, [rbx+18h]
0x180019c91  cmp     eax, 1
0x180019c94  jnz     short loc_180019CA0
0x180019c96  mov     ecx, edi; dwMilliseconds
0x180019c98  call    cs:__imp_Sleep
0x180019c9e  jmp     short loc_180019C8E
0x180019ca0  xor     edx, edx; fCancelPendingCallbacks
0x180019ca2  mov     rcx, [rbx+38h]; pti
0x180019ca6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019cac  mov     rcx, rbx; this
0x180019caf  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x180019cb4  nop
0x180019cb5  mov     rcx, [rbp+57h+var_8]
0x180019cb9  xor     rcx, rsp; StackCookie
0x180019cbc  call    __security_check_cookie
0x180019cc1  lea     r11, [rsp+90h+var_s0]
0x180019cc9  mov     rbx, [r11+20h]
0x180019ccd  mov     rdi, [r11+28h]
0x180019cd1  mov     rsp, r11
0x180019cd4  pop     rbp
0x180019cd5  retn
```
