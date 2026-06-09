# std::_Xbad_alloc(void)

- ea: `0x1800014b8`
- end: `0x1800014d8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001174`
- `0x180001358`
- `0x18000c973`

## callees

- `0x1800011e0`
- `0x18000215c`

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
0x1800014b8  sub     rsp, 48h
0x1800014bc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800014c1  call    ??0bad_alloc@std@@QEAA@XZ
0x1800014c6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800014cd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800014d2  call    _CxxThrowException_0
```
