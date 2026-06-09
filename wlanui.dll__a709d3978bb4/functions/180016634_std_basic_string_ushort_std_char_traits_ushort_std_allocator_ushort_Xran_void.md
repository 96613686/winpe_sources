# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180016634`
- end: `0x180016645`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001664c`
- `0x180016920`
- `0x18001a8c0`
- `0x18001b214`
- `0x18001b4b8`
- `0x18001b820`

## callees

- `0x1800013cc`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180016634  sub     rsp, 28h
0x180016638  lea     rcx, aInvalidStringP
0x18001663f  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
