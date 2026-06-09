# SsValidCertandUpdateCertinfo

- ea: `0x180034df0`
- end: `0x18003548f`
- name: `SsValidCertandUpdateCertinfo`
- size: `1695`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180031c8c`
- `0x180032f00`

## callees

- `0x180020dc0`
- `0x180020de8`
- `0x1800214a4`
- `0x180031be4`
- `0x180033c28`
- `0x180033fc8`
- `0x1800347cc`
- `0x180034c10`
- `0x180034ce0`
- `0x180034df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003541c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003541c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035201`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035256`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800352c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035201`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035256`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800352c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035394`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035394`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180035338`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180035338`
- `CRYPT32!CertFreeCertificateContext` at `0x180034f6e`
- `CRYPT32!CertFreeCertificateContext` at `0x18003539d`
- `CRYPT32!CertFreeCertificateContext` at `0x180034f6e`
- `CRYPT32!CertFreeCertificateContext` at `0x18003539d`
- `CRYPT32!CertCloseStore` at `0x180034f81`
- `CRYPT32!CertCloseStore` at `0x1800353ab`
- `CRYPT32!CertCloseStore` at `0x180034f81`
- `CRYPT32!CertCloseStore` at `0x1800353ab`
- `CRYPT32!CertFindCertificateInStore` at `0x18003504b`
- `CRYPT32!CertFindCertificateInStore` at `0x18003504b`
- `CRYPT32!CertOpenStore` at `0x180034e8c`
- `CRYPT32!CertOpenStore` at `0x180034e8c`

## pseudocode

```c
__int64 __fastcall SsValidCertandUpdateCertinfo(__int64 **a1)
{
  __int64 **v1; // rax
  _UNKNOWN **v2; // rdx
  __int64 *v4; // rcx
  const CERT_CONTEXT *v5; // rsi
  char v6; // r12
  char v7; // r13
  HCERTSTORE v8; // r15
  DWORD LastError; // eax
  DWORD v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  char v14; // bp
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  PCCERT_CONTEXT CertificateInStore; // rax
  __int64 v22; // rbp
  __int64 v23; // r8
  _QWORD *v24; // rcx
  DWORD v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  _QWORD *v28; // rcx
  _QWORD *v29; // rcx
  DWORD v30; // eax
  HLOCAL v31; // rax
  __int64 v32; // rcx
  HLOCAL v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rax
  SIZE_T v37; // r14
  HLOCAL v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  DWORD v41; // eax
  __int64 v42; // rbx
  DWORD v43; // eax
  DWORD pcbData; // [rsp+30h] [rbp-68h] BYREF
  int pvData; // [rsp+34h] [rbp-64h] BYREF
  HLOCAL hMem[2]; // [rsp+38h] [rbp-60h] BYREF
  char v47; // [rsp+A8h] [rbp+10h]
  char v48; // [rsp+B0h] [rbp+18h]
  char v49; // [rsp+B8h] [rbp+20h]

  v1 = (__int64 **)*a1;
  v2 = &WPP_GLOBAL_Control;
  pcbData = 4;
  pvData = 0;
  *(_OWORD *)hMem = 0;
  v47 = 0;
  v4 = *v1;
  v5 = 0;
  v48 = 0;
  v6 = 0;
  v49 = 0;
  v7 = 0;
  if ( !**v1 || !v4[3] || !v4[8] )
  {
    v8 = 0;
    v10 = 87;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_11;
    }
    v12 = 56;
    v13 = 87;
    goto LABEL_10;
  }
  v8 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x20000u, (const void *)v4[8]);
  if ( !v8 )
  {
    LastError = GetLastError();
    v10 = LastError;
    v11 = WPP_GLOBAL_Control;
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_11;
    }
    v12 = 57;
    goto LABEL_9;
  }
  LastError = SsConvertCryptStringToBinary(*(LPCWSTR *)(**a1 + 24), (DWORD *)hMem);
  v10 = LastError;
  if ( LastError )
  {
    v11 = WPP_GLOBAL_Control;
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_11;
    }
    v12 = 58;
LABEL_9:
    v13 = LastError;
LABEL_10:
    WPP_SF_d(v11[2], v12, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v13);
LABEL_11:
    v14 = 0;
LABEL_12:
    LOBYTE(v2) = v47;
    FreeCertField(**a1 + 8, v2);
    LOBYTE(v15) = v6;
    FreeCertField(**a1 + 16, v15);
    LOBYTE(v16) = v7;
    FreeCertField(**a1 + 32, v16);
    LOBYTE(v17) = v48;
    FreeCertField(**a1 + 40, v17);
    LOBYTE(v18) = v49;
    FreeCertField(**a1 + 48, v18);
    LOBYTE(v19) = v14;
    FreeCertField(**a1 + 56, v19);
    if ( hMem[1] )
      LocalFree(hMem[1]);
    if ( v5 )
      CertFreeCertificateContext(v5);
    if ( v8 )
    {
      if ( !CertCloseStore(v8, 2u) )
      {
        v10 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v10);
        }
      }
    }
    return v10;
  }
  CertificateInStore = CertFindCertificateInStore(v8, 0x10001u, 0, 0x10000u, hMem, 0);
  v5 = CertificateInStore;
  if ( !CertificateInStore )
  {
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v42 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v43 = GetLastError();
      WPP_SF_d(v42, 64, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v43);
    }
    v10 = 1168;
    goto LABEL_34;
  }
  v22 = *(_QWORD *)**a1;
  if ( !(unsigned int)SsIsValidCertMappingName(v22, CertificateInStore) )
  {
    v10 = 1616;
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v22);
    }
    goto LABEL_34;
  }
  v24 = (_QWORD *)(**a1 + 8);
  if ( !*v24 )
  {
    if ( !(unsigned int)SsGetOptionalCertificateName(v24, 2, v23, v5) )
    {
      v25 = GetLastError();
      v10 = v25;
      v26 = WPP_GLOBAL_Control;
      v2 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_34;
      }
      v27 = 60;
LABEL_41:
      WPP_SF_d(v26[2], v27, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v25);
LABEL_34:
      v14 = 0;
      goto LABEL_12;
    }
    v47 = 1;
  }
  v28 = (_QWORD *)(**a1 + 16);
  if ( !*v28 )
  {
    if ( !(unsigned int)SsGetCertificateName(v28, 4, 1, v5) )
    {
      v25 = GetLastError();
      v10 = v25;
      v26 = WPP_GLOBAL_Control;
      v2 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_34;
      }
      v27 = 61;
      goto LABEL_41;
    }
    v6 = 1;
  }
  v29 = (_QWORD *)(**a1 + 32);
  if ( !*v29 )
  {
    if ( !(unsigned int)SsGetOptionalCertificateName(v29, 5, v23, v5) )
    {
      v30 = GetLastError();
      v10 = v30;
      v2 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v30);
      }
      v14 = 0;
      goto LABEL_12;
    }
    v7 = 1;
  }
  if ( !*(_QWORD *)(**a1 + 40) )
  {
    v31 = LocalAlloc(0x40u, 0x2Au);
    v2 = (_UNKNOWN **)**a1;
    v2[5] = v31;
    v32 = *(_QWORD *)(**a1 + 40);
    if ( !v32 )
      goto LABEL_93;
    RtlStringCbPrintfW(v32, 42, L"%llu", *(_QWORD *)&v5->pCertInfo->NotBefore);
    v48 = 1;
  }
  if ( *(_QWORD *)(**a1 + 48) )
    goto LABEL_64;
  v33 = LocalAlloc(0x40u, 0x2Au);
  v2 = (_UNKNOWN **)**a1;
  v2[6] = v33;
  v34 = *(_QWORD *)(**a1 + 48);
  if ( !v34 )
  {
LABEL_93:
    v14 = 0;
    goto LABEL_12;
  }
  RtlStringCbPrintfW(v34, 42, L"%llu", *(_QWORD *)&v5->pCertInfo->NotAfter);
  v49 = 1;
LABEL_64:
  v35 = **a1;
  if ( *(_QWORD *)(v35 + 56) )
  {
    v14 = 0;
  }
  else
  {
    v36 = -1;
    do
      ++v36;
    while ( *(_WORD *)(*(_QWORD *)(v35 + 64) + 2 * v36) );
    v37 = 2 * v36 + 40;
    v38 = LocalAlloc(0x40u, v37);
    v2 = (_UNKNOWN **)**a1;
    v2[7] = v38;
    v39 = **a1;
    v40 = *(_QWORD *)(v39 + 56);
    if ( !v40 )
    {
      v14 = 0;
      goto LABEL_12;
    }
    RtlStringCbPrintfW(v40, v37, L"%ws%ws", L"cert:\\LocalMachine\\", *(_QWORD *)(v39 + 64));
    v14 = 1;
  }
  *(_DWORD *)(**a1 + 80) = 0;
  *(_DWORD *)(**a1 + 92) = 0;
  if ( !CertGetCertificateContextProperty(v5, 6u, &pvData, &pcbData) )
  {
    v10 = -1067646970;
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids);
    }
    goto LABEL_12;
  }
  if ( hMem[1] )
    LocalFree(hMem[1]);
  CertFreeCertificateContext(v5);
  if ( !CertCloseStore(v8, 2u) )
  {
    v41 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v41);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180034df0  push    rbx
0x180034df2  push    rbp
0x180034df3  push    rsi
0x180034df4  push    rdi
0x180034df5  push    r12
0x180034df7  push    r13
0x180034df9  push    r14
0x180034dfb  push    r15
0x180034dfd  sub     rsp, 58h
0x180034e01  mov     rax, [rcx]
0x180034e04  lea     rdx, WPP_GLOBAL_Control
0x180034e0b  xor     r14d, r14d
0x180034e0e  mov     [rsp+98h+pcbData], 4
0x180034e16  mov     [rsp+98h+pvData], r14d
0x180034e1b  xorps   xmm0, xmm0
0x180034e1e  movups  xmmword ptr [rsp+98h+hMem], xmm0
0x180034e23  mov     rdi, rcx
0x180034e26  mov     [rsp+98h+arg_8], r14b
0x180034e2e  mov     rcx, [rax]
0x180034e31  lea     ebp, [r14+1]
0x180034e35  mov     esi, r14d
0x180034e38  mov     [rsp+98h+arg_10], r14b
0x180034e40  mov     r12b, r14b
0x180034e43  mov     [rsp+98h+arg_18], r14b
0x180034e4b  mov     r13b, r14b
0x180034e4e  mov     [rsp+98h+arg_0], r14b
0x180034e56  cmp     [rcx], r14
0x180034e59  jz      loc_180035443
0x180034e5f  cmp     [rcx+18h], r14
0x180034e63  jz      loc_180035443
0x180034e69  mov     rax, [rcx+40h]
0x180034e6d  test    rax, rax
0x180034e70  jz      loc_180035443
0x180034e76  mov     r9d, 20000h; dwFlags
0x180034e7c  mov     [rsp+98h+pvPara], rax; pvPara
0x180034e81  xor     r8d, r8d; hCryptProv
0x180034e84  lea     ecx, [rbp+9]; lpszStoreProvider
0x180034e87  mov     edx, 10001h; dwEncodingType
0x180034e8c  call    cs:__imp_CertOpenStore
0x180034e92  mov     r15, rax
0x180034e95  test    rax, rax
0x180034e98  jnz     loc_180034FDD
0x180034e9e  call    cs:__imp_GetLastError
0x180034ea4  mov     ebx, eax
0x180034ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ead  lea     rdx, WPP_GLOBAL_Control
0x180034eb4  cmp     rcx, rdx
0x180034eb7  jz      short loc_180034EDB
0x180034eb9  test    [rcx+1Ch], bpl
0x180034ebd  jz      short loc_180034EDB
0x180034ebf  cmp     [rcx+19h], bpl
0x180034ec3  jb      short loc_180034EDB
0x180034ec5  lea     edx, [rbp+38h]
0x180034ec8  mov     r9d, eax
0x180034ecb  mov     rcx, [rcx+10h]
0x180034ecf  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180034ed6  call    WPP_SF_d
0x180034edb  mov     bpl, sil
0x180034ede  mov     rax, [rdi]
0x180034ee1  mov     dl, [rsp+98h+arg_8]
0x180034ee8  mov     rcx, [rax]
0x180034eeb  add     rcx, 8
0x180034eef  call    FreeCertField
0x180034ef4  mov     rax, [rdi]
0x180034ef7  mov     dl, r12b
0x180034efa  mov     rcx, [rax]
0x180034efd  add     rcx, 10h
0x180034f01  call    FreeCertField
0x180034f06  mov     rax, [rdi]
0x180034f09  mov     dl, r13b
0x180034f0c  mov     rcx, [rax]
0x180034f0f  add     rcx, 20h ; ' '
0x180034f13  call    FreeCertField
0x180034f18  mov     rax, [rdi]
0x180034f1b  mov     dl, [rsp+98h+arg_10]
0x180034f22  mov     rcx, [rax]
0x180034f25  add     rcx, 28h ; '('
0x180034f29  call    FreeCertField
0x180034f2e  mov     rax, [rdi]
0x180034f31  mov     dl, [rsp+98h+arg_18]
0x180034f38  mov     rcx, [rax]
0x180034f3b  add     rcx, 30h ; '0'
0x180034f3f  call    FreeCertField
0x180034f44  mov     rax, [rdi]
0x180034f47  mov     dl, bpl
0x180034f4a  mov     rcx, [rax]
0x180034f4d  add     rcx, 38h ; '8'
0x180034f51  call    FreeCertField
0x180034f56  mov     rcx, [rsp+98h+hMem+8]; hMem
0x180034f5b  test    rcx, rcx
0x180034f5e  jz      short loc_180034F66
0x180034f60  call    cs:__imp_LocalFree
0x180034f66  test    rsi, rsi
0x180034f69  jz      short loc_180034F74
0x180034f6b  mov     rcx, rsi; pCertContext
0x180034f6e  call    cs:__imp_CertFreeCertificateContext
0x180034f74  test    r15, r15
0x180034f77  jz      short loc_180034FCA
0x180034f79  mov     edx, 2; dwFlags
0x180034f7e  mov     rcx, r15; hCertStore
0x180034f81  call    cs:__imp_CertCloseStore
0x180034f87  test    eax, eax
0x180034f89  jnz     short loc_180034FCA
0x180034f8b  call    cs:__imp_GetLastError
0x180034f91  mov     ebx, eax
0x180034f93  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f9a  lea     rax, WPP_GLOBAL_Control
0x180034fa1  cmp     rcx, rax
0x180034fa4  jz      short loc_180034FCA
0x180034fa6  test    byte ptr [rcx+1Ch], 1
0x180034faa  jz      short loc_180034FCA
0x180034fac  cmp     byte ptr [rcx+19h], 1
0x180034fb0  jb      short loc_180034FCA
0x180034fb2  mov     rcx, [rcx+10h]
0x180034fb6  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180034fbd  mov     edx, 42h ; 'B'
0x180034fc2  mov     r9d, ebx
0x180034fc5  call    WPP_SF_d
0x180034fca  mov     eax, ebx
0x180034fcc  add     rsp, 58h
0x180034fd0  pop     r15
0x180034fd2  pop     r14
0x180034fd4  pop     r13
0x180034fd6  pop     r12
0x180034fd8  pop     rdi
0x180034fd9  pop     rsi
0x180034fda  pop     rbp
0x180034fdb  pop     rbx
0x180034fdc  retn
0x180034fdd  mov     rax, [rdi]
0x180034fe0  lea     rdx, [rsp+98h+hMem]; pcbBinary
0x180034fe5  mov     rcx, [rax]
0x180034fe8  mov     rcx, [rcx+18h]; pszString
0x180034fec  call    SsConvertCryptStringToBinary
0x180034ff1  mov     ebx, eax
0x180034ff3  test    eax, eax
0x180034ff5  jz      short loc_18003502C
0x180034ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ffe  lea     rdx, WPP_GLOBAL_Control
0x180035005  cmp     rcx, rdx
0x180035008  jz      loc_180034EDB
0x18003500e  test    [rcx+1Ch], bpl
0x180035012  jz      loc_180034EDB
0x180035018  cmp     [rcx+19h], bpl
0x18003501c  jb      loc_180034EDB
0x180035022  mov     edx, 3Ah ; ':'
0x180035027  jmp     loc_180034EC8
0x18003502c  mov     r9d, 10000h; dwFindType
0x180035032  mov     [rsp+98h+pPrevCertContext], r14; pPrevCertContext
0x180035037  lea     rax, [rsp+98h+hMem]
0x18003503c  xor     r8d, r8d; dwFindFlags
0x18003503f  mov     rcx, r15; hCertStore
0x180035042  mov     [rsp+98h+pvPara], rax; pvFindPara
0x180035047  lea     edx, [r9+1]; dwCertEncodingType
0x18003504b  call    cs:__imp_CertFindCertificateInStore
0x180035051  mov     rsi, rax
0x180035054  test    rax, rax
0x180035057  jz      loc_1800353F9
0x18003505d  mov     rcx, [rdi]
0x180035060  mov     rdx, [rcx]
0x180035063  mov     rbp, [rdx]
0x180035066  mov     rdx, rax
0x180035069  mov     rcx, rbp
0x18003506c  call    SsIsValidCertMappingName
0x180035071  test    eax, eax
0x180035073  jnz     short loc_1800350B7
0x180035075  mov     ebx, 650h
0x18003507a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035081  lea     rdx, WPP_GLOBAL_Control
0x180035088  cmp     rcx, rdx
0x18003508b  jz      short loc_1800350AF
0x18003508d  test    byte ptr [rcx+1Ch], 1
0x180035091  jz      short loc_1800350AF
0x180035093  cmp     byte ptr [rcx+19h], 1
0x180035097  jb      short loc_1800350AF
0x180035099  mov     rcx, [rcx+10h]
0x18003509d  lea     edx, [rax+3Bh]
0x1800350a0  mov     r9, rbp
0x1800350a3  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800350aa  call    WPP_SF_S
0x1800350af  mov     bpl, r12b
0x1800350b2  jmp     loc_180034EDE
0x1800350b7  mov     rax, [rdi]
0x1800350ba  mov     rcx, [rax]
0x1800350bd  add     rcx, 8
0x1800350c1  cmp     [rcx], r14
0x1800350c4  jnz     short loc_180035120
0x1800350c6  mov     r9, rsi
0x1800350c9  mov     edx, 2
0x1800350ce  call    SsGetOptionalCertificateName
0x1800350d3  test    eax, eax
0x1800350d5  jnz     short loc_180035118
0x1800350d7  call    cs:__imp_GetLastError
0x1800350dd  mov     ebx, eax
0x1800350df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350e6  lea     rdx, WPP_GLOBAL_Control
0x1800350ed  cmp     rcx, rdx
0x1800350f0  jz      short loc_1800350AF
0x1800350f2  test    byte ptr [rcx+1Ch], 1
0x1800350f6  jz      short loc_1800350AF
0x1800350f8  cmp     byte ptr [rcx+19h], 1
0x1800350fc  jb      short loc_1800350AF
0x1800350fe  mov     edx, 3Ch ; '<'
0x180035103  mov     rcx, [rcx+10h]
0x180035107  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x18003510e  mov     r9d, eax
0x180035111  call    WPP_SF_d
0x180035116  jmp     short loc_1800350AF
0x180035118  mov     [rsp+98h+arg_8], 1
0x180035120  mov     rax, [rdi]
0x180035123  mov     rcx, [rax]
0x180035126  add     rcx, 10h
0x18003512a  cmp     [rcx], r14
0x18003512d  jnz     short loc_180035181
0x18003512f  mov     edx, 4
0x180035134  mov     r9, rsi
0x180035137  lea     r8d, [rdx-3]
0x18003513b  call    SsGetCertificateName
0x180035140  test    eax, eax
0x180035142  jnz     short loc_18003517E
0x180035144  call    cs:__imp_GetLastError
0x18003514a  mov     ebx, eax
0x18003514c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035153  lea     rdx, WPP_GLOBAL_Control
0x18003515a  cmp     rcx, rdx
0x18003515d  jz      loc_1800350AF
0x180035163  test    byte ptr [rcx+1Ch], 1
0x180035167  jz      loc_1800350AF
0x18003516d  cmp     byte ptr [rcx+19h], 1
0x180035171  jb      loc_1800350AF
0x180035177  mov     edx, 3Dh ; '='
0x18003517c  jmp     short loc_180035103
0x18003517e  mov     r12b, 1
0x180035181  mov     rax, [rdi]
0x180035184  mov     rcx, [rax]
0x180035187  add     rcx, 20h ; ' '
0x18003518b  cmp     [rcx], r14
0x18003518e  jnz     short loc_1800351EB
0x180035190  mov     r9, rsi
0x180035193  mov     edx, 5
0x180035198  call    SsGetOptionalCertificateName
0x18003519d  test    eax, eax
0x18003519f  jnz     short loc_1800351E8
0x1800351a1  call    cs:__imp_GetLastError
0x1800351a7  mov     ebx, eax
0x1800351a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351b0  lea     rdx, WPP_GLOBAL_Control
0x1800351b7  cmp     rcx, rdx
0x1800351ba  jz      short loc_1800351E0
0x1800351bc  test    byte ptr [rcx+1Ch], 1
0x1800351c0  jz      short loc_1800351E0
0x1800351c2  cmp     byte ptr [rcx+19h], 1
0x1800351c6  jb      short loc_1800351E0
0x1800351c8  mov     rcx, [rcx+10h]
0x1800351cc  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800351d3  mov     edx, 3Eh ; '>'
0x1800351d8  mov     r9d, eax
0x1800351db  call    WPP_SF_d
0x1800351e0  mov     bpl, r13b
0x1800351e3  jmp     loc_180034EDE
0x1800351e8  mov     r13b, 1
0x1800351eb  mov     rax, [rdi]
0x1800351ee  mov     ebp, 40h ; '@'
0x1800351f3  mov     rcx, [rax]
0x1800351f6  cmp     [rcx+28h], r14
0x1800351fa  jnz     short loc_180035243
0x1800351fc  lea     edx, [rbp-16h]; uBytes
0x1800351ff  mov     ecx, ebp; uFlags
0x180035201  call    cs:__imp_LocalAlloc
0x180035207  mov     rcx, [rdi]
0x18003520a  mov     rdx, [rcx]
0x18003520d  mov     [rdx+28h], rax
0x180035211  mov     rax, [rdi]
0x180035214  mov     rcx, [rax]
0x180035217  mov     rcx, [rcx+28h]
0x18003521b  test    rcx, rcx
0x18003521e  jz      loc_180035487
0x180035224  mov     r9, [rsi+18h]
0x180035228  lea     r8, aLlu; "%llu"
0x18003522f  lea     edx, [rbp-16h]
0x180035232  mov     r9, [r9+40h]
0x180035236  call    RtlStringCbPrintfW
0x18003523b  mov     [rsp+98h+arg_10], 1
0x180035243  mov     rax, [rdi]
0x180035246  mov     rcx, [rax]
0x180035249  cmp     [rcx+30h], r14
0x18003524d  jnz     short loc_18003529A
0x18003524f  mov     edx, 2Ah ; '*'; uBytes
0x180035254  mov     ecx, ebp; uFlags
0x180035256  call    cs:__imp_LocalAlloc
0x18003525c  mov     rcx, [rdi]
0x18003525f  mov     rdx, [rcx]
0x180035262  mov     [rdx+30h], rax
0x180035266  mov     rax, [rdi]
0x180035269  mov     rcx, [rax]
0x18003526c  mov     rcx, [rcx+30h]
0x180035270  test    rcx, rcx
0x180035273  jz      loc_180035487
0x180035279  mov     r9, [rsi+18h]
0x18003527d  lea     r8, aLlu; "%llu"
  ... truncated ...
```
