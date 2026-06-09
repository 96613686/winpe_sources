# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180002c5c`
- end: `0x180002cd5`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002cdb`
- `0x180002cff`
- `0x180002d11`
- `0x180002d23`

## callees

- `0x180001850`
- `0x180002c5c`

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
0x180002c5c  mov     [rsp+arg_0], rcx
0x180002c61  mov     [rsp+arg_8], rdx
0x180002c66  mov     [rsp+arg_10], r8
0x180002c6b  mov     [rsp+arg_18], r9
0x180002c70  sub     rsp, 68h
0x180002c74  movdqa  [rsp+68h+var_48], xmm0
0x180002c7a  movdqa  [rsp+68h+var_38], xmm1
0x180002c80  movdqa  [rsp+68h+var_28], xmm2
0x180002c86  movdqa  [rsp+68h+var_18], xmm3
0x180002c8c  mov     rdx, rax
0x180002c8f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180002c96  call    __delayLoadHelper2
0x180002c9b  movdqa  xmm0, [rsp+68h+var_48]
0x180002ca1  movdqa  xmm1, [rsp+68h+var_38]
0x180002ca7  movdqa  xmm2, [rsp+68h+var_28]
0x180002cad  movdqa  xmm3, [rsp+68h+var_18]
0x180002cb3  mov     rcx, [rsp+68h+arg_0]
0x180002cb8  mov     rdx, [rsp+68h+arg_8]
0x180002cbd  mov     r8, [rsp+68h+arg_10]
0x180002cc5  mov     r9, [rsp+68h+arg_18]
0x180002ccd  add     rsp, 68h
0x180002cd1  jmp     short $+2
0x180002cd3  jmp     rax
```
