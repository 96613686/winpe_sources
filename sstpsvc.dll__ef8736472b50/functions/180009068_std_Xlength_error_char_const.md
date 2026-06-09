# std::_Xlength_error(char const *)

- ea: `0x180009068`
- end: `0x18000908b`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180008610`
- `0x180008850`
- `0x18001286c`
- `0x180012cd0`
- `0x180012dc0`
- `0x180012f50`
- `0x180013334`
- `0x1800133b4`
- `0x18001406c`
- `0x180014168`

## callees

- `0x180008fe4`
- `0x18000983e`

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
0x180009068  sub     rsp, 48h
0x18000906c  mov     rdx, rcx; char *
0x18000906f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180009074  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180009079  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180009080  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180009085  call    _CxxThrowException_0
```
