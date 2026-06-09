# __tailMerge_gdiplus_dll

- ea: `0x18000383a`
- end: `0x1800038b3`
- name: `__tailMerge_gdiplus_dll`
- size: `121`
- prototype: ``
- caller_count: `28`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800038b9`
- `0x1800038cb`
- `0x1800038dd`
- `0x1800038ef`
- `0x180003901`
- `0x180003913`
- `0x180003925`
- `0x180003937`
- `0x180003949`
- `0x18000395b`
- `0x18000396d`
- `0x18000397f`
- `0x180003991`
- `0x1800039a3`
- `0x1800039b5`
- `0x1800039c7`
- `0x1800039d9`
- `0x1800039eb`
- `0x1800039fd`
- `0x180003a0f`
- `0x180003a21`
- `0x180003a33`
- `0x180003a45`
- `0x180003a57`
- `0x180003a69`
- `0x180003a7b`
- `0x180003a8d`
- `0x180003a9f`

## callees

- `0x18000383a`
- `0x18001a930`

## pseudocode

```c
__int64 __fastcall _tailMerge_gdiplus_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_gdiplus_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000383a  mov     [rsp+arg_0], rcx
0x18000383f  mov     [rsp+arg_8], rdx
0x180003844  mov     [rsp+arg_10], r8
0x180003849  mov     [rsp+arg_18], r9
0x18000384e  sub     rsp, 68h
0x180003852  movdqa  [rsp+68h+var_48], xmm0
0x180003858  movdqa  [rsp+68h+var_38], xmm1
0x18000385e  movdqa  [rsp+68h+var_28], xmm2
0x180003864  movdqa  [rsp+68h+var_18], xmm3
0x18000386a  mov     rdx, rax
0x18000386d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_gdiplus_dll
0x180003874  call    __delayLoadHelper2
0x180003879  movdqa  xmm0, [rsp+68h+var_48]
0x18000387f  movdqa  xmm1, [rsp+68h+var_38]
0x180003885  movdqa  xmm2, [rsp+68h+var_28]
0x18000388b  movdqa  xmm3, [rsp+68h+var_18]
0x180003891  mov     rcx, [rsp+68h+arg_0]
0x180003896  mov     rdx, [rsp+68h+arg_8]
0x18000389b  mov     r8, [rsp+68h+arg_10]
0x1800038a3  mov     r9, [rsp+68h+arg_18]
0x1800038ab  add     rsp, 68h
0x1800038af  jmp     short $+2
0x1800038b1  jmp     rax
```
