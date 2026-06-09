# PROTOCOL_MANAGER_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180009fc8`
- end: `0x180009fe8`
- name: `??_GPROTOCOL_MANAGER_ENTRY@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009ff0`
- `0x18000a0f4`

## callees

- `0x1800020d0`
- `0x180009f54`

## pseudocode

```c
PROTOCOL_MANAGER_ENTRY *__fastcall PROTOCOL_MANAGER_ENTRY::`scalar deleting destructor'(PROTOCOL_MANAGER_ENTRY *this)
{
  PROTOCOL_MANAGER_ENTRY::~PROTOCOL_MANAGER_ENTRY(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009fc8  push    rbx
0x180009fca  sub     rsp, 20h
0x180009fce  mov     rbx, rcx
0x180009fd1  call    ??1PROTOCOL_MANAGER_ENTRY@@QEAA@XZ; PROTOCOL_MANAGER_ENTRY::~PROTOCOL_MANAGER_ENTRY(void)
0x180009fd6  mov     rcx, rbx; Block
0x180009fd9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009fde  mov     rax, rbx
0x180009fe1  add     rsp, 20h
0x180009fe5  pop     rbx
0x180009fe6  retn
```
