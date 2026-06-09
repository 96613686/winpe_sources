# __tailMerge_ext_ms_win_resourcemanager_limits_l1_1_0_dll

- ea: `0x14000593a`
- end: `0x1400059b3`
- name: `__tailMerge_ext_ms_win_resourcemanager_limits_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400059b9`

## callees

- `0x140001ff0`
- `0x14000593a`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_resourcemanager_limits_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_resourcemanager_limits_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000593a  mov     [rsp+arg_0], rcx
0x14000593f  mov     [rsp+arg_8], rdx
0x140005944  mov     [rsp+arg_10], r8
0x140005949  mov     [rsp+arg_18], r9
0x14000594e  sub     rsp, 68h
0x140005952  movdqa  [rsp+68h+var_48], xmm0
0x140005958  movdqa  [rsp+68h+var_38], xmm1
0x14000595e  movdqa  [rsp+68h+var_28], xmm2
0x140005964  movdqa  [rsp+68h+var_18], xmm3
0x14000596a  mov     rdx, rax
0x14000596d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_resourcemanager_limits_l1_1_0_dll
0x140005974  call    __delayLoadHelper2
0x140005979  movdqa  xmm0, [rsp+68h+var_48]
0x14000597f  movdqa  xmm1, [rsp+68h+var_38]
0x140005985  movdqa  xmm2, [rsp+68h+var_28]
0x14000598b  movdqa  xmm3, [rsp+68h+var_18]
0x140005991  mov     rcx, [rsp+68h+arg_0]
0x140005996  mov     rdx, [rsp+68h+arg_8]
0x14000599b  mov     r8, [rsp+68h+arg_10]
0x1400059a3  mov     r9, [rsp+68h+arg_18]
0x1400059ab  add     rsp, 68h
0x1400059af  jmp     short $+2
0x1400059b1  jmp     rax
```
