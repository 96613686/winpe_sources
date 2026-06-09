# ThreadWithCancel::`scalar deleting destructor'(uint)

- ea: `0x14001d170`
- end: `0x14001d190`
- name: `??_GThreadWithCancel@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(ThreadWithCancel *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001dc10`
- `0x14001e394`
- `0x14002ed30`

## callees

- `0x14001d070`
- `0x1400454a0`

## pseudocode

```c
ThreadWithCancel *__fastcall ThreadWithCancel::`scalar deleting destructor'(ThreadWithCancel *this)
{
  ThreadWithCancel::~ThreadWithCancel(this);
  TpmFree(this);
  return this;
}

```

## disassembly

```asm
0x14001d170  push    rbx
0x14001d172  sub     rsp, 20h
0x14001d176  mov     rbx, rcx
0x14001d179  call    ??1ThreadWithCancel@@QEAA@XZ; ThreadWithCancel::~ThreadWithCancel(void)
0x14001d17e  mov     rcx, rbx; void *
0x14001d181  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14001d186  mov     rax, rbx
0x14001d189  add     rsp, 20h
0x14001d18d  pop     rbx
0x14001d18e  retn
```
