# SspiCopyAuthIdentity

- ea: `0x180008920`
- end: `0x180008e8d`
- name: `SspiCopyAuthIdentity`
- size: `1389`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *AuthDataCopy)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017410`

## callees

- `0x180005cc0`
- `0x1800078a0`
- `0x180008920`
- `0x180014520`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008986`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008bf1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008c5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008cab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008dd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008e3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008986`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008bf1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008c5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008cab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008dd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008e3b`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiCopyAuthIdentity(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *AuthDataCopy)
{
  _QWORD *v3; // rbp
  void *v4; // r15
  _DWORD *v5; // rsi
  const void **v6; // rdi
  SECURITY_STATUS v7; // ebx
  _DWORD *v8; // rax
  unsigned int v9; // ecx
  size_t v10; // r8
  unsigned int v11; // ecx
  unsigned int v12; // edx
  unsigned int v13; // ecx
  __int64 v14; // rbp
  _WORD *v15; // rax
  unsigned __int64 v16; // r15
  _WORD *v17; // rbx
  int v18; // r10d
  _WORD *v19; // rbp
  char *v20; // rcx
  size_t v21; // r8
  unsigned int v22; // r12d
  __int64 v23; // rdx
  unsigned __int16 v24; // bx
  _QWORD *v25; // rax
  char *v26; // r13
  HLOCAL v27; // rax
  _OWORD *v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // eax
  HLOCAL v31; // rax
  void *v32; // rcx
  unsigned int v34; // eax
  unsigned int v35; // eax
  HLOCAL v36; // rax
  void *v37; // rcx
  unsigned int v38; // eax
  unsigned int v39; // eax
  HLOCAL v40; // rax
  void *v41; // rcx
  unsigned int v42; // eax
  unsigned __int16 v43; // [rsp+60h] [rbp+8h]

  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = (const void **)AuthData;
  v7 = SspiValidateAuthIdentity(AuthData);
  if ( v7 < 0 )
  {
LABEL_51:
    *AuthDataCopy = 0;
    if ( v4 )
      SspiFreeAuthIdentity(v4);
    if ( !v3 )
      goto LABEL_55;
    goto LABEL_54;
  }
  if ( *(_DWORD *)v6 == 513 )
  {
    if ( (*((_DWORD *)v6 + 9) & 0x10070) != 0 )
    {
      if ( (*((_DWORD *)v6 + 9) & 0x10000) != 0 )
      {
        v8 = LocalAlloc(0x40u, (unsigned int)(*((_DWORD *)v6 + 2) + 8) + 2LL);
        v5 = v8;
        if ( v8 )
        {
          v9 = *((_DWORD *)v6 + 2);
          v10 = v9 + 8;
          if ( (*((_DWORD *)v6 + 9) & 0x10000) == 0 )
            v10 = v9;
          memcpy_0(v8, v6, v10);
          goto LABEL_9;
        }
        goto LABEL_45;
      }
LABEL_36:
      v7 = -1073741811;
LABEL_46:
      *AuthDataCopy = 0;
      goto LABEL_55;
    }
    v11 = *((unsigned __int16 *)v6 + 8) + 64;
    if ( v11 < 0x40 )
      goto LABEL_36;
    v12 = v11 + *((unsigned __int16 *)v6 + 12);
    if ( v12 < v11 )
      goto LABEL_36;
    v13 = v12 + *((unsigned __int16 *)v6 + 22);
    if ( v13 < v12 )
      goto LABEL_36;
    v14 = v13 + *((unsigned __int16 *)v6 + 16);
    if ( (unsigned int)v14 < v13 || (unsigned int)v14 > 0xFFFF )
      goto LABEL_36;
    v15 = LocalAlloc(0x40u, v14 + 2);
    v5 = v15;
    if ( v15 )
    {
      *(_DWORD *)v15 = 513;
      v16 = (unsigned __int64)v15 + v14;
      v15[2] = 48;
      v17 = v15 + 24;
      *((_DWORD *)v15 + 2) = v14 - 8;
      if ( *((_DWORD *)v6 + 3) )
      {
        *((_DWORD *)v15 + 3) = 48;
        v15[8] = *((_WORD *)v6 + 8);
        memcpy_0(v17, (char *)v6 + *((unsigned int *)v6 + 3), *((unsigned __int16 *)v6 + 8));
        v17 = (_WORD *)((char *)v17 + *((unsigned __int16 *)v5 + 8));
      }
      if ( *((_DWORD *)v6 + 5) )
      {
        v5[5] = (_DWORD)v17 - (_DWORD)v5;
        *((_WORD *)v5 + 12) = *((_WORD *)v6 + 12);
        memcpy_0(v17, (char *)v6 + *((unsigned int *)v6 + 5), *((unsigned __int16 *)v6 + 12));
        v17 = (_WORD *)((char *)v17 + *((unsigned __int16 *)v5 + 12));
      }
      if ( *((_DWORD *)v6 + 7) )
      {
        v18 = (int)v17;
        v5[7] = (_DWORD)v17 - (_DWORD)v5;
        v19 = v17;
        if ( v16 - (unsigned __int64)v17 < 0x1C )
          goto LABEL_36;
        v20 = (char *)v6 + *((unsigned int *)v6 + 7);
        if ( *((_WORD *)v6 + 16) < *((_WORD *)v20 + 1) )
          goto LABEL_36;
        *v17 = 28;
        *(_OWORD *)(v17 + 2) = *(_OWORD *)(v20 + 4);
        v21 = *((unsigned __int16 *)v20 + 12);
        v17 += 14;
        v22 = (v21 + 7) & 0xFFFFFFF8;
        if ( (int)v16 - (int)v17 < v22
          || (v23 = *((unsigned int *)v20 + 5), (int)v23 + (int)v21 < (unsigned int)v23)
          || (int)v23 + (int)v21 > (unsigned int)*((unsigned __int16 *)v20 + 1) )
        {
          v7 = -1073741811;
          *AuthDataCopy = 0;
          goto LABEL_55;
        }
        if ( (_DWORD)v23 )
        {
          v19[12] = v21;
          *((_DWORD *)v19 + 5) = (_DWORD)v17 - v18;
          memcpy_0(v17, &v20[v23], v21);
          v17 = (_WORD *)((char *)v17 + v22);
        }
        v19[1] = (_WORD)v17 - (_WORD)v19;
        *((_WORD *)v5 + 16) = (_WORD)v17 - (_WORD)v19;
      }
      if ( *((_DWORD *)v6 + 10) )
      {
        if ( (int)v16 - (int)v17 < (unsigned int)*((unsigned __int16 *)v6 + 22) )
          goto LABEL_36;
        v5[10] = (_DWORD)v17 - (_DWORD)v5;
        *((_WORD *)v5 + 22) = *((_WORD *)v6 + 22);
        memcpy_0(v17, (char *)v6 + *((unsigned int *)v6 + 10), *((unsigned __int16 *)v6 + 22));
        v17 = (_WORD *)((char *)v17 + *((unsigned __int16 *)v5 + 22));
      }
      if ( (unsigned __int64)(v17 + 4) <= v16 )
      {
        v5[9] = *((_DWORD *)v6 + 9) | 0x10000;
LABEL_9:
        *AuthDataCopy = v5;
LABEL_10:
        v7 = 0;
        return SspNtStatusToSecStatus((unsigned int)v7);
      }
      goto LABEL_36;
    }
LABEL_45:
    v7 = -1073741801;
    goto LABEL_46;
  }
  if ( *(_DWORD *)v6 != 512 )
  {
    v24 = 2 - ((*((_DWORD *)v6 + 11) & 1) != 0);
    v43 = v24;
    v28 = LocalAlloc(0x40u, 0x32u);
    v4 = v28;
    if ( !v28 )
      goto LABEL_45;
    *v28 = *(_OWORD *)v6;
    v28[1] = *((_OWORD *)v6 + 1);
    v28[2] = *((_OWORD *)v6 + 2);
    *((_QWORD *)v28 + 2) = 0;
    *(_QWORD *)v28 = 0;
    *((_QWORD *)v28 + 4) = 0;
    v26 = (char *)v28;
    *AuthDataCopy = v28;
LABEL_48:
    v29 = v24;
    if ( *v6 )
    {
      v30 = ((*((_DWORD *)v6 + 2) * v24 + 7) & 0xFFFFFFF8) / v24;
      *((_DWORD *)v26 + 2) = v30;
      v31 = LocalAlloc(0x40u, v24 * (v30 + 1) + 2LL);
      *(_QWORD *)v26 = v31;
      v32 = v31;
      if ( !v31 )
      {
LABEL_50:
        v7 = -1073741801;
        goto LABEL_51;
      }
      v34 = *((_DWORD *)v6 + 2) * v24;
      if ( (*((_DWORD *)v6 + 11) & 0x10000) != 0 )
        v34 = (v34 + 7) & 0xFFFFFFF8;
      memcpy_0(v32, *v6, v34);
      v29 = v24;
      *((_DWORD *)v26 + 2) = *((_DWORD *)v6 + 2);
    }
    if ( v6[2] )
    {
      v35 = ((*((_DWORD *)v6 + 6) * v29 + 7) & 0xFFFFFFF8) / v29;
      *((_DWORD *)v26 + 6) = v35;
      v36 = LocalAlloc(0x40u, v29 * (v35 + 1) + 2LL);
      *((_QWORD *)v26 + 2) = v36;
      v37 = v36;
      if ( !v36 )
        goto LABEL_50;
      v38 = *((_DWORD *)v6 + 6) * v24;
      if ( (*((_DWORD *)v6 + 11) & 0x10000) != 0 )
        v38 = (v38 + 7) & 0xFFFFFFF8;
      memcpy_0(v37, v6[2], v38);
      *((_DWORD *)v26 + 6) = *((_DWORD *)v6 + 6);
    }
    if ( v6[4] )
    {
      v39 = ((v24 * (*((_DWORD *)v6 + 10) + 1) + 7) & 0xFFFFFFF8) / v24;
      *((_DWORD *)v26 + 10) = v39;
      v40 = LocalAlloc(0x40u, v24 * (v39 + 1) + 2LL);
      *((_QWORD *)v26 + 4) = v40;
      v41 = v40;
      if ( !v40 )
        goto LABEL_50;
      v42 = *((_DWORD *)v6 + 10) * v43;
      if ( (*((_DWORD *)v6 + 11) & 0x10000) != 0 )
        v42 = (v42 + 7) & 0xFFFFFFF8;
      memcpy_0(v41, v6[4], v42);
      *((_DWORD *)v26 + 10) = *((_DWORD *)v6 + 10);
    }
    *((_DWORD *)v26 + 11) = *((_DWORD *)v26 + 11) & 0xFFFEFFFB | 0x10000;
    goto LABEL_10;
  }
  v24 = 2 - ((*((_DWORD *)v6 + 13) & 1) != 0);
  v43 = v24;
  v25 = LocalAlloc(0x40u, 0x4Au);
  v3 = v25;
  if ( !v25 )
    goto LABEL_45;
  *(_OWORD *)v25 = *(_OWORD *)v6;
  *((_OWORD *)v25 + 1) = *((_OWORD *)v6 + 1);
  *((_OWORD *)v25 + 2) = *((_OWORD *)v6 + 2);
  *((_OWORD *)v25 + 3) = *((_OWORD *)v6 + 3);
  v25[8] = v6[8];
  v25[3] = 0;
  v26 = (char *)(v25 + 1);
  v25[1] = 0;
  v25[5] = 0;
  v25[7] = 0;
  *AuthDataCopy = v25;
  if ( !v6[7] )
  {
LABEL_43:
    ++v6;
    goto LABEL_48;
  }
  v27 = LocalAlloc(0x40u, (unsigned int)v24 * (*((_DWORD *)v6 + 16) + 1) + 2LL);
  v3[7] = v27;
  if ( v27 )
  {
    memcpy_0(v27, v6[7], *((_DWORD *)v6 + 16) * (unsigned int)v24);
    goto LABEL_43;
  }
  v7 = -1073741801;
  *AuthDataCopy = 0;
LABEL_54:
  SspiFreeAuthIdentity(v3);
LABEL_55:
  if ( v5 )
    SspiFreeAuthIdentity(v5);
  return SspNtStatusToSecStatus((unsigned int)v7);
}

```

## disassembly

```asm
0x180008920  mov     [rsp+arg_8], rbx
0x180008925  push    rbp
0x180008926  push    rsi
0x180008927  push    rdi
0x180008928  push    r12
0x18000892a  push    r13
0x18000892c  push    r14
0x18000892e  push    r15
0x180008930  sub     rsp, 20h
0x180008934  xor     r13d, r13d
0x180008937  mov     r14, rdx
0x18000893a  mov     ebp, r13d
0x18000893d  mov     r15d, r13d
0x180008940  mov     esi, r13d
0x180008943  mov     rdi, rcx
0x180008946  call    SspiValidateAuthIdentity
0x18000894b  mov     ebx, eax
0x18000894d  test    eax, eax
0x18000894f  js      loc_180008D3D
0x180008955  cmp     dword ptr [rdi], 201h
0x18000895b  jnz     loc_180008BC4
0x180008961  test    dword ptr [rdi+24h], 10070h
0x180008968  jz      short loc_1800089BC
0x18000896a  mov     ebx, 10000h
0x18000896f  test    [rdi+24h], ebx
0x180008972  jz      loc_180008BBA
0x180008978  mov     edx, [rdi+8]
0x18000897b  lea     ecx, [r13+40h]; uFlags
0x18000897f  add     edx, 8
0x180008982  add     rdx, 2; uBytes
0x180008986  call    cs:__imp_LocalAlloc
0x18000898c  mov     rsi, rax
0x18000898f  test    rax, rax
0x180008992  jz      loc_180008CB9
0x180008998  mov     ecx, [rdi+8]
0x18000899b  mov     rdx, rdi; Src
0x18000899e  test    [rdi+24h], ebx
0x1800089a1  lea     r8d, [rcx+8]
0x1800089a5  cmovz   r8d, ecx; Size
0x1800089a9  mov     rcx, rax; void *
0x1800089ac  call    memcpy_0
0x1800089b1  mov     [r14], rsi
0x1800089b4  mov     ebx, r13d
0x1800089b7  jmp     loc_180008D67
0x1800089bc  movzx   ecx, word ptr [rdi+10h]
0x1800089c0  mov     r12d, 40h ; '@'
0x1800089c6  add     ecx, 40h ; '@'
0x1800089c9  cmp     ecx, r12d
0x1800089cc  jb      loc_180008BBA
0x1800089d2  movzx   edx, word ptr [rdi+18h]
0x1800089d6  add     edx, ecx
0x1800089d8  cmp     edx, ecx
0x1800089da  jb      loc_180008BBA
0x1800089e0  movzx   ecx, word ptr [rdi+2Ch]
0x1800089e4  add     ecx, edx
0x1800089e6  cmp     ecx, edx
0x1800089e8  jb      loc_180008BBA
0x1800089ee  movzx   ebp, word ptr [rdi+20h]
0x1800089f2  add     ebp, ecx
0x1800089f4  cmp     ebp, ecx
0x1800089f6  jb      loc_180008BBA
0x1800089fc  cmp     ebp, 0FFFFh
0x180008a02  ja      loc_180008BBA
0x180008a08  lea     rdx, [rbp+2]; uBytes
0x180008a0c  mov     ecx, r12d; uFlags
0x180008a0f  call    cs:__imp_LocalAlloc
0x180008a15  mov     rsi, rax
0x180008a18  test    rax, rax
0x180008a1b  jz      loc_180008CB9
0x180008a21  mov     dword ptr [rax], 201h
0x180008a27  lea     r15, [rax+rbp]
0x180008a2b  mov     word ptr [rax+4], 30h ; '0'
0x180008a31  lea     rbx, [rax+30h]
0x180008a35  lea     eax, [rbp-8]
0x180008a38  mov     [rsi+8], eax
0x180008a3b  cmp     [rdi+0Ch], r13d
0x180008a3f  jz      short loc_180008A6A
0x180008a41  mov     eax, ebx
0x180008a43  mov     rcx, rbx; void *
0x180008a46  sub     eax, esi
0x180008a48  mov     [rsi+0Ch], eax
0x180008a4b  movzx   eax, word ptr [rdi+10h]
0x180008a4f  mov     [rsi+10h], ax
0x180008a53  mov     edx, [rdi+0Ch]
0x180008a56  movzx   r8d, word ptr [rdi+10h]; Size
0x180008a5b  add     rdx, rdi; Src
0x180008a5e  call    memcpy_0
0x180008a63  movzx   eax, word ptr [rsi+10h]
0x180008a67  add     rbx, rax
0x180008a6a  mov     ebp, esi
0x180008a6c  cmp     [rdi+14h], r13d
0x180008a70  jz      short loc_180008A9B
0x180008a72  mov     eax, ebx
0x180008a74  mov     rcx, rbx; void *
0x180008a77  sub     eax, esi
0x180008a79  mov     [rsi+14h], eax
0x180008a7c  movzx   eax, word ptr [rdi+18h]
0x180008a80  mov     [rsi+18h], ax
0x180008a84  mov     edx, [rdi+14h]
0x180008a87  movzx   r8d, word ptr [rdi+18h]; Size
0x180008a8c  add     rdx, rdi; Src
0x180008a8f  call    memcpy_0
0x180008a94  movzx   eax, word ptr [rsi+18h]
0x180008a98  add     rbx, rax
0x180008a9b  cmp     [rdi+1Ch], r13d
0x180008a9f  jz      loc_180008B55
0x180008aa5  mov     eax, ebx
0x180008aa7  mov     edx, 1Ch
0x180008aac  sub     eax, ebp
0x180008aae  mov     r10d, ebx
0x180008ab1  mov     [rsi+1Ch], eax
0x180008ab4  mov     rbp, rbx
0x180008ab7  mov     rax, r15
0x180008aba  sub     rax, rbx
0x180008abd  cmp     rax, rdx
0x180008ac0  jb      loc_180008BBA
0x180008ac6  mov     ecx, [rdi+1Ch]
0x180008ac9  add     rcx, rdi
0x180008acc  movzx   eax, word ptr [rcx+2]
0x180008ad0  cmp     [rdi+20h], ax
0x180008ad4  jb      loc_180008BBA
0x180008ada  mov     [rbx], dx
0x180008add  mov     eax, r15d
0x180008ae0  movups  xmm0, xmmword ptr [rcx+4]
0x180008ae4  movdqu  xmmword ptr [rbx+4], xmm0
0x180008ae9  movzx   r8d, word ptr [rcx+18h]; Size
0x180008aee  add     rbx, rdx
0x180008af1  sub     eax, ebx
0x180008af3  mov     r13, rbx
0x180008af6  lea     r12d, [r8+7]
0x180008afa  and     r12d, 0FFFFFFF8h
0x180008afe  cmp     eax, r12d
0x180008b01  jb      loc_180008BA9
0x180008b07  mov     edx, [rcx+14h]
0x180008b0a  lea     r9d, [rdx+r8]
0x180008b0e  cmp     r9d, edx
0x180008b11  jb      loc_180008BA9
0x180008b17  movzx   eax, word ptr [rcx+2]
0x180008b1b  cmp     r9d, eax
0x180008b1e  ja      loc_180008BA9
0x180008b24  test    edx, edx
0x180008b26  jz      short loc_180008B44
0x180008b28  sub     ebx, r10d
0x180008b2b  mov     [rbp+18h], r8w
0x180008b30  add     rdx, rcx; Src
0x180008b33  mov     [rbp+14h], ebx
0x180008b36  mov     rcx, r13; void *
0x180008b39  call    memcpy_0
0x180008b3e  mov     ebx, r12d
0x180008b41  add     rbx, r13
0x180008b44  movzx   eax, bx
0x180008b47  sub     ax, bp
0x180008b4a  mov     [rbp+2], ax
0x180008b4e  xor     r13d, r13d
0x180008b51  mov     [rsi+20h], ax
0x180008b55  cmp     [rdi+28h], r13d
0x180008b59  jz      short loc_180008B91
0x180008b5b  movzx   eax, word ptr [rdi+2Ch]
0x180008b5f  mov     ecx, r15d
0x180008b62  sub     ecx, ebx
0x180008b64  cmp     ecx, eax
0x180008b66  jb      short loc_180008BBA
0x180008b68  mov     eax, ebx
0x180008b6a  mov     rcx, rbx; void *
0x180008b6d  sub     eax, esi
0x180008b6f  mov     [rsi+28h], eax
0x180008b72  movzx   eax, word ptr [rdi+2Ch]
0x180008b76  mov     [rsi+2Ch], ax
0x180008b7a  mov     edx, [rdi+28h]
0x180008b7d  movzx   r8d, word ptr [rdi+2Ch]; Size
0x180008b82  add     rdx, rdi; Src
0x180008b85  call    memcpy_0
0x180008b8a  movzx   eax, word ptr [rsi+2Ch]
0x180008b8e  add     rbx, rax
0x180008b91  lea     rax, [rbx+8]
0x180008b95  cmp     rax, r15
0x180008b98  ja      short loc_180008BBA
0x180008b9a  mov     eax, [rdi+24h]
0x180008b9d  bts     eax, 10h
0x180008ba1  mov     [rsi+24h], eax
0x180008ba4  jmp     loc_1800089B1
0x180008ba9  mov     ebx, 0C000000Dh
0x180008bae  mov     qword ptr [r14], 0
0x180008bb5  jmp     loc_180008D5A
0x180008bba  mov     ebx, 0C000000Dh
0x180008bbf  jmp     loc_180008CBE
0x180008bc4  cmp     dword ptr [rdi], 200h
0x180008bca  mov     r12d, 40h ; '@'
0x180008bd0  mov     ecx, r12d; uFlags
0x180008bd3  jnz     loc_180008C93
0x180008bd9  mov     eax, [rdi+34h]
0x180008bdc  lea     edx, [r12+0Ah]; uBytes
0x180008be1  and     al, 1
0x180008be3  neg     al
0x180008be5  sbb     bx, bx
0x180008be8  add     bx, 2
0x180008bec  mov     [rsp+58h+arg_0], bx
0x180008bf1  call    cs:__imp_LocalAlloc
0x180008bf7  mov     rbp, rax
0x180008bfa  test    rax, rax
0x180008bfd  jz      loc_180008CB9
0x180008c03  movups  xmm0, xmmword ptr [rdi]
0x180008c06  movups  xmmword ptr [rax], xmm0
0x180008c09  movups  xmm1, xmmword ptr [rdi+10h]
0x180008c0d  movups  xmmword ptr [rax+10h], xmm1
0x180008c11  movups  xmm0, xmmword ptr [rdi+20h]
0x180008c15  movups  xmmword ptr [rax+20h], xmm0
0x180008c19  movups  xmm1, xmmword ptr [rdi+30h]
0x180008c1d  movups  xmmword ptr [rax+30h], xmm1
0x180008c21  movsd   xmm0, qword ptr [rdi+40h]
0x180008c26  movsd   qword ptr [rax+40h], xmm0
0x180008c2b  mov     [rax+18h], r13
0x180008c2f  lea     r13, [rax+8]
0x180008c33  xor     eax, eax
0x180008c35  mov     [r13+0], rax
0x180008c39  mov     [rbp+28h], rax
0x180008c3d  mov     [rbp+38h], rax
0x180008c41  mov     [r14], rbp
0x180008c44  cmp     [rdi+38h], rax
0x180008c48  jz      short loc_180008C8D
0x180008c4a  mov     edx, [rdi+40h]
0x180008c4d  inc     edx
0x180008c4f  movzx   ecx, bx
0x180008c52  imul    edx, ecx
0x180008c55  mov     ecx, r12d; uFlags
0x180008c58  add     rdx, 2; uBytes
0x180008c5c  call    cs:__imp_LocalAlloc
0x180008c62  mov     [rbp+38h], rax
0x180008c66  mov     rcx, rax; void *
0x180008c69  test    rax, rax
0x180008c6c  jnz     short loc_180008C7B
0x180008c6e  mov     ebx, 0C0000017h
0x180008c73  mov     [r14], rsi
0x180008c76  jmp     loc_180008D52
0x180008c7b  mov     rdx, [rdi+38h]; Src
0x180008c7f  movzx   r8d, bx
0x180008c83  imul    r8d, [rdi+40h]; Size
0x180008c88  call    memcpy_0
0x180008c8d  add     rdi, 8
0x180008c91  jmp     short loc_180008CED
0x180008c93  mov     eax, [rdi+2Ch]
0x180008c96  mov     edx, 32h ; '2'; uBytes
0x180008c9b  and     al, 1
0x180008c9d  neg     al
0x180008c9f  sbb     bx, bx
0x180008ca2  add     bx, 2
0x180008ca6  mov     [rsp+58h+arg_0], bx
0x180008cab  call    cs:__imp_LocalAlloc
0x180008cb1  mov     r15, rax
0x180008cb4  test    rax, rax
0x180008cb7  jnz     short loc_180008CC6
0x180008cb9  mov     ebx, 0C0000017h
0x180008cbe  mov     [r14], r13
0x180008cc1  jmp     loc_180008D5A
0x180008cc6  movups  xmm0, xmmword ptr [rdi]
0x180008cc9  movups  xmmword ptr [rax], xmm0
0x180008ccc  movups  xmm1, xmmword ptr [rdi+10h]
0x180008cd0  movups  xmmword ptr [rax+10h], xmm1
0x180008cd4  movups  xmm0, xmmword ptr [rdi+20h]
0x180008cd8  movups  xmmword ptr [rax+20h], xmm0
0x180008cdc  mov     [rax+10h], r13
0x180008ce0  mov     [rax], r13
0x180008ce3  mov     [rax+20h], r13
0x180008ce7  mov     r13, rax
0x180008cea  mov     [r14], rax
0x180008ced  movzx   ecx, bx
0x180008cf0  mov     ebx, 10000h
0x180008cf5  mov     [rsp+58h+arg_10], ecx
0x180008cf9  cmp     [rdi], rsi
0x180008cfc  jz      loc_180008DAB
0x180008d02  xor     edx, edx
0x180008d04  mov     eax, ecx
0x180008d06  imul    eax, [rdi+8]
0x180008d0a  add     eax, 7
0x180008d0d  and     eax, 0FFFFFFF8h
0x180008d10  div     ecx
0x180008d12  mov     [r13+8], eax
0x180008d16  lea     edx, [rax+1]
0x180008d19  imul    edx, ecx
0x180008d1c  mov     ecx, r12d; uFlags
0x180008d1f  add     rdx, 2; uBytes
0x180008d23  call    cs:__imp_LocalAlloc
0x180008d29  mov     [r13+0], rax
0x180008d2d  mov     rcx, rax; void *
0x180008d30  test    rax, rax
0x180008d33  jnz     short loc_180008D82
0x180008d35  mov     ebx, 0C0000017h
0x180008d3a  xor     r13d, r13d
0x180008d3d  mov     [r14], r13
0x180008d40  test    r15, r15
0x180008d43  jz      short loc_180008D4D
0x180008d45  mov     rcx, r15; AuthData
0x180008d48  call    SspiFreeAuthIdentity
0x180008d4d  test    rbp, rbp
0x180008d50  jz      short loc_180008D5A
0x180008d52  mov     rcx, rbp; AuthData
0x180008d55  call    SspiFreeAuthIdentity
0x180008d5a  test    rsi, rsi
0x180008d5d  jz      short loc_180008D67
0x180008d5f  mov     rcx, rsi; AuthData
  ... truncated ...
```
