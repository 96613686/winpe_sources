# __tailMerge_regapi_dll

- ea: `0x180007200`
- end: `0x180007279`
- name: `__tailMerge_regapi_dll`
- size: `121`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000727f`
- `0x180007291`
- `0x1800072a3`
- `0x1800072b5`
- `0x1800072c7`
- `0x1800072d9`
- `0x1800072eb`
- `0x1800072fd`
- `0x18000730f`
- `0x180007321`
- `0x180007333`
- `0x180007345`
- `0x180007357`
- `0x180007369`

## callees

- `0x180004ab0`
- `0x180007200`

## pseudocode

```c
__int64 __fastcall _tailMerge_regapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_regapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180007200  mov     [rsp+arg_0], rcx
0x180007205  mov     [rsp+arg_8], rdx
0x18000720a  mov     [rsp+arg_10], r8
0x18000720f  mov     [rsp+arg_18], r9
0x180007214  sub     rsp, 68h
0x180007218  movdqa  [rsp+68h+var_48], xmm0
0x18000721e  movdqa  [rsp+68h+var_38], xmm1
0x180007224  movdqa  [rsp+68h+var_28], xmm2
0x18000722a  movdqa  [rsp+68h+var_18], xmm3
0x180007230  mov     rdx, rax
0x180007233  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_regapi_dll
0x18000723a  call    __delayLoadHelper2
0x18000723f  movdqa  xmm0, [rsp+68h+var_48]
0x180007245  movdqa  xmm1, [rsp+68h+var_38]
0x18000724b  movdqa  xmm2, [rsp+68h+var_28]
0x180007251  movdqa  xmm3, [rsp+68h+var_18]
0x180007257  mov     rcx, [rsp+68h+arg_0]
0x18000725c  mov     rdx, [rsp+68h+arg_8]
0x180007261  mov     r8, [rsp+68h+arg_10]
0x180007269  mov     r9, [rsp+68h+arg_18]
0x180007271  add     rsp, 68h
0x180007275  jmp     short $+2
0x180007277  jmp     rax
```
