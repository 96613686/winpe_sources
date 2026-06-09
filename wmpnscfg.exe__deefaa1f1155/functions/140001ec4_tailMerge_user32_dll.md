# __tailMerge_user32_dll

- ea: `0x140001ec4`
- end: `0x140001f3d`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001f43`
- `0x140001f55`
- `0x140001f67`

## callees

- `0x140001ec4`
- `0x140007430`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001ec4  mov     [rsp+arg_0], rcx
0x140001ec9  mov     [rsp+arg_8], rdx
0x140001ece  mov     [rsp+arg_10], r8
0x140001ed3  mov     [rsp+arg_18], r9
0x140001ed8  sub     rsp, 68h
0x140001edc  movdqa  [rsp+68h+var_48], xmm0
0x140001ee2  movdqa  [rsp+68h+var_38], xmm1
0x140001ee8  movdqa  [rsp+68h+var_28], xmm2
0x140001eee  movdqa  [rsp+68h+var_18], xmm3
0x140001ef4  mov     rdx, rax
0x140001ef7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x140001efe  call    __delayLoadHelper2
0x140001f03  movdqa  xmm0, [rsp+68h+var_48]
0x140001f09  movdqa  xmm1, [rsp+68h+var_38]
0x140001f0f  movdqa  xmm2, [rsp+68h+var_28]
0x140001f15  movdqa  xmm3, [rsp+68h+var_18]
0x140001f1b  mov     rcx, [rsp+68h+arg_0]
0x140001f20  mov     rdx, [rsp+68h+arg_8]
0x140001f25  mov     r8, [rsp+68h+arg_10]
0x140001f2d  mov     r9, [rsp+68h+arg_18]
0x140001f35  add     rsp, 68h
0x140001f39  jmp     short $+2
0x140001f3b  jmp     rax
```
