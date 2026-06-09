# std::_Xlen_string(void)

- ea: `0x14000a2dc`
- end: `0x14000a2ee`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x140007078`
- `0x140007168`
- `0x1400073a0`
- `0x140007498`
- `0x1400075ec`
- `0x1400076f0`
- `0x14000780c`
- `0x140007980`
- `0x140007ab8`
- `0x140007bf8`
- `0x140007d60`
- `0x1400084a4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000a2e7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000a2e7`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000a2dc  sub     rsp, 28h
0x14000a2e0  lea     rcx, aStringTooLong; "string too long"
0x14000a2e7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
