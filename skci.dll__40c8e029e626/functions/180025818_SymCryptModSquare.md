# SymCryptModSquare

- ea: `0x180025818`
- end: `0x180025843`
- name: `SymCryptModSquare`
- size: `43`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18002cac8`
- `0x18002cc18`
- `0x18002f3e0`
- `0x18002f7ec`
- `0x180030030`
- `0x180030340`
- `0x1800307d0`
- `0x180030b70`
- `0x180031290`
- `0x180031b60`
- `0x180031e00`

## pseudocode

```c
__int64 __fastcall SymCryptModSquare(_DWORD *a1)
{
  return (*(__int64 (__fastcall **)(_DWORD *))((char *)&off_180035120 + (*a1 & 0x380)))(a1);
}

```

## disassembly

```asm
0x180025818  sub     rsp, 38h
0x18002581c  mov     eax, [rcx]
0x18002581e  lea     r10, off_180035120
0x180025825  and     eax, 380h
0x18002582a  mov     rax, [rax+r10]
0x18002582e  mov     r10, [rsp+38h+arg_20]
0x180025833  mov     [rsp+38h+var_18], r10
0x180025838  call    rax
0x18002583a  nop     dword ptr [rax]
0x18002583d  add     rsp, 38h
0x180025841  retn
```
