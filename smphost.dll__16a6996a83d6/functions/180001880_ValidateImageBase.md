# _ValidateImageBase

- ea: `0x180001880`
- end: `0x1800018ab`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001830`

## callees

- `0x180001880`

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
0x180001880  mov     eax, 5A4Dh
0x180001885  cmp     [rcx], ax
0x180001888  jnz     short loc_1800018A8
0x18000188a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000188e  add     rdx, rcx
0x180001891  cmp     dword ptr [rdx], 4550h
0x180001897  jnz     short loc_1800018A8
0x180001899  xor     eax, eax
0x18000189b  mov     ecx, 20Bh
0x1800018a0  cmp     [rdx+18h], cx
0x1800018a4  setz    al
0x1800018a7  retn
0x1800018a8  xor     eax, eax
0x1800018aa  retn
```
