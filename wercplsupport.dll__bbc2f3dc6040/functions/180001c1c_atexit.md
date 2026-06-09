# atexit

- ea: `0x180001c1c`
- end: `0x180001c33`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001430`
- `0x180001450`
- `0x180001480`
- `0x1800014e0`
- `0x180001600`
- `0x180001620`

## callees

- `0x180001b80`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001c1c  sub     rsp, 28h
0x180001c20  call    _onexit_0
0x180001c25  neg     rax
0x180001c28  sbb     eax, eax
0x180001c2a  neg     eax
0x180001c2c  dec     eax
0x180001c2e  add     rsp, 28h
0x180001c32  retn
```
