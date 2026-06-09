# __tailMerge_api_ms_win_eventlog_legacy_l1_1_0_dll

- ea: `0x180004506`
- end: `0x18000457f`
- name: `__tailMerge_api_ms_win_eventlog_legacy_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004585`
- `0x180004597`
- `0x1800045a9`
- `0x1800045bb`
- `0x1800045cd`

## callees

- `0x180004506`
- `0x18000a6a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_eventlog_legacy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventlog_legacy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004506  mov     [rsp+arg_0], rcx
0x18000450b  mov     [rsp+arg_8], rdx
0x180004510  mov     [rsp+arg_10], r8
0x180004515  mov     [rsp+arg_18], r9
0x18000451a  sub     rsp, 68h
0x18000451e  movdqa  [rsp+68h+var_48], xmm0
0x180004524  movdqa  [rsp+68h+var_38], xmm1
0x18000452a  movdqa  [rsp+68h+var_28], xmm2
0x180004530  movdqa  [rsp+68h+var_18], xmm3
0x180004536  mov     rdx, rax
0x180004539  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventlog_legacy_l1_1_0_dll
0x180004540  call    __delayLoadHelper2
0x180004545  movdqa  xmm0, [rsp+68h+var_48]
0x18000454b  movdqa  xmm1, [rsp+68h+var_38]
0x180004551  movdqa  xmm2, [rsp+68h+var_28]
0x180004557  movdqa  xmm3, [rsp+68h+var_18]
0x18000455d  mov     rcx, [rsp+68h+arg_0]
0x180004562  mov     rdx, [rsp+68h+arg_8]
0x180004567  mov     r8, [rsp+68h+arg_10]
0x18000456f  mov     r9, [rsp+68h+arg_18]
0x180004577  add     rsp, 68h
0x18000457b  jmp     short $+2
0x18000457d  jmp     rax
```
