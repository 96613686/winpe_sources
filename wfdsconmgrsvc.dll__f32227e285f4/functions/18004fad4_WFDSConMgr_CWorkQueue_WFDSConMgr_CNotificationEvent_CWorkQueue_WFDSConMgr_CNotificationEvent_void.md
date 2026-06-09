# WFDSConMgr::CWorkQueue<WFDSConMgr::CNotificationEvent>::~CWorkQueue<WFDSConMgr::CNotificationEvent>(void)

- ea: `0x18004fad4`
- end: `0x18004fb78`
- name: `??1?$CWorkQueue@VCNotificationEvent@WFDSConMgr@@@WFDSConMgr@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, const void *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18004fbd8`
- `0x18004fd00`
- `0x18006b0fe`

## callees

- `0x1800069d0`
- `0x18002fae8`
- `0x18004fad4`
- `0x18004fb80`
- `0x18005cd7c`
- `0x18005cedc`
- `0x18005d27c`
- `0x18005dca0`
- `0x18005f1c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004fb60`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004fb60`

## pseudocode

```c
void __fastcall WFDSConMgr::CWorkQueue<WFDSConMgr::CNotificationEvent>::~CWorkQueue<WFDSConMgr::CNotificationEvent>(
        struct _RTL_CRITICAL_SECTION *this,
        const void *a2)
{
  bool v3; // dl
  __int64 v4; // r8
  __int64 v5; // r9
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&WFDSConMgr::CWorkQueue<WFDSConMgr::CNotificationEvent>::`vftable';
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
  std::deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>::~deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>(&this[2]);
  DeleteCriticalSection(this + 1);
  WFDSConMgr::WorkItem::~WorkItem((WFDSConMgr::WorkItem *)this);
}

```

## disassembly

```asm
0x18004fad4  mov     [rsp+arg_0], rbx
0x18004fad9  push    rdi
0x18004fada  sub     rsp, 20h
0x18004fade  lea     rax, ??_7?$CWorkQueue@VCNotificationEvent@WFDSConMgr@@@WFDSConMgr@@6B@; const WFDSConMgr::CWorkQueue<WFDSConMgr::CNotificationEvent>::`vftable'
0x18004fae5  mov     rdi, rcx
0x18004fae8  mov     [rcx], rax
0x18004faeb  call    ?TraceCleanupAndWait@WorkQueueTrace@WFDSConMgr@@YAXPEBX@Z; WFDSConMgr::WorkQueueTrace::TraceCleanupAndWait(void const *)
0x18004faf0  lea     rbx, [rdi+98h]
0x18004faf7  mov     rcx, rbx; this
0x18004fafa  call    ?CleanupGroupMembers@CThreadpoolEnvironment@WFDSConMgr@@QEAAX_N@Z; WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18004faff  lea     rcx, [rdi+110h]; this
0x18004fb06  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x18004fb0b  mov     rcx, rbx; this
0x18004fb0e  call    ??1CThreadpoolEnvironment@WFDSConMgr@@UEAA@XZ; WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18004fb13  mov     rcx, [rdi+78h]
0x18004fb17  xor     ebx, ebx
0x18004fb19  test    rcx, rcx
0x18004fb1c  jz      short loc_18004FB53
0x18004fb1e  mov     rdx, [rdi+80h]
0x18004fb25  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VIWorkQueueJob@WFDSConMgr@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VIWorkQueueJob@WFDSConMgr@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VIWorkQueueJob@WFDSConMgr@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<WFDSConMgr::IWorkQueueJob>>>(std::shared_ptr<WFDSConMgr::IWorkQueueJob> *,std::shared_ptr<WFDSConMgr::IWorkQueueJob> * const,std::allocator<std::shared_ptr<WFDSConMgr::IWorkQueueJob>> &)
0x18004fb2a  mov     rcx, [rdi+78h]
0x18004fb2e  mov     rdx, [rdi+88h]
0x18004fb35  sub     rdx, rcx
0x18004fb38  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18004fb3c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004fb41  mov     [rdi+78h], rbx
0x18004fb45  mov     [rdi+80h], rbx
0x18004fb4c  mov     [rdi+88h], rbx
0x18004fb53  lea     rcx, [rdi+50h]
0x18004fb57  call    ??1?$deque@V?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@V?$allocator@V?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>::~deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>(void)
0x18004fb5c  lea     rcx, [rdi+28h]; lpCriticalSection
0x18004fb60  call    cs:__imp_DeleteCriticalSection
0x18004fb66  mov     rcx, rdi; this
0x18004fb69  mov     rbx, [rsp+28h+arg_0]
0x18004fb6e  add     rsp, 20h
0x18004fb72  pop     rdi
0x18004fb73  jmp     ??1WorkItem@WFDSConMgr@@UEAA@XZ; WFDSConMgr::WorkItem::~WorkItem(void)
```
