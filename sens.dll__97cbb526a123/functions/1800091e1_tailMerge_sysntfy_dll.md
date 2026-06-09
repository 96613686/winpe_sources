# __tailMerge_sysntfy_dll

- ea: `0x1800091e1`
- end: `0x18000925a`
- name: `__tailMerge_sysntfy_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009260`
- `0x180009272`

## callees

- `0x180006a50`
- `0x1800091e1`

## pseudocode

```c
__int64 __fastcall _tailMerge_sysntfy_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_sysntfy_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800091e1  mov     [rsp+arg_0], rcx
0x1800091e6  mov     [rsp+arg_8], rdx
0x1800091eb  mov     [rsp+arg_10], r8
0x1800091f0  mov     [rsp+arg_18], r9
0x1800091f5  sub     rsp, 68h
0x1800091f9  movdqa  [rsp+68h+var_48], xmm0
0x1800091ff  movdqa  [rsp+68h+var_38], xmm1
0x180009205  movdqa  [rsp+68h+var_28], xmm2
0x18000920b  movdqa  [rsp+68h+var_18], xmm3
0x180009211  mov     rdx, rax
0x180009214  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sysntfy_dll
0x18000921b  call    __delayLoadHelper2
0x180009220  movdqa  xmm0, [rsp+68h+var_48]
0x180009226  movdqa  xmm1, [rsp+68h+var_38]
0x18000922c  movdqa  xmm2, [rsp+68h+var_28]
0x180009232  movdqa  xmm3, [rsp+68h+var_18]
0x180009238  mov     rcx, [rsp+68h+arg_0]
0x18000923d  mov     rdx, [rsp+68h+arg_8]
0x180009242  mov     r8, [rsp+68h+arg_10]
0x18000924a  mov     r9, [rsp+68h+arg_18]
0x180009252  add     rsp, 68h
0x180009256  jmp     short $+2
0x180009258  jmp     rax
```
