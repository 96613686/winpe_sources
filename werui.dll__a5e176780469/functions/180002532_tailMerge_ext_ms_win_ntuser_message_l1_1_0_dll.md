# __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll

- ea: `0x180002532`
- end: `0x1800025ab`
- name: `__tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025b1`
- `0x180002618`
- `0x18000262a`
- `0x18000263c`
- `0x18000264e`
- `0x180002660`
- `0x180002672`

## callees

- `0x180002532`
- `0x180016ac0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002532  mov     [rsp+arg_0], rcx
0x180002537  mov     [rsp+arg_8], rdx
0x18000253c  mov     [rsp+arg_10], r8
0x180002541  mov     [rsp+arg_18], r9
0x180002546  sub     rsp, 68h
0x18000254a  movdqa  [rsp+68h+var_48], xmm0
0x180002550  movdqa  [rsp+68h+var_38], xmm1
0x180002556  movdqa  [rsp+68h+var_28], xmm2
0x18000255c  movdqa  [rsp+68h+var_18], xmm3
0x180002562  mov     rdx, rax
0x180002565  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll
0x18000256c  call    __delayLoadHelper2
0x180002571  movdqa  xmm0, [rsp+68h+var_48]
0x180002577  movdqa  xmm1, [rsp+68h+var_38]
0x18000257d  movdqa  xmm2, [rsp+68h+var_28]
0x180002583  movdqa  xmm3, [rsp+68h+var_18]
0x180002589  mov     rcx, [rsp+68h+arg_0]
0x18000258e  mov     rdx, [rsp+68h+arg_8]
0x180002593  mov     r8, [rsp+68h+arg_10]
0x18000259b  mov     r9, [rsp+68h+arg_18]
0x1800025a3  add     rsp, 68h
0x1800025a7  jmp     short $+2
0x1800025a9  jmp     rax
```
