# atexit

- ea: `0x1800018ec`
- end: `0x180001903`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001060`
- `0x1800010a0`
- `0x1800010d0`

## callees

- `0x1800018ac`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1800018ec  sub     rsp, 28h
0x1800018f0  call    _onexit
0x1800018f5  neg     rax
0x1800018f8  sbb     eax, eax
0x1800018fa  neg     eax
0x1800018fc  dec     eax
0x1800018fe  add     rsp, 28h
0x180001902  retn
```
