# __tailMerge_winspool_drv

- ea: `0x180006b40`
- end: `0x180006bb9`
- name: `__tailMerge_winspool_drv`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180006bbf`
- `0x180006bd1`
- `0x180006be3`
- `0x180006bf5`
- `0x180006c07`
- `0x180006c19`
- `0x180006c2b`
- `0x180006c3d`
- `0x180006c4f`
- `0x180006c61`

## callees

- `0x180006b40`
- `0x18000f4a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_winspool_drv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winspool_drv,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006b40  mov     [rsp+arg_0], rcx
0x180006b45  mov     [rsp+arg_8], rdx
0x180006b4a  mov     [rsp+arg_10], r8
0x180006b4f  mov     [rsp+arg_18], r9
0x180006b54  sub     rsp, 68h
0x180006b58  movdqa  [rsp+68h+var_48], xmm0
0x180006b5e  movdqa  [rsp+68h+var_38], xmm1
0x180006b64  movdqa  [rsp+68h+var_28], xmm2
0x180006b6a  movdqa  [rsp+68h+var_18], xmm3
0x180006b70  mov     rdx, rax
0x180006b73  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winspool_drv
0x180006b7a  call    __delayLoadHelper2
0x180006b7f  movdqa  xmm0, [rsp+68h+var_48]
0x180006b85  movdqa  xmm1, [rsp+68h+var_38]
0x180006b8b  movdqa  xmm2, [rsp+68h+var_28]
0x180006b91  movdqa  xmm3, [rsp+68h+var_18]
0x180006b97  mov     rcx, [rsp+68h+arg_0]
0x180006b9c  mov     rdx, [rsp+68h+arg_8]
0x180006ba1  mov     r8, [rsp+68h+arg_10]
0x180006ba9  mov     r9, [rsp+68h+arg_18]
0x180006bb1  add     rsp, 68h
0x180006bb5  jmp     short $+2
0x180006bb7  jmp     rax
```
