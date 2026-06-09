# __tailMerge_samlib_dll

- ea: `0x180002ff2`
- end: `0x18000306b`
- name: `__tailMerge_samlib_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003071`
- `0x180003083`
- `0x180003095`
- `0x1800030a7`
- `0x1800030cb`
- `0x1800030dd`

## callees

- `0x180002ff2`
- `0x1800095f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_samlib_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_samlib_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002ff2  mov     [rsp+arg_0], rcx
0x180002ff7  mov     [rsp+arg_8], rdx
0x180002ffc  mov     [rsp+arg_10], r8
0x180003001  mov     [rsp+arg_18], r9
0x180003006  sub     rsp, 68h
0x18000300a  movdqa  [rsp+68h+var_48], xmm0
0x180003010  movdqa  [rsp+68h+var_38], xmm1
0x180003016  movdqa  [rsp+68h+var_28], xmm2
0x18000301c  movdqa  [rsp+68h+var_18], xmm3
0x180003022  mov     rdx, rax
0x180003025  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_samlib_dll
0x18000302c  call    __delayLoadHelper2
0x180003031  movdqa  xmm0, [rsp+68h+var_48]
0x180003037  movdqa  xmm1, [rsp+68h+var_38]
0x18000303d  movdqa  xmm2, [rsp+68h+var_28]
0x180003043  movdqa  xmm3, [rsp+68h+var_18]
0x180003049  mov     rcx, [rsp+68h+arg_0]
0x18000304e  mov     rdx, [rsp+68h+arg_8]
0x180003053  mov     r8, [rsp+68h+arg_10]
0x18000305b  mov     r9, [rsp+68h+arg_18]
0x180003063  add     rsp, 68h
0x180003067  jmp     short $+2
0x180003069  jmp     rax
```
