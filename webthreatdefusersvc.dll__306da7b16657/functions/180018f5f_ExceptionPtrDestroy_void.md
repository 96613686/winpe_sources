# __ExceptionPtrDestroy(void *)

- ea: `0x180018f5f`
- end: `0x180018f65`
- name: `?__ExceptionPtrDestroy@@YAXPEAX@Z`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800073ec`
- `0x1800078d0`
- `0x180007abc`
- `0x180008610`
- `0x18000f168`
- `0x18002aaa7`
- `0x18002b024`
- `0x18002b183`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180018f5f`

## pseudocode

```c
// attributes: thunk
void __fastcall __ExceptionPtrDestroy(void *a1)
{
  __imp_?__ExceptionPtrDestroy@@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180018f5f  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z
```
