# std::_Xbad_alloc(void)

- ea: `0x180002308`
- end: `0x180002328`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fd4`
- `0x1800021a8`
- `0x180011f06`

## callees

- `0x180002034`
- `0x18000297c`

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
0x180002308  sub     rsp, 48h
0x18000230c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002311  call    ??0bad_alloc@std@@QEAA@XZ
0x180002316  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000231d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002322  call    _CxxThrowException_0
```
