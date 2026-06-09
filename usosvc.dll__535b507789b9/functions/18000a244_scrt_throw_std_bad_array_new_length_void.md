# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000a244`
- end: `0x18000a264`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180002adc`
- `0x180007344`
- `0x1800073bc`
- `0x1800077dc`
- `0x180007b50`
- `0x180007cc4`
- `0x180007f3c`
- `0x1800080a4`

## callees

- `0x1800031b0`
- `0x180008650`

## pseudocode

```c
void __noreturn __scrt_throw_std_bad_array_new_length(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_array_new_length::bad_array_new_length((std::bad_array_new_length *)pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x18000a244  sub     rsp, 48h
0x18000a248  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000a24d  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000a252  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000a259  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000a25e  call    _CxxThrowException_0
```
