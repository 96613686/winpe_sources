# __tailMerge_ole32_dll

- ea: `0x180003056`
- end: `0x1800030cf`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800030d5`
- `0x1800030fc`
- `0x18000311c`
- `0x18000313c`
- `0x18000315c`
- `0x18000317c`
- `0x18000319c`
- `0x1800031bc`
- `0x1800031ce`

## callees

- `0x180001850`
- `0x180003056`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003056  mov     [rsp+arg_0], rcx
0x18000305b  mov     [rsp+arg_8], rdx
0x180003060  mov     [rsp+arg_10], r8
0x180003065  mov     [rsp+arg_18], r9
0x18000306a  sub     rsp, 68h
0x18000306e  movdqa  [rsp+68h+var_48], xmm0
0x180003074  movdqa  [rsp+68h+var_38], xmm1
0x18000307a  movdqa  [rsp+68h+var_28], xmm2
0x180003080  movdqa  [rsp+68h+var_18], xmm3
0x180003086  mov     rdx, rax
0x180003089  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x180003090  call    __delayLoadHelper2
0x180003095  movdqa  xmm0, [rsp+68h+var_48]
0x18000309b  movdqa  xmm1, [rsp+68h+var_38]
0x1800030a1  movdqa  xmm2, [rsp+68h+var_28]
0x1800030a7  movdqa  xmm3, [rsp+68h+var_18]
0x1800030ad  mov     rcx, [rsp+68h+arg_0]
0x1800030b2  mov     rdx, [rsp+68h+arg_8]
0x1800030b7  mov     r8, [rsp+68h+arg_10]
0x1800030bf  mov     r9, [rsp+68h+arg_18]
0x1800030c7  add     rsp, 68h
0x1800030cb  jmp     short $+2
0x1800030cd  jmp     rax
```
