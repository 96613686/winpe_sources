# std::_Xlen_string(void)

- ea: `0x18000c5d4`
- end: `0x18000c5e6`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003a84`
- `0x18000e47c`
- `0x18000e5bc`
- `0x18000f7dc`
- `0x1800169b8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c5df`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c5df`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000c5d4  sub     rsp, 28h
0x18000c5d8  lea     rcx, aStringTooLong; "string too long"
0x18000c5df  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
