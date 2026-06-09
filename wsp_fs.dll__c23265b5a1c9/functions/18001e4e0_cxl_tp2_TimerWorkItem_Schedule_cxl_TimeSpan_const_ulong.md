# cxl::tp2::TimerWorkItem::Schedule(cxl::TimeSpan const &,ulong)

- ea: `0x18001e4e0`
- end: `0x18001e65d`
- name: `?Schedule@TimerWorkItem@tp2@cxl@@QEAAXAEBUTimeSpan@3@K@Z`
- size: `381`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this, const struct cxl::TimeSpan *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001e450`
- `0x18002180c`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000d600`
- `0x18000e14c`
- `0x1800124ac`
- `0x180016fb8`
- `0x18001a0c8`
- `0x18001a578`
- `0x18001dc40`
- `0x18001e4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e592`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e630`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e630`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e56a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e5e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e56a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e5e5`

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
0x18001e4e0  mov     [rsp-8+arg_10], rbx
0x18001e4e5  push    rbp
0x18001e4e6  push    rsi
0x18001e4e7  push    rdi
0x18001e4e8  lea     rbp, [rsp-47h]
0x18001e4ed  sub     rsp, 0A0h
0x18001e4f4  mov     rax, cs:__security_cookie
0x18001e4fb  xor     rax, rsp
0x18001e4fe  mov     [rbp+57h+var_20], rax
0x18001e502  mov     rdi, rdx
0x18001e505  mov     rbx, rcx
0x18001e508  mov     eax, [rcx+18h]
0x18001e50b  lea     rsi, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001e512  cmp     eax, 3
0x18001e515  jnz     short loc_18001E58B
0x18001e517  call    cs:__imp_GetLastError
0x18001e51e  nop     dword ptr [rax+rax+00h]
0x18001e523  mov     [rbp+57h+var_70], eax
0x18001e526  lea     rcx, [rbp+57h+var_40]
0x18001e52a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e52f  lea     rdx, [rbp+57h+var_40]
0x18001e533  lea     rcx, [rbp+57h+var_60]
0x18001e537  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001e53c  mov     dword ptr [rbp+57h+var_6C], 485h
0x18001e543  lea     rax, [rbp+57h+var_70]
0x18001e547  mov     [rsp+0B0h+var_80], rax; __int64
0x18001e54c  lea     rax, [rbp+57h+var_6C]
0x18001e550  mov     [rsp+0B0h+var_90], rax; __int64
0x18001e555  lea     rcx, [rbp+57h+var_60]; struct cxl::TextWriter *
0x18001e559  call    ??$WriteLine@D$$BY0M@D$$BY0DM@DH$$BY0CC@DK@TextWriter@cxl@@QEAAXPEBDAEAY0M@$$CBDAEAY0DM@$$CBDAEBHAEAY0CC@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [34],ulong>(char const *,char const (&)[12],char const (&)[60],int const &,char const (&)[34],ulong const &)
0x18001e55e  lea     rcx, [rbp+57h+var_40]
0x18001e562  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e567  mov     rcx, rax; lpOutputString
0x18001e56a  call    cs:__imp_OutputDebugStringW
0x18001e571  nop     dword ptr [rax+rax+00h]
0x18001e576  mov     ecx, [rbp+57h+var_70]; unsigned int
0x18001e579  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001e57e  mov     [rbp+57h+var_60], rsi
0x18001e582  lea     rcx, [rbp+57h+var_40]
0x18001e586  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e58b  cmp     qword ptr [rbx+28h], 0
0x18001e590  jnz     short loc_18001E606
0x18001e592  call    cs:__imp_GetLastError
0x18001e599  nop     dword ptr [rax+rax+00h]
0x18001e59e  mov     [rbp+57h+var_70], eax
0x18001e5a1  lea     rcx, [rbp+57h+var_40]
0x18001e5a5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e5aa  lea     rdx, [rbp+57h+var_40]
0x18001e5ae  lea     rcx, [rbp+57h+var_60]
0x18001e5b2  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001e5b7  mov     dword ptr [rbp+57h+var_6C], 486h
0x18001e5be  lea     rax, [rbp+57h+var_70]
0x18001e5c2  mov     [rsp+0B0h+var_80], rax; __int64
0x18001e5c7  lea     rax, [rbp+57h+var_6C]
0x18001e5cb  mov     [rsp+0B0h+var_90], rax; __int64
0x18001e5d0  lea     rcx, [rbp+57h+var_60]; struct cxl::TextWriter *
0x18001e5d4  call    ??$WriteLine@D$$BY0BF@D$$BY0DM@DH$$BY0CC@DK@TextWriter@cxl@@QEAAXPEBDAEAY0BF@$$CBDAEAY0DM@$$CBDAEBHAEAY0CC@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [21],char [60],int,char [34],ulong>(char const *,char const (&)[21],char const (&)[60],int const &,char const (&)[34],ulong const &)
0x18001e5d9  lea     rcx, [rbp+57h+var_40]
0x18001e5dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e5e2  mov     rcx, rax; lpOutputString
0x18001e5e5  call    cs:__imp_OutputDebugStringW
0x18001e5ec  nop     dword ptr [rax+rax+00h]
0x18001e5f1  mov     ecx, [rbp+57h+var_70]; unsigned int
0x18001e5f4  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001e5f9  mov     [rbp+57h+var_60], rsi
0x18001e5fd  lea     rcx, [rbp+57h+var_40]
0x18001e601  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e606  mov     rcx, rbx; this
0x18001e609  call    ?MoveToWaiting@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToWaiting(void)
0x18001e60e  mov     rax, [rdi+8]
0x18001e612  neg     rax
0x18001e615  mov     rdx, rax
0x18001e618  shr     rdx, 20h
0x18001e61c  mov     dword ptr [rbp+57h+var_6C+8], edx
0x18001e61f  mov     dword ptr [rbp+57h+var_6C+4], eax
0x18001e622  xor     r9d, r9d; msWindowLength
0x18001e625  xor     r8d, r8d; msPeriod
0x18001e628  lea     rdx, [rbp+57h+var_6C+4]; pftDueTime
0x18001e62c  mov     rcx, [rbx+38h]; pti
0x18001e630  call    cs:__imp_SetThreadpoolTimer
0x18001e637  nop     dword ptr [rax+rax+00h]
0x18001e63c  nop
0x18001e63d  mov     rcx, [rbp+57h+var_20]
0x18001e641  xor     rcx, rsp; StackCookie
0x18001e644  call    __security_check_cookie
0x18001e649  mov     rbx, [rsp+0B0h+arg_10]
0x18001e651  add     rsp, 0A0h
0x18001e658  pop     rdi
0x18001e659  pop     rsi
0x18001e65a  pop     rbp
0x18001e65b  retn
```
