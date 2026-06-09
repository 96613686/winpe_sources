# std::_Xbad_alloc(void)

- ea: `0x1800012d8`
- end: `0x1800012f8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010a0`
- `0x180001f2c`
- `0x180003604`
- `0x180003c0c`
- `0x180003c4c`
- `0x180003d78`
- `0x180009ba0`
- `0x180009cb8`
- `0x180009d3c`
- `0x180009de0`
- `0x18000be11`
- `0x18000c607`

## callees

- `0x180001188`
- `0x180001aac`

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
0x1800012d8  sub     rsp, 48h
0x1800012dc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800012e1  call    ??0bad_alloc@std@@QEAA@XZ
0x1800012e6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800012ed  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800012f2  call    _CxxThrowException_0
```
