# std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>::_Xlength(void)

- ea: `0x180015130`
- end: `0x180015142`
- name: `?_Xlength@?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000e22c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001513b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001513b`

## pseudocode

```c
void __noreturn std::vector<winrt::com_ptr<IStream>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180015130  sub     rsp, 28h
0x180015134  lea     rcx, aVectorTooLong; "vector too long"
0x18001513b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
