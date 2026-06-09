# __tailMerge_oleaut32_dll

- ea: `0x100439cf4`
- end: `0x100439d6d`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100439ce8`
- `0x100439d73`
- `0x100439d85`
- `0x100439d97`
- `0x100439da9`
- `0x100439dbb`
- `0x100439dcd`

## callees

- `0x100439a10`
- `0x100439cf4`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x100439cf4  mov     [rsp+arg_0], rcx
0x100439cf9  mov     [rsp+arg_8], rdx
0x100439cfe  mov     [rsp+arg_10], r8
0x100439d03  mov     [rsp+arg_18], r9
0x100439d08  sub     rsp, 68h
0x100439d0c  movdqa  [rsp+68h+var_48], xmm0
0x100439d12  movdqa  [rsp+68h+var_38], xmm1
0x100439d18  movdqa  [rsp+68h+var_28], xmm2
0x100439d1e  movdqa  [rsp+68h+var_18], xmm3
0x100439d24  mov     rdx, rax
0x100439d27  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x100439d2e  call    __delayLoadHelper2
0x100439d33  movdqa  xmm0, [rsp+68h+var_48]
0x100439d39  movdqa  xmm1, [rsp+68h+var_38]
0x100439d3f  movdqa  xmm2, [rsp+68h+var_28]
0x100439d45  movdqa  xmm3, [rsp+68h+var_18]
0x100439d4b  mov     rcx, [rsp+68h+arg_0]
0x100439d50  mov     rdx, [rsp+68h+arg_8]
0x100439d55  mov     r8, [rsp+68h+arg_10]
0x100439d5d  mov     r9, [rsp+68h+arg_18]
0x100439d65  add     rsp, 68h
0x100439d69  jmp     short $+2
0x100439d6b  jmp     rax
```
