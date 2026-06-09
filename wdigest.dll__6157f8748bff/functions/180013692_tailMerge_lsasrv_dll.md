# __tailMerge_lsasrv_dll

- ea: `0x180013692`
- end: `0x18001370b`
- name: `__tailMerge_lsasrv_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013711`
- `0x180013723`
- `0x180013735`
- `0x180013747`
- `0x180013759`
- `0x18001376b`
- `0x18001377d`

## callees

- `0x180013692`
- `0x1800376a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_lsasrv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_lsasrv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180013692  mov     [rsp+arg_0], rcx
0x180013697  mov     [rsp+arg_8], rdx
0x18001369c  mov     [rsp+arg_10], r8
0x1800136a1  mov     [rsp+arg_18], r9
0x1800136a6  sub     rsp, 68h
0x1800136aa  movdqa  [rsp+68h+var_48], xmm0
0x1800136b0  movdqa  [rsp+68h+var_38], xmm1
0x1800136b6  movdqa  [rsp+68h+var_28], xmm2
0x1800136bc  movdqa  [rsp+68h+var_18], xmm3
0x1800136c2  mov     rdx, rax
0x1800136c5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_lsasrv_dll
0x1800136cc  call    __delayLoadHelper2
0x1800136d1  movdqa  xmm0, [rsp+68h+var_48]
0x1800136d7  movdqa  xmm1, [rsp+68h+var_38]
0x1800136dd  movdqa  xmm2, [rsp+68h+var_28]
0x1800136e3  movdqa  xmm3, [rsp+68h+var_18]
0x1800136e9  mov     rcx, [rsp+68h+arg_0]
0x1800136ee  mov     rdx, [rsp+68h+arg_8]
0x1800136f3  mov     r8, [rsp+68h+arg_10]
0x1800136fb  mov     r9, [rsp+68h+arg_18]
0x180013703  add     rsp, 68h
0x180013707  jmp     short $+2
0x180013709  jmp     rax
```
