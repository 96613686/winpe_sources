# _FindPESection

- ea: `0x1800017d0`
- end: `0x180001813`
- name: `_FindPESection`
- size: `67`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001820`

## callees

- `0x1800017d0`

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
0x1800017d0  movsxd  r8, dword ptr [rcx+3Ch]
0x1800017d4  xor     r9d, r9d
0x1800017d7  add     r8, rcx
0x1800017da  movzx   eax, word ptr [r8+14h]
0x1800017df  movzx   r10d, word ptr [r8+6]
0x1800017e4  add     rax, 18h
0x1800017e8  add     rax, r8
0x1800017eb  test    r10d, r10d
0x1800017ee  jz      short loc_180001810
0x1800017f0  mov     r8d, [rax+0Ch]
0x1800017f4  cmp     rdx, r8
0x1800017f7  jb      short loc_180001804
0x1800017f9  mov     ecx, [rax+8]
0x1800017fc  add     ecx, r8d
0x1800017ff  cmp     rdx, rcx
0x180001802  jb      short locret_180001812
0x180001804  inc     r9d
0x180001807  add     rax, 28h ; '('
0x18000180b  cmp     r9d, r10d
0x18000180e  jb      short loc_1800017F0
0x180001810  xor     eax, eax
0x180001812  retn
```
