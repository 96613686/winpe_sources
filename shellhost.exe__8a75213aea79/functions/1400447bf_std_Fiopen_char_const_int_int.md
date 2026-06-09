# std::_Fiopen(char const *,int,int)

- ea: `0x1400447bf`
- end: `0x1400447c5`
- name: `?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z_0`
- size: `6`
- prototype: `struct _iobuf *(const char *, int, int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140015db0`

## import_xrefs

- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z` at `0x1400447bf`

## pseudocode

```c
// attributes: thunk
struct _iobuf *__fastcall std::_Fiopen(const char *a1, int a2, int a3)
{
  return __imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z(a1, a2, a3);
}

```

## disassembly

```asm
0x1400447bf  jmp     cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z
```
