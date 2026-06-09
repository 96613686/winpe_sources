# _ValidateImageBase

- ea: `0x180001630`
- end: `0x18000165b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015e0`

## callees

- `0x180001630`

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
0x180001630  mov     eax, 5A4Dh
0x180001635  cmp     [rcx], ax
0x180001638  jnz     short loc_180001658
0x18000163a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000163e  add     rdx, rcx
0x180001641  cmp     dword ptr [rdx], 4550h
0x180001647  jnz     short loc_180001658
0x180001649  xor     eax, eax
0x18000164b  mov     ecx, 20Bh
0x180001650  cmp     [rdx+18h], cx
0x180001654  setz    al
0x180001657  retn
0x180001658  xor     eax, eax
0x18000165a  retn
```
