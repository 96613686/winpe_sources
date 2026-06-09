# __tailMerge_api_ms_win_core_file_l1_1_0_dll

- ea: `0x18000ea17`
- end: `0x18000ea90`
- name: `__tailMerge_api_ms_win_core_file_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ea96`
- `0x1800150ba`
- `0x1800150cc`
- `0x1800150de`
- `0x1800152ff`

## callees

- `0x18000ea17`
- `0x180014c80`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_file_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_file_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ea17  mov     [rsp+arg_0], rcx
0x18000ea1c  mov     [rsp+arg_8], rdx
0x18000ea21  mov     [rsp+arg_10], r8
0x18000ea26  mov     [rsp+arg_18], r9
0x18000ea2b  sub     rsp, 68h
0x18000ea2f  movdqa  [rsp+68h+var_48], xmm0
0x18000ea35  movdqa  [rsp+68h+var_38], xmm1
0x18000ea3b  movdqa  [rsp+68h+var_28], xmm2
0x18000ea41  movdqa  [rsp+68h+var_18], xmm3
0x18000ea47  mov     rdx, rax
0x18000ea4a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_file_l1_1_0_dll
0x18000ea51  call    __delayLoadHelper2
0x18000ea56  movdqa  xmm0, [rsp+68h+var_48]
0x18000ea5c  movdqa  xmm1, [rsp+68h+var_38]
0x18000ea62  movdqa  xmm2, [rsp+68h+var_28]
0x18000ea68  movdqa  xmm3, [rsp+68h+var_18]
0x18000ea6e  mov     rcx, [rsp+68h+arg_0]
0x18000ea73  mov     rdx, [rsp+68h+arg_8]
0x18000ea78  mov     r8, [rsp+68h+arg_10]
0x18000ea80  mov     r9, [rsp+68h+arg_18]
0x18000ea88  add     rsp, 68h
0x18000ea8c  jmp     short $+2
0x18000ea8e  jmp     rax
```
