# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x140010716`
- end: `0x14001078f`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010795`
- `0x1400107a7`
- `0x1400107b9`
- `0x1400107d7`
- `0x140010801`
- `0x14001081f`
- `0x140010831`
- `0x140010843`

## callees

- `0x140010716`
- `0x1400604d0`

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
0x140010716  mov     [rsp+arg_0], rcx
0x14001071b  mov     [rsp+arg_8], rdx
0x140010720  mov     [rsp+arg_10], r8
0x140010725  mov     [rsp+arg_18], r9
0x14001072a  sub     rsp, 68h
0x14001072e  movdqa  [rsp+68h+var_48], xmm0
0x140010734  movdqa  [rsp+68h+var_38], xmm1
0x14001073a  movdqa  [rsp+68h+var_28], xmm2
0x140010740  movdqa  [rsp+68h+var_18], xmm3
0x140010746  mov     rdx, rax
0x140010749  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x140010750  call    __delayLoadHelper2
0x140010755  movdqa  xmm0, [rsp+68h+var_48]
0x14001075b  movdqa  xmm1, [rsp+68h+var_38]
0x140010761  movdqa  xmm2, [rsp+68h+var_28]
0x140010767  movdqa  xmm3, [rsp+68h+var_18]
0x14001076d  mov     rcx, [rsp+68h+arg_0]
0x140010772  mov     rdx, [rsp+68h+arg_8]
0x140010777  mov     r8, [rsp+68h+arg_10]
0x14001077f  mov     r9, [rsp+68h+arg_18]
0x140010787  add     rsp, 68h
0x14001078b  jmp     short $+2
0x14001078d  jmp     rax
```
