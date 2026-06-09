# _com_raise_error(long,IErrorInfo *)

- ea: `0x14000a1f8`
- end: `0x14000a22b`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `51`
- prototype: `void __fastcall __noreturn(__int64, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006210`

## callees

- `0x14000894c`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(__int64 a1, struct IErrorInfo *a2)
{
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  int v3; // [rsp+28h] [rbp-20h]
  __int128 v4; // [rsp+30h] [rbp-18h]

  v3 = -2147024882;
  pExceptionObject = &_com_error::`vftable';
  v4 = 0;
  throw (_com_error *)&pExceptionObject;
}

```

## disassembly

```asm
0x14000a1f8  sub     rsp, 48h
0x14000a1fc  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x14000a203  mov     [rsp+48h+var_20], 8007000Eh
0x14000a20b  xorps   xmm0, xmm0
0x14000a20e  mov     [rsp+48h+pExceptionObject], rax
0x14000a213  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x14000a21a  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000a21f  movdqu  [rsp+48h+var_18], xmm0
0x14000a225  call    _CxxThrowException_0
```
