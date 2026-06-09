# __tailMerge_oleaut32_dll

- ea: `0x100423d49`
- end: `0x100423dc2`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100423d3d`
- `0x100423dc8`
- `0x100423dda`
- `0x100423dec`
- `0x100423dfe`

## callees

- `0x100423d49`
- `0x1004241e0`

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
0x100423d49  mov     [rsp+arg_0], rcx
0x100423d4e  mov     [rsp+arg_8], rdx
0x100423d53  mov     [rsp+arg_10], r8
0x100423d58  mov     [rsp+arg_18], r9
0x100423d5d  sub     rsp, 68h
0x100423d61  movdqa  [rsp+68h+var_48], xmm0
0x100423d67  movdqa  [rsp+68h+var_38], xmm1
0x100423d6d  movdqa  [rsp+68h+var_28], xmm2
0x100423d73  movdqa  [rsp+68h+var_18], xmm3
0x100423d79  mov     rdx, rax
0x100423d7c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x100423d83  call    __delayLoadHelper2
0x100423d88  movdqa  xmm0, [rsp+68h+var_48]
0x100423d8e  movdqa  xmm1, [rsp+68h+var_38]
0x100423d94  movdqa  xmm2, [rsp+68h+var_28]
0x100423d9a  movdqa  xmm3, [rsp+68h+var_18]
0x100423da0  mov     rcx, [rsp+68h+arg_0]
0x100423da5  mov     rdx, [rsp+68h+arg_8]
0x100423daa  mov     r8, [rsp+68h+arg_10]
0x100423db2  mov     r9, [rsp+68h+arg_18]
0x100423dba  add     rsp, 68h
0x100423dbe  jmp     short $+2
0x100423dc0  jmp     rax
```
