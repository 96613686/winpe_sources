# __tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll

- ea: `0x1400025ca`
- end: `0x140002643`
- name: `__tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002649`
- `0x14000265b`
- `0x1400026f8`
- `0x14000271c`

## callees

- `0x1400025ca`
- `0x14000b0a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400025ca  mov     [rsp+arg_0], rcx
0x1400025cf  mov     [rsp+arg_8], rdx
0x1400025d4  mov     [rsp+arg_10], r8
0x1400025d9  mov     [rsp+arg_18], r9
0x1400025de  sub     rsp, 68h
0x1400025e2  movdqa  [rsp+68h+var_48], xmm0
0x1400025e8  movdqa  [rsp+68h+var_38], xmm1
0x1400025ee  movdqa  [rsp+68h+var_28], xmm2
0x1400025f4  movdqa  [rsp+68h+var_18], xmm3
0x1400025fa  mov     rdx, rax
0x1400025fd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll
0x140002604  call    __delayLoadHelper2
0x140002609  movdqa  xmm0, [rsp+68h+var_48]
0x14000260f  movdqa  xmm1, [rsp+68h+var_38]
0x140002615  movdqa  xmm2, [rsp+68h+var_28]
0x14000261b  movdqa  xmm3, [rsp+68h+var_18]
0x140002621  mov     rcx, [rsp+68h+arg_0]
0x140002626  mov     rdx, [rsp+68h+arg_8]
0x14000262b  mov     r8, [rsp+68h+arg_10]
0x140002633  mov     r9, [rsp+68h+arg_18]
0x14000263b  add     rsp, 68h
0x14000263f  jmp     short $+2
0x140002641  jmp     rax
```
