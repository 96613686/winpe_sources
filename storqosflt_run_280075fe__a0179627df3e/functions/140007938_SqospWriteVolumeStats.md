# SqospWriteVolumeStats

- ea: `0x140007938`
- end: `0x140007e71`
- name: `SqospWriteVolumeStats`
- size: `1337`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011f10`

## callees

- `0x1400078e4`
- `0x140007938`
- `0x140009240`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007c9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007e4d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007c9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007e4d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007969`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007969`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b42`

## pseudocode

```c
__int64 __fastcall SqospWriteVolumeStats(__int64 a1, _WORD *a2, unsigned int a3, int *a4)
{
  __int64 v5; // rbx
  unsigned int v8; // edi
  unsigned int v9; // r8d
  __int64 *v10; // rdx
  __int64 *v11; // rsi
  unsigned __int64 v12; // r10
  __int64 *v13; // r9
  bool v14; // cc
  bool v15; // zf
  unsigned int v16; // ecx
  int v17; // ebp
  __int64 v18; // r12
  int v19; // r13d
  _OWORD *v20; // rbp
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rax
  unsigned __int64 v30; // rax
  int v31; // ecx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rcx
  __int128 v35; // xmm0
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rcx
  int *v43; // rax
  __int64 v44; // r8
  int v46; // [rsp+20h] [rbp-48h]
  int i; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v48; // [rsp+80h] [rbp+18h]
  int *v49; // [rsp+88h] [rbp+20h]

  v49 = a4;
  v48 = a3;
  v5 = a3;
  v8 = 0;
  *(_BYTE *)(a1 + 840) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 832));
  if ( (unsigned int)v5 < *(_DWORD *)(a1 + 4316) )
    goto LABEL_2;
  v9 = 0;
  v10 = (__int64 *)(a1 + 896);
  v11 = *(__int64 **)(a1 + 896);
  v12 = (v5 - 632) / 0x88uLL;
  v13 = v11;
  if ( v11 == (__int64 *)(a1 + 896) )
    goto LABEL_10;
  while ( 1 )
  {
    v14 = v9 <= (unsigned int)v12;
    if ( v9 >= (unsigned int)v12 )
      break;
    v15 = *((_BYTE *)v13 + 416) == 0;
    v16 = v9 + 1;
    v13 = (__int64 *)*v13;
    if ( v15 )
      v16 = v9;
    v9 = v16;
    if ( v13 == v10 )
    {
      v14 = v16 <= (unsigned int)v12;
      break;
    }
  }
  if ( v14 )
  {
LABEL_10:
    v17 = 0;
    v46 = 0;
    LODWORD(v18) = -1;
    v19 = 136 * v9 + 632;
    for ( i = v19; v11 != v10; v11 = (__int64 *)*v11 )
    {
      if ( *((_BYTE *)v11 + 416) )
      {
        v20 = &a2[68 * v17 + 316];
        memset(v20, 0, 0x88u);
        *v20 = *(_OWORD *)(*(v11 - 2) + 88);
        if ( *((_BYTE *)v11 + 417) )
        {
          *((_DWORD *)v20 + 32) = v19;
          v21 = SqospWriteUnicodeString(a2, (unsigned int)v5, &i, v11 + 4);
          v19 = i;
          *((_DWORD *)v20 + 33) = v21;
        }
        v22 = v11[23];
        LODWORD(v23) = -1;
        if ( (unsigned __int64)(v22 - v11[47]) < 0xFFFFFFFF )
          v23 = v11[23] - v11[47];
        *((_DWORD *)v20 + 24) = v23;
        LODWORD(v23) = -1;
        v11[47] = v22;
        v24 = v11[24];
        if ( (unsigned __int64)(v24 - v11[48]) < 0xFFFFFFFF )
          v23 = v11[24] - v11[48];
        *((_DWORD *)v20 + 25) = v23;
        LODWORD(v23) = -1;
        v11[48] = v24;
        v25 = v11[25];
        if ( (unsigned __int64)(v25 - v11[49]) < 0xFFFFFFFF )
          v23 = v11[25] - v11[49];
        *((_DWORD *)v20 + 26) = v23;
        v11[49] = v25;
        v26 = v11[26];
        *((_QWORD *)v20 + 14) = (unsigned __int64)(qword_14000D298 * (v26 - v11[50])) >> 16;
        v11[50] = v26;
        v27 = v11[27];
        *((_QWORD *)v20 + 15) = (unsigned __int64)(qword_14000D298 * (v27 - v11[51])) >> 16;
        v28 = *(v11 - 2);
        v11[51] = v27;
        *(_BYTE *)(v28 + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v28);
        v20[1] = *(_OWORD *)(*(v11 - 2) + 136);
        v20[2] = *(_OWORD *)(*(v11 - 2) + 152);
        v29 = *(v11 - 2);
        if ( *(_BYTE *)(v29 + 126) )
        {
          *((_DWORD *)v20 + 12) = *((_DWORD *)v20 + 24);
          *((_DWORD *)v20 + 13) = *((_DWORD *)v20 + 25);
          *((_QWORD *)v20 + 8) = *((_QWORD *)v20 + 14);
          *((_QWORD *)v20 + 9) = *((_QWORD *)v20 + 15);
          *((_DWORD *)v20 + 14) = *((_DWORD *)v20 + 26);
        }
        else
        {
          v30 = *(_QWORD *)(v29 + 224);
          v31 = -1;
          if ( v30 < 0xFFFFFFFF )
            v31 = v30;
          *((_DWORD *)v20 + 12) = v31;
          *(_QWORD *)(*(v11 - 2) + 224) = 0;
          LODWORD(v32) = -1;
          if ( *(_QWORD *)(*(v11 - 2) + 232) < 0xFFFFFFFF )
            v32 = *(_QWORD *)(*(v11 - 2) + 232);
          *((_DWORD *)v20 + 13) = v32;
          *(_QWORD *)(*(v11 - 2) + 232) = 0;
          LODWORD(v32) = -1;
          if ( *(_QWORD *)(*(v11 - 2) + 240) < 0xFFFFFFFF )
            v32 = *(_QWORD *)(*(v11 - 2) + 240);
          *((_DWORD *)v20 + 14) = v32;
          *(_QWORD *)(*(v11 - 2) + 240) = 0;
          *((_QWORD *)v20 + 8) = *(_QWORD *)(*(v11 - 2) + 248);
          *(_QWORD *)(*(v11 - 2) + 248) = 0;
          *((_QWORD *)v20 + 9) = *(_QWORD *)(*(v11 - 2) + 256);
          *(_QWORD *)(*(v11 - 2) + 256) = 0;
        }
        LODWORD(v5) = v48;
        if ( *((_BYTE *)v11 + 417) )
        {
          *((_DWORD *)v20 + 20) = v19;
          *((_DWORD *)v20 + 21) = SqospWriteUnicodeString(a2, (unsigned int)v5, &i, *(v11 - 2) + 168);
          *((_DWORD *)v20 + 22) = i;
          v33 = SqospWriteUnicodeString(a2, (unsigned int)v5, &i, *(v11 - 2) + 184);
          v19 = i;
          *((_DWORD *)v20 + 23) = v33;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)*(v11 - 2), *(_BYTE *)(*(v11 - 2) + 8));
        v10 = (__int64 *)(a1 + 896);
        v17 = v46 + 1;
        *((_BYTE *)v11 + 416) = 0;
        ++v46;
      }
    }
    memset(a2, 0, 0x278u);
    *a2 = 257;
    v34 = 0;
    *((_DWORD *)a2 + 1) = 3;
    v35 = *(_OWORD *)(a1 + 8);
    *((_DWORD *)a2 + 156) = 632;
    *((_DWORD *)a2 + 157) = v17;
    *((_OWORD *)a2 + 33) = v35;
    do
    {
      *(_QWORD *)&a2[4 * v34 + 292] = *(_QWORD *)(a1 + 8 * v34 + 1296) / 0x2000LL;
      ++v34;
    }
    while ( v34 != 4 );
    v36 = *(_QWORD *)(a1 + 4032);
    v37 = qword_14000D2D0;
    *((_QWORD *)a2 + 77) = v36;
    if ( !v36 || v36 > v37 || (v37 = qword_14000D2D8, v36 < qword_14000D2D8) )
      *((_QWORD *)a2 + 77) = v37;
    v38 = *(_QWORD *)(a1 + 4064);
    LODWORD(v39) = -1;
    if ( (unsigned __int64)(v38 - *(_QWORD *)(a1 + 4320)) < 0xFFFFFFFF )
      v39 = *(_QWORD *)(a1 + 4064) - *(_QWORD *)(a1 + 4320);
    *((_DWORD *)a2 + 138) = v39;
    LODWORD(v39) = -1;
    *(_QWORD *)(a1 + 4320) = v38;
    v40 = *(_QWORD *)(a1 + 4088);
    if ( (unsigned __int64)(v40 - *(_QWORD *)(a1 + 4328)) < 0xFFFFFFFF )
      v39 = *(_QWORD *)(a1 + 4088) - *(_QWORD *)(a1 + 4328);
    *((_DWORD *)a2 + 139) = v39;
    *(_QWORD *)(a1 + 4328) = v40;
    v41 = *(_QWORD *)(a1 + 4112);
    if ( (unsigned __int64)(v41 - *(_QWORD *)(a1 + 4336)) < 0xFFFFFFFF )
      v18 = *(_QWORD *)(a1 + 4112) - *(_QWORD *)(a1 + 4336);
    *((_DWORD *)a2 + 140) = v18;
    *(_QWORD *)(a1 + 4336) = v41;
    v42 = *(_QWORD *)(a1 + 4144);
    *((_QWORD *)a2 + 71) = (unsigned __int64)(qword_14000D298 * (v42 - *(_QWORD *)(a1 + 4344))) >> 16;
    v43 = v49;
    *(_QWORD *)(a1 + 4344) = v42;
    v44 = *(_QWORD *)(a1 + 4152);
    *((_QWORD *)a2 + 72) = (unsigned __int64)(qword_14000D298 * (v44 - *(_QWORD *)(a1 + 4352))) >> 16;
    *(_QWORD *)(a1 + 4352) = v44;
    *v43 = v19;
  }
  else
  {
LABEL_2:
    *a4 = 0;
    v8 = -1073741789;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 832), *(_BYTE *)(a1 + 840));
  return v8;
}

```

## disassembly

```asm
0x140007938  mov     [rsp+arg_8], rbx
0x14000793d  mov     [rsp+arg_18], r9
0x140007942  mov     [rsp+arg_10], r8d
0x140007947  push    rbp
0x140007948  push    rsi
0x140007949  push    rdi
0x14000794a  push    r12
0x14000794c  push    r13
0x14000794e  push    r14
0x140007950  push    r15
0x140007952  sub     rsp, 30h
0x140007956  mov     r14, rcx
0x140007959  mov     ebx, r8d
0x14000795c  add     rcx, 340h; SpinLock
0x140007963  mov     rbp, r9
0x140007966  mov     r15, rdx
0x140007969  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007970  nop     dword ptr [rax+rax+00h]
0x140007975  xor     edi, edi
0x140007977  mov     [r14+348h], al
0x14000797e  cmp     ebx, [r14+10DCh]
0x140007985  jnb     short loc_140007994
0x140007987  mov     [rbp+0], edi
0x14000798a  mov     edi, 0C0000023h
0x14000798f  jmp     loc_140007E3F
0x140007994  mov     rcx, rbx
0x140007997  mov     r11d, 278h
0x14000799d  sub     rcx, r11
0x1400079a0  mov     rax, 0F0F0F0F0F0F0F0F1h
0x1400079aa  mul     rcx
0x1400079ad  mov     r8d, edi
0x1400079b0  mov     r10, rdx
0x1400079b3  lea     rdx, [r14+380h]
0x1400079ba  mov     rsi, [rdx]
0x1400079bd  shr     r10, 7
0x1400079c1  mov     r9, rsi
0x1400079c4  cmp     rsi, rdx
0x1400079c7  jz      short loc_1400079ED
0x1400079c9  cmp     r8d, r10d
0x1400079cc  jnb     short loc_1400079EB
0x1400079ce  cmp     [r9+1A0h], dil
0x1400079d5  lea     ecx, [r8+1]
0x1400079d9  mov     r9, [r9]
0x1400079dc  cmovz   ecx, r8d
0x1400079e0  mov     r8d, ecx
0x1400079e3  cmp     r9, rdx
0x1400079e6  jnz     short loc_1400079C9
0x1400079e8  cmp     ecx, r10d
0x1400079eb  ja      short loc_140007987
0x1400079ed  imul    r13d, r8d, 88h
0x1400079f4  mov     ebp, edi
0x1400079f6  mov     [rsp+68h+var_48], edi
0x1400079fa  mov     r12d, 0FFFFFFFFh
0x140007a00  add     r13d, r11d
0x140007a03  mov     [rsp+68h+arg_0], r13d
0x140007a08  cmp     rsi, rdx
0x140007a0b  jz      loc_140007CD2
0x140007a11  cmp     [rsi+1A0h], dil
0x140007a18  jz      loc_140007CC0
0x140007a1e  mov     eax, ebp
0x140007a20  xor     edx, edx; Val
0x140007a22  imul    rbp, rax, 88h
0x140007a29  mov     r8d, 88h; Size
0x140007a2f  add     rbp, 278h
0x140007a36  add     rbp, r15
0x140007a39  mov     rcx, rbp; void *
0x140007a3c  call    memset
0x140007a41  mov     rax, [rsi-10h]
0x140007a45  movups  xmm0, xmmword ptr [rax+58h]
0x140007a49  movdqu  xmmword ptr [rbp+0], xmm0
0x140007a4e  cmp     [rsi+1A1h], dil
0x140007a55  jz      short loc_140007A7C
0x140007a57  lea     r9, [rsi+20h]
0x140007a5b  mov     [rbp+80h], r13d
0x140007a62  lea     r8, [rsp+68h+arg_0]
0x140007a67  mov     edx, ebx
0x140007a69  mov     rcx, r15
0x140007a6c  call    SqospWriteUnicodeString
0x140007a71  mov     r13d, [rsp+68h+arg_0]
0x140007a76  mov     [rbp+84h], eax
0x140007a7c  mov     rdx, [rsi+0B8h]
0x140007a83  mov     rcx, r12
0x140007a86  mov     rax, rdx
0x140007a89  sub     rax, [rsi+178h]
0x140007a90  cmp     rax, r12
0x140007a93  cmovb   rcx, rax
0x140007a97  mov     [rbp+60h], ecx
0x140007a9a  mov     rcx, r12
0x140007a9d  mov     [rsi+178h], rdx
0x140007aa4  mov     rdx, [rsi+0C0h]
0x140007aab  mov     rax, rdx
0x140007aae  sub     rax, [rsi+180h]
0x140007ab5  cmp     rax, r12
0x140007ab8  cmovb   rcx, rax
0x140007abc  mov     [rbp+64h], ecx
0x140007abf  mov     rcx, r12
0x140007ac2  mov     [rsi+180h], rdx
0x140007ac9  mov     rdx, [rsi+0C8h]
0x140007ad0  mov     rax, rdx
0x140007ad3  sub     rax, [rsi+188h]
0x140007ada  cmp     rax, r12
0x140007add  cmovb   rcx, rax
0x140007ae1  mov     [rbp+68h], ecx
0x140007ae4  mov     [rsi+188h], rdx
0x140007aeb  mov     rcx, [rsi+0D0h]
0x140007af2  mov     rax, rcx
0x140007af5  sub     rax, [rsi+190h]
0x140007afc  imul    rax, cs:qword_14000D298
0x140007b04  shr     rax, 10h
0x140007b08  mov     [rbp+70h], rax
0x140007b0c  mov     [rsi+190h], rcx
0x140007b13  mov     rcx, [rsi+0D8h]
0x140007b1a  mov     rax, rcx
0x140007b1d  sub     rax, [rsi+198h]
0x140007b24  imul    rax, cs:qword_14000D298
0x140007b2c  shr     rax, 10h
0x140007b30  mov     [rbp+78h], rax
0x140007b34  mov     rbx, [rsi-10h]
0x140007b38  mov     [rsi+198h], rcx
0x140007b3f  mov     rcx, rbx; SpinLock
0x140007b42  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007b49  nop     dword ptr [rax+rax+00h]
0x140007b4e  mov     [rbx+8], al
0x140007b51  mov     rax, [rsi-10h]
0x140007b55  movups  xmm0, xmmword ptr [rax+88h]
0x140007b5c  movdqu  xmmword ptr [rbp+10h], xmm0
0x140007b61  mov     rax, [rsi-10h]
0x140007b65  movups  xmm1, xmmword ptr [rax+98h]
0x140007b6c  movdqu  xmmword ptr [rbp+20h], xmm1
0x140007b71  mov     rax, [rsi-10h]
0x140007b75  cmp     [rax+7Eh], dil
0x140007b79  jz      short loc_140007BA2
0x140007b7b  mov     eax, [rbp+60h]
0x140007b7e  mov     [rbp+30h], eax
0x140007b81  mov     eax, [rbp+64h]
0x140007b84  mov     [rbp+34h], eax
0x140007b87  mov     rax, [rbp+70h]
0x140007b8b  mov     [rbp+40h], rax
0x140007b8f  mov     rax, [rbp+78h]
0x140007b93  mov     [rbp+48h], rax
0x140007b97  mov     eax, [rbp+68h]
0x140007b9a  mov     [rbp+38h], eax
0x140007b9d  jmp     loc_140007C3B
0x140007ba2  mov     rax, [rax+0E0h]
0x140007ba9  mov     rcx, r12
0x140007bac  cmp     rax, r12
0x140007baf  cmovb   rcx, rax
0x140007bb3  mov     [rbp+30h], ecx
0x140007bb6  mov     rax, [rsi-10h]
0x140007bba  mov     [rax+0E0h], rdi
0x140007bc1  mov     rax, [rsi-10h]
0x140007bc5  mov     rcx, [rax+0E8h]
0x140007bcc  mov     rax, r12
0x140007bcf  cmp     rcx, r12
0x140007bd2  cmovb   rax, rcx
0x140007bd6  mov     [rbp+34h], eax
0x140007bd9  mov     rax, [rsi-10h]
0x140007bdd  mov     [rax+0E8h], rdi
0x140007be4  mov     rax, [rsi-10h]
0x140007be8  mov     rcx, [rax+0F0h]
0x140007bef  mov     rax, r12
0x140007bf2  cmp     rcx, r12
0x140007bf5  cmovb   rax, rcx
0x140007bf9  mov     [rbp+38h], eax
0x140007bfc  mov     rax, [rsi-10h]
0x140007c00  mov     [rax+0F0h], rdi
0x140007c07  mov     rax, [rsi-10h]
0x140007c0b  mov     rcx, [rax+0F8h]
0x140007c12  mov     [rbp+40h], rcx
0x140007c16  mov     rax, [rsi-10h]
0x140007c1a  mov     [rax+0F8h], rdi
0x140007c21  mov     rax, [rsi-10h]
0x140007c25  mov     rcx, [rax+100h]
0x140007c2c  mov     [rbp+48h], rcx
0x140007c30  mov     rax, [rsi-10h]
0x140007c34  mov     [rax+100h], rdi
0x140007c3b  mov     ebx, [rsp+68h+arg_10]
0x140007c42  cmp     [rsi+1A1h], dil
0x140007c49  jz      short loc_140007C95
0x140007c4b  mov     [rbp+50h], r13d
0x140007c4f  lea     r8, [rsp+68h+arg_0]
0x140007c54  mov     r9, [rsi-10h]
0x140007c58  mov     edx, ebx
0x140007c5a  add     r9, 0A8h
0x140007c61  mov     rcx, r15
0x140007c64  call    SqospWriteUnicodeString
0x140007c69  mov     [rbp+54h], eax
0x140007c6c  lea     r8, [rsp+68h+arg_0]
0x140007c71  mov     eax, [rsp+68h+arg_0]
0x140007c75  mov     edx, ebx
0x140007c77  mov     [rbp+58h], eax
0x140007c7a  mov     rcx, r15
0x140007c7d  mov     r9, [rsi-10h]
0x140007c81  add     r9, 0B8h
0x140007c88  call    SqospWriteUnicodeString
0x140007c8d  mov     r13d, [rsp+68h+arg_0]
0x140007c92  mov     [rbp+5Ch], eax
0x140007c95  mov     rcx, [rsi-10h]; SpinLock
0x140007c99  mov     dl, [rcx+8]; NewIrql
0x140007c9c  call    cs:__imp_KeReleaseSpinLock
0x140007ca3  nop     dword ptr [rax+rax+00h]
0x140007ca8  mov     ebp, [rsp+68h+var_48]
0x140007cac  lea     rdx, [r14+380h]
0x140007cb3  inc     ebp
0x140007cb5  mov     [rsi+1A0h], dil
0x140007cbc  mov     [rsp+68h+var_48], ebp
0x140007cc0  mov     rsi, [rsi]
0x140007cc3  cmp     rsi, rdx
0x140007cc6  jnz     loc_140007A11
0x140007ccc  mov     r11d, 278h
0x140007cd2  mov     r8, r11; Size
0x140007cd5  xor     edx, edx; Val
0x140007cd7  mov     rcx, r15; void *
0x140007cda  call    memset
0x140007cdf  mov     word ptr [r15], 101h
0x140007ce5  mov     rcx, rdi
0x140007ce8  mov     dword ptr [r15+4], 3
0x140007cf0  movups  xmm0, xmmword ptr [r14+8]
0x140007cf5  mov     dword ptr [r15+270h], 278h
0x140007d00  mov     [r15+274h], ebp
0x140007d07  movdqu  xmmword ptr [r15+210h], xmm0
0x140007d10  mov     rax, [r14+rcx*8+510h]
0x140007d18  mov     r8d, 2000h
0x140007d1e  cqo
0x140007d20  idiv    r8
0x140007d23  mov     [r15+rcx*8+248h], rax
0x140007d2b  inc     rcx
0x140007d2e  cmp     rcx, 4
0x140007d32  jnz     short loc_140007D10
0x140007d34  mov     rax, [r14+0FC0h]
0x140007d3b  mov     rcx, cs:qword_14000D2D0
0x140007d42  mov     [r15+268h], rax
0x140007d49  test    rax, rax
0x140007d4c  jz      short loc_140007D5F
0x140007d4e  cmp     rax, rcx
0x140007d51  ja      short loc_140007D5F
0x140007d53  mov     rcx, cs:qword_14000D2D8
0x140007d5a  cmp     rax, rcx
0x140007d5d  jnb     short loc_140007D66
0x140007d5f  mov     [r15+268h], rcx
0x140007d66  mov     rdx, [r14+0FE0h]
0x140007d6d  mov     rcx, r12
0x140007d70  mov     rax, rdx
0x140007d73  sub     rax, [r14+10E0h]
0x140007d7a  cmp     rax, r12
0x140007d7d  cmovb   rcx, rax
0x140007d81  mov     [r15+228h], ecx
0x140007d88  mov     rcx, r12
0x140007d8b  mov     [r14+10E0h], rdx
0x140007d92  mov     rdx, [r14+0FF8h]
0x140007d99  mov     rax, rdx
0x140007d9c  sub     rax, [r14+10E8h]
0x140007da3  cmp     rax, r12
0x140007da6  cmovb   rcx, rax
0x140007daa  mov     [r15+22Ch], ecx
0x140007db1  mov     [r14+10E8h], rdx
0x140007db8  mov     rcx, [r14+1010h]
0x140007dbf  mov     rax, rcx
0x140007dc2  sub     rax, [r14+10F0h]
0x140007dc9  cmp     rax, r12
0x140007dcc  cmovb   r12, rax
0x140007dd0  mov     [r15+230h], r12d
0x140007dd7  mov     [r14+10F0h], rcx
0x140007dde  mov     rcx, [r14+1030h]
0x140007de5  mov     rax, rcx
0x140007de8  sub     rax, [r14+10F8h]
0x140007def  imul    rax, cs:qword_14000D298
0x140007df7  shr     rax, 10h
0x140007dfb  mov     [r15+238h], rax
0x140007e02  mov     rax, [rsp+68h+arg_18]
0x140007e0a  mov     [r14+10F8h], rcx
0x140007e11  mov     r8, [r14+1038h]
0x140007e18  mov     rdx, r8
0x140007e1b  sub     rdx, [r14+1100h]
0x140007e22  imul    rdx, cs:qword_14000D298
0x140007e2a  shr     rdx, 10h
0x140007e2e  mov     [r15+240h], rdx
0x140007e35  mov     [r14+1100h], r8
0x140007e3c  mov     [rax], r13d
0x140007e3f  mov     dl, [r14+348h]; NewIrql
0x140007e46  lea     rcx, [r14+340h]; SpinLock
0x140007e4d  call    cs:__imp_KeReleaseSpinLock
0x140007e54  nop     dword ptr [rax+rax+00h]
0x140007e59  mov     rbx, [rsp+68h+arg_8]
0x140007e5e  mov     eax, edi
0x140007e60  add     rsp, 30h
0x140007e64  pop     r15
0x140007e66  pop     r14
0x140007e68  pop     r13
0x140007e6a  pop     r12
0x140007e6c  pop     rdi
0x140007e6d  pop     rsi
0x140007e6e  pop     rbp
0x140007e6f  retn
```
