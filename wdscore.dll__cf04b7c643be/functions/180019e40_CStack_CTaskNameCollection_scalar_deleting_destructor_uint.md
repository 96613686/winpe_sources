# CStack<CTaskNameCollection *>::`scalar deleting destructor'(uint)

- ea: `0x180019e40`
- end: `0x180019e60`
- name: `??_G?$CStack@PEAVCTaskNameCollection@@@@QEAAPEAXI@Z`
- size: `32`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18001a5d8`
- `0x18001bb80`

## callees

- `0x180001184`
- `0x18000f200`

## pseudocode

```c
CBuffer *__fastcall CStack<CTaskNameCollection *>::`scalar deleting destructor'(CBuffer *Block)
{
  CBuffer::~CBuffer(Block);
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180019e40  push    rbx
0x180019e42  sub     rsp, 20h
0x180019e46  mov     rbx, rcx
0x180019e49  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180019e4e  mov     rcx, rbx; Block
0x180019e51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019e56  mov     rax, rbx
0x180019e59  add     rsp, 20h
0x180019e5d  pop     rbx
0x180019e5e  retn
```
