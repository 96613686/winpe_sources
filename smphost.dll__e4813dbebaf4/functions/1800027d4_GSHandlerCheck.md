# __GSHandlerCheck

- ea: `0x1800027d4`
- end: `0x1800027f1`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800027f8`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _GSHandlerCheckCommon(a2, a4, *(_QWORD *)(a4 + 56));
  return 1;
}

```

## disassembly

```asm
0x1800027d4  sub     rsp, 28h
0x1800027d8  mov     r8, [r9+38h]
0x1800027dc  mov     rcx, rdx
0x1800027df  mov     rdx, r9
0x1800027e2  call    __GSHandlerCheckCommon
0x1800027e7  mov     eax, 1
0x1800027ec  add     rsp, 28h
0x1800027f0  retn
```
