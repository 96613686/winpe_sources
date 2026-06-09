# __tailMerge_api_ms_win_eventing_provider_l1_1_0_dll

- ea: `0x14001a7c1`
- end: `0x14001a83a`
- name: `__tailMerge_api_ms_win_eventing_provider_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001a840`
- `0x14001a852`
- `0x14001a864`
- `0x14001a876`

## callees

- `0x14001a7c1`
- `0x14001a890`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_eventing_provider_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_provider_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14001a7c1  mov     [rsp+arg_0], rcx
0x14001a7c6  mov     [rsp+arg_8], rdx
0x14001a7cb  mov     [rsp+arg_10], r8
0x14001a7d0  mov     [rsp+arg_18], r9
0x14001a7d5  sub     rsp, 68h
0x14001a7d9  movdqa  [rsp+68h+var_48], xmm0
0x14001a7df  movdqa  [rsp+68h+var_38], xmm1
0x14001a7e5  movdqa  [rsp+68h+var_28], xmm2
0x14001a7eb  movdqa  [rsp+68h+var_18], xmm3
0x14001a7f1  mov     rdx, rax
0x14001a7f4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_provider_l1_1_0_dll
0x14001a7fb  call    __delayLoadHelper2
0x14001a800  movdqa  xmm0, [rsp+68h+var_48]
0x14001a806  movdqa  xmm1, [rsp+68h+var_38]
0x14001a80c  movdqa  xmm2, [rsp+68h+var_28]
0x14001a812  movdqa  xmm3, [rsp+68h+var_18]
0x14001a818  mov     rcx, [rsp+68h+arg_0]
0x14001a81d  mov     rdx, [rsp+68h+arg_8]
0x14001a822  mov     r8, [rsp+68h+arg_10]
0x14001a82a  mov     r9, [rsp+68h+arg_18]
0x14001a832  add     rsp, 68h
0x14001a836  jmp     short $+2
0x14001a838  jmp     rax
```
