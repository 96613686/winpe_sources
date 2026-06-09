# cxl::ExceptionManager::ReportException(cxl::Exception const &)

- ea: `0x18000da10`
- end: `0x18000dacf`
- name: `?ReportException@ExceptionManager@cxl@@SAXAEBVException@2@@Z`
- size: `191`
- prototype: `void __fastcall(const struct cxl::Exception *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a4ce0`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000ca68`
- `0x18000d100`
- `0x18000d4dc`
- `0x18000d5b0`
- `0x18000d850`
- `0x18000de78`
- `0x18000e6f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da3b`

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
0x18000da10  mov     [rsp+arg_8], rbx
0x18000da15  push    rdi
0x18000da16  sub     rsp, 190h
0x18000da1d  mov     rax, cs:__security_cookie
0x18000da24  xor     rax, rsp
0x18000da27  mov     [rsp+198h+var_18], rax
0x18000da2f  mov     rdi, rcx
0x18000da32  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18000da37  lea     rbx, [rax+28h]
0x18000da3b  call    cs:__imp_GetCurrentThreadId
0x18000da41  mov     [rsp+198h+var_178], eax
0x18000da45  mov     r9, rdi
0x18000da48  lea     r8, [rsp+198h+var_178]
0x18000da4d  mov     rcx, rbx
0x18000da50  call    ??$WriteLine@DKVException@cxl@@@TextWriter@cxl@@QEAAXPEBDAEBKAEBVException@1@@Z; cxl::TextWriter::WriteLine<char,ulong,cxl::Exception>(char const *,ulong const &,cxl::Exception const &)
0x18000da55  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18000da5a  call    ?WriteCurrentException@ExceptionManager@cxl@@SAXAEAVTextWriter@2@AEBUFormat@2@@Z; cxl::ExceptionManager::WriteCurrentException(cxl::TextWriter &,cxl::Format const &)
0x18000da5f  mov     rdx, cs:?instance@ExceptionManager@cxl@@0PEAV12@EA; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000da66  add     rdx, 50h ; 'P'
0x18000da6a  lea     rcx, [rsp+198h+var_170]
0x18000da6f  call    ??0?$AcquireExclusive@VCriticalSection@cxl@@@cxl@@QEAA@AEAVCriticalSection@1@@Z; cxl::AcquireExclusive<cxl::CriticalSection>::AcquireExclusive<cxl::CriticalSection>(cxl::CriticalSection &)
0x18000da74  nop
0x18000da75  mov     rbx, cs:?instance@ExceptionManager@cxl@@0PEAV12@EA; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000da7c  mov     rdx, rdi; struct cxl::Exception *
0x18000da7f  lea     rcx, [rsp+198h+var_158]; this
0x18000da84  call    ??0ReportedExceptionRecord@ExceptionManager@cxl@@QEAA@AEBVException@2@@Z; cxl::ExceptionManager::ReportedExceptionRecord::ReportedExceptionRecord(cxl::Exception const &)
0x18000da89  nop
0x18000da8a  lea     rdx, [rsp+198h+var_158]
0x18000da8f  lea     rcx, [rbx+38h]
0x18000da93  call    ?push_back@?$vector@UReportedExceptionRecord@ExceptionManager@cxl@@V?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@std@@@std@@QEAAX$$QEAUReportedExceptionRecord@ExceptionManager@cxl@@@Z; std::vector<cxl::ExceptionManager::ReportedExceptionRecord>::push_back(cxl::ExceptionManager::ReportedExceptionRecord &&)
0x18000da98  nop
0x18000da99  lea     rcx, [rsp+198h+var_158]
0x18000da9e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000daa3  nop
0x18000daa4  lea     rcx, [rsp+198h+var_170]
0x18000daa9  call    ??1?$AcquireExclusive@$$CBVCriticalSection@cxl@@@cxl@@QEAA@XZ; cxl::AcquireExclusive<cxl::CriticalSection const>::~AcquireExclusive<cxl::CriticalSection const>(void)
0x18000daae  mov     rcx, [rsp+198h+var_18]
0x18000dab6  xor     rcx, rsp; StackCookie
0x18000dab9  call    __security_check_cookie
0x18000dabe  mov     rbx, [rsp+198h+arg_8]
0x18000dac6  add     rsp, 190h
0x18000dacd  pop     rdi
0x18000dace  retn
```
