# WFDSConMgr::CWorkQueue<WFDSConMgr::ISessionWork>::~CWorkQueue<WFDSConMgr::ISessionWork>(void)

- ea: `0x18003cd24`
- end: `0x18003cdc8`
- name: `??1?$CWorkQueue@VISessionWork@WFDSConMgr@@@WFDSConMgr@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, const void *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18003cf80`
- `0x18003d000`
- `0x180068344`

## callees

- `0x1800069d0`
- `0x18002fae8`
- `0x1800308fc`
- `0x18003cd24`
- `0x18005cd7c`
- `0x18005cedc`
- `0x18005d27c`
- `0x18005dca0`
- `0x18005f1c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003cdb0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003cdb0`

## pseudocode

```c
void __fastcall WFDSConMgr::CWorkQueue<WFDSConMgr::ISessionWork>::~CWorkQueue<WFDSConMgr::ISessionWork>(
        struct _RTL_CRITICAL_SECTION *this,
        const void *a2)
{
  bool v3; // dl
  __int64 v4; // r8
  __int64 v5; // r9
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&WFDSConMgr::CWorkQueue<WFDSConMgr::ISessionWork>::`vftable';
  WFDSConMgr::WorkQueueTrace::TraceCleanupAndWait((WFDSConMgr::WorkQueueTrace *)this, a2);
  WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers((WFDSConMgr::CThreadpoolEnvironment *)&this[3].SpinCount, v3);
  WFDSConMgr::CEventWrapper::~CEventWrapper((WFDSConMgr::CEventWrapper *)&this[6].SpinCount);
  WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment((WFDSConMgr::CThreadpoolEnvironment *)&this[3].SpinCount);
  DebugInfo = this[3].DebugInfo;
  if ( DebugInfo )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<WFDSConMgr::IWorkQueueJob>>>(
      DebugInfo,
      *(_QWORD *)&this[3].LockCount,
      v4,
      v5);
    std::_Deallocate<16>(
      &this[3].DebugInfo->Type,
      ((PRTL_CRITICAL_SECTION_DEBUG)this[3].OwningThread - this[3].DebugInfo) & 0xFFFFFFFFFFFFFFF0uLL);
    this[3].DebugInfo = 0;
    *(_QWORD *)&this[3].LockCount = 0;
    this[3].OwningThread = 0;
  }
  std::deque<std::unique_ptr<WFDSConMgr::ISessionWork>>::~deque<std::unique_ptr<WFDSConMgr::ISessionWork>>(&this[2]);
  DeleteCriticalSection(this + 1);
  WFDSConMgr::WorkItem::~WorkItem((WFDSConMgr::WorkItem *)this);
}

```

## disassembly

```asm
0x18003cd24  mov     [rsp+arg_0], rbx
0x18003cd29  push    rdi
0x18003cd2a  sub     rsp, 20h
0x18003cd2e  lea     rax, ??_7?$CWorkQueue@VISessionWork@WFDSConMgr@@@WFDSConMgr@@6B@; const WFDSConMgr::CWorkQueue<WFDSConMgr::ISessionWork>::`vftable'
0x18003cd35  mov     rdi, rcx
0x18003cd38  mov     [rcx], rax
0x18003cd3b  call    ?TraceCleanupAndWait@WorkQueueTrace@WFDSConMgr@@YAXPEBX@Z; WFDSConMgr::WorkQueueTrace::TraceCleanupAndWait(void const *)
0x18003cd40  lea     rbx, [rdi+98h]
0x18003cd47  mov     rcx, rbx; this
0x18003cd4a  call    ?CleanupGroupMembers@CThreadpoolEnvironment@WFDSConMgr@@QEAAX_N@Z; WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18003cd4f  lea     rcx, [rdi+110h]; this
0x18003cd56  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x18003cd5b  mov     rcx, rbx; this
0x18003cd5e  call    ??1CThreadpoolEnvironment@WFDSConMgr@@UEAA@XZ; WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18003cd63  mov     rcx, [rdi+78h]
0x18003cd67  xor     ebx, ebx
0x18003cd69  test    rcx, rcx
0x18003cd6c  jz      short loc_18003CDA3
0x18003cd6e  mov     rdx, [rdi+80h]
0x18003cd75  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VIWorkQueueJob@WFDSConMgr@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VIWorkQueueJob@WFDSConMgr@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VIWorkQueueJob@WFDSConMgr@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<WFDSConMgr::IWorkQueueJob>>>(std::shared_ptr<WFDSConMgr::IWorkQueueJob> *,std::shared_ptr<WFDSConMgr::IWorkQueueJob> * const,std::allocator<std::shared_ptr<WFDSConMgr::IWorkQueueJob>> &)
0x18003cd7a  mov     rcx, [rdi+78h]
0x18003cd7e  mov     rdx, [rdi+88h]
0x18003cd85  sub     rdx, rcx
0x18003cd88  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18003cd8c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003cd91  mov     [rdi+78h], rbx
0x18003cd95  mov     [rdi+80h], rbx
0x18003cd9c  mov     [rdi+88h], rbx
0x18003cda3  lea     rcx, [rdi+50h]
0x18003cda7  call    ??1?$deque@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@V?$allocator@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::unique_ptr<WFDSConMgr::ISessionWork>>::~deque<std::unique_ptr<WFDSConMgr::ISessionWork>>(void)
0x18003cdac  lea     rcx, [rdi+28h]; lpCriticalSection
0x18003cdb0  call    cs:__imp_DeleteCriticalSection
0x18003cdb6  mov     rcx, rdi; this
0x18003cdb9  mov     rbx, [rsp+28h+arg_0]
0x18003cdbe  add     rsp, 20h
0x18003cdc2  pop     rdi
0x18003cdc3  jmp     ??1WorkItem@WFDSConMgr@@UEAA@XZ; WFDSConMgr::WorkItem::~WorkItem(void)
```
