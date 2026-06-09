# __tailMerge_oleaut32_dll

- ea: `0x180021991`
- end: `0x180021a0a`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021a10`
- `0x180021a22`
- `0x180021a34`
- `0x180021a46`
- `0x180021a58`
- `0x180021b07`
- `0x180021b2b`
- `0x180021b3d`
- `0x180021b4f`
- `0x180021b61`
- `0x180021b73`
- `0x180021b85`
- `0x180021ba9`

## callees

- `0x180021991`
- `0x180049e40`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180021991  mov     [rsp+arg_0], rcx
0x180021996  mov     [rsp+arg_8], rdx
0x18002199b  mov     [rsp+arg_10], r8
0x1800219a0  mov     [rsp+arg_18], r9
0x1800219a5  sub     rsp, 68h
0x1800219a9  movdqa  [rsp+68h+var_48], xmm0
0x1800219af  movdqa  [rsp+68h+var_38], xmm1
0x1800219b5  movdqa  [rsp+68h+var_28], xmm2
0x1800219bb  movdqa  [rsp+68h+var_18], xmm3
0x1800219c1  mov     rdx, rax
0x1800219c4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x1800219cb  call    __delayLoadHelper2
0x1800219d0  movdqa  xmm0, [rsp+68h+var_48]
0x1800219d6  movdqa  xmm1, [rsp+68h+var_38]
0x1800219dc  movdqa  xmm2, [rsp+68h+var_28]
0x1800219e2  movdqa  xmm3, [rsp+68h+var_18]
0x1800219e8  mov     rcx, [rsp+68h+arg_0]
0x1800219ed  mov     rdx, [rsp+68h+arg_8]
0x1800219f2  mov     r8, [rsp+68h+arg_10]
0x1800219fa  mov     r9, [rsp+68h+arg_18]
0x180021a02  add     rsp, 68h
0x180021a06  jmp     short $+2
0x180021a08  jmp     rax
```
