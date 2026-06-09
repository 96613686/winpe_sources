# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xran(void)

- ea: `0x180001e10`
- end: `0x180001e21`
- name: `?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e28`
- `0x180002100`

## callees

- `0x180001de4`

## pseudocode

```c
void __noreturn std::string::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180001e10  sub     rsp, 28h
0x180001e14  lea     rcx, aInvalidStringP
0x180001e1b  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
