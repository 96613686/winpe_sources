# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000cced`
- end: `0x18000cd66`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cd6c`
- `0x18000cd7e`
- `0x18000ce2d`
- `0x18000ce3f`
- `0x18000cf79`

## callees

- `0x180008bd0`
- `0x18000cced`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000cced  mov     [rsp+arg_0], rcx
0x18000ccf2  mov     [rsp+arg_8], rdx
0x18000ccf7  mov     [rsp+arg_10], r8
0x18000ccfc  mov     [rsp+arg_18], r9
0x18000cd01  sub     rsp, 68h
0x18000cd05  movdqa  [rsp+68h+var_48], xmm0
0x18000cd0b  movdqa  [rsp+68h+var_38], xmm1
0x18000cd11  movdqa  [rsp+68h+var_28], xmm2
0x18000cd17  movdqa  [rsp+68h+var_18], xmm3
0x18000cd1d  mov     rdx, rax
0x18000cd20  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000cd27  call    __delayLoadHelper2
0x18000cd2c  movdqa  xmm0, [rsp+68h+var_48]
0x18000cd32  movdqa  xmm1, [rsp+68h+var_38]
0x18000cd38  movdqa  xmm2, [rsp+68h+var_28]
0x18000cd3e  movdqa  xmm3, [rsp+68h+var_18]
0x18000cd44  mov     rcx, [rsp+68h+arg_0]
0x18000cd49  mov     rdx, [rsp+68h+arg_8]
0x18000cd4e  mov     r8, [rsp+68h+arg_10]
0x18000cd56  mov     r9, [rsp+68h+arg_18]
0x18000cd5e  add     rsp, 68h
0x18000cd62  jmp     short $+2
0x18000cd64  jmp     rax
```
