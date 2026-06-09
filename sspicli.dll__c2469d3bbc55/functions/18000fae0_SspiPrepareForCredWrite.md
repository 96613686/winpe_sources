# SspiPrepareForCredWrite

- ea: `0x18000fae0`
- end: `0x18000ffa8`
- name: `SspiPrepareForCredWrite`
- size: `1224`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity, PCWSTR pszTargetName, PULONG pCredmanCredentialType, PCWSTR *ppszCredmanTargetName, PCWSTR *ppszCredmanUserName, PUCHAR *ppCredentialBlob, PULONG pCredentialBlobSize)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000fa60`

## callees

- `0x180005cc0`
- `0x18000fae0`
- `0x18000ffb0`
- `0x1800113a0`
- `0x180015068`
- `0x180017970`
- `0x180018600`
- `0x18001fe8c`
- `0x180020374`
- `0x180022047`
- `0x18002205f`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fc17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fee6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fc17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fee6`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiPrepareForCredWrite(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity,
        PCWSTR pszTargetName,
        PULONG pCredmanCredentialType,
        PCWSTR *ppszCredmanTargetName,
        PCWSTR *ppszCredmanUserName,
        PUCHAR *ppCredentialBlob,
        PULONG pCredentialBlobSize)
{
  PVOID *v7; // rsi
  __int64 v8; // r13
  __int64 v10; // r12
  PVOID *v11; // r14
  unsigned __int16 *v12; // r15
  SECURITY_STATUS TargetHostName; // eax
  SECURITY_STATUS v14; // edi
  __int64 v15; // rsi
  __int64 v16; // rbx
  WCHAR *v17; // r14
  PVOID v18; // rbx
  size_t v20; // rbx
  __int64 v21; // rbx
  WCHAR *v22; // rcx
  int IsMarshaledCredentialW; // eax
  PULONG v24; // rsi
  int v25; // eax
  int v26; // eax
  WCHAR *v27; // rax
  _WORD *v28; // rcx
  __int64 v29; // rax
  unsigned int *v30; // [rsp+28h] [rbp-71h]
  PVOID v31; // [rsp+48h] [rbp-51h] BYREF
  PCWSTR ppszUserName; // [rsp+50h] [rbp-49h] BYREF
  PCWSTR ppszDomainName; // [rsp+58h] [rbp-41h] BYREF
  PVOID DataBuffer; // [rsp+60h] [rbp-39h] BYREF
  _CRED_MARSHAL_TYPE v35; // [rsp+68h] [rbp-31h] BYREF
  unsigned int Size[3]; // [rsp+6Ch] [rbp-2Dh] BYREF
  PVOID v37; // [rsp+78h] [rbp-21h] BYREF
  PVOID v38; // [rsp+80h] [rbp-19h] BYREF
  PVOID v39; // [rsp+88h] [rbp-11h] BYREF

  v7 = (PVOID *)ppszCredmanUserName;
  LODWORD(v8) = 0;
  v35 = 0;
  v10 = -1;
  v37 = 0;
  *(_QWORD *)&Size[1] = 0;
  v11 = (PVOID *)ppszCredmanTargetName;
  v31 = 0;
  *ppCredentialBlob = 0;
  v12 = 0;
  Size[0] = 0;
  ppszUserName = 0;
  ppszDomainName = 0;
  *pCredentialBlobSize = 0;
  *ppszCredmanUserName = 0;
  *ppszCredmanTargetName = 0;
  *pCredmanCredentialType = 0;
  DataBuffer = 0;
  v38 = 0;
  v39 = 0;
  if ( pszTargetName )
  {
    TargetHostName = SspiGetTargetHostName(pszTargetName, (PWSTR *)&Size[1]);
    v12 = *(unsigned __int16 **)&Size[1];
    v14 = TargetHostName;
    if ( TargetHostName < 0 )
    {
LABEL_21:
      v18 = v31;
      goto LABEL_22;
    }
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(*(_QWORD *)&Size[1] + 2 * v8) );
    if ( (unsigned int)v8 > 0x7FFD )
    {
      v14 = -1073741811;
      goto LABEL_21;
    }
  }
  v14 = SspiEncodeAuthIdentityAsStrings(AuthIdentity, &ppszUserName, &ppszDomainName, 0);
  if ( v14 < 0 )
    goto LABEL_21;
  LODWORD(v15) = 0;
  if ( ppszUserName )
  {
    v15 = -1;
    do
      ++v15;
    while ( ppszUserName[v15] );
    if ( (unsigned int)v15 > 0x7FFD )
      goto LABEL_12;
  }
  LODWORD(v16) = 0;
  if ( ppszDomainName )
  {
    v16 = -1;
    do
      ++v16;
    while ( ppszDomainName[v16] );
    if ( (unsigned int)v16 > 0x7FFD )
    {
LABEL_12:
      v14 = -1073741811;
LABEL_20:
      v7 = (PVOID *)ppszCredmanUserName;
      goto LABEL_21;
    }
  }
  v17 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(2 * (v16 + v15) + 4) + 2LL);
  *ppszCredmanUserName = v17;
  if ( !v17 )
  {
    v14 = -1073741801;
LABEL_19:
    v11 = (PVOID *)ppszCredmanTargetName;
    goto LABEL_20;
  }
  if ( (_DWORD)v16 )
  {
    v20 = 2LL * (unsigned int)v16;
    memcpy_0(v17, ppszDomainName, v20);
    v17[v20 / 2] = 92;
    v17 = (WCHAR *)((char *)v17 + v20 + 2);
  }
  memcpy_0(v17, ppszUserName, 2LL * (unsigned int)v15);
  v7 = (PVOID *)ppszCredmanUserName;
  v21 = -1;
  do
    ++v21;
  while ( (*ppszCredmanUserName)[v21] );
  if ( *(_DWORD *)AuthIdentity == 513 )
  {
    v11 = (PVOID *)ppszCredmanTargetName;
    v7 = (PVOID *)ppszCredmanUserName;
    v14 = SspiHelperProcessPackedCredentials(
            (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)((char *)AuthIdentity + *((unsigned int *)AuthIdentity + 7)),
            v12,
            ppszCredmanUserName,
            ppszCredmanTargetName,
            pCredmanCredentialType,
            ppCredentialBlob,
            pCredentialBlobSize);
    goto LABEL_21;
  }
  v22 = (WCHAR *)ppszUserName;
  if ( ppszUserName
    && (IsMarshaledCredentialW = LocalCredIsMarshaledCredentialW(ppszUserName),
        v22 = (WCHAR *)ppszUserName,
        IsMarshaledCredentialW) )
  {
    if ( LocalCredUnmarshalCredentialW(ppszUserName, &v35, &v37) )
    {
      v11 = (PVOID *)ppszCredmanTargetName;
      v14 = -1073741670;
      goto LABEL_21;
    }
    v24 = pCredmanCredentialType;
    v22 = (WCHAR *)ppszUserName;
    if ( v35 == CertCredential )
      *pCredmanCredentialType = 3;
  }
  else
  {
    v24 = pCredmanCredentialType;
  }
  if ( *v24 )
  {
LABEL_72:
    v26 = v8;
    if ( !pszTargetName )
      v26 = v21;
    v27 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(2 * v26 + 2) + 2LL);
    v11 = (PVOID *)ppszCredmanTargetName;
    *ppszCredmanTargetName = v27;
    if ( v27 )
    {
      if ( pszTargetName )
      {
        memcpy_0(v27, v12, 2LL * (unsigned int)v8);
        v7 = (PVOID *)ppszCredmanUserName;
      }
      else
      {
        v7 = (PVOID *)ppszCredmanUserName;
        memcpy_0(v27, *ppszCredmanUserName, 2LL * (unsigned int)v21);
      }
      v28 = DataBuffer;
      if ( !DataBuffer )
      {
        v18 = v31;
        goto LABEL_25;
      }
      *ppCredentialBlob = (PUCHAR)DataBuffer;
      v29 = -1;
      do
        ++v29;
      while ( v28[v29] );
      DataBuffer = 0;
      *pCredentialBlobSize = 2 * v29;
      goto LABEL_21;
    }
    v14 = -1073741801;
    goto LABEL_20;
  }
  if ( v22 )
  {
    SspiLocalFree(v22);
    ppszUserName = 0;
  }
  if ( ppszDomainName )
  {
    SspiLocalFree((PVOID)ppszDomainName);
    ppszDomainName = 0;
  }
  v14 = SspiEncodeAuthIdentityAsStrings(AuthIdentity, &ppszUserName, &ppszDomainName, (PCWSTR *)&DataBuffer);
  if ( v14 < 0 )
    goto LABEL_19;
  if ( ppszDomainName && *ppszDomainName )
  {
LABEL_71:
    *v24 = 2;
    goto LABEL_72;
  }
  v25 = SspiHelperProcessEncodedPackedCredentials(
          ppszUserName,
          (const unsigned __int16 *)DataBuffer,
          (const unsigned __int16 **)&v38,
          (const unsigned __int16 **)&v39,
          (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **)&v31,
          Size);
  v14 = v25;
  if ( v25 < 0 )
  {
    if ( v25 != -1073741275 )
      goto LABEL_19;
    v14 = 0;
    goto LABEL_71;
  }
  v11 = (PVOID *)ppszCredmanTargetName;
  v18 = v31;
  v30 = v24;
  v7 = (PVOID *)ppszCredmanUserName;
  v14 = SspiHelperProcessPackedCredentials(
          (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)v31,
          v12,
          ppszCredmanUserName,
          ppszCredmanTargetName,
          v30,
          ppCredentialBlob,
          pCredentialBlobSize);
LABEL_22:
  if ( DataBuffer )
  {
    do
      ++v10;
    while ( *((_WORD *)DataBuffer + v10) );
    memset_0(DataBuffer, 0, 2LL * (unsigned int)v10);
    SspiLocalFree(DataBuffer);
  }
LABEL_25:
  if ( ppszUserName )
    SspiLocalFree((PVOID)ppszUserName);
  if ( ppszDomainName )
    SspiLocalFree((PVOID)ppszDomainName);
  if ( v37 )
    SspiLocalFree(v37);
  if ( v12 )
    SspiLocalFree(v12);
  if ( v38 )
    SspiLocalFree(v38);
  if ( v39 )
    SspiLocalFree(v39);
  if ( v18 )
  {
    memset_0(v18, 0, Size[0]);
    SspiLocalFree(v18);
  }
  if ( v14 < 0 )
  {
    if ( *ppCredentialBlob )
    {
      memset_0(*ppCredentialBlob, 0, *pCredentialBlobSize);
      *ppCredentialBlob = 0;
    }
    *pCredentialBlobSize = 0;
    if ( *v11 )
    {
      SspiLocalFree(*v11);
      *v11 = 0;
    }
    if ( *v7 )
    {
      SspiLocalFree(*v7);
      *v7 = 0;
    }
  }
  return SspNtStatusToSecStatus((unsigned int)v14);
}

```

## disassembly

```asm
0x18000fae0  mov     rax, rsp
0x18000fae3  mov     [rax+20h], r9
0x18000fae7  mov     [rax+18h], r8
0x18000faeb  mov     [rax+10h], rdx
0x18000faef  mov     [rax+8], rcx
0x18000faf3  push    rbp
0x18000faf4  push    rbx
0x18000faf5  push    rsi
0x18000faf6  push    rdi
0x18000faf7  push    r12
0x18000faf9  push    r13
0x18000fafb  push    r14
0x18000fafd  push    r15
0x18000faff  lea     rbp, [rax-47h]
0x18000fb03  sub     rsp, 98h
0x18000fb0a  mov     rsi, [rbp+3Fh+ppszCredmanUserName]
0x18000fb0e  xor     r13d, r13d
0x18000fb11  mov     rbx, rcx
0x18000fb14  mov     [rbp+3Fh+var_70], r13d
0x18000fb18  mov     rcx, [rbp+3Fh+ppCredentialBlob]
0x18000fb1c  mov     rax, r8
0x18000fb1f  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000fb23  mov     [rbp+3Fh+var_60], r13
0x18000fb27  mov     qword ptr [rbp+3Fh+Size+4], r13
0x18000fb2b  mov     r14, r9
0x18000fb2e  mov     [rbp+3Fh+var_90], r13
0x18000fb32  mov     r8, rdx
0x18000fb35  mov     [rcx], r13
0x18000fb38  mov     r15d, r13d
0x18000fb3b  mov     rcx, [rbp+3Fh+pCredentialBlobSize]
0x18000fb3f  mov     dword ptr [rbp+3Fh+Size], r13d
0x18000fb43  mov     [rbp+3Fh+ppszUserName], r13
0x18000fb47  mov     [rbp+3Fh+ppszDomainName], r13
0x18000fb4b  mov     [rcx], r13d
0x18000fb4e  mov     [rsi], r13
0x18000fb51  mov     [r9], r13
0x18000fb54  mov     [rax], r13d
0x18000fb57  mov     [rbp+3Fh+DataBuffer], r13
0x18000fb5b  mov     [rbp+3Fh+var_58], r13
0x18000fb5f  mov     [rbp+3Fh+var_50], r13
0x18000fb63  test    rdx, rdx
0x18000fb66  jz      short loc_18000FBA4
0x18000fb68  lea     rdx, [rbp+3Fh+Size+4]; pszHostName
0x18000fb6c  mov     rcx, r8; pszTargetName
0x18000fb6f  call    SspiGetTargetHostName
0x18000fb74  mov     r15, qword ptr [rbp+3Fh+Size+4]
0x18000fb78  mov     edi, eax
0x18000fb7a  test    eax, eax
0x18000fb7c  js      loc_18000FC40
0x18000fb82  mov     r13, r12
0x18000fb85  xor     eax, eax
0x18000fb87  inc     r13
0x18000fb8a  cmp     [r15+r13*2], ax
0x18000fb8f  jnz     short loc_18000FB87
0x18000fb91  cmp     r13d, 7FFDh
0x18000fb98  jbe     short loc_18000FBA4
0x18000fb9a  mov     edi, 0C000000Dh
0x18000fb9f  jmp     loc_18000FC3D
0x18000fba4  xor     r9d, r9d; ppszPackedCredentialsString
0x18000fba7  lea     r8, [rbp+3Fh+ppszDomainName]; ppszDomainName
0x18000fbab  lea     rdx, [rbp+3Fh+ppszUserName]; ppszUserName
0x18000fbaf  mov     rcx, rbx; pAuthIdentity
0x18000fbb2  call    SspiEncodeAuthIdentityAsStrings
0x18000fbb7  mov     edi, eax
0x18000fbb9  xor     eax, eax
0x18000fbbb  test    edi, edi
0x18000fbbd  js      short loc_18000FC3D
0x18000fbbf  mov     rcx, [rbp+3Fh+ppszUserName]
0x18000fbc3  mov     esi, eax
0x18000fbc5  test    rcx, rcx
0x18000fbc8  jz      short loc_18000FBE5
0x18000fbca  mov     rsi, r12
0x18000fbcd  inc     rsi
0x18000fbd0  cmp     [rcx+rsi*2], ax
0x18000fbd4  jnz     short loc_18000FBCD
0x18000fbd6  cmp     esi, 7FFDh
0x18000fbdc  jbe     short loc_18000FBE5
0x18000fbde  mov     edi, 0C000000Dh
0x18000fbe3  jmp     short loc_18000FC39
0x18000fbe5  mov     rcx, [rbp+3Fh+ppszDomainName]
0x18000fbe9  mov     ebx, eax
0x18000fbeb  test    rcx, rcx
0x18000fbee  jz      short loc_18000FC04
0x18000fbf0  mov     rbx, r12
0x18000fbf3  inc     rbx
0x18000fbf6  cmp     [rcx+rbx*2], ax
0x18000fbfa  jnz     short loc_18000FBF3
0x18000fbfc  cmp     ebx, 7FFDh
0x18000fc02  ja      short loc_18000FBDE
0x18000fc04  lea     eax, [rbx+rsi]
0x18000fc07  mov     ecx, 40h ; '@'; uFlags
0x18000fc0c  lea     edx, ds:4[rax*2]
0x18000fc13  add     rdx, 2; uBytes
0x18000fc17  call    cs:__imp_LocalAlloc
0x18000fc1d  mov     r14, rax
0x18000fc20  mov     rax, [rbp+3Fh+ppszCredmanUserName]
0x18000fc24  mov     [rax], r14
0x18000fc27  test    r14, r14
0x18000fc2a  jnz     loc_18000FD42
0x18000fc30  mov     edi, 0C0000017h
0x18000fc35  mov     r14, [rbp+3Fh+arg_18]
0x18000fc39  mov     rsi, [rbp+3Fh+ppszCredmanUserName]
0x18000fc3d  xor     r13d, r13d
0x18000fc40  mov     rbx, [rbp+3Fh+var_90]
0x18000fc44  mov     rax, [rbp+3Fh+DataBuffer]
0x18000fc48  test    rax, rax
0x18000fc4b  jz      short loc_18000FC71
0x18000fc4d  inc     r12
0x18000fc50  cmp     [rax+r12*2], r13w
0x18000fc55  jnz     short loc_18000FC4D
0x18000fc57  mov     rcx, [rbp+3Fh+DataBuffer]; void *
0x18000fc5b  xor     edx, edx; Val
0x18000fc5d  mov     r8d, r12d
0x18000fc60  add     r8, r8; Size
0x18000fc63  call    memset_0
0x18000fc68  mov     rcx, [rbp+3Fh+DataBuffer]; DataBuffer
0x18000fc6c  call    SspiLocalFree
0x18000fc71  mov     rcx, [rbp+3Fh+ppszUserName]; DataBuffer
0x18000fc75  test    rcx, rcx
0x18000fc78  jz      short loc_18000FC7F
0x18000fc7a  call    SspiLocalFree
0x18000fc7f  mov     rcx, [rbp+3Fh+ppszDomainName]; DataBuffer
0x18000fc83  test    rcx, rcx
0x18000fc86  jz      short loc_18000FC8D
0x18000fc88  call    SspiLocalFree
0x18000fc8d  mov     rcx, [rbp+3Fh+var_60]; DataBuffer
0x18000fc91  test    rcx, rcx
0x18000fc94  jz      short loc_18000FC9B
0x18000fc96  call    SspiLocalFree
0x18000fc9b  test    r15, r15
0x18000fc9e  jz      short loc_18000FCA8
0x18000fca0  mov     rcx, r15; DataBuffer
0x18000fca3  call    SspiLocalFree
0x18000fca8  mov     rcx, [rbp+3Fh+var_58]; DataBuffer
0x18000fcac  test    rcx, rcx
0x18000fcaf  jz      short loc_18000FCB6
0x18000fcb1  call    SspiLocalFree
0x18000fcb6  mov     rcx, [rbp+3Fh+var_50]; DataBuffer
0x18000fcba  test    rcx, rcx
0x18000fcbd  jz      short loc_18000FCC4
0x18000fcbf  call    SspiLocalFree
0x18000fcc4  test    rbx, rbx
0x18000fcc7  jz      short loc_18000FCDF
0x18000fcc9  mov     r8d, dword ptr [rbp+3Fh+Size]; Size
0x18000fccd  xor     edx, edx; Val
0x18000fccf  mov     rcx, rbx; void *
0x18000fcd2  call    memset_0
0x18000fcd7  mov     rcx, rbx; DataBuffer
0x18000fcda  call    SspiLocalFree
0x18000fcdf  test    edi, edi
0x18000fce1  jns     short loc_18000FD27
0x18000fce3  mov     rbx, [rbp+3Fh+ppCredentialBlob]
0x18000fce7  mov     rcx, [rbx]; void *
0x18000fcea  test    rcx, rcx
0x18000fced  jz      short loc_18000FD00
0x18000fcef  mov     rax, [rbp+3Fh+pCredentialBlobSize]
0x18000fcf3  xor     edx, edx; Val
0x18000fcf5  mov     r8d, [rax]; Size
0x18000fcf8  call    memset_0
0x18000fcfd  mov     [rbx], r13
0x18000fd00  mov     rax, [rbp+3Fh+pCredentialBlobSize]
0x18000fd04  mov     [rax], r13d
0x18000fd07  mov     rcx, [r14]; DataBuffer
0x18000fd0a  test    rcx, rcx
0x18000fd0d  jz      short loc_18000FD17
0x18000fd0f  call    SspiLocalFree
0x18000fd14  mov     [r14], r13
0x18000fd17  mov     rcx, [rsi]; DataBuffer
0x18000fd1a  test    rcx, rcx
0x18000fd1d  jz      short loc_18000FD27
0x18000fd1f  call    SspiLocalFree
0x18000fd24  mov     [rsi], r13
0x18000fd27  mov     ecx, edi
0x18000fd29  call    SspNtStatusToSecStatus
0x18000fd2e  add     rsp, 98h
0x18000fd35  pop     r15
0x18000fd37  pop     r14
0x18000fd39  pop     r13
0x18000fd3b  pop     r12
0x18000fd3d  pop     rdi
0x18000fd3e  pop     rsi
0x18000fd3f  pop     rbx
0x18000fd40  pop     rbp
0x18000fd41  retn
0x18000fd42  test    ebx, ebx
0x18000fd44  jz      short loc_18000FD68
0x18000fd46  mov     rdx, [rbp+3Fh+ppszDomainName]; Src
0x18000fd4a  mov     rcx, r14; void *
0x18000fd4d  mov     eax, ebx
0x18000fd4f  lea     rbx, [rax+rax]
0x18000fd53  mov     r8, rbx; Size
0x18000fd56  call    memcpy_0
0x18000fd5b  lea     rax, [rbx+r14]
0x18000fd5f  mov     word ptr [rax], 5Ch ; '\'
0x18000fd64  lea     r14, [rax+2]
0x18000fd68  mov     rdx, [rbp+3Fh+ppszUserName]; Src
0x18000fd6c  mov     rcx, r14; void *
0x18000fd6f  mov     r8d, esi
0x18000fd72  add     r8, r8; Size
0x18000fd75  call    memcpy_0
0x18000fd7a  mov     rsi, [rbp+3Fh+ppszCredmanUserName]
0x18000fd7e  mov     rbx, r12
0x18000fd81  xor     edx, edx
0x18000fd83  mov     rax, [rsi]
0x18000fd86  inc     rbx
0x18000fd89  cmp     [rax+rbx*2], dx
0x18000fd8d  jnz     short loc_18000FD86
0x18000fd8f  mov     r14, [rbp+3Fh+pAuthIdentity]
0x18000fd93  cmp     dword ptr [r14], 201h
0x18000fd9a  jnz     short loc_18000FDDB
0x18000fd9c  mov     ecx, [r14+1Ch]
0x18000fda0  mov     rdx, r15; unsigned __int16 *
0x18000fda3  mov     rax, [rbp+3Fh+pCredentialBlobSize]
0x18000fda7  add     rcx, r14; struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *
0x18000fdaa  mov     rsi, [rbp+3Fh+arg_10]
0x18000fdae  mov     r14, [rbp+3Fh+arg_18]
0x18000fdb2  mov     [rsp+30h], rax; unsigned int *
0x18000fdb7  mov     r9, r14; unsigned __int16 **
0x18000fdba  mov     rax, [rbp+3Fh+ppCredentialBlob]
0x18000fdbe  mov     [rsp+0D0h+var_A8], rax; unsigned __int8 **
0x18000fdc3  mov     [rsp+0D0h+var_B0], rsi; unsigned int *
0x18000fdc8  mov     rsi, [rbp+3Fh+ppszCredmanUserName]
0x18000fdcc  mov     r8, rsi; unsigned __int16 **
0x18000fdcf  call    ?SspiHelperProcessPackedCredentials@@YAJPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@PEBGPEAPEBG2PEAKPEAPEAE3@Z; SspiHelperProcessPackedCredentials(_SEC_WINNT_AUTH_PACKED_CREDENTIALS *,ushort const *,ushort const * *,ushort const * *,ulong *,uchar * *,ulong *)
0x18000fdd4  mov     edi, eax
0x18000fdd6  jmp     loc_18000FC3D
0x18000fddb  mov     rcx, [rbp+3Fh+ppszUserName]; unsigned __int16 *
0x18000fddf  test    rcx, rcx
0x18000fde2  jz      short loc_18000FE2A
0x18000fde4  call    ?LocalCredIsMarshaledCredentialW@@YAHPEBG@Z; LocalCredIsMarshaledCredentialW(ushort const *)
0x18000fde9  mov     rcx, [rbp+3Fh+ppszUserName]; unsigned __int16 *
0x18000fded  test    eax, eax
0x18000fdef  jz      short loc_18000FE28
0x18000fdf1  lea     r8, [rbp+3Fh+var_60]; void **
0x18000fdf5  lea     rdx, [rbp+3Fh+var_70]; enum _CRED_MARSHAL_TYPE *
0x18000fdf9  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x18000fdfe  test    eax, eax
0x18000fe00  jz      short loc_18000FE10
0x18000fe02  mov     r14, [rbp+3Fh+arg_18]
0x18000fe06  mov     edi, 0C000009Ah
0x18000fe0b  jmp     loc_18000FC3D
0x18000fe10  mov     rsi, [rbp+3Fh+arg_10]
0x18000fe14  xor     edx, edx
0x18000fe16  cmp     [rbp+3Fh+var_70], 1
0x18000fe1a  mov     rcx, [rbp+3Fh+ppszUserName]
0x18000fe1e  jnz     short loc_18000FE2E
0x18000fe20  mov     dword ptr [rsi], 3
0x18000fe26  jmp     short loc_18000FE2E
0x18000fe28  xor     edx, edx
0x18000fe2a  mov     rsi, [rbp+3Fh+arg_10]
0x18000fe2e  cmp     [rsi], edx
0x18000fe30  jnz     loc_18000FEC9
0x18000fe36  xor     edi, edi
0x18000fe38  test    rcx, rcx
0x18000fe3b  jz      short loc_18000FE46
0x18000fe3d  call    SspiLocalFree
0x18000fe42  mov     [rbp+3Fh+ppszUserName], rdi
0x18000fe46  mov     rcx, [rbp+3Fh+ppszDomainName]; DataBuffer
0x18000fe4a  test    rcx, rcx
0x18000fe4d  jz      short loc_18000FE58
0x18000fe4f  call    SspiLocalFree
0x18000fe54  mov     [rbp+3Fh+ppszDomainName], rdi
0x18000fe58  lea     r9, [rbp+3Fh+DataBuffer]; ppszPackedCredentialsString
0x18000fe5c  mov     rcx, r14; pAuthIdentity
0x18000fe5f  lea     r8, [rbp+3Fh+ppszDomainName]; ppszDomainName
0x18000fe63  lea     rdx, [rbp+3Fh+ppszUserName]; ppszUserName
0x18000fe67  call    SspiEncodeAuthIdentityAsStrings
0x18000fe6c  xor     r14d, r14d
0x18000fe6f  mov     edi, eax
0x18000fe71  test    eax, eax
0x18000fe73  js      loc_18000FC35
0x18000fe79  mov     rax, [rbp+3Fh+ppszDomainName]
0x18000fe7d  test    rax, rax
0x18000fe80  jz      short loc_18000FE88
0x18000fe82  cmp     [rax], r14w
0x18000fe86  jnz     short loc_18000FEC3
0x18000fe88  mov     rdx, [rbp+3Fh+DataBuffer]; unsigned __int16 *
0x18000fe8c  lea     rax, [rbp+3Fh+Size]
0x18000fe90  mov     rcx, [rbp+3Fh+ppszUserName]; unsigned __int16 *
0x18000fe94  lea     r9, [rbp+3Fh+var_50]; unsigned __int16 **
0x18000fe98  mov     [rsp+0D0h+var_A8], rax; unsigned int *
0x18000fe9d  lea     r8, [rbp+3Fh+var_58]; unsigned __int16 **
0x18000fea1  lea     rax, [rbp+3Fh+var_90]
0x18000fea5  mov     [rsp+0D0h+var_B0], rax; struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **
0x18000feaa  call    ?SspiHelperProcessEncodedPackedCredentials@@YAJPEBG0PEAPEBG1PEAPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@PEAK@Z; SspiHelperProcessEncodedPackedCredentials(ushort const *,ushort const *,ushort const * *,ushort const * *,_SEC_WINNT_AUTH_PACKED_CREDENTIALS * *,ulong *)
0x18000feaf  mov     edi, eax
0x18000feb1  test    eax, eax
0x18000feb3  jns     short loc_18000FF02
0x18000feb5  cmp     eax, 0C0000225h
0x18000feba  jnz     loc_18000FC35
0x18000fec0  mov     edi, r14d
0x18000fec3  mov     dword ptr [rsi], 2
0x18000fec9  mov     rsi, [rbp+3Fh+arg_8]
0x18000fecd  mov     eax, r13d
0x18000fed0  test    rsi, rsi
0x18000fed3  mov     ecx, 40h ; '@'; uFlags
0x18000fed8  cmovz   eax, ebx
0x18000fedb  lea     edx, ds:2[rax*2]
0x18000fee2  add     rdx, 2; uBytes
0x18000fee6  call    cs:__imp_LocalAlloc
  ... truncated ...
```
