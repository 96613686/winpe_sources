# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180002d36`
- end: `0x180002daf`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002db5`
- `0x180002dc7`
- `0x180002e64`
- `0x180002f25`

## callees

- `0x180002d36`
- `0x1800095f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002d36  mov     [rsp+arg_0], rcx
0x180002d3b  mov     [rsp+arg_8], rdx
0x180002d40  mov     [rsp+arg_10], r8
0x180002d45  mov     [rsp+arg_18], r9
0x180002d4a  sub     rsp, 68h
0x180002d4e  movdqa  [rsp+68h+var_48], xmm0
0x180002d54  movdqa  [rsp+68h+var_38], xmm1
0x180002d5a  movdqa  [rsp+68h+var_28], xmm2
0x180002d60  movdqa  [rsp+68h+var_18], xmm3
0x180002d66  mov     rdx, rax
0x180002d69  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180002d70  call    __delayLoadHelper2
0x180002d75  movdqa  xmm0, [rsp+68h+var_48]
0x180002d7b  movdqa  xmm1, [rsp+68h+var_38]
0x180002d81  movdqa  xmm2, [rsp+68h+var_28]
0x180002d87  movdqa  xmm3, [rsp+68h+var_18]
0x180002d8d  mov     rcx, [rsp+68h+arg_0]
0x180002d92  mov     rdx, [rsp+68h+arg_8]
0x180002d97  mov     r8, [rsp+68h+arg_10]
0x180002d9f  mov     r9, [rsp+68h+arg_18]
0x180002da7  add     rsp, 68h
0x180002dab  jmp     short $+2
0x180002dad  jmp     rax
```
