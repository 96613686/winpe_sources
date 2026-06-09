# __tailMerge_eappcfg_dll

- ea: `0x180002498`
- end: `0x180002511`
- name: `__tailMerge_eappcfg_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002517`
- `0x180002529`
- `0x18000253b`
- `0x18000254d`
- `0x180002af8`
- `0x180002b0a`

## callees

- `0x180002498`
- `0x18001be40`

## pseudocode

```c
__int64 __fastcall _tailMerge_eappcfg_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_eappcfg_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002498  mov     [rsp+arg_0], rcx
0x18000249d  mov     [rsp+arg_8], rdx
0x1800024a2  mov     [rsp+arg_10], r8
0x1800024a7  mov     [rsp+arg_18], r9
0x1800024ac  sub     rsp, 68h
0x1800024b0  movdqa  [rsp+68h+var_48], xmm0
0x1800024b6  movdqa  [rsp+68h+var_38], xmm1
0x1800024bc  movdqa  [rsp+68h+var_28], xmm2
0x1800024c2  movdqa  [rsp+68h+var_18], xmm3
0x1800024c8  mov     rdx, rax
0x1800024cb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_eappcfg_dll
0x1800024d2  call    __delayLoadHelper2
0x1800024d7  movdqa  xmm0, [rsp+68h+var_48]
0x1800024dd  movdqa  xmm1, [rsp+68h+var_38]
0x1800024e3  movdqa  xmm2, [rsp+68h+var_28]
0x1800024e9  movdqa  xmm3, [rsp+68h+var_18]
0x1800024ef  mov     rcx, [rsp+68h+arg_0]
0x1800024f4  mov     rdx, [rsp+68h+arg_8]
0x1800024f9  mov     r8, [rsp+68h+arg_10]
0x180002501  mov     r9, [rsp+68h+arg_18]
0x180002509  add     rsp, 68h
0x18000250d  jmp     short $+2
0x18000250f  jmp     rax
```
