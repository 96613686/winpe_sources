# PROTOCOL_MANAGER_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180009520`
- end: `0x18000953f`
- name: `??_GPROTOCOL_MANAGER_ENTRY@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009548`
- `0x180009630`

## callees

- `0x180001fa8`
- `0x1800094bc`

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
0x180009520  push    rbx
0x180009522  sub     rsp, 20h
0x180009526  mov     rbx, rcx
0x180009529  call    ??1PROTOCOL_MANAGER_ENTRY@@QEAA@XZ; PROTOCOL_MANAGER_ENTRY::~PROTOCOL_MANAGER_ENTRY(void)
0x18000952e  mov     rcx, rbx; Block
0x180009531  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009536  mov     rax, rbx
0x180009539  add     rsp, 20h
0x18000953d  pop     rbx
0x18000953e  retn
```
