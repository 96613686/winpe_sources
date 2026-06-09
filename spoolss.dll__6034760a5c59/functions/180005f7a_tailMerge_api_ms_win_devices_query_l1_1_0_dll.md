# __tailMerge_api_ms_win_devices_query_l1_1_0_dll

- ea: `0x180005f7a`
- end: `0x180005ff3`
- name: `__tailMerge_api_ms_win_devices_query_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005ff9`
- `0x18000600b`
- `0x18000601d`

## callees

- `0x180005f7a`
- `0x180014d80`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_devices_query_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_query_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005f7a  mov     [rsp+arg_0], rcx
0x180005f7f  mov     [rsp+arg_8], rdx
0x180005f84  mov     [rsp+arg_10], r8
0x180005f89  mov     [rsp+arg_18], r9
0x180005f8e  sub     rsp, 68h
0x180005f92  movdqa  [rsp+68h+var_48], xmm0
0x180005f98  movdqa  [rsp+68h+var_38], xmm1
0x180005f9e  movdqa  [rsp+68h+var_28], xmm2
0x180005fa4  movdqa  [rsp+68h+var_18], xmm3
0x180005faa  mov     rdx, rax
0x180005fad  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_query_l1_1_0_dll
0x180005fb4  call    __delayLoadHelper2
0x180005fb9  movdqa  xmm0, [rsp+68h+var_48]
0x180005fbf  movdqa  xmm1, [rsp+68h+var_38]
0x180005fc5  movdqa  xmm2, [rsp+68h+var_28]
0x180005fcb  movdqa  xmm3, [rsp+68h+var_18]
0x180005fd1  mov     rcx, [rsp+68h+arg_0]
0x180005fd6  mov     rdx, [rsp+68h+arg_8]
0x180005fdb  mov     r8, [rsp+68h+arg_10]
0x180005fe3  mov     r9, [rsp+68h+arg_18]
0x180005feb  add     rsp, 68h
0x180005fef  jmp     short $+2
0x180005ff1  jmp     rax
```
