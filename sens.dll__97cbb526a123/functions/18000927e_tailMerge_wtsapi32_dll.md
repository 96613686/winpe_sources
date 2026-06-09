# __tailMerge_wtsapi32_dll

- ea: `0x18000927e`
- end: `0x1800092f7`
- name: `__tailMerge_wtsapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800092fd`

## callees

- `0x180006a50`
- `0x18000927e`

## pseudocode

```c
__int64 __fastcall _tailMerge_wtsapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wtsapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000927e  mov     [rsp+arg_0], rcx
0x180009283  mov     [rsp+arg_8], rdx
0x180009288  mov     [rsp+arg_10], r8
0x18000928d  mov     [rsp+arg_18], r9
0x180009292  sub     rsp, 68h
0x180009296  movdqa  [rsp+68h+var_48], xmm0
0x18000929c  movdqa  [rsp+68h+var_38], xmm1
0x1800092a2  movdqa  [rsp+68h+var_28], xmm2
0x1800092a8  movdqa  [rsp+68h+var_18], xmm3
0x1800092ae  mov     rdx, rax
0x1800092b1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wtsapi32_dll
0x1800092b8  call    __delayLoadHelper2
0x1800092bd  movdqa  xmm0, [rsp+68h+var_48]
0x1800092c3  movdqa  xmm1, [rsp+68h+var_38]
0x1800092c9  movdqa  xmm2, [rsp+68h+var_28]
0x1800092cf  movdqa  xmm3, [rsp+68h+var_18]
0x1800092d5  mov     rcx, [rsp+68h+arg_0]
0x1800092da  mov     rdx, [rsp+68h+arg_8]
0x1800092df  mov     r8, [rsp+68h+arg_10]
0x1800092e7  mov     r9, [rsp+68h+arg_18]
0x1800092ef  add     rsp, 68h
0x1800092f3  jmp     short $+2
0x1800092f5  jmp     rax
```
