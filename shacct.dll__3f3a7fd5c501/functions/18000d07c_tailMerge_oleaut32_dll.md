# __tailMerge_oleaut32_dll

- ea: `0x18000d07c`
- end: `0x18000d0f5`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d0fb`

## callees

- `0x180008bd0`
- `0x18000d07c`

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
0x18000d07c  mov     [rsp+arg_0], rcx
0x18000d081  mov     [rsp+arg_8], rdx
0x18000d086  mov     [rsp+arg_10], r8
0x18000d08b  mov     [rsp+arg_18], r9
0x18000d090  sub     rsp, 68h
0x18000d094  movdqa  [rsp+68h+var_48], xmm0
0x18000d09a  movdqa  [rsp+68h+var_38], xmm1
0x18000d0a0  movdqa  [rsp+68h+var_28], xmm2
0x18000d0a6  movdqa  [rsp+68h+var_18], xmm3
0x18000d0ac  mov     rdx, rax
0x18000d0af  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x18000d0b6  call    __delayLoadHelper2
0x18000d0bb  movdqa  xmm0, [rsp+68h+var_48]
0x18000d0c1  movdqa  xmm1, [rsp+68h+var_38]
0x18000d0c7  movdqa  xmm2, [rsp+68h+var_28]
0x18000d0cd  movdqa  xmm3, [rsp+68h+var_18]
0x18000d0d3  mov     rcx, [rsp+68h+arg_0]
0x18000d0d8  mov     rdx, [rsp+68h+arg_8]
0x18000d0dd  mov     r8, [rsp+68h+arg_10]
0x18000d0e5  mov     r9, [rsp+68h+arg_18]
0x18000d0ed  add     rsp, 68h
0x18000d0f1  jmp     short $+2
0x18000d0f3  jmp     rax
```
