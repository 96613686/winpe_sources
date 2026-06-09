# std::_Xout_of_range(char const *)

- ea: `0x180001404`
- end: `0x180001427`
- name: `?_Xout_of_range@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001430`

## callees

- `0x180001134`
- `0x18000200c`

## pseudocode

```c
void __fastcall __noreturn std::_Xout_of_range(char *a1)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::length_error::length_error((std::length_error *)pExceptionObject, a1);
  throw (std::out_of_range *)pExceptionObject;
}

```

## disassembly

```asm
0x180001404  sub     rsp, 48h
0x180001408  mov     rdx, rcx; char *
0x18000140b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001410  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180001415  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x18000141c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001421  call    _CxxThrowException_0
```
