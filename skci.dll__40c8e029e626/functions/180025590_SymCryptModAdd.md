# SymCryptModAdd

- ea: `0x180025590`
- end: `0x1800255c5`
- name: `SymCryptModAdd`
- size: `53`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180023e94`
- `0x180025888`
- `0x18002f3e0`
- `0x18002f7ec`
- `0x180030030`
- `0x180030340`
- `0x180030b70`
- `0x180030e30`
- `0x180031290`
- `0x180031b60`
- `0x180031e00`

## pseudocode

```c
__int64 __fastcall SymCryptModAdd(_DWORD *a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(_DWORD *, __int64))((char *)g_SymCryptModFns + (*a1 & 0x380)))(a1, a2);
}

```

## disassembly

```asm
0x180025590  sub     rsp, 38h
0x180025594  mov     eax, [rcx]
0x180025596  lea     r10, g_SymCryptModFns
0x18002559d  and     eax, 380h
0x1800255a2  mov     rax, [rax+r10]
0x1800255a6  mov     r10, [rsp+38h+arg_28]
0x1800255ab  mov     [rsp+38h+var_10], r10
0x1800255b0  mov     r10, [rsp+38h+arg_20]
0x1800255b5  mov     [rsp+38h+var_18], r10
0x1800255ba  call    rax
0x1800255bc  nop     dword ptr [rax]
0x1800255bf  add     rsp, 38h
0x1800255c3  retn
```
