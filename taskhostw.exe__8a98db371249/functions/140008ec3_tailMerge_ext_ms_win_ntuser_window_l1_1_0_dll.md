# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x140008ec3`
- end: `0x140008f3c`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008f42`
- `0x140008f54`
- `0x140008f66`
- `0x140008f78`
- `0x140008f8a`
- `0x140008f9c`

## callees

- `0x140006020`
- `0x140008ec3`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140008ec3  mov     [rsp+arg_0], rcx
0x140008ec8  mov     [rsp+arg_8], rdx
0x140008ecd  mov     [rsp+arg_10], r8
0x140008ed2  mov     [rsp+arg_18], r9
0x140008ed7  sub     rsp, 68h
0x140008edb  movdqa  [rsp+68h+var_48], xmm0
0x140008ee1  movdqa  [rsp+68h+var_38], xmm1
0x140008ee7  movdqa  [rsp+68h+var_28], xmm2
0x140008eed  movdqa  [rsp+68h+var_18], xmm3
0x140008ef3  mov     rdx, rax
0x140008ef6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x140008efd  call    __delayLoadHelper2
0x140008f02  movdqa  xmm0, [rsp+68h+var_48]
0x140008f08  movdqa  xmm1, [rsp+68h+var_38]
0x140008f0e  movdqa  xmm2, [rsp+68h+var_28]
0x140008f14  movdqa  xmm3, [rsp+68h+var_18]
0x140008f1a  mov     rcx, [rsp+68h+arg_0]
0x140008f1f  mov     rdx, [rsp+68h+arg_8]
0x140008f24  mov     r8, [rsp+68h+arg_10]
0x140008f2c  mov     r9, [rsp+68h+arg_18]
0x140008f34  add     rsp, 68h
0x140008f38  jmp     short $+2
0x140008f3a  jmp     rax
```
