# _ClusWmi::TaskManager::ScheduledTask::ExecuteTask__lambda_6f66528e1ae7293b25a3b66c9ae688ab____::_1_::catch$17

- ea: `0x18008548c`
- end: `0x180085566`
- name: `_ClusWmi::TaskManager::ScheduledTask::ExecuteTask__lambda_6f66528e1ae7293b25a3b66c9ae688ab____::_1_::catch$17`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ca34`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x180010ca4`
- `0x180014dc0`
- `0x18001bb70`
- `0x18001bc98`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800854cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800854cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18008552a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18008552a`

## string_xrefs

- `0x1800854bd`: `An Error occurred processing the completion of Task '{0}' due to {1}.`

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
0x18008548c  mov     [rsp+arg_8], rdx
0x180085491  push    rbx
0x180085492  push    rbp
0x180085493  sub     rsp, 48h
0x180085497  mov     rbp, rdx
0x18008549a  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18008549f  lea     rbx, [rax+28h]
0x1800854a3  mov     rax, [rbp+40h]
0x1800854a7  mov     rcx, [rax+20h]
0x1800854ab  mov     rax, [rcx]
0x1800854ae  mov     rax, [rax]
0x1800854b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854b6  mov     r9, [rbp+58h]
0x1800854ba  mov     r8, rax
0x1800854bd  lea     rdx, aAnErrorOccurre; "An Error occurred processing the comple"...
0x1800854c4  mov     rcx, rbx; struct cxl::TextWriter *
0x1800854c7  call    ??$WriteLine@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VException@cxl@@@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVException@1@@Z; cxl::TextWriter::WriteLine<char,std::wstring,cxl::Exception>(char const *,std::wstring const &,cxl::Exception const &)
0x1800854cc  call    cs:__imp_GetLastError
0x1800854d2  mov     [rbp+60h], eax
0x1800854d5  lea     rcx, [rbp+80h]
0x1800854dc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800854e1  nop
0x1800854e2  lea     rdx, [rbp+80h]
0x1800854e9  lea     rcx, [rbp+0A0h]
0x1800854f0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800854f5  nop
0x1800854f6  mov     dword ptr [rbp+40h], 176h
0x1800854fd  lea     rax, [rbp+60h]
0x180085501  mov     [rsp+58h+var_28], rax; __int64
0x180085506  lea     rax, [rbp+40h]
0x18008550a  mov     [rsp+58h+var_38], rax; __int64
0x18008550f  lea     rcx, [rbp+0A0h]; struct cxl::TextWriter *
0x180085516  call    ??$WriteLine@D$$BY05D$$BY0DP@DH$$BY0DB@DK@TextWriter@cxl@@QEAAXPEBDAEAY05$$CBDAEAY0DP@$$CBDAEBHAEAY0DB@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [6],char [63],int,char [49],ulong>(char const *,char const (&)[6],char const (&)[63],int const &,char const (&)[49],ulong const &)
0x18008551b  lea     rcx, [rbp+80h]
0x180085522  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180085527  mov     rcx, rax; lpOutputString
0x18008552a  call    cs:__imp_OutputDebugStringW
0x180085530  mov     ecx, [rbp+60h]; unsigned int
0x180085533  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x180085538  nop
0x180085539  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x180085540  mov     [rbp+0A0h], rax
0x180085547  lea     rcx, [rbp+80h]
0x18008554e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085553  nop
0x180085554  mov     rax, 0
0x18008555e  add     rsp, 48h
0x180085562  pop     rbp
0x180085563  pop     rbx
0x180085564  retn
```
