# _com_raise_error(long,IErrorInfo *)

- ea: `0x18000e328`
- end: `0x18000e357`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `47`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e190`

## callees

- `0x180002e7a`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2)
{
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  int v3; // [rsp+28h] [rbp-20h]
  __int128 v4; // [rsp+30h] [rbp-18h]

  v3 = a1;
  pExceptionObject = &_com_error::`vftable';
  v4 = 0;
  throw (_com_error *)&pExceptionObject;
}

```

## disassembly

```asm
0x18000e328  sub     rsp, 48h
0x18000e32c  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000e333  mov     [rsp+48h+var_20], ecx
0x18000e337  xorps   xmm0, xmm0
0x18000e33a  mov     [rsp+48h+pExceptionObject], rax
0x18000e33f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e344  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000e34b  movdqu  [rsp+48h+var_18], xmm0
0x18000e351  call    _CxxThrowException_0
```
