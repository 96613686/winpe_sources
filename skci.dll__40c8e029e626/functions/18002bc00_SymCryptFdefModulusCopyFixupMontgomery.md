# SymCryptFdefModulusCopyFixupMontgomery

- ea: `0x18002bc00`
- end: `0x18002bc1f`
- name: `SymCryptFdefModulusCopyFixupMontgomery`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002c2b8`

## pseudocode

```c
__int64 __fastcall SymCryptFdefModulusCopyFixupMontgomery(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 result; // rax

  v4 = SymCryptFdefSizeofDivisorFromDigits(*(unsigned int *)(a2 + 4), a2, a3, a4);
  result = v5 + v4 + 64LL;
  *(_QWORD *)(v5 + 40) = result;
  return result;
}

```

## disassembly

```asm
0x18002bc00  sub     rsp, 28h
0x18002bc04  mov     ecx, [rdx+4]
0x18002bc07  call    SymCryptFdefSizeofDivisorFromDigits
0x18002bc0c  mov     eax, eax
0x18002bc0e  add     rax, 40h ; '@'
0x18002bc12  add     rax, rdx
0x18002bc15  mov     [rdx+28h], rax
0x18002bc19  add     rsp, 28h
0x18002bc1d  retn
```
