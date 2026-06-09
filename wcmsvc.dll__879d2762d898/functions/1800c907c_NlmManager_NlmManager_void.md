# NlmManager::~NlmManager(void)

- ea: `0x1800c907c`
- end: `0x1800c911b`
- name: `??1NlmManager@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(NlmManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ca390`

## callees

- `0x180065274`
- `0x1800652bc`
- `0x1800c8f5c`
- `0x1800c907c`
- `0x1800c9940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c90db`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c90db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c90e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c90e8`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800c9094`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800c9094`

## pseudocode

```c
void __fastcall NlmManager::~NlmManager(struct _RTL_CRITICAL_SECTION *this)
{
  if ( this[24].DebugInfo )
  {
    UnsubscribeServiceChangeNotifications();
    this[24].DebugInfo = 0;
  }
  WcmCommon::ThreadPoolWorkQueue::Cancel((WcmCommon::ThreadPoolWorkQueue *)&this->LockCount);
  WcmCommon::ThreadPoolWorkQueue::Cancel((WcmCommon::ThreadPoolWorkQueue *)&this[7].LockCount);
  WcmCommon::ThreadPoolWorkQueue::Cancel((WcmCommon::ThreadPoolWorkQueue *)&this[14].LockCount);
  NlmManager::CleanupCOM((NlmManager *)this);
  SetEvent(g_nlmManagerExitHandle);
  DeleteCriticalSection(this + 23);
  NlmManager::_unnamed_type_m_lockedData_::__unnamed_type_m_lockedData_(&this[21].LockCount);
  WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue((WcmCommon::ThreadPoolWorkQueue *)&this[14].LockCount);
  WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue((WcmCommon::ThreadPoolWorkQueue *)&this[7].LockCount);
  WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue((WcmCommon::ThreadPoolWorkQueue *)&this->LockCount);
}

```

## disassembly

```asm
0x1800c907c  push    rbx
0x1800c907e  push    rbp
0x1800c907f  push    rsi
0x1800c9080  push    rdi
0x1800c9081  sub     rsp, 28h
0x1800c9085  mov     rbp, rcx
0x1800c9088  mov     rcx, [rcx+3C0h]
0x1800c908f  test    rcx, rcx
0x1800c9092  jz      short loc_1800C90A5
0x1800c9094  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x1800c909a  mov     qword ptr [rbp+3C0h], 0
0x1800c90a5  lea     rcx, [rbp+8]; this
0x1800c90a9  call    ?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ; WcmCommon::ThreadPoolWorkQueue::Cancel(void)
0x1800c90ae  lea     rdi, [rbp+120h]
0x1800c90b5  mov     rcx, rdi; this
0x1800c90b8  call    ?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ; WcmCommon::ThreadPoolWorkQueue::Cancel(void)
0x1800c90bd  lea     rbx, [rbp+238h]
0x1800c90c4  mov     rcx, rbx; this
0x1800c90c7  call    ?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ; WcmCommon::ThreadPoolWorkQueue::Cancel(void)
0x1800c90cc  mov     rcx, rbp; this
0x1800c90cf  call    ?CleanupCOM@NlmManager@@AEAAXXZ; NlmManager::CleanupCOM(void)
0x1800c90d4  mov     rcx, cs:?g_nlmManagerExitHandle@@3PEAXEA; hEvent
0x1800c90db  call    cs:__imp_SetEvent
0x1800c90e1  lea     rcx, [rbp+398h]; lpCriticalSection
0x1800c90e8  call    cs:__imp_DeleteCriticalSection
0x1800c90ee  lea     rcx, [rbp+350h]
0x1800c90f5  call    NlmManager___unnamed_type_m_lockedData_____unnamed_type_m_lockedData_
0x1800c90fa  mov     rcx, rbx; this
0x1800c90fd  call    ??1ThreadPoolWorkQueue@WcmCommon@@QEAA@XZ; WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(void)
0x1800c9102  mov     rcx, rdi; this
0x1800c9105  call    ??1ThreadPoolWorkQueue@WcmCommon@@QEAA@XZ; WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(void)
0x1800c910a  lea     rcx, [rbp+8]; this
0x1800c910e  add     rsp, 28h
0x1800c9112  pop     rdi
0x1800c9113  pop     rsi
0x1800c9114  pop     rbp
0x1800c9115  pop     rbx
0x1800c9116  jmp     ??1ThreadPoolWorkQueue@WcmCommon@@QEAA@XZ; WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(void)
```
