# DllGetClassObject$catch$1

- ea: `0x1800437dd`
- end: `0x180043802`
- name: `DllGetClassObject$catch$1`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall DllGetClassObject_catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x1800437dd  mov     [rsp+arg_8], rdx
0x1800437e2  push    rbp
0x1800437e3  sub     rsp, 20h
0x1800437e7  mov     rbp, rdx
0x1800437ea  mov     dword ptr [rbp+60h], 8007000Eh
0x1800437f1  mov     rax, 0
0x1800437fb  add     rsp, 20h
0x1800437ff  pop     rbp
0x180043800  retn
```
