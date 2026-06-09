# __tailMerge_cryptsp_dll

- ea: `0x18000262b`
- end: `0x1800026a4`
- name: `__tailMerge_cryptsp_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800026aa`
- `0x1800026bc`
- `0x1800026ce`
- `0x1800026e0`
- `0x1800026f2`
- `0x180002704`

## callees

- `0x18000262b`
- `0x18002d6a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptsp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptsp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000262b  mov     [rsp+arg_0], rcx
0x180002630  mov     [rsp+arg_8], rdx
0x180002635  mov     [rsp+arg_10], r8
0x18000263a  mov     [rsp+arg_18], r9
0x18000263f  sub     rsp, 68h
0x180002643  movdqa  [rsp+68h+var_48], xmm0
0x180002649  movdqa  [rsp+68h+var_38], xmm1
0x18000264f  movdqa  [rsp+68h+var_28], xmm2
0x180002655  movdqa  [rsp+68h+var_18], xmm3
0x18000265b  mov     rdx, rax
0x18000265e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptsp_dll
0x180002665  call    __delayLoadHelper2
0x18000266a  movdqa  xmm0, [rsp+68h+var_48]
0x180002670  movdqa  xmm1, [rsp+68h+var_38]
0x180002676  movdqa  xmm2, [rsp+68h+var_28]
0x18000267c  movdqa  xmm3, [rsp+68h+var_18]
0x180002682  mov     rcx, [rsp+68h+arg_0]
0x180002687  mov     rdx, [rsp+68h+arg_8]
0x18000268c  mov     r8, [rsp+68h+arg_10]
0x180002694  mov     r9, [rsp+68h+arg_18]
0x18000269c  add     rsp, 68h
0x1800026a0  jmp     short $+2
0x1800026a2  jmp     rax
```
