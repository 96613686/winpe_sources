# __tailMerge_ole32_dll

- ea: `0x180001a0c`
- end: `0x180001a85`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a8b`

## callees

- `0x180001a0c`
- `0x1800035c0`

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
0x180001a0c  mov     [rsp+arg_0], rcx
0x180001a11  mov     [rsp+arg_8], rdx
0x180001a16  mov     [rsp+arg_10], r8
0x180001a1b  mov     [rsp+arg_18], r9
0x180001a20  sub     rsp, 68h
0x180001a24  movdqa  [rsp+68h+var_48], xmm0
0x180001a2a  movdqa  [rsp+68h+var_38], xmm1
0x180001a30  movdqa  [rsp+68h+var_28], xmm2
0x180001a36  movdqa  [rsp+68h+var_18], xmm3
0x180001a3c  mov     rdx, rax
0x180001a3f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x180001a46  call    __delayLoadHelper2
0x180001a4b  movdqa  xmm0, [rsp+68h+var_48]
0x180001a51  movdqa  xmm1, [rsp+68h+var_38]
0x180001a57  movdqa  xmm2, [rsp+68h+var_28]
0x180001a5d  movdqa  xmm3, [rsp+68h+var_18]
0x180001a63  mov     rcx, [rsp+68h+arg_0]
0x180001a68  mov     rdx, [rsp+68h+arg_8]
0x180001a6d  mov     r8, [rsp+68h+arg_10]
0x180001a75  mov     r9, [rsp+68h+arg_18]
0x180001a7d  add     rsp, 68h
0x180001a81  jmp     short $+2
0x180001a83  jmp     rax
```
