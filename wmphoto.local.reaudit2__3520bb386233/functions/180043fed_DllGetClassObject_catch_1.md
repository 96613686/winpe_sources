# DllGetClassObject$catch$1

- ea: `0x180043fed`
- end: `0x180044012`
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
0x180043fed  mov     [rsp+arg_8], rdx
0x180043ff2  push    rbp
0x180043ff3  sub     rsp, 20h
0x180043ff7  mov     rbp, rdx
0x180043ffa  mov     dword ptr [rbp+60h], 8007000Eh
0x180044001  mov     rax, 0
0x18004400b  add     rsp, 20h
0x18004400f  pop     rbp
0x180044010  retn
```
