# cxl::ExceptionManager::~ExceptionManager(void)

- ea: `0x18000d694`
- end: `0x18000d73e`
- name: `??1ExceptionManager@cxl@@QEAA@XZ`
- size: `170`
- prototype: `void __fastcall(cxl::ExceptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c1ac`

## callees

- `0x180005d94`
- `0x18000cdd4`
- `0x18000d5d4`
- `0x18000d694`
- `0x18000d874`

## import_xrefs

- `ntdll!RtlRemoveVectoredExceptionHandler` at `0x18000d6cf`
- `ntdll!RtlRemoveVectoredExceptionHandler` at `0x18000d6cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000d6ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000d6ae`

## pseudocode

```c
void __fastcall cxl::ExceptionManager::~ExceptionManager(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 v2; // r8
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
      this[1].LockSemaphore,
      v2);
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
0x18000d694  push    rbx
0x18000d696  sub     rsp, 20h
0x18000d69a  mov     rbx, rcx
0x18000d69d  mov     cs:?instance@ExceptionManager@cxl@@0PEAV12@EA, 0; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000d6a8  mov     ecx, cs:?tlsIndex@?$ThreadLocal@UExceptionContext@ExceptionManager@cxl@@@cxl@@0HA; dwTlsIndex
0x18000d6ae  call    cs:__imp_TlsFree
0x18000d6b4  mov     cs:?tlsIndex@?$ThreadLocal@UExceptionContext@ExceptionManager@cxl@@@cxl@@0HA, 0FFFFFFFFh; int cxl::ThreadLocal<cxl::ExceptionManager::ExceptionContext>::tlsIndex
0x18000d6be  lea     rcx, [rbx+20h]
0x18000d6c2  call    ?DestroyAll@?$nt_list@UExceptionContext@ExceptionManager@cxl@@@cxl@@QEAAXXZ; cxl::nt_list<cxl::ExceptionManager::ExceptionContext>::DestroyAll(void)
0x18000d6c7  mov     rcx, [rbx]; VectoredHandlerHandle
0x18000d6ca  test    rcx, rcx
0x18000d6cd  jz      short loc_18000D6DC
0x18000d6cf  call    cs:__imp_RtlRemoveVectoredExceptionHandler
0x18000d6d5  mov     qword ptr [rbx], 0
0x18000d6dc  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000d6e0  call    ??1?$OrderedLock@$0MJ@@cxl@@QEAA@XZ; cxl::OrderedLock<201>::~OrderedLock<201>(void)
0x18000d6e5  mov     rcx, [rbx+38h]
0x18000d6e9  test    rcx, rcx
0x18000d6ec  jz      short loc_18000D738
0x18000d6ee  mov     rdx, [rbx+40h]
0x18000d6f2  call    ??$_Destroy_range@V?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@std@@@std@@YAXPEAUReportedExceptionRecord@ExceptionManager@cxl@@QEAU123@AEAV?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@0@@Z; std::_Destroy_range<std::allocator<cxl::ExceptionManager::ReportedExceptionRecord>>(cxl::ExceptionManager::ReportedExceptionRecord *,cxl::ExceptionManager::ReportedExceptionRecord * const,std::allocator<cxl::ExceptionManager::ReportedExceptionRecord> &)
0x18000d6f7  mov     rcx, [rbx+38h]
0x18000d6fb  mov     rax, [rbx+48h]
0x18000d6ff  sub     rax, rcx
0x18000d702  sar     rax, 3
0x18000d706  mov     rdx, 6F96F96F96F96F97h
0x18000d710  imul    rax, rdx
0x18000d714  imul    rdx, rax, 138h
0x18000d71b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d720  mov     qword ptr [rbx+38h], 0
0x18000d728  mov     qword ptr [rbx+40h], 0
0x18000d730  mov     qword ptr [rbx+48h], 0
0x18000d738  add     rsp, 20h
0x18000d73c  pop     rbx
0x18000d73d  retn
```
