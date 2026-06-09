# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x180002084`
- end: `0x180002095`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020b4`
- `0x1800021ac`
- `0x180009ff0`
- `0x18000a100`
- `0x18000a4ec`
- `0x18000b380`

## callees

- `0x180001300`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180002084  sub     rsp, 28h
0x180002088  lea     rcx, aStringTooLong
0x18000208f  call    ?_Xlength_error@std@@YAXPEBD@Z
```
