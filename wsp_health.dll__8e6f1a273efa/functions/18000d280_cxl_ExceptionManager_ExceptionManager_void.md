# cxl::ExceptionManager::~ExceptionManager(void)

- ea: `0x18000d280`
- end: `0x18000d337`
- name: `??1ExceptionManager@cxl@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(cxl::ExceptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000bbc8`

## callees

- `0x18000c85c`
- `0x18000c89c`
- `0x18000d1b0`
- `0x18000d280`
- `0x18000d474`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000d29a`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000d29a`
- `ntdll!RtlRemoveVectoredExceptionHandler` at `0x18000d2c1`
- `ntdll!RtlRemoveVectoredExceptionHandler` at `0x18000d2c1`

## pseudocode

```c
void __fastcall cxl::ExceptionManager::~ExceptionManager(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rcx

  cxl::ExceptionManager::instance = 0;
  TlsFree(cxl::ThreadLocal<cxl::ExceptionManager::ExceptionContext>::tlsIndex);
  cxl::ThreadLocal<cxl::ExceptionManager::ExceptionContext>::tlsIndex = -1;
  cxl::nt_list<cxl::ExceptionManager::ExceptionContext>::DestroyAll(&this->SpinCount);
  if ( this->DebugInfo )
  {
    RtlRemoveVectoredExceptionHandler(this->DebugInfo);
    this->DebugInfo = 0;
  }
  cxl::OrderedLock<201>::~OrderedLock<201>(this + 2);
  OwningThread = this[1].OwningThread;
  if ( OwningThread )
  {
    std::_Destroy_range<std::allocator<cxl::ExceptionManager::ReportedExceptionRecord>>(
      OwningThread,
      this[1].LockSemaphore);
    std::_Deallocate<16>(
      this[1].OwningThread,
      8 * ((__int64)(this[1].SpinCount - (unsigned __int64)this[1].OwningThread) >> 3));
    this[1].OwningThread = 0;
    this[1].LockSemaphore = 0;
    this[1].SpinCount = 0;
  }
}

```

## disassembly

```asm
0x18000d280  push    rbx
0x18000d282  sub     rsp, 20h
0x18000d286  mov     rbx, rcx
0x18000d289  mov     cs:?instance@ExceptionManager@cxl@@0PEAV12@EA, 0; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000d294  mov     ecx, cs:?tlsIndex@?$ThreadLocal@UExceptionContext@ExceptionManager@cxl@@@cxl@@0HA; dwTlsIndex
0x18000d29a  call    cs:__imp_TlsFree
0x18000d2a1  nop     dword ptr [rax+rax+00h]
0x18000d2a6  mov     cs:?tlsIndex@?$ThreadLocal@UExceptionContext@ExceptionManager@cxl@@@cxl@@0HA, 0FFFFFFFFh; int cxl::ThreadLocal<cxl::ExceptionManager::ExceptionContext>::tlsIndex
0x18000d2b0  lea     rcx, [rbx+20h]
0x18000d2b4  call    ?DestroyAll@?$nt_list@UExceptionContext@ExceptionManager@cxl@@@cxl@@QEAAXXZ; cxl::nt_list<cxl::ExceptionManager::ExceptionContext>::DestroyAll(void)
0x18000d2b9  mov     rcx, [rbx]; VectoredHandlerHandle
0x18000d2bc  test    rcx, rcx
0x18000d2bf  jz      short loc_18000D2D4
0x18000d2c1  call    cs:__imp_RtlRemoveVectoredExceptionHandler
0x18000d2c8  nop     dword ptr [rax+rax+00h]
0x18000d2cd  mov     qword ptr [rbx], 0
0x18000d2d4  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000d2d8  call    ??1?$OrderedLock@$0MJ@@cxl@@QEAA@XZ; cxl::OrderedLock<201>::~OrderedLock<201>(void)
0x18000d2dd  mov     rcx, [rbx+38h]
0x18000d2e1  test    rcx, rcx
0x18000d2e4  jz      short loc_18000D330
0x18000d2e6  mov     rdx, [rbx+40h]
0x18000d2ea  call    ??$_Destroy_range@V?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@std@@@std@@YAXPEAUReportedExceptionRecord@ExceptionManager@cxl@@QEAU123@AEAV?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@0@@Z; std::_Destroy_range<std::allocator<cxl::ExceptionManager::ReportedExceptionRecord>>(cxl::ExceptionManager::ReportedExceptionRecord *,cxl::ExceptionManager::ReportedExceptionRecord * const,std::allocator<cxl::ExceptionManager::ReportedExceptionRecord> &)
0x18000d2ef  mov     rcx, [rbx+38h]
0x18000d2f3  mov     rax, [rbx+48h]
0x18000d2f7  sub     rax, rcx
0x18000d2fa  sar     rax, 3
0x18000d2fe  mov     rdx, 6F96F96F96F96F97h
0x18000d308  imul    rax, rdx
0x18000d30c  imul    rdx, rax, 138h
0x18000d313  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d318  mov     qword ptr [rbx+38h], 0
0x18000d320  mov     qword ptr [rbx+40h], 0
0x18000d328  mov     qword ptr [rbx+48h], 0
0x18000d330  add     rsp, 20h
0x18000d334  pop     rbx
0x18000d335  retn
```
