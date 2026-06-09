# atexit

- ea: `0x140007bf8`
- end: `0x140007c0f`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140001090`
- `0x1400010b0`
- `0x1400010d0`
- `0x1400010f0`
- `0x140006ec0`
- `0x140007210`
- `0x140007230`

## callees

- `0x140007b5c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140007bf8  sub     rsp, 28h
0x140007bfc  call    _onexit_0
0x140007c01  neg     rax
0x140007c04  sbb     eax, eax
0x140007c06  neg     eax
0x140007c08  dec     eax
0x140007c0a  add     rsp, 28h
0x140007c0e  retn
```
