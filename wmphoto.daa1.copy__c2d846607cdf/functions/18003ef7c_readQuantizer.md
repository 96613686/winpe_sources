# readQuantizer

- ea: `0x18003ef7c`
- end: `0x18003f09e`
- name: `readQuantizer`
- size: `290`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180031110`
- `0x1800312c4`
- `0x180032914`

## callees

- `0x18003ef7c`

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
0x18003ef7c  push    rbx
0x18003ef7e  push    rbp
0x18003ef7f  push    rsi
0x18003ef80  push    rdi
0x18003ef81  push    r14
0x18003ef83  push    r15
0x18003ef85  xor     dil, dil
0x18003ef88  lea     r11, [rdx+4]
0x18003ef8c  lea     r10, [rdx+8]
0x18003ef90  mov     rbp, r8
0x18003ef93  lea     rbx, [rdx+18h]
0x18003ef97  mov     r14, rcx
0x18003ef9a  lea     rsi, [rdx+0Ch]
0x18003ef9e  cmp     r8, 1
0x18003efa2  jbe     short loc_18003EFD1
0x18003efa4  mov     ecx, [r10]
0x18003efa7  movsxd  rax, dword ptr [rsi]
0x18003efaa  add     ecx, 2
0x18003efad  mov     edi, [r11]
0x18003efb0  mov     edx, ecx
0x18003efb2  and     ecx, 0Fh
0x18003efb5  shr     rdx, 3
0x18003efb9  add     rdx, [rbx]
0x18003efbc  and     rdx, rax
0x18003efbf  mov     [r10], ecx
0x18003efc2  mov     [rbx], rdx
0x18003efc5  shr     edi, 1Eh
0x18003efc8  mov     eax, [rdx]
0x18003efca  bswap   eax
0x18003efcc  shl     eax, cl
0x18003efce  mov     [r11], eax
0x18003efd1  add     dword ptr [r10], 8
0x18003efd5  lea     r15, [r9+r9*4]
0x18003efd9  mov     ecx, [r10]
0x18003efdc  movsxd  rax, dword ptr [rsi]
0x18003efdf  mov     edx, ecx
0x18003efe1  movzx   r8d, byte ptr [r11+3]
0x18003efe6  and     ecx, 0Fh
0x18003efe9  shr     rdx, 3
0x18003efed  add     rdx, [rbx]
0x18003eff0  and     rdx, rax
0x18003eff3  mov     [r10], ecx
0x18003eff6  mov     [rbx], rdx
0x18003eff9  mov     eax, [rdx]
0x18003effb  bswap   eax
0x18003effd  shl     eax, cl
0x18003efff  mov     [r11], eax
0x18003f002  mov     rax, [r14]
0x18003f005  mov     [rax+r15*4], r8b
0x18003f009  cmp     dil, 1
0x18003f00d  jnz     short loc_18003F046
0x18003f00f  add     dword ptr [r10], 8
0x18003f013  mov     ecx, [r10]
0x18003f016  movsxd  rax, dword ptr [rsi]
0x18003f019  mov     edx, ecx
0x18003f01b  movzx   r8d, byte ptr [r11+3]
0x18003f020  and     ecx, 0Fh
0x18003f023  shr     rdx, 3
0x18003f027  add     rdx, [rbx]
0x18003f02a  and     rdx, rax
0x18003f02d  mov     [r10], ecx
0x18003f030  mov     [rbx], rdx
0x18003f033  mov     eax, [rdx]
0x18003f035  bswap   eax
0x18003f037  shl     eax, cl
0x18003f039  mov     [r11], eax
0x18003f03c  mov     rax, [r14+8]
0x18003f040  mov     [rax+r15*4], r8b
0x18003f044  jmp     short loc_18003F092
0x18003f046  test    dil, dil
0x18003f049  jz      short loc_18003F092
0x18003f04b  mov     r9d, 1
0x18003f051  cmp     rbp, r9
0x18003f054  jbe     short loc_18003F092
0x18003f056  mov     ecx, [r10]
0x18003f059  movsxd  rax, dword ptr [rsi]
0x18003f05c  add     ecx, 8
0x18003f05f  movzx   r8d, byte ptr [r11+3]
0x18003f064  mov     edx, ecx
0x18003f066  and     ecx, 0Fh
0x18003f069  shr     rdx, 3
0x18003f06d  add     rdx, [rbx]
0x18003f070  and     rdx, rax
0x18003f073  mov     [r10], ecx
0x18003f076  mov     [rbx], rdx
0x18003f079  mov     edx, [rdx]
0x18003f07b  bswap   edx
0x18003f07d  shl     edx, cl
0x18003f07f  mov     [r11], edx
0x18003f082  mov     rcx, [r14+r9*8]
0x18003f086  inc     r9
0x18003f089  mov     [rcx+r15*4], r8b
0x18003f08d  cmp     r9, rbp
0x18003f090  jb      short loc_18003F056
0x18003f092  mov     al, dil
0x18003f095  pop     r15
0x18003f097  pop     r14
0x18003f099  pop     rdi
0x18003f09a  pop     rsi
0x18003f09b  pop     rbp
0x18003f09c  pop     rbx
0x18003f09d  retn
```
