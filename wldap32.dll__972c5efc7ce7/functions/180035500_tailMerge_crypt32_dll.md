# __tailMerge_crypt32_dll

- ea: `0x180035500`
- end: `0x180035579`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003557f`
- `0x180035591`

## callees

- `0x18002be40`
- `0x180035500`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180035500  mov     [rsp+arg_0], rcx
0x180035505  mov     [rsp+arg_8], rdx
0x18003550a  mov     [rsp+arg_10], r8
0x18003550f  mov     [rsp+arg_18], r9
0x180035514  sub     rsp, 68h
0x180035518  movdqa  [rsp+68h+var_48], xmm0
0x18003551e  movdqa  [rsp+68h+var_38], xmm1
0x180035524  movdqa  [rsp+68h+var_28], xmm2
0x18003552a  movdqa  [rsp+68h+var_18], xmm3
0x180035530  mov     rdx, rax
0x180035533  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x18003553a  call    __delayLoadHelper2
0x18003553f  movdqa  xmm0, [rsp+68h+var_48]
0x180035545  movdqa  xmm1, [rsp+68h+var_38]
0x18003554b  movdqa  xmm2, [rsp+68h+var_28]
0x180035551  movdqa  xmm3, [rsp+68h+var_18]
0x180035557  mov     rcx, [rsp+68h+arg_0]
0x18003555c  mov     rdx, [rsp+68h+arg_8]
0x180035561  mov     r8, [rsp+68h+arg_10]
0x180035569  mov     r9, [rsp+68h+arg_18]
0x180035571  add     rsp, 68h
0x180035575  jmp     short $+2
0x180035577  jmp     rax
```
