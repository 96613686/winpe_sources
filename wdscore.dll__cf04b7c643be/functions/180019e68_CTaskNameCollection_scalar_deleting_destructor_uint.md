# CTaskNameCollection::`scalar deleting destructor'(uint)

- ea: `0x180019e68`
- end: `0x180019e88`
- name: `??_GCTaskNameCollection@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CTaskNameCollection *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18001a5d8`
- `0x18001b900`

## callees

- `0x180001184`
- `0x180019d70`

## pseudocode

```c
CTaskNameCollection *__fastcall CTaskNameCollection::`scalar deleting destructor'(CTaskNameCollection *this)
{
  CTaskNameCollection::~CTaskNameCollection(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180019e68  push    rbx
0x180019e6a  sub     rsp, 20h
0x180019e6e  mov     rbx, rcx
0x180019e71  call    ??1CTaskNameCollection@@QEAA@XZ; CTaskNameCollection::~CTaskNameCollection(void)
0x180019e76  mov     rcx, rbx; Block
0x180019e79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019e7e  mov     rax, rbx
0x180019e81  add     rsp, 20h
0x180019e85  pop     rbx
0x180019e86  retn
```
