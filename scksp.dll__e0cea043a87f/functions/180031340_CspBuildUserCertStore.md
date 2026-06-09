# CspBuildUserCertStore

- ea: `0x180031340`
- end: `0x180031795`
- name: `CspBuildUserCertStore`
- size: `1109`
- prototype: `__int64 __fastcall(__int64, __int64, int, HCERTSTORE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800229fc`

## callees

- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x18002e6d4`
- `0x18002eb6c`
- `0x18002f1c8`
- `0x1800300a4`
- `0x180030e7c`
- `0x180031340`
- `0x18003179c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031706`
- `CRYPT32!CertFreeCertificateContext` at `0x1800314d4`
- `CRYPT32!CertFreeCertificateContext` at `0x180031743`
- `CRYPT32!CertFreeCertificateContext` at `0x1800314d4`
- `CRYPT32!CertFreeCertificateContext` at `0x180031743`
- `CRYPT32!CertCloseStore` at `0x180031720`
- `CRYPT32!CertCloseStore` at `0x180031720`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180031660`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180031660`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800315dd`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800315fb`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180031641`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800315dd`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800315fb`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180031641`
- `CRYPT32!CertOpenStore` at `0x180031415`
- `CRYPT32!CertOpenStore` at `0x180031415`
- `CRYPT32!CertCreateCertificateContext` at `0x18003154f`
- `CRYPT32!CertCreateCertificateContext` at `0x18003154f`

## pseudocode

```c
__int64 __fastcall CspBuildUserCertStore(__int64 a1, __int64 a2, int a3, HCERTSTORE *a4)
{
  int v5; // ebx
  __int64 v6; // rsi
  const CERT_CONTEXT *CertificateContext; // r14
  __int64 v8; // r12
  DWORD LastError; // ebx
  int v10; // r9d
  HCERTSTORE v11; // rax
  DWORD v12; // eax
  __int64 v13; // r8
  unsigned __int8 i; // r13
  __int64 v15; // rcx
  unsigned int j; // r15d
  DWORD v17; // eax
  DWORD UserCertificate; // eax
  int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  int v23; // edx
  HCERTSTORE *v24; // rdi
  __int64 v26; // [rsp+38h] [rbp-59h] BYREF
  __int128 pvData; // [rsp+40h] [rbp-51h] BYREF
  BYTE *pbCertEncoded[2]; // [rsp+50h] [rbp-41h] BYREF
  __int128 v29; // [rsp+60h] [rbp-31h] BYREF
  __int128 v30; // [rsp+70h] [rbp-21h] BYREF
  __int128 v31; // [rsp+80h] [rbp-11h]
  __int128 v32; // [rsp+90h] [rbp-1h]
  __int64 v34; // [rsp+100h] [rbp+6Fh] BYREF
  int v35; // [rsp+108h] [rbp+77h] BYREF
  HCERTSTORE *v36; // [rsp+110h] [rbp+7Fh]

  v36 = a4;
  v35 = a3;
  v5 = a1;
  v6 = 0;
  CertificateContext = 0;
  v34 = 0;
  v8 = 0;
  v26 = 0;
  LOBYTE(v35) = 0;
  pvData = 0;
  v29 = 0;
  *(_OWORD *)pbCertEncoded = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  if ( !*(_QWORD *)(a1 + 8) )
  {
    LastError = 87;
    WppTraceIndent(a1, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_9990ba7a724b3d1b787a644c0a5cfe6b_Traceguids,
        v10,
        (__int64)"pCardState->pCardData");
    }
    goto LABEL_54;
  }
  v11 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  *a4 = v11;
  if ( !v11 )
  {
LABEL_53:
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_54;
    goto LABEL_56;
  }
  v12 = I_ContainerMapFind(v5, 0, 0, (unsigned int)&v26, (__int64)&v35);
  v8 = v26;
  LastError = v12;
  if ( v12 )
    goto LABEL_54;
  LODWORD(v31) = 0;
  *((_QWORD *)&v30 + 1) = L"Microsoft Smart Card Key Storage Provider";
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned __int8)v35 )
      goto LABEL_56;
    v15 = v8 + 86LL * i;
    v26 = v15;
    if ( (*(_BYTE *)(v15 + 80) & 1) != 0 )
      break;
LABEL_42:
    ;
  }
  *(_QWORD *)&v30 = v8 + 86LL * i;
  for ( j = 2; ; j = j == 2 )
  {
    if ( !j )
      goto LABEL_42;
    if ( (j != 2 || *(_WORD *)(v15 + 82)) && (j != 1 || *(_WORD *)(v15 + 84)) )
      break;
LABEL_41:
    ;
  }
  if ( pbCertEncoded[1] )
  {
    CspFreeH(pbCertEncoded[1]);
    pbCertEncoded[1] = 0;
  }
  if ( CertificateContext )
  {
    CertFreeCertificateContext(CertificateContext);
    CertificateContext = 0;
  }
  if ( v6 )
  {
    CspFreeH(v6);
    v34 = 0;
  }
  LOBYTE(v13) = i;
  v17 = CspBuildCertificateFilename(a1, 0, v13, j, &v34);
  v6 = v34;
  LastError = v17;
  if ( v17 )
    goto LABEL_54;
  UserCertificate = CspReadUserCertificate(a1, v34, (unsigned int *)pbCertEncoded);
  LastError = UserCertificate;
  if ( UserCertificate )
  {
    if ( UserCertificate != -2146435028 )
      goto LABEL_54;
    LastError = 0;
LABEL_40:
    v15 = v26;
    goto LABEL_41;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded[1], (DWORD)pbCertEncoded[0]);
  if ( !CertificateContext )
    goto LABEL_53;
  DWORD2(v32) = 0;
  if ( **(_DWORD **)(a1 + 8) < 6u )
  {
LABEL_38:
    if ( !CertSetCertificateContextProperty(CertificateContext, 2u, 0, &v30)
      || !CertAddCertificateContextToStore(*v36, CertificateContext, 4u, 0) )
    {
      goto LABEL_53;
    }
    goto LABEL_40;
  }
  LOBYTE(v19) = i;
  LastError = GetCachedCardContainerProperty(
                a1,
                v19,
                (unsigned int)L"PIN Identifier",
                (unsigned int)&pvData + 8,
                (__int64)&pvData);
  if ( !LastError )
  {
    if ( (_DWORD)pvData != 4 )
    {
      LastError = -2146893820;
      goto LABEL_54;
    }
    LastError = GetCardPinInfo(a1, (unsigned int)**((_DWORD **)&pvData + 1), (char *)&v29 + 8);
    if ( LastError )
    {
      WppTraceIndent(v21, 2);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = 12;
LABEL_52:
        WPP_SF_sd(
          v22[2],
          v23,
          (unsigned int)WPP_9990ba7a724b3d1b787a644c0a5cfe6b_Traceguids,
          (_DWORD)WPP_pszIndent,
          LastError);
        goto LABEL_54;
      }
      goto LABEL_54;
    }
    LODWORD(v29) = 36;
    if ( !CertSetCertificateContextProperty(CertificateContext, 0x5Au, 0x40000000u, &pvData)
      || !CertSetCertificateContextProperty(CertificateContext, 0x5Bu, 0x40000000u, &v29) )
    {
      goto LABEL_53;
    }
    if ( *((_QWORD *)&pvData + 1) )
    {
      CspFreeH(*((_QWORD *)&pvData + 1));
      *((_QWORD *)&pvData + 1) = 0;
    }
    if ( *((_QWORD *)&v29 + 1) )
    {
      CspFreeH(*((_QWORD *)&v29 + 1));
      *((_QWORD *)&v29 + 1) = 0;
    }
    goto LABEL_38;
  }
  WppTraceIndent(v20, 2);
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v23 = 11;
    goto LABEL_52;
  }
LABEL_54:
  v24 = v36;
  if ( *v36 )
  {
    CertCloseStore(*v36, 0);
    *v24 = 0;
  }
LABEL_56:
  if ( pbCertEncoded[1] )
    CspFreeH(pbCertEncoded[1]);
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
  if ( v6 )
    CspFreeH(v6);
  if ( v8 )
    CspFreeH(v8);
  if ( *((_QWORD *)&pvData + 1) )
    CspFreeH(*((_QWORD *)&pvData + 1));
  if ( *((_QWORD *)&v29 + 1) )
    CspFreeH(*((_QWORD *)&v29 + 1));
  return LastError;
}

```

## disassembly

```asm
0x180031340  mov     rax, rsp
0x180031343  mov     [rax+20h], r9
0x180031347  mov     [rax+18h], r8d
0x18003134b  mov     [rax+10h], rdx
0x18003134f  mov     [rax+8], rcx
0x180031353  push    rbp
0x180031354  push    rbx
0x180031355  push    rsi
0x180031356  push    rdi
0x180031357  push    r12
0x180031359  push    r13
0x18003135b  push    r14
0x18003135d  push    r15
0x18003135f  lea     rbp, [rax-5Fh]
0x180031363  sub     rsp, 0A8h
0x18003136a  xor     eax, eax
0x18003136c  xorps   xmm1, xmm1
0x18003136f  xorps   xmm0, xmm0
0x180031372  mov     r15, r9
0x180031375  mov     rbx, rcx
0x180031378  mov     esi, eax
0x18003137a  mov     r14d, eax
0x18003137d  mov     [rbp+57h+arg_8], rax
0x180031381  lea     edi, [rax+2]
0x180031384  mov     r12d, eax
0x180031387  mov     [rbp+57h+var_B0], rax
0x18003138b  mov     byte ptr [rbp+57h+arg_10], al
0x18003138e  movups  [rbp+57h+pvData], xmm0
0x180031392  movups  [rbp+57h+var_88], xmm1
0x180031396  movups  xmmword ptr [rbp+57h+pbCertEncoded], xmm0
0x18003139a  movups  [rbp+57h+var_78], xmm1
0x18003139e  movups  [rbp+57h+var_68], xmm1
0x1800313a2  movups  [rbp+57h+var_58], xmm1
0x1800313a6  cmp     [rcx+8], rax
0x1800313aa  jnz     short loc_180031405
0x1800313ac  mov     edx, edi
0x1800313ae  lea     ebx, [rax+57h]
0x1800313b1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800313b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313bd  lea     rax, WPP_GLOBAL_Control
0x1800313c4  cmp     rcx, rax
0x1800313c7  jz      loc_180031712
0x1800313cd  test    byte ptr [rcx+1Ch], 1
0x1800313d1  jz      loc_180031712
0x1800313d7  cmp     [rcx+19h], dil
0x1800313db  jb      loc_180031712
0x1800313e1  mov     rcx, [rcx+10h]
0x1800313e5  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x1800313ec  lea     edx, [rdi+8]
0x1800313ef  mov     [rsp+20h], rax
0x1800313f4  lea     r8, WPP_9990ba7a724b3d1b787a644c0a5cfe6b_Traceguids
0x1800313fb  call    WPP_SF_ss
0x180031400  jmp     loc_180031712
0x180031405  xor     r9d, r9d; dwFlags
0x180031408  mov     [rsp+20h], rax; pvPara
0x18003140d  xor     r8d, r8d; hCryptProv
0x180031410  xor     edx, edx; dwEncodingType
0x180031412  mov     rcx, rdi; lpszStoreProvider
0x180031415  call    cs:__imp_CertOpenStore
0x18003141b  mov     [r15], rax
0x18003141e  test    rax, rax
0x180031421  jz      loc_180031706
0x180031427  lea     rax, [rbp+57h+arg_10]
0x18003142b  xor     r8d, r8d
0x18003142e  lea     r9, [rbp+57h+var_B0]
0x180031432  mov     [rsp+20h], rax
0x180031437  xor     edx, edx
0x180031439  mov     rcx, rbx
0x18003143c  call    I_ContainerMapFind
0x180031441  mov     r12, [rbp+57h+var_B0]
0x180031445  mov     ebx, eax
0x180031447  test    eax, eax
0x180031449  jnz     loc_180031712
0x18003144f  lea     rax, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x180031456  mov     dword ptr [rbp+57h+var_68], esi
0x180031459  mov     qword ptr [rbp+57h+var_78+8], rax
0x18003145d  xor     r13b, r13b
0x180031460  cmp     r13b, byte ptr [rbp+57h+arg_10]
0x180031464  jnb     loc_18003172D
0x18003146a  movzx   eax, r13b
0x18003146e  imul    rcx, rax, 56h ; 'V'
0x180031472  add     rcx, r12
0x180031475  mov     [rbp+57h+var_B0], rcx
0x180031479  test    byte ptr [rcx+50h], 1
0x18003147d  jz      loc_180031682
0x180031483  mov     qword ptr [rbp+57h+var_78], rcx
0x180031487  mov     r15d, edi
0x18003148a  test    r15d, r15d
0x18003148d  jz      loc_180031682
0x180031493  cmp     r15d, edi
0x180031496  jnz     short loc_1800314A4
0x180031498  xor     eax, eax
0x18003149a  cmp     ax, [rcx+52h]
0x18003149e  jz      loc_180031672
0x1800314a4  cmp     r15d, 1
0x1800314a8  jnz     short loc_1800314B6
0x1800314aa  xor     eax, eax
0x1800314ac  cmp     ax, [rcx+54h]
0x1800314b0  jz      loc_180031672
0x1800314b6  mov     rcx, [rbp+57h+pbCertEncoded+8]
0x1800314ba  test    rcx, rcx
0x1800314bd  jz      short loc_1800314CC
0x1800314bf  call    CspFreeH
0x1800314c4  mov     [rbp+57h+pbCertEncoded+8], 0
0x1800314cc  test    r14, r14
0x1800314cf  jz      short loc_1800314DD
0x1800314d1  mov     rcx, r14; pCertContext
0x1800314d4  call    cs:__imp_CertFreeCertificateContext
0x1800314da  xor     r14d, r14d
0x1800314dd  test    rsi, rsi
0x1800314e0  jz      short loc_1800314F2
0x1800314e2  mov     rcx, rsi
0x1800314e5  call    CspFreeH
0x1800314ea  mov     [rbp+57h+arg_8], 0
0x1800314f2  mov     rcx, [rbp+57h+arg_0]
0x1800314f6  lea     rax, [rbp+57h+arg_8]
0x1800314fa  mov     r9d, r15d
0x1800314fd  mov     [rsp+20h], rax
0x180031502  mov     r8b, r13b
0x180031505  xor     edx, edx
0x180031507  call    CspBuildCertificateFilename
0x18003150c  mov     rsi, [rbp+57h+arg_8]
0x180031510  mov     ebx, eax
0x180031512  test    eax, eax
0x180031514  jnz     loc_180031712
0x18003151a  mov     rcx, [rbp+57h+arg_0]
0x18003151e  lea     r8, [rbp+57h+pbCertEncoded]
0x180031522  mov     rdx, rsi
0x180031525  call    CspReadUserCertificate
0x18003152a  mov     ebx, eax
0x18003152c  test    eax, eax
0x18003152e  jz      short loc_180031542
0x180031530  cmp     eax, 8010002Ch
0x180031535  jnz     loc_180031712
0x18003153b  xor     ebx, ebx
0x18003153d  jmp     loc_18003166E
0x180031542  mov     r8d, dword ptr [rbp+57h+pbCertEncoded]; cbCertEncoded
0x180031546  mov     ecx, 10001h; dwCertEncodingType
0x18003154b  mov     rdx, [rbp+57h+pbCertEncoded+8]; pbCertEncoded
0x18003154f  call    cs:__imp_CertCreateCertificateContext
0x180031555  mov     r14, rax
0x180031558  test    rax, rax
0x18003155b  jz      loc_180031706
0x180031561  mov     rcx, [rbp+57h+arg_0]
0x180031565  mov     dword ptr [rbp+57h+var_58+8], 0
0x18003156c  mov     rax, [rcx+8]
0x180031570  cmp     dword ptr [rax], 6
0x180031573  jb      loc_180031635
0x180031579  lea     rax, [rbp+57h+pvData]
0x18003157d  mov     dl, r13b
0x180031580  lea     r9, [rbp+57h+pvData+8]
0x180031584  mov     [rsp+20h], rax
0x180031589  lea     r8, aPinIdentifier; "PIN Identifier"
0x180031590  call    GetCachedCardContainerProperty
0x180031595  mov     ebx, eax
0x180031597  test    eax, eax
0x180031599  jnz     loc_1800316BE
0x18003159f  cmp     dword ptr [rbp+57h+pvData], 4
0x1800315a3  jnz     loc_1800316B7
0x1800315a9  mov     rdx, qword ptr [rbp+57h+pvData+8]
0x1800315ad  lea     r8, [rbp+57h+var_88+8]
0x1800315b1  mov     rcx, [rbp+57h+arg_0]
0x1800315b5  mov     edx, [rdx]
0x1800315b7  call    GetCardPinInfo
0x1800315bc  mov     ebx, eax
0x1800315be  test    eax, eax
0x1800315c0  jnz     loc_18003168A
0x1800315c6  lea     r9, [rbp+57h+pvData]; pvData
0x1800315ca  mov     dword ptr [rbp+57h+var_88], 24h ; '$'
0x1800315d1  lea     edx, [rax+5Ah]; dwPropId
0x1800315d4  mov     r8d, 40000000h; dwFlags
0x1800315da  mov     rcx, r14; pCertContext
0x1800315dd  call    cs:__imp_CertSetCertificateContextProperty
0x1800315e3  test    eax, eax
0x1800315e5  jz      loc_180031706
0x1800315eb  lea     r9, [rbp+57h+var_88]; pvData
0x1800315ef  mov     r8d, 40000000h; dwFlags
0x1800315f5  lea     edx, [rbx+5Bh]; dwPropId
0x1800315f8  mov     rcx, r14; pCertContext
0x1800315fb  call    cs:__imp_CertSetCertificateContextProperty
0x180031601  test    eax, eax
0x180031603  jz      loc_180031706
0x180031609  mov     rcx, qword ptr [rbp+57h+pvData+8]
0x18003160d  test    rcx, rcx
0x180031610  jz      short loc_18003161F
0x180031612  call    CspFreeH
0x180031617  mov     qword ptr [rbp+57h+pvData+8], 0
0x18003161f  mov     rcx, qword ptr [rbp+57h+var_88+8]
0x180031623  test    rcx, rcx
0x180031626  jz      short loc_180031635
0x180031628  call    CspFreeH
0x18003162d  mov     qword ptr [rbp+57h+var_88+8], 0
0x180031635  lea     r9, [rbp+57h+var_78]; pvData
0x180031639  xor     r8d, r8d; dwFlags
0x18003163c  mov     edx, edi; dwPropId
0x18003163e  mov     rcx, r14; pCertContext
0x180031641  call    cs:__imp_CertSetCertificateContextProperty
0x180031647  test    eax, eax
0x180031649  jz      loc_180031706
0x18003164f  mov     rax, [rbp+57h+arg_18]
0x180031653  xor     r9d, r9d; ppStoreContext
0x180031656  mov     rdx, r14; pCertContext
0x180031659  mov     rcx, [rax]; hCertStore
0x18003165c  lea     r8d, [r9+4]; dwAddDisposition
0x180031660  call    cs:__imp_CertAddCertificateContextToStore
0x180031666  test    eax, eax
0x180031668  jz      loc_180031706
0x18003166e  mov     rcx, [rbp+57h+var_B0]
0x180031672  xor     eax, eax
0x180031674  cmp     r15d, edi
0x180031677  setz    al
0x18003167a  mov     r15d, eax
0x18003167d  jmp     loc_18003148A
0x180031682  inc     r13b
0x180031685  jmp     loc_180031460
0x18003168a  mov     edx, edi
0x18003168c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031691  mov     rcx, cs:WPP_GLOBAL_Control
0x180031698  lea     rax, WPP_GLOBAL_Control
0x18003169f  cmp     rcx, rax
0x1800316a2  jz      short loc_180031712
0x1800316a4  test    byte ptr [rcx+1Ch], 1
0x1800316a8  jz      short loc_180031712
0x1800316aa  cmp     [rcx+19h], dil
0x1800316ae  jb      short loc_180031712
0x1800316b0  mov     edx, 0Ch
0x1800316b5  jmp     short loc_1800316E9
0x1800316b7  mov     ebx, 80090004h
0x1800316bc  jmp     short loc_180031712
0x1800316be  mov     edx, edi
0x1800316c0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800316c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316cc  lea     rax, WPP_GLOBAL_Control
0x1800316d3  cmp     rcx, rax
0x1800316d6  jz      short loc_180031712
0x1800316d8  test    byte ptr [rcx+1Ch], 1
0x1800316dc  jz      short loc_180031712
0x1800316de  cmp     [rcx+19h], dil
0x1800316e2  jb      short loc_180031712
0x1800316e4  mov     edx, 0Bh
0x1800316e9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800316f0  lea     r8, WPP_9990ba7a724b3d1b787a644c0a5cfe6b_Traceguids
0x1800316f7  mov     rcx, [rcx+10h]
0x1800316fb  mov     [rsp+20h], ebx
0x1800316ff  call    WPP_SF_sd
0x180031704  jmp     short loc_180031712
0x180031706  call    cs:__imp_GetLastError
0x18003170c  mov     ebx, eax
0x18003170e  test    eax, eax
0x180031710  jz      short loc_18003172D
0x180031712  mov     rdi, [rbp+57h+arg_18]
0x180031716  mov     rcx, [rdi]; hCertStore
0x180031719  test    rcx, rcx
0x18003171c  jz      short loc_18003172D
0x18003171e  xor     edx, edx; dwFlags
0x180031720  call    cs:__imp_CertCloseStore
0x180031726  mov     qword ptr [rdi], 0
0x18003172d  mov     rcx, [rbp+57h+pbCertEncoded+8]
0x180031731  test    rcx, rcx
0x180031734  jz      short loc_18003173B
0x180031736  call    CspFreeH
0x18003173b  test    r14, r14
0x18003173e  jz      short loc_180031749
0x180031740  mov     rcx, r14; pCertContext
0x180031743  call    cs:__imp_CertFreeCertificateContext
0x180031749  test    rsi, rsi
0x18003174c  jz      short loc_180031756
0x18003174e  mov     rcx, rsi
0x180031751  call    CspFreeH
0x180031756  test    r12, r12
0x180031759  jz      short loc_180031763
0x18003175b  mov     rcx, r12
0x18003175e  call    CspFreeH
0x180031763  mov     rcx, qword ptr [rbp+57h+pvData+8]
0x180031767  test    rcx, rcx
0x18003176a  jz      short loc_180031771
0x18003176c  call    CspFreeH
0x180031771  mov     rcx, qword ptr [rbp+57h+var_88+8]
0x180031775  test    rcx, rcx
0x180031778  jz      short loc_18003177F
0x18003177a  call    CspFreeH
0x18003177f  mov     eax, ebx
0x180031781  add     rsp, 0A8h
0x180031788  pop     r15
0x18003178a  pop     r14
0x18003178c  pop     r13
0x18003178e  pop     r12
0x180031790  pop     rdi
0x180031791  pop     rsi
0x180031792  pop     rbx
0x180031793  pop     rbp
0x180031794  retn
```
