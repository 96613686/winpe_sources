# __scrt_is_nonwritable_in_current_image

- ea: `0x180002cfc`
- end: `0x180002d94`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002668`

## callees

- `0x180002cfc`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( MEMORY[0x180000000] != 23117 )
    return 0;
  v2 = (_DWORD *)(0x180000000LL + MEMORY[0x18000003C]);
  if ( *v2 != 17744 || *(_WORD *)(0x180000018LL + MEMORY[0x18000003C]) != 523 )
    return 0;
  v3 = a1 - 0x180000000LL;
  v4 = (_DWORD *)((char *)v2 + *(unsigned __int16 *)(0x180000014LL + MEMORY[0x18000003C]) + 24);
  v5 = &v4[10 * *(unsigned __int16 *)(0x180000006LL + MEMORY[0x18000003C])];
  while ( v4 != v5 )
  {
    v6 = (unsigned int)v4[3];
    if ( v3 >= v6 && v3 < (unsigned int)(v6 + v4[2]) )
      return v4 && v4[9] >= 0;
    v4 += 10;
  }
  v4 = 0;
  return v4 && v4[9] >= 0;
}

```

## disassembly

```asm
0x180002cfc  sub     rsp, 18h
0x180002d00  mov     r8, rcx
0x180002d03  mov     eax, 5A4Dh
0x180002d08  cmp     cs:180000000h, ax
0x180002d0f  jnz     short loc_180002D89
0x180002d11  movsxd  rcx, dword ptr cs:18000003Ch
0x180002d18  lea     rdx, cs:180000000h
0x180002d1f  add     rcx, rdx
0x180002d22  cmp     dword ptr [rcx], 4550h
0x180002d28  jnz     short loc_180002D89
0x180002d2a  mov     eax, 20Bh
0x180002d2f  cmp     [rcx+18h], ax
0x180002d33  jnz     short loc_180002D89
0x180002d35  sub     r8, rdx
0x180002d38  movzx   edx, word ptr [rcx+14h]
0x180002d3c  add     rdx, 18h
0x180002d40  add     rdx, rcx
0x180002d43  movzx   eax, word ptr [rcx+6]
0x180002d47  lea     rcx, [rax+rax*4]
0x180002d4b  lea     r9, [rdx+rcx*8]
0x180002d4f  mov     [rsp+18h+var_18], rdx
0x180002d53  cmp     rdx, r9
0x180002d56  jz      short loc_180002D70
0x180002d58  mov     ecx, [rdx+0Ch]
0x180002d5b  cmp     r8, rcx
0x180002d5e  jb      short loc_180002D6A
0x180002d60  mov     eax, [rdx+8]
0x180002d63  add     eax, ecx
0x180002d65  cmp     r8, rax
0x180002d68  jb      short loc_180002D72
0x180002d6a  add     rdx, 28h ; '('
0x180002d6e  jmp     short loc_180002D4F
0x180002d70  xor     edx, edx
0x180002d72  test    rdx, rdx
0x180002d75  jnz     short loc_180002D7B
0x180002d77  xor     al, al
0x180002d79  jmp     short loc_180002D8F
0x180002d7b  cmp     dword ptr [rdx+24h], 0
0x180002d7f  jge     short loc_180002D85
0x180002d81  xor     al, al
0x180002d83  jmp     short loc_180002D8F
0x180002d85  mov     al, 1
0x180002d87  jmp     short loc_180002D8F
0x180002d89  xor     al, al
0x180002d8b  jmp     short loc_180002D8F
0x180002d8d  xor     al, al
0x180002d8f  add     rsp, 18h
0x180002d93  retn
0x1800034d8  push    rbp
0x1800034da  mov     rbp, rdx
0x1800034dd  mov     rax, [rcx]
0x1800034e0  xor     ecx, ecx
0x1800034e2  cmp     dword ptr [rax], 0C0000005h
0x1800034e8  setz    cl
0x1800034eb  mov     eax, ecx
0x1800034ed  pop     rbp
0x1800034ee  retn
```
