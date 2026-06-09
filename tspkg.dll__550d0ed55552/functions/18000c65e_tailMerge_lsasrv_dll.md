# __tailMerge_lsasrv_dll

- ea: `0x18000c65e`
- end: `0x18000c6d7`
- name: `__tailMerge_lsasrv_dll`
- size: `121`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c6dd`
- `0x18000c6ef`
- `0x18000c701`
- `0x18000c713`
- `0x18000c725`
- `0x18000c737`
- `0x18000c749`
- `0x18000c75b`
- `0x18000c76d`
- `0x18000c77f`
- `0x18000c791`
- `0x18000c7a3`

## callees

- `0x180009770`
- `0x18000c65e`

## pseudocode

```c
__int64 __fastcall _tailMerge_lsasrv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_lsasrv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c65e  mov     [rsp+arg_0], rcx
0x18000c663  mov     [rsp+arg_8], rdx
0x18000c668  mov     [rsp+arg_10], r8
0x18000c66d  mov     [rsp+arg_18], r9
0x18000c672  sub     rsp, 68h
0x18000c676  movdqa  [rsp+68h+var_48], xmm0
0x18000c67c  movdqa  [rsp+68h+var_38], xmm1
0x18000c682  movdqa  [rsp+68h+var_28], xmm2
0x18000c688  movdqa  [rsp+68h+var_18], xmm3
0x18000c68e  mov     rdx, rax
0x18000c691  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_lsasrv_dll
0x18000c698  call    __delayLoadHelper2
0x18000c69d  movdqa  xmm0, [rsp+68h+var_48]
0x18000c6a3  movdqa  xmm1, [rsp+68h+var_38]
0x18000c6a9  movdqa  xmm2, [rsp+68h+var_28]
0x18000c6af  movdqa  xmm3, [rsp+68h+var_18]
0x18000c6b5  mov     rcx, [rsp+68h+arg_0]
0x18000c6ba  mov     rdx, [rsp+68h+arg_8]
0x18000c6bf  mov     r8, [rsp+68h+arg_10]
0x18000c6c7  mov     r9, [rsp+68h+arg_18]
0x18000c6cf  add     rsp, 68h
0x18000c6d3  jmp     short $+2
0x18000c6d5  jmp     rax
```
