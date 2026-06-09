# atexit

- ea: `0x180001fb0`
- end: `0x180001fc7`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001030`
- `0x180001050`

## callees

- `0x180001f14`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001fb0  sub     rsp, 28h
0x180001fb4  call    _onexit_0
0x180001fb9  neg     rax
0x180001fbc  sbb     eax, eax
0x180001fbe  neg     eax
0x180001fc0  dec     eax
0x180001fc2  add     rsp, 28h
0x180001fc6  retn
```
