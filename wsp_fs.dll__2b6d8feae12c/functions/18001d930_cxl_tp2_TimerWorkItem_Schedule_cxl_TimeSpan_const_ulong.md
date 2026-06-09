# cxl::tp2::TimerWorkItem::Schedule(cxl::TimeSpan const &,ulong)

- ea: `0x18001d930`
- end: `0x18001da8e`
- name: `?Schedule@TimerWorkItem@tp2@cxl@@QEAAXAEBUTimeSpan@3@K@Z`
- size: `350`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this, const struct cxl::TimeSpan *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001d8a4`
- `0x180020b6c`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000d298`
- `0x18000dd74`
- `0x180012028`
- `0x180016830`
- `0x1800196b4`
- `0x180019b3c`
- `0x18001d0f0`
- `0x18001d930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001da68`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001da68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d9b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001da23`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d9b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001da23`

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
0x18001d930  mov     [rsp-8+arg_10], rbx
0x18001d935  push    rbp
0x18001d936  push    rsi
0x18001d937  push    rdi
0x18001d938  lea     rbp, [rsp-47h]
0x18001d93d  sub     rsp, 0A0h
0x18001d944  mov     rax, cs:__security_cookie
0x18001d94b  xor     rax, rsp
0x18001d94e  mov     [rbp+57h+var_20], rax
0x18001d952  mov     rdi, rdx
0x18001d955  mov     rbx, rcx
0x18001d958  mov     eax, [rcx+18h]
0x18001d95b  lea     rsi, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001d962  cmp     eax, 3
0x18001d965  jnz     short loc_18001D9CF
0x18001d967  call    cs:__imp_GetLastError
0x18001d96d  mov     [rbp+57h+var_70], eax
0x18001d970  lea     rcx, [rbp+57h+var_40]
0x18001d974  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d979  lea     rdx, [rbp+57h+var_40]
0x18001d97d  lea     rcx, [rbp+57h+var_60]
0x18001d981  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001d986  mov     dword ptr [rbp+57h+var_6C], 485h
0x18001d98d  lea     rax, [rbp+57h+var_70]
0x18001d991  mov     [rsp+0B0h+var_80], rax; __int64
0x18001d996  lea     rax, [rbp+57h+var_6C]
0x18001d99a  mov     [rsp+0B0h+var_90], rax; __int64
0x18001d99f  lea     rcx, [rbp+57h+var_60]; struct cxl::TextWriter *
0x18001d9a3  call    ??$WriteLine@D$$BY0M@D$$BY0DM@DH$$BY0CC@DK@TextWriter@cxl@@QEAAXPEBDAEAY0M@$$CBDAEAY0DM@$$CBDAEBHAEAY0CC@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [34],ulong>(char const *,char const (&)[12],char const (&)[60],int const &,char const (&)[34],ulong const &)
0x18001d9a8  lea     rcx, [rbp+57h+var_40]
0x18001d9ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d9b1  mov     rcx, rax; lpOutputString
0x18001d9b4  call    cs:__imp_OutputDebugStringW
0x18001d9ba  mov     ecx, [rbp+57h+var_70]; unsigned int
0x18001d9bd  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001d9c2  mov     [rbp+57h+var_60], rsi
0x18001d9c6  lea     rcx, [rbp+57h+var_40]
0x18001d9ca  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d9cf  cmp     qword ptr [rbx+28h], 0
0x18001d9d4  jnz     short loc_18001DA3E
0x18001d9d6  call    cs:__imp_GetLastError
0x18001d9dc  mov     [rbp+57h+var_70], eax
0x18001d9df  lea     rcx, [rbp+57h+var_40]
0x18001d9e3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d9e8  lea     rdx, [rbp+57h+var_40]
0x18001d9ec  lea     rcx, [rbp+57h+var_60]
0x18001d9f0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001d9f5  mov     dword ptr [rbp+57h+var_6C], 486h
0x18001d9fc  lea     rax, [rbp+57h+var_70]
0x18001da00  mov     [rsp+0B0h+var_80], rax; __int64
0x18001da05  lea     rax, [rbp+57h+var_6C]
0x18001da09  mov     [rsp+0B0h+var_90], rax; __int64
0x18001da0e  lea     rcx, [rbp+57h+var_60]; struct cxl::TextWriter *
0x18001da12  call    ??$WriteLine@D$$BY0BF@D$$BY0DM@DH$$BY0CC@DK@TextWriter@cxl@@QEAAXPEBDAEAY0BF@$$CBDAEAY0DM@$$CBDAEBHAEAY0CC@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [21],char [60],int,char [34],ulong>(char const *,char const (&)[21],char const (&)[60],int const &,char const (&)[34],ulong const &)
0x18001da17  lea     rcx, [rbp+57h+var_40]
0x18001da1b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001da20  mov     rcx, rax; lpOutputString
0x18001da23  call    cs:__imp_OutputDebugStringW
0x18001da29  mov     ecx, [rbp+57h+var_70]; unsigned int
0x18001da2c  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001da31  mov     [rbp+57h+var_60], rsi
0x18001da35  lea     rcx, [rbp+57h+var_40]
0x18001da39  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001da3e  mov     rcx, rbx; this
0x18001da41  call    ?MoveToWaiting@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToWaiting(void)
0x18001da46  mov     rax, [rdi+8]
0x18001da4a  neg     rax
0x18001da4d  mov     rdx, rax
0x18001da50  shr     rdx, 20h
0x18001da54  mov     dword ptr [rbp+57h+var_6C+8], edx
0x18001da57  mov     dword ptr [rbp+57h+var_6C+4], eax
0x18001da5a  xor     r9d, r9d; msWindowLength
0x18001da5d  xor     r8d, r8d; msPeriod
0x18001da60  lea     rdx, [rbp+57h+var_6C+4]; pftDueTime
0x18001da64  mov     rcx, [rbx+38h]; pti
0x18001da68  call    cs:__imp_SetThreadpoolTimer
0x18001da6e  nop
0x18001da6f  mov     rcx, [rbp+57h+var_20]
0x18001da73  xor     rcx, rsp; StackCookie
0x18001da76  call    __security_check_cookie
0x18001da7b  mov     rbx, [rsp+0B0h+arg_10]
0x18001da83  add     rsp, 0A0h
0x18001da8a  pop     rdi
0x18001da8b  pop     rsi
0x18001da8c  pop     rbp
0x18001da8d  retn
```
