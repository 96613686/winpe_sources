# __tailMerge_advpack_dll

- ea: `0x180002a60`
- end: `0x180002ad9`
- name: `__tailMerge_advpack_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002adf`

## callees

- `0x180002a60`
- `0x18001d240`

## pseudocode

```c
__int64 __fastcall _tailMerge_advpack_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_advpack_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002a60  mov     [rsp+arg_0], rcx
0x180002a65  mov     [rsp+arg_8], rdx
0x180002a6a  mov     [rsp+arg_10], r8
0x180002a6f  mov     [rsp+arg_18], r9
0x180002a74  sub     rsp, 68h
0x180002a78  movdqa  [rsp+68h+var_48], xmm0
0x180002a7e  movdqa  [rsp+68h+var_38], xmm1
0x180002a84  movdqa  [rsp+68h+var_28], xmm2
0x180002a8a  movdqa  [rsp+68h+var_18], xmm3
0x180002a90  mov     rdx, rax
0x180002a93  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advpack_dll
0x180002a9a  call    __delayLoadHelper2
0x180002a9f  movdqa  xmm0, [rsp+68h+var_48]
0x180002aa5  movdqa  xmm1, [rsp+68h+var_38]
0x180002aab  movdqa  xmm2, [rsp+68h+var_28]
0x180002ab1  movdqa  xmm3, [rsp+68h+var_18]
0x180002ab7  mov     rcx, [rsp+68h+arg_0]
0x180002abc  mov     rdx, [rsp+68h+arg_8]
0x180002ac1  mov     r8, [rsp+68h+arg_10]
0x180002ac9  mov     r9, [rsp+68h+arg_18]
0x180002ad1  add     rsp, 68h
0x180002ad5  jmp     short $+2
0x180002ad7  jmp     rax
```
