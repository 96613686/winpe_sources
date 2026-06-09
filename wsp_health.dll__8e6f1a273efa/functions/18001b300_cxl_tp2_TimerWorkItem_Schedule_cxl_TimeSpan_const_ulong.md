# cxl::tp2::TimerWorkItem::Schedule(cxl::TimeSpan const &,ulong)

- ea: `0x18001b300`
- end: `0x18001b47d`
- name: `?Schedule@TimerWorkItem@tp2@cxl@@QEAAXAEBUTimeSpan@3@K@Z`
- size: `381`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this, const struct cxl::TimeSpan *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001b270`
- `0x18001e4cc`

## callees

- `0x180002b50`
- `0x18000cde0`
- `0x18000da34`
- `0x18000daf8`
- `0x180011184`
- `0x180015578`
- `0x180016ecc`
- `0x18001737c`
- `0x18001aa60`
- `0x18001b300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b450`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b450`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b38a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b405`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b38a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b405`

## pseudocode

```c
void __fastcall cxl::tp2::TimerWorkItem::Schedule(cxl::tp2::TimerWorkItem *this, const struct cxl::TimeSpan *a2)
{
  const WCHAR *v4; // rax
  const WCHAR *v5; // rax
  __int64 v6; // rax
  int v7; // [rsp+28h] [rbp-31h]
  unsigned int LastError; // [rsp+40h] [rbp-19h] BYREF
  _DWORD v9[3]; // [rsp+44h] [rbp-15h] BYREF
  _QWORD v10[4]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v11[32]; // [rsp+70h] [rbp+17h] BYREF

  if ( *((_DWORD *)this + 6) == 3 )
  {
    LastError = GetLastError();
    std::wstring::wstring(v11);
    cxl::StringWriter::StringWriter(v10, v11);
    v9[0] = 1157;
    cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [34],unsigned long>(
      (struct cxl::TextWriter *)v10,
      (__int64)v9,
      v7,
      (__int64)&LastError);
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v11);
    OutputDebugStringW(v4);
    cxl::Debug::StopIfIsDebuggedOrCrash(LastError);
    v10[0] = &cxl::RefCounted::`vftable';
    std::wstring::_Tidy_deallocate(v11);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    LastError = GetLastError();
    std::wstring::wstring(v11);
    cxl::StringWriter::StringWriter(v10, v11);
    v9[0] = 1158;
    cxl::TextWriter::WriteLine<char,char [21],char [60],int,char [34],unsigned long>(
      (struct cxl::TextWriter *)v10,
      (__int64)v9,
      v7,
      (__int64)&LastError);
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v11);
    OutputDebugStringW(v5);
    cxl::Debug::StopIfIsDebuggedOrCrash(LastError);
    v10[0] = &cxl::RefCounted::`vftable';
    std::wstring::_Tidy_deallocate(v11);
  }
  cxl::tp2::WorkItemBase::MoveToWaiting(this);
  v6 = -*((_QWORD *)a2 + 1);
  *(_QWORD *)&v9[1] = v6;
  SetThreadpoolTimer(*((PTP_TIMER *)this + 7), (PFILETIME)&v9[1], 0, 0);
}

```

## disassembly

```asm
0x18001b300  mov     [rsp-8+arg_10], rbx
0x18001b305  push    rbp
0x18001b306  push    rsi
0x18001b307  push    rdi
0x18001b308  lea     rbp, [rsp-47h]
0x18001b30d  sub     rsp, 0A0h
0x18001b314  mov     rax, cs:__security_cookie
0x18001b31b  xor     rax, rsp
0x18001b31e  mov     [rbp+57h+var_20], rax
0x18001b322  mov     rdi, rdx
0x18001b325  mov     rbx, rcx
0x18001b328  mov     eax, [rcx+18h]
0x18001b32b  lea     rsi, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001b332  cmp     eax, 3
0x18001b335  jnz     short loc_18001B3AB
0x18001b337  call    cs:__imp_GetLastError
0x18001b33e  nop     dword ptr [rax+rax+00h]
0x18001b343  mov     [rbp+57h+var_70], eax
0x18001b346  lea     rcx, [rbp+57h+var_40]
0x18001b34a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b34f  lea     rdx, [rbp+57h+var_40]
0x18001b353  lea     rcx, [rbp+57h+var_60]
0x18001b357  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001b35c  mov     dword ptr [rbp+57h+var_6C], 485h
0x18001b363  lea     rax, [rbp+57h+var_70]
0x18001b367  mov     [rsp+0B0h+var_80], rax; __int64
0x18001b36c  lea     rax, [rbp+57h+var_6C]
0x18001b370  mov     [rsp+0B0h+var_90], rax; __int64
0x18001b375  lea     rcx, [rbp+57h+var_60]; struct cxl::TextWriter *
0x18001b379  call    ??$WriteLine@D$$BY0M@D$$BY0DM@DH$$BY0CC@DK@TextWriter@cxl@@QEAAXPEBDAEAY0M@$$CBDAEAY0DM@$$CBDAEBHAEAY0CC@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [34],ulong>(char const *,char const (&)[12],char const (&)[60],int const &,char const (&)[34],ulong const &)
0x18001b37e  lea     rcx, [rbp+57h+var_40]
0x18001b382  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b387  mov     rcx, rax; lpOutputString
0x18001b38a  call    cs:__imp_OutputDebugStringW
0x18001b391  nop     dword ptr [rax+rax+00h]
0x18001b396  mov     ecx, [rbp+57h+var_70]; unsigned int
0x18001b399  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001b39e  mov     [rbp+57h+var_60], rsi
0x18001b3a2  lea     rcx, [rbp+57h+var_40]
0x18001b3a6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b3ab  cmp     qword ptr [rbx+28h], 0
0x18001b3b0  jnz     short loc_18001B426
0x18001b3b2  call    cs:__imp_GetLastError
0x18001b3b9  nop     dword ptr [rax+rax+00h]
0x18001b3be  mov     [rbp+57h+var_70], eax
0x18001b3c1  lea     rcx, [rbp+57h+var_40]
0x18001b3c5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b3ca  lea     rdx, [rbp+57h+var_40]
0x18001b3ce  lea     rcx, [rbp+57h+var_60]
0x18001b3d2  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001b3d7  mov     dword ptr [rbp+57h+var_6C], 486h
0x18001b3de  lea     rax, [rbp+57h+var_70]
0x18001b3e2  mov     [rsp+0B0h+var_80], rax; __int64
0x18001b3e7  lea     rax, [rbp+57h+var_6C]
0x18001b3eb  mov     [rsp+0B0h+var_90], rax; __int64
0x18001b3f0  lea     rcx, [rbp+57h+var_60]; struct cxl::TextWriter *
0x18001b3f4  call    ??$WriteLine@D$$BY0BF@D$$BY0DM@DH$$BY0CC@DK@TextWriter@cxl@@QEAAXPEBDAEAY0BF@$$CBDAEAY0DM@$$CBDAEBHAEAY0CC@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [21],char [60],int,char [34],ulong>(char const *,char const (&)[21],char const (&)[60],int const &,char const (&)[34],ulong const &)
0x18001b3f9  lea     rcx, [rbp+57h+var_40]
0x18001b3fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b402  mov     rcx, rax; lpOutputString
0x18001b405  call    cs:__imp_OutputDebugStringW
0x18001b40c  nop     dword ptr [rax+rax+00h]
0x18001b411  mov     ecx, [rbp+57h+var_70]; unsigned int
0x18001b414  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001b419  mov     [rbp+57h+var_60], rsi
0x18001b41d  lea     rcx, [rbp+57h+var_40]
0x18001b421  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b426  mov     rcx, rbx; this
0x18001b429  call    ?MoveToWaiting@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToWaiting(void)
0x18001b42e  mov     rax, [rdi+8]
0x18001b432  neg     rax
0x18001b435  mov     rdx, rax
0x18001b438  shr     rdx, 20h
0x18001b43c  mov     dword ptr [rbp+57h+var_6C+8], edx
0x18001b43f  mov     dword ptr [rbp+57h+var_6C+4], eax
0x18001b442  xor     r9d, r9d; msWindowLength
0x18001b445  xor     r8d, r8d; msPeriod
0x18001b448  lea     rdx, [rbp+57h+var_6C+4]; pftDueTime
0x18001b44c  mov     rcx, [rbx+38h]; pti
0x18001b450  call    cs:__imp_SetThreadpoolTimer
0x18001b457  nop     dword ptr [rax+rax+00h]
0x18001b45c  nop
0x18001b45d  mov     rcx, [rbp+57h+var_20]
0x18001b461  xor     rcx, rsp; StackCookie
0x18001b464  call    __security_check_cookie
0x18001b469  mov     rbx, [rsp+0B0h+arg_10]
0x18001b471  add     rsp, 0A0h
0x18001b478  pop     rdi
0x18001b479  pop     rsi
0x18001b47a  pop     rbp
0x18001b47b  retn
```
