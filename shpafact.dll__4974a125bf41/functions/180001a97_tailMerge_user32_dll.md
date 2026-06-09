# __tailMerge_user32_dll

- ea: `0x180001a97`
- end: `0x180001b10`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b16`
- `0x180001b28`

## callees

- `0x180001a97`
- `0x1800035c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001a97  mov     [rsp+arg_0], rcx
0x180001a9c  mov     [rsp+arg_8], rdx
0x180001aa1  mov     [rsp+arg_10], r8
0x180001aa6  mov     [rsp+arg_18], r9
0x180001aab  sub     rsp, 68h
0x180001aaf  movdqa  [rsp+68h+var_48], xmm0
0x180001ab5  movdqa  [rsp+68h+var_38], xmm1
0x180001abb  movdqa  [rsp+68h+var_28], xmm2
0x180001ac1  movdqa  [rsp+68h+var_18], xmm3
0x180001ac7  mov     rdx, rax
0x180001aca  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x180001ad1  call    __delayLoadHelper2
0x180001ad6  movdqa  xmm0, [rsp+68h+var_48]
0x180001adc  movdqa  xmm1, [rsp+68h+var_38]
0x180001ae2  movdqa  xmm2, [rsp+68h+var_28]
0x180001ae8  movdqa  xmm3, [rsp+68h+var_18]
0x180001aee  mov     rcx, [rsp+68h+arg_0]
0x180001af3  mov     rdx, [rsp+68h+arg_8]
0x180001af8  mov     r8, [rsp+68h+arg_10]
0x180001b00  mov     r9, [rsp+68h+arg_18]
0x180001b08  add     rsp, 68h
0x180001b0c  jmp     short $+2
0x180001b0e  jmp     rax
```
