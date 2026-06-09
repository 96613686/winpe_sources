# __tailMerge_onex_dll

- ea: `0x180002559`
- end: `0x1800025d2`
- name: `__tailMerge_onex_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025d8`
- `0x1800025ea`
- `0x1800025fc`
- `0x18000260e`

## callees

- `0x180002559`
- `0x18001be40`

## pseudocode

```c
__int64 __fastcall _tailMerge_onex_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_onex_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002559  mov     [rsp+arg_0], rcx
0x18000255e  mov     [rsp+arg_8], rdx
0x180002563  mov     [rsp+arg_10], r8
0x180002568  mov     [rsp+arg_18], r9
0x18000256d  sub     rsp, 68h
0x180002571  movdqa  [rsp+68h+var_48], xmm0
0x180002577  movdqa  [rsp+68h+var_38], xmm1
0x18000257d  movdqa  [rsp+68h+var_28], xmm2
0x180002583  movdqa  [rsp+68h+var_18], xmm3
0x180002589  mov     rdx, rax
0x18000258c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_onex_dll
0x180002593  call    __delayLoadHelper2
0x180002598  movdqa  xmm0, [rsp+68h+var_48]
0x18000259e  movdqa  xmm1, [rsp+68h+var_38]
0x1800025a4  movdqa  xmm2, [rsp+68h+var_28]
0x1800025aa  movdqa  xmm3, [rsp+68h+var_18]
0x1800025b0  mov     rcx, [rsp+68h+arg_0]
0x1800025b5  mov     rdx, [rsp+68h+arg_8]
0x1800025ba  mov     r8, [rsp+68h+arg_10]
0x1800025c2  mov     r9, [rsp+68h+arg_18]
0x1800025ca  add     rsp, 68h
0x1800025ce  jmp     short $+2
0x1800025d0  jmp     rax
```
