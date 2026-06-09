# SymCryptModMul

- ea: `0x18002574c`
- end: `0x180025781`
- name: `SymCryptModMul`
- size: `53`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x180025888`
- `0x180026108`
- `0x180029120`
- `0x180029704`
- `0x18002b020`
- `0x18002cac8`
- `0x18002cc18`
- `0x18002f3e0`
- `0x18002f7ec`
- `0x180030030`
- `0x180030340`
- `0x1800307d0`
- `0x180030b70`
- `0x180030e30`
- `0x180031290`
- `0x1800317c0`
- `0x180031b60`
- `0x180031e00`
- `0x180032260`

## pseudocode

```c
__int64 __fastcall SymCryptModMul(_DWORD *a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(_DWORD *, __int64))((char *)&off_180035118 + (*a1 & 0x380)))(a1, a2);
}

```

## disassembly

```asm
0x18002574c  sub     rsp, 38h
0x180025750  mov     eax, [rcx]
0x180025752  lea     r10, off_180035118
0x180025759  and     eax, 380h
0x18002575e  mov     rax, [rax+r10]
0x180025762  mov     r10, [rsp+38h+arg_28]
0x180025767  mov     [rsp+38h+var_10], r10
0x18002576c  mov     r10, [rsp+38h+arg_20]
0x180025771  mov     [rsp+38h+var_18], r10
0x180025776  call    rax
0x180025778  nop     dword ptr [rax]
0x18002577b  add     rsp, 38h
0x18002577f  retn
```
