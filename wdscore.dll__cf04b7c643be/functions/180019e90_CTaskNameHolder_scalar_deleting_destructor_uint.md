# CTaskNameHolder::`scalar deleting destructor'(uint)

- ea: `0x180019e90`
- end: `0x180019eb0`
- name: `??_GCTaskNameHolder@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CTaskNameHolder *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180019d70`
- `0x18001b940`

## callees

- `0x180001184`
- `0x180019dc4`

## pseudocode

```c
CTaskNameHolder *__fastcall CTaskNameHolder::`scalar deleting destructor'(CTaskNameHolder *this)
{
  CTaskNameHolder::~CTaskNameHolder(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180019e90  push    rbx
0x180019e92  sub     rsp, 20h
0x180019e96  mov     rbx, rcx
0x180019e99  call    ??1CTaskNameHolder@@QEAA@XZ; CTaskNameHolder::~CTaskNameHolder(void)
0x180019e9e  mov     rcx, rbx; Block
0x180019ea1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019ea6  mov     rax, rbx
0x180019ea9  add     rsp, 20h
0x180019ead  pop     rbx
0x180019eae  retn
```
