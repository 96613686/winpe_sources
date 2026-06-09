# _FindPESection

- ea: `0x180002060`
- end: `0x1800020a3`
- name: `_FindPESection`
- size: `67`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020b0`

## callees

- `0x180002060`

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
0x180002060  movsxd  r8, dword ptr [rcx+3Ch]
0x180002064  xor     r9d, r9d
0x180002067  add     r8, rcx
0x18000206a  movzx   eax, word ptr [r8+14h]
0x18000206f  movzx   r10d, word ptr [r8+6]
0x180002074  add     rax, 18h
0x180002078  add     rax, r8
0x18000207b  test    r10d, r10d
0x18000207e  jz      short loc_1800020A0
0x180002080  mov     r8d, [rax+0Ch]
0x180002084  cmp     rdx, r8
0x180002087  jb      short loc_180002094
0x180002089  mov     ecx, [rax+8]
0x18000208c  add     ecx, r8d
0x18000208f  cmp     rdx, rcx
0x180002092  jb      short locret_1800020A2
0x180002094  inc     r9d
0x180002097  add     rax, 28h ; '('
0x18000209b  cmp     r9d, r10d
0x18000209e  jb      short loc_180002080
0x1800020a0  xor     eax, eax
0x1800020a2  retn
```
