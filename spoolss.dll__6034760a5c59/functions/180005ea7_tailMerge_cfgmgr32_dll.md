# __tailMerge_cfgmgr32_dll

- ea: `0x180005ea7`
- end: `0x180005f20`
- name: `__tailMerge_cfgmgr32_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005f26`
- `0x180005f38`
- `0x180005f4a`
- `0x180005f5c`
- `0x180005f6e`
- `0x18000623c`

## callees

- `0x180005ea7`
- `0x180014d80`

## pseudocode

```c
__int64 __fastcall _tailMerge_cfgmgr32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cfgmgr32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005ea7  mov     [rsp+arg_0], rcx
0x180005eac  mov     [rsp+arg_8], rdx
0x180005eb1  mov     [rsp+arg_10], r8
0x180005eb6  mov     [rsp+arg_18], r9
0x180005ebb  sub     rsp, 68h
0x180005ebf  movdqa  [rsp+68h+var_48], xmm0
0x180005ec5  movdqa  [rsp+68h+var_38], xmm1
0x180005ecb  movdqa  [rsp+68h+var_28], xmm2
0x180005ed1  movdqa  [rsp+68h+var_18], xmm3
0x180005ed7  mov     rdx, rax
0x180005eda  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cfgmgr32_dll
0x180005ee1  call    __delayLoadHelper2
0x180005ee6  movdqa  xmm0, [rsp+68h+var_48]
0x180005eec  movdqa  xmm1, [rsp+68h+var_38]
0x180005ef2  movdqa  xmm2, [rsp+68h+var_28]
0x180005ef8  movdqa  xmm3, [rsp+68h+var_18]
0x180005efe  mov     rcx, [rsp+68h+arg_0]
0x180005f03  mov     rdx, [rsp+68h+arg_8]
0x180005f08  mov     r8, [rsp+68h+arg_10]
0x180005f10  mov     r9, [rsp+68h+arg_18]
0x180005f18  add     rsp, 68h
0x180005f1c  jmp     short $+2
0x180005f1e  jmp     rax
```
