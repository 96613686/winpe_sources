# __tailMerge_ext_ms_win_cluster_clusapi_l1_1_2_dll

- ea: `0x140001f13`
- end: `0x140001f8c`
- name: `__tailMerge_ext_ms_win_cluster_clusapi_l1_1_2_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001f92`

## callees

- `0x140001f13`
- `0x14000d0d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_cluster_clusapi_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_cluster_clusapi_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001f13  mov     [rsp+arg_0], rcx
0x140001f18  mov     [rsp+arg_8], rdx
0x140001f1d  mov     [rsp+arg_10], r8
0x140001f22  mov     [rsp+arg_18], r9
0x140001f27  sub     rsp, 68h
0x140001f2b  movdqa  [rsp+68h+var_48], xmm0
0x140001f31  movdqa  [rsp+68h+var_38], xmm1
0x140001f37  movdqa  [rsp+68h+var_28], xmm2
0x140001f3d  movdqa  [rsp+68h+var_18], xmm3
0x140001f43  mov     rdx, rax
0x140001f46  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_cluster_clusapi_l1_1_2_dll
0x140001f4d  call    __delayLoadHelper2
0x140001f52  movdqa  xmm0, [rsp+68h+var_48]
0x140001f58  movdqa  xmm1, [rsp+68h+var_38]
0x140001f5e  movdqa  xmm2, [rsp+68h+var_28]
0x140001f64  movdqa  xmm3, [rsp+68h+var_18]
0x140001f6a  mov     rcx, [rsp+68h+arg_0]
0x140001f6f  mov     rdx, [rsp+68h+arg_8]
0x140001f74  mov     r8, [rsp+68h+arg_10]
0x140001f7c  mov     r9, [rsp+68h+arg_18]
0x140001f84  add     rsp, 68h
0x140001f88  jmp     short $+2
0x140001f8a  jmp     rax
```
