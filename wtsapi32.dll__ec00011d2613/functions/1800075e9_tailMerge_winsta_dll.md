# __tailMerge_winsta_dll

- ea: `0x1800075e9`
- end: `0x180007662`
- name: `__tailMerge_winsta_dll`
- size: `121`
- prototype: ``
- caller_count: `36`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007668`
- `0x18000767a`
- `0x18000768c`
- `0x18000769e`
- `0x1800076b0`
- `0x1800076c2`
- `0x1800076d4`
- `0x1800076e6`
- `0x1800076f8`
- `0x18000770a`
- `0x18000771c`
- `0x18000772e`
- `0x180007740`
- `0x180007752`
- `0x180007764`
- `0x180007776`
- `0x180007788`
- `0x18000779a`
- `0x1800077ac`
- `0x1800077be`
- `0x1800077d0`
- `0x1800077e2`
- `0x1800077f4`
- `0x180007806`
- `0x180007818`
- `0x18000782a`
- `0x18000783c`
- `0x18000784e`
- `0x180007860`
- `0x180007872`
- `0x180007884`
- `0x180007896`
- `0x1800078a8`
- `0x1800078ba`
- `0x1800078cc`
- `0x1800078de`

## callees

- `0x180004ab0`
- `0x1800075e9`

## pseudocode

```c
__int64 __fastcall _tailMerge_winsta_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winsta_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800075e9  mov     [rsp+arg_0], rcx
0x1800075ee  mov     [rsp+arg_8], rdx
0x1800075f3  mov     [rsp+arg_10], r8
0x1800075f8  mov     [rsp+arg_18], r9
0x1800075fd  sub     rsp, 68h
0x180007601  movdqa  [rsp+68h+var_48], xmm0
0x180007607  movdqa  [rsp+68h+var_38], xmm1
0x18000760d  movdqa  [rsp+68h+var_28], xmm2
0x180007613  movdqa  [rsp+68h+var_18], xmm3
0x180007619  mov     rdx, rax
0x18000761c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winsta_dll
0x180007623  call    __delayLoadHelper2
0x180007628  movdqa  xmm0, [rsp+68h+var_48]
0x18000762e  movdqa  xmm1, [rsp+68h+var_38]
0x180007634  movdqa  xmm2, [rsp+68h+var_28]
0x18000763a  movdqa  xmm3, [rsp+68h+var_18]
0x180007640  mov     rcx, [rsp+68h+arg_0]
0x180007645  mov     rdx, [rsp+68h+arg_8]
0x18000764a  mov     r8, [rsp+68h+arg_10]
0x180007652  mov     r9, [rsp+68h+arg_18]
0x18000765a  add     rsp, 68h
0x18000765e  jmp     short $+2
0x180007660  jmp     rax
```
