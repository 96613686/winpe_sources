# cxl::tp2::TimerWorkItem::Schedule(cxl::TimeSpan const &,ulong)

- ea: `0x18001a850`
- end: `0x18001a9ae`
- name: `?Schedule@TimerWorkItem@tp2@cxl@@QEAAXAEBUTimeSpan@3@K@Z`
- size: `350`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this, const struct cxl::TimeSpan *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001a7c4`
- `0x18001d91c`

## callees

- `0x180002ae0`
- `0x18000ca34`
- `0x18000d618`
- `0x18000d6dc`
- `0x180010ca4`
- `0x180014dc0`
- `0x1800165ac`
- `0x180016a34`
- `0x18001a010`
- `0x18001a850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a988`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a988`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a8d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a943`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a8d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a943`

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
0x18001a850  mov     [rsp-8+arg_10], rbx
0x18001a855  push    rbp
0x18001a856  push    rsi
0x18001a857  push    rdi
0x18001a858  lea     rbp, [rsp-47h]
0x18001a85d  sub     rsp, 0A0h
0x18001a864  mov     rax, cs:__security_cookie
0x18001a86b  xor     rax, rsp
0x18001a86e  mov     [rbp+57h+var_20], rax
0x18001a872  mov     rdi, rdx
0x18001a875  mov     rbx, rcx
0x18001a878  mov     eax, [rcx+18h]
0x18001a87b  lea     rsi, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001a882  cmp     eax, 3
0x18001a885  jnz     short loc_18001A8EF
0x18001a887  call    cs:__imp_GetLastError
0x18001a88d  mov     [rbp+57h+var_70], eax
0x18001a890  lea     rcx, [rbp+57h+var_40]
0x18001a894  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a899  lea     rdx, [rbp+57h+var_40]
0x18001a89d  lea     rcx, [rbp+57h+var_60]
0x18001a8a1  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001a8a6  mov     dword ptr [rbp+57h+var_6C], 485h
0x18001a8ad  lea     rax, [rbp+57h+var_70]
0x18001a8b1  mov     [rsp+0B0h+var_80], rax; __int64
0x18001a8b6  lea     rax, [rbp+57h+var_6C]
0x18001a8ba  mov     [rsp+0B0h+var_90], rax; __int64
0x18001a8bf  lea     rcx, [rbp+57h+var_60]; struct cxl::TextWriter *
0x18001a8c3  call    ??$WriteLine@D$$BY0M@D$$BY0DM@DH$$BY0CC@DK@TextWriter@cxl@@QEAAXPEBDAEAY0M@$$CBDAEAY0DM@$$CBDAEBHAEAY0CC@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [34],ulong>(char const *,char const (&)[12],char const (&)[60],int const &,char const (&)[34],ulong const &)
0x18001a8c8  lea     rcx, [rbp+57h+var_40]
0x18001a8cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a8d1  mov     rcx, rax; lpOutputString
0x18001a8d4  call    cs:__imp_OutputDebugStringW
0x18001a8da  mov     ecx, [rbp+57h+var_70]; unsigned int
0x18001a8dd  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001a8e2  mov     [rbp+57h+var_60], rsi
0x18001a8e6  lea     rcx, [rbp+57h+var_40]
0x18001a8ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a8ef  cmp     qword ptr [rbx+28h], 0
0x18001a8f4  jnz     short loc_18001A95E
0x18001a8f6  call    cs:__imp_GetLastError
0x18001a8fc  mov     [rbp+57h+var_70], eax
0x18001a8ff  lea     rcx, [rbp+57h+var_40]
0x18001a903  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a908  lea     rdx, [rbp+57h+var_40]
0x18001a90c  lea     rcx, [rbp+57h+var_60]
0x18001a910  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001a915  mov     dword ptr [rbp+57h+var_6C], 486h
0x18001a91c  lea     rax, [rbp+57h+var_70]
0x18001a920  mov     [rsp+0B0h+var_80], rax; __int64
0x18001a925  lea     rax, [rbp+57h+var_6C]
0x18001a929  mov     [rsp+0B0h+var_90], rax; __int64
0x18001a92e  lea     rcx, [rbp+57h+var_60]; struct cxl::TextWriter *
0x18001a932  call    ??$WriteLine@D$$BY0BF@D$$BY0DM@DH$$BY0CC@DK@TextWriter@cxl@@QEAAXPEBDAEAY0BF@$$CBDAEAY0DM@$$CBDAEBHAEAY0CC@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [21],char [60],int,char [34],ulong>(char const *,char const (&)[21],char const (&)[60],int const &,char const (&)[34],ulong const &)
0x18001a937  lea     rcx, [rbp+57h+var_40]
0x18001a93b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a940  mov     rcx, rax; lpOutputString
0x18001a943  call    cs:__imp_OutputDebugStringW
0x18001a949  mov     ecx, [rbp+57h+var_70]; unsigned int
0x18001a94c  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001a951  mov     [rbp+57h+var_60], rsi
0x18001a955  lea     rcx, [rbp+57h+var_40]
0x18001a959  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a95e  mov     rcx, rbx; this
0x18001a961  call    ?MoveToWaiting@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToWaiting(void)
0x18001a966  mov     rax, [rdi+8]
0x18001a96a  neg     rax
0x18001a96d  mov     rdx, rax
0x18001a970  shr     rdx, 20h
0x18001a974  mov     dword ptr [rbp+57h+var_6C+8], edx
0x18001a977  mov     dword ptr [rbp+57h+var_6C+4], eax
0x18001a97a  xor     r9d, r9d; msWindowLength
0x18001a97d  xor     r8d, r8d; msPeriod
0x18001a980  lea     rdx, [rbp+57h+var_6C+4]; pftDueTime
0x18001a984  mov     rcx, [rbx+38h]; pti
0x18001a988  call    cs:__imp_SetThreadpoolTimer
0x18001a98e  nop
0x18001a98f  mov     rcx, [rbp+57h+var_20]
0x18001a993  xor     rcx, rsp; StackCookie
0x18001a996  call    __security_check_cookie
0x18001a99b  mov     rbx, [rsp+0B0h+arg_10]
0x18001a9a3  add     rsp, 0A0h
0x18001a9aa  pop     rdi
0x18001a9ab  pop     rsi
0x18001a9ac  pop     rbp
0x18001a9ad  retn
```
