# __tailMerge_secur32_dll

- ea: `0x1800061ab`
- end: `0x180006224`
- name: `__tailMerge_secur32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000622a`

## callees

- `0x1800061ab`
- `0x180014d80`

## pseudocode

```c
__int64 __fastcall _tailMerge_secur32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_secur32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800061ab  mov     [rsp+arg_0], rcx
0x1800061b0  mov     [rsp+arg_8], rdx
0x1800061b5  mov     [rsp+arg_10], r8
0x1800061ba  mov     [rsp+arg_18], r9
0x1800061bf  sub     rsp, 68h
0x1800061c3  movdqa  [rsp+68h+var_48], xmm0
0x1800061c9  movdqa  [rsp+68h+var_38], xmm1
0x1800061cf  movdqa  [rsp+68h+var_28], xmm2
0x1800061d5  movdqa  [rsp+68h+var_18], xmm3
0x1800061db  mov     rdx, rax
0x1800061de  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_secur32_dll
0x1800061e5  call    __delayLoadHelper2
0x1800061ea  movdqa  xmm0, [rsp+68h+var_48]
0x1800061f0  movdqa  xmm1, [rsp+68h+var_38]
0x1800061f6  movdqa  xmm2, [rsp+68h+var_28]
0x1800061fc  movdqa  xmm3, [rsp+68h+var_18]
0x180006202  mov     rcx, [rsp+68h+arg_0]
0x180006207  mov     rdx, [rsp+68h+arg_8]
0x18000620c  mov     r8, [rsp+68h+arg_10]
0x180006214  mov     r9, [rsp+68h+arg_18]
0x18000621c  add     rsp, 68h
0x180006220  jmp     short $+2
0x180006222  jmp     rax
```
