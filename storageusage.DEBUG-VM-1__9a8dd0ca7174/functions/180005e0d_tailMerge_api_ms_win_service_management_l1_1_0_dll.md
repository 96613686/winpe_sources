# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x180005e0d`
- end: `0x180005e86`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180005e8c`
- `0x180005f3b`
- `0x180005f4d`

## callees

- `0x180005e0d`
- `0x18002ad80`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005e0d  mov     [rsp+arg_0], rcx
0x180005e12  mov     [rsp+arg_8], rdx
0x180005e17  mov     [rsp+arg_10], r8
0x180005e1c  mov     [rsp+arg_18], r9
0x180005e21  sub     rsp, 68h
0x180005e25  movdqa  [rsp+68h+var_48], xmm0
0x180005e2b  movdqa  [rsp+68h+var_38], xmm1
0x180005e31  movdqa  [rsp+68h+var_28], xmm2
0x180005e37  movdqa  [rsp+68h+var_18], xmm3
0x180005e3d  mov     rdx, rax
0x180005e40  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x180005e47  call    __delayLoadHelper2
0x180005e4c  movdqa  xmm0, [rsp+68h+var_48]
0x180005e52  movdqa  xmm1, [rsp+68h+var_38]
0x180005e58  movdqa  xmm2, [rsp+68h+var_28]
0x180005e5e  movdqa  xmm3, [rsp+68h+var_18]
0x180005e64  mov     rcx, [rsp+68h+arg_0]
0x180005e69  mov     rdx, [rsp+68h+arg_8]
0x180005e6e  mov     r8, [rsp+68h+arg_10]
0x180005e76  mov     r9, [rsp+68h+arg_18]
0x180005e7e  add     rsp, 68h
0x180005e82  jmp     short $+2
0x180005e84  jmp     rax
```
