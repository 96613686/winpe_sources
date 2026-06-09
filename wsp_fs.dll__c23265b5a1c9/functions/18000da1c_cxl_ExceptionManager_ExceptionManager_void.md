# cxl::ExceptionManager::~ExceptionManager(void)

- ea: `0x18000da1c`
- end: `0x18000dad3`
- name: `??1ExceptionManager@cxl@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(cxl::ExceptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c4f0`

## callees

- `0x180005e64`
- `0x18000d12c`
- `0x18000d958`
- `0x18000da1c`
- `0x18000dc14`

## import_xrefs

- `ntdll!RtlRemoveVectoredExceptionHandler` at `0x18000da5d`
- `ntdll!RtlRemoveVectoredExceptionHandler` at `0x18000da5d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000da36`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000da36`

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
0x18000da1c  push    rbx
0x18000da1e  sub     rsp, 20h
0x18000da22  mov     rbx, rcx
0x18000da25  mov     cs:?instance@ExceptionManager@cxl@@0PEAV12@EA, 0; cxl::ExceptionManager * cxl::ExceptionManager::instance
0x18000da30  mov     ecx, cs:?tlsIndex@?$ThreadLocal@UExceptionContext@ExceptionManager@cxl@@@cxl@@0HA; dwTlsIndex
0x18000da36  call    cs:__imp_TlsFree
0x18000da3d  nop     dword ptr [rax+rax+00h]
0x18000da42  mov     cs:?tlsIndex@?$ThreadLocal@UExceptionContext@ExceptionManager@cxl@@@cxl@@0HA, 0FFFFFFFFh; int cxl::ThreadLocal<cxl::ExceptionManager::ExceptionContext>::tlsIndex
0x18000da4c  lea     rcx, [rbx+20h]
0x18000da50  call    ?DestroyAll@?$nt_list@UExceptionContext@ExceptionManager@cxl@@@cxl@@QEAAXXZ; cxl::nt_list<cxl::ExceptionManager::ExceptionContext>::DestroyAll(void)
0x18000da55  mov     rcx, [rbx]; VectoredHandlerHandle
0x18000da58  test    rcx, rcx
0x18000da5b  jz      short loc_18000DA70
0x18000da5d  call    cs:__imp_RtlRemoveVectoredExceptionHandler
0x18000da64  nop     dword ptr [rax+rax+00h]
0x18000da69  mov     qword ptr [rbx], 0
0x18000da70  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000da74  call    ??1?$OrderedLock@$0MJ@@cxl@@QEAA@XZ; cxl::OrderedLock<201>::~OrderedLock<201>(void)
0x18000da79  mov     rcx, [rbx+38h]
0x18000da7d  test    rcx, rcx
0x18000da80  jz      short loc_18000DACC
0x18000da82  mov     rdx, [rbx+40h]
0x18000da86  call    ??$_Destroy_range@V?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@std@@@std@@YAXPEAUReportedExceptionRecord@ExceptionManager@cxl@@QEAU123@AEAV?$allocator@UReportedExceptionRecord@ExceptionManager@cxl@@@0@@Z; std::_Destroy_range<std::allocator<cxl::ExceptionManager::ReportedExceptionRecord>>(cxl::ExceptionManager::ReportedExceptionRecord *,cxl::ExceptionManager::ReportedExceptionRecord * const,std::allocator<cxl::ExceptionManager::ReportedExceptionRecord> &)
0x18000da8b  mov     rcx, [rbx+38h]
0x18000da8f  mov     rax, [rbx+48h]
0x18000da93  sub     rax, rcx
0x18000da96  sar     rax, 3
0x18000da9a  mov     rdx, 6F96F96F96F96F97h
0x18000daa4  imul    rax, rdx
0x18000daa8  imul    rdx, rax, 138h
0x18000daaf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000dab4  mov     qword ptr [rbx+38h], 0
0x18000dabc  mov     qword ptr [rbx+40h], 0
0x18000dac4  mov     qword ptr [rbx+48h], 0
0x18000dacc  add     rsp, 20h
0x18000dad0  pop     rbx
0x18000dad1  retn
```
