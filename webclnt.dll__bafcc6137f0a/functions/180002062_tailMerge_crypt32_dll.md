# __tailMerge_crypt32_dll

- ea: `0x180002062`
- end: `0x1800020db`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020e1`
- `0x1800020f3`
- `0x180002105`
- `0x180002117`
- `0x180002129`
- `0x18000213b`

## callees

- `0x180002062`
- `0x18002ce10`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002062  mov     [rsp+arg_0], rcx
0x180002067  mov     [rsp+arg_8], rdx
0x18000206c  mov     [rsp+arg_10], r8
0x180002071  mov     [rsp+arg_18], r9
0x180002076  sub     rsp, 68h
0x18000207a  movdqa  [rsp+68h+var_48], xmm0
0x180002080  movdqa  [rsp+68h+var_38], xmm1
0x180002086  movdqa  [rsp+68h+var_28], xmm2
0x18000208c  movdqa  [rsp+68h+var_18], xmm3
0x180002092  mov     rdx, rax
0x180002095  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x18000209c  call    __delayLoadHelper2
0x1800020a1  movdqa  xmm0, [rsp+68h+var_48]
0x1800020a7  movdqa  xmm1, [rsp+68h+var_38]
0x1800020ad  movdqa  xmm2, [rsp+68h+var_28]
0x1800020b3  movdqa  xmm3, [rsp+68h+var_18]
0x1800020b9  mov     rcx, [rsp+68h+arg_0]
0x1800020be  mov     rdx, [rsp+68h+arg_8]
0x1800020c3  mov     r8, [rsp+68h+arg_10]
0x1800020cb  mov     r9, [rsp+68h+arg_18]
0x1800020d3  add     rsp, 68h
0x1800020d7  jmp     short $+2
0x1800020d9  jmp     rax
```
