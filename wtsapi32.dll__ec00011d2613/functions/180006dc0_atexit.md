# atexit

- ea: `0x180006dc0`
- end: `0x180006dd7`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001990`
- `0x1800019c0`
- `0x1800019e0`
- `0x18000c91c`

## callees

- `0x180006d24`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180006dc0  sub     rsp, 28h
0x180006dc4  call    _onexit_0
0x180006dc9  neg     rax
0x180006dcc  sbb     eax, eax
0x180006dce  neg     eax
0x180006dd0  dec     eax
0x180006dd2  add     rsp, 28h
0x180006dd6  retn
```
