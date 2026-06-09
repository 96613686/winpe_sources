# SkciCreateSecureImage

- ea: `0x14003bf36`
- end: `0x14003bf3c`
- name: `SkciCreateSecureImage`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `skci!SkciCreateSecureImage` at `0x14003bf36`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall SkciCreateSecureImage(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  return __imp_SkciCreateSecureImage(a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x14003bf36  jmp     cs:__imp_SkciCreateSecureImage
```
