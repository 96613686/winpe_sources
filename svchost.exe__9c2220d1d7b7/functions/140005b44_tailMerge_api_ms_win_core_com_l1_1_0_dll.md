# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x140005b44`
- end: `0x140005bbd`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005bc3`
- `0x140005c84`
- `0x140005c96`
- `0x140005ca8`
- `0x140005cba`

## callees

- `0x140002100`
- `0x140005b44`

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
0x140005b44  mov     [rsp+arg_0], rcx
0x140005b49  mov     [rsp+arg_8], rdx
0x140005b4e  mov     [rsp+arg_10], r8
0x140005b53  mov     [rsp+arg_18], r9
0x140005b58  sub     rsp, 68h
0x140005b5c  movdqa  [rsp+68h+var_48], xmm0
0x140005b62  movdqa  [rsp+68h+var_38], xmm1
0x140005b68  movdqa  [rsp+68h+var_28], xmm2
0x140005b6e  movdqa  [rsp+68h+var_18], xmm3
0x140005b74  mov     rdx, rax
0x140005b77  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x140005b7e  call    __delayLoadHelper2
0x140005b83  movdqa  xmm0, [rsp+68h+var_48]
0x140005b89  movdqa  xmm1, [rsp+68h+var_38]
0x140005b8f  movdqa  xmm2, [rsp+68h+var_28]
0x140005b95  movdqa  xmm3, [rsp+68h+var_18]
0x140005b9b  mov     rcx, [rsp+68h+arg_0]
0x140005ba0  mov     rdx, [rsp+68h+arg_8]
0x140005ba5  mov     r8, [rsp+68h+arg_10]
0x140005bad  mov     r9, [rsp+68h+arg_18]
0x140005bb5  add     rsp, 68h
0x140005bb9  jmp     short $+2
0x140005bbb  jmp     rax
```
