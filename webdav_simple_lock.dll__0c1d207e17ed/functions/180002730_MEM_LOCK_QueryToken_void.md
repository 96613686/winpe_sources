# MEM_LOCK::QueryToken(void)

- ea: `0x180002730`
- end: `0x180002735`
- name: `?QueryToken@MEM_LOCK@@UEBAPEBGXZ`
- size: `5`
- prototype: `const unsigned __int16 *__fastcall(MEM_LOCK *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
const unsigned __int16 *__fastcall MEM_LOCK::QueryToken(MEM_LOCK *this)
{
  return (const unsigned __int16 *)*((_QWORD *)this + 8);
}

```

## disassembly

```asm
0x180002730  mov     rax, [rcx+40h]
0x180002734  retn
```
