# CiCompareSigningLevels

- ea: `0x180047600`
- end: `0x180047622`
- name: `CiCompareSigningLevels`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180011b94`
- `0x180011c50`
- `0x180012308`

## pseudocode

```c
__int64 __fastcall CiCompareSigningLevels(char a1, char a2)
{
  unsigned int v2; // r8d
  int v3; // ecx

  v2 = a1 & 0xF;
  v3 = *((_DWORD *)g_CipWhichLevelComparisons + (a2 & 0xF));
  return _bittest(&v3, v2);
}

```

## disassembly

```asm
0x180047600  mov     rax, cs:g_CipWhichLevelComparisons
0x180047607  movzx   r8d, cl
0x18004760b  movzx   ecx, dl
0x18004760e  and     r8d, 0Fh
0x180047612  and     ecx, 0Fh
0x180047615  mov     ecx, [rax+rcx*4]
0x180047618  xor     eax, eax
0x18004761a  bt      ecx, r8d
0x18004761e  setb    al
0x180047621  retn
```
