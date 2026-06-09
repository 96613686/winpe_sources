# std::_Xbad_alloc(void)

- ea: `0x180001518`
- end: `0x180001538`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x180001374`
- `0x180010154`
- `0x1800128f0`
- `0x1800144f0`
- `0x18001cbd0`
- `0x18001cc1c`
- `0x18001cc68`
- `0x18001ccb4`
- `0x18001cd10`
- `0x18001cd64`
- `0x18001cdb8`
- `0x18001cf14`
- `0x18001d118`
- `0x18001d208`
- `0x1800201a4`
- `0x180020460`
- `0x1800206bc`
- `0x180028384`
- `0x1800283d0`
- `0x18002841c`
- `0x180028468`
- `0x1800284bc`
- `0x180028510`
- `0x180028564`
- `0x180028848`
- `0x180028e5c`
- `0x18002eb60`
- `0x18002ebd8`
- `0x18003215c`
- `0x1800321ec`

## callees

- `0x1800013d4`
- `0x180001d4c`

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
0x180001518  sub     rsp, 48h
0x18000151c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001521  call    ??0bad_alloc@std@@QEAA@XZ
0x180001526  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000152d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001532  call    _CxxThrowException_0
```
