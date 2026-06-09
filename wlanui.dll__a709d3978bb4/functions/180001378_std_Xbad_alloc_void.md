# std::_Xbad_alloc(void)

- ea: `0x180001378`
- end: `0x180001398`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011d0`
- `0x1800164c4`
- `0x18001af34`
- `0x18001b050`
- `0x18001c3a7`
- `0x18001c474`

## callees

- `0x180001230`
- `0x180001e0c`

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
0x180001378  sub     rsp, 48h
0x18000137c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001381  call    ??0bad_alloc@std@@QEAA@XZ
0x180001386  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000138d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001392  call    _CxxThrowException_0
```
