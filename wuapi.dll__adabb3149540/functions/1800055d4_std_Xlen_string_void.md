# std::_Xlen_string(void)

- ea: `0x1800055d4`
- end: `0x1800055de`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `10`
- prototype: `void __noreturn(void)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180006358`
- `0x1800084c4`
- `0x180008718`
- `0x180008868`
- `0x180008928`
- `0x180008b78`
- `0x180008cb8`
- `0x180008e10`
- `0x180008f24`
- `0x1800092e0`
- `0x180009414`
- `0x180009614`

## callees

- `0x18000f138`

## pseudocode

```c
void __fastcall __noreturn std::_Xlen_string(const char *a1)
{
  std::_Xlength_error(a1);
}

```

## disassembly

```asm
0x1800055d4  sub     rsp, 28h
0x1800055d8  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
