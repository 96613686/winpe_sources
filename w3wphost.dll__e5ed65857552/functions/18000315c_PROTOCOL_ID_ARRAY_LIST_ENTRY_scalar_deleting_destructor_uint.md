# PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x18000315c`
- end: `0x180003180`
- name: `??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(PROTOCOL_ID_ARRAY_LIST_ENTRY *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003340`
- `0x180003ff0`
- `0x18000c248`
- `0x18000c320`

## callees

- `0x180001c80`
- `0x1800020d0`

## pseudocode

```c
PROTOCOL_ID_ARRAY_LIST_ENTRY *__fastcall PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(
        PROTOCOL_ID_ARRAY_LIST_ENTRY *this)
{
  SMALL_STRU::Reset((PROTOCOL_ID_ARRAY_LIST_ENTRY *)((char *)this + 8));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000315c  push    rbx
0x18000315e  sub     rsp, 20h
0x180003162  mov     rbx, rcx
0x180003165  add     rcx, 8; this
0x180003169  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x18000316e  mov     rcx, rbx; Block
0x180003171  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003176  mov     rax, rbx
0x180003179  add     rsp, 20h
0x18000317d  pop     rbx
0x18000317e  retn
```
