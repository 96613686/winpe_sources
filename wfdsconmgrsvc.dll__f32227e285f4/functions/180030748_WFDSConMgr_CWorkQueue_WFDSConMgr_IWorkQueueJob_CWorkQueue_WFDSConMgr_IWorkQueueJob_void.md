# WFDSConMgr::CWorkQueue<WFDSConMgr::IWorkQueueJob>::~CWorkQueue<WFDSConMgr::IWorkQueueJob>(void)

- ea: `0x180030748`
- end: `0x1800307ec`
- name: `??1?$CWorkQueue@VIWorkQueueJob@WFDSConMgr@@@WFDSConMgr@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, const void *)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180030a78`
- `0x180030cd0`
- `0x1800531d0`
- `0x18006b265`

## callees

- `0x1800069d0`
- `0x18002fae8`
- `0x180030748`
- `0x1800308fc`
- `0x18005cd7c`
- `0x18005cedc`
- `0x18005d27c`
- `0x18005dca0`
- `0x18005f1c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800307d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800307d4`

## pseudocode

```c
void __fastcall WFDSConMgr::CWorkQueue<WFDSConMgr::IWorkQueueJob>::~CWorkQueue<WFDSConMgr::IWorkQueueJob>(
        struct _RTL_CRITICAL_SECTION *this,
        const void *a2)
{
  bool v3; // dl
  __int64 v4; // r8
  __int64 v5; // r9
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&WFDSConMgr::CWorkQueue<WFDSConMgr::IWorkQueueJob>::`vftable';
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
0x180030748  mov     [rsp+arg_0], rbx
0x18003074d  push    rdi
0x18003074e  sub     rsp, 20h
0x180030752  lea     rax, ??_7?$CWorkQueue@VIWorkQueueJob@WFDSConMgr@@@WFDSConMgr@@6B@; const WFDSConMgr::CWorkQueue<WFDSConMgr::IWorkQueueJob>::`vftable'
0x180030759  mov     rdi, rcx
0x18003075c  mov     [rcx], rax
0x18003075f  call    ?TraceCleanupAndWait@WorkQueueTrace@WFDSConMgr@@YAXPEBX@Z; WFDSConMgr::WorkQueueTrace::TraceCleanupAndWait(void const *)
0x180030764  lea     rbx, [rdi+98h]
0x18003076b  mov     rcx, rbx; this
0x18003076e  call    ?CleanupGroupMembers@CThreadpoolEnvironment@WFDSConMgr@@QEAAX_N@Z; WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x180030773  lea     rcx, [rdi+110h]; this
0x18003077a  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x18003077f  mov     rcx, rbx; this
0x180030782  call    ??1CThreadpoolEnvironment@WFDSConMgr@@UEAA@XZ; WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x180030787  mov     rcx, [rdi+78h]
0x18003078b  xor     ebx, ebx
0x18003078d  test    rcx, rcx
0x180030790  jz      short loc_1800307C7
0x180030792  mov     rdx, [rdi+80h]
0x180030799  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VIWorkQueueJob@WFDSConMgr@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VIWorkQueueJob@WFDSConMgr@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VIWorkQueueJob@WFDSConMgr@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<WFDSConMgr::IWorkQueueJob>>>(std::shared_ptr<WFDSConMgr::IWorkQueueJob> *,std::shared_ptr<WFDSConMgr::IWorkQueueJob> * const,std::allocator<std::shared_ptr<WFDSConMgr::IWorkQueueJob>> &)
0x18003079e  mov     rcx, [rdi+78h]
0x1800307a2  mov     rdx, [rdi+88h]
0x1800307a9  sub     rdx, rcx
0x1800307ac  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800307b0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800307b5  mov     [rdi+78h], rbx
0x1800307b9  mov     [rdi+80h], rbx
0x1800307c0  mov     [rdi+88h], rbx
0x1800307c7  lea     rcx, [rdi+50h]
0x1800307cb  call    ??1?$deque@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@V?$allocator@V?$unique_ptr@VISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::unique_ptr<WFDSConMgr::ISessionWork>>::~deque<std::unique_ptr<WFDSConMgr::ISessionWork>>(void)
0x1800307d0  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800307d4  call    cs:__imp_DeleteCriticalSection
0x1800307da  mov     rcx, rdi; this
0x1800307dd  mov     rbx, [rsp+28h+arg_0]
0x1800307e2  add     rsp, 20h
0x1800307e6  pop     rdi
0x1800307e7  jmp     ??1WorkItem@WFDSConMgr@@UEAA@XZ; WFDSConMgr::WorkItem::~WorkItem(void)
```
