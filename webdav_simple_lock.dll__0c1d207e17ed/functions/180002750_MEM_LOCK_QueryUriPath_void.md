# MEM_LOCK::QueryUriPath(void)

- ea: `0x180002750`
- end: `0x180002755`
- name: `?QueryUriPath@MEM_LOCK@@UEBAPEBGXZ`
- size: `5`
- prototype: `const unsigned __int16 *__fastcall(MEM_LOCK *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
const unsigned __int16 *__fastcall MEM_LOCK::QueryUriPath(MEM_LOCK *this)
{
  return (const unsigned __int16 *)*((_QWORD *)this + 15);
}

```

## disassembly

```asm
0x180002750  mov     rax, [rcx+78h]
0x180002754  retn
```
