# atexit

- ea: `0x140001a9c`
- end: `0x140001ab3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001220`
- `0x1400013b0`
- `0x1400013d0`

## callees

- `0x140001a00`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140001a9c  sub     rsp, 28h
0x140001aa0  call    _onexit_0
0x140001aa5  neg     rax
0x140001aa8  sbb     eax, eax
0x140001aaa  neg     eax
0x140001aac  dec     eax
0x140001aae  add     rsp, 28h
0x140001ab2  retn
```
