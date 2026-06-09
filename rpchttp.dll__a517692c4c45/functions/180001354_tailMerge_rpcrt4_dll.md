# __tailMerge_rpcrt4_dll

- ea: `0x180001354`
- end: `0x1800013cd`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800013d3`
- `0x1800013e5`
- `0x1800013f7`
- `0x180001409`
- `0x18000141b`
- `0x18000142d`
- `0x18000143f`
- `0x180001451`
- `0x18000175f`
- `0x180001771`
- `0x180001783`
- `0x180001795`
- `0x1800017a7`
- `0x1800017b9`
- `0x1800017cb`
- `0x1800017dd`
- `0x1800017ef`
- `0x180001801`
- `0x180001813`
- `0x180001825`
- `0x180001837`
- `0x180001849`

## callees

- `0x180001354`
- `0x1800244c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001354  mov     [rsp+arg_0], rcx
0x180001359  mov     [rsp+arg_8], rdx
0x18000135e  mov     [rsp+arg_10], r8
0x180001363  mov     [rsp+arg_18], r9
0x180001368  sub     rsp, 68h
0x18000136c  movdqa  [rsp+68h+var_48], xmm0
0x180001372  movdqa  [rsp+68h+var_38], xmm1
0x180001378  movdqa  [rsp+68h+var_28], xmm2
0x18000137e  movdqa  [rsp+68h+var_18], xmm3
0x180001384  mov     rdx, rax
0x180001387  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18000138e  call    __delayLoadHelper2
0x180001393  movdqa  xmm0, [rsp+68h+var_48]
0x180001399  movdqa  xmm1, [rsp+68h+var_38]
0x18000139f  movdqa  xmm2, [rsp+68h+var_28]
0x1800013a5  movdqa  xmm3, [rsp+68h+var_18]
0x1800013ab  mov     rcx, [rsp+68h+arg_0]
0x1800013b0  mov     rdx, [rsp+68h+arg_8]
0x1800013b5  mov     r8, [rsp+68h+arg_10]
0x1800013bd  mov     r9, [rsp+68h+arg_18]
0x1800013c5  add     rsp, 68h
0x1800013c9  jmp     short $+2
0x1800013cb  jmp     rax
```
