# MvmpCreateGpadlHelper

- ea: `0x14000e050`
- end: `0x14000e096`
- name: `MvmpCreateGpadlHelper`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d410`

## callees

- `0x14000e050`

## pseudocode

```c
char __fastcall MvmpCreateGpadlHelper(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // r10
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // r9
  __int64 v6; // rcx

  if ( *(_BYTE *)(a1 + 57) )
    return 1;
  if ( *(_BYTE *)(a1 + 58) )
    return 1;
  v3 = *(_QWORD *)(a1 + 40);
  v4 = *(_QWORD *)(v3 + 176);
  if ( !v4 )
    return 1;
  v5 = v4 >> 12;
  v6 = 0;
  if ( !a3 )
    return 1;
  while ( *(_QWORD *)(a2 + 8 * v6) >= v5 )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= a3 )
      return 1;
  }
  *(_DWORD *)(v3 + 208) = 11;
  return 0;
}

```

## disassembly

```asm
0x14000e050  cmp     byte ptr [rcx+39h], 0
0x14000e054  jnz     short loc_14000E084
0x14000e056  cmp     byte ptr [rcx+3Ah], 0
0x14000e05a  jnz     short loc_14000E084
0x14000e05c  mov     r10, [rcx+28h]
0x14000e060  mov     r9, [r10+0B0h]
0x14000e067  test    r9, r9
0x14000e06a  jz      short loc_14000E084
0x14000e06c  shr     r9, 0Ch
0x14000e070  xor     ecx, ecx
0x14000e072  test    r8d, r8d
0x14000e075  jz      short loc_14000E084
0x14000e077  cmp     [rdx+rcx*8], r9
0x14000e07b  jb      short loc_14000E088
0x14000e07d  inc     ecx
0x14000e07f  cmp     ecx, r8d
0x14000e082  jb      short loc_14000E077
0x14000e084  mov     al, 1
0x14000e086  retn
0x14000e088  mov     dword ptr [r10+0D0h], 0Bh
0x14000e093  xor     al, al
0x14000e095  retn
```
