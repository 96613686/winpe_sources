# std::_Xout_of_range(char const *)

- ea: `0x180009094`
- end: `0x1800090b7`
- name: `?_Xout_of_range@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180013610`
- `0x18001378c`
- `0x180013a24`
- `0x180013d08`

## callees

- `0x180008fe4`
- `0x18000983e`

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
0x180009094  sub     rsp, 48h
0x180009098  mov     rdx, rcx; char *
0x18000909b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800090a0  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1800090a5  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x1800090ac  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800090b1  call    _CxxThrowException_0
```
