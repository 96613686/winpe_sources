# __tailMerge_rpcrt4_dll

- ea: `0x1800020e0`
- end: `0x180002159`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000215f`
- `0x180002171`
- `0x180002183`
- `0x180002195`
- `0x1800021a7`
- `0x1800021b9`
- `0x1800021cb`
- `0x1800021dd`
- `0x1800021ef`
- `0x180002201`
- `0x180002213`
- `0x180002225`

## callees

- `0x1800020e0`
- `0x18000ce60`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800020e0  mov     [rsp+arg_0], rcx
0x1800020e5  mov     [rsp+arg_8], rdx
0x1800020ea  mov     [rsp+arg_10], r8
0x1800020ef  mov     [rsp+arg_18], r9
0x1800020f4  sub     rsp, 68h
0x1800020f8  movdqa  [rsp+68h+var_48], xmm0
0x1800020fe  movdqa  [rsp+68h+var_38], xmm1
0x180002104  movdqa  [rsp+68h+var_28], xmm2
0x18000210a  movdqa  [rsp+68h+var_18], xmm3
0x180002110  mov     rdx, rax
0x180002113  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18000211a  call    __delayLoadHelper2
0x18000211f  movdqa  xmm0, [rsp+68h+var_48]
0x180002125  movdqa  xmm1, [rsp+68h+var_38]
0x18000212b  movdqa  xmm2, [rsp+68h+var_28]
0x180002131  movdqa  xmm3, [rsp+68h+var_18]
0x180002137  mov     rcx, [rsp+68h+arg_0]
0x18000213c  mov     rdx, [rsp+68h+arg_8]
0x180002141  mov     r8, [rsp+68h+arg_10]
0x180002149  mov     r9, [rsp+68h+arg_18]
0x180002151  add     rsp, 68h
0x180002155  jmp     short $+2
0x180002157  jmp     rax
```
