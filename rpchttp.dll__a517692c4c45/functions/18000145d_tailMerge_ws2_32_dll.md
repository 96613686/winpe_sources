# __tailMerge_ws2_32_dll

- ea: `0x18000145d`
- end: `0x1800014d6`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800014dc`
- `0x1800014ee`
- `0x180001500`
- `0x180001512`
- `0x180001524`
- `0x180001536`
- `0x180001548`
- `0x18000155a`
- `0x18000156c`
- `0x18000157e`
- `0x180001590`

## callees

- `0x18000145d`
- `0x1800244c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000145d  mov     [rsp+arg_0], rcx
0x180001462  mov     [rsp+arg_8], rdx
0x180001467  mov     [rsp+arg_10], r8
0x18000146c  mov     [rsp+arg_18], r9
0x180001471  sub     rsp, 68h
0x180001475  movdqa  [rsp+68h+var_48], xmm0
0x18000147b  movdqa  [rsp+68h+var_38], xmm1
0x180001481  movdqa  [rsp+68h+var_28], xmm2
0x180001487  movdqa  [rsp+68h+var_18], xmm3
0x18000148d  mov     rdx, rax
0x180001490  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x180001497  call    __delayLoadHelper2
0x18000149c  movdqa  xmm0, [rsp+68h+var_48]
0x1800014a2  movdqa  xmm1, [rsp+68h+var_38]
0x1800014a8  movdqa  xmm2, [rsp+68h+var_28]
0x1800014ae  movdqa  xmm3, [rsp+68h+var_18]
0x1800014b4  mov     rcx, [rsp+68h+arg_0]
0x1800014b9  mov     rdx, [rsp+68h+arg_8]
0x1800014be  mov     r8, [rsp+68h+arg_10]
0x1800014c6  mov     r9, [rsp+68h+arg_18]
0x1800014ce  add     rsp, 68h
0x1800014d2  jmp     short $+2
0x1800014d4  jmp     rax
```
