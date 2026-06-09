# __tailMerge_ole32_dll

- ea: `0x180003e30`
- end: `0x180003ea9`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003eaf`
- `0x180003ec1`
- `0x18000421f`
- `0x180004243`
- `0x180004255`

## callees

- `0x180002eb0`
- `0x180003e30`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003e30  mov     [rsp+arg_0], rcx
0x180003e35  mov     [rsp+arg_8], rdx
0x180003e3a  mov     [rsp+arg_10], r8
0x180003e3f  mov     [rsp+arg_18], r9
0x180003e44  sub     rsp, 68h
0x180003e48  movdqa  [rsp+68h+var_48], xmm0
0x180003e4e  movdqa  [rsp+68h+var_38], xmm1
0x180003e54  movdqa  [rsp+68h+var_28], xmm2
0x180003e5a  movdqa  [rsp+68h+var_18], xmm3
0x180003e60  mov     rdx, rax
0x180003e63  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x180003e6a  call    __delayLoadHelper2
0x180003e6f  movdqa  xmm0, [rsp+68h+var_48]
0x180003e75  movdqa  xmm1, [rsp+68h+var_38]
0x180003e7b  movdqa  xmm2, [rsp+68h+var_28]
0x180003e81  movdqa  xmm3, [rsp+68h+var_18]
0x180003e87  mov     rcx, [rsp+68h+arg_0]
0x180003e8c  mov     rdx, [rsp+68h+arg_8]
0x180003e91  mov     r8, [rsp+68h+arg_10]
0x180003e99  mov     r9, [rsp+68h+arg_18]
0x180003ea1  add     rsp, 68h
0x180003ea5  jmp     short $+2
0x180003ea7  jmp     rax
```
