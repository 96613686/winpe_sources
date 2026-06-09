# __tailMerge_credui_dll

- ea: `0x180002976`
- end: `0x1800029ef`
- name: `__tailMerge_credui_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800029f5`
- `0x180002a07`

## callees

- `0x180002976`
- `0x18001be40`

## pseudocode

```c
__int64 __fastcall _tailMerge_credui_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_credui_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002976  mov     [rsp+arg_0], rcx
0x18000297b  mov     [rsp+arg_8], rdx
0x180002980  mov     [rsp+arg_10], r8
0x180002985  mov     [rsp+arg_18], r9
0x18000298a  sub     rsp, 68h
0x18000298e  movdqa  [rsp+68h+var_48], xmm0
0x180002994  movdqa  [rsp+68h+var_38], xmm1
0x18000299a  movdqa  [rsp+68h+var_28], xmm2
0x1800029a0  movdqa  [rsp+68h+var_18], xmm3
0x1800029a6  mov     rdx, rax
0x1800029a9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_credui_dll
0x1800029b0  call    __delayLoadHelper2
0x1800029b5  movdqa  xmm0, [rsp+68h+var_48]
0x1800029bb  movdqa  xmm1, [rsp+68h+var_38]
0x1800029c1  movdqa  xmm2, [rsp+68h+var_28]
0x1800029c7  movdqa  xmm3, [rsp+68h+var_18]
0x1800029cd  mov     rcx, [rsp+68h+arg_0]
0x1800029d2  mov     rdx, [rsp+68h+arg_8]
0x1800029d7  mov     r8, [rsp+68h+arg_10]
0x1800029df  mov     r9, [rsp+68h+arg_18]
0x1800029e7  add     rsp, 68h
0x1800029eb  jmp     short $+2
0x1800029ed  jmp     rax
```
