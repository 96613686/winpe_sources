# THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'(uint)

- ea: `0x180001770`
- end: `0x18000178d`
- name: `??_GTHREAD_PARAM@THREAD_MANAGER@@QEAAPEAXI@Z`
- size: `29`
- prototype: `void *__fastcall(THREAD_MANAGER::THREAD_PARAM *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002ab8`
- `0x180002c34`
- `0x1800034e0`

## callees

- `0x180001f8c`

## pseudocode

```c
THREAD_MANAGER::THREAD_PARAM *__fastcall THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'(
        THREAD_MANAGER::THREAD_PARAM *this)
{
  *(_DWORD *)this = 2017546324;
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001770  push    rbx
0x180001772  sub     rsp, 20h
0x180001776  mov     rbx, rcx
0x180001779  mov     dword ptr [rcx], 78415054h
0x18000177f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001784  mov     rax, rbx
0x180001787  add     rsp, 20h
0x18000178b  pop     rbx
0x18000178c  retn
```
