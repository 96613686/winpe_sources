# RtlCopyXStateArea

- ea: `0x1400d68a0`
- end: `0x1400d6b72`
- name: `RtlCopyXStateArea`
- size: `722`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140092f74`
- `0x140093674`
- `0x140093844`
- `0x140093f90`

## callees

- `0x1400d68a0`
- `0x1400f9780`

## pseudocode

```c
void __fastcall RtlCopyXStateArea(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebp
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r13
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // r13
  _OWORD *v11; // rax
  __int64 v12; // rdx
  _OWORD *v13; // rcx
  __int128 v14; // xmm1
  unsigned int v15; // r15d
  unsigned __int64 v16; // r14
  int v17; // eax
  unsigned __int64 v18; // r13
  unsigned __int64 v19; // rsi
  int v20; // r8d
  unsigned int v21; // r12d
  unsigned __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rbp
  unsigned __int64 v25; // [rsp+20h] [rbp-48h]
  int v26; // [rsp+78h] [rbp+10h]
  int v27; // [rsp+88h] [rbp+20h]

  if ( a2 )
  {
    v5 = 2;
    v6 = a2 & (MEMORY[0xFFFFF780000003D8] | MEMORY[0xFFFFF780000005F0] | 3LL);
    v7 = v6 & *(_QWORD *)(a3 + 512);
    *(_QWORD *)(a1 + 512) = v7 | *(_QWORD *)(a1 + 512) & ~v6;
    if ( (v7 & 3) == 2 )
      *(_DWORD *)(a1 + 24) = *(_DWORD *)(a3 + 24);
    if ( (MEMORY[0xFFFFF780000003EC] & 2) != 0 )
    {
      v8 = MEMORY[0xFFFFF780000003D8] | MEMORY[0xFFFFF780000005F0] | 0x8000000000000003uLL;
      v9 = *(_QWORD *)(a1 + 520) & v8;
      v10 = *(_QWORD *)(a3 + 520) & v8;
      if ( (v7 & 1) != 0 )
      {
        *(_OWORD *)a1 = *(_OWORD *)a3;
        *(_OWORD *)(a1 + 16) = *(_OWORD *)(a3 + 16);
        *(_OWORD *)(a1 + 32) = *(_OWORD *)(a3 + 32);
        *(_OWORD *)(a1 + 48) = *(_OWORD *)(a3 + 48);
        *(_OWORD *)(a1 + 64) = *(_OWORD *)(a3 + 64);
        *(_OWORD *)(a1 + 80) = *(_OWORD *)(a3 + 80);
        *(_OWORD *)(a1 + 96) = *(_OWORD *)(a3 + 96);
        *(_OWORD *)(a1 + 112) = *(_OWORD *)(a3 + 112);
        *(_OWORD *)(a1 + 128) = *(_OWORD *)(a3 + 128);
        *(_OWORD *)(a1 + 144) = *(_OWORD *)(a3 + 144);
      }
      if ( (v7 & 2) != 0 )
      {
        v11 = (_OWORD *)(a1 + 160);
        v12 = 2;
        v13 = (_OWORD *)(a3 + 160);
        do
        {
          *v11 = *v13;
          v11[1] = v13[1];
          v11[2] = v13[2];
          v11[3] = v13[3];
          v11[4] = v13[4];
          v11[5] = v13[5];
          v11[6] = v13[6];
          v14 = v13[7];
          v13 += 8;
          v11[7] = v14;
          v11 += 8;
          --v12;
        }
        while ( v12 );
      }
      v15 = 576;
      v16 = v9 >> 2;
      v17 = 576;
      v18 = v10 >> 2;
      v26 = 576;
      v19 = v18 & v16 & (v7 >> 2);
      v20 = 576;
      v27 = 576;
      v21 = 576;
      v22 = MEMORY[0xFFFFF780000005F8] >> 2;
      v25 = MEMORY[0xFFFFF780000005F8] >> 2;
      do
      {
        if ( (v18 & 1) != 0 )
        {
          if ( (v22 & 1) != 0 )
            v15 = (v20 + 63) & 0xFFFFFFC0;
          else
            v15 = v20;
          v23 = v5;
          v17 = v26;
          v20 = v15 + *(_DWORD *)(4LL * v5 - 0x87FFFFFF9FCLL);
          v27 = v20;
        }
        else
        {
          v23 = v5;
        }
        if ( (v16 & 1) != 0 )
        {
          if ( (v22 & 1) != 0 )
            v21 = (v17 + 63) & 0xFFFFFFC0;
          else
            v21 = v17;
          v17 = v21 + *(_DWORD *)(4 * v23 - 0x87FFFFFF9FCLL);
          v26 = v17;
        }
        if ( (v19 & 1) != 0 )
        {
          memmove((void *)(a1 + v21), (const void *)(a3 + v15), v20 - v15);
          v22 = v25;
          v17 = v26;
        }
        v19 >>= 1;
        if ( !v19 )
          break;
        v20 = v27;
        ++v5;
        v22 >>= 1;
        v18 >>= 1;
        v16 >>= 1;
        v25 = v22;
      }
      while ( v5 < 0x40 );
    }
    else
    {
      v24 = 0;
      do
      {
        if ( (v7 & 1) != 0 )
          memmove(
            (void *)(*(unsigned int *)(8 * v24 - 0x87FFFFFFC10LL) + a1),
            (const void *)(*(unsigned int *)(8 * v24 - 0x87FFFFFFC10LL) + a3),
            *(unsigned int *)(8 * v24 - 0x87FFFFFFC0CLL));
        v7 >>= 1;
        if ( !v7 )
          break;
        v24 = (unsigned int)(v24 + 1);
      }
      while ( (unsigned int)v24 < 0x40 );
    }
  }
}

```

## disassembly

```asm
0x1400d68a0  test    rdx, rdx
0x1400d68a3  jz      locret_1400D6B70
0x1400d68a9  mov     [rsp+arg_0], rbx
0x1400d68ae  push    rbp
0x1400d68af  push    rsi
0x1400d68b0  push    rdi
0x1400d68b1  push    r12
0x1400d68b3  push    r13
0x1400d68b5  push    r14
0x1400d68b7  push    r15
0x1400d68b9  sub     rsp, 30h
0x1400d68bd  mov     rbx, rcx
0x1400d68c0  mov     rdi, r8
0x1400d68c3  mov     rcx, 0FFFFF780000005F0h
0x1400d68cd  mov     r10, rcx
0x1400d68d0  mov     r8, 0FFFFF780000003D8h
0x1400d68da  mov     rax, r8
0x1400d68dd  mov     r9, [rax]
0x1400d68e0  mov     ebp, 2
0x1400d68e5  mov     rax, [r10]
0x1400d68e8  mov     rsi, [rdi+200h]
0x1400d68ef  or      rax, r9
0x1400d68f2  or      rax, 3
0x1400d68f6  and     rax, rdx
0x1400d68f9  and     rsi, rax
0x1400d68fc  not     rax
0x1400d68ff  and     rax, [rbx+200h]
0x1400d6906  or      rax, rsi
0x1400d6909  mov     [rbx+200h], rax
0x1400d6910  mov     al, sil
0x1400d6913  and     al, 3
0x1400d6915  cmp     al, bpl
0x1400d6918  jnz     short loc_1400D6920
0x1400d691a  mov     eax, [rdi+18h]
0x1400d691d  mov     [rbx+18h], eax
0x1400d6920  mov     rax, 0FFFFF780000003ECh
0x1400d692a  mov     eax, [rax]
0x1400d692c  test    bpl, al
0x1400d692f  jz      loc_1400D6B20
0x1400d6935  mov     rdx, rcx
0x1400d6938  mov     rax, r8
0x1400d693b  mov     r14, [rdx]
0x1400d693e  or      r14, [rax]
0x1400d6941  mov     rax, 8000000000000003h
0x1400d694b  or      r14, rax
0x1400d694e  mov     r13, r14
0x1400d6951  and     r14, [rbx+208h]
0x1400d6958  and     r13, [rdi+208h]
0x1400d695f  test    sil, 1
0x1400d6963  jz      short loc_1400D69BF
0x1400d6965  movups  xmm0, xmmword ptr [rdi]
0x1400d6968  movups  xmmword ptr [rbx], xmm0
0x1400d696b  movups  xmm1, xmmword ptr [rdi+10h]
0x1400d696f  movups  xmmword ptr [rbx+10h], xmm1
0x1400d6973  movups  xmm0, xmmword ptr [rdi+20h]
0x1400d6977  movups  xmmword ptr [rbx+20h], xmm0
0x1400d697b  movups  xmm1, xmmword ptr [rdi+30h]
0x1400d697f  movups  xmmword ptr [rbx+30h], xmm1
0x1400d6983  movups  xmm0, xmmword ptr [rdi+40h]
0x1400d6987  movups  xmmword ptr [rbx+40h], xmm0
0x1400d698b  movups  xmm1, xmmword ptr [rdi+50h]
0x1400d698f  movups  xmmword ptr [rbx+50h], xmm1
0x1400d6993  movups  xmm0, xmmword ptr [rdi+60h]
0x1400d6997  movups  xmmword ptr [rbx+60h], xmm0
0x1400d699b  movups  xmm1, xmmword ptr [rdi+70h]
0x1400d699f  movups  xmmword ptr [rbx+70h], xmm1
0x1400d69a3  movups  xmm0, xmmword ptr [rdi+80h]
0x1400d69aa  movups  xmmword ptr [rbx+80h], xmm0
0x1400d69b1  movups  xmm1, xmmword ptr [rdi+90h]
0x1400d69b8  movups  xmmword ptr [rbx+90h], xmm1
0x1400d69bf  test    bpl, sil
0x1400d69c2  jz      short loc_1400D6A25
0x1400d69c4  lea     rax, [rbx+0A0h]
0x1400d69cb  mov     rdx, rbp
0x1400d69ce  lea     rcx, [rdi+0A0h]
0x1400d69d5  mov     r8d, 80h
0x1400d69db  movups  xmm0, xmmword ptr [rcx]
0x1400d69de  movups  xmmword ptr [rax], xmm0
0x1400d69e1  movups  xmm1, xmmword ptr [rcx+10h]
0x1400d69e5  movups  xmmword ptr [rax+10h], xmm1
0x1400d69e9  movups  xmm0, xmmword ptr [rcx+20h]
0x1400d69ed  movups  xmmword ptr [rax+20h], xmm0
0x1400d69f1  movups  xmm1, xmmword ptr [rcx+30h]
0x1400d69f5  movups  xmmword ptr [rax+30h], xmm1
0x1400d69f9  movups  xmm0, xmmword ptr [rcx+40h]
0x1400d69fd  movups  xmmword ptr [rax+40h], xmm0
0x1400d6a01  movups  xmm1, xmmword ptr [rcx+50h]
0x1400d6a05  movups  xmmword ptr [rax+50h], xmm1
0x1400d6a09  movups  xmm0, xmmword ptr [rcx+60h]
0x1400d6a0d  movups  xmmword ptr [rax+60h], xmm0
0x1400d6a11  movups  xmm1, xmmword ptr [rcx+70h]
0x1400d6a15  add     rcx, r8
0x1400d6a18  movups  xmmword ptr [rax+70h], xmm1
0x1400d6a1c  add     rax, r8
0x1400d6a1f  sub     rdx, 1
0x1400d6a23  jnz     short loc_1400D69DB
0x1400d6a25  mov     r15d, 240h
0x1400d6a2b  shr     rsi, 2
0x1400d6a2f  shr     r14, 2
0x1400d6a33  mov     eax, r15d
0x1400d6a36  and     rsi, r14
0x1400d6a39  shr     r13, 2
0x1400d6a3d  mov     [rsp+68h+arg_8], eax
0x1400d6a41  and     rsi, r13
0x1400d6a44  mov     r8d, r15d
0x1400d6a47  mov     [rsp+68h+arg_18], r15d
0x1400d6a4f  mov     r12d, r15d
0x1400d6a52  mov     r9, 0FFFFF780000005F8h
0x1400d6a5c  mov     r9, [r9]
0x1400d6a5f  shr     r9, 2
0x1400d6a63  mov     [rsp+68h+var_48], r9
0x1400d6a68  mov     rcx, r9
0x1400d6a6b  and     ecx, 1
0x1400d6a6e  test    r13b, 1
0x1400d6a72  jz      short loc_1400D6AA7
0x1400d6a74  test    rcx, rcx
0x1400d6a77  jz      short loc_1400D6A83
0x1400d6a79  lea     r15d, [r8+3Fh]
0x1400d6a7d  and     r15d, 0FFFFFFC0h
0x1400d6a81  jmp     short loc_1400D6A86
0x1400d6a83  mov     r15d, r8d
0x1400d6a86  mov     edx, ebp
0x1400d6a88  mov     rax, 0FFFFF78000000604h
0x1400d6a92  mov     r8d, [rax+rdx*4]
0x1400d6a96  mov     eax, [rsp+68h+arg_8]
0x1400d6a9a  add     r8d, r15d
0x1400d6a9d  mov     [rsp+68h+arg_18], r8d
0x1400d6aa5  jmp     short loc_1400D6AA9
0x1400d6aa7  mov     edx, ebp
0x1400d6aa9  test    r14b, 1
0x1400d6aad  jz      short loc_1400D6AD5
0x1400d6aaf  test    rcx, rcx
0x1400d6ab2  jz      short loc_1400D6ABE
0x1400d6ab4  lea     r12d, [rax+3Fh]
0x1400d6ab8  and     r12d, 0FFFFFFC0h
0x1400d6abc  jmp     short loc_1400D6AC1
0x1400d6abe  mov     r12d, eax
0x1400d6ac1  mov     rax, 0FFFFF78000000604h
0x1400d6acb  mov     eax, [rax+rdx*4]
0x1400d6ace  add     eax, r12d
0x1400d6ad1  mov     [rsp+68h+arg_8], eax
0x1400d6ad5  test    sil, 1
0x1400d6ad9  jz      short loc_1400D6AF8
0x1400d6adb  mov     edx, r15d
0x1400d6ade  sub     r8d, r15d; Size
0x1400d6ae1  mov     ecx, r12d
0x1400d6ae4  add     rdx, rdi; Src
0x1400d6ae7  add     rcx, rbx; void *
0x1400d6aea  call    memmove
0x1400d6aef  mov     r9, [rsp+68h+var_48]
0x1400d6af4  mov     eax, [rsp+68h+arg_8]
0x1400d6af8  shr     rsi, 1
0x1400d6afb  jz      short loc_1400D6B5C
0x1400d6afd  mov     r8d, [rsp+68h+arg_18]
0x1400d6b05  inc     ebp
0x1400d6b07  shr     r9, 1
0x1400d6b0a  shr     r13, 1
0x1400d6b0d  shr     r14, 1
0x1400d6b10  mov     [rsp+68h+var_48], r9
0x1400d6b15  cmp     ebp, 40h ; '@'
0x1400d6b18  jb      loc_1400D6A68
0x1400d6b1e  jmp     short loc_1400D6B5C
0x1400d6b20  xor     ebp, ebp
0x1400d6b22  test    sil, 1
0x1400d6b26  jz      short loc_1400D6B50
0x1400d6b28  mov     rax, 0FFFFF780000003F0h
0x1400d6b32  mov     eax, [rax+rbp*8]
0x1400d6b35  mov     rdx, 0FFFFF780000003F4h
0x1400d6b3f  mov     r8d, [rdx+rbp*8]; Size
0x1400d6b43  lea     rcx, [rax+rbx]; void *
0x1400d6b47  lea     rdx, [rax+rdi]; Src
0x1400d6b4b  call    memmove
0x1400d6b50  shr     rsi, 1
0x1400d6b53  jz      short loc_1400D6B5C
0x1400d6b55  inc     ebp
0x1400d6b57  cmp     ebp, 40h ; '@'
0x1400d6b5a  jb      short loc_1400D6B22
0x1400d6b5c  mov     rbx, [rsp+68h+arg_0]
0x1400d6b61  add     rsp, 30h
0x1400d6b65  pop     r15
0x1400d6b67  pop     r14
0x1400d6b69  pop     r13
0x1400d6b6b  pop     r12
0x1400d6b6d  pop     rdi
0x1400d6b6e  pop     rsi
0x1400d6b6f  pop     rbp
0x1400d6b70  retn
```
