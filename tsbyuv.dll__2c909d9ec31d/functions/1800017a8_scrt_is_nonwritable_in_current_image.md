# __scrt_is_nonwritable_in_current_image

- ea: `0x1800017a8`
- end: `0x180001840`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800017a8`

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
0x1800017a8  sub     rsp, 18h
0x1800017ac  mov     r8, rcx
0x1800017af  mov     eax, 5A4Dh
0x1800017b4  cmp     cs:180000000h, ax
0x1800017bb  jnz     short loc_180001835
0x1800017bd  movsxd  rcx, dword ptr cs:18000003Ch
0x1800017c4  lea     rdx, cs:180000000h
0x1800017cb  add     rcx, rdx
0x1800017ce  cmp     dword ptr [rcx], 4550h
0x1800017d4  jnz     short loc_180001835
0x1800017d6  mov     eax, 20Bh
0x1800017db  cmp     [rcx+18h], ax
0x1800017df  jnz     short loc_180001835
0x1800017e1  sub     r8, rdx
0x1800017e4  movzx   edx, word ptr [rcx+14h]
0x1800017e8  add     rdx, 18h
0x1800017ec  add     rdx, rcx
0x1800017ef  movzx   eax, word ptr [rcx+6]
0x1800017f3  lea     rcx, [rax+rax*4]
0x1800017f7  lea     r9, [rdx+rcx*8]
0x1800017fb  mov     [rsp+18h+var_18], rdx
0x1800017ff  cmp     rdx, r9
0x180001802  jz      short loc_18000181C
0x180001804  mov     ecx, [rdx+0Ch]
0x180001807  cmp     r8, rcx
0x18000180a  jb      short loc_180001816
0x18000180c  mov     eax, [rdx+8]
0x18000180f  add     eax, ecx
0x180001811  cmp     r8, rax
0x180001814  jb      short loc_18000181E
0x180001816  add     rdx, 28h ; '('
0x18000181a  jmp     short loc_1800017FB
0x18000181c  xor     edx, edx
0x18000181e  test    rdx, rdx
0x180001821  jnz     short loc_180001827
0x180001823  xor     al, al
0x180001825  jmp     short loc_18000183B
0x180001827  cmp     dword ptr [rdx+24h], 0
0x18000182b  jge     short loc_180001831
0x18000182d  xor     al, al
0x18000182f  jmp     short loc_18000183B
0x180001831  mov     al, 1
0x180001833  jmp     short loc_18000183B
0x180001835  xor     al, al
0x180001837  jmp     short loc_18000183B
0x180001839  xor     al, al
0x18000183b  add     rsp, 18h
0x18000183f  retn
0x1800035c8  push    rbp
0x1800035ca  mov     rbp, rdx
0x1800035cd  mov     rax, [rcx]
0x1800035d0  xor     ecx, ecx
0x1800035d2  cmp     dword ptr [rax], 0C0000005h
0x1800035d8  setz    cl
0x1800035db  mov     eax, ecx
0x1800035dd  pop     rbp
0x1800035de  retn
```
