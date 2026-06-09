# __tailMerge_samsrv_dll

- ea: `0x180013892`
- end: `0x18001390b`
- name: `__tailMerge_samsrv_dll`
- size: `121`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013911`
- `0x180013923`
- `0x180013935`
- `0x180013947`
- `0x180013959`
- `0x18001396b`
- `0x18001397d`
- `0x18001398f`
- `0x1800139a1`

## callees

- `0x180013892`
- `0x1800376a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_samsrv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_samsrv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180013892  mov     [rsp+arg_0], rcx
0x180013897  mov     [rsp+arg_8], rdx
0x18001389c  mov     [rsp+arg_10], r8
0x1800138a1  mov     [rsp+arg_18], r9
0x1800138a6  sub     rsp, 68h
0x1800138aa  movdqa  [rsp+68h+var_48], xmm0
0x1800138b0  movdqa  [rsp+68h+var_38], xmm1
0x1800138b6  movdqa  [rsp+68h+var_28], xmm2
0x1800138bc  movdqa  [rsp+68h+var_18], xmm3
0x1800138c2  mov     rdx, rax
0x1800138c5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_samsrv_dll
0x1800138cc  call    __delayLoadHelper2
0x1800138d1  movdqa  xmm0, [rsp+68h+var_48]
0x1800138d7  movdqa  xmm1, [rsp+68h+var_38]
0x1800138dd  movdqa  xmm2, [rsp+68h+var_28]
0x1800138e3  movdqa  xmm3, [rsp+68h+var_18]
0x1800138e9  mov     rcx, [rsp+68h+arg_0]
0x1800138ee  mov     rdx, [rsp+68h+arg_8]
0x1800138f3  mov     r8, [rsp+68h+arg_10]
0x1800138fb  mov     r9, [rsp+68h+arg_18]
0x180013903  add     rsp, 68h
0x180013907  jmp     short $+2
0x180013909  jmp     rax
```
