# __tailMerge_ext_ms_win_cluster_clusapi_l1_1_1_dll

- ea: `0x140001d6d`
- end: `0x140001de6`
- name: `__tailMerge_ext_ms_win_cluster_clusapi_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ead`
- `0x140001ebf`
- `0x140001ed1`
- `0x140001ee3`
- `0x140001f07`

## callees

- `0x140001d6d`
- `0x14000d0d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_cluster_clusapi_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_cluster_clusapi_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001d6d  mov     [rsp+arg_0], rcx
0x140001d72  mov     [rsp+arg_8], rdx
0x140001d77  mov     [rsp+arg_10], r8
0x140001d7c  mov     [rsp+arg_18], r9
0x140001d81  sub     rsp, 68h
0x140001d85  movdqa  [rsp+68h+var_48], xmm0
0x140001d8b  movdqa  [rsp+68h+var_38], xmm1
0x140001d91  movdqa  [rsp+68h+var_28], xmm2
0x140001d97  movdqa  [rsp+68h+var_18], xmm3
0x140001d9d  mov     rdx, rax
0x140001da0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_cluster_clusapi_l1_1_1_dll
0x140001da7  call    __delayLoadHelper2
0x140001dac  movdqa  xmm0, [rsp+68h+var_48]
0x140001db2  movdqa  xmm1, [rsp+68h+var_38]
0x140001db8  movdqa  xmm2, [rsp+68h+var_28]
0x140001dbe  movdqa  xmm3, [rsp+68h+var_18]
0x140001dc4  mov     rcx, [rsp+68h+arg_0]
0x140001dc9  mov     rdx, [rsp+68h+arg_8]
0x140001dce  mov     r8, [rsp+68h+arg_10]
0x140001dd6  mov     r9, [rsp+68h+arg_18]
0x140001dde  add     rsp, 68h
0x140001de2  jmp     short $+2
0x140001de4  jmp     rax
```
