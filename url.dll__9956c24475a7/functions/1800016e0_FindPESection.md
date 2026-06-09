# _FindPESection

- ea: `0x1800016e0`
- end: `0x180001723`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001730`

## callees

- `0x1800016e0`

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
0x1800016e0  movsxd  r8, dword ptr [rcx+3Ch]
0x1800016e4  xor     r9d, r9d
0x1800016e7  add     r8, rcx
0x1800016ea  movzx   eax, word ptr [r8+14h]
0x1800016ef  movzx   r10d, word ptr [r8+6]
0x1800016f4  add     rax, 18h
0x1800016f8  add     rax, r8
0x1800016fb  test    r10d, r10d
0x1800016fe  jz      short loc_180001720
0x180001700  mov     r8d, [rax+0Ch]
0x180001704  cmp     rdx, r8
0x180001707  jb      short loc_180001714
0x180001709  mov     ecx, [rax+8]
0x18000170c  add     ecx, r8d
0x18000170f  cmp     rdx, rcx
0x180001712  jb      short locret_180001722
0x180001714  inc     r9d
0x180001717  add     rax, 28h ; '('
0x18000171b  cmp     r9d, r10d
0x18000171e  jb      short loc_180001700
0x180001720  xor     eax, eax
0x180001722  retn
```
