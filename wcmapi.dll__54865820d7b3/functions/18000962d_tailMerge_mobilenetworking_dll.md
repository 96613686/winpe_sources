# __tailMerge_mobilenetworking_dll

- ea: `0x18000962d`
- end: `0x1800096a6`
- name: `__tailMerge_mobilenetworking_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800096ac`
- `0x1800096be`
- `0x1800096d0`
- `0x1800096e2`
- `0x1800096f4`
- `0x180009706`

## callees

- `0x180005980`
- `0x18000962d`

## pseudocode

```c
__int64 __fastcall _tailMerge_mobilenetworking_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mobilenetworking_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000962d  mov     [rsp+arg_0], rcx
0x180009632  mov     [rsp+arg_8], rdx
0x180009637  mov     [rsp+arg_10], r8
0x18000963c  mov     [rsp+arg_18], r9
0x180009641  sub     rsp, 68h
0x180009645  movdqa  [rsp+68h+var_48], xmm0
0x18000964b  movdqa  [rsp+68h+var_38], xmm1
0x180009651  movdqa  [rsp+68h+var_28], xmm2
0x180009657  movdqa  [rsp+68h+var_18], xmm3
0x18000965d  mov     rdx, rax
0x180009660  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mobilenetworking_dll
0x180009667  call    __delayLoadHelper2
0x18000966c  movdqa  xmm0, [rsp+68h+var_48]
0x180009672  movdqa  xmm1, [rsp+68h+var_38]
0x180009678  movdqa  xmm2, [rsp+68h+var_28]
0x18000967e  movdqa  xmm3, [rsp+68h+var_18]
0x180009684  mov     rcx, [rsp+68h+arg_0]
0x180009689  mov     rdx, [rsp+68h+arg_8]
0x18000968e  mov     r8, [rsp+68h+arg_10]
0x180009696  mov     r9, [rsp+68h+arg_18]
0x18000969e  add     rsp, 68h
0x1800096a2  jmp     short $+2
0x1800096a4  jmp     rax
```
