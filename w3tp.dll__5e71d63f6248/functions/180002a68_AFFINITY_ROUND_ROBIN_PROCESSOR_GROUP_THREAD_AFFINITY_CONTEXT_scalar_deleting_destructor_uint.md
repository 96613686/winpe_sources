# AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x180002a68`
- end: `0x180002a87`
- name: `??_GTHREAD_AFFINITY_CONTEXT@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002888`
- `0x180002ddc`

## callees

- `0x180001f8c`
- `0x180002908`

## pseudocode

```c
struct _PROC_THREAD_ATTRIBUTE_LIST **__fastcall AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::`scalar deleting destructor'(
        struct _PROC_THREAD_ATTRIBUTE_LIST **this)
{
  AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::~THREAD_AFFINITY_CONTEXT(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002a68  push    rbx
0x180002a6a  sub     rsp, 20h
0x180002a6e  mov     rbx, rcx
0x180002a71  call    ??1THREAD_AFFINITY_CONTEXT@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAA@XZ; AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::~THREAD_AFFINITY_CONTEXT(void)
0x180002a76  mov     rcx, rbx; Block
0x180002a79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002a7e  mov     rax, rbx
0x180002a81  add     rsp, 20h
0x180002a85  pop     rbx
0x180002a86  retn
```
