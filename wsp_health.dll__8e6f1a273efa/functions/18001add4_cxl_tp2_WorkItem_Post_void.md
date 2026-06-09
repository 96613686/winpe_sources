# cxl::tp2::WorkItem::Post(void)

- ea: `0x18001add4`
- end: `0x18001aeb1`
- name: `?Post@WorkItem@tp2@cxl@@QEAAXXZ`
- size: `221`
- prototype: `void __fastcall(cxl::tp2::WorkItem *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18001ad20`
- `0x18001dfe0`

## callees

- `0x180002b50`
- `0x18000cde0`
- `0x18000da34`
- `0x18000daf8`
- `0x180011184`
- `0x180015578`
- `0x180017304`
- `0x18001aa60`
- `0x18001add4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ae86`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ae86`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ae52`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ae52`

## pseudocode

```c
void __fastcall cxl::tp2::WorkItem::Post(cxl::tp2::WorkItem *this)
{
  const WCHAR *v2; // rax
  int v3; // [rsp+28h] [rbp-11h]
  unsigned int LastError; // [rsp+40h] [rbp+7h] BYREF
  int v5; // [rsp+44h] [rbp+Bh] BYREF
  _QWORD v6[4]; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v7[32]; // [rsp+68h] [rbp+2Fh] BYREF

  if ( *((_DWORD *)this + 6) == 3 )
  {
    LastError = GetLastError();
    std::wstring::wstring(v7);
    cxl::StringWriter::StringWriter(v6, v7);
    v5 = 950;
    cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [25],unsigned long>(
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
  cxl::tp2::WorkItemBase::MoveToWaiting(this);
  SubmitThreadpoolWork(*((PTP_WORK *)this + 11));
}

```

## disassembly

```asm
0x18001add4  mov     [rsp-8+arg_8], rbx
0x18001add9  push    rbp
0x18001adda  lea     rbp, [rsp-57h]
0x18001addf  sub     rsp, 90h
0x18001ade6  mov     rax, cs:__security_cookie
0x18001aded  xor     rax, rsp
0x18001adf0  mov     [rbp+57h+var_8], rax
0x18001adf4  mov     rbx, rcx
0x18001adf7  mov     eax, [rcx+18h]
0x18001adfa  cmp     eax, 3
0x18001adfd  jnz     short loc_18001AE7A
0x18001adff  call    cs:__imp_GetLastError
0x18001ae06  nop     dword ptr [rax+rax+00h]
0x18001ae0b  mov     [rbp+57h+var_50], eax
0x18001ae0e  lea     rcx, [rbp+57h+var_28]
0x18001ae12  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ae17  lea     rdx, [rbp+57h+var_28]
0x18001ae1b  lea     rcx, [rbp+57h+var_4C+4]
0x18001ae1f  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001ae24  mov     dword ptr [rbp+57h+var_4C], 3B6h
0x18001ae2b  lea     rax, [rbp+57h+var_50]
0x18001ae2f  mov     [rsp+90h+var_60], rax; __int64
0x18001ae34  lea     rax, [rbp+57h+var_4C]
0x18001ae38  mov     [rsp+90h+var_70], rax; __int64
0x18001ae3d  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x18001ae41  call    ??$WriteLine@D$$BY0M@D$$BY0DM@DH$$BY0BJ@DK@TextWriter@cxl@@QEAAXPEBDAEAY0M@$$CBDAEAY0DM@$$CBDAEBHAEAY0BJ@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [12],char [60],int,char [25],ulong>(char const *,char const (&)[12],char const (&)[60],int const &,char const (&)[25],ulong const &)
0x18001ae46  lea     rcx, [rbp+57h+var_28]
0x18001ae4a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ae4f  mov     rcx, rax; lpOutputString
0x18001ae52  call    cs:__imp_OutputDebugStringW
0x18001ae59  nop     dword ptr [rax+rax+00h]
0x18001ae5e  mov     ecx, [rbp+57h+var_50]; unsigned int
0x18001ae61  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001ae66  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001ae6d  mov     [rbp+57h+var_4C+4], rax
0x18001ae71  lea     rcx, [rbp+57h+var_28]
0x18001ae75  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ae7a  mov     rcx, rbx; this
0x18001ae7d  call    ?MoveToWaiting@WorkItemBase@tp2@cxl@@IEAAXXZ; cxl::tp2::WorkItemBase::MoveToWaiting(void)
0x18001ae82  mov     rcx, [rbx+58h]; pwk
0x18001ae86  call    cs:__imp_SubmitThreadpoolWork
0x18001ae8d  nop     dword ptr [rax+rax+00h]
0x18001ae92  nop
0x18001ae93  mov     rcx, [rbp+57h+var_8]
0x18001ae97  xor     rcx, rsp; StackCookie
0x18001ae9a  call    __security_check_cookie
0x18001ae9f  mov     rbx, [rsp+90h+arg_8]
0x18001aea7  add     rsp, 90h
0x18001aeae  pop     rbp
0x18001aeaf  retn
```
