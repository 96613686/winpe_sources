# _ClusWmi::TaskManager::ScheduledTask::ExecuteTask__lambda_6f66528e1ae7293b25a3b66c9ae688ab____::_1_::catch$17

- ea: `0x1800878b2`
- end: `0x180087998`
- name: `_ClusWmi::TaskManager::ScheduledTask::ExecuteTask__lambda_6f66528e1ae7293b25a3b66c9ae688ab____::_1_::catch$17`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cde0`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x180011184`
- `0x180015578`
- `0x18001c694`
- `0x18001c7c4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878f2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180087956`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180087956`

## string_xrefs

- `0x1800878e3`: `An Error occurred processing the completion of Task '{0}' due to {1}.`

## pseudocode

```c
__int64 __fastcall ClusWmi::TaskManager::ScheduledTask::ExecuteTask__lambda_6f66528e1ae7293b25a3b66c9ae688ab____::_1_::catch_17(
        __int64 a1,
        __int64 a2)
{
  struct cxl::TextWriter *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  const WCHAR *v7; // rax
  int v9; // [rsp+28h] [rbp-30h]

  v3 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
  (***(void (__fastcall ****)(_QWORD))(*(_QWORD *)(a2 + 64) + 32LL))(*(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL));
  cxl::TextWriter::WriteLine<char,std::wstring,cxl::Exception>(
    v3,
    "An Error occurred processing the completion of Task '{0}' due to {1}.");
  *(_DWORD *)(a2 + 96) = GetLastError();
  std::wstring::wstring(a2 + 128);
  cxl::StringWriter::StringWriter(a2 + 160, a2 + 128);
  *(_DWORD *)(a2 + 64) = 374;
  cxl::TextWriter::WriteLine<char,char [6],char [63],int,char [49],unsigned long>(
    (struct cxl::TextWriter *)(a2 + 160),
    v4,
    v5,
    v6,
    a2 + 64,
    v9,
    a2 + 96);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2 + 128);
  OutputDebugStringW(v7);
  cxl::Debug::StopIfIsDebuggedOrCrash(*(_DWORD *)(a2 + 96));
  *(_QWORD *)(a2 + 160) = &cxl::RefCounted::`vftable';
  std::wstring::_Tidy_deallocate(a2 + 128);
  return 0;
}

```

## disassembly

```asm
0x1800878b2  mov     [rsp+arg_8], rdx
0x1800878b7  push    rbx
0x1800878b8  push    rbp
0x1800878b9  sub     rsp, 48h
0x1800878bd  mov     rbp, rdx
0x1800878c0  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800878c5  lea     rbx, [rax+28h]
0x1800878c9  mov     rax, [rbp+40h]
0x1800878cd  mov     rcx, [rax+20h]
0x1800878d1  mov     rax, [rcx]
0x1800878d4  mov     rax, [rax]
0x1800878d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800878dc  mov     r9, [rbp+58h]
0x1800878e0  mov     r8, rax
0x1800878e3  lea     rdx, aAnErrorOccurre; "An Error occurred processing the comple"...
0x1800878ea  mov     rcx, rbx; struct cxl::TextWriter *
0x1800878ed  call    ??$WriteLine@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VException@cxl@@@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVException@1@@Z; cxl::TextWriter::WriteLine<char,std::wstring,cxl::Exception>(char const *,std::wstring const &,cxl::Exception const &)
0x1800878f2  call    cs:__imp_GetLastError
0x1800878f9  nop     dword ptr [rax+rax+00h]
0x1800878fe  mov     [rbp+60h], eax
0x180087901  lea     rcx, [rbp+80h]
0x180087908  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008790d  nop
0x18008790e  lea     rdx, [rbp+80h]
0x180087915  lea     rcx, [rbp+0A0h]
0x18008791c  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180087921  nop
0x180087922  mov     dword ptr [rbp+40h], 176h
0x180087929  lea     rax, [rbp+60h]
0x18008792d  mov     [rsp+58h+var_28], rax; __int64
0x180087932  lea     rax, [rbp+40h]
0x180087936  mov     [rsp+58h+var_38], rax; __int64
0x18008793b  lea     rcx, [rbp+0A0h]; struct cxl::TextWriter *
0x180087942  call    ??$WriteLine@D$$BY05D$$BY0DP@DH$$BY0DB@DK@TextWriter@cxl@@QEAAXPEBDAEAY05$$CBDAEAY0DP@$$CBDAEBHAEAY0DB@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [6],char [63],int,char [49],ulong>(char const *,char const (&)[6],char const (&)[63],int const &,char const (&)[49],ulong const &)
0x180087947  lea     rcx, [rbp+80h]
0x18008794e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180087953  mov     rcx, rax; lpOutputString
0x180087956  call    cs:__imp_OutputDebugStringW
0x18008795d  nop     dword ptr [rax+rax+00h]
0x180087962  mov     ecx, [rbp+60h]; unsigned int
0x180087965  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18008796a  nop
0x18008796b  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x180087972  mov     [rbp+0A0h], rax
0x180087979  lea     rcx, [rbp+80h]
0x180087980  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180087985  nop
0x180087986  mov     rax, 0
0x180087990  add     rsp, 48h
0x180087994  pop     rbp
0x180087995  pop     rbx
0x180087996  retn
```
