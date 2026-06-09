# __tailMerge_propsys_dll

- ea: `0x18000cb8a`
- end: `0x18000cc03`
- name: `__tailMerge_propsys_dll`
- size: `121`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000cc09`
- `0x18000cc1b`
- `0x18000cc2d`
- `0x18000cc3f`
- `0x18000cc51`
- `0x18000cc63`
- `0x18000cc75`
- `0x18000cc87`
- `0x18000cc99`
- `0x18000ccab`
- `0x18000ccbd`
- `0x18000cccf`
- `0x18000cce1`

## callees

- `0x180008bd0`
- `0x18000cb8a`

## pseudocode

```c
__int64 __fastcall _tailMerge_propsys_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_propsys_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000cb8a  mov     [rsp+arg_0], rcx
0x18000cb8f  mov     [rsp+arg_8], rdx
0x18000cb94  mov     [rsp+arg_10], r8
0x18000cb99  mov     [rsp+arg_18], r9
0x18000cb9e  sub     rsp, 68h
0x18000cba2  movdqa  [rsp+68h+var_48], xmm0
0x18000cba8  movdqa  [rsp+68h+var_38], xmm1
0x18000cbae  movdqa  [rsp+68h+var_28], xmm2
0x18000cbb4  movdqa  [rsp+68h+var_18], xmm3
0x18000cbba  mov     rdx, rax
0x18000cbbd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_propsys_dll
0x18000cbc4  call    __delayLoadHelper2
0x18000cbc9  movdqa  xmm0, [rsp+68h+var_48]
0x18000cbcf  movdqa  xmm1, [rsp+68h+var_38]
0x18000cbd5  movdqa  xmm2, [rsp+68h+var_28]
0x18000cbdb  movdqa  xmm3, [rsp+68h+var_18]
0x18000cbe1  mov     rcx, [rsp+68h+arg_0]
0x18000cbe6  mov     rdx, [rsp+68h+arg_8]
0x18000cbeb  mov     r8, [rsp+68h+arg_10]
0x18000cbf3  mov     r9, [rsp+68h+arg_18]
0x18000cbfb  add     rsp, 68h
0x18000cbff  jmp     short $+2
0x18000cc01  jmp     rax
```
