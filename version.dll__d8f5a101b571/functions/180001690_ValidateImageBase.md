# _ValidateImageBase

- ea: `0x180001690`
- end: `0x1800016bb`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001640`

## callees

- `0x180001690`

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
0x180001690  mov     eax, 5A4Dh
0x180001695  cmp     [rcx], ax
0x180001698  jnz     short loc_1800016B8
0x18000169a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000169e  add     rdx, rcx
0x1800016a1  cmp     dword ptr [rdx], 4550h
0x1800016a7  jnz     short loc_1800016B8
0x1800016a9  xor     eax, eax
0x1800016ab  mov     ecx, 20Bh
0x1800016b0  cmp     [rdx+18h], cx
0x1800016b4  setz    al
0x1800016b7  retn
0x1800016b8  xor     eax, eax
0x1800016ba  retn
```
