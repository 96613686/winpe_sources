# memset

- ea: `0x18006ef3a`
- end: `0x18006ef40`
- name: `memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `52`
- callee_count: `0`
- tags: ``

## callers

- `0x1800088b4`
- `0x180014978`
- `0x1800152f0`
- `0x18002393c`
- `0x180023bd8`
- `0x180023ea8`
- `0x1800240b8`
- `0x1800268e4`
- `0x18002dcf4`
- `0x18002f614`
- `0x18003102c`
- `0x180031744`
- `0x1800367d8`
- `0x1800368dc`
- `0x180038058`
- `0x180039abc`
- `0x180039cec`
- `0x18003d2a0`
- `0x18003e140`
- `0x18003f62c`
- `0x180041830`
- `0x1800419a8`
- `0x18004461c`
- `0x1800451b8`
- `0x180045598`
- `0x180046078`
- `0x180046c14`
- `0x18004739c`
- `0x180047b24`
- `0x1800482ac`
- `0x180048a34`
- `0x1800491bc`
- `0x180049f14`
- `0x18004afa4`
- `0x18004c418`
- `0x18004d884`
- `0x18004dcec`
- `0x18004e600`
- `0x180050a30`
- `0x180050b1c`
- `0x180050da8`
- `0x1800512cc`
- `0x180051488`
- `0x180051644`
- `0x180051800`
- `0x1800519bc`
- `0x180051b78`
- `0x180052b58`
- `0x1800541a8`
- `0x1800543b8`

## import_xrefs

- `msvcrt!memset` at `0x18006ef3a`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  return __imp_memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18006ef3a  jmp     cs:__imp_memset
```
