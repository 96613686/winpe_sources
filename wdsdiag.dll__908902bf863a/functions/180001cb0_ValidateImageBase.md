# _ValidateImageBase

- ea: `0x180001cb0`
- end: `0x180001cde`
- name: `_ValidateImageBase`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c60`

## callees

- `0x180001cb0`

## pseudocode

```c
bool __fastcall ValidateImageBase(__int64 a1)
{
  bool result; // al
  __int64 v2; // rcx

  if ( *(_WORD *)a1 != 23117 )
    return 0;
  v2 = a1 + *(int *)(a1 + 60);
  result = 0;
  if ( *(_DWORD *)v2 == 17744 )
    return *(_WORD *)(v2 + 24) == 523;
  return result;
}

```

## disassembly

```asm
0x180001cb0  mov     rax, rcx
0x180001cb3  mov     ecx, 5A4Dh
0x180001cb8  cmp     [rax], cx
0x180001cbb  jz      short loc_180001CC0
0x180001cbd  xor     eax, eax
0x180001cbf  retn
0x180001cc0  movsxd  rcx, dword ptr [rax+3Ch]
0x180001cc4  add     rcx, rax
0x180001cc7  xor     eax, eax
0x180001cc9  cmp     dword ptr [rcx], 4550h
0x180001ccf  jnz     short locret_180001CDD
0x180001cd1  mov     edx, 20Bh
0x180001cd6  cmp     [rcx+18h], dx
0x180001cda  setz    al
0x180001cdd  retn
```
