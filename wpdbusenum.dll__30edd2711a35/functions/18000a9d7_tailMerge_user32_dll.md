# __tailMerge_user32_dll

- ea: `0x18000a9d7`
- end: `0x18000aa50`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aa56`
- `0x18000aa68`
- `0x18000aa7a`
- `0x18000aa8c`
- `0x18000aa9e`
- `0x18000aab0`

## callees

- `0x180006050`
- `0x18000a9d7`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a9d7  mov     [rsp+arg_0], rcx
0x18000a9dc  mov     [rsp+arg_8], rdx
0x18000a9e1  mov     [rsp+arg_10], r8
0x18000a9e6  mov     [rsp+arg_18], r9
0x18000a9eb  sub     rsp, 68h
0x18000a9ef  movdqa  [rsp+68h+var_48], xmm0
0x18000a9f5  movdqa  [rsp+68h+var_38], xmm1
0x18000a9fb  movdqa  [rsp+68h+var_28], xmm2
0x18000aa01  movdqa  [rsp+68h+var_18], xmm3
0x18000aa07  mov     rdx, rax
0x18000aa0a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x18000aa11  call    __delayLoadHelper2
0x18000aa16  movdqa  xmm0, [rsp+68h+var_48]
0x18000aa1c  movdqa  xmm1, [rsp+68h+var_38]
0x18000aa22  movdqa  xmm2, [rsp+68h+var_28]
0x18000aa28  movdqa  xmm3, [rsp+68h+var_18]
0x18000aa2e  mov     rcx, [rsp+68h+arg_0]
0x18000aa33  mov     rdx, [rsp+68h+arg_8]
0x18000aa38  mov     r8, [rsp+68h+arg_10]
0x18000aa40  mov     r9, [rsp+68h+arg_18]
0x18000aa48  add     rsp, 68h
0x18000aa4c  jmp     short $+2
0x18000aa4e  jmp     rax
```
