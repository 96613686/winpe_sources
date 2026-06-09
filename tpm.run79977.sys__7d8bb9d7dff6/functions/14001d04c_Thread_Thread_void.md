# Thread::~Thread(void)

- ea: `0x14001d04c`
- end: `0x14001d069`
- name: `??1Thread@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(Thread *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001d070`
- `0x14001d0e0`
- `0x140020100`

## callees

- `0x140044e50`
- `0x140044f00`

## pseudocode

```c
void __fastcall Thread::~Thread(Thread *this)
{
  Thread::Cleanup(this);
  SyncObject::Cleanup(this);
}

```

## disassembly

```asm
0x14001d04c  push    rbx
0x14001d04e  sub     rsp, 20h
0x14001d052  mov     rbx, rcx
0x14001d055  call    ?Cleanup@Thread@@QEAAXXZ; Thread::Cleanup(void)
0x14001d05a  mov     rcx, rbx; this
0x14001d05d  call    ?Cleanup@SyncObject@@QEAAXXZ; SyncObject::Cleanup(void)
0x14001d062  add     rsp, 20h
0x14001d066  pop     rbx
0x14001d067  retn
```
