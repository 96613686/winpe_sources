# _ValidateImageBase

- ea: `0x180001870`
- end: `0x18000189b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001820`

## callees

- `0x180001870`

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
0x180001870  mov     eax, 5A4Dh
0x180001875  cmp     [rcx], ax
0x180001878  jnz     short loc_180001898
0x18000187a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000187e  add     rdx, rcx
0x180001881  cmp     dword ptr [rdx], 4550h
0x180001887  jnz     short loc_180001898
0x180001889  xor     eax, eax
0x18000188b  mov     ecx, 20Bh
0x180001890  cmp     [rdx+18h], cx
0x180001894  setz    al
0x180001897  retn
0x180001898  xor     eax, eax
0x18000189a  retn
```
