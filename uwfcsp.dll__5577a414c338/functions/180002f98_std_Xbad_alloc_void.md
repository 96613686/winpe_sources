# std::_Xbad_alloc(void)

- ea: `0x180002f98`
- end: `0x180002fb8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c54`
- `0x180002e38`
- `0x18001a323`

## callees

- `0x180002cc0`
- `0x180003f4c`

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
0x180002f98  sub     rsp, 48h
0x180002f9c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002fa1  call    ??0bad_alloc@std@@QEAA@XZ
0x180002fa6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180002fad  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002fb2  call    _CxxThrowException_0
```
