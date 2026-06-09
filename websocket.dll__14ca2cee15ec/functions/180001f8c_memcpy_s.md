# memcpy_s

- ea: `0x180001f8c`
- end: `0x180001f92`
- name: `memcpy_s`
- size: `6`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180004d80`
- `0x1800057f8`
- `0x1800067b8`
- `0x180006948`
- `0x180007164`
- `0x180007c88`
- `0x1800080e8`
- `0x1800082b4`
- `0x180008c2c`
- `0x180008d9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_memcpy_s` at `0x180001f8c`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl memcpy_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  return __imp_memcpy_s(Destination, DestinationSize, Source, SourceSize);
}

```

## disassembly

```asm
0x180001f8c  jmp     cs:__imp_memcpy_s
```
