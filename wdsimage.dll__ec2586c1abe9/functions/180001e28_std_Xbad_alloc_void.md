# std::_Xbad_alloc(void)

- ea: `0x180001e28`
- end: `0x180001e48`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ae8`
- `0x180001cc8`
- `0x180010326`

## callees

- `0x180001b48`
- `0x18000249c`

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
0x180001e28  sub     rsp, 48h
0x180001e2c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001e31  call    ??0bad_alloc@std@@QEAA@XZ
0x180001e36  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001e3d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001e42  call    _CxxThrowException_0
```
