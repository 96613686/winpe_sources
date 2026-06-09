# __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll

- ea: `0x14000909b`
- end: `0x140009114`
- name: `__tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000911a`

## callees

- `0x140006020`
- `0x14000909b`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000909b  mov     [rsp+arg_0], rcx
0x1400090a0  mov     [rsp+arg_8], rdx
0x1400090a5  mov     [rsp+arg_10], r8
0x1400090aa  mov     [rsp+arg_18], r9
0x1400090af  sub     rsp, 68h
0x1400090b3  movdqa  [rsp+68h+var_48], xmm0
0x1400090b9  movdqa  [rsp+68h+var_38], xmm1
0x1400090bf  movdqa  [rsp+68h+var_28], xmm2
0x1400090c5  movdqa  [rsp+68h+var_18], xmm3
0x1400090cb  mov     rdx, rax
0x1400090ce  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_l1_1_0_dll
0x1400090d5  call    __delayLoadHelper2
0x1400090da  movdqa  xmm0, [rsp+68h+var_48]
0x1400090e0  movdqa  xmm1, [rsp+68h+var_38]
0x1400090e6  movdqa  xmm2, [rsp+68h+var_28]
0x1400090ec  movdqa  xmm3, [rsp+68h+var_18]
0x1400090f2  mov     rcx, [rsp+68h+arg_0]
0x1400090f7  mov     rdx, [rsp+68h+arg_8]
0x1400090fc  mov     r8, [rsp+68h+arg_10]
0x140009104  mov     r9, [rsp+68h+arg_18]
0x14000910c  add     rsp, 68h
0x140009110  jmp     short $+2
0x140009112  jmp     rax
```
