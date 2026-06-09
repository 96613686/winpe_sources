# __tailMerge_ext_ms_win_shell_shell32_l1_2_0_dll

- ea: `0x140003022`
- end: `0x14000309b`
- name: `__tailMerge_ext_ms_win_shell_shell32_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400030a1`

## callees

- `0x140003022`
- `0x1400171b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_shell_shell32_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_shell32_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140003022  mov     [rsp+arg_0], rcx
0x140003027  mov     [rsp+arg_8], rdx
0x14000302c  mov     [rsp+arg_10], r8
0x140003031  mov     [rsp+arg_18], r9
0x140003036  sub     rsp, 68h
0x14000303a  movdqa  [rsp+68h+var_48], xmm0
0x140003040  movdqa  [rsp+68h+var_38], xmm1
0x140003046  movdqa  [rsp+68h+var_28], xmm2
0x14000304c  movdqa  [rsp+68h+var_18], xmm3
0x140003052  mov     rdx, rax
0x140003055  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_shell32_l1_2_0_dll
0x14000305c  call    __delayLoadHelper2
0x140003061  movdqa  xmm0, [rsp+68h+var_48]
0x140003067  movdqa  xmm1, [rsp+68h+var_38]
0x14000306d  movdqa  xmm2, [rsp+68h+var_28]
0x140003073  movdqa  xmm3, [rsp+68h+var_18]
0x140003079  mov     rcx, [rsp+68h+arg_0]
0x14000307e  mov     rdx, [rsp+68h+arg_8]
0x140003083  mov     r8, [rsp+68h+arg_10]
0x14000308b  mov     r9, [rsp+68h+arg_18]
0x140003093  add     rsp, 68h
0x140003097  jmp     short $+2
0x140003099  jmp     rax
```
