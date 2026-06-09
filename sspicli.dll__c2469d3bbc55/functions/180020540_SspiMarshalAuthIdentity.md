# SspiMarshalAuthIdentity

- ea: `0x180020540`
- end: `0x1800207e9`
- name: `SspiMarshalAuthIdentity`
- size: `681`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity, unsigned int *AuthIdentityLength, char **AuthIdentityByteArray)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e8e4`

## callees

- `0x180005cc0`
- `0x1800078a0`
- `0x180020540`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020599`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002068e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020599`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002068e`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiMarshalAuthIdentity(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity,
        unsigned int *AuthIdentityLength,
        char **AuthIdentityByteArray)
{
  unsigned int v6; // eax
  char *v7; // rax
  unsigned int v8; // ecx
  size_t v9; // r8
  char *v10; // rbx
  int v11; // ecx
  int v12; // ebp
  unsigned int v13; // edx
  unsigned int v15; // eax
  int v16; // ecx
  unsigned int v17; // r8d
  unsigned int v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // eax
  unsigned int v21; // esi
  char *v22; // rax
  char *v23; // r14
  unsigned int v24; // eax
  unsigned int v25; // eax
  char *v26; // rsi
  unsigned int v27; // eax
  __int64 v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rax

  *AuthIdentityByteArray = 0;
  *AuthIdentityLength = 0;
  v6 = SspiValidateAuthIdentity(AuthIdentity);
  if ( (v6 & 0x80000000) == 0 )
  {
    if ( *(_DWORD *)AuthIdentity == 513 )
    {
      if ( (*((_BYTE *)AuthIdentity + 36) & 0x10) != 0 )
      {
LABEL_4:
        v6 = -1073741811;
        return SspNtStatusToSecStatus(v6);
      }
      v7 = (char *)LocalAlloc(0x40u, (unsigned int)(*((_DWORD *)AuthIdentity + 2) + 8) + 2LL);
      *AuthIdentityByteArray = v7;
      if ( !v7 )
      {
LABEL_6:
        v6 = -1073741801;
        return SspNtStatusToSecStatus(v6);
      }
      v8 = *((_DWORD *)AuthIdentity + 2);
      v9 = v8 + 8;
      if ( (*((_DWORD *)AuthIdentity + 9) & 0x10000) == 0 )
        v9 = v8;
      memcpy_0(v7, AuthIdentity, v9);
      *AuthIdentityLength = *((_DWORD *)AuthIdentity + 2) + 8;
LABEL_50:
      v6 = 0;
      return SspNtStatusToSecStatus(v6);
    }
    v10 = (char *)AuthIdentity + 8;
    if ( *(_DWORD *)AuthIdentity != 512 )
      v10 = (char *)AuthIdentity;
    v11 = *((_DWORD *)v10 + 11);
    if ( (v11 & 0x10) != 0 )
      goto LABEL_4;
    v12 = ((v11 & 1) == 0) + 1;
    if ( *(_DWORD *)AuthIdentity == 512 )
    {
      v13 = *((_DWORD *)AuthIdentity + 16) * v12 + 48;
      if ( (unsigned int)(*((_DWORD *)AuthIdentity + 16) * v12) >= 0xFFFFFFD0 )
        goto LABEL_15;
    }
    else
    {
      v13 = 48;
    }
    v15 = *((_DWORD *)v10 + 2) * v12;
    v16 = v11 & 0x10000;
    if ( v16 )
      v15 = (v15 + 7) & 0xFFFFFFF8;
    v17 = v15 + v13;
    if ( v15 + v13 >= v13 )
    {
      v18 = *((_DWORD *)v10 + 6) * v12;
      if ( v16 )
        v18 = (v18 + 7) & 0xFFFFFFF8;
      v19 = v17 + v18;
      if ( v17 + v18 >= v17 )
      {
        v20 = *((_DWORD *)v10 + 10) * v12;
        if ( v16 )
          v20 = (v20 + 7) & 0xFFFFFFF8;
        v21 = v19 + v20;
        if ( v19 + v20 >= v19 )
        {
          v22 = (char *)LocalAlloc(0x40u, v21 + 2LL);
          *AuthIdentityByteArray = v22;
          if ( !v22 )
            goto LABEL_6;
          *AuthIdentityLength = v21;
          v23 = *AuthIdentityByteArray;
          *(_DWORD *)v23 = 512;
          *((_DWORD *)v23 + 1) = 44;
          *((_DWORD *)v23 + 3) = *((_DWORD *)v10 + 2);
          if ( *(_QWORD *)v10 )
          {
            *((_DWORD *)v23 + 2) = 44;
            v24 = *((_DWORD *)v10 + 2) * v12;
            if ( (*((_DWORD *)v10 + 11) & 0x10000) != 0 )
              v24 = (v24 + 7) & 0xFFFFFFF8;
            memcpy_0(v23 + 44, *(const void **)v10, v24);
            v25 = *((_DWORD *)v10 + 2) * v12;
            if ( (*((_DWORD *)v10 + 11) & 0x10000) != 0 )
              v25 = (v25 + 7) & 0xFFFFFFF8;
            v26 = &v23[v25 + 44];
          }
          else
          {
            v26 = v23 + 44;
          }
          *((_DWORD *)v23 + 5) = *((_DWORD *)v10 + 6);
          if ( *((_QWORD *)v10 + 2) )
          {
            *((_DWORD *)v23 + 4) = (_DWORD)v26 - (_DWORD)v23;
            v27 = *((_DWORD *)v10 + 6) * v12;
            if ( (*((_DWORD *)v10 + 11) & 0x10000) != 0 )
              v27 = (v27 + 7) & 0xFFFFFFF8;
            memcpy_0(v26, *((const void **)v10 + 2), v27);
            v28 = (unsigned int)(*((_DWORD *)v10 + 6) * v12);
            if ( (*((_DWORD *)v10 + 11) & 0x10000) != 0 )
              v28 = ((_DWORD)v28 + 7) & 0xFFFFFFF8;
            v26 += v28;
          }
          *((_DWORD *)v23 + 7) = *((_DWORD *)v10 + 10);
          if ( *((_QWORD *)v10 + 4) )
          {
            *((_DWORD *)v23 + 6) = (_DWORD)v26 - (_DWORD)v23;
            v29 = *((_DWORD *)v10 + 10) * v12;
            if ( (*((_DWORD *)v10 + 11) & 0x10000) != 0 )
              v29 = (v29 + 7) & 0xFFFFFFF8;
            memcpy_0(v26, *((const void **)v10 + 4), v29);
            v30 = (unsigned int)(*((_DWORD *)v10 + 10) * v12);
            if ( (*((_DWORD *)v10 + 11) & 0x10000) != 0 )
              v30 = ((_DWORD)v30 + 7) & 0xFFFFFFF8;
            v26 += v30;
          }
          *((_DWORD *)v23 + 8) = *((_DWORD *)v10 + 11);
          if ( *(_DWORD *)AuthIdentity == 512 )
          {
            *((_DWORD *)v23 + 10) = *((_DWORD *)AuthIdentity + 16);
            if ( *((_QWORD *)AuthIdentity + 7) )
            {
              *((_DWORD *)v23 + 9) = (_DWORD)v26 - (_DWORD)v23;
              memcpy_0(v26, *((const void **)AuthIdentity + 7), (unsigned int)(*((_DWORD *)AuthIdentity + 16) * v12));
            }
          }
          goto LABEL_50;
        }
      }
    }
LABEL_15:
    v6 = -1073741675;
  }
  return SspNtStatusToSecStatus(v6);
}

```

## disassembly

```asm
0x180020540  push    rbx
0x180020542  push    rbp
0x180020543  push    rsi
0x180020544  push    rdi
0x180020545  push    r12
0x180020547  push    r14
0x180020549  push    r15
0x18002054b  sub     rsp, 20h
0x18002054f  mov     qword ptr [r8], 0
0x180020556  mov     r14, r8
0x180020559  mov     dword ptr [rdx], 0
0x18002055f  mov     r15, rdx
0x180020562  mov     rdi, rcx
0x180020565  call    SspiValidateAuthIdentity
0x18002056a  test    eax, eax
0x18002056c  js      loc_180020613
0x180020572  cmp     dword ptr [rdi], 201h
0x180020578  jnz     short loc_1800205DC
0x18002057a  test    byte ptr [rdi+24h], 10h
0x18002057e  jz      short loc_18002058A
0x180020580  mov     eax, 0C000000Dh
0x180020585  jmp     loc_180020613
0x18002058a  mov     edx, [rdi+8]
0x18002058d  mov     ecx, 40h ; '@'; uFlags
0x180020592  add     edx, 8
0x180020595  add     rdx, 2; uBytes
0x180020599  call    cs:__imp_LocalAlloc
0x18002059f  mov     [r14], rax
0x1800205a2  test    rax, rax
0x1800205a5  jnz     short loc_1800205AE
0x1800205a7  mov     eax, 0C0000017h
0x1800205ac  jmp     short loc_180020613
0x1800205ae  mov     ecx, [rdi+8]
0x1800205b1  mov     r12d, 10000h
0x1800205b7  test    [rdi+24h], r12d
0x1800205bb  mov     rdx, rdi; Src
0x1800205be  lea     r8d, [rcx+8]
0x1800205c2  cmovz   r8d, ecx; Size
0x1800205c6  mov     rcx, rax; void *
0x1800205c9  call    memcpy_0
0x1800205ce  mov     eax, [rdi+8]
0x1800205d1  add     eax, 8
0x1800205d4  mov     [r15], eax
0x1800205d7  jmp     loc_1800207E2
0x1800205dc  mov     edx, 200h
0x1800205e1  lea     rbx, [rdi+8]
0x1800205e5  cmp     [rdi], edx
0x1800205e7  cmovnz  rbx, rdi
0x1800205eb  mov     ecx, [rbx+2Ch]
0x1800205ee  test    cl, 10h
0x1800205f1  jnz     short loc_180020580
0x1800205f3  mov     ebp, ecx
0x1800205f5  not     ebp
0x1800205f7  and     ebp, 1
0x1800205fa  inc     ebp
0x1800205fc  cmp     [rdi], edx
0x1800205fe  jnz     short loc_180020628
0x180020600  mov     edx, ebp
0x180020602  imul    edx, [rdi+40h]
0x180020606  add     edx, 30h ; '0'
0x180020609  cmp     edx, 30h ; '0'
0x18002060c  jnb     short loc_18002062D
0x18002060e  mov     eax, 0C0000095h
0x180020613  mov     ecx, eax
0x180020615  add     rsp, 20h
0x180020619  pop     r15
0x18002061b  pop     r14
0x18002061d  pop     r12
0x18002061f  pop     rdi
0x180020620  pop     rsi
0x180020621  pop     rbp
0x180020622  pop     rbx
0x180020623  jmp     SspNtStatusToSecStatus
0x180020628  mov     edx, 30h ; '0'
0x18002062d  mov     eax, ebp
0x18002062f  mov     r12d, 10000h
0x180020635  imul    eax, [rbx+8]
0x180020639  mov     r9d, 0FFFFFFF8h
0x18002063f  and     ecx, r12d
0x180020642  jz      short loc_18002064A
0x180020644  add     eax, 7
0x180020647  and     eax, r9d
0x18002064a  lea     r8d, [rax+rdx]
0x18002064e  cmp     r8d, edx
0x180020651  jb      short loc_18002060E
0x180020653  mov     eax, ebp
0x180020655  imul    eax, [rbx+18h]
0x180020659  test    ecx, ecx
0x18002065b  jz      short loc_180020663
0x18002065d  add     eax, 7
0x180020660  and     eax, r9d
0x180020663  lea     edx, [r8+rax]
0x180020667  cmp     edx, r8d
0x18002066a  jb      short loc_18002060E
0x18002066c  mov     eax, ebp
0x18002066e  imul    eax, [rbx+28h]
0x180020672  test    ecx, ecx
0x180020674  jz      short loc_18002067C
0x180020676  add     eax, 7
0x180020679  and     eax, r9d
0x18002067c  lea     esi, [rdx+rax]
0x18002067f  cmp     esi, edx
0x180020681  jb      short loc_18002060E
0x180020683  mov     edx, esi
0x180020685  mov     ecx, 40h ; '@'; uFlags
0x18002068a  add     rdx, 2; uBytes
0x18002068e  call    cs:__imp_LocalAlloc
0x180020694  mov     [r14], rax
0x180020697  test    rax, rax
0x18002069a  jz      loc_1800205A7
0x1800206a0  mov     [r15], esi
0x1800206a3  mov     r14, [r14]
0x1800206a6  mov     dword ptr [r14], 200h
0x1800206ad  lea     r15, [r14+2Ch]
0x1800206b1  mov     dword ptr [r14+4], 2Ch ; ','
0x1800206b9  mov     eax, [rbx+8]
0x1800206bc  mov     [r14+0Ch], eax
0x1800206c0  cmp     qword ptr [rbx], 0
0x1800206c4  jz      short loc_180020709
0x1800206c6  mov     eax, r15d
0x1800206c9  sub     eax, r14d
0x1800206cc  mov     [r14+8], eax
0x1800206d0  mov     eax, ebp
0x1800206d2  imul    eax, [rbx+8]
0x1800206d6  test    [rbx+2Ch], r12d
0x1800206da  jz      short loc_1800206E2
0x1800206dc  add     eax, 7
0x1800206df  and     eax, 0FFFFFFF8h
0x1800206e2  mov     rdx, [rbx]; Src
0x1800206e5  mov     rcx, r15; void *
0x1800206e8  mov     r8d, eax; Size
0x1800206eb  call    memcpy_0
0x1800206f0  mov     eax, ebp
0x1800206f2  imul    eax, [rbx+8]
0x1800206f6  test    [rbx+2Ch], r12d
0x1800206fa  jz      short loc_180020702
0x1800206fc  add     eax, 7
0x1800206ff  and     eax, 0FFFFFFF8h
0x180020702  mov     esi, eax
0x180020704  add     rsi, r15
0x180020707  jmp     short loc_18002070C
0x180020709  mov     rsi, r15
0x18002070c  mov     eax, [rbx+18h]
0x18002070f  mov     r15d, r14d
0x180020712  mov     [r14+14h], eax
0x180020716  cmp     qword ptr [rbx+10h], 0
0x18002071b  jz      short loc_18002075C
0x18002071d  mov     eax, esi
0x18002071f  sub     eax, r14d
0x180020722  mov     [r14+10h], eax
0x180020726  mov     eax, ebp
0x180020728  imul    eax, [rbx+18h]
0x18002072c  test    [rbx+2Ch], r12d
0x180020730  jz      short loc_180020738
0x180020732  add     eax, 7
0x180020735  and     eax, 0FFFFFFF8h
0x180020738  mov     rdx, [rbx+10h]; Src
0x18002073c  mov     rcx, rsi; void *
0x18002073f  mov     r8d, eax; Size
0x180020742  call    memcpy_0
0x180020747  mov     eax, ebp
0x180020749  imul    eax, [rbx+18h]
0x18002074d  test    [rbx+2Ch], r12d
0x180020751  jz      short loc_180020759
0x180020753  add     eax, 7
0x180020756  and     eax, 0FFFFFFF8h
0x180020759  add     rsi, rax
0x18002075c  mov     eax, [rbx+28h]
0x18002075f  mov     [r14+1Ch], eax
0x180020763  cmp     qword ptr [rbx+20h], 0
0x180020768  jz      short loc_1800207A9
0x18002076a  mov     eax, esi
0x18002076c  sub     eax, r15d
0x18002076f  mov     [r14+18h], eax
0x180020773  mov     eax, ebp
0x180020775  imul    eax, [rbx+28h]
0x180020779  test    [rbx+2Ch], r12d
0x18002077d  jz      short loc_180020785
0x18002077f  add     eax, 7
0x180020782  and     eax, 0FFFFFFF8h
0x180020785  mov     rdx, [rbx+20h]; Src
0x180020789  mov     rcx, rsi; void *
0x18002078c  mov     r8d, eax; Size
0x18002078f  call    memcpy_0
0x180020794  mov     eax, ebp
0x180020796  imul    eax, [rbx+28h]
0x18002079a  test    [rbx+2Ch], r12d
0x18002079e  jz      short loc_1800207A6
0x1800207a0  add     eax, 7
0x1800207a3  and     eax, 0FFFFFFF8h
0x1800207a6  add     rsi, rax
0x1800207a9  mov     eax, [rbx+2Ch]
0x1800207ac  mov     [r14+20h], eax
0x1800207b0  cmp     dword ptr [rdi], 200h
0x1800207b6  jnz     short loc_1800207E2
0x1800207b8  mov     eax, [rdi+40h]
0x1800207bb  mov     [r14+28h], eax
0x1800207bf  cmp     qword ptr [rdi+38h], 0
0x1800207c4  jz      short loc_1800207E2
0x1800207c6  mov     eax, esi
0x1800207c8  mov     rcx, rsi; void *
0x1800207cb  sub     eax, r15d
0x1800207ce  mov     [r14+24h], eax
0x1800207d2  imul    ebp, [rdi+40h]
0x1800207d6  mov     rdx, [rdi+38h]; Src
0x1800207da  mov     r8d, ebp; Size
0x1800207dd  call    memcpy_0
0x1800207e2  xor     eax, eax
0x1800207e4  jmp     loc_180020613
```
