# __tailMerge_oleaut32_dll

- ea: `0x1800019f0`
- end: `0x180001a69`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `17`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a6f`
- `0x180001a81`
- `0x180001a93`
- `0x180001aa5`
- `0x180001ab7`
- `0x180001ac9`
- `0x180001adb`
- `0x180001aed`
- `0x180001aff`
- `0x180001b11`
- `0x180001b23`
- `0x180001b35`
- `0x180001b47`
- `0x180001b59`
- `0x180001b6b`
- `0x180001df6`
- `0x180001e08`

## callees

- `0x1800019f0`
- `0x180017fd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800019f0  mov     [rsp+arg_0], rcx
0x1800019f5  mov     [rsp+arg_8], rdx
0x1800019fa  mov     [rsp+arg_10], r8
0x1800019ff  mov     [rsp+arg_18], r9
0x180001a04  sub     rsp, 68h
0x180001a08  movdqa  [rsp+68h+var_48], xmm0
0x180001a0e  movdqa  [rsp+68h+var_38], xmm1
0x180001a14  movdqa  [rsp+68h+var_28], xmm2
0x180001a1a  movdqa  [rsp+68h+var_18], xmm3
0x180001a20  mov     rdx, rax
0x180001a23  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180001a2a  call    __delayLoadHelper2
0x180001a2f  movdqa  xmm0, [rsp+68h+var_48]
0x180001a35  movdqa  xmm1, [rsp+68h+var_38]
0x180001a3b  movdqa  xmm2, [rsp+68h+var_28]
0x180001a41  movdqa  xmm3, [rsp+68h+var_18]
0x180001a47  mov     rcx, [rsp+68h+arg_0]
0x180001a4c  mov     rdx, [rsp+68h+arg_8]
0x180001a51  mov     r8, [rsp+68h+arg_10]
0x180001a59  mov     r9, [rsp+68h+arg_18]
0x180001a61  add     rsp, 68h
0x180001a65  jmp     short $+2
0x180001a67  jmp     rax
```
