# __scrt_is_nonwritable_in_current_image

- ea: `0x180004ffc`
- end: `0x180005094`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004968`

## callees

- `0x180004ffc`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( _ImageBase != 23117 )
    return 0;
  v2 = (_DWORD *)((char *)&_ImageBase + (int)off_18000003C);
  if ( *v2 != 17744 || *(__int16 *)((char *)&word_180000018 + (int)off_18000003C) != 523 )
    return 0;
  v3 = a1 - (_QWORD)&_ImageBase;
  v4 = (_DWORD *)((char *)v2 + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C) + 24);
  v5 = &v4[10 * *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C)];
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
0x180004ffc  sub     rsp, 18h
0x180005000  mov     r8, rcx
0x180005003  mov     eax, 5A4Dh
0x180005008  cmp     cs:__ImageBase, ax
0x18000500f  jnz     short loc_180005089
0x180005011  movsxd  rcx, cs:off_18000003C
0x180005018  lea     rdx, __ImageBase
0x18000501f  add     rcx, rdx
0x180005022  cmp     dword ptr [rcx], 4550h
0x180005028  jnz     short loc_180005089
0x18000502a  mov     eax, 20Bh
0x18000502f  cmp     [rcx+18h], ax
0x180005033  jnz     short loc_180005089
0x180005035  sub     r8, rdx
0x180005038  movzx   edx, word ptr [rcx+14h]
0x18000503c  add     rdx, 18h
0x180005040  add     rdx, rcx
0x180005043  movzx   eax, word ptr [rcx+6]
0x180005047  lea     rcx, [rax+rax*4]
0x18000504b  lea     r9, [rdx+rcx*8]
0x18000504f  mov     [rsp+18h+var_18], rdx
0x180005053  cmp     rdx, r9
0x180005056  jz      short loc_180005070
0x180005058  mov     ecx, [rdx+0Ch]
0x18000505b  cmp     r8, rcx
0x18000505e  jb      short loc_18000506A
0x180005060  mov     eax, [rdx+8]
0x180005063  add     eax, ecx
0x180005065  cmp     r8, rax
0x180005068  jb      short loc_180005072
0x18000506a  add     rdx, 28h ; '('
0x18000506e  jmp     short loc_18000504F
0x180005070  xor     edx, edx
0x180005072  test    rdx, rdx
0x180005075  jnz     short loc_18000507B
0x180005077  xor     al, al
0x180005079  jmp     short loc_18000508F
0x18000507b  cmp     dword ptr [rdx+24h], 0
0x18000507f  jge     short loc_180005085
0x180005081  xor     al, al
0x180005083  jmp     short loc_18000508F
0x180005085  mov     al, 1
0x180005087  jmp     short loc_18000508F
0x180005089  xor     al, al
0x18000508b  jmp     short loc_18000508F
0x18000508d  xor     al, al
0x18000508f  add     rsp, 18h
0x180005093  retn
0x1800078de  push    rbp
0x1800078e0  mov     rbp, rdx
0x1800078e3  mov     rax, [rcx]
0x1800078e6  xor     ecx, ecx
0x1800078e8  cmp     dword ptr [rax], 0C0000005h
0x1800078ee  setz    cl
0x1800078f1  mov     eax, ecx
0x1800078f3  pop     rbp
0x1800078f4  retn
```
