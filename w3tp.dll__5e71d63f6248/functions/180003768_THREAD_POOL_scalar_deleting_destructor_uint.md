# THREAD_POOL::`scalar deleting destructor'(uint)

- ea: `0x180003768`
- end: `0x180003787`
- name: `??_GTHREAD_POOL@@AEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(THREAD_POOL *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800037c0`
- `0x180003be0`

## callees

- `0x180001f8c`
- `0x180003730`

## pseudocode

```c
THREAD_POOL *__fastcall THREAD_POOL::`scalar deleting destructor'(THREAD_POOL *this)
{
  THREAD_POOL::~THREAD_POOL(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003768  push    rbx
0x18000376a  sub     rsp, 20h
0x18000376e  mov     rbx, rcx
0x180003771  call    ??1THREAD_POOL@@AEAA@XZ; THREAD_POOL::~THREAD_POOL(void)
0x180003776  mov     rcx, rbx; Block
0x180003779  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000377e  mov     rax, rbx
0x180003781  add     rsp, 20h
0x180003785  pop     rbx
0x180003786  retn
```
