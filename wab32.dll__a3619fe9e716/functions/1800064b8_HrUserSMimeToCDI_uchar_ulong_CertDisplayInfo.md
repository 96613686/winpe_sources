# HrUserSMimeToCDI(uchar *,ulong,_CertDisplayInfo *)

- ea: `0x1800064b8`
- end: `0x180006834`
- name: `?HrUserSMimeToCDI@@YAJPEAEKPEAU_CertDisplayInfo@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD cbData, struct _CertDisplayInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005a1c`

## callees

- `0x1800064b8`
- `0x180091e92`
- `0x180091eaa`
- `0x180091eb6`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800065ba`
- `KERNEL32!LocalAlloc` at `0x18000662c`
- `KERNEL32!LocalAlloc` at `0x180006756`
- `KERNEL32!LocalAlloc` at `0x1800065ba`
- `KERNEL32!LocalAlloc` at `0x18000662c`
- `KERNEL32!LocalAlloc` at `0x180006756`
- `KERNEL32!LocalFree` at `0x1800067f7`
- `KERNEL32!LocalFree` at `0x18000680a`
- `KERNEL32!LocalFree` at `0x1800067f7`
- `KERNEL32!LocalFree` at `0x18000680a`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180006523`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180006523`
- `CRYPT32!CryptMsgUpdate` at `0x180006543`
- `CRYPT32!CryptMsgUpdate` at `0x180006543`
- `CRYPT32!CryptMsgGetParam` at `0x180006573`
- `CRYPT32!CryptMsgGetParam` at `0x1800065a6`
- `CRYPT32!CryptMsgGetParam` at `0x1800065e7`
- `CRYPT32!CryptMsgGetParam` at `0x1800066ff`
- `CRYPT32!CryptMsgGetParam` at `0x180006735`
- `CRYPT32!CryptMsgGetParam` at `0x180006787`
- `CRYPT32!CryptMsgGetParam` at `0x180006573`
- `CRYPT32!CryptMsgGetParam` at `0x1800065a6`
- `CRYPT32!CryptMsgGetParam` at `0x1800065e7`
- `CRYPT32!CryptMsgGetParam` at `0x1800066ff`
- `CRYPT32!CryptMsgGetParam` at `0x180006735`
- `CRYPT32!CryptMsgGetParam` at `0x180006787`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800066a9`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800066a9`
- `CRYPT32!CertCompareCertificate` at `0x1800067c2`
- `CRYPT32!CertCompareCertificate` at `0x1800067c2`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800067cf`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800067cf`
- `CRYPT32!CryptMsgClose` at `0x180006818`
- `CRYPT32!CryptMsgClose` at `0x180006818`

## pseudocode

```c
__int64 __fastcall HrUserSMimeToCDI(BYTE *pbData, DWORD cbData, struct _CertDisplayInfo *a3)
{
  HLOCAL v6; // r14
  HCRYPTMSG v7; // rax
  void *v8; // rdi
  DWORD v9; // ebx
  unsigned int i; // ebx
  __int64 v11; // r15
  HLOCAL v12; // rax
  const void **v13; // rdx
  __int64 v14; // r8
  CERT_NAME_BLOB v15; // xmm1
  DWORD v16; // eax
  DWORD j; // esi
  HLOCAL v18; // r12
  DWORD k; // esi
  __int64 v20; // rax
  const CERT_CONTEXT *v21; // r15
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v24; // [rsp+44h] [rbp-BCh] BYREF
  int pvData; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _CERT_INFO pCertId2; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v28; // [rsp+198h] [rbp+98h] BYREF

  pcbData = 0;
  v28 = 0;
  v24 = 0;
  memset_0(&pCertId2, 0, sizeof(pCertId2));
  pvData = 0;
  hMem[0] = 0;
  v6 = 0;
  v7 = CryptMsgOpenToDecode(0x10000u, 0, 0, 0, 0, 0);
  v8 = v7;
  if ( !v7 )
    goto LABEL_33;
  if ( !CryptMsgUpdate(v7, pbData, cbData, 1) )
    goto LABEL_33;
  pcbData = 4;
  if ( !CryptMsgGetParam(v8, 5u, 0, &pvData, &pcbData) || !pvData || !CryptMsgGetParam(v8, 6u, 0, 0, &pcbData) )
    goto LABEL_33;
  v6 = LocalAlloc(0, pcbData);
  if ( !v6 )
  {
LABEL_7:
    v9 = -2147024882;
    goto LABEL_34;
  }
  if ( !CryptMsgGetParam(v8, 6u, 0, v6, &pcbData) )
    goto LABEL_33;
  for ( i = 0; i < *((_DWORD *)v6 + 26); ++i )
  {
    v11 = *((_QWORD *)v6 + 14);
    if ( !strcmp_0(*(const char **)(v11 + 24LL * i), "1.2.840.113549.1.9.15") )
    {
      v12 = LocalAlloc(0x40u, **(unsigned int **)(v11 + 24LL * i + 16));
      *((_QWORD *)a3 + 7) = v12;
      if ( !v12 )
        goto LABEL_7;
      *((_DWORD *)a3 + 12) = **(_DWORD **)(v11 + 24LL * i + 16);
      v13 = *(const void ***)(v11 + 24LL * i + 16);
      memcpy_0(v12, v13[1], *(unsigned int *)v13);
    }
    else if ( !strcmp_0(*(const char **)(v11 + 24LL * i), "1.3.6.1.4.1.311.16.4") )
    {
      v14 = *(_QWORD *)(v11 + 24LL * i + 16);
      CryptDecodeObjectEx(
        1u,
        "1.3.6.1.4.1.311.16.4",
        *(const BYTE **)(v14 + 8),
        *(_DWORD *)v14,
        0x8000u,
        0,
        hMem,
        &pcbData);
    }
  }
  v9 = 0;
  if ( !hMem[0] )
    goto LABEL_37;
  pCertId2.SerialNumber = *(CRYPT_INTEGER_BLOB *)((char *)hMem[0] + 24);
  v15 = *(CERT_NAME_BLOB *)((char *)hMem[0] + 8);
  v28 = 4;
  pCertId2.Issuer = v15;
  if ( CryptMsgGetParam(v8, 0xBu, 0, &v24, &v28) )
  {
    v16 = v28;
    for ( j = 0; j < v24; ++j )
    {
      if ( !CryptMsgGetParam(v8, 0xCu, j, 0, &v28) )
        goto LABEL_33;
      v16 = v28;
      if ( v9 < v28 )
        v9 = v28;
    }
    v18 = LocalAlloc(0, v16);
    for ( k = 0; k < v24; ++k )
    {
      v28 = v9;
      if ( !CryptMsgGetParam(v8, 0xCu, k, v18, &v28) )
        goto LABEL_33;
      v20 = ((__int64 (__fastcall *)(__int64, HLOCAL, _QWORD))gpfnCertCreateCertificateContext)(1, v18, v28);
      v21 = (const CERT_CONTEXT *)v20;
      if ( v20 && CertCompareCertificate(1u, *(PCERT_INFO *)(v20 + 24), &pCertId2) )
        *((_QWORD *)a3 + 5) = CertDuplicateCertificateContext(v21);
    }
    v9 = 0;
  }
  else
  {
LABEL_33:
    v9 = -2147467259;
  }
LABEL_34:
  if ( hMem[0] )
  {
    LocalFree(hMem[0]);
    hMem[0] = 0;
  }
  if ( v6 )
LABEL_37:
    LocalFree(v6);
  if ( v8 )
    CryptMsgClose(v8);
  return v9;
}

```

## disassembly

```asm
0x1800064b8  push    rbp
0x1800064ba  push    rbx
0x1800064bb  push    rsi
0x1800064bc  push    rdi
0x1800064bd  push    r12
0x1800064bf  push    r13
0x1800064c1  push    r14
0x1800064c3  push    r15
0x1800064c5  lea     rbp, [rsp-38h]
0x1800064ca  sub     rsp, 138h
0x1800064d1  xor     r12d, r12d
0x1800064d4  mov     r13, r8
0x1800064d7  mov     ebx, edx
0x1800064d9  mov     [rsp+170h+pcbData], r12d
0x1800064de  mov     rsi, rcx
0x1800064e1  mov     [rbp+70h+arg_18], r12d
0x1800064e8  xor     edx, edx; Val
0x1800064ea  mov     [rsp+170h+var_12C], r12d
0x1800064ef  mov     r8d, 0D0h; Size
0x1800064f5  lea     rcx, [rsp+170h+pCertId2]; void *
0x1800064fa  call    memset_0
0x1800064ff  xor     r9d, r9d; hCryptProv
0x180006502  mov     [rsp+170h+pStreamInfo], r12; pStreamInfo
0x180006507  xor     r8d, r8d; dwMsgType
0x18000650a  mov     [rsp+170h+pvData], r12d
0x18000650f  xor     edx, edx; dwFlags
0x180006511  mov     [rsp+170h+hMem], r12
0x180006516  mov     ecx, 10000h; dwMsgEncodingType
0x18000651b  mov     [rsp+170h+pRecipientInfo], r12; pRecipientInfo
0x180006520  mov     r14d, r12d
0x180006523  call    cs:__imp_CryptMsgOpenToDecode
0x180006529  mov     rdi, rax
0x18000652c  test    rax, rax
0x18000652f  jz      loc_1800067E8
0x180006535  lea     r9d, [r12+1]; fFinal
0x18000653a  mov     r8d, ebx; cbData
0x18000653d  mov     rdx, rsi; pbData
0x180006540  mov     rcx, rax; hCryptMsg
0x180006543  call    cs:__imp_CryptMsgUpdate
0x180006549  test    eax, eax
0x18000654b  jz      loc_1800067E8
0x180006551  lea     rax, [rsp+170h+pcbData]
0x180006556  mov     [rsp+170h+pcbData], 4
0x18000655e  lea     r9, [rsp+170h+pvData]; pvData
0x180006563  mov     [rsp+170h+pRecipientInfo], rax; pcbData
0x180006568  xor     r8d, r8d; dwIndex
0x18000656b  lea     edx, [r12+5]; dwParamType
0x180006570  mov     rcx, rdi; hCryptMsg
0x180006573  call    cs:__imp_CryptMsgGetParam
0x180006579  test    eax, eax
0x18000657b  jz      loc_1800067E8
0x180006581  cmp     [rsp+170h+pvData], r12d
0x180006586  jz      loc_1800067E8
0x18000658c  lea     rax, [rsp+170h+pcbData]
0x180006591  xor     r9d, r9d; pvData
0x180006594  lea     ebx, [r12+6]
0x180006599  mov     [rsp+170h+pRecipientInfo], rax; pcbData
0x18000659e  mov     edx, ebx; dwParamType
0x1800065a0  xor     r8d, r8d; dwIndex
0x1800065a3  mov     rcx, rdi; hCryptMsg
0x1800065a6  call    cs:__imp_CryptMsgGetParam
0x1800065ac  test    eax, eax
0x1800065ae  jz      loc_1800067E8
0x1800065b4  mov     edx, [rsp+170h+pcbData]; uBytes
0x1800065b8  xor     ecx, ecx; uFlags
0x1800065ba  call    cs:__imp_LocalAlloc
0x1800065c0  mov     r14, rax
0x1800065c3  test    rax, rax
0x1800065c6  jnz     short loc_1800065D2
0x1800065c8  mov     ebx, 8007000Eh
0x1800065cd  jmp     loc_1800067ED
0x1800065d2  lea     rax, [rsp+170h+pcbData]
0x1800065d7  mov     r9, r14; pvData
0x1800065da  xor     r8d, r8d; dwIndex
0x1800065dd  mov     [rsp+170h+pRecipientInfo], rax; pcbData
0x1800065e2  mov     edx, ebx; dwParamType
0x1800065e4  mov     rcx, rdi; hCryptMsg
0x1800065e7  call    cs:__imp_CryptMsgGetParam
0x1800065ed  test    eax, eax
0x1800065ef  jz      loc_1800067E8
0x1800065f5  mov     ebx, r12d
0x1800065f8  cmp     ebx, [r14+68h]
0x1800065fc  jnb     loc_1800066B6
0x180006602  mov     r15, [r14+70h]
0x180006606  lea     rdx, Str2; "1.2.840.113549.1.9.15"
0x18000660d  mov     eax, ebx
0x18000660f  lea     rsi, [rax+rax*2]
0x180006613  mov     rcx, [r15+rsi*8]; Str1
0x180006617  call    strcmp_0
0x18000661c  test    eax, eax
0x18000661e  jnz     short loc_18000665C
0x180006620  mov     rax, [r15+rsi*8+10h]
0x180006625  mov     ecx, 40h ; '@'; uFlags
0x18000662a  mov     edx, [rax]; uBytes
0x18000662c  call    cs:__imp_LocalAlloc
0x180006632  mov     [r13+38h], rax
0x180006636  test    rax, rax
0x180006639  jz      short loc_1800065C8
0x18000663b  mov     rcx, [r15+rsi*8+10h]
0x180006640  mov     edx, [rcx]
0x180006642  mov     rcx, rax; void *
0x180006645  mov     [r13+30h], edx
0x180006649  mov     rdx, [r15+rsi*8+10h]
0x18000664e  mov     r8d, [rdx]; Size
0x180006651  mov     rdx, [rdx+8]; Src
0x180006655  call    memcpy_0
0x18000665a  jmp     short loc_1800066AF
0x18000665c  mov     rcx, [r15+rsi*8]; Str1
0x180006660  lea     rdx, szStructType; "1.3.6.1.4.1.311.16.4"
0x180006667  call    strcmp_0
0x18000666c  test    eax, eax
0x18000666e  jnz     short loc_1800066AF
0x180006670  mov     r8, [r15+rsi*8+10h]
0x180006675  lea     rax, [rsp+170h+pcbData]
0x18000667a  mov     [rsp+170h+pcbStructInfo], rax; pcbStructInfo
0x18000667f  lea     rdx, szStructType; "1.3.6.1.4.1.311.16.4"
0x180006686  lea     rax, [rsp+170h+hMem]
0x18000668b  mov     ecx, 1; dwCertEncodingType
0x180006690  mov     [rsp+170h+pvStructInfo], rax; pvStructInfo
0x180006695  mov     r9d, [r8]; cbEncoded
0x180006698  mov     r8, [r8+8]; pbEncoded
0x18000669c  mov     [rsp+170h+pStreamInfo], r12; pDecodePara
0x1800066a1  mov     dword ptr [rsp+170h+pRecipientInfo], 8000h; dwFlags
0x1800066a9  call    cs:__imp_CryptDecodeObjectEx
0x1800066af  inc     ebx
0x1800066b1  jmp     loc_1800065F8
0x1800066b6  mov     rax, [rsp+170h+hMem]
0x1800066bb  mov     ebx, r12d
0x1800066be  test    rax, rax
0x1800066c1  jz      loc_180006807
0x1800066c7  movups  xmm0, xmmword ptr [rax+18h]
0x1800066cb  xor     r8d, r8d; dwIndex
0x1800066ce  lea     r9, [rsp+170h+var_12C]; pvData
0x1800066d3  mov     rcx, rdi; hCryptMsg
0x1800066d6  movdqu  xmmword ptr [rsp+170h+pCertId2.SerialNumber.cbData], xmm0
0x1800066dc  movups  xmm1, xmmword ptr [rax+8]
0x1800066e0  lea     rax, [rbp+70h+arg_18]
0x1800066e7  mov     [rbp+70h+arg_18], 4
0x1800066f1  lea     edx, [r8+0Bh]; dwParamType
0x1800066f5  mov     [rsp+170h+pRecipientInfo], rax; pcbData
0x1800066fa  movdqu  xmmword ptr [rbp+70h+pCertId2.Issuer.cbData], xmm1
0x1800066ff  call    cs:__imp_CryptMsgGetParam
0x180006705  test    eax, eax
0x180006707  jz      loc_1800067E8
0x18000670d  mov     eax, [rbp+70h+arg_18]
0x180006713  mov     esi, r12d
0x180006716  cmp     esi, [rsp+170h+var_12C]
0x18000671a  jnb     short loc_180006752
0x18000671c  xor     r9d, r9d; pvData
0x18000671f  lea     rax, [rbp+70h+arg_18]
0x180006726  mov     r8d, esi; dwIndex
0x180006729  mov     [rsp+170h+pRecipientInfo], rax; pcbData
0x18000672e  mov     rcx, rdi; hCryptMsg
0x180006731  lea     edx, [r9+0Ch]; dwParamType
0x180006735  call    cs:__imp_CryptMsgGetParam
0x18000673b  test    eax, eax
0x18000673d  jz      loc_1800067E8
0x180006743  mov     eax, [rbp+70h+arg_18]
0x180006749  cmp     ebx, eax
0x18000674b  cmovb   ebx, eax
0x18000674e  inc     esi
0x180006750  jmp     short loc_180006716
0x180006752  mov     edx, eax; uBytes
0x180006754  xor     ecx, ecx; uFlags
0x180006756  call    cs:__imp_LocalAlloc
0x18000675c  mov     r12, rax
0x18000675f  xor     esi, esi
0x180006761  cmp     esi, [rsp+170h+var_12C]
0x180006765  jnb     short loc_1800067DD
0x180006767  lea     rax, [rbp+70h+arg_18]
0x18000676e  mov     [rbp+70h+arg_18], ebx
0x180006774  mov     r9, r12; pvData
0x180006777  mov     [rsp+170h+pRecipientInfo], rax; pcbData
0x18000677c  mov     r8d, esi; dwIndex
0x18000677f  mov     edx, 0Ch; dwParamType
0x180006784  mov     rcx, rdi; hCryptMsg
0x180006787  call    cs:__imp_CryptMsgGetParam
0x18000678d  test    eax, eax
0x18000678f  jz      short loc_1800067E5
0x180006791  mov     r8d, [rbp+70h+arg_18]
0x180006798  mov     rdx, r12
0x18000679b  mov     rax, cs:?gpfnCertCreateCertificateContext@@3P6APEBU_CERT_CONTEXT@@KPEBEK@ZEA; _CERT_CONTEXT const * (*gpfnCertCreateCertificateContext)(ulong,uchar const *,ulong)
0x1800067a2  mov     ecx, 1
0x1800067a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ac  mov     r15, rax
0x1800067af  test    rax, rax
0x1800067b2  jz      short loc_1800067D9
0x1800067b4  mov     rdx, [rax+18h]; pCertId1
0x1800067b8  lea     r8, [rsp+170h+pCertId2]; pCertId2
0x1800067bd  mov     ecx, 1; dwCertEncodingType
0x1800067c2  call    cs:__imp_CertCompareCertificate
0x1800067c8  test    eax, eax
0x1800067ca  jz      short loc_1800067D9
0x1800067cc  mov     rcx, r15; pCertContext
0x1800067cf  call    cs:__imp_CertDuplicateCertificateContext
0x1800067d5  mov     [r13+28h], rax
0x1800067d9  inc     esi
0x1800067db  jmp     short loc_180006761
0x1800067dd  xor     r12d, r12d
0x1800067e0  mov     ebx, r12d
0x1800067e3  jmp     short loc_1800067ED
0x1800067e5  xor     r12d, r12d
0x1800067e8  mov     ebx, 80004005h
0x1800067ed  mov     rcx, [rsp+170h+hMem]; hMem
0x1800067f2  test    rcx, rcx
0x1800067f5  jz      short loc_180006802
0x1800067f7  call    cs:__imp_LocalFree
0x1800067fd  mov     [rsp+170h+hMem], r12
0x180006802  test    r14, r14
0x180006805  jz      short loc_180006810
0x180006807  mov     rcx, r14; hMem
0x18000680a  call    cs:__imp_LocalFree
0x180006810  test    rdi, rdi
0x180006813  jz      short loc_18000681E
0x180006815  mov     rcx, rdi; hCryptMsg
0x180006818  call    cs:__imp_CryptMsgClose
0x18000681e  mov     eax, ebx
0x180006820  add     rsp, 138h
0x180006827  pop     r15
0x180006829  pop     r14
0x18000682b  pop     r13
0x18000682d  pop     r12
0x18000682f  pop     rdi
0x180006830  pop     rsi
0x180006831  pop     rbx
0x180006832  pop     rbp
0x180006833  retn
```
