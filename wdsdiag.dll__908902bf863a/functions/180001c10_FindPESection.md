# _FindPESection

- ea: `0x180001c10`
- end: `0x180001c54`
- name: `_FindPESection`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c60`

## callees

- `0x180001c10`

## pseudocode

```c
__int64 __fastcall FindPESection(__int64 a1, unsigned __int64 a2)
{
  unsigned int v2; // r9d
  __int64 v3; // r8
  __int64 result; // rax
  unsigned __int64 v6; // rdx

  v2 = 0;
  v3 = a1 + *(int *)(a1 + 60);
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
    if ( v2 >= *(unsigned __int16 *)(v3 + 6) )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001c10  movsxd  r8, dword ptr [rcx+3Ch]
0x180001c14  xor     r9d, r9d
0x180001c17  add     r8, rcx
0x180001c1a  mov     r10, rdx
0x180001c1d  movzx   eax, word ptr [r8+14h]
0x180001c22  movzx   r11d, word ptr [r8+6]
0x180001c27  add     rax, 18h
0x180001c2b  add     rax, r8
0x180001c2e  test    r11d, r11d
0x180001c31  jz      short loc_180001C51
0x180001c33  mov     edx, [rax+0Ch]
0x180001c36  cmp     r10, rdx
0x180001c39  jb      short loc_180001C45
0x180001c3b  mov     ecx, [rax+8]
0x180001c3e  add     ecx, edx
0x180001c40  cmp     r10, rcx
0x180001c43  jb      short locret_180001C53
0x180001c45  inc     r9d
0x180001c48  add     rax, 28h ; '('
0x180001c4c  cmp     r9d, r11d
0x180001c4f  jb      short loc_180001C33
0x180001c51  xor     eax, eax
0x180001c53  retn
```
