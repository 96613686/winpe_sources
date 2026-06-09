# __tailMerge_winsta_dll

- ea: `0x18000804d`
- end: `0x1800080c6`
- name: `__tailMerge_winsta_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800080cc`

## callees

- `0x1800063c0`
- `0x18000804d`

## pseudocode

```c
__int64 __fastcall _tailMerge_winsta_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_winsta_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000804d  mov     [rsp+arg_0], rcx
0x180008052  mov     [rsp+arg_8], rdx
0x180008057  mov     [rsp+arg_10], r8
0x18000805c  mov     [rsp+arg_18], r9
0x180008061  sub     rsp, 68h
0x180008065  movdqa  [rsp+68h+var_48], xmm0
0x18000806b  movdqa  [rsp+68h+var_38], xmm1
0x180008071  movdqa  [rsp+68h+var_28], xmm2
0x180008077  movdqa  [rsp+68h+var_18], xmm3
0x18000807d  mov     rdx, rax
0x180008080  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winsta_dll
0x180008087  call    __delayLoadHelper2
0x18000808c  movdqa  xmm0, [rsp+68h+var_48]
0x180008092  movdqa  xmm1, [rsp+68h+var_38]
0x180008098  movdqa  xmm2, [rsp+68h+var_28]
0x18000809e  movdqa  xmm3, [rsp+68h+var_18]
0x1800080a4  mov     rcx, [rsp+68h+arg_0]
0x1800080a9  mov     rdx, [rsp+68h+arg_8]
0x1800080ae  mov     r8, [rsp+68h+arg_10]
0x1800080b6  mov     r9, [rsp+68h+arg_18]
0x1800080be  add     rsp, 68h
0x1800080c2  jmp     short $+2
0x1800080c4  jmp     rax
```
