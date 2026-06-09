# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x18001661c`
- end: `0x18001662d`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001664c`
- `0x180016744`
- `0x180019c58`
- `0x18001a8c0`
- `0x18001b214`
- `0x18001b4b8`
- `0x18001b820`

## callees

- `0x1800013a0`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18001661c  sub     rsp, 28h
0x180016620  lea     rcx, aStringTooLong
0x180016627  call    ?_Xlength_error@std@@YAXPEBD@Z
```
