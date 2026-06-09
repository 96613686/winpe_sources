# __tailMerge_avrt_dll

- ea: `0x1800026c6`
- end: `0x18000273f`
- name: `__tailMerge_avrt_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002745`
- `0x180002757`

## callees

- `0x1800026c6`
- `0x180015830`

## pseudocode

```c
__int64 __fastcall _tailMerge_avrt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_avrt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026c6  mov     [rsp+arg_0], rcx
0x1800026cb  mov     [rsp+arg_8], rdx
0x1800026d0  mov     [rsp+arg_10], r8
0x1800026d5  mov     [rsp+arg_18], r9
0x1800026da  sub     rsp, 68h
0x1800026de  movdqa  [rsp+68h+var_48], xmm0
0x1800026e4  movdqa  [rsp+68h+var_38], xmm1
0x1800026ea  movdqa  [rsp+68h+var_28], xmm2
0x1800026f0  movdqa  [rsp+68h+var_18], xmm3
0x1800026f6  mov     rdx, rax
0x1800026f9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_avrt_dll
0x180002700  call    __delayLoadHelper2
0x180002705  movdqa  xmm0, [rsp+68h+var_48]
0x18000270b  movdqa  xmm1, [rsp+68h+var_38]
0x180002711  movdqa  xmm2, [rsp+68h+var_28]
0x180002717  movdqa  xmm3, [rsp+68h+var_18]
0x18000271d  mov     rcx, [rsp+68h+arg_0]
0x180002722  mov     rdx, [rsp+68h+arg_8]
0x180002727  mov     r8, [rsp+68h+arg_10]
0x18000272f  mov     r9, [rsp+68h+arg_18]
0x180002737  add     rsp, 68h
0x18000273b  jmp     short $+2
0x18000273d  jmp     rax
```
