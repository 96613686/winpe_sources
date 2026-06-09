# __tailMerge_setupapi_dll

- ea: `0x18000ab47`
- end: `0x18000abc0`
- name: `__tailMerge_setupapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000abc6`
- `0x18000abd8`
- `0x18000abea`
- `0x18000abfc`
- `0x18000ac0e`
- `0x18000ac20`
- `0x18000ac32`
- `0x18000ac44`
- `0x18000ac56`
- `0x18000ac68`
- `0x18000ac7a`
- `0x18000ac8c`
- `0x18000ac9e`
- `0x18000acb0`
- `0x18000acc2`
- `0x18000acd4`
- `0x18000ace6`
- `0x18000acf8`

## callees

- `0x180006050`
- `0x18000ab47`

## pseudocode

```c
__int64 __fastcall _tailMerge_setupapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_setupapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ab47  mov     [rsp+arg_0], rcx
0x18000ab4c  mov     [rsp+arg_8], rdx
0x18000ab51  mov     [rsp+arg_10], r8
0x18000ab56  mov     [rsp+arg_18], r9
0x18000ab5b  sub     rsp, 68h
0x18000ab5f  movdqa  [rsp+68h+var_48], xmm0
0x18000ab65  movdqa  [rsp+68h+var_38], xmm1
0x18000ab6b  movdqa  [rsp+68h+var_28], xmm2
0x18000ab71  movdqa  [rsp+68h+var_18], xmm3
0x18000ab77  mov     rdx, rax
0x18000ab7a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_setupapi_dll
0x18000ab81  call    __delayLoadHelper2
0x18000ab86  movdqa  xmm0, [rsp+68h+var_48]
0x18000ab8c  movdqa  xmm1, [rsp+68h+var_38]
0x18000ab92  movdqa  xmm2, [rsp+68h+var_28]
0x18000ab98  movdqa  xmm3, [rsp+68h+var_18]
0x18000ab9e  mov     rcx, [rsp+68h+arg_0]
0x18000aba3  mov     rdx, [rsp+68h+arg_8]
0x18000aba8  mov     r8, [rsp+68h+arg_10]
0x18000abb0  mov     r9, [rsp+68h+arg_18]
0x18000abb8  add     rsp, 68h
0x18000abbc  jmp     short $+2
0x18000abbe  jmp     rax
```
