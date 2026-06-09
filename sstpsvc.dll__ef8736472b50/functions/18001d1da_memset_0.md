# memset_0

- ea: `0x18001d1da`
- end: `0x18001d1e0`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `82`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012b0`
- `0x180001b40`
- `0x180001fe0`
- `0x180002320`
- `0x180002aac`
- `0x180003010`
- `0x180003620`
- `0x180003bc0`
- `0x180004950`
- `0x180004bdc`
- `0x180004d10`
- `0x180004fb0`
- `0x180005110`
- `0x18000530c`
- `0x1800056e0`
- `0x1800059f0`
- `0x180005e30`
- `0x180006290`
- `0x180006960`
- `0x1800071cc`
- `0x180007ae4`
- `0x1800080dc`
- `0x18000823c`
- `0x180009c3c`
- `0x18000a300`
- `0x18000a59c`
- `0x18000a710`
- `0x18000aa44`
- `0x18000abe0`
- `0x18000accc`
- `0x18000adb8`
- `0x18000afb0`
- `0x18000b9c8`
- `0x18000bd24`
- `0x18000c4c4`
- `0x18000c768`
- `0x18000ca68`
- `0x18000d2ec`
- `0x18000d444`
- `0x18000d730`
- `0x18000d978`
- `0x18000da7c`
- `0x18000dd70`
- `0x18000df08`
- `0x18000ebd0`
- `0x18000f6e0`
- `0x18000fd50`
- `0x18001072c`
- `0x180010d80`
- `0x180010fe8`

## import_xrefs

- `msvcrt!memset` at `0x18001d1da`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18001d1da  jmp     cs:__imp_memset
```
