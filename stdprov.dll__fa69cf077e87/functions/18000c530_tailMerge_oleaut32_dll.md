# __tailMerge_oleaut32_dll

- ea: `0x18000c530`
- end: `0x18000c5a9`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `16`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c5af`
- `0x18000c5c1`
- `0x18000c5d3`
- `0x18000c5e5`
- `0x18000c5f7`
- `0x18000c609`
- `0x18000c61b`
- `0x18000c62d`
- `0x18000c63f`
- `0x18000c651`
- `0x18000c663`
- `0x18000c675`
- `0x18000c687`
- `0x18000c699`
- `0x18000c7e5`
- `0x18000c7f7`

## callees

- `0x18000b110`
- `0x18000c530`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c530  mov     [rsp+arg_0], rcx
0x18000c535  mov     [rsp+arg_8], rdx
0x18000c53a  mov     [rsp+arg_10], r8
0x18000c53f  mov     [rsp+arg_18], r9
0x18000c544  sub     rsp, 68h
0x18000c548  movdqa  [rsp+68h+var_48], xmm0
0x18000c54e  movdqa  [rsp+68h+var_38], xmm1
0x18000c554  movdqa  [rsp+68h+var_28], xmm2
0x18000c55a  movdqa  [rsp+68h+var_18], xmm3
0x18000c560  mov     rdx, rax
0x18000c563  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x18000c56a  call    __delayLoadHelper2
0x18000c56f  movdqa  xmm0, [rsp+68h+var_48]
0x18000c575  movdqa  xmm1, [rsp+68h+var_38]
0x18000c57b  movdqa  xmm2, [rsp+68h+var_28]
0x18000c581  movdqa  xmm3, [rsp+68h+var_18]
0x18000c587  mov     rcx, [rsp+68h+arg_0]
0x18000c58c  mov     rdx, [rsp+68h+arg_8]
0x18000c591  mov     r8, [rsp+68h+arg_10]
0x18000c599  mov     r9, [rsp+68h+arg_18]
0x18000c5a1  add     rsp, 68h
0x18000c5a5  jmp     short $+2
0x18000c5a7  jmp     rax
```
