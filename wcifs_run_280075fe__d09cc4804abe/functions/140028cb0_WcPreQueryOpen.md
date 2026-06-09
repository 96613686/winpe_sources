# WcPreQueryOpen

- ea: `0x140028cb0`
- end: `0x140028cd6`
- name: `WcPreQueryOpen`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001580`

## pseudocode

```c
_BOOL8 __fastcall WcPreQueryOpen(__int64 a1, __int64 a2)
{
  return (unsigned __int8)WcUnionsExistForInstance(*(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32), 0, 0) == 0;
}

```

## disassembly

```asm
0x140028cb0  sub     rsp, 28h
0x140028cb4  mov     rcx, [rdx+18h]
0x140028cb8  xor     r9d, r9d
0x140028cbb  mov     rdx, [rdx+20h]
0x140028cbf  xor     r8d, r8d
0x140028cc2  call    WcUnionsExistForInstance
0x140028cc7  xor     ecx, ecx
0x140028cc9  test    al, al
0x140028ccb  setz    cl
0x140028cce  mov     eax, ecx
0x140028cd0  add     rsp, 28h
0x140028cd4  retn
```
