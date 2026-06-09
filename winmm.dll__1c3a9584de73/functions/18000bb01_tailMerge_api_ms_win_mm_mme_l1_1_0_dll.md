# __tailMerge_api_ms_win_mm_mme_l1_1_0_dll

- ea: `0x18000bb01`
- end: `0x18000bb7a`
- name: `__tailMerge_api_ms_win_mm_mme_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `102`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000bb80`
- `0x18000bb92`
- `0x18000bba4`
- `0x18000bbb6`
- `0x18000bbc8`
- `0x18000bbda`
- `0x18000bbec`
- `0x18000bbfe`
- `0x18000bc10`
- `0x18000bc22`
- `0x18000bc34`
- `0x18000bc46`
- `0x18000bc58`
- `0x18000bc6a`
- `0x18000bc7c`
- `0x18000bc8e`
- `0x18000bca0`
- `0x18000bcb2`
- `0x18000bcc4`
- `0x18000bcd6`
- `0x18000bce8`
- `0x18000bcfa`
- `0x18000bd0c`
- `0x18000bd1e`
- `0x18000bd30`
- `0x18000bd42`
- `0x18000bd54`
- `0x18000bd66`
- `0x18000bd78`
- `0x18000bd8a`
- `0x18000bd9c`
- `0x18000bdae`
- `0x18000bdc0`
- `0x18000bdd2`
- `0x18000bde4`
- `0x18000bdf6`
- `0x18000be08`
- `0x18000be1a`
- `0x18000be2c`
- `0x18000be3e`
- `0x18000be50`
- `0x18000be62`
- `0x18000be74`
- `0x18000be86`
- `0x18000be98`
- `0x18000beaa`
- `0x18000bebc`
- `0x18000bece`
- `0x18000bee0`
- `0x18000bef2`

## callees

- `0x180009370`
- `0x18000bb01`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_mm_mme_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_mm_mme_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000bb01  mov     [rsp+arg_0], rcx
0x18000bb06  mov     [rsp+arg_8], rdx
0x18000bb0b  mov     [rsp+arg_10], r8
0x18000bb10  mov     [rsp+arg_18], r9
0x18000bb15  sub     rsp, 68h
0x18000bb19  movdqa  [rsp+68h+var_48], xmm0
0x18000bb1f  movdqa  [rsp+68h+var_38], xmm1
0x18000bb25  movdqa  [rsp+68h+var_28], xmm2
0x18000bb2b  movdqa  [rsp+68h+var_18], xmm3
0x18000bb31  mov     rdx, rax
0x18000bb34  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_mm_mme_l1_1_0_dll
0x18000bb3b  call    __delayLoadHelper2
0x18000bb40  movdqa  xmm0, [rsp+68h+var_48]
0x18000bb46  movdqa  xmm1, [rsp+68h+var_38]
0x18000bb4c  movdqa  xmm2, [rsp+68h+var_28]
0x18000bb52  movdqa  xmm3, [rsp+68h+var_18]
0x18000bb58  mov     rcx, [rsp+68h+arg_0]
0x18000bb5d  mov     rdx, [rsp+68h+arg_8]
0x18000bb62  mov     r8, [rsp+68h+arg_10]
0x18000bb6a  mov     r9, [rsp+68h+arg_18]
0x18000bb72  add     rsp, 68h
0x18000bb76  jmp     short $+2
0x18000bb78  jmp     rax
```
