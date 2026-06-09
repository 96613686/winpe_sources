# __tailMerge_oleaut32_dll

- ea: `0x18000341a`
- end: `0x180003493`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003499`
- `0x1800034ab`
- `0x1800034bd`
- `0x1800034cf`
- `0x1800034e1`
- `0x1800034f3`

## callees

- `0x18000341a`
- `0x18000fec0`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000341a  mov     [rsp+arg_0], rcx
0x18000341f  mov     [rsp+arg_8], rdx
0x180003424  mov     [rsp+arg_10], r8
0x180003429  mov     [rsp+arg_18], r9
0x18000342e  sub     rsp, 68h
0x180003432  movdqa  [rsp+68h+var_48], xmm0
0x180003438  movdqa  [rsp+68h+var_38], xmm1
0x18000343e  movdqa  [rsp+68h+var_28], xmm2
0x180003444  movdqa  [rsp+68h+var_18], xmm3
0x18000344a  mov     rdx, rax
0x18000344d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180003454  call    __delayLoadHelper2
0x180003459  movdqa  xmm0, [rsp+68h+var_48]
0x18000345f  movdqa  xmm1, [rsp+68h+var_38]
0x180003465  movdqa  xmm2, [rsp+68h+var_28]
0x18000346b  movdqa  xmm3, [rsp+68h+var_18]
0x180003471  mov     rcx, [rsp+68h+arg_0]
0x180003476  mov     rdx, [rsp+68h+arg_8]
0x18000347b  mov     r8, [rsp+68h+arg_10]
0x180003483  mov     r9, [rsp+68h+arg_18]
0x18000348b  add     rsp, 68h
0x18000348f  jmp     short $+2
0x180003491  jmp     rax
```
