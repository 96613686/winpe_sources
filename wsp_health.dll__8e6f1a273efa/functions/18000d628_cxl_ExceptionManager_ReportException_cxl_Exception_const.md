# cxl::ExceptionManager::ReportException(cxl::Exception const &)

- ea: `0x18000d628`
- end: `0x18000d6ee`
- name: `?ReportException@ExceptionManager@cxl@@SAXAEBVException@2@@Z`
- size: `198`
- prototype: `void __fastcall(const struct cxl::Exception *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18008998f`

## callees

- `0x180002b50`
- `0x18000c388`
- `0x18000cbfc`
- `0x18000d034`
- `0x18000d184`
- `0x18000d450`
- `0x18000daf8`
- `0x18000dbf8`
- `0x18000e4b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d653`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d653`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::ExceptionManager::ReportException(const struct cxl::Exception *a1)
{
  struct cxl::TextWriter *v2; // rbx
  const struct cxl::Format *v3; // rdx
  struct cxl::TextWriter *v4; // rcx
  struct cxl::ExceptionManager *v5; // rbx
  _BYTE v6[24]; // [rsp+28h] [rbp-170h] BYREF
  _BYTE v7[320]; // [rsp+40h] [rbp-158h] BYREF

  v2 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
  GetCurrentThreadId();
  cxl::TextWriter::WriteLine<char,unsigned long,cxl::Exception>(v2);
  cxl::TraceManager::Instance();
  cxl::ExceptionManager::WriteCurrentException(v4, v3);
  cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(
    v6,
    (char *)cxl::ExceptionManager::instance + 80);
  v5 = cxl::ExceptionManager::instance;
  cxl::ExceptionManager::ReportedExceptionRecord::ReportedExceptionRecord(
    (cxl::ExceptionManager::ReportedExceptionRecord *)v7,
    a1);
  std::vector<cxl::ExceptionManager::ReportedExceptionRecord>::push_back((char *)v5 + 56, v7);
  std::wstring::_Tidy_deallocate(v7);
  cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(v6);
}

```

## disassembly

```asm
0x18000d628  mov     [rsp+arg_8], rbx
0x18000d62d  push    rdi
0x18000d62e  sub     rsp, 190h
0x18000d635  mov     rax, cs:__security_cookie
0x18000d63c  xor     rax, rsp
0x18000d63f  mov     [rsp+198h+var_18], rax
0x18000d647  mov     rdi, rcx
0x18000d64a  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18000d64f  lea     rbx, [rax+28h]
0x18000d653  call    cs:__imp_GetCurrentThreadId
0x18000d65a  nop     dword ptr [rax+rax+00h]
0x18000d65f  mov     [rsp+198h+var_178], eax
0x18000d663  mov     r9, rdi
0x18000d666  lea     r8, [rsp+198h+var_178]
0x18000d66b  mov     rcx, rbx
0x18000d66e  call    ??$WriteLine@DKVException@cxl@@@TextWriter@cxl@@QEAAXPEBDAEBKAEBVException@1@@Z; cxl::TextWriter::WriteLine<char,ulong,cxl::Exception>(char const *,ulong const &,cxl::Exception const &)
0x18000d673  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18000d678  call    ?WriteCurrentException@ExceptionManager@cxl@@SAXAEAVTextWriter@2@AEBUFormat@2@@Z; cxl::ExceptionManager::WriteCurrentException(cxl::TextWriter &,cxl::Format const &)
0x18000d67d  mov     rdx, cs:?instance@ExceptionManager@cxl@@0PEAV12@EA; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000d684  add     rdx, 50h ; 'P'
0x18000d688  lea     rcx, [rsp+198h+var_170]
0x18000d68d  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x18000d692  nop
0x18000d693  mov     rbx, cs:?instance@ExceptionManager@cxl@@0PEAV12@EA; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000d69a  mov     rdx, rdi; struct cxl::Exception *
0x18000d69d  lea     rcx, [rsp+198h+var_158]; this
0x18000d6a2  call    ??0ReportedExceptionRecord@ExceptionManager@cxl@@QEAA@AEBVException@2@@Z; cxl::ExceptionManager::ReportedExceptionRecord::ReportedExceptionRecord(cxl::Exception const &)
0x18000d6a7  nop
0x18000d6a8  lea     rdx, [rsp+198h+var_158]
0x18000d6ad  lea     rcx, [rbx+38h]
0x18000d6b1  call    ?push_back@?$vector@UReportedExceptionRecord@ExceptionManager@cxl@@V?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@std@@@std@@QEAAX$$QEAUReportedExceptionRecord@ExceptionManager@cxl@@@Z; std::vector<cxl::ExceptionManager::ReportedExceptionRecord>::push_back(cxl::ExceptionManager::ReportedExceptionRecord &&)
0x18000d6b6  nop
0x18000d6b7  lea     rcx, [rsp+198h+var_158]
0x18000d6bc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000d6c1  nop
0x18000d6c2  lea     rcx, [rsp+198h+var_170]
0x18000d6c7  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x18000d6cc  mov     rcx, [rsp+198h+var_18]
0x18000d6d4  xor     rcx, rsp; StackCookie
0x18000d6d7  call    __security_check_cookie
0x18000d6dc  mov     rbx, [rsp+198h+arg_8]
0x18000d6e4  add     rsp, 190h
0x18000d6eb  pop     rdi
0x18000d6ec  retn
```
