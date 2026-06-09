# __tailMerge_cryptbase_dll

- ea: `0x180003cdc`
- end: `0x180003d55`
- name: `__tailMerge_cryptbase_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003d5b`

## callees

- `0x180003580`
- `0x180003cdc`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptbase_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptbase_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003cdc  mov     [rsp+arg_0], rcx
0x180003ce1  mov     [rsp+arg_8], rdx
0x180003ce6  mov     [rsp+arg_10], r8
0x180003ceb  mov     [rsp+arg_18], r9
0x180003cf0  sub     rsp, 68h
0x180003cf4  movdqa  [rsp+68h+var_48], xmm0
0x180003cfa  movdqa  [rsp+68h+var_38], xmm1
0x180003d00  movdqa  [rsp+68h+var_28], xmm2
0x180003d06  movdqa  [rsp+68h+var_18], xmm3
0x180003d0c  mov     rdx, rax
0x180003d0f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptbase_dll
0x180003d16  call    __delayLoadHelper2
0x180003d1b  movdqa  xmm0, [rsp+68h+var_48]
0x180003d21  movdqa  xmm1, [rsp+68h+var_38]
0x180003d27  movdqa  xmm2, [rsp+68h+var_28]
0x180003d2d  movdqa  xmm3, [rsp+68h+var_18]
0x180003d33  mov     rcx, [rsp+68h+arg_0]
0x180003d38  mov     rdx, [rsp+68h+arg_8]
0x180003d3d  mov     r8, [rsp+68h+arg_10]
0x180003d45  mov     r9, [rsp+68h+arg_18]
0x180003d4d  add     rsp, 68h
0x180003d51  jmp     short $+2
0x180003d53  jmp     rax
```
