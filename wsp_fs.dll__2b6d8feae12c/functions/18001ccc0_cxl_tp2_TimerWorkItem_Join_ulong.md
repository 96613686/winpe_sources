# cxl::tp2::TimerWorkItem::Join(ulong)

- ea: `0x18001ccc0`
- end: `0x18001cdb6`
- name: `?Join@TimerWorkItem@tp2@cxl@@UEAAXK@Z`
- size: `246`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this, DWORD dwMilliseconds)`
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
- `0x1800198f8`
- `0x18001cc74`
- `0x18001ccc0`
- `0x18001d0d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001cd86`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001cd86`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cd4c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cd4c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001cd78`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001cd78`

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
0x18001ccc0  mov     [rsp-8+arg_10], rbx
0x18001ccc5  mov     [rsp-8+arg_18], rdi
0x18001ccca  push    rbp
0x18001cccb  lea     rbp, [rsp-57h]
0x18001ccd0  sub     rsp, 90h
0x18001ccd7  mov     rax, cs:__security_cookie
0x18001ccde  xor     rax, rsp
0x18001cce1  mov     [rbp+57h+var_8], rax
0x18001cce5  mov     edi, edx
0x18001cce7  mov     rbx, rcx
0x18001ccea  mov     eax, [rcx+18h]
0x18001cced  cmp     eax, 3
0x18001ccf0  jz      loc_18001CD95
0x18001ccf6  call    ?IsCurrentThreadExecutingCallBack@TimerWorkItem@tp2@cxl@@QEBA_NXZ; cxl::tp2::TimerWorkItem::IsCurrentThreadExecutingCallBack(void)
0x18001ccfb  test    al, al
0x18001ccfd  jz      short loc_18001CD6E
0x18001ccff  call    cs:__imp_GetLastError
0x18001cd05  mov     [rbp+57h+var_50], eax
0x18001cd08  lea     rcx, [rbp+57h+var_28]
0x18001cd0c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001cd11  lea     rdx, [rbp+57h+var_28]
0x18001cd15  lea     rcx, [rbp+57h+var_4C+4]
0x18001cd19  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001cd1e  mov     dword ptr [rbp+57h+var_4C], 4ABh
0x18001cd25  lea     rax, [rbp+57h+var_50]
0x18001cd29  mov     [rsp+90h+var_60], rax; __int64
0x18001cd2e  lea     rax, [rbp+57h+var_4C]
0x18001cd32  mov     [rsp+90h+var_70], rax; __int64
0x18001cd37  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001cd3b  call    ??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0BO@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0BO@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [30],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[30],ulong const &)
0x18001cd40  lea     rcx, [rbp+57h+var_28]
0x18001cd44  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cd49  mov     rcx, rax; lpOutputString
0x18001cd4c  call    cs:__imp_OutputDebugStringW
0x18001cd52  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001cd55  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001cd5a  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001cd61  mov     [rbp+57h+var_4C+4], rax
0x18001cd65  lea     rcx, [rbp+57h+var_28]
0x18001cd69  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cd6e  mov     eax, [rbx+18h]
0x18001cd71  cmp     eax, 1
0x18001cd74  jnz     short loc_18001CD80
0x18001cd76  mov     ecx, edi; dwMilliseconds
0x18001cd78  call    cs:__imp_Sleep
0x18001cd7e  jmp     short loc_18001CD6E
0x18001cd80  xor     edx, edx; fCancelPendingCallbacks
0x18001cd82  mov     rcx, [rbx+38h]; pti
0x18001cd86  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001cd8c  mov     rcx, rbx; this
0x18001cd8f  call    ?MoveToIdle@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToIdle(void)
0x18001cd94  nop
0x18001cd95  mov     rcx, [rbp+57h+var_8]
0x18001cd99  xor     rcx, rsp; StackCookie
0x18001cd9c  call    __security_check_cookie
0x18001cda1  lea     r11, [rsp+90h+var_s0]
0x18001cda9  mov     rbx, [r11+20h]
0x18001cdad  mov     rdi, [r11+28h]
0x18001cdb1  mov     rsp, r11
0x18001cdb4  pop     rbp
0x18001cdb5  retn
```
