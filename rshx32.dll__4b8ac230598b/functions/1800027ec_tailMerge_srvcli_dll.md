# __tailMerge_srvcli_dll

- ea: `0x1800027ec`
- end: `0x180002865`
- name: `__tailMerge_srvcli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000286b`
- `0x18000287d`

## callees

- `0x1800027ec`
- `0x18001d240`

## pseudocode

```c
__int64 __fastcall _tailMerge_srvcli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_srvcli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027ec  mov     [rsp+arg_0], rcx
0x1800027f1  mov     [rsp+arg_8], rdx
0x1800027f6  mov     [rsp+arg_10], r8
0x1800027fb  mov     [rsp+arg_18], r9
0x180002800  sub     rsp, 68h
0x180002804  movdqa  [rsp+68h+var_48], xmm0
0x18000280a  movdqa  [rsp+68h+var_38], xmm1
0x180002810  movdqa  [rsp+68h+var_28], xmm2
0x180002816  movdqa  [rsp+68h+var_18], xmm3
0x18000281c  mov     rdx, rax
0x18000281f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_srvcli_dll
0x180002826  call    __delayLoadHelper2
0x18000282b  movdqa  xmm0, [rsp+68h+var_48]
0x180002831  movdqa  xmm1, [rsp+68h+var_38]
0x180002837  movdqa  xmm2, [rsp+68h+var_28]
0x18000283d  movdqa  xmm3, [rsp+68h+var_18]
0x180002843  mov     rcx, [rsp+68h+arg_0]
0x180002848  mov     rdx, [rsp+68h+arg_8]
0x18000284d  mov     r8, [rsp+68h+arg_10]
0x180002855  mov     r9, [rsp+68h+arg_18]
0x18000285d  add     rsp, 68h
0x180002861  jmp     short $+2
0x180002863  jmp     rax
```
