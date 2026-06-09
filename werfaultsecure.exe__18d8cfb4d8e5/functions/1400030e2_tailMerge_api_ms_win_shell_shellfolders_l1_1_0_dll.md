# __tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll

- ea: `0x1400030e2`
- end: `0x14000315b`
- name: `__tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003161`

## callees

- `0x1400030e2`
- `0x140010620`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_shell_shellfolders_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400030e2  mov     [rsp+arg_0], rcx
0x1400030e7  mov     [rsp+arg_8], rdx
0x1400030ec  mov     [rsp+arg_10], r8
0x1400030f1  mov     [rsp+arg_18], r9
0x1400030f6  sub     rsp, 68h
0x1400030fa  movdqa  [rsp+68h+var_48], xmm0
0x140003100  movdqa  [rsp+68h+var_38], xmm1
0x140003106  movdqa  [rsp+68h+var_28], xmm2
0x14000310c  movdqa  [rsp+68h+var_18], xmm3
0x140003112  mov     rdx, rax
0x140003115  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_shell_shellfolders_l1_1_0_dll
0x14000311c  call    __delayLoadHelper2
0x140003121  movdqa  xmm0, [rsp+68h+var_48]
0x140003127  movdqa  xmm1, [rsp+68h+var_38]
0x14000312d  movdqa  xmm2, [rsp+68h+var_28]
0x140003133  movdqa  xmm3, [rsp+68h+var_18]
0x140003139  mov     rcx, [rsp+68h+arg_0]
0x14000313e  mov     rdx, [rsp+68h+arg_8]
0x140003143  mov     r8, [rsp+68h+arg_10]
0x14000314b  mov     r9, [rsp+68h+arg_18]
0x140003153  add     rsp, 68h
0x140003157  jmp     short $+2
0x140003159  jmp     rax
```
