# __tailMerge_user32_dll

- ea: `0x18000146f`
- end: `0x1800014e8`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: ``
- caller_count: `78`
- callee_count: `2`
- tags: `loader_planting`

## callers

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
- `0x1800015a2`
- `0x1800015b4`
- `0x1800015c6`
- `0x1800015d8`
- `0x1800015ea`
- `0x1800015fc`
- `0x18000160e`
- `0x180001620`
- `0x180001632`
- `0x180001644`
- `0x180001656`
- `0x180001668`
- `0x18000167a`
- `0x18000168c`
- `0x18000169e`
- `0x1800016b0`
- `0x1800016c2`
- `0x1800016d4`
- `0x1800016e6`
- `0x1800016f8`
- `0x18000170a`
- `0x18000171c`
- `0x18000172e`
- `0x180001740`
- `0x180001752`
- `0x180001764`
- `0x180001776`
- `0x180001788`
- `0x18000179a`
- `0x1800017ac`
- `0x1800017be`
- `0x1800017d0`
- `0x1800017e2`
- `0x1800017f4`
- `0x180001806`
- `0x180001818`
- `0x18000182a`
- `0x18000183c`
- `0x18000184e`
- `0x180001860`

## callees

- `0x18000146f`
- `0x180012d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000146f  mov     [rsp+arg_0], rcx
0x180001474  mov     [rsp+arg_8], rdx
0x180001479  mov     [rsp+arg_10], r8
0x18000147e  mov     [rsp+arg_18], r9
0x180001483  sub     rsp, 68h
0x180001487  movdqa  [rsp+68h+var_48], xmm0
0x18000148d  movdqa  [rsp+68h+var_38], xmm1
0x180001493  movdqa  [rsp+68h+var_28], xmm2
0x180001499  movdqa  [rsp+68h+var_18], xmm3
0x18000149f  mov     rdx, rax
0x1800014a2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x1800014a9  call    __delayLoadHelper2
0x1800014ae  movdqa  xmm0, [rsp+68h+var_48]
0x1800014b4  movdqa  xmm1, [rsp+68h+var_38]
0x1800014ba  movdqa  xmm2, [rsp+68h+var_28]
0x1800014c0  movdqa  xmm3, [rsp+68h+var_18]
0x1800014c6  mov     rcx, [rsp+68h+arg_0]
0x1800014cb  mov     rdx, [rsp+68h+arg_8]
0x1800014d0  mov     r8, [rsp+68h+arg_10]
0x1800014d8  mov     r9, [rsp+68h+arg_18]
0x1800014e0  add     rsp, 68h
0x1800014e4  jmp     short $+2
0x1800014e6  jmp     rax
```
