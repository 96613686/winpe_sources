# _decode_pointer

- ea: `0x180003858`
- end: `0x18000385f`
- name: `_decode_pointer`
- size: `7`
- prototype: `PVOID __stdcall(PVOID Ptr)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000361c`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003858`

## pseudocode

```c
// attributes: thunk
PVOID __stdcall decode_pointer(PVOID Ptr)
{
  return DecodePointer(Ptr);
}

```

## disassembly

```asm
0x180003858  jmp     cs:__imp_DecodePointer
```
