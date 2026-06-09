# atexit

- ea: `0x180002bd8`
- end: `0x180002bef`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020c0`
- `0x180002210`
- `0x180002230`
- `0x180002250`
- `0x180002280`
- `0x1800022b0`
- `0x1800022f0`
- `0x180002310`
- `0x180002350`
- `0x180002390`
- `0x1800023b0`
- `0x18000ec50`

## callees

- `0x180002b98`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180002bd8  sub     rsp, 28h
0x180002bdc  call    _onexit
0x180002be1  neg     rax
0x180002be4  sbb     eax, eax
0x180002be6  neg     eax
0x180002be8  dec     eax
0x180002bea  add     rsp, 28h
0x180002bee  retn
```
