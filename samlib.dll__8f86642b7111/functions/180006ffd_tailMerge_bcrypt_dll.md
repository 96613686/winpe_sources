# __tailMerge_bcrypt_dll

- ea: `0x180006ffd`
- end: `0x180007076`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000707c`
- `0x18000708e`
- `0x1800070a0`
- `0x1800070b2`
- `0x1800070c4`
- `0x1800070d6`
- `0x1800070e8`
- `0x1800071a9`
- `0x1800071bb`
- `0x1800071cd`
- `0x1800071df`
- `0x1800073df`
- `0x1800073f1`

## callees

- `0x1800054c0`
- `0x180006ffd`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006ffd  mov     [rsp+arg_0], rcx
0x180007002  mov     [rsp+arg_8], rdx
0x180007007  mov     [rsp+arg_10], r8
0x18000700c  mov     [rsp+arg_18], r9
0x180007011  sub     rsp, 68h
0x180007015  movdqa  [rsp+68h+var_48], xmm0
0x18000701b  movdqa  [rsp+68h+var_38], xmm1
0x180007021  movdqa  [rsp+68h+var_28], xmm2
0x180007027  movdqa  [rsp+68h+var_18], xmm3
0x18000702d  mov     rdx, rax
0x180007030  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x180007037  call    __delayLoadHelper2
0x18000703c  movdqa  xmm0, [rsp+68h+var_48]
0x180007042  movdqa  xmm1, [rsp+68h+var_38]
0x180007048  movdqa  xmm2, [rsp+68h+var_28]
0x18000704e  movdqa  xmm3, [rsp+68h+var_18]
0x180007054  mov     rcx, [rsp+68h+arg_0]
0x180007059  mov     rdx, [rsp+68h+arg_8]
0x18000705e  mov     r8, [rsp+68h+arg_10]
0x180007066  mov     r9, [rsp+68h+arg_18]
0x18000706e  add     rsp, 68h
0x180007072  jmp     short $+2
0x180007074  jmp     rax
```
