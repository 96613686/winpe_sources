# __tailMerge_rpcrt4_dll

- ea: `0x1400057ef`
- end: `0x140005868`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000586e`
- `0x140005880`
- `0x1400059cb`
- `0x1400059dd`
- `0x1400059ef`
- `0x140005a01`
- `0x140005a13`
- `0x140005a25`
- `0x140005a37`
- `0x140005a49`

## callees

- `0x140001ff0`
- `0x1400057ef`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400057ef  mov     [rsp+arg_0], rcx
0x1400057f4  mov     [rsp+arg_8], rdx
0x1400057f9  mov     [rsp+arg_10], r8
0x1400057fe  mov     [rsp+arg_18], r9
0x140005803  sub     rsp, 68h
0x140005807  movdqa  [rsp+68h+var_48], xmm0
0x14000580d  movdqa  [rsp+68h+var_38], xmm1
0x140005813  movdqa  [rsp+68h+var_28], xmm2
0x140005819  movdqa  [rsp+68h+var_18], xmm3
0x14000581f  mov     rdx, rax
0x140005822  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x140005829  call    __delayLoadHelper2
0x14000582e  movdqa  xmm0, [rsp+68h+var_48]
0x140005834  movdqa  xmm1, [rsp+68h+var_38]
0x14000583a  movdqa  xmm2, [rsp+68h+var_28]
0x140005840  movdqa  xmm3, [rsp+68h+var_18]
0x140005846  mov     rcx, [rsp+68h+arg_0]
0x14000584b  mov     rdx, [rsp+68h+arg_8]
0x140005850  mov     r8, [rsp+68h+arg_10]
0x140005858  mov     r9, [rsp+68h+arg_18]
0x140005860  add     rsp, 68h
0x140005864  jmp     short $+2
0x140005866  jmp     rax
```
