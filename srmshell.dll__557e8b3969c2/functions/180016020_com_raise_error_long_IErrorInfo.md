# _com_raise_error(long,IErrorInfo *)

- ea: `0x180016020`
- end: `0x180016042`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015ef4`

## callees

- `0x180001e44`
- `0x180015f50`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2, struct IErrorInfo *a3)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  _com_error::_com_error((_com_error *)pExceptionObject, a1, a3);
  throw (_com_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180016020  sub     rsp, 48h
0x180016024  mov     edx, ecx; int
0x180016026  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001602b  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x180016030  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180016037  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001603c  call    _CxxThrowException_0
```
