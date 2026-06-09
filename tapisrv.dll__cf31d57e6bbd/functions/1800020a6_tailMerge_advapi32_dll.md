# __tailMerge_advapi32_dll

- ea: `0x1800020a6`
- end: `0x18000211f`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `33`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002125`
- `0x180002137`
- `0x180002149`
- `0x18000215b`
- `0x18000216d`
- `0x18000217f`
- `0x180002191`
- `0x1800021a3`
- `0x1800021b5`
- `0x1800021c7`
- `0x1800021d9`
- `0x1800021eb`
- `0x1800021fd`
- `0x18000220f`
- `0x180002221`
- `0x180002233`
- `0x180002245`
- `0x180002257`
- `0x180002269`
- `0x18000227b`
- `0x18000228d`
- `0x18000229f`
- `0x1800022b1`
- `0x1800022c3`
- `0x1800022d5`
- `0x1800022e7`
- `0x1800022f9`
- `0x18000230b`
- `0x18000231d`
- `0x18000232f`
- `0x180002341`
- `0x180002353`
- `0x180002871`

## callees

- `0x1800020a6`
- `0x18003f9c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800020a6  mov     [rsp+arg_0], rcx
0x1800020ab  mov     [rsp+arg_8], rdx
0x1800020b0  mov     [rsp+arg_10], r8
0x1800020b5  mov     [rsp+arg_18], r9
0x1800020ba  sub     rsp, 68h
0x1800020be  movdqa  [rsp+68h+var_48], xmm0
0x1800020c4  movdqa  [rsp+68h+var_38], xmm1
0x1800020ca  movdqa  [rsp+68h+var_28], xmm2
0x1800020d0  movdqa  [rsp+68h+var_18], xmm3
0x1800020d6  mov     rdx, rax
0x1800020d9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x1800020e0  call    __delayLoadHelper2
0x1800020e5  movdqa  xmm0, [rsp+68h+var_48]
0x1800020eb  movdqa  xmm1, [rsp+68h+var_38]
0x1800020f1  movdqa  xmm2, [rsp+68h+var_28]
0x1800020f7  movdqa  xmm3, [rsp+68h+var_18]
0x1800020fd  mov     rcx, [rsp+68h+arg_0]
0x180002102  mov     rdx, [rsp+68h+arg_8]
0x180002107  mov     r8, [rsp+68h+arg_10]
0x18000210f  mov     r9, [rsp+68h+arg_18]
0x180002117  add     rsp, 68h
0x18000211b  jmp     short $+2
0x18000211d  jmp     rax
```
