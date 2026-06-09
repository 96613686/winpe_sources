# SspiEncodeStringsAsAuthIdentity

- ea: `0x180017e40`
- end: `0x180018429`
- name: `SspiEncodeStringsAsAuthIdentity`
- size: `1513`
- prototype: `SECURITY_STATUS __stdcall(PCWSTR pszUserName, PCWSTR pszDomainName, PCWSTR pszPackedCredentialsString, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppAuthIdentity)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180005cc0`
- `0x180015068`
- `0x1800152c0`
- `0x18001592c`
- `0x180017e40`
- `0x180018600`
- `0x18001fe8c`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180017ed9`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180017f46`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180018272`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x1800182f0`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180017ed9`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180017f46`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180018272`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x1800182f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017f11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018058`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001818a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800181d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001821e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800182bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017f11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018058`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001818a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800181d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001821e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800182bd`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiEncodeStringsAsAuthIdentity(
        PCWSTR pszUserName,
        PCWSTR pszDomainName,
        PCWSTR pszPackedCredentialsString,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppAuthIdentity)
{
  const unsigned __int16 *v4; // rsi
  _WORD *v5; // rdi
  PCWSTR v6; // rbx
  const wchar_t **v7; // r12
  unsigned int *v8; // r13
  unsigned int v9; // ebx
  wchar_t *v10; // r15
  __int64 v11; // rdi
  HLOCAL v12; // rax
  const wchar_t *v13; // r15
  wchar_t *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rsi
  PVOID v17; // r14
  unsigned int i; // edi
  unsigned int v19; // r14d
  unsigned int v20; // eax
  _OWORD *v21; // rax
  void *v22; // rcx
  void *v23; // rdx
  __int64 v24; // r8
  int IsEncodedNullUserName; // eax
  __int64 v26; // r14
  __int64 v27; // rax
  unsigned int v28; // ecx
  __int64 v29; // rdi
  __int64 v30; // rax
  unsigned int v31; // ecx
  unsigned int v32; // eax
  int v33; // r8d
  HLOCAL v34; // rax
  HLOCAL v35; // rax
  unsigned int v36; // eax
  __int64 v37; // rdx
  unsigned int v38; // ecx
  HLOCAL v39; // rax
  __int64 v40; // rdi
  __int64 v41; // rbx
  wchar_t *v42; // rax
  wchar_t *v43; // rax
  PVOID v44; // rdx
  _BYTE *v45; // rcx
  __int64 j; // rax
  unsigned int v48; // [rsp+30h] [rbp-40h] BYREF
  PVOID v49; // [rsp+38h] [rbp-38h]
  wchar_t *v50; // [rsp+40h] [rbp-30h]
  PVOID v51; // [rsp+48h] [rbp-28h] BYREF
  void *v52; // [rsp+50h] [rbp-20h] BYREF
  PVOID v53; // [rsp+58h] [rbp-18h]
  PVOID DataBuffer; // [rsp+60h] [rbp-10h]
  PVOID v55; // [rsp+68h] [rbp-8h]
  enum _CRED_MARSHAL_TYPE v56; // [rsp+B0h] [rbp+40h] BYREF
  void *Src; // [rsp+C0h] [rbp+50h]
  struct _SEC_WINNT_AUTH_IDENTITY_EXW **v58; // [rsp+C8h] [rbp+58h]

  v58 = (struct _SEC_WINNT_AUTH_IDENTITY_EXW **)ppAuthIdentity;
  Src = (void *)pszPackedCredentialsString;
  v4 = pszDomainName;
  v5 = pszPackedCredentialsString;
  v6 = pszUserName;
  v56 = 0;
  v7 = 0;
  v52 = 0;
  v8 = 0;
  v51 = 0;
  v48 = 0;
  if ( __PAIR128__((unsigned __int64)pszUserName, (unsigned __int64)pszDomainName) == 0 && !pszPackedCredentialsString )
    goto LABEL_3;
  DataBuffer = 0;
  v49 = 0;
  v53 = 0;
  v50 = 0;
  v55 = 0;
  if ( !pszUserName )
    goto LABEL_106;
  v10 = 0;
  if ( *pszUserName && (!pszDomainName || !*pszDomainName) )
  {
    v10 = wcschr(pszUserName, 0x5Cu);
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v6[v11] );
      if ( (unsigned int)v11 > 0x7FFD )
      {
LABEL_3:
        v9 = -1073741811;
        return SspNtStatusToSecStatus(v9);
      }
      v12 = LocalAlloc(0x40u, (unsigned int)(2 * v11 + 2) + 2LL);
      DataBuffer = v12;
      v13 = (const wchar_t *)v12;
      if ( !v12 )
      {
        v9 = -1073741801;
        return SspNtStatusToSecStatus(v9);
      }
      memcpy_0(v12, v6, 2LL * (unsigned int)v11);
      v14 = wcschr(v13, 0x5Cu);
      v10 = v14;
      if ( v14 )
      {
        v4 = (const unsigned __int16 *)DataBuffer;
        v6 = v14 + 1;
        *v14 = 0;
        if ( v14 == (wchar_t *)-2LL )
          goto LABEL_106;
        v10 = v14 + 1;
      }
      v5 = Src;
    }
  }
  if ( !*v6
    || v4 && *v4
    || !(unsigned int)SspiHelperIsEncodedNullUserName(v6) && !(unsigned int)LocalCredIsMarshaledCredentialW(v6) )
  {
    goto LABEL_106;
  }
  if ( v5 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v5[v15] );
    if ( (unsigned int)v15 > 0x7FFD )
    {
      v9 = -1073741811;
      v16 = 0;
      v17 = 0;
LABEL_108:
      v40 = -1;
      goto LABEL_109;
    }
  }
  else
  {
    LODWORD(v15) = 0;
  }
  for ( i = 0; i < 8; ++i )
  {
    if ( i >= (unsigned int)v15 )
      break;
    if ( aD[i] != *((_WORD *)Src + i) )
      break;
  }
  v19 = v15 + 8;
  if ( i == 8 )
    v19 = v15;
  if ( !(unsigned int)SspiHelperIsEncodedNullUserName(v6) )
  {
    v20 = LocalCredUnmarshalCredentialW(v6, &v56, &v52);
    v7 = (const wchar_t **)v52;
    if ( v20 )
    {
      v9 = -1073741670;
LABEL_38:
      v16 = 0;
LABEL_39:
      v17 = v16;
      goto LABEL_108;
    }
    if ( v56 != UsernameForPackedCredentials )
      goto LABEL_106;
  }
  v56 = BinaryBlobCredential;
  v21 = LocalAlloc(0x40u, 2 * v19 + 2 + 2LL);
  v55 = v21;
  v22 = v21;
  if ( !v21 )
  {
    v9 = -1073741801;
    goto LABEL_38;
  }
  v23 = Src;
  if ( i == 8 )
  {
    v24 = v19;
  }
  else
  {
    v24 = v19 - 8;
    *v21 = *(_OWORD *)aD;
    v22 = v21 + 1;
  }
  memcpy_0(v22, v23, 2 * v24);
  if ( LocalCredUnmarshalCredentialW((const unsigned __int16 *)v55, &v56, &v51) || v56 != BinaryBlobCredential )
  {
    IsEncodedNullUserName = SspiHelperIsEncodedNullUserName(v6);
    v8 = (unsigned int *)v51;
    if ( !IsEncodedNullUserName )
      goto LABEL_48;
LABEL_106:
    v17 = v49;
    v9 = SspiHelperConstructAuthdataExWMarshalledW(
           v6,
           v4,
           (const unsigned __int16 *)Src,
           (const unsigned __int16 *)v49,
           v58,
           &v48);
    goto LABEL_107;
  }
  v8 = (unsigned int *)v51;
  if ( *(_DWORD *)v51 < 0x18u )
    goto LABEL_48;
  v26 = *((_QWORD *)v51 + 1);
  if ( *(_WORD *)v26 < 0x18u )
    goto LABEL_48;
  v27 = *(unsigned int *)(v26 + 8);
  if ( (_DWORD)v27 )
  {
    if ( (unsigned int)v27 > *(_DWORD *)v51 )
      goto LABEL_48;
    v28 = *(unsigned __int16 *)(v26 + 12);
    if ( v28 + (unsigned int)v27 >= (unsigned int)v27 )
    {
      if ( v28 + (unsigned int)v27 > *(_DWORD *)v51 )
        goto LABEL_48;
      if ( !(_WORD)v28 )
      {
        v35 = LocalAlloc(0x40u, 4u);
        v53 = v35;
        if ( !v35 )
          goto LABEL_68;
LABEL_72:
        Src = v35;
        goto LABEL_74;
      }
      if ( v28 < 0x1C )
        goto LABEL_48;
      v29 = v26 + v27;
      if ( *(_WORD *)(v26 + v27) < 0x1Cu || *(_WORD *)(v29 + 2) > (unsigned __int16)v28 )
        goto LABEL_48;
      v30 = *(_QWORD *)(v29 + 4) - SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
      if ( !v30 )
        v30 = *(_QWORD *)(v29 + 12) - *((_QWORD *)&SEC_WINNT_AUTH_DATA_TYPE_PASSWORD + 1);
      if ( v30 )
        goto LABEL_106;
      v31 = *(unsigned __int16 *)(v29 + 2);
      v32 = *(_DWORD *)(v29 + 20);
      if ( v32 > v31 )
        goto LABEL_48;
      v33 = *(unsigned __int16 *)(v29 + 24);
      if ( v33 + v32 >= v32 )
      {
        if ( v33 + v32 > v31 )
          goto LABEL_48;
        v34 = LocalAlloc(0x40u, (unsigned int)(v33 + 4) + 2LL);
        v53 = v34;
        if ( !v34 )
        {
LABEL_68:
          v9 = -1073741801;
          goto LABEL_49;
        }
        memcpy_0(v34, (const void *)(v29 + *(unsigned int *)(v29 + 20)), *(unsigned __int16 *)(v29 + 24));
        v35 = v53;
        goto LABEL_72;
      }
    }
LABEL_70:
    v9 = -1073741675;
    goto LABEL_49;
  }
  Src = 0;
LABEL_74:
  v36 = *(_DWORD *)(v26 + 16);
  if ( !v36 )
  {
    v49 = 0;
    goto LABEL_82;
  }
  if ( v36 > *v8 )
  {
LABEL_48:
    v9 = -1073741811;
LABEL_49:
    v16 = v50;
    goto LABEL_39;
  }
  v37 = *(unsigned __int16 *)(v26 + 20);
  v38 = v36 + 2 * v37;
  if ( v38 < v36 )
    goto LABEL_70;
  if ( v38 > *v8 )
    goto LABEL_48;
  v39 = LocalAlloc(0x40u, 2 * v37 + 4);
  v49 = v39;
  if ( !v39 )
  {
    v9 = -1073741801;
    v17 = 0;
LABEL_107:
    v16 = v50;
    goto LABEL_108;
  }
  memcpy_0(v39, (const void *)(v26 + *(unsigned int *)(v26 + 16)), 2LL * *(unsigned __int16 *)(v26 + 20));
LABEL_82:
  if ( !v7 || !*v7 || !wcschr(*v7, 0x5Cu) )
  {
LABEL_94:
    v4 = (const unsigned __int16 *)&qword_1800319E0;
    if ( (*(_DWORD *)(v26 + 4) & 0x20000) != 0 )
    {
      v6 = 0;
    }
    else if ( v10 )
    {
      v6 = v10;
    }
    else if ( v7 )
    {
      v6 = *v7;
    }
    else
    {
      v6 = (PCWSTR)&qword_1800319E0;
    }
    if ( (*(_DWORD *)(v26 + 4) & 0x40000) != 0 )
    {
      v4 = 0;
    }
    else if ( v50 )
    {
      v4 = v50;
    }
    goto LABEL_106;
  }
  v40 = -1;
  v41 = -1;
  v16 = 0;
  do
    ++v41;
  while ( (*v7)[v41] );
  if ( (unsigned int)v41 <= 0x7FFD )
  {
    v42 = (wchar_t *)LocalAlloc(0x40u, (unsigned int)(2 * v41 + 2) + 2LL);
    v50 = v42;
    v16 = v42;
    if ( !v42 )
    {
      v9 = -1073741801;
      goto LABEL_89;
    }
    memcpy_0(v42, *v7, 2LL * (unsigned int)v41);
    v43 = wcschr(v16, 0x5Cu);
    v10 = v43;
    if ( v43 )
    {
      *v43 = 0;
      v10 = v43 + 1;
    }
    goto LABEL_94;
  }
  v9 = -1073741811;
LABEL_89:
  v17 = v49;
LABEL_109:
  if ( DataBuffer )
    SspiLocalFree(DataBuffer);
  if ( v7 )
    SspiLocalFree(v7);
  if ( v8 )
    SspiLocalFree(v8);
  v44 = v53;
  if ( v53 )
  {
    do
      ++v40;
    while ( *((_WORD *)v53 + v40) );
    v45 = v53;
    for ( j = 2LL * (unsigned int)v40; j; --j )
      *v45++ = 0;
    SspiLocalFree(v44);
  }
  if ( v17 )
    SspiLocalFree(v17);
  if ( v16 )
    SspiLocalFree(v16);
  if ( v55 )
    SspiLocalFree(v55);
  return SspNtStatusToSecStatus(v9);
}

```

## disassembly

```asm
0x180017e40  mov     [rsp-38h+arg_8], rbx
0x180017e45  mov     [rsp-38h+arg_18], r9
0x180017e4a  mov     [rsp-38h+Src], r8
0x180017e4f  push    rbp
0x180017e50  push    rsi
0x180017e51  push    rdi
0x180017e52  push    r12
0x180017e54  push    r13
0x180017e56  push    r14
0x180017e58  push    r15
0x180017e5a  mov     rbp, rsp
0x180017e5d  sub     rsp, 70h
0x180017e61  mov     rsi, rdx
0x180017e64  mov     rdi, r8
0x180017e67  xor     edx, edx
0x180017e69  mov     rbx, rcx
0x180017e6c  mov     [rbp+arg_0], edx
0x180017e6f  mov     r12d, edx
0x180017e72  mov     [rbp+var_20], rdx
0x180017e76  mov     r13d, edx
0x180017e79  mov     [rbp+var_28], rdx
0x180017e7d  mov     [rbp+var_40], edx
0x180017e80  test    rcx, rcx
0x180017e83  jnz     short loc_180017E99
0x180017e85  test    rsi, rsi
0x180017e88  jnz     short loc_180017E99
0x180017e8a  test    r8, r8
0x180017e8d  jnz     short loc_180017E99
0x180017e8f  mov     ebx, 0C000000Dh
0x180017e94  jmp     loc_18001840B
0x180017e99  or      r14, 0FFFFFFFFFFFFFFFFh
0x180017e9d  mov     [rbp+DataBuffer], rdx
0x180017ea1  mov     [rbp+var_38], rdx
0x180017ea5  mov     [rbp+var_18], rdx
0x180017ea9  mov     [rbp+var_30], rdx
0x180017ead  mov     [rbp+var_8], rdx
0x180017eb1  test    rbx, rbx
0x180017eb4  jz      loc_18001834F
0x180017eba  mov     r15, rdx
0x180017ebd  cmp     [rcx], dx
0x180017ec0  jz      loc_180017F71
0x180017ec6  test    rsi, rsi
0x180017ec9  jz      short loc_180017ED4
0x180017ecb  cmp     [rsi], dx
0x180017ece  jnz     loc_180017F71
0x180017ed4  mov     edx, 5Ch ; '\'; Ch
0x180017ed9  call    cs:__imp_wcschr
0x180017edf  xor     edx, edx
0x180017ee1  mov     r15, rax
0x180017ee4  test    rax, rax
0x180017ee7  jz      loc_180017F71
0x180017eed  mov     rdi, r14
0x180017ef0  inc     rdi
0x180017ef3  cmp     [rbx+rdi*2], dx
0x180017ef7  jnz     short loc_180017EF0
0x180017ef9  cmp     edi, 7FFDh
0x180017eff  ja      short loc_180017E8F
0x180017f01  lea     edx, ds:2[rdi*2]
0x180017f08  mov     ecx, 40h ; '@'; uFlags
0x180017f0d  add     rdx, 2; uBytes
0x180017f11  call    cs:__imp_LocalAlloc
0x180017f17  mov     [rbp+DataBuffer], rax
0x180017f1b  mov     r15, rax
0x180017f1e  test    rax, rax
0x180017f21  jnz     short loc_180017F2D
0x180017f23  mov     ebx, 0C0000017h
0x180017f28  jmp     loc_18001840B
0x180017f2d  mov     r8d, edi
0x180017f30  mov     rdx, rbx; Src
0x180017f33  add     r8, r8; Size
0x180017f36  mov     rcx, r15; void *
0x180017f39  call    memcpy_0
0x180017f3e  mov     edx, 5Ch ; '\'; Ch
0x180017f43  mov     rcx, r15; Str
0x180017f46  call    cs:__imp_wcschr
0x180017f4c  xor     edx, edx
0x180017f4e  mov     r15, rax
0x180017f51  test    rax, rax
0x180017f54  jz      short loc_180017F6D
0x180017f56  mov     rsi, [rbp+DataBuffer]
0x180017f5a  lea     rbx, [rax+2]
0x180017f5e  mov     [rax], dx
0x180017f61  test    rbx, rbx
0x180017f64  jz      loc_18001834F
0x180017f6a  mov     r15, rbx
0x180017f6d  mov     rdi, [rbp+Src]
0x180017f71  cmp     [rbx], dx
0x180017f74  jz      loc_18001834F
0x180017f7a  test    rsi, rsi
0x180017f7d  jz      short loc_180017F88
0x180017f7f  cmp     [rsi], dx
0x180017f82  jnz     loc_18001834F
0x180017f88  mov     rcx, rbx; unsigned __int16 *
0x180017f8b  call    ?SspiHelperIsEncodedNullUserName@@YAHPEBG@Z; SspiHelperIsEncodedNullUserName(ushort const *)
0x180017f90  test    eax, eax
0x180017f92  jnz     short loc_180017FA4
0x180017f94  mov     rcx, rbx; unsigned __int16 *
0x180017f97  call    ?LocalCredIsMarshaledCredentialW@@YAHPEBG@Z; LocalCredIsMarshaledCredentialW(ushort const *)
0x180017f9c  test    eax, eax
0x180017f9e  jz      loc_18001834F
0x180017fa4  xor     eax, eax
0x180017fa6  test    rdi, rdi
0x180017fa9  jz      short loc_180017FCF
0x180017fab  mov     rdx, r14
0x180017fae  inc     rdx
0x180017fb1  cmp     [rdi+rdx*2], ax
0x180017fb5  jnz     short loc_180017FAE
0x180017fb7  cmp     edx, 7FFDh
0x180017fbd  jbe     short loc_180017FD1
0x180017fbf  mov     ebx, 0C000000Dh
0x180017fc4  mov     rsi, rax
0x180017fc7  mov     r14, rax
0x180017fca  jmp     loc_18001837D
0x180017fcf  mov     edx, eax
0x180017fd1  mov     r8, [rbp+Src]
0x180017fd5  mov     edi, eax
0x180017fd7  cmp     edi, edx
0x180017fd9  jnb     short loc_180017FF7
0x180017fdb  mov     ecx, edi
0x180017fdd  lea     r9, aD; "@@D\a\b"
0x180017fe4  movzx   eax, word ptr [r8+rcx*2]
0x180017fe9  cmp     [r9+rcx*2], ax
0x180017fee  jnz     short loc_180017FF7
0x180017ff0  inc     edi
0x180017ff2  cmp     edi, 8
0x180017ff5  jb      short loc_180017FD7
0x180017ff7  lea     r14d, [rdx+8]
0x180017ffb  cmp     edi, 8
0x180017ffe  mov     rcx, rbx; unsigned __int16 *
0x180018001  cmovz   r14d, edx
0x180018005  call    ?SspiHelperIsEncodedNullUserName@@YAHPEBG@Z; SspiHelperIsEncodedNullUserName(ushort const *)
0x18001800a  test    eax, eax
0x18001800c  jnz     short loc_180018040
0x18001800e  lea     r8, [rbp+var_20]; void **
0x180018012  mov     rcx, rbx; unsigned __int16 *
0x180018015  lea     rdx, [rbp+arg_0]; enum _CRED_MARSHAL_TYPE *
0x180018019  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x18001801e  mov     r12, [rbp+var_20]
0x180018022  test    eax, eax
0x180018024  jz      short loc_180018036
0x180018026  mov     ebx, 0C000009Ah
0x18001802b  mov     rsi, r13
0x18001802e  mov     r14, rsi
0x180018031  jmp     loc_18001837D
0x180018036  cmp     [rbp+arg_0], 4
0x18001803a  jnz     loc_18001834F
0x180018040  lea     edx, ds:2[r14*2]
0x180018048  mov     [rbp+arg_0], 3
0x18001804f  add     rdx, 2; uBytes
0x180018053  mov     ecx, 40h ; '@'; uFlags
0x180018058  call    cs:__imp_LocalAlloc
0x18001805e  mov     [rbp+var_8], rax
0x180018062  mov     rcx, rax; void *
0x180018065  test    rax, rax
0x180018068  jnz     short loc_180018071
0x18001806a  mov     ebx, 0C0000017h
0x18001806f  jmp     short loc_18001802B
0x180018071  mov     rdx, [rbp+Src]; Src
0x180018075  cmp     edi, 8
0x180018078  jz      short loc_18001808F
0x18001807a  movaps  xmm0, xmmword ptr cs:aD; "@@D\a\b"
0x180018081  lea     r8d, [r14-8]
0x180018085  movdqu  xmmword ptr [rax], xmm0
0x180018089  add     rcx, 10h
0x18001808d  jmp     short loc_180018092
0x18001808f  mov     r8d, r14d
0x180018092  add     r8, r8; Size
0x180018095  call    memcpy_0
0x18001809a  mov     rcx, [rbp+var_8]; unsigned __int16 *
0x18001809e  lea     r8, [rbp+var_28]; void **
0x1800180a2  lea     rdx, [rbp+arg_0]; enum _CRED_MARSHAL_TYPE *
0x1800180a6  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x1800180ab  xor     edi, edi
0x1800180ad  test    eax, eax
0x1800180af  jz      short loc_1800180D3
0x1800180b1  mov     rcx, rbx; unsigned __int16 *
0x1800180b4  call    ?SspiHelperIsEncodedNullUserName@@YAHPEBG@Z; SspiHelperIsEncodedNullUserName(ushort const *)
0x1800180b9  mov     r13, [rbp+var_28]
0x1800180bd  test    eax, eax
0x1800180bf  jnz     loc_18001834F
0x1800180c5  mov     ebx, 0C000000Dh
0x1800180ca  mov     rsi, [rbp+var_30]
0x1800180ce  jmp     loc_18001802E
0x1800180d3  cmp     [rbp+arg_0], 3
0x1800180d7  jnz     short loc_1800180B1
0x1800180d9  mov     r13, [rbp+var_28]
0x1800180dd  mov     eax, 18h
0x1800180e2  cmp     [r13+0], eax
0x1800180e6  jb      short loc_1800180C5
0x1800180e8  mov     r14, [r13+8]
0x1800180ec  cmp     [r14], ax
0x1800180f0  jb      short loc_1800180C5
0x1800180f2  mov     eax, [r14+8]
0x1800180f6  test    eax, eax
0x1800180f8  jz      loc_1800181E5
0x1800180fe  cmp     eax, [r13+0]
0x180018102  ja      short loc_1800180C5
0x180018104  movzx   ecx, word ptr [r14+0Ch]
0x180018109  lea     edx, [rcx+rax]
0x18001810c  cmp     edx, eax
0x18001810e  jb      loc_1800181BE
0x180018114  cmp     edx, [r13+0]
0x180018118  ja      short loc_1800180C5
0x18001811a  test    cx, cx
0x18001811d  jz      loc_1800181C8
0x180018123  cmp     ecx, 1Ch
0x180018126  jb      short loc_1800180C5
0x180018128  lea     rdi, [r14+rax]
0x18001812c  cmp     word ptr [rdi], 1Ch
0x180018130  jb      short loc_1800180C5
0x180018132  cmp     [rdi+2], cx
0x180018136  ja      short loc_1800180C5
0x180018138  mov     rax, [rdi+4]
0x18001813c  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD
0x180018143  jnz     short loc_180018150
0x180018145  mov     rax, [rdi+0Ch]
0x180018149  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD+8
0x180018150  test    rax, rax
0x180018153  jnz     loc_18001834F
0x180018159  movzx   ecx, word ptr [rdi+2]
0x18001815d  mov     eax, [rdi+14h]
0x180018160  cmp     eax, ecx
0x180018162  ja      loc_1800180C5
0x180018168  movzx   r8d, word ptr [rdi+18h]
0x18001816d  lea     edx, [r8+rax]
0x180018171  cmp     edx, eax
0x180018173  jb      short loc_1800181BE
0x180018175  cmp     edx, ecx
0x180018177  ja      loc_1800180C5
0x18001817d  lea     edx, [r8+4]
0x180018181  mov     ecx, 40h ; '@'; uFlags
0x180018186  add     rdx, 2; uBytes
0x18001818a  call    cs:__imp_LocalAlloc
0x180018190  mov     [rbp+var_18], rax
0x180018194  test    rax, rax
0x180018197  jnz     short loc_1800181A3
0x180018199  mov     ebx, 0C0000017h
0x18001819e  jmp     loc_1800180CA
0x1800181a3  mov     edx, [rdi+14h]
0x1800181a6  mov     rcx, rax; void *
0x1800181a9  movzx   r8d, word ptr [rdi+18h]; Size
0x1800181ae  add     rdx, rdi; Src
0x1800181b1  call    memcpy_0
0x1800181b6  mov     rax, [rbp+var_18]
0x1800181ba  xor     edi, edi
0x1800181bc  jmp     short loc_1800181DF
0x1800181be  mov     ebx, 0C0000095h
0x1800181c3  jmp     loc_1800180CA
0x1800181c8  mov     edx, 4; uBytes
0x1800181cd  lea     ecx, [rdx+3Ch]; uFlags
0x1800181d0  call    cs:__imp_LocalAlloc
0x1800181d6  mov     [rbp+var_18], rax
0x1800181da  test    rax, rax
0x1800181dd  jz      short loc_180018199
0x1800181df  mov     [rbp+Src], rax
0x1800181e3  jmp     short loc_1800181E9
0x1800181e5  mov     [rbp+Src], rdi
0x1800181e9  mov     eax, [r14+10h]
0x1800181ed  test    eax, eax
0x1800181ef  jz      short loc_180018253
0x1800181f1  cmp     eax, [r13+0]
0x1800181f5  ja      loc_1800180C5
0x1800181fb  movzx   edx, word ptr [r14+14h]
0x180018200  lea     ecx, [rax+rdx*2]
0x180018203  cmp     ecx, eax
0x180018205  jb      short loc_1800181BE
0x180018207  cmp     ecx, [r13+0]
0x18001820b  ja      loc_1800180C5
0x180018211  lea     rdx, ds:4[rdx*2]; uBytes
0x180018219  mov     ecx, 40h ; '@'; uFlags
0x18001821e  call    cs:__imp_LocalAlloc
0x180018224  mov     [rbp+var_38], rax
0x180018228  test    rax, rax
0x18001822b  jnz     short loc_18001823A
0x18001822d  mov     ebx, 0C0000017h
0x180018232  mov     r14, rax
0x180018235  jmp     loc_180018379
0x18001823a  movzx   r8d, word ptr [r14+14h]
0x18001823f  mov     rcx, rax; void *
0x180018242  mov     edx, [r14+10h]
0x180018246  add     r8, r8; Size
0x180018249  add     rdx, r14; Src
0x18001824c  call    memcpy_0
0x180018251  jmp     short loc_180018257
0x180018253  mov     [rbp+var_38], rdi
0x180018257  test    r12, r12
0x18001825a  jz      loc_180018307
0x180018260  mov     rcx, [r12]; Str
0x180018264  test    rcx, rcx
0x180018267  jz      loc_180018307
0x18001826d  mov     edx, 5Ch ; '\'; Ch
0x180018272  call    cs:__imp_wcschr
0x180018278  test    rax, rax
0x18001827b  jz      loc_180018307
0x180018281  mov     rax, [r12]
0x180018285  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018289  mov     rbx, rdi
0x18001828c  xor     esi, esi
0x18001828e  inc     rbx
0x180018291  cmp     [rax+rbx*2], si
  ... truncated ...
```
