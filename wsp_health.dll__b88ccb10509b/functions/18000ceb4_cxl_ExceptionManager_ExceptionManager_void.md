# cxl::ExceptionManager::~ExceptionManager(void)

- ea: `0x18000ceb4`
- end: `0x18000cf5e`
- name: `??1ExceptionManager@cxl@@QEAA@XZ`
- size: `170`
- prototype: `void __fastcall(cxl::ExceptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b844`

## callees

- `0x18000c4c4`
- `0x18000c504`
- `0x18000cde8`
- `0x18000ceb4`
- `0x18000d094`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000cece`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000cece`
- `ntdll!RtlRemoveVectoredExceptionHandler` at `0x18000ceef`
- `ntdll!RtlRemoveVectoredExceptionHandler` at `0x18000ceef`

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
0x18000ceb4  push    rbx
0x18000ceb6  sub     rsp, 20h
0x18000ceba  mov     rbx, rcx
0x18000cebd  mov     cs:?instance@ExceptionManager@cxl@@0PEAV12@EA, 0; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000cec8  mov     ecx, cs:?tlsIndex@?$ThreadLocal@UExceptionContext@ExceptionManager@cxl@@@cxl@@0HA; dwTlsIndex
0x18000cece  call    cs:__imp_TlsFree
0x18000ced4  mov     cs:?tlsIndex@?$ThreadLocal@UExceptionContext@ExceptionManager@cxl@@@cxl@@0HA, 0FFFFFFFFh; int cxl::ThreadLocal<cxl::ExceptionManager::ExceptionContext>::tlsIndex
0x18000cede  lea     rcx, [rbx+20h]
0x18000cee2  call    ?DestroyAll@?$nt_list@UExceptionContext@ExceptionManager@cxl@@@cxl@@QEAAXXZ; cxl::nt_list<cxl::ExceptionManager::ExceptionContext>::DestroyAll(void)
0x18000cee7  mov     rcx, [rbx]; VectoredHandlerHandle
0x18000ceea  test    rcx, rcx
0x18000ceed  jz      short loc_18000CEFC
0x18000ceef  call    cs:__imp_RtlRemoveVectoredExceptionHandler
0x18000cef5  mov     qword ptr [rbx], 0
0x18000cefc  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000cf00  call    ??1?$OrderedLock@$0MJ@@cxl@@QEAA@XZ; cxl::OrderedLock<201>::~OrderedLock<201>(void)
0x18000cf05  mov     rcx, [rbx+38h]
0x18000cf09  test    rcx, rcx
0x18000cf0c  jz      short loc_18000CF58
0x18000cf0e  mov     rdx, [rbx+40h]
0x18000cf12  call    ??$_Destroy_range@V?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@std@@@std@@YAXPEAUReportedExceptionRecord@ExceptionManager@cxl@@QEAU123@AEAV?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@0@@Z; std::_Destroy_range<std::allocator<cxl::ExceptionManager::ReportedExceptionRecord>>(cxl::ExceptionManager::ReportedExceptionRecord *,cxl::ExceptionManager::ReportedExceptionRecord * const,std::allocator<cxl::ExceptionManager::ReportedExceptionRecord> &)
0x18000cf17  mov     rcx, [rbx+38h]
0x18000cf1b  mov     rax, [rbx+48h]
0x18000cf1f  sub     rax, rcx
0x18000cf22  sar     rax, 3
0x18000cf26  mov     rdx, 6F96F96F96F96F97h
0x18000cf30  imul    rax, rdx
0x18000cf34  imul    rdx, rax, 138h
0x18000cf3b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000cf40  mov     qword ptr [rbx+38h], 0
0x18000cf48  mov     qword ptr [rbx+40h], 0
0x18000cf50  mov     qword ptr [rbx+48h], 0
0x18000cf58  add     rsp, 20h
0x18000cf5c  pop     rbx
0x18000cf5d  retn
```
