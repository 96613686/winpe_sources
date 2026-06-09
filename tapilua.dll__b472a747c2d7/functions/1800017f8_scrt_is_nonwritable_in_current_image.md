# __scrt_is_nonwritable_in_current_image

- ea: `0x1800017f8`
- end: `0x180001890`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001158`

## callees

- `0x1800017f8`

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
0x1800017f8  sub     rsp, 18h
0x1800017fc  mov     r8, rcx
0x1800017ff  mov     eax, 5A4Dh
0x180001804  cmp     cs:180000000h, ax
0x18000180b  jnz     short loc_180001885
0x18000180d  movsxd  rcx, dword ptr cs:18000003Ch
0x180001814  lea     rdx, cs:180000000h
0x18000181b  add     rcx, rdx
0x18000181e  cmp     dword ptr [rcx], 4550h
0x180001824  jnz     short loc_180001885
0x180001826  mov     eax, 20Bh
0x18000182b  cmp     [rcx+18h], ax
0x18000182f  jnz     short loc_180001885
0x180001831  sub     r8, rdx
0x180001834  movzx   edx, word ptr [rcx+14h]
0x180001838  add     rdx, 18h
0x18000183c  add     rdx, rcx
0x18000183f  movzx   eax, word ptr [rcx+6]
0x180001843  lea     rcx, [rax+rax*4]
0x180001847  lea     r9, [rdx+rcx*8]
0x18000184b  mov     [rsp+18h+var_18], rdx
0x18000184f  cmp     rdx, r9
0x180001852  jz      short loc_18000186C
0x180001854  mov     ecx, [rdx+0Ch]
0x180001857  cmp     r8, rcx
0x18000185a  jb      short loc_180001866
0x18000185c  mov     eax, [rdx+8]
0x18000185f  add     eax, ecx
0x180001861  cmp     r8, rax
0x180001864  jb      short loc_18000186E
0x180001866  add     rdx, 28h ; '('
0x18000186a  jmp     short loc_18000184B
0x18000186c  xor     edx, edx
0x18000186e  test    rdx, rdx
0x180001871  jnz     short loc_180001877
0x180001873  xor     al, al
0x180001875  jmp     short loc_18000188B
0x180001877  cmp     dword ptr [rdx+24h], 0
0x18000187b  jge     short loc_180001881
0x18000187d  xor     al, al
0x18000187f  jmp     short loc_18000188B
0x180001881  mov     al, 1
0x180001883  jmp     short loc_18000188B
0x180001885  xor     al, al
0x180001887  jmp     short loc_18000188B
0x180001889  xor     al, al
0x18000188b  add     rsp, 18h
0x18000188f  retn
0x180005058  push    rbp
0x18000505a  mov     rbp, rdx
0x18000505d  mov     rax, [rcx]
0x180005060  xor     ecx, ecx
0x180005062  cmp     dword ptr [rax], 0C0000005h
0x180005068  setz    cl
0x18000506b  mov     eax, ecx
0x18000506d  pop     rbp
0x18000506e  retn
```
