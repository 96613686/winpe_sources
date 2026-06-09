# std::_Xlen_string(void)

- ea: `0x18000a6e0`
- end: `0x18000a6ea`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `10`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180006cec`
- `0x1800073dc`
- `0x180007574`
- `0x1800076c4`
- `0x180007bbc`
- `0x180007e1c`
- `0x180008f84`
- `0x1800090a0`
- `0x1800093b8`
- `0x1800094f8`
- `0x18000a620`
- `0x18000a85c`

## callees

- `0x18000f0e8`

## pseudocode

```c
void __fastcall __noreturn std::_Xlen_string(const char *a1)
{
  std::_Xlength_error(a1);
}

```

## disassembly

```asm
0x18000a6e0  sub     rsp, 28h
0x18000a6e4  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
