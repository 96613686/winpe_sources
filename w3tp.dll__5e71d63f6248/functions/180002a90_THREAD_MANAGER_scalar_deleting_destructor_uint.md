# THREAD_MANAGER::`scalar deleting destructor'(uint)

- ea: `0x180002a90`
- end: `0x180002aaf`
- name: `??_GTHREAD_MANAGER@@AEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(THREAD_MANAGER *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003418`

## callees

- `0x180001f8c`
- `0x180002954`

## pseudocode

```c
THREAD_MANAGER *__fastcall THREAD_MANAGER::`scalar deleting destructor'(THREAD_MANAGER *this)
{
  THREAD_MANAGER::~THREAD_MANAGER(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002a90  push    rbx
0x180002a92  sub     rsp, 20h
0x180002a96  mov     rbx, rcx
0x180002a99  call    ??1THREAD_MANAGER@@AEAA@XZ; THREAD_MANAGER::~THREAD_MANAGER(void)
0x180002a9e  mov     rcx, rbx; Block
0x180002aa1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002aa6  mov     rax, rbx
0x180002aa9  add     rsp, 20h
0x180002aad  pop     rbx
0x180002aae  retn
```
