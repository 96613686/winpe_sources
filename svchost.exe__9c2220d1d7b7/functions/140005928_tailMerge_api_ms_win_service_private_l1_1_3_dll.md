# __tailMerge_api_ms_win_service_private_l1_1_3_dll

- ea: `0x140005928`
- end: `0x1400059a1`
- name: `__tailMerge_api_ms_win_service_private_l1_1_3_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1400059a7`

## callees

- `0x140002100`
- `0x140005928`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_private_l1_1_3_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_3_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140005928  mov     [rsp+arg_0], rcx
0x14000592d  mov     [rsp+arg_8], rdx
0x140005932  mov     [rsp+arg_10], r8
0x140005937  mov     [rsp+arg_18], r9
0x14000593c  sub     rsp, 68h
0x140005940  movdqa  [rsp+68h+var_48], xmm0
0x140005946  movdqa  [rsp+68h+var_38], xmm1
0x14000594c  movdqa  [rsp+68h+var_28], xmm2
0x140005952  movdqa  [rsp+68h+var_18], xmm3
0x140005958  mov     rdx, rax
0x14000595b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_3_dll
0x140005962  call    __delayLoadHelper2
0x140005967  movdqa  xmm0, [rsp+68h+var_48]
0x14000596d  movdqa  xmm1, [rsp+68h+var_38]
0x140005973  movdqa  xmm2, [rsp+68h+var_28]
0x140005979  movdqa  xmm3, [rsp+68h+var_18]
0x14000597f  mov     rcx, [rsp+68h+arg_0]
0x140005984  mov     rdx, [rsp+68h+arg_8]
0x140005989  mov     r8, [rsp+68h+arg_10]
0x140005991  mov     r9, [rsp+68h+arg_18]
0x140005999  add     rsp, 68h
0x14000599d  jmp     short $+2
0x14000599f  jmp     rax
```
