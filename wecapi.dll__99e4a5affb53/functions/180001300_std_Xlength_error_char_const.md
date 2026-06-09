# std::_Xlength_error(char const *)

- ea: `0x180001300`
- end: `0x180001323`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002084`
- `0x180002b60`
- `0x180003f48`
- `0x180009fd8`

## callees

- `0x1800011f8`
- `0x180001aac`

## pseudocode

```c
void __fastcall __noreturn std::_Xlength_error(const char *a1)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::length_error::length_error((std::length_error *)pExceptionObject, a1);
  throw (std::length_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180001300  sub     rsp, 48h
0x180001304  mov     rdx, rcx; char *
0x180001307  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000130c  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180001311  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180001318  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000131d  call    _CxxThrowException_0
```
