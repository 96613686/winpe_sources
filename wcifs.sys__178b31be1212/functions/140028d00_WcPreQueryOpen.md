# WcPreQueryOpen

- ea: `0x140028d00`
- end: `0x140028d26`
- name: `WcPreQueryOpen`
- size: `38`
- prototype: `_BOOL8 __fastcall(__int64, __int64)`
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
0x140028d00  sub     rsp, 28h
0x140028d04  mov     rcx, [rdx+18h]
0x140028d08  xor     r9d, r9d
0x140028d0b  mov     rdx, [rdx+20h]
0x140028d0f  xor     r8d, r8d
0x140028d12  call    WcUnionsExistForInstance
0x140028d17  xor     ecx, ecx
0x140028d19  test    al, al
0x140028d1b  setz    cl
0x140028d1e  mov     eax, ecx
0x140028d20  add     rsp, 28h
0x140028d24  retn
```
