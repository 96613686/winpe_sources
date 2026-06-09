# std::_Xbad_alloc(void)

- ea: `0x180001e28`
- end: `0x180001e48`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800019e4`
- `0x180001cc8`
- `0x180003ac4`
- `0x1800082b4`
- `0x1800083d8`
- `0x180008988`
- `0x180008ad0`
- `0x1800132f3`

## callees

- `0x180001b54`
- `0x180002b4c`

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
