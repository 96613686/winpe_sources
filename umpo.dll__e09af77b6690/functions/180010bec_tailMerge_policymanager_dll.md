# __tailMerge_policymanager_dll

- ea: `0x180010bec`
- end: `0x180010c65`
- name: `__tailMerge_policymanager_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180010c6b`
- `0x180010c7d`

## callees

- `0x180010bec`
- `0x180018770`

## pseudocode

```c
__int64 __fastcall _tailMerge_policymanager_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_policymanager_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010bec  mov     [rsp+arg_0], rcx
0x180010bf1  mov     [rsp+arg_8], rdx
0x180010bf6  mov     [rsp+arg_10], r8
0x180010bfb  mov     [rsp+arg_18], r9
0x180010c00  sub     rsp, 68h
0x180010c04  movdqa  [rsp+68h+var_48], xmm0
0x180010c0a  movdqa  [rsp+68h+var_38], xmm1
0x180010c10  movdqa  [rsp+68h+var_28], xmm2
0x180010c16  movdqa  [rsp+68h+var_18], xmm3
0x180010c1c  mov     rdx, rax
0x180010c1f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_policymanager_dll
0x180010c26  call    __delayLoadHelper2
0x180010c2b  movdqa  xmm0, [rsp+68h+var_48]
0x180010c31  movdqa  xmm1, [rsp+68h+var_38]
0x180010c37  movdqa  xmm2, [rsp+68h+var_28]
0x180010c3d  movdqa  xmm3, [rsp+68h+var_18]
0x180010c43  mov     rcx, [rsp+68h+arg_0]
0x180010c48  mov     rdx, [rsp+68h+arg_8]
0x180010c4d  mov     r8, [rsp+68h+arg_10]
0x180010c55  mov     r9, [rsp+68h+arg_18]
0x180010c5d  add     rsp, 68h
0x180010c61  jmp     short $+2
0x180010c63  jmp     rax
```
