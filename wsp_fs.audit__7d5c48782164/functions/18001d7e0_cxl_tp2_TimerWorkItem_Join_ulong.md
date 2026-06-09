# cxl::tp2::TimerWorkItem::Join(ulong)

- ea: `0x18001d7e0`
- end: `0x18001d8ef`
- name: `?Join@TimerWorkItem@tp2@cxl@@UEAAXK@Z`
- size: `271`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this, DWORD dwMilliseconds)`
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
- `0x18001a320`
- `0x18001d784`
- `0x18001d7e0`
- `0x18001dc20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d81f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d81f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d8b8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d8b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d872`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d872`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d8a4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d8a4`

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
0x18001d7e0  mov     [rsp-8+arg_10], rbx
0x18001d7e5  mov     [rsp-8+arg_18], rdi
0x18001d7ea  push    rbp
0x18001d7eb  lea     rbp, [rsp-57h]
0x18001d7f0  sub     rsp, 90h
0x18001d7f7  mov     rax, cs:__security_cookie
0x18001d7fe  xor     rax, rsp
0x18001d801  mov     [rbp+57h+var_8], rax
0x18001d805  mov     edi, edx
0x18001d807  mov     rbx, rcx
0x18001d80a  mov     eax, [rcx+18h]
0x18001d80d  cmp     eax, 3
0x18001d810  jz      loc_18001D8CD
0x18001d816  call    ?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001d81b  test    al, al
0x18001d81d  jz      short loc_18001D89A
0x18001d81f  call    cs:__imp_GetLastError
0x18001d826  nop     dword ptr [rax+rax+00h]
0x18001d82b  mov     [rbp+57h+var_50], eax
0x18001d82e  lea     rcx, [rbp+57h+var_28]
0x18001d832  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d837  lea     rdx, [rbp+57h+var_28]
0x18001d83b  lea     rcx, [rbp+57h+var_4C+4]
0x18001d83f  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001d844  mov     dword ptr [rbp+57h+var_4C], 4ABh
0x18001d84b  lea     rax, [rbp+57h+var_50]
0x18001d84f  mov     [rsp+90h+var_60], rax; __int64
0x18001d854  lea     rax, [rbp+57h+var_4C]
0x18001d858  mov     [rsp+90h+var_70], rax; __int64
0x18001d85d  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001d861  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0BO@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0BO@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [30],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[30],ulong const &)
0x18001d866  lea     rcx, [rbp+57h+var_28]
0x18001d86a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d86f  mov     rcx, rax; lpOutputString
0x18001d872  call    cs:__imp_OutputDebugStringW
0x18001d879  nop     dword ptr [rax+rax+00h]
0x18001d87e  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001d881  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001d886  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001d88d  mov     [rbp+57h+var_4C+4], rax
0x18001d891  lea     rcx, [rbp+57h+var_28]
0x18001d895  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d89a  mov     eax, [rbx+18h]
0x18001d89d  cmp     eax, 1
0x18001d8a0  jnz     short loc_18001D8B2
0x18001d8a2  mov     ecx, edi; dwMilliseconds
0x18001d8a4  call    cs:__imp_Sleep
0x18001d8ab  nop     dword ptr [rax+rax+00h]
0x18001d8b0  jmp     short loc_18001D89A
0x18001d8b2  xor     edx, edx; fCancelPendingCallbacks
0x18001d8b4  mov     rcx, [rbx+38h]; pti
0x18001d8b8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001d8bf  nop     dword ptr [rax+rax+00h]
0x18001d8c4  mov     rcx, rbx; this
0x18001d8c7  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001d8cc  nop
0x18001d8cd  mov     rcx, [rbp+57h+var_8]
0x18001d8d1  xor     rcx, rsp; StackCookie
0x18001d8d4  call    __security_check_cookie
0x18001d8d9  lea     r11, [rsp+90h+var_s0]
0x18001d8e1  mov     rbx, [r11+20h]
0x18001d8e5  mov     rdi, [r11+28h]
0x18001d8e9  mov     rsp, r11
0x18001d8ec  pop     rbp
0x18001d8ed  retn
```
