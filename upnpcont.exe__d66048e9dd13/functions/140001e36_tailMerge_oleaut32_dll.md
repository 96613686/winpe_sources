# __tailMerge_oleaut32_dll

- ea: `0x140001e36`
- end: `0x140001eaf`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001eb5`
- `0x140001ec7`
- `0x140001ed9`
- `0x140001eeb`
- `0x140001efd`
- `0x140001f0f`
- `0x140001f21`

## callees

- `0x140001e36`
- `0x140006530`

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
0x140001e36  mov     [rsp+arg_0], rcx
0x140001e3b  mov     [rsp+arg_8], rdx
0x140001e40  mov     [rsp+arg_10], r8
0x140001e45  mov     [rsp+arg_18], r9
0x140001e4a  sub     rsp, 68h
0x140001e4e  movdqa  [rsp+68h+var_48], xmm0
0x140001e54  movdqa  [rsp+68h+var_38], xmm1
0x140001e5a  movdqa  [rsp+68h+var_28], xmm2
0x140001e60  movdqa  [rsp+68h+var_18], xmm3
0x140001e66  mov     rdx, rax
0x140001e69  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x140001e70  call    __delayLoadHelper2
0x140001e75  movdqa  xmm0, [rsp+68h+var_48]
0x140001e7b  movdqa  xmm1, [rsp+68h+var_38]
0x140001e81  movdqa  xmm2, [rsp+68h+var_28]
0x140001e87  movdqa  xmm3, [rsp+68h+var_18]
0x140001e8d  mov     rcx, [rsp+68h+arg_0]
0x140001e92  mov     rdx, [rsp+68h+arg_8]
0x140001e97  mov     r8, [rsp+68h+arg_10]
0x140001e9f  mov     r9, [rsp+68h+arg_18]
0x140001ea7  add     rsp, 68h
0x140001eab  jmp     short $+2
0x140001ead  jmp     rax
```
