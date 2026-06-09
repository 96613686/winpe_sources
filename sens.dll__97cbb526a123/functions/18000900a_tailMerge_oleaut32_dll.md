# __tailMerge_oleaut32_dll

- ea: `0x18000900a`
- end: `0x180009083`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009089`
- `0x18000909b`
- `0x1800090ad`
- `0x1800090bf`

## callees

- `0x180006a50`
- `0x18000900a`

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
0x18000900a  mov     [rsp+arg_0], rcx
0x18000900f  mov     [rsp+arg_8], rdx
0x180009014  mov     [rsp+arg_10], r8
0x180009019  mov     [rsp+arg_18], r9
0x18000901e  sub     rsp, 68h
0x180009022  movdqa  [rsp+68h+var_48], xmm0
0x180009028  movdqa  [rsp+68h+var_38], xmm1
0x18000902e  movdqa  [rsp+68h+var_28], xmm2
0x180009034  movdqa  [rsp+68h+var_18], xmm3
0x18000903a  mov     rdx, rax
0x18000903d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180009044  call    __delayLoadHelper2
0x180009049  movdqa  xmm0, [rsp+68h+var_48]
0x18000904f  movdqa  xmm1, [rsp+68h+var_38]
0x180009055  movdqa  xmm2, [rsp+68h+var_28]
0x18000905b  movdqa  xmm3, [rsp+68h+var_18]
0x180009061  mov     rcx, [rsp+68h+arg_0]
0x180009066  mov     rdx, [rsp+68h+arg_8]
0x18000906b  mov     r8, [rsp+68h+arg_10]
0x180009073  mov     r9, [rsp+68h+arg_18]
0x18000907b  add     rsp, 68h
0x18000907f  jmp     short $+2
0x180009081  jmp     rax
```
