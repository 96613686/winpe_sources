# _ValidateImageBase

- ea: `0x180001780`
- end: `0x1800017ab`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001730`

## callees

- `0x180001780`

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
0x180001780  mov     eax, 5A4Dh
0x180001785  cmp     [rcx], ax
0x180001788  jnz     short loc_1800017A8
0x18000178a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000178e  add     rdx, rcx
0x180001791  cmp     dword ptr [rdx], 4550h
0x180001797  jnz     short loc_1800017A8
0x180001799  xor     eax, eax
0x18000179b  mov     ecx, 20Bh
0x1800017a0  cmp     [rdx+18h], cx
0x1800017a4  setz    al
0x1800017a7  retn
0x1800017a8  xor     eax, eax
0x1800017aa  retn
```
