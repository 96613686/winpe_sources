# __tailMerge_api_ms_win_power_base_l1_1_0_dll

- ea: `0x180002e70`
- end: `0x180002ee9`
- name: `__tailMerge_api_ms_win_power_base_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002eef`

## callees

- `0x180002e70`
- `0x1800095f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_power_base_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_power_base_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002e70  mov     [rsp+arg_0], rcx
0x180002e75  mov     [rsp+arg_8], rdx
0x180002e7a  mov     [rsp+arg_10], r8
0x180002e7f  mov     [rsp+arg_18], r9
0x180002e84  sub     rsp, 68h
0x180002e88  movdqa  [rsp+68h+var_48], xmm0
0x180002e8e  movdqa  [rsp+68h+var_38], xmm1
0x180002e94  movdqa  [rsp+68h+var_28], xmm2
0x180002e9a  movdqa  [rsp+68h+var_18], xmm3
0x180002ea0  mov     rdx, rax
0x180002ea3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_power_base_l1_1_0_dll
0x180002eaa  call    __delayLoadHelper2
0x180002eaf  movdqa  xmm0, [rsp+68h+var_48]
0x180002eb5  movdqa  xmm1, [rsp+68h+var_38]
0x180002ebb  movdqa  xmm2, [rsp+68h+var_28]
0x180002ec1  movdqa  xmm3, [rsp+68h+var_18]
0x180002ec7  mov     rcx, [rsp+68h+arg_0]
0x180002ecc  mov     rdx, [rsp+68h+arg_8]
0x180002ed1  mov     r8, [rsp+68h+arg_10]
0x180002ed9  mov     r9, [rsp+68h+arg_18]
0x180002ee1  add     rsp, 68h
0x180002ee5  jmp     short $+2
0x180002ee7  jmp     rax
```
