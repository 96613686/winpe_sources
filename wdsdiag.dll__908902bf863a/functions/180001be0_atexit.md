# atexit

- ea: `0x180001be0`
- end: `0x180001bf7`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001000`
- `0x180001030`
- `0x180002004`

## callees

- `0x180001b50`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001be0  sub     rsp, 28h
0x180001be4  call    _onexit_0
0x180001be9  neg     rax
0x180001bec  sbb     eax, eax
0x180001bee  neg     eax
0x180001bf0  dec     eax
0x180001bf2  add     rsp, 28h
0x180001bf6  retn
```
