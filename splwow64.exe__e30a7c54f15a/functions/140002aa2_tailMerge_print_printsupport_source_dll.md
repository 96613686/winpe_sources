# __tailMerge_print_printsupport_source_dll

- ea: `0x140002aa2`
- end: `0x140002b1b`
- name: `__tailMerge_print_printsupport_source_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002b21`

## callees

- `0x140002aa2`
- `0x140014f70`

## pseudocode

```c
__int64 __fastcall _tailMerge_print_printsupport_source_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_print_printsupport_source_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002aa2  mov     [rsp+arg_0], rcx
0x140002aa7  mov     [rsp+arg_8], rdx
0x140002aac  mov     [rsp+arg_10], r8
0x140002ab1  mov     [rsp+arg_18], r9
0x140002ab6  sub     rsp, 68h
0x140002aba  movdqa  [rsp+68h+var_48], xmm0
0x140002ac0  movdqa  [rsp+68h+var_38], xmm1
0x140002ac6  movdqa  [rsp+68h+var_28], xmm2
0x140002acc  movdqa  [rsp+68h+var_18], xmm3
0x140002ad2  mov     rdx, rax
0x140002ad5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_print_printsupport_source_dll
0x140002adc  call    __delayLoadHelper2
0x140002ae1  movdqa  xmm0, [rsp+68h+var_48]
0x140002ae7  movdqa  xmm1, [rsp+68h+var_38]
0x140002aed  movdqa  xmm2, [rsp+68h+var_28]
0x140002af3  movdqa  xmm3, [rsp+68h+var_18]
0x140002af9  mov     rcx, [rsp+68h+arg_0]
0x140002afe  mov     rdx, [rsp+68h+arg_8]
0x140002b03  mov     r8, [rsp+68h+arg_10]
0x140002b0b  mov     r9, [rsp+68h+arg_18]
0x140002b13  add     rsp, 68h
0x140002b17  jmp     short $+2
0x140002b19  jmp     rax
```
