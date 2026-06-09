# std::_Xlen_string(void)

- ea: `0x18000a348`
- end: `0x18000a35a`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x1800073bc`
- `0x1800074ac`
- `0x1800076e4`
- `0x1800077dc`
- `0x180007930`
- `0x180007a34`
- `0x180007b50`
- `0x180007cc4`
- `0x180007dfc`
- `0x180007f3c`
- `0x1800080a4`
- `0x1800087e8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a353`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a353`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000a348  sub     rsp, 28h
0x18000a34c  lea     rcx, aStringTooLong; "string too long"
0x18000a353  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
