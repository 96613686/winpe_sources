# __tailMerge_winmmbase_dll

- ea: `0x18000b9b0`
- end: `0x18000ba29`
- name: `__tailMerge_winmmbase_dll`
- size: `121`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ba2f`
- `0x18000ba41`
- `0x18000ba53`
- `0x18000ba65`
- `0x18000ba77`
- `0x18000ba89`
- `0x18000ba9b`
- `0x18000baad`
- `0x18000babf`
- `0x18000bad1`
- `0x18000bae3`
- `0x18000baf5`

## callees

- `0x180009370`
- `0x18000b9b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_winmmbase_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winmmbase_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b9b0  mov     [rsp+arg_0], rcx
0x18000b9b5  mov     [rsp+arg_8], rdx
0x18000b9ba  mov     [rsp+arg_10], r8
0x18000b9bf  mov     [rsp+arg_18], r9
0x18000b9c4  sub     rsp, 68h
0x18000b9c8  movdqa  [rsp+68h+var_48], xmm0
0x18000b9ce  movdqa  [rsp+68h+var_38], xmm1
0x18000b9d4  movdqa  [rsp+68h+var_28], xmm2
0x18000b9da  movdqa  [rsp+68h+var_18], xmm3
0x18000b9e0  mov     rdx, rax
0x18000b9e3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winmmbase_dll
0x18000b9ea  call    __delayLoadHelper2
0x18000b9ef  movdqa  xmm0, [rsp+68h+var_48]
0x18000b9f5  movdqa  xmm1, [rsp+68h+var_38]
0x18000b9fb  movdqa  xmm2, [rsp+68h+var_28]
0x18000ba01  movdqa  xmm3, [rsp+68h+var_18]
0x18000ba07  mov     rcx, [rsp+68h+arg_0]
0x18000ba0c  mov     rdx, [rsp+68h+arg_8]
0x18000ba11  mov     r8, [rsp+68h+arg_10]
0x18000ba19  mov     r9, [rsp+68h+arg_18]
0x18000ba21  add     rsp, 68h
0x18000ba25  jmp     short $+2
0x18000ba27  jmp     rax
```
