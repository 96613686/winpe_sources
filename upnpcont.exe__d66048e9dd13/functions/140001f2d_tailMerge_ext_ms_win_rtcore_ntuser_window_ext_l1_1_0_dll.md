# __tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll

- ea: `0x140001f2d`
- end: `0x140001fa6`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001fac`
- `0x140001fbe`
- `0x140001fd0`
- `0x140001fe2`

## callees

- `0x140001f2d`
- `0x140006530`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001f2d  mov     [rsp+arg_0], rcx
0x140001f32  mov     [rsp+arg_8], rdx
0x140001f37  mov     [rsp+arg_10], r8
0x140001f3c  mov     [rsp+arg_18], r9
0x140001f41  sub     rsp, 68h
0x140001f45  movdqa  [rsp+68h+var_48], xmm0
0x140001f4b  movdqa  [rsp+68h+var_38], xmm1
0x140001f51  movdqa  [rsp+68h+var_28], xmm2
0x140001f57  movdqa  [rsp+68h+var_18], xmm3
0x140001f5d  mov     rdx, rax
0x140001f60  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll
0x140001f67  call    __delayLoadHelper2
0x140001f6c  movdqa  xmm0, [rsp+68h+var_48]
0x140001f72  movdqa  xmm1, [rsp+68h+var_38]
0x140001f78  movdqa  xmm2, [rsp+68h+var_28]
0x140001f7e  movdqa  xmm3, [rsp+68h+var_18]
0x140001f84  mov     rcx, [rsp+68h+arg_0]
0x140001f89  mov     rdx, [rsp+68h+arg_8]
0x140001f8e  mov     r8, [rsp+68h+arg_10]
0x140001f96  mov     r9, [rsp+68h+arg_18]
0x140001f9e  add     rsp, 68h
0x140001fa2  jmp     short $+2
0x140001fa4  jmp     rax
```
