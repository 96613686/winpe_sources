# cxl::ExceptionManager::ReportException(cxl::Exception const &)

- ea: `0x18000ddc8`
- end: `0x18000de8e`
- name: `?ReportException@ExceptionManager@cxl@@SAXAEBVException@2@@Z`
- size: `198`
- prototype: `void __fastcall(const struct cxl::Exception *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a6f5a`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000cdb4`
- `0x18000d460`
- `0x18000d854`
- `0x18000d92c`
- `0x18000dbf0`
- `0x18000e258`
- `0x18000eb18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ddf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ddf3`

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
  cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(v6);
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
0x18000ddc8  mov     [rsp+arg_8], rbx
0x18000ddcd  push    rdi
0x18000ddce  sub     rsp, 190h
0x18000ddd5  mov     rax, cs:__security_cookie
0x18000dddc  xor     rax, rsp
0x18000dddf  mov     [rsp+198h+var_18], rax
0x18000dde7  mov     rdi, rcx
0x18000ddea  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18000ddef  lea     rbx, [rax+28h]
0x18000ddf3  call    cs:__imp_GetCurrentThreadId
0x18000ddfa  nop     dword ptr [rax+rax+00h]
0x18000ddff  mov     [rsp+198h+var_178], eax
0x18000de03  mov     r9, rdi
0x18000de06  lea     r8, [rsp+198h+var_178]
0x18000de0b  mov     rcx, rbx
0x18000de0e  call    ??$WriteLine@DKVException@cxl@@@TextWriter@cxl@@QEAAXPEBDAEBKAEBVException@1@@Z; cxl::TextWriter::WriteLine<char,ulong,cxl::Exception>(char const *,ulong const &,cxl::Exception const &)
0x18000de13  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18000de18  call    ?WriteCurrentException@ExceptionManager@cxl@@SAXAEAVTextWriter@2@AEBUFormat@2@@Z; cxl::ExceptionManager::WriteCurrentException(cxl::TextWriter &,cxl::Format const &)
0x18000de1d  mov     rdx, cs:?instance@ExceptionManager@cxl@@0PEAV12@EA; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000de24  add     rdx, 50h ; 'P'
0x18000de28  lea     rcx, [rsp+198h+var_170]
0x18000de2d  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x18000de32  nop
0x18000de33  mov     rbx, cs:?instance@ExceptionManager@cxl@@0PEAV12@EA; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000de3a  mov     rdx, rdi; struct cxl::Exception *
0x18000de3d  lea     rcx, [rsp+198h+var_158]; this
0x18000de42  call    ??0ReportedExceptionRecord@ExceptionManager@cxl@@QEAA@AEBVException@2@@Z; cxl::ExceptionManager::ReportedExceptionRecord::ReportedExceptionRecord(cxl::Exception const &)
0x18000de47  nop
0x18000de48  lea     rdx, [rsp+198h+var_158]
0x18000de4d  lea     rcx, [rbx+38h]
0x18000de51  call    ?push_back@?$vector@UReportedExceptionRecord@ExceptionManager@cxl@@V?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@std@@@std@@QEAAX$$QEAUReportedExceptionRecord@ExceptionManager@cxl@@@Z; std::vector<cxl::ExceptionManager::ReportedExceptionRecord>::push_back(cxl::ExceptionManager::ReportedExceptionRecord &&)
0x18000de56  nop
0x18000de57  lea     rcx, [rsp+198h+var_158]
0x18000de5c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000de61  nop
0x18000de62  lea     rcx, [rsp+198h+var_170]
0x18000de67  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x18000de6c  mov     rcx, [rsp+198h+var_18]
0x18000de74  xor     rcx, rsp; StackCookie
0x18000de77  call    __security_check_cookie
0x18000de7c  mov     rbx, [rsp+198h+arg_8]
0x18000de84  add     rsp, 190h
0x18000de8b  pop     rdi
0x18000de8c  retn
```
