# __tailMerge_wlanapi_dll

- ea: `0x180002407`
- end: `0x180002480`
- name: `__tailMerge_wlanapi_dll`
- size: `121`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002486`
- `0x180002498`
- `0x1800024aa`
- `0x1800024bc`
- `0x1800024ce`
- `0x1800024e0`
- `0x18000257d`
- `0x18000258f`
- `0x1800025a1`
- `0x1800025b3`
- `0x1800025c5`
- `0x1800025d7`
- `0x1800025e9`
- `0x1800025fb`
- `0x18000260d`
- `0x18000261f`
- `0x180002716`
- `0x180002728`
- `0x18000273a`

## callees

- `0x180002407`
- `0x18002d6a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_wlanapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wlanapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002407  mov     [rsp+arg_0], rcx
0x18000240c  mov     [rsp+arg_8], rdx
0x180002411  mov     [rsp+arg_10], r8
0x180002416  mov     [rsp+arg_18], r9
0x18000241b  sub     rsp, 68h
0x18000241f  movdqa  [rsp+68h+var_48], xmm0
0x180002425  movdqa  [rsp+68h+var_38], xmm1
0x18000242b  movdqa  [rsp+68h+var_28], xmm2
0x180002431  movdqa  [rsp+68h+var_18], xmm3
0x180002437  mov     rdx, rax
0x18000243a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wlanapi_dll
0x180002441  call    __delayLoadHelper2
0x180002446  movdqa  xmm0, [rsp+68h+var_48]
0x18000244c  movdqa  xmm1, [rsp+68h+var_38]
0x180002452  movdqa  xmm2, [rsp+68h+var_28]
0x180002458  movdqa  xmm3, [rsp+68h+var_18]
0x18000245e  mov     rcx, [rsp+68h+arg_0]
0x180002463  mov     rdx, [rsp+68h+arg_8]
0x180002468  mov     r8, [rsp+68h+arg_10]
0x180002470  mov     r9, [rsp+68h+arg_18]
0x180002478  add     rsp, 68h
0x18000247c  jmp     short $+2
0x18000247e  jmp     rax
```
