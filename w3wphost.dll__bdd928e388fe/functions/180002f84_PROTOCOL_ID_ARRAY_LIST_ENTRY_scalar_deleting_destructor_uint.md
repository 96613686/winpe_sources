# PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180002f84`
- end: `0x180002fa7`
- name: `??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z`
- size: `35`
- prototype: `void *__fastcall(PROTOCOL_ID_ARRAY_LIST_ENTRY *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003150`
- `0x180003cf0`
- `0x18000b444`
- `0x18000b50c`

## callees

- `0x180001be0`
- `0x180001fa8`

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
0x180002f84  push    rbx
0x180002f86  sub     rsp, 20h
0x180002f8a  mov     rbx, rcx
0x180002f8d  add     rcx, 8; this
0x180002f91  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x180002f96  mov     rcx, rbx; Block
0x180002f99  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f9e  mov     rax, rbx
0x180002fa1  add     rsp, 20h
0x180002fa5  pop     rbx
0x180002fa6  retn
```
