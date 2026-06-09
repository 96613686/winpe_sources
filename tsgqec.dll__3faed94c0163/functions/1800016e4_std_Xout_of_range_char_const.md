# std::_Xout_of_range(char const *)

- ea: `0x1800016e4`
- end: `0x180001707`
- name: `?_Xout_of_range@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001710`
- `0x1800044e4`

## callees

- `0x180001414`
- `0x1800022cc`

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
0x1800016e4  sub     rsp, 48h
0x1800016e8  mov     rdx, rcx; char *
0x1800016eb  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800016f0  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1800016f5  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x1800016fc  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001701  call    _CxxThrowException_0
```
