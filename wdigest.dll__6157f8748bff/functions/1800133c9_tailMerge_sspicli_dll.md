# __tailMerge_sspicli_dll

- ea: `0x1800133c9`
- end: `0x180013442`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013448`
- `0x18001345a`
- `0x18001346c`
- `0x18001347e`
- `0x18001351b`

## callees

- `0x1800133c9`
- `0x1800376a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800133c9  mov     [rsp+arg_0], rcx
0x1800133ce  mov     [rsp+arg_8], rdx
0x1800133d3  mov     [rsp+arg_10], r8
0x1800133d8  mov     [rsp+arg_18], r9
0x1800133dd  sub     rsp, 68h
0x1800133e1  movdqa  [rsp+68h+var_48], xmm0
0x1800133e7  movdqa  [rsp+68h+var_38], xmm1
0x1800133ed  movdqa  [rsp+68h+var_28], xmm2
0x1800133f3  movdqa  [rsp+68h+var_18], xmm3
0x1800133f9  mov     rdx, rax
0x1800133fc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x180013403  call    __delayLoadHelper2
0x180013408  movdqa  xmm0, [rsp+68h+var_48]
0x18001340e  movdqa  xmm1, [rsp+68h+var_38]
0x180013414  movdqa  xmm2, [rsp+68h+var_28]
0x18001341a  movdqa  xmm3, [rsp+68h+var_18]
0x180013420  mov     rcx, [rsp+68h+arg_0]
0x180013425  mov     rdx, [rsp+68h+arg_8]
0x18001342a  mov     r8, [rsp+68h+arg_10]
0x180013432  mov     r9, [rsp+68h+arg_18]
0x18001343a  add     rsp, 68h
0x18001343e  jmp     short $+2
0x180013440  jmp     rax
```
