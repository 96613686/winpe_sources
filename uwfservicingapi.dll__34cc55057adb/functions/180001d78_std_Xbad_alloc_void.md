# std::_Xbad_alloc(void)

- ea: `0x180001d78`
- end: `0x180001d98`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001a38`
- `0x180001c18`
- `0x180005527`

## callees

- `0x180001a98`
- `0x1800024dc`

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
0x180001d78  sub     rsp, 48h
0x180001d7c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001d81  call    ??0bad_alloc@std@@QEAA@XZ
0x180001d86  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001d8d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001d92  call    _CxxThrowException_0
```
