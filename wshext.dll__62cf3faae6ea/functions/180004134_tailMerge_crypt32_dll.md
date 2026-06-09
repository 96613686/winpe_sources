# __tailMerge_crypt32_dll

- ea: `0x180004134`
- end: `0x1800041ad`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800041b3`
- `0x1800041c5`
- `0x1800041d7`
- `0x1800041e9`
- `0x1800041fb`
- `0x180004279`
- `0x18000428b`
- `0x1800042c1`
- `0x1800042d3`
- `0x1800042e5`

## callees

- `0x180002eb0`
- `0x180004134`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004134  mov     [rsp+arg_0], rcx
0x180004139  mov     [rsp+arg_8], rdx
0x18000413e  mov     [rsp+arg_10], r8
0x180004143  mov     [rsp+arg_18], r9
0x180004148  sub     rsp, 68h
0x18000414c  movdqa  [rsp+68h+var_48], xmm0
0x180004152  movdqa  [rsp+68h+var_38], xmm1
0x180004158  movdqa  [rsp+68h+var_28], xmm2
0x18000415e  movdqa  [rsp+68h+var_18], xmm3
0x180004164  mov     rdx, rax
0x180004167  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x18000416e  call    __delayLoadHelper2
0x180004173  movdqa  xmm0, [rsp+68h+var_48]
0x180004179  movdqa  xmm1, [rsp+68h+var_38]
0x18000417f  movdqa  xmm2, [rsp+68h+var_28]
0x180004185  movdqa  xmm3, [rsp+68h+var_18]
0x18000418b  mov     rcx, [rsp+68h+arg_0]
0x180004190  mov     rdx, [rsp+68h+arg_8]
0x180004195  mov     r8, [rsp+68h+arg_10]
0x18000419d  mov     r9, [rsp+68h+arg_18]
0x1800041a5  add     rsp, 68h
0x1800041a9  jmp     short $+2
0x1800041ab  jmp     rax
```
