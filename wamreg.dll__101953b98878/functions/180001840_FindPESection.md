# _FindPESection

- ea: `0x180001840`
- end: `0x180001883`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001890`

## callees

- `0x180001840`

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
0x180001840  movsxd  r8, dword ptr [rcx+3Ch]
0x180001844  xor     r9d, r9d
0x180001847  add     r8, rcx
0x18000184a  movzx   eax, word ptr [r8+14h]
0x18000184f  movzx   r10d, word ptr [r8+6]
0x180001854  add     rax, 18h
0x180001858  add     rax, r8
0x18000185b  test    r10d, r10d
0x18000185e  jz      short loc_180001880
0x180001860  mov     r8d, [rax+0Ch]
0x180001864  cmp     rdx, r8
0x180001867  jb      short loc_180001874
0x180001869  mov     ecx, [rax+8]
0x18000186c  add     ecx, r8d
0x18000186f  cmp     rdx, rcx
0x180001872  jb      short locret_180001882
0x180001874  inc     r9d
0x180001877  add     rax, 28h ; '('
0x18000187b  cmp     r9d, r10d
0x18000187e  jb      short loc_180001860
0x180001880  xor     eax, eax
0x180001882  retn
```
