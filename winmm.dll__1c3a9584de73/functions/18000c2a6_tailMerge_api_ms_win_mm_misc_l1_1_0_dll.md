# __tailMerge_api_ms_win_mm_misc_l1_1_0_dll

- ea: `0x18000c2a6`
- end: `0x18000c31f`
- name: `__tailMerge_api_ms_win_mm_misc_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c325`
- `0x18000c337`
- `0x18000c349`
- `0x18000c35b`
- `0x18000c36d`
- `0x18000c37f`
- `0x18000c391`
- `0x18000c3a3`
- `0x18000c3b5`
- `0x18000c3c7`
- `0x18000c3d9`
- `0x18000c3eb`
- `0x18000c3fd`
- `0x18000c40f`
- `0x18000c421`
- `0x18000c433`
- `0x18000c445`
- `0x18000c457`
- `0x18000c469`
- `0x18000c47b`
- `0x18000c48d`
- `0x18000c49f`

## callees

- `0x180009370`
- `0x18000c2a6`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_mm_misc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_mm_misc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c2a6  mov     [rsp+arg_0], rcx
0x18000c2ab  mov     [rsp+arg_8], rdx
0x18000c2b0  mov     [rsp+arg_10], r8
0x18000c2b5  mov     [rsp+arg_18], r9
0x18000c2ba  sub     rsp, 68h
0x18000c2be  movdqa  [rsp+68h+var_48], xmm0
0x18000c2c4  movdqa  [rsp+68h+var_38], xmm1
0x18000c2ca  movdqa  [rsp+68h+var_28], xmm2
0x18000c2d0  movdqa  [rsp+68h+var_18], xmm3
0x18000c2d6  mov     rdx, rax
0x18000c2d9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_mm_misc_l1_1_0_dll
0x18000c2e0  call    __delayLoadHelper2
0x18000c2e5  movdqa  xmm0, [rsp+68h+var_48]
0x18000c2eb  movdqa  xmm1, [rsp+68h+var_38]
0x18000c2f1  movdqa  xmm2, [rsp+68h+var_28]
0x18000c2f7  movdqa  xmm3, [rsp+68h+var_18]
0x18000c2fd  mov     rcx, [rsp+68h+arg_0]
0x18000c302  mov     rdx, [rsp+68h+arg_8]
0x18000c307  mov     r8, [rsp+68h+arg_10]
0x18000c30f  mov     r9, [rsp+68h+arg_18]
0x18000c317  add     rsp, 68h
0x18000c31b  jmp     short $+2
0x18000c31d  jmp     rax
```
