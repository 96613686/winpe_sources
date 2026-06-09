# __tailMerge_samlib_dll

- ea: `0x18000d1c8`
- end: `0x18000d241`
- name: `__tailMerge_samlib_dll`
- size: `121`
- prototype: ``
- caller_count: `25`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d247`
- `0x18000d259`
- `0x18000d26b`
- `0x18000d27d`
- `0x18000d28f`
- `0x18000d2a1`
- `0x18000d2b3`
- `0x18000d2c5`
- `0x18000d331`
- `0x18000d343`
- `0x18000d355`
- `0x18000d367`
- `0x18000d379`
- `0x18000d38b`
- `0x18000d39d`
- `0x18000d43a`
- `0x18000d44c`
- `0x18000d45e`
- `0x18000d470`
- `0x18000d482`
- `0x18000d494`
- `0x18000d4a6`
- `0x18000d4b8`
- `0x18000d4ca`
- `0x18000d4dc`

## callees

- `0x180008bd0`
- `0x18000d1c8`

## pseudocode

```c
__int64 __fastcall _tailMerge_samlib_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_samlib_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000d1c8  mov     [rsp+arg_0], rcx
0x18000d1cd  mov     [rsp+arg_8], rdx
0x18000d1d2  mov     [rsp+arg_10], r8
0x18000d1d7  mov     [rsp+arg_18], r9
0x18000d1dc  sub     rsp, 68h
0x18000d1e0  movdqa  [rsp+68h+var_48], xmm0
0x18000d1e6  movdqa  [rsp+68h+var_38], xmm1
0x18000d1ec  movdqa  [rsp+68h+var_28], xmm2
0x18000d1f2  movdqa  [rsp+68h+var_18], xmm3
0x18000d1f8  mov     rdx, rax
0x18000d1fb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_samlib_dll
0x18000d202  call    __delayLoadHelper2
0x18000d207  movdqa  xmm0, [rsp+68h+var_48]
0x18000d20d  movdqa  xmm1, [rsp+68h+var_38]
0x18000d213  movdqa  xmm2, [rsp+68h+var_28]
0x18000d219  movdqa  xmm3, [rsp+68h+var_18]
0x18000d21f  mov     rcx, [rsp+68h+arg_0]
0x18000d224  mov     rdx, [rsp+68h+arg_8]
0x18000d229  mov     r8, [rsp+68h+arg_10]
0x18000d231  mov     r9, [rsp+68h+arg_18]
0x18000d239  add     rsp, 68h
0x18000d23d  jmp     short $+2
0x18000d23f  jmp     rax
```
