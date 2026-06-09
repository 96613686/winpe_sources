# __tailMerge_winhttp_dll

- ea: `0x18000159c`
- end: `0x180001615`
- name: `__tailMerge_winhttp_dll`
- size: `121`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000161b`
- `0x18000162d`
- `0x18000163f`
- `0x180001651`
- `0x180001663`
- `0x180001675`
- `0x180001687`
- `0x180001699`
- `0x1800016ab`
- `0x1800016bd`
- `0x1800016cf`
- `0x1800016e1`
- `0x1800016f3`
- `0x180001705`
- `0x180001717`
- `0x180001729`
- `0x18000173b`
- `0x18000174d`

## callees

- `0x18000159c`
- `0x1800244c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_winhttp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winhttp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000159c  mov     [rsp+arg_0], rcx
0x1800015a1  mov     [rsp+arg_8], rdx
0x1800015a6  mov     [rsp+arg_10], r8
0x1800015ab  mov     [rsp+arg_18], r9
0x1800015b0  sub     rsp, 68h
0x1800015b4  movdqa  [rsp+68h+var_48], xmm0
0x1800015ba  movdqa  [rsp+68h+var_38], xmm1
0x1800015c0  movdqa  [rsp+68h+var_28], xmm2
0x1800015c6  movdqa  [rsp+68h+var_18], xmm3
0x1800015cc  mov     rdx, rax
0x1800015cf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winhttp_dll
0x1800015d6  call    __delayLoadHelper2
0x1800015db  movdqa  xmm0, [rsp+68h+var_48]
0x1800015e1  movdqa  xmm1, [rsp+68h+var_38]
0x1800015e7  movdqa  xmm2, [rsp+68h+var_28]
0x1800015ed  movdqa  xmm3, [rsp+68h+var_18]
0x1800015f3  mov     rcx, [rsp+68h+arg_0]
0x1800015f8  mov     rdx, [rsp+68h+arg_8]
0x1800015fd  mov     r8, [rsp+68h+arg_10]
0x180001605  mov     r9, [rsp+68h+arg_18]
0x18000160d  add     rsp, 68h
0x180001611  jmp     short $+2
0x180001613  jmp     rax
```
