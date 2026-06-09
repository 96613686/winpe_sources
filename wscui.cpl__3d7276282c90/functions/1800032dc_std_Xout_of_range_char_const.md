# std::_Xout_of_range(char const *)

- ea: `0x1800032dc`
- end: `0x1800032ff`
- name: `?_Xout_of_range@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800084ac`
- `0x180008710`
- `0x1800087b4`

## callees

- `0x18000283c`
- `0x180003208`

## pseudocode

```c
void __fastcall __noreturn std::_Xout_of_range(const char *a1)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::length_error::length_error((std::length_error *)pExceptionObject, a1);
  throw (std::out_of_range *)pExceptionObject;
}

```

## disassembly

```asm
0x1800032dc  sub     rsp, 48h
0x1800032e0  mov     rdx, rcx; char *
0x1800032e3  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800032e8  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1800032ed  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x1800032f4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800032f9  call    _CxxThrowException_0
```
