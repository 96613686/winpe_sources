# __tailMerge_crypt32_dll

- ea: `0x18000c275`
- end: `0x18000c2ee`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c2f4`
- `0x18000c391`
- `0x18000c3a3`
- `0x18000c3b5`
- `0x18000c3d9`
- `0x18000c3eb`
- `0x18000c3fd`
- `0x18000c421`
- `0x18000c433`
- `0x18000c445`
- `0x18000c457`
- `0x18000c469`
- `0x18000c47b`
- `0x18000c48d`
- `0x18000c4c3`
- `0x18000c4d5`

## callees

- `0x180009770`
- `0x18000c275`

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
0x18000c275  mov     [rsp+arg_0], rcx
0x18000c27a  mov     [rsp+arg_8], rdx
0x18000c27f  mov     [rsp+arg_10], r8
0x18000c284  mov     [rsp+arg_18], r9
0x18000c289  sub     rsp, 68h
0x18000c28d  movdqa  [rsp+68h+var_48], xmm0
0x18000c293  movdqa  [rsp+68h+var_38], xmm1
0x18000c299  movdqa  [rsp+68h+var_28], xmm2
0x18000c29f  movdqa  [rsp+68h+var_18], xmm3
0x18000c2a5  mov     rdx, rax
0x18000c2a8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x18000c2af  call    __delayLoadHelper2
0x18000c2b4  movdqa  xmm0, [rsp+68h+var_48]
0x18000c2ba  movdqa  xmm1, [rsp+68h+var_38]
0x18000c2c0  movdqa  xmm2, [rsp+68h+var_28]
0x18000c2c6  movdqa  xmm3, [rsp+68h+var_18]
0x18000c2cc  mov     rcx, [rsp+68h+arg_0]
0x18000c2d1  mov     rdx, [rsp+68h+arg_8]
0x18000c2d6  mov     r8, [rsp+68h+arg_10]
0x18000c2de  mov     r9, [rsp+68h+arg_18]
0x18000c2e6  add     rsp, 68h
0x18000c2ea  jmp     short $+2
0x18000c2ec  jmp     rax
```
