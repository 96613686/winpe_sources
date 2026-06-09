# __tailMerge_wmiclnt_dll

- ea: `0x180009156`
- end: `0x1800091cf`
- name: `__tailMerge_wmiclnt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800091d5`

## callees

- `0x180006a50`
- `0x180009156`

## pseudocode

```c
__int64 __fastcall _tailMerge_wmiclnt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wmiclnt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180009156  mov     [rsp+arg_0], rcx
0x18000915b  mov     [rsp+arg_8], rdx
0x180009160  mov     [rsp+arg_10], r8
0x180009165  mov     [rsp+arg_18], r9
0x18000916a  sub     rsp, 68h
0x18000916e  movdqa  [rsp+68h+var_48], xmm0
0x180009174  movdqa  [rsp+68h+var_38], xmm1
0x18000917a  movdqa  [rsp+68h+var_28], xmm2
0x180009180  movdqa  [rsp+68h+var_18], xmm3
0x180009186  mov     rdx, rax
0x180009189  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wmiclnt_dll
0x180009190  call    __delayLoadHelper2
0x180009195  movdqa  xmm0, [rsp+68h+var_48]
0x18000919b  movdqa  xmm1, [rsp+68h+var_38]
0x1800091a1  movdqa  xmm2, [rsp+68h+var_28]
0x1800091a7  movdqa  xmm3, [rsp+68h+var_18]
0x1800091ad  mov     rcx, [rsp+68h+arg_0]
0x1800091b2  mov     rdx, [rsp+68h+arg_8]
0x1800091b7  mov     r8, [rsp+68h+arg_10]
0x1800091bf  mov     r9, [rsp+68h+arg_18]
0x1800091c7  add     rsp, 68h
0x1800091cb  jmp     short $+2
0x1800091cd  jmp     rax
```
