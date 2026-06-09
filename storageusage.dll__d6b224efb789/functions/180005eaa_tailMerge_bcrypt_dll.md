# __tailMerge_bcrypt_dll

- ea: `0x180005eaa`
- end: `0x180005f23`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005f29`
- `0x180005f5f`
- `0x180005f71`
- `0x180005f83`
- `0x180005f95`
- `0x180005fa7`
- `0x180005fb9`

## callees

- `0x180005eaa`
- `0x18002ad80`

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
0x180005eaa  mov     [rsp+arg_0], rcx
0x180005eaf  mov     [rsp+arg_8], rdx
0x180005eb4  mov     [rsp+arg_10], r8
0x180005eb9  mov     [rsp+arg_18], r9
0x180005ebe  sub     rsp, 68h
0x180005ec2  movdqa  [rsp+68h+var_48], xmm0
0x180005ec8  movdqa  [rsp+68h+var_38], xmm1
0x180005ece  movdqa  [rsp+68h+var_28], xmm2
0x180005ed4  movdqa  [rsp+68h+var_18], xmm3
0x180005eda  mov     rdx, rax
0x180005edd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x180005ee4  call    __delayLoadHelper2
0x180005ee9  movdqa  xmm0, [rsp+68h+var_48]
0x180005eef  movdqa  xmm1, [rsp+68h+var_38]
0x180005ef5  movdqa  xmm2, [rsp+68h+var_28]
0x180005efb  movdqa  xmm3, [rsp+68h+var_18]
0x180005f01  mov     rcx, [rsp+68h+arg_0]
0x180005f06  mov     rdx, [rsp+68h+arg_8]
0x180005f0b  mov     r8, [rsp+68h+arg_10]
0x180005f13  mov     r9, [rsp+68h+arg_18]
0x180005f1b  add     rsp, 68h
0x180005f1f  jmp     short $+2
0x180005f21  jmp     rax
```
