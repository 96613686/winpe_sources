# std::_Xlength_error(char const *)

- ea: `0x180001e68`
- end: `0x180001e8b`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e50`
- `0x180003754`
- `0x1800083d8`
- `0x1800085a4`
- `0x180008698`

## callees

- `0x180001bc4`
- `0x180002b4c`

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
0x180001e68  sub     rsp, 48h
0x180001e6c  mov     rdx, rcx; char *
0x180001e6f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001e74  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180001e79  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180001e80  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001e85  call    _CxxThrowException_0
```
