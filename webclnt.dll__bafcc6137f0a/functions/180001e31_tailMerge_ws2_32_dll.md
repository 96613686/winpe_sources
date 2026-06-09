# __tailMerge_ws2_32_dll

- ea: `0x180001e31`
- end: `0x180001eaa`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001eb0`
- `0x180001ec2`
- `0x180001ed4`

## callees

- `0x180001e31`
- `0x18002ce10`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e31  mov     [rsp+arg_0], rcx
0x180001e36  mov     [rsp+arg_8], rdx
0x180001e3b  mov     [rsp+arg_10], r8
0x180001e40  mov     [rsp+arg_18], r9
0x180001e45  sub     rsp, 68h
0x180001e49  movdqa  [rsp+68h+var_48], xmm0
0x180001e4f  movdqa  [rsp+68h+var_38], xmm1
0x180001e55  movdqa  [rsp+68h+var_28], xmm2
0x180001e5b  movdqa  [rsp+68h+var_18], xmm3
0x180001e61  mov     rdx, rax
0x180001e64  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x180001e6b  call    __delayLoadHelper2
0x180001e70  movdqa  xmm0, [rsp+68h+var_48]
0x180001e76  movdqa  xmm1, [rsp+68h+var_38]
0x180001e7c  movdqa  xmm2, [rsp+68h+var_28]
0x180001e82  movdqa  xmm3, [rsp+68h+var_18]
0x180001e88  mov     rcx, [rsp+68h+arg_0]
0x180001e8d  mov     rdx, [rsp+68h+arg_8]
0x180001e92  mov     r8, [rsp+68h+arg_10]
0x180001e9a  mov     r9, [rsp+68h+arg_18]
0x180001ea2  add     rsp, 68h
0x180001ea6  jmp     short $+2
0x180001ea8  jmp     rax
```
