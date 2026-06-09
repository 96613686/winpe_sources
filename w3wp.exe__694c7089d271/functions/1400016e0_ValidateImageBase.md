# _ValidateImageBase

- ea: `0x1400016e0`
- end: `0x14000170b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001690`

## callees

- `0x1400016e0`

## pseudocode

```c
_BOOL8 __fastcall ValidateImageBase(__int64 a1)
{
  __int64 v1; // rdx

  if ( *(_WORD *)a1 == 23117 && (v1 = a1 + *(int *)(a1 + 60), *(_DWORD *)v1 == 17744) )
    return *(_WORD *)(v1 + 24) == 523;
  else
    return 0;
}

```

## disassembly

```asm
0x1400016e0  mov     eax, 5A4Dh
0x1400016e5  cmp     [rcx], ax
0x1400016e8  jnz     short loc_140001708
0x1400016ea  movsxd  rdx, dword ptr [rcx+3Ch]
0x1400016ee  add     rdx, rcx
0x1400016f1  cmp     dword ptr [rdx], 4550h
0x1400016f7  jnz     short loc_140001708
0x1400016f9  xor     eax, eax
0x1400016fb  mov     ecx, 20Bh
0x140001700  cmp     [rdx+18h], cx
0x140001704  setz    al
0x140001707  retn
0x140001708  xor     eax, eax
0x14000170a  retn
```
