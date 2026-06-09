# std::_Throw_Cpp_error(int)

- ea: `0x180003290`
- end: `0x180003296`
- name: `?_Throw_Cpp_error@std@@YAXH@Z`
- size: `6`
- prototype: `void __fastcall(int)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x180007724`
- `0x180007e2c`
- `0x18000903c`
- `0x18000b500`
- `0x18000bce0`
- `0x18000c3b0`
- `0x18000c59c`
- `0x18000cc70`
- `0x18000cd80`
- `0x18000d120`
- `0x18000d7f8`
- `0x18000e118`
- `0x18000e360`
- `0x18000e73c`
- `0x18000ea20`
- `0x18000f0e4`
- `0x18000f168`
- `0x18000f264`
- `0x18000f408`
- `0x18000f540`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180003290`

## pseudocode

```c
// attributes: thunk
void __fastcall std::_Throw_Cpp_error(int a1)
{
  __imp_?_Throw_Cpp_error@std@@YAXH@Z(a1);
}

```

## disassembly

```asm
0x180003290  jmp     cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z
```
