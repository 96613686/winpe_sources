# WcPostRead

- ea: `0x140005960`
- end: `0x1400059ab`
- name: `WcPostRead`
- size: `75`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005960`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140005997`
- `FLTMGR!FltReleaseContext` at `0x140005997`

## pseudocode

```c
__int64 __fastcall WcPostRead(__int64 a1, __int64 a2, void *a3)
{
  __int64 v3; // r9
  __int64 v4; // r10
  __int64 v5; // rdx

  if ( *(int *)(a1 + 24) >= 0 )
  {
    v3 = *(_QWORD *)(a1 + 32);
    if ( v3 )
    {
      v4 = *(_QWORD *)(a2 + 32);
      if ( (*(_DWORD *)(v4 + 80) & 2) != 0 )
      {
        v5 = *(_QWORD *)(a1 + 16);
        if ( (*(_DWORD *)v5 & 2) == 0 )
          *(_QWORD *)(v4 + 104) = v3 + *(_QWORD *)(v5 + 40);
      }
    }
  }
  FltReleaseContext(a3);
  return 0;
}

```

## disassembly

```asm
0x140005960  sub     rsp, 28h
0x140005964  cmp     dword ptr [rcx+18h], 0
0x140005968  jl      short loc_140005994
0x14000596a  mov     r9, [rcx+20h]
0x14000596e  test    r9, r9
0x140005971  jz      short loc_140005994
0x140005973  mov     r10, [rdx+20h]
0x140005977  mov     eax, [r10+50h]
0x14000597b  test    al, 2
0x14000597d  jz      short loc_140005994
0x14000597f  mov     rdx, [rcx+10h]
0x140005983  mov     eax, [rdx]
0x140005985  test    al, 2
0x140005987  jnz     short loc_140005994
0x140005989  mov     rcx, [rdx+28h]
0x14000598d  add     rcx, r9
0x140005990  mov     [r10+68h], rcx
0x140005994  mov     rcx, r8; Context
0x140005997  call    cs:__imp_FltReleaseContext
0x14000599e  nop     dword ptr [rax+rax+00h]
0x1400059a3  xor     eax, eax
0x1400059a5  add     rsp, 28h
0x1400059a9  retn
```
