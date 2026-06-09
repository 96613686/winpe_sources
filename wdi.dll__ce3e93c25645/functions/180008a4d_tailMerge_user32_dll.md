# __tailMerge_user32_dll

- ea: `0x180008a4d`
- end: `0x180008ac6`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008acc`
- `0x180008ade`
- `0x180008af0`
- `0x180008b02`
- `0x180008b14`
- `0x180008b26`
- `0x180008b38`
- `0x180008b4a`
- `0x180008b5c`

## callees

- `0x180003970`
- `0x180008a4d`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180008a4d  mov     [rsp+arg_0], rcx
0x180008a52  mov     [rsp+arg_8], rdx
0x180008a57  mov     [rsp+arg_10], r8
0x180008a5c  mov     [rsp+arg_18], r9
0x180008a61  sub     rsp, 68h
0x180008a65  movdqa  [rsp+68h+var_48], xmm0
0x180008a6b  movdqa  [rsp+68h+var_38], xmm1
0x180008a71  movdqa  [rsp+68h+var_28], xmm2
0x180008a77  movdqa  [rsp+68h+var_18], xmm3
0x180008a7d  mov     rdx, rax
0x180008a80  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x180008a87  call    __delayLoadHelper2
0x180008a8c  movdqa  xmm0, [rsp+68h+var_48]
0x180008a92  movdqa  xmm1, [rsp+68h+var_38]
0x180008a98  movdqa  xmm2, [rsp+68h+var_28]
0x180008a9e  movdqa  xmm3, [rsp+68h+var_18]
0x180008aa4  mov     rcx, [rsp+68h+arg_0]
0x180008aa9  mov     rdx, [rsp+68h+arg_8]
0x180008aae  mov     r8, [rsp+68h+arg_10]
0x180008ab6  mov     r9, [rsp+68h+arg_18]
0x180008abe  add     rsp, 68h
0x180008ac2  jmp     short $+2
0x180008ac4  jmp     rax
```
