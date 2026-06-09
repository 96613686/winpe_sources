# atexit

- ea: `0x180001cb4`
- end: `0x180001ccb`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001030`
- `0x1800015a0`
- `0x1800015c0`
- `0x1800015e0`

## callees

- `0x180001c18`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001cb4  sub     rsp, 28h
0x180001cb8  call    _onexit_0
0x180001cbd  neg     rax
0x180001cc0  sbb     eax, eax
0x180001cc2  neg     eax
0x180001cc4  dec     eax
0x180001cc6  add     rsp, 28h
0x180001cca  retn
```
