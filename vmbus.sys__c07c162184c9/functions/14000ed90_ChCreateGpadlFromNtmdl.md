# ChCreateGpadlFromNtmdl

- ea: `0x14000ed90`
- end: `0x14000edbd`
- name: `ChCreateGpadlFromNtmdl`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002c930`

## callees

- `0x14000f158`

## pseudocode

```c
__int64 __fastcall ChCreateGpadlFromNtmdl(__int64 a1, __int64 a2, int a3, int a4, __int64 a5, __int64 a6)
{
  return ChpCreateGpadlFromNtmdl(a1, a2, a3, a4, (__int64)BusChGpadlCreated, a6, 0);
}

```

## disassembly

```asm
0x14000ed90  sub     rsp, 48h
0x14000ed94  mov     rax, [rsp+48h+arg_28]
0x14000ed99  mov     [rsp+48h+var_18], 0
0x14000eda1  mov     [rsp+48h+var_20], rax
0x14000eda6  lea     rax, BusChGpadlCreated
0x14000edad  mov     [rsp+48h+var_28], rax
0x14000edb2  call    ChpCreateGpadlFromNtmdl
0x14000edb7  add     rsp, 48h
0x14000edbb  retn
```
