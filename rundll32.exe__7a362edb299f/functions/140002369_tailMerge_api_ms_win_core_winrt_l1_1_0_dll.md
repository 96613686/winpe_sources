# __tailMerge_api_ms_win_core_winrt_l1_1_0_dll

- ea: `0x140002369`
- end: `0x1400023e2`
- name: `__tailMerge_api_ms_win_core_winrt_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400023e8`
- `0x14000241e`

## callees

- `0x140002369`
- `0x14000b0a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002369  mov     [rsp+arg_0], rcx
0x14000236e  mov     [rsp+arg_8], rdx
0x140002373  mov     [rsp+arg_10], r8
0x140002378  mov     [rsp+arg_18], r9
0x14000237d  sub     rsp, 68h
0x140002381  movdqa  [rsp+68h+var_48], xmm0
0x140002387  movdqa  [rsp+68h+var_38], xmm1
0x14000238d  movdqa  [rsp+68h+var_28], xmm2
0x140002393  movdqa  [rsp+68h+var_18], xmm3
0x140002399  mov     rdx, rax
0x14000239c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_l1_1_0_dll
0x1400023a3  call    __delayLoadHelper2
0x1400023a8  movdqa  xmm0, [rsp+68h+var_48]
0x1400023ae  movdqa  xmm1, [rsp+68h+var_38]
0x1400023b4  movdqa  xmm2, [rsp+68h+var_28]
0x1400023ba  movdqa  xmm3, [rsp+68h+var_18]
0x1400023c0  mov     rcx, [rsp+68h+arg_0]
0x1400023c5  mov     rdx, [rsp+68h+arg_8]
0x1400023ca  mov     r8, [rsp+68h+arg_10]
0x1400023d2  mov     r9, [rsp+68h+arg_18]
0x1400023da  add     rsp, 68h
0x1400023de  jmp     short $+2
0x1400023e0  jmp     rax
```
