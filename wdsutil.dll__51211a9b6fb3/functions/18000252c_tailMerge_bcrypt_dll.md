# __tailMerge_bcrypt_dll

- ea: `0x18000252c`
- end: `0x1800025a5`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025ab`
- `0x1800025bd`
- `0x1800025cf`
- `0x1800025e1`
- `0x1800025f3`
- `0x180002605`
- `0x180002617`

## callees

- `0x18000252c`
- `0x180031390`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000252c  mov     [rsp+arg_0], rcx
0x180002531  mov     [rsp+arg_8], rdx
0x180002536  mov     [rsp+arg_10], r8
0x18000253b  mov     [rsp+arg_18], r9
0x180002540  sub     rsp, 68h
0x180002544  movdqa  [rsp+68h+var_48], xmm0
0x18000254a  movdqa  [rsp+68h+var_38], xmm1
0x180002550  movdqa  [rsp+68h+var_28], xmm2
0x180002556  movdqa  [rsp+68h+var_18], xmm3
0x18000255c  mov     rdx, rax
0x18000255f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x180002566  call    __delayLoadHelper2
0x18000256b  movdqa  xmm0, [rsp+68h+var_48]
0x180002571  movdqa  xmm1, [rsp+68h+var_38]
0x180002577  movdqa  xmm2, [rsp+68h+var_28]
0x18000257d  movdqa  xmm3, [rsp+68h+var_18]
0x180002583  mov     rcx, [rsp+68h+arg_0]
0x180002588  mov     rdx, [rsp+68h+arg_8]
0x18000258d  mov     r8, [rsp+68h+arg_10]
0x180002595  mov     r9, [rsp+68h+arg_18]
0x18000259d  add     rsp, 68h
0x1800025a1  jmp     short $+2
0x1800025a3  jmp     rax
```
