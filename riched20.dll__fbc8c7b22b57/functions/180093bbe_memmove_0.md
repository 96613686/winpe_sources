# memmove_0

- ea: `0x180093bbe`
- end: `0x180093bc4`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a80`
- `0x180009584`
- `0x18000e874`
- `0x180017230`
- `0x180018380`
- `0x180019d74`
- `0x18001aee4`
- `0x18001ce50`
- `0x18001dfe0`
- `0x180027678`
- `0x18002cc48`
- `0x180037c70`
- `0x180037e20`
- `0x180038208`
- `0x180038970`
- `0x18003ccbc`
- `0x18003d330`
- `0x18003d490`
- `0x180042058`
- `0x18004670c`
- `0x180046a68`
- `0x1800481d4`
- `0x180049ec8`
- `0x18004b92c`
- `0x180051f9c`
- `0x180052130`
- `0x180052354`
- `0x180052484`
- `0x1800526fc`
- `0x180054d70`
- `0x18005ab00`
- `0x18006f180`
- `0x18006f570`
- `0x180071ef0`
- `0x180089a90`

## import_xrefs

- `msvcrt!memmove` at `0x180093bbe`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x180093bbe  jmp     cs:__imp_memmove
```
