# __tailMerge_mmdevapi_dll

- ea: `0x18001191e`
- end: `0x180011997`
- name: `__tailMerge_mmdevapi_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001199d`
- `0x1800119af`

## callees

- `0x18000f240`
- `0x18001191e`

## pseudocode

```c
__int64 __fastcall _tailMerge_mmdevapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mmdevapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001191e  mov     [rsp+arg_0], rcx
0x180011923  mov     [rsp+arg_8], rdx
0x180011928  mov     [rsp+arg_10], r8
0x18001192d  mov     [rsp+arg_18], r9
0x180011932  sub     rsp, 68h
0x180011936  movdqa  [rsp+68h+var_48], xmm0
0x18001193c  movdqa  [rsp+68h+var_38], xmm1
0x180011942  movdqa  [rsp+68h+var_28], xmm2
0x180011948  movdqa  [rsp+68h+var_18], xmm3
0x18001194e  mov     rdx, rax
0x180011951  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mmdevapi_dll
0x180011958  call    __delayLoadHelper2
0x18001195d  movdqa  xmm0, [rsp+68h+var_48]
0x180011963  movdqa  xmm1, [rsp+68h+var_38]
0x180011969  movdqa  xmm2, [rsp+68h+var_28]
0x18001196f  movdqa  xmm3, [rsp+68h+var_18]
0x180011975  mov     rcx, [rsp+68h+arg_0]
0x18001197a  mov     rdx, [rsp+68h+arg_8]
0x18001197f  mov     r8, [rsp+68h+arg_10]
0x180011987  mov     r9, [rsp+68h+arg_18]
0x18001198f  add     rsp, 68h
0x180011993  jmp     short $+2
0x180011995  jmp     rax
```
