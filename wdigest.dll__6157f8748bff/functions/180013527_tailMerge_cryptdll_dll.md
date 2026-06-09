# __tailMerge_cryptdll_dll

- ea: `0x180013527`
- end: `0x1800135a0`
- name: `__tailMerge_cryptdll_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800135a6`

## callees

- `0x180013527`
- `0x1800376a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptdll_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptdll_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180013527  mov     [rsp+arg_0], rcx
0x18001352c  mov     [rsp+arg_8], rdx
0x180013531  mov     [rsp+arg_10], r8
0x180013536  mov     [rsp+arg_18], r9
0x18001353b  sub     rsp, 68h
0x18001353f  movdqa  [rsp+68h+var_48], xmm0
0x180013545  movdqa  [rsp+68h+var_38], xmm1
0x18001354b  movdqa  [rsp+68h+var_28], xmm2
0x180013551  movdqa  [rsp+68h+var_18], xmm3
0x180013557  mov     rdx, rax
0x18001355a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptdll_dll
0x180013561  call    __delayLoadHelper2
0x180013566  movdqa  xmm0, [rsp+68h+var_48]
0x18001356c  movdqa  xmm1, [rsp+68h+var_38]
0x180013572  movdqa  xmm2, [rsp+68h+var_28]
0x180013578  movdqa  xmm3, [rsp+68h+var_18]
0x18001357e  mov     rcx, [rsp+68h+arg_0]
0x180013583  mov     rdx, [rsp+68h+arg_8]
0x180013588  mov     r8, [rsp+68h+arg_10]
0x180013590  mov     r9, [rsp+68h+arg_18]
0x180013598  add     rsp, 68h
0x18001359c  jmp     short $+2
0x18001359e  jmp     rax
```
