# std::_Xlength_error(char const *)

- ea: `0x1800013d8`
- end: `0x1800013fb`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800013c0`
- `0x180002d48`

## callees

- `0x180001134`
- `0x18000200c`

## pseudocode

```c
void __fastcall __noreturn std::_Xlength_error(char *a1)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::length_error::length_error((std::length_error *)pExceptionObject, a1);
  throw (std::length_error *)pExceptionObject;
}

```

## disassembly

```asm
0x1800013d8  sub     rsp, 48h
0x1800013dc  mov     rdx, rcx; char *
0x1800013df  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800013e4  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1800013e9  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x1800013f0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800013f5  call    _CxxThrowException_0
```
