# __tailMerge_icu_dll

- ea: `0x180002ee0`
- end: `0x180002f59`
- name: `__tailMerge_icu_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002f5f`
- `0x180002f71`
- `0x180002f83`
- `0x180002fa0`
- `0x180002fb2`
- `0x180002fc4`

## callees

- `0x180002ee0`
- `0x18001af90`

## pseudocode

```c
__int64 __fastcall _tailMerge_icu_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_icu_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002ee0  mov     [rsp+arg_0], rcx
0x180002ee5  mov     [rsp+arg_8], rdx
0x180002eea  mov     [rsp+arg_10], r8
0x180002eef  mov     [rsp+arg_18], r9
0x180002ef4  sub     rsp, 68h
0x180002ef8  movdqa  [rsp+68h+var_48], xmm0
0x180002efe  movdqa  [rsp+68h+var_38], xmm1
0x180002f04  movdqa  [rsp+68h+var_28], xmm2
0x180002f0a  movdqa  [rsp+68h+var_18], xmm3
0x180002f10  mov     rdx, rax
0x180002f13  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_icu_dll
0x180002f1a  call    __delayLoadHelper2
0x180002f1f  movdqa  xmm0, [rsp+68h+var_48]
0x180002f25  movdqa  xmm1, [rsp+68h+var_38]
0x180002f2b  movdqa  xmm2, [rsp+68h+var_28]
0x180002f31  movdqa  xmm3, [rsp+68h+var_18]
0x180002f37  mov     rcx, [rsp+68h+arg_0]
0x180002f3c  mov     rdx, [rsp+68h+arg_8]
0x180002f41  mov     r8, [rsp+68h+arg_10]
0x180002f49  mov     r9, [rsp+68h+arg_18]
0x180002f51  add     rsp, 68h
0x180002f55  jmp     short $+2
0x180002f57  jmp     rax
```
