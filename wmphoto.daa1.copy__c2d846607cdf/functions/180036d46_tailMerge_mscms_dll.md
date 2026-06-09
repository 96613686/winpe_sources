# __tailMerge_mscms_dll

- ea: `0x180036d46`
- end: `0x180036dbf`
- name: `__tailMerge_mscms_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180036dc5`
- `0x180036dd7`
- `0x180036de9`
- `0x180036dfb`
- `0x180036e0d`

## callees

- `0x180036d46`
- `0x180043490`

## pseudocode

```c
__int64 __fastcall _tailMerge_mscms_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mscms_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180036d46  mov     [rsp+arg_0], rcx
0x180036d4b  mov     [rsp+arg_8], rdx
0x180036d50  mov     [rsp+arg_10], r8
0x180036d55  mov     [rsp+arg_18], r9
0x180036d5a  sub     rsp, 68h
0x180036d5e  movdqa  [rsp+68h+var_48], xmm0
0x180036d64  movdqa  [rsp+68h+var_38], xmm1
0x180036d6a  movdqa  [rsp+68h+var_28], xmm2
0x180036d70  movdqa  [rsp+68h+var_18], xmm3
0x180036d76  mov     rdx, rax
0x180036d79  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mscms_dll
0x180036d80  call    __delayLoadHelper2
0x180036d85  movdqa  xmm0, [rsp+68h+var_48]
0x180036d8b  movdqa  xmm1, [rsp+68h+var_38]
0x180036d91  movdqa  xmm2, [rsp+68h+var_28]
0x180036d97  movdqa  xmm3, [rsp+68h+var_18]
0x180036d9d  mov     rcx, [rsp+68h+arg_0]
0x180036da2  mov     rdx, [rsp+68h+arg_8]
0x180036da7  mov     r8, [rsp+68h+arg_10]
0x180036daf  mov     r9, [rsp+68h+arg_18]
0x180036db7  add     rsp, 68h
0x180036dbb  jmp     short $+2
0x180036dbd  jmp     rax
```
