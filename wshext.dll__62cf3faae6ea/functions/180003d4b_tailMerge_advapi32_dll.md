# __tailMerge_advapi32_dll

- ea: `0x180003d4b`
- end: `0x180003dc4`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003dca`
- `0x180003ddc`
- `0x180003dee`
- `0x180003e00`
- `0x180003e12`
- `0x180003e24`
- `0x180003ed3`
- `0x180003ee5`
- `0x180003ef7`
- `0x180003f09`
- `0x180003f1b`
- `0x18000420d`
- `0x180004231`
- `0x180004267`
- `0x18000429d`
- `0x1800042af`
- `0x1800042f7`
- `0x180004363`
- `0x180004375`
- `0x180004387`
- `0x180004399`

## callees

- `0x180002eb0`
- `0x180003d4b`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003d4b  mov     [rsp+arg_0], rcx
0x180003d50  mov     [rsp+arg_8], rdx
0x180003d55  mov     [rsp+arg_10], r8
0x180003d5a  mov     [rsp+arg_18], r9
0x180003d5f  sub     rsp, 68h
0x180003d63  movdqa  [rsp+68h+var_48], xmm0
0x180003d69  movdqa  [rsp+68h+var_38], xmm1
0x180003d6f  movdqa  [rsp+68h+var_28], xmm2
0x180003d75  movdqa  [rsp+68h+var_18], xmm3
0x180003d7b  mov     rdx, rax
0x180003d7e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x180003d85  call    __delayLoadHelper2
0x180003d8a  movdqa  xmm0, [rsp+68h+var_48]
0x180003d90  movdqa  xmm1, [rsp+68h+var_38]
0x180003d96  movdqa  xmm2, [rsp+68h+var_28]
0x180003d9c  movdqa  xmm3, [rsp+68h+var_18]
0x180003da2  mov     rcx, [rsp+68h+arg_0]
0x180003da7  mov     rdx, [rsp+68h+arg_8]
0x180003dac  mov     r8, [rsp+68h+arg_10]
0x180003db4  mov     r9, [rsp+68h+arg_18]
0x180003dbc  add     rsp, 68h
0x180003dc0  jmp     short $+2
0x180003dc2  jmp     rax
```
