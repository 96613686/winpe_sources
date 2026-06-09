# __tailMerge_userenv_dll

- ea: `0x180003c51`
- end: `0x180003cca`
- name: `__tailMerge_userenv_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003cd0`
- `0x180003d6d`
- `0x180003da3`
- `0x180003db5`

## callees

- `0x180003580`
- `0x180003c51`

## pseudocode

```c
__int64 __fastcall _tailMerge_userenv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_userenv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003c51  mov     [rsp+arg_0], rcx
0x180003c56  mov     [rsp+arg_8], rdx
0x180003c5b  mov     [rsp+arg_10], r8
0x180003c60  mov     [rsp+arg_18], r9
0x180003c65  sub     rsp, 68h
0x180003c69  movdqa  [rsp+68h+var_48], xmm0
0x180003c6f  movdqa  [rsp+68h+var_38], xmm1
0x180003c75  movdqa  [rsp+68h+var_28], xmm2
0x180003c7b  movdqa  [rsp+68h+var_18], xmm3
0x180003c81  mov     rdx, rax
0x180003c84  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userenv_dll
0x180003c8b  call    __delayLoadHelper2
0x180003c90  movdqa  xmm0, [rsp+68h+var_48]
0x180003c96  movdqa  xmm1, [rsp+68h+var_38]
0x180003c9c  movdqa  xmm2, [rsp+68h+var_28]
0x180003ca2  movdqa  xmm3, [rsp+68h+var_18]
0x180003ca8  mov     rcx, [rsp+68h+arg_0]
0x180003cad  mov     rdx, [rsp+68h+arg_8]
0x180003cb2  mov     r8, [rsp+68h+arg_10]
0x180003cba  mov     r9, [rsp+68h+arg_18]
0x180003cc2  add     rsp, 68h
0x180003cc6  jmp     short $+2
0x180003cc8  jmp     rax
```
