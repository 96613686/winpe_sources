# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Xlen(void)

- ea: `0x180009fd8`
- end: `0x180009fe9`
- name: `?_Xlen@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009ee0`
- `0x180009f5c`
- `0x18000a2bc`

## callees

- `0x180001300`

## pseudocode

```c
void __noreturn std::vector<std::wstring>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x180009fd8  sub     rsp, 28h
0x180009fdc  lea     rcx, aVectorTTooLong
0x180009fe3  call    ?_Xlength_error@std@@YAXPEBD@Z
```
