# SymCryptModSub

- ea: `0x18002584c`
- end: `0x180025881`
- name: `SymCryptModSub`
- size: `53`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180029120`
- `0x18002b020`
- `0x18002f3e0`
- `0x18002f7ec`
- `0x180030030`
- `0x180030340`
- `0x180030e30`
- `0x180031290`
- `0x180031e00`

## pseudocode

```c
__int64 __fastcall SymCryptModSub(_DWORD *a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(_DWORD *, __int64))((char *)&off_180035108 + (*a1 & 0x380)))(a1, a2);
}

```

## disassembly

```asm
0x18002584c  sub     rsp, 38h
0x180025850  mov     eax, [rcx]
0x180025852  lea     r10, off_180035108
0x180025859  and     eax, 380h
0x18002585e  mov     rax, [rax+r10]
0x180025862  mov     r10, [rsp+38h+arg_28]
0x180025867  mov     [rsp+38h+var_10], r10
0x18002586c  mov     r10, [rsp+38h+arg_20]
0x180025871  mov     [rsp+38h+var_18], r10
0x180025876  call    rax
0x180025878  nop     dword ptr [rax]
0x18002587b  add     rsp, 38h
0x18002587f  retn
```
