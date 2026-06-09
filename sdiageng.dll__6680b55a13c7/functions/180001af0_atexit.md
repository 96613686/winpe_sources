# atexit

- ea: `0x180001af0`
- end: `0x180001b07`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001030`
- `0x180001050`
- `0x180001070`
- `0x180001230`
- `0x180001250`

## callees

- `0x180001a54`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001af0  sub     rsp, 28h
0x180001af4  call    _onexit_0
0x180001af9  neg     rax
0x180001afc  sbb     eax, eax
0x180001afe  neg     eax
0x180001b00  dec     eax
0x180001b02  add     rsp, 28h
0x180001b06  retn
```
