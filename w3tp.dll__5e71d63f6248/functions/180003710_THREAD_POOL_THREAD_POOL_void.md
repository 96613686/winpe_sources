# THREAD_POOL::THREAD_POOL(void)

- ea: `0x180003710`
- end: `0x18000371b`
- name: `??0THREAD_POOL@@AEAA@XZ`
- size: `11`
- prototype: `THREAD_POOL *__fastcall(THREAD_POOL *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
THREAD_POOL *__fastcall THREAD_POOL::THREAD_POOL(THREAD_POOL *this)
{
  *(_QWORD *)this = 0;
  return this;
}

```

## disassembly

```asm
0x180003710  mov     qword ptr [rcx], 0
0x180003717  mov     rax, rcx
0x18000371a  retn
```
