# __tailMerge_oleaut32_dll

- ea: `0x180001d46`
- end: `0x180001dbf`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001dc5`
- `0x180001dd7`
- `0x180001de9`
- `0x180001dfb`
- `0x180001e98`
- `0x180001eaa`
- `0x180001ebc`
- `0x180001ece`
- `0x180001ee0`

## callees

- `0x180001d46`
- `0x18000b9e0`

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
0x180001d46  mov     [rsp+arg_0], rcx
0x180001d4b  mov     [rsp+arg_8], rdx
0x180001d50  mov     [rsp+arg_10], r8
0x180001d55  mov     [rsp+arg_18], r9
0x180001d5a  sub     rsp, 68h
0x180001d5e  movdqa  [rsp+68h+var_48], xmm0
0x180001d64  movdqa  [rsp+68h+var_38], xmm1
0x180001d6a  movdqa  [rsp+68h+var_28], xmm2
0x180001d70  movdqa  [rsp+68h+var_18], xmm3
0x180001d76  mov     rdx, rax
0x180001d79  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180001d80  call    __delayLoadHelper2
0x180001d85  movdqa  xmm0, [rsp+68h+var_48]
0x180001d8b  movdqa  xmm1, [rsp+68h+var_38]
0x180001d91  movdqa  xmm2, [rsp+68h+var_28]
0x180001d97  movdqa  xmm3, [rsp+68h+var_18]
0x180001d9d  mov     rcx, [rsp+68h+arg_0]
0x180001da2  mov     rdx, [rsp+68h+arg_8]
0x180001da7  mov     r8, [rsp+68h+arg_10]
0x180001daf  mov     r9, [rsp+68h+arg_18]
0x180001db7  add     rsp, 68h
0x180001dbb  jmp     short $+2
0x180001dbd  jmp     rax
```
