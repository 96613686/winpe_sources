# cxl::ExceptionManager::ReportException(cxl::Exception const &)

- ea: `0x18000d230`
- end: `0x18000d2ef`
- name: `?ReportException@ExceptionManager@cxl@@SAXAEBVException@2@@Z`
- size: `191`
- prototype: `void __fastcall(const struct cxl::Exception *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800874c3`

## callees

- `0x180002ae0`
- `0x18000bff4`
- `0x18000c858`
- `0x18000cc78`
- `0x18000cdc4`
- `0x18000d070`
- `0x18000d6dc`
- `0x18000d7c8`
- `0x18000e044`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d25b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d25b`

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
0x18000d230  mov     [rsp+arg_8], rbx
0x18000d235  push    rdi
0x18000d236  sub     rsp, 190h
0x18000d23d  mov     rax, cs:__security_cookie
0x18000d244  xor     rax, rsp
0x18000d247  mov     [rsp+198h+var_18], rax
0x18000d24f  mov     rdi, rcx
0x18000d252  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18000d257  lea     rbx, [rax+28h]
0x18000d25b  call    cs:__imp_GetCurrentThreadId
0x18000d261  mov     [rsp+198h+var_178], eax
0x18000d265  mov     r9, rdi
0x18000d268  lea     r8, [rsp+198h+var_178]
0x18000d26d  mov     rcx, rbx
0x18000d270  call    ??$WriteLine@DKVException@cxl@@@TextWriter@cxl@@QEAAXPEBDAEBKAEBVException@1@@Z; cxl::TextWriter::WriteLine<char,ulong,cxl::Exception>(char const *,ulong const &,cxl::Exception const &)
0x18000d275  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18000d27a  call    ?WriteCurrentException@ExceptionManager@cxl@@SAXAEAVTextWriter@2@AEBUFormat@2@@Z; cxl::ExceptionManager::WriteCurrentException(cxl::TextWriter &,cxl::Format const &)
0x18000d27f  mov     rdx, cs:?instance@ExceptionManager@cxl@@0PEAV12@EA; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000d286  add     rdx, 50h ; 'P'
0x18000d28a  lea     rcx, [rsp+198h+var_170]
0x18000d28f  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x18000d294  nop
0x18000d295  mov     rbx, cs:?instance@ExceptionManager@cxl@@0PEAV12@EA; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000d29c  mov     rdx, rdi; struct cxl::Exception *
0x18000d29f  lea     rcx, [rsp+198h+var_158]; this
0x18000d2a4  call    ??0ReportedExceptionRecord@ExceptionManager@cxl@@QEAA@AEBVException@2@@Z; cxl::ExceptionManager::ReportedExceptionRecord::ReportedExceptionRecord(cxl::Exception const &)
0x18000d2a9  nop
0x18000d2aa  lea     rdx, [rsp+198h+var_158]
0x18000d2af  lea     rcx, [rbx+38h]
0x18000d2b3  call    ?push_back@?$vector@UReportedExceptionRecord@ExceptionManager@cxl@@V?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@std@@@std@@QEAAX$$QEAUReportedExceptionRecord@ExceptionManager@cxl@@@Z; std::vector<cxl::ExceptionManager::ReportedExceptionRecord>::push_back(cxl::ExceptionManager::ReportedExceptionRecord &&)
0x18000d2b8  nop
0x18000d2b9  lea     rcx, [rsp+198h+var_158]
0x18000d2be  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000d2c3  nop
0x18000d2c4  lea     rcx, [rsp+198h+var_170]
0x18000d2c9  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x18000d2ce  mov     rcx, [rsp+198h+var_18]
0x18000d2d6  xor     rcx, rsp; StackCookie
0x18000d2d9  call    __security_check_cookie
0x18000d2de  mov     rbx, [rsp+198h+arg_8]
0x18000d2e6  add     rsp, 190h
0x18000d2ed  pop     rdi
0x18000d2ee  retn
```
