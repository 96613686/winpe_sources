# __tailMerge_wininet_dll

- ea: `0x1800018e0`
- end: `0x180001959`
- name: `__tailMerge_wininet_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000195f`
- `0x180001971`
- `0x180001983`

## callees

- `0x1800018e0`
- `0x1800020d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_wininet_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wininet_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800018e0  mov     [rsp+arg_0], rcx
0x1800018e5  mov     [rsp+arg_8], rdx
0x1800018ea  mov     [rsp+arg_10], r8
0x1800018ef  mov     [rsp+arg_18], r9
0x1800018f4  sub     rsp, 68h
0x1800018f8  movdqa  [rsp+68h+var_48], xmm0
0x1800018fe  movdqa  [rsp+68h+var_38], xmm1
0x180001904  movdqa  [rsp+68h+var_28], xmm2
0x18000190a  movdqa  [rsp+68h+var_18], xmm3
0x180001910  mov     rdx, rax
0x180001913  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wininet_dll
0x18000191a  call    __delayLoadHelper2
0x18000191f  movdqa  xmm0, [rsp+68h+var_48]
0x180001925  movdqa  xmm1, [rsp+68h+var_38]
0x18000192b  movdqa  xmm2, [rsp+68h+var_28]
0x180001931  movdqa  xmm3, [rsp+68h+var_18]
0x180001937  mov     rcx, [rsp+68h+arg_0]
0x18000193c  mov     rdx, [rsp+68h+arg_8]
0x180001941  mov     r8, [rsp+68h+arg_10]
0x180001949  mov     r9, [rsp+68h+arg_18]
0x180001951  add     rsp, 68h
0x180001955  jmp     short $+2
0x180001957  jmp     rax
```
