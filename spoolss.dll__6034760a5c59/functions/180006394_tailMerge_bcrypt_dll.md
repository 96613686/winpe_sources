# __tailMerge_bcrypt_dll

- ea: `0x180006394`
- end: `0x18000640d`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006413`
- `0x180006425`
- `0x180006437`
- `0x180006449`
- `0x18000645b`
- `0x18000646d`
- `0x18000647f`

## callees

- `0x180006394`
- `0x180014d80`

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
0x180006394  mov     [rsp+arg_0], rcx
0x180006399  mov     [rsp+arg_8], rdx
0x18000639e  mov     [rsp+arg_10], r8
0x1800063a3  mov     [rsp+arg_18], r9
0x1800063a8  sub     rsp, 68h
0x1800063ac  movdqa  [rsp+68h+var_48], xmm0
0x1800063b2  movdqa  [rsp+68h+var_38], xmm1
0x1800063b8  movdqa  [rsp+68h+var_28], xmm2
0x1800063be  movdqa  [rsp+68h+var_18], xmm3
0x1800063c4  mov     rdx, rax
0x1800063c7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x1800063ce  call    __delayLoadHelper2
0x1800063d3  movdqa  xmm0, [rsp+68h+var_48]
0x1800063d9  movdqa  xmm1, [rsp+68h+var_38]
0x1800063df  movdqa  xmm2, [rsp+68h+var_28]
0x1800063e5  movdqa  xmm3, [rsp+68h+var_18]
0x1800063eb  mov     rcx, [rsp+68h+arg_0]
0x1800063f0  mov     rdx, [rsp+68h+arg_8]
0x1800063f5  mov     r8, [rsp+68h+arg_10]
0x1800063fd  mov     r9, [rsp+68h+arg_18]
0x180006405  add     rsp, 68h
0x180006409  jmp     short $+2
0x18000640b  jmp     rax
```
