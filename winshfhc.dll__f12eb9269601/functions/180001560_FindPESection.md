# _FindPESection

- ea: `0x180001560`
- end: `0x1800015a3`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015b0`

## callees

- `0x180001560`

## pseudocode

```c
__int64 __fastcall FindPESection(__int64 a1, unsigned __int64 a2)
{
  unsigned int v2; // r9d
  __int64 v3; // r8
  unsigned int v4; // r10d
  __int64 result; // rax
  unsigned __int64 v6; // r8

  v2 = 0;
  v3 = a1 + *(int *)(a1 + 60);
  v4 = *(unsigned __int16 *)(v3 + 6);
  result = v3 + *(unsigned __int16 *)(v3 + 20) + 24LL;
  if ( !*(_WORD *)(v3 + 6) )
    return 0;
  while ( 1 )
  {
    v6 = *(unsigned int *)(result + 12);
    if ( a2 >= v6 && a2 < (unsigned int)(v6 + *(_DWORD *)(result + 8)) )
      break;
    ++v2;
    result += 40;
    if ( v2 >= v4 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001560  movsxd  r8, dword ptr [rcx+3Ch]
0x180001564  xor     r9d, r9d
0x180001567  add     r8, rcx
0x18000156a  movzx   eax, word ptr [r8+14h]
0x18000156f  movzx   r10d, word ptr [r8+6]
0x180001574  add     rax, 18h
0x180001578  add     rax, r8
0x18000157b  test    r10d, r10d
0x18000157e  jz      short loc_1800015A0
0x180001580  mov     r8d, [rax+0Ch]
0x180001584  cmp     rdx, r8
0x180001587  jb      short loc_180001594
0x180001589  mov     ecx, [rax+8]
0x18000158c  add     ecx, r8d
0x18000158f  cmp     rdx, rcx
0x180001592  jb      short locret_1800015A2
0x180001594  inc     r9d
0x180001597  add     rax, 28h ; '('
0x18000159b  cmp     r9d, r10d
0x18000159e  jb      short loc_180001580
0x1800015a0  xor     eax, eax
0x1800015a2  retn
```
