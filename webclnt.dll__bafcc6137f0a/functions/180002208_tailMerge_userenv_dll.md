# __tailMerge_userenv_dll

- ea: `0x180002208`
- end: `0x180002281`
- name: `__tailMerge_userenv_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002287`
- `0x180002299`

## callees

- `0x180002208`
- `0x18002ce10`

## pseudocode

```c
__int64 __fastcall _tailMerge_userenv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_userenv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002208  mov     [rsp+arg_0], rcx
0x18000220d  mov     [rsp+arg_8], rdx
0x180002212  mov     [rsp+arg_10], r8
0x180002217  mov     [rsp+arg_18], r9
0x18000221c  sub     rsp, 68h
0x180002220  movdqa  [rsp+68h+var_48], xmm0
0x180002226  movdqa  [rsp+68h+var_38], xmm1
0x18000222c  movdqa  [rsp+68h+var_28], xmm2
0x180002232  movdqa  [rsp+68h+var_18], xmm3
0x180002238  mov     rdx, rax
0x18000223b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userenv_dll
0x180002242  call    __delayLoadHelper2
0x180002247  movdqa  xmm0, [rsp+68h+var_48]
0x18000224d  movdqa  xmm1, [rsp+68h+var_38]
0x180002253  movdqa  xmm2, [rsp+68h+var_28]
0x180002259  movdqa  xmm3, [rsp+68h+var_18]
0x18000225f  mov     rcx, [rsp+68h+arg_0]
0x180002264  mov     rdx, [rsp+68h+arg_8]
0x180002269  mov     r8, [rsp+68h+arg_10]
0x180002271  mov     r9, [rsp+68h+arg_18]
0x180002279  add     rsp, 68h
0x18000227d  jmp     short $+2
0x18000227f  jmp     rax
```
