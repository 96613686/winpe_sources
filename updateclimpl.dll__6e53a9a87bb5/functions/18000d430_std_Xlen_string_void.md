# std::_Xlen_string(void)

- ea: `0x18000d430`
- end: `0x18000d43a`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `10`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180009a38`
- `0x180009b88`
- `0x180009f94`
- `0x18000b090`
- `0x18000b1b4`
- `0x18000b2f4`
- `0x18000c2e0`
- `0x18000d5ac`
- `0x18000f384`

## callees

- `0x18000dba4`

## pseudocode

```c
void __fastcall __noreturn std::_Xlen_string(const char *a1)
{
  std::_Xlength_error(a1);
}

```

## disassembly

```asm
0x18000d430  sub     rsp, 28h
0x18000d434  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
