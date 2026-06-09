# std::_Throw_Cpp_error(int)

- ea: `0x18000914e`
- end: `0x180009154`
- name: `?_Throw_Cpp_error@std@@YAXH@Z`
- size: `6`
- prototype: `void __fastcall(int)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c4c`
- `0x180004354`
- `0x1800043dc`
- `0x180004514`
- `0x1800045a8`
- `0x180004760`
- `0x180004890`
- `0x180004c9c`
- `0x180004d34`
- `0x1800055b4`
- `0x180006848`
- `0x1800069f8`
- `0x180007898`
- `0x180007a10`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000914e`

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
0x18000914e  jmp     cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z
```
