# __tailMerge_wer_dll

- ea: `0x18000628e`
- end: `0x180006307`
- name: `__tailMerge_wer_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000630d`
- `0x18000631f`
- `0x180006331`
- `0x180006343`
- `0x180006355`

## callees

- `0x18000628e`
- `0x18002ad80`

## pseudocode

```c
__int64 __fastcall _tailMerge_wer_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wer_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000628e  mov     [rsp+arg_0], rcx
0x180006293  mov     [rsp+arg_8], rdx
0x180006298  mov     [rsp+arg_10], r8
0x18000629d  mov     [rsp+arg_18], r9
0x1800062a2  sub     rsp, 68h
0x1800062a6  movdqa  [rsp+68h+var_48], xmm0
0x1800062ac  movdqa  [rsp+68h+var_38], xmm1
0x1800062b2  movdqa  [rsp+68h+var_28], xmm2
0x1800062b8  movdqa  [rsp+68h+var_18], xmm3
0x1800062be  mov     rdx, rax
0x1800062c1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wer_dll
0x1800062c8  call    __delayLoadHelper2
0x1800062cd  movdqa  xmm0, [rsp+68h+var_48]
0x1800062d3  movdqa  xmm1, [rsp+68h+var_38]
0x1800062d9  movdqa  xmm2, [rsp+68h+var_28]
0x1800062df  movdqa  xmm3, [rsp+68h+var_18]
0x1800062e5  mov     rcx, [rsp+68h+arg_0]
0x1800062ea  mov     rdx, [rsp+68h+arg_8]
0x1800062ef  mov     r8, [rsp+68h+arg_10]
0x1800062f7  mov     r9, [rsp+68h+arg_18]
0x1800062ff  add     rsp, 68h
0x180006303  jmp     short $+2
0x180006305  jmp     rax
```
