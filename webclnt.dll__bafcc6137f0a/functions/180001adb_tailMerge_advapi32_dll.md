# __tailMerge_advapi32_dll

- ea: `0x180001adb`
- end: `0x180001b54`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b5a`
- `0x180001b6c`
- `0x180001b7e`
- `0x180001b90`
- `0x180001ba2`
- `0x180001bb4`
- `0x180001bc6`
- `0x180001bd8`
- `0x180001bea`
- `0x180001bfc`
- `0x180001c0e`
- `0x180001c20`
- `0x180001c32`
- `0x180001c44`
- `0x180001c56`

## callees

- `0x180001adb`
- `0x18002ce10`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001adb  mov     [rsp+arg_0], rcx
0x180001ae0  mov     [rsp+arg_8], rdx
0x180001ae5  mov     [rsp+arg_10], r8
0x180001aea  mov     [rsp+arg_18], r9
0x180001aef  sub     rsp, 68h
0x180001af3  movdqa  [rsp+68h+var_48], xmm0
0x180001af9  movdqa  [rsp+68h+var_38], xmm1
0x180001aff  movdqa  [rsp+68h+var_28], xmm2
0x180001b05  movdqa  [rsp+68h+var_18], xmm3
0x180001b0b  mov     rdx, rax
0x180001b0e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x180001b15  call    __delayLoadHelper2
0x180001b1a  movdqa  xmm0, [rsp+68h+var_48]
0x180001b20  movdqa  xmm1, [rsp+68h+var_38]
0x180001b26  movdqa  xmm2, [rsp+68h+var_28]
0x180001b2c  movdqa  xmm3, [rsp+68h+var_18]
0x180001b32  mov     rcx, [rsp+68h+arg_0]
0x180001b37  mov     rdx, [rsp+68h+arg_8]
0x180001b3c  mov     r8, [rsp+68h+arg_10]
0x180001b44  mov     r9, [rsp+68h+arg_18]
0x180001b4c  add     rsp, 68h
0x180001b50  jmp     short $+2
0x180001b52  jmp     rax
```
