# __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll

- ea: `0x140003782`
- end: `0x1400037fb`
- name: `__tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003801`
- `0x140003813`
- `0x140003825`

## callees

- `0x140003782`
- `0x1400171b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140003782  mov     [rsp+arg_0], rcx
0x140003787  mov     [rsp+arg_8], rdx
0x14000378c  mov     [rsp+arg_10], r8
0x140003791  mov     [rsp+arg_18], r9
0x140003796  sub     rsp, 68h
0x14000379a  movdqa  [rsp+68h+var_48], xmm0
0x1400037a0  movdqa  [rsp+68h+var_38], xmm1
0x1400037a6  movdqa  [rsp+68h+var_28], xmm2
0x1400037ac  movdqa  [rsp+68h+var_18], xmm3
0x1400037b2  mov     rdx, rax
0x1400037b5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_l1_1_0_dll
0x1400037bc  call    __delayLoadHelper2
0x1400037c1  movdqa  xmm0, [rsp+68h+var_48]
0x1400037c7  movdqa  xmm1, [rsp+68h+var_38]
0x1400037cd  movdqa  xmm2, [rsp+68h+var_28]
0x1400037d3  movdqa  xmm3, [rsp+68h+var_18]
0x1400037d9  mov     rcx, [rsp+68h+arg_0]
0x1400037de  mov     rdx, [rsp+68h+arg_8]
0x1400037e3  mov     r8, [rsp+68h+arg_10]
0x1400037eb  mov     r9, [rsp+68h+arg_18]
0x1400037f3  add     rsp, 68h
0x1400037f7  jmp     short $+2
0x1400037f9  jmp     rax
```
