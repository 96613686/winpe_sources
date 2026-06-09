# atexit

- ea: `0x180001aa0`
- end: `0x180001ab7`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001030`
- `0x180001050`
- `0x180001070`
- `0x1800010a0`
- `0x1800010d0`
- `0x180001150`
- `0x180001290`
- `0x180001420`
- `0x180001440`
- `0x180001500`

## callees

- `0x180001a08`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001aa0  sub     rsp, 28h
0x180001aa4  call    _onexit_0
0x180001aa9  neg     rax
0x180001aac  sbb     eax, eax
0x180001aae  neg     eax
0x180001ab0  dec     eax
0x180001ab2  add     rsp, 28h
0x180001ab6  retn
```
