# readQuantizer

- ea: `0x18003f748`
- end: `0x18003f86b`
- name: `readQuantizer`
- size: `291`
- prototype: `char __fastcall(_QWORD *, __int64, unsigned __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18003146c`
- `0x180031620`
- `0x180032eb4`

## callees

- `0x18003f748`

## pseudocode

```c
char __fastcall readQuantizer(_QWORD *a1, __int64 a2, unsigned __int64 a3, __int64 a4)
{
  unsigned int v4; // edi
  unsigned int *v5; // r11
  _BYTE *v6; // r10
  unsigned int **v8; // rbx
  int *v10; // rsi
  unsigned int v11; // edi
  int v12; // ecx
  unsigned int *v13; // rdx
  __int64 v14; // r15
  char v15; // r8
  int v16; // ecx
  unsigned int *v17; // rdx
  char v18; // r8
  int v19; // ecx
  unsigned int *v20; // rdx
  unsigned __int64 i; // r9
  char v22; // r8
  int v23; // ecx
  unsigned int *v24; // rdx
  __int64 v25; // rcx

  LOBYTE(v4) = 0;
  v5 = (unsigned int *)(a2 + 4);
  v6 = (_BYTE *)(a2 + 8);
  v8 = (unsigned int **)(a2 + 24);
  v10 = (int *)(a2 + 12);
  if ( a3 > 1 )
  {
    v11 = *v5;
    v12 = (*v6 + 2) & 0xF;
    v13 = (unsigned int *)(*v10 & ((unsigned __int64)*v8 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v6 + 2) >> 3)));
    *(_DWORD *)v6 = v12;
    *v8 = v13;
    v4 = v11 >> 30;
    *v5 = _byteswap_ulong(*v13) << v12;
  }
  *(_DWORD *)v6 += 8;
  v14 = 5 * a4;
  v15 = *((_BYTE *)v5 + 3);
  v16 = *(_DWORD *)v6 & 0xF;
  v17 = (unsigned int *)(*v10 & ((unsigned __int64)*v8 + ((unsigned __int64)*(unsigned int *)v6 >> 3)));
  *(_DWORD *)v6 = v16;
  *v8 = v17;
  *v5 = _byteswap_ulong(*v17) << v16;
  *(_BYTE *)(*a1 + 20 * a4) = v15;
  if ( (_BYTE)v4 == 1 )
  {
    *(_DWORD *)v6 += 8;
    v18 = *((_BYTE *)v5 + 3);
    v19 = *(_DWORD *)v6 & 0xF;
    v20 = (unsigned int *)(*v10 & ((unsigned __int64)*v8 + ((unsigned __int64)*(unsigned int *)v6 >> 3)));
    *(_DWORD *)v6 = v19;
    *v8 = v20;
    *v5 = _byteswap_ulong(*v20) << v19;
    *(_BYTE *)(a1[1] + 20 * a4) = v18;
  }
  else if ( (_BYTE)v4 )
  {
    for ( i = 1; i < a3; *(_BYTE *)(v25 + 4 * v14) = v22 )
    {
      v22 = *((_BYTE *)v5 + 3);
      v23 = (*v6 + 8) & 0xF;
      v24 = (unsigned int *)(*v10 & ((unsigned __int64)*v8 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v6 + 8) >> 3)));
      *(_DWORD *)v6 = v23;
      *v8 = v24;
      *v5 = _byteswap_ulong(*v24) << v23;
      v25 = a1[i++];
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003f748  push    rbx
0x18003f74a  push    rbp
0x18003f74b  push    rsi
0x18003f74c  push    rdi
0x18003f74d  push    r14
0x18003f74f  push    r15
0x18003f751  xor     dil, dil
0x18003f754  lea     r11, [rdx+4]
0x18003f758  lea     r10, [rdx+8]
0x18003f75c  mov     rbp, r8
0x18003f75f  lea     rbx, [rdx+18h]
0x18003f763  mov     r14, rcx
0x18003f766  lea     rsi, [rdx+0Ch]
0x18003f76a  cmp     r8, 1
0x18003f76e  jbe     short loc_18003F79D
0x18003f770  mov     ecx, [r10]
0x18003f773  movsxd  rax, dword ptr [rsi]
0x18003f776  add     ecx, 2
0x18003f779  mov     edi, [r11]
0x18003f77c  mov     edx, ecx
0x18003f77e  and     ecx, 0Fh
0x18003f781  shr     rdx, 3
0x18003f785  add     rdx, [rbx]
0x18003f788  and     rdx, rax
0x18003f78b  mov     [r10], ecx
0x18003f78e  mov     [rbx], rdx
0x18003f791  shr     edi, 1Eh
0x18003f794  mov     eax, [rdx]
0x18003f796  bswap   eax
0x18003f798  shl     eax, cl
0x18003f79a  mov     [r11], eax
0x18003f79d  add     dword ptr [r10], 8
0x18003f7a1  lea     r15, [r9+r9*4]
0x18003f7a5  mov     ecx, [r10]
0x18003f7a8  movsxd  rax, dword ptr [rsi]
0x18003f7ab  mov     edx, ecx
0x18003f7ad  movzx   r8d, byte ptr [r11+3]
0x18003f7b2  and     ecx, 0Fh
0x18003f7b5  shr     rdx, 3
0x18003f7b9  add     rdx, [rbx]
0x18003f7bc  and     rdx, rax
0x18003f7bf  mov     [r10], ecx
0x18003f7c2  mov     [rbx], rdx
0x18003f7c5  mov     eax, [rdx]
0x18003f7c7  bswap   eax
0x18003f7c9  shl     eax, cl
0x18003f7cb  mov     [r11], eax
0x18003f7ce  mov     rax, [r14]
0x18003f7d1  mov     [rax+r15*4], r8b
0x18003f7d5  cmp     dil, 1
0x18003f7d9  jnz     short loc_18003F812
0x18003f7db  add     dword ptr [r10], 8
0x18003f7df  mov     ecx, [r10]
0x18003f7e2  movsxd  rax, dword ptr [rsi]
0x18003f7e5  mov     edx, ecx
0x18003f7e7  movzx   r8d, byte ptr [r11+3]
0x18003f7ec  and     ecx, 0Fh
0x18003f7ef  shr     rdx, 3
0x18003f7f3  add     rdx, [rbx]
0x18003f7f6  and     rdx, rax
0x18003f7f9  mov     [r10], ecx
0x18003f7fc  mov     [rbx], rdx
0x18003f7ff  mov     eax, [rdx]
0x18003f801  bswap   eax
0x18003f803  shl     eax, cl
0x18003f805  mov     [r11], eax
0x18003f808  mov     rax, [r14+8]
0x18003f80c  mov     [rax+r15*4], r8b
0x18003f810  jmp     short loc_18003F85E
0x18003f812  test    dil, dil
0x18003f815  jz      short loc_18003F85E
0x18003f817  mov     r9d, 1
0x18003f81d  cmp     rbp, r9
0x18003f820  jbe     short loc_18003F85E
0x18003f822  mov     ecx, [r10]
0x18003f825  movsxd  rax, dword ptr [rsi]
0x18003f828  add     ecx, 8
0x18003f82b  movzx   r8d, byte ptr [r11+3]
0x18003f830  mov     edx, ecx
0x18003f832  and     ecx, 0Fh
0x18003f835  shr     rdx, 3
0x18003f839  add     rdx, [rbx]
0x18003f83c  and     rdx, rax
0x18003f83f  mov     [r10], ecx
0x18003f842  mov     [rbx], rdx
0x18003f845  mov     edx, [rdx]
0x18003f847  bswap   edx
0x18003f849  shl     edx, cl
0x18003f84b  mov     [r11], edx
0x18003f84e  mov     rcx, [r14+r9*8]
0x18003f852  inc     r9
0x18003f855  mov     [rcx+r15*4], r8b
0x18003f859  cmp     r9, rbp
0x18003f85c  jb      short loc_18003F822
0x18003f85e  mov     al, dil
0x18003f861  pop     r15
0x18003f863  pop     r14
0x18003f865  pop     rdi
0x18003f866  pop     rsi
0x18003f867  pop     rbp
0x18003f868  pop     rbx
0x18003f869  retn
```
