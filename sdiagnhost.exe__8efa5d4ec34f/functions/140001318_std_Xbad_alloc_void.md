# std::_Xbad_alloc(void)

- ea: `0x140001318`
- end: `0x140001338`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001174`
- `0x140006d2c`
- `0x1400078f6`

## callees

- `0x1400011d4`
- `0x14000191c`

## pseudocode

```c
void __noreturn std::_Xbad_alloc(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x140001318  sub     rsp, 48h
0x14000131c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140001321  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001326  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000132d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140001332  call    _CxxThrowException_0
```
