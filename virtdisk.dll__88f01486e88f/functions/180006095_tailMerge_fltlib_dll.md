# __tailMerge_fltlib_dll

- ea: `0x180006095`
- end: `0x18000610e`
- name: `__tailMerge_fltlib_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006114`

## callees

- `0x180006095`
- `0x18000b940`

## pseudocode

```c
__int64 __fastcall _tailMerge_fltlib_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_fltlib_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006095  mov     [rsp+arg_0], rcx
0x18000609a  mov     [rsp+arg_8], rdx
0x18000609f  mov     [rsp+arg_10], r8
0x1800060a4  mov     [rsp+arg_18], r9
0x1800060a9  sub     rsp, 68h
0x1800060ad  movdqa  [rsp+68h+var_48], xmm0
0x1800060b3  movdqa  [rsp+68h+var_38], xmm1
0x1800060b9  movdqa  [rsp+68h+var_28], xmm2
0x1800060bf  movdqa  [rsp+68h+var_18], xmm3
0x1800060c5  mov     rdx, rax
0x1800060c8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_fltlib_dll
0x1800060cf  call    __delayLoadHelper2
0x1800060d4  movdqa  xmm0, [rsp+68h+var_48]
0x1800060da  movdqa  xmm1, [rsp+68h+var_38]
0x1800060e0  movdqa  xmm2, [rsp+68h+var_28]
0x1800060e6  movdqa  xmm3, [rsp+68h+var_18]
0x1800060ec  mov     rcx, [rsp+68h+arg_0]
0x1800060f1  mov     rdx, [rsp+68h+arg_8]
0x1800060f6  mov     r8, [rsp+68h+arg_10]
0x1800060fe  mov     r9, [rsp+68h+arg_18]
0x180006106  add     rsp, 68h
0x18000610a  jmp     short $+2
0x18000610c  jmp     rax
```
