# _FindPESection

- ea: `0x180001d40`
- end: `0x180001d83`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d90`

## callees

- `0x180001d40`

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
0x180001d40  movsxd  r8, dword ptr [rcx+3Ch]
0x180001d44  xor     r9d, r9d
0x180001d47  add     r8, rcx
0x180001d4a  movzx   eax, word ptr [r8+14h]
0x180001d4f  movzx   r10d, word ptr [r8+6]
0x180001d54  add     rax, 18h
0x180001d58  add     rax, r8
0x180001d5b  test    r10d, r10d
0x180001d5e  jz      short loc_180001D80
0x180001d60  mov     r8d, [rax+0Ch]
0x180001d64  cmp     rdx, r8
0x180001d67  jb      short loc_180001D74
0x180001d69  mov     ecx, [rax+8]
0x180001d6c  add     ecx, r8d
0x180001d6f  cmp     rdx, rcx
0x180001d72  jb      short locret_180001D82
0x180001d74  inc     r9d
0x180001d77  add     rax, 28h ; '('
0x180001d7b  cmp     r9d, r10d
0x180001d7e  jb      short loc_180001D60
0x180001d80  xor     eax, eax
0x180001d82  retn
```
