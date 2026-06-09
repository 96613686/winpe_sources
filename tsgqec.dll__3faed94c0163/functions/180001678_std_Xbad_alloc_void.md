# std::_Xbad_alloc(void)

- ea: `0x180001678`
- end: `0x180001698`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001344`
- `0x180001518`
- `0x1800043e0`
- `0x180004428`
- `0x18000af50`

## callees

- `0x1800013a4`
- `0x1800022cc`

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
0x180001678  sub     rsp, 48h
0x18000167c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001681  call    ??0bad_alloc@std@@QEAA@XZ
0x180001686  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000168d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001692  call    _CxxThrowException_0
```
