# __tailMerge_bcrypt_dll

- ea: `0x1800020eb`
- end: `0x180002164`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000216a`
- `0x18000217c`
- `0x18000218e`
- `0x1800021a0`
- `0x1800021b2`
- `0x1800021c4`
- `0x1800021d6`
- `0x1800021e8`
- `0x1800021fa`
- `0x18000220c`
- `0x18000221e`

## callees

- `0x1800020eb`
- `0x18003c140`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800020eb  mov     [rsp+arg_0], rcx
0x1800020f0  mov     [rsp+arg_8], rdx
0x1800020f5  mov     [rsp+arg_10], r8
0x1800020fa  mov     [rsp+arg_18], r9
0x1800020ff  sub     rsp, 68h
0x180002103  movdqa  [rsp+68h+var_48], xmm0
0x180002109  movdqa  [rsp+68h+var_38], xmm1
0x18000210f  movdqa  [rsp+68h+var_28], xmm2
0x180002115  movdqa  [rsp+68h+var_18], xmm3
0x18000211b  mov     rdx, rax
0x18000211e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x180002125  call    __delayLoadHelper2
0x18000212a  movdqa  xmm0, [rsp+68h+var_48]
0x180002130  movdqa  xmm1, [rsp+68h+var_38]
0x180002136  movdqa  xmm2, [rsp+68h+var_28]
0x18000213c  movdqa  xmm3, [rsp+68h+var_18]
0x180002142  mov     rcx, [rsp+68h+arg_0]
0x180002147  mov     rdx, [rsp+68h+arg_8]
0x18000214c  mov     r8, [rsp+68h+arg_10]
0x180002154  mov     r9, [rsp+68h+arg_18]
0x18000215c  add     rsp, 68h
0x180002160  jmp     short $+2
0x180002162  jmp     rax
```
