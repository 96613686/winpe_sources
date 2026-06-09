# CInfraConnectTask::~CInfraConnectTask(void)

- ea: `0x1800035b0`
- end: `0x1800035d0`
- name: `??1CInfraConnectTask@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(CInfraConnectTask *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002d9c`
- `0x180002e24`
- `0x1800030d4`
- `0x180003160`

## callees

- `0x180003458`
- `0x18000354c`

## pseudocode

```c
void __fastcall CInfraConnectTask::~CInfraConnectTask(CInfraConnectTask *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 8);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CInfraConnectTask *)((char *)this + 16));
}

```

## disassembly

```asm
0x1800035b0  push    rbx
0x1800035b2  sub     rsp, 20h
0x1800035b6  mov     rbx, rcx
0x1800035b9  add     rcx, 40h ; '@'
0x1800035bd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800035c2  lea     rcx, [rbx+10h]; this
0x1800035c6  add     rsp, 20h
0x1800035ca  pop     rbx
0x1800035cb  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
