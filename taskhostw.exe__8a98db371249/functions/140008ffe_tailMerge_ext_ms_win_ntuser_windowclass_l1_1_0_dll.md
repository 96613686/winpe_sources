# __tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll

- ea: `0x140008ffe`
- end: `0x140009077`
- name: `__tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000907d`
- `0x14000908f`

## callees

- `0x140006020`
- `0x140008ffe`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140008ffe  mov     [rsp+arg_0], rcx
0x140009003  mov     [rsp+arg_8], rdx
0x140009008  mov     [rsp+arg_10], r8
0x14000900d  mov     [rsp+arg_18], r9
0x140009012  sub     rsp, 68h
0x140009016  movdqa  [rsp+68h+var_48], xmm0
0x14000901c  movdqa  [rsp+68h+var_38], xmm1
0x140009022  movdqa  [rsp+68h+var_28], xmm2
0x140009028  movdqa  [rsp+68h+var_18], xmm3
0x14000902e  mov     rdx, rax
0x140009031  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll
0x140009038  call    __delayLoadHelper2
0x14000903d  movdqa  xmm0, [rsp+68h+var_48]
0x140009043  movdqa  xmm1, [rsp+68h+var_38]
0x140009049  movdqa  xmm2, [rsp+68h+var_28]
0x14000904f  movdqa  xmm3, [rsp+68h+var_18]
0x140009055  mov     rcx, [rsp+68h+arg_0]
0x14000905a  mov     rdx, [rsp+68h+arg_8]
0x14000905f  mov     r8, [rsp+68h+arg_10]
0x140009067  mov     r9, [rsp+68h+arg_18]
0x14000906f  add     rsp, 68h
0x140009073  jmp     short $+2
0x140009075  jmp     rax
```
