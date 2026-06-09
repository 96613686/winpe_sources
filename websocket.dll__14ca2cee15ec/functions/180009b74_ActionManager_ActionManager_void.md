# ActionManager::~ActionManager(void)

- ea: `0x180009b74`
- end: `0x180009bb7`
- name: `??1ActionManager@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003cf8`

## callees

- `0x18000ba64`
- `0x18000cb34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009ba2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009ba2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009bb0`

## pseudocode

```c
void __fastcall ActionManager::~ActionManager(struct _RTL_CRITICAL_SECTION *this)
{
  SendQueue::~SendQueue((SendQueue *)&this[10].LockCount);
  SendQueue::~SendQueue((SendQueue *)&this[9]);
  WebSocketProcessor::~WebSocketProcessor((WebSocketProcessor *)&this[2]);
  DeleteCriticalSection(this + 1);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180009b74  push    rbx
0x180009b76  sub     rsp, 20h
0x180009b7a  mov     rbx, rcx
0x180009b7d  add     rcx, 198h; this
0x180009b84  call    ??1SendQueue@@QEAA@XZ; SendQueue::~SendQueue(void)
0x180009b89  lea     rcx, [rbx+168h]; this
0x180009b90  call    ??1SendQueue@@QEAA@XZ; SendQueue::~SendQueue(void)
0x180009b95  lea     rcx, [rbx+50h]; this
0x180009b99  call    ??1WebSocketProcessor@@QEAA@XZ; WebSocketProcessor::~WebSocketProcessor(void)
0x180009b9e  lea     rcx, [rbx+28h]; lpCriticalSection
0x180009ba2  call    cs:__imp_DeleteCriticalSection
0x180009ba8  mov     rcx, rbx
0x180009bab  add     rsp, 20h
0x180009baf  pop     rbx
0x180009bb0  jmp     cs:__imp_DeleteCriticalSection
```
