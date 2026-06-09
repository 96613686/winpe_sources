# __tailMerge_profapi_dll

- ea: `0x18000e7f6`
- end: `0x18000e86f`
- name: `__tailMerge_profapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e875`
- `0x18000e887`
- `0x18000e899`
- `0x18000e8ab`
- `0x18000e8bd`

## callees

- `0x180007910`
- `0x18000e7f6`

## pseudocode

```c
__int64 __fastcall _tailMerge_profapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_profapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e7f6  mov     [rsp+arg_0], rcx
0x18000e7fb  mov     [rsp+arg_8], rdx
0x18000e800  mov     [rsp+arg_10], r8
0x18000e805  mov     [rsp+arg_18], r9
0x18000e80a  sub     rsp, 68h
0x18000e80e  movdqa  [rsp+68h+var_48], xmm0
0x18000e814  movdqa  [rsp+68h+var_38], xmm1
0x18000e81a  movdqa  [rsp+68h+var_28], xmm2
0x18000e820  movdqa  [rsp+68h+var_18], xmm3
0x18000e826  mov     rdx, rax
0x18000e829  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_profapi_dll
0x18000e830  call    __delayLoadHelper2
0x18000e835  movdqa  xmm0, [rsp+68h+var_48]
0x18000e83b  movdqa  xmm1, [rsp+68h+var_38]
0x18000e841  movdqa  xmm2, [rsp+68h+var_28]
0x18000e847  movdqa  xmm3, [rsp+68h+var_18]
0x18000e84d  mov     rcx, [rsp+68h+arg_0]
0x18000e852  mov     rdx, [rsp+68h+arg_8]
0x18000e857  mov     r8, [rsp+68h+arg_10]
0x18000e85f  mov     r9, [rsp+68h+arg_18]
0x18000e867  add     rsp, 68h
0x18000e86b  jmp     short $+2
0x18000e86d  jmp     rax
```
