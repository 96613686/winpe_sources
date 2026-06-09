# std::_Xbad_alloc(void)

- ea: `0x180002bc8`
- end: `0x180002be8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a88`
- `0x180006fe4`
- `0x18000720c`
- `0x180007290`
- `0x180007334`
- `0x180009b70`
- `0x18000bc38`
- `0x18000c610`
- `0x18000c670`
- `0x18000d654`
- `0x18000f1f7`
- `0x18000f73c`

## callees

- `0x180002ebc`
- `0x18000453c`

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
0x180002bc8  sub     rsp, 48h
0x180002bcc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002bd1  call    ??0bad_alloc@std@@QEAA@XZ
0x180002bd6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180002bdd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002be2  call    _CxxThrowException_0
```
