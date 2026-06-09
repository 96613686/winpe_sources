# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x140008a92`
- end: `0x140008b0b`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008b11`
- `0x140008ba1`
- `0x140008bd7`
- `0x140008c86`
- `0x140008c98`
- `0x140008caa`
- `0x140008cbc`

## callees

- `0x140006020`
- `0x140008a92`

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
0x140008a92  mov     [rsp+arg_0], rcx
0x140008a97  mov     [rsp+arg_8], rdx
0x140008a9c  mov     [rsp+arg_10], r8
0x140008aa1  mov     [rsp+arg_18], r9
0x140008aa6  sub     rsp, 68h
0x140008aaa  movdqa  [rsp+68h+var_48], xmm0
0x140008ab0  movdqa  [rsp+68h+var_38], xmm1
0x140008ab6  movdqa  [rsp+68h+var_28], xmm2
0x140008abc  movdqa  [rsp+68h+var_18], xmm3
0x140008ac2  mov     rdx, rax
0x140008ac5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x140008acc  call    __delayLoadHelper2
0x140008ad1  movdqa  xmm0, [rsp+68h+var_48]
0x140008ad7  movdqa  xmm1, [rsp+68h+var_38]
0x140008add  movdqa  xmm2, [rsp+68h+var_28]
0x140008ae3  movdqa  xmm3, [rsp+68h+var_18]
0x140008ae9  mov     rcx, [rsp+68h+arg_0]
0x140008aee  mov     rdx, [rsp+68h+arg_8]
0x140008af3  mov     r8, [rsp+68h+arg_10]
0x140008afb  mov     r9, [rsp+68h+arg_18]
0x140008b03  add     rsp, 68h
0x140008b07  jmp     short $+2
0x140008b09  jmp     rax
```
