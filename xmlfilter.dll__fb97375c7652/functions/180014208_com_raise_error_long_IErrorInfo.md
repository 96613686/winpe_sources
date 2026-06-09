# _com_raise_error(long,IErrorInfo *)

- ea: `0x180014208`
- end: `0x18001422d`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800140d0`

## callees

- `0x180002b44`
- `0x180014134`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  _com_error::_com_error((_com_error *)pExceptionObject, a1, a2);
  throw (_com_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180014208  sub     rsp, 48h
0x18001420c  mov     r8, rdx; struct IErrorInfo *
0x18001420f  mov     edx, ecx; int
0x180014211  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180014216  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x18001421b  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180014222  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180014227  call    _CxxThrowException_0
```
