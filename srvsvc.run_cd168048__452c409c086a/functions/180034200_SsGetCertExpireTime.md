# SsGetCertExpireTime

- ea: `0x180034200`
- end: `0x1800345ac`
- name: `SsGetCertExpireTime`
- size: `940`
- prototype: `__int64 __fastcall(LPCWSTR pszString, void *pvPara)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180011e2c`

## callees

- `0x18001deb0`
- `0x180020dc0`
- `0x180020de8`
- `0x180033fc8`
- `0x180034200`
- `0x180035d44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003427a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003454b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003427a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003454b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003452e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003452e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800343a0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800343a0`
- `CRYPT32!CertFreeCertificateContext` at `0x18003441f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800344e4`
- `CRYPT32!CertFreeCertificateContext` at `0x18003441f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800344e4`
- `CRYPT32!CertCloseStore` at `0x180034541`
- `CRYPT32!CertCloseStore` at `0x180034541`
- `CRYPT32!CertFindCertificateInStore` at `0x18003432f`
- `CRYPT32!CertFindCertificateInStore` at `0x18003440e`
- `CRYPT32!CertFindCertificateInStore` at `0x18003432f`
- `CRYPT32!CertFindCertificateInStore` at `0x18003440e`
- `CRYPT32!CertOpenStore` at `0x18003426c`
- `CRYPT32!CertOpenStore` at `0x18003426c`

## pseudocode

```c
__int64 __fastcall SsGetCertExpireTime(LPCWSTR pszString, void *pvPara, FILETIME *a3)
{
  HCERTSTORE v5; // r15
  DWORD LastError; // eax
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  PCCERT_CONTEXT CertificateInStore; // rsi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int i; // r14d
  PCCERT_CONTEXT v14; // r12
  _QWORD *v15; // rcx
  DWORD v16; // eax
  DWORD pcbData; // [rsp+30h] [rbp-50h] BYREF
  __int128 v19; // [rsp+38h] [rbp-48h] BYREF
  __int128 pvFindPara; // [rsp+48h] [rbp-38h] BYREF
  _BYTE pvData[24]; // [rsp+58h] [rbp-28h] BYREF

  pcbData = 20;
  pvFindPara = 0;
  v19 = 0;
  if ( !pszString || !pvPara )
  {
    v5 = 0;
    v7 = 87;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_48;
    }
    v12 = 95;
    goto LABEL_47;
  }
  v5 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x20000u, pvPara);
  if ( !v5 )
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v9 = 96;
LABEL_8:
      WPP_SF_d(v8[2], v9, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, LastError);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  LastError = SsConvertCryptStringToBinary(pszString, (DWORD *)&pvFindPara);
  v7 = LastError;
  if ( !LastError )
  {
    CertificateInStore = CertFindCertificateInStore(v5, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    if ( CertificateInStore )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 0x14 )
          goto LABEL_36;
        pcbData = 20;
        if ( !CertGetCertificateContextProperty(CertificateInStore, 0x40u, pvData, &pcbData) )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                99,
                WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids,
                CertificateInStore);
LABEL_36:
              v15 = WPP_GLOBAL_Control;
            }
            if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 2u )
              WPP_SF_d(v15[2], 102, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, i);
          }
          *a3 = CertificateInStore->pCertInfo->NotAfter;
          goto LABEL_42;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            100,
            WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids,
            CertificateInStore);
        }
        LODWORD(v19) = pcbData;
        *((_QWORD *)&v19 + 1) = pvData;
        v14 = CertFindCertificateInStore(v5, 0x10001u, 0, 0x10000u, &v19, 0);
        if ( !v14 )
          break;
        CertFreeCertificateContext(CertificateInStore);
        CertificateInStore = v14;
      }
      v7 = 1168;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids);
      }
LABEL_42:
      CertFreeCertificateContext(CertificateInStore);
      goto LABEL_48;
    }
    v7 = 1168;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_48;
    }
    v12 = 98;
LABEL_47:
    WPP_SF_(v11[2], v12, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids);
    goto LABEL_48;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v9 = 97;
    goto LABEL_8;
  }
LABEL_48:
  if ( *((_QWORD *)&pvFindPara + 1) )
    LocalFree(*((HLOCAL *)&pvFindPara + 1));
  if ( v5 )
  {
    if ( !CertCloseStore(v5, 2u) )
    {
      v16 = GetLastError();
      v7 = v16;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v16);
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180034200  mov     [rsp-38h+arg_18], rbx
0x180034205  push    rbp
0x180034206  push    rsi
0x180034207  push    rdi
0x180034208  push    r12
0x18003420a  push    r13
0x18003420c  push    r14
0x18003420e  push    r15
0x180034210  mov     rbp, rsp
0x180034213  sub     rsp, 80h
0x18003421a  mov     rax, cs:__security_cookie
0x180034221  xor     rax, rsp
0x180034224  mov     [rbp+var_10], rax
0x180034228  mov     [rbp+pcbData], 14h
0x18003422f  xorps   xmm0, xmm0
0x180034232  xorps   xmm1, xmm1
0x180034235  mov     r13, r8
0x180034238  mov     rbx, rcx
0x18003423b  movups  [rbp+pvFindPara], xmm0
0x18003423f  movups  [rbp+var_48], xmm1
0x180034243  test    rcx, rcx
0x180034246  jz      loc_1800344EC
0x18003424c  test    rdx, rdx
0x18003424f  jz      loc_1800344EC
0x180034255  xor     r8d, r8d; hCryptProv
0x180034258  mov     [rsp+80h+pvPara], rdx; pvPara
0x18003425d  mov     r9d, 20000h; dwFlags
0x180034263  mov     edx, 10001h; dwEncodingType
0x180034268  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18003426c  call    cs:__imp_CertOpenStore
0x180034272  mov     r15, rax
0x180034275  test    rax, rax
0x180034278  jnz     short loc_1800342C9
0x18003427a  call    cs:__imp_GetLastError
0x180034280  mov     edi, eax
0x180034282  mov     rcx, cs:WPP_GLOBAL_Control
0x180034289  lea     rbx, WPP_GLOBAL_Control
0x180034290  cmp     rcx, rbx
0x180034293  jz      loc_180034525
0x180034299  test    byte ptr [rcx+1Ch], 1
0x18003429d  jz      loc_180034525
0x1800342a3  cmp     byte ptr [rcx+19h], 1
0x1800342a7  jb      loc_180034525
0x1800342ad  lea     edx, [r15+60h]
0x1800342b1  mov     rcx, [rcx+10h]
0x1800342b5  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800342bc  mov     r9d, eax
0x1800342bf  call    WPP_SF_d
0x1800342c4  jmp     loc_180034525
0x1800342c9  lea     rdx, [rbp+pvFindPara]; pcbBinary
0x1800342cd  mov     rcx, rbx; pszString
0x1800342d0  call    SsConvertCryptStringToBinary
0x1800342d5  mov     edi, eax
0x1800342d7  test    eax, eax
0x1800342d9  jz      short loc_18003430D
0x1800342db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342e2  lea     rbx, WPP_GLOBAL_Control
0x1800342e9  cmp     rcx, rbx
0x1800342ec  jz      loc_180034525
0x1800342f2  test    byte ptr [rcx+1Ch], 1
0x1800342f6  jz      loc_180034525
0x1800342fc  cmp     byte ptr [rcx+19h], 1
0x180034300  jb      loc_180034525
0x180034306  mov     edx, 61h ; 'a'
0x18003430b  jmp     short loc_1800342B1
0x18003430d  mov     r9d, 10000h; dwFindType
0x180034313  mov     [rsp+80h+pPrevCertContext], 0; pPrevCertContext
0x18003431c  lea     rax, [rbp+pvFindPara]
0x180034320  xor     r8d, r8d; dwFindFlags
0x180034323  mov     rcx, r15; hCertStore
0x180034326  mov     [rsp+80h+pvPara], rax; pvFindPara
0x18003432b  lea     edx, [r9+1]; dwCertEncodingType
0x18003432f  call    cs:__imp_CertFindCertificateInStore
0x180034335  mov     rsi, rax
0x180034338  test    rax, rax
0x18003433b  jnz     short loc_180034375
0x18003433d  mov     edi, 490h
0x180034342  mov     rcx, cs:WPP_GLOBAL_Control
0x180034349  lea     rbx, WPP_GLOBAL_Control
0x180034350  cmp     rcx, rbx
0x180034353  jz      loc_180034525
0x180034359  test    byte ptr [rcx+1Ch], 1
0x18003435d  jz      loc_180034525
0x180034363  cmp     byte ptr [rcx+19h], 1
0x180034367  jb      loc_180034525
0x18003436d  lea     edx, [rax+62h]
0x180034370  jmp     loc_180034515
0x180034375  xor     r14d, r14d
0x180034378  lea     rbx, WPP_GLOBAL_Control
0x18003437f  cmp     r14d, 14h
0x180034383  jnb     loc_1800344A0
0x180034389  lea     r9, [rbp+pcbData]; pcbData
0x18003438d  mov     [rbp+pcbData], 14h
0x180034394  lea     r8, [rbp+pvData]; pvData
0x180034398  mov     edx, 40h ; '@'; dwPropId
0x18003439d  mov     rcx, rsi; pCertContext
0x1800343a0  call    cs:__imp_CertGetCertificateContextProperty
0x1800343a6  test    eax, eax
0x1800343a8  jz      loc_180034470
0x1800343ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800343b5  cmp     rcx, rbx
0x1800343b8  jz      short loc_1800343DE
0x1800343ba  test    byte ptr [rcx+1Ch], 1
0x1800343be  jz      short loc_1800343DE
0x1800343c0  cmp     byte ptr [rcx+19h], 2
0x1800343c4  jb      short loc_1800343DE
0x1800343c6  mov     rcx, [rcx+10h]
0x1800343ca  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800343d1  mov     edx, 64h ; 'd'
0x1800343d6  mov     r9, rsi
0x1800343d9  call    WPP_SF_q
0x1800343de  mov     eax, [rbp+pcbData]
0x1800343e1  mov     r9d, 10000h; dwFindType
0x1800343e7  mov     dword ptr [rbp+var_48], eax
0x1800343ea  xor     r8d, r8d; dwFindFlags
0x1800343ed  lea     rax, [rbp+pvData]
0x1800343f1  mov     [rsp+80h+pPrevCertContext], 0; pPrevCertContext
0x1800343fa  mov     qword ptr [rbp+var_48+8], rax
0x1800343fe  mov     rcx, r15; hCertStore
0x180034401  lea     rax, [rbp+var_48]
0x180034405  lea     edx, [r9+1]; dwCertEncodingType
0x180034409  mov     [rsp+80h+pvPara], rax; pvFindPara
0x18003440e  call    cs:__imp_CertFindCertificateInStore
0x180034414  mov     r12, rax
0x180034417  test    rax, rax
0x18003441a  jz      short loc_180034430
0x18003441c  mov     rcx, rsi; pCertContext
0x18003441f  call    cs:__imp_CertFreeCertificateContext
0x180034425  inc     r14d
0x180034428  mov     rsi, r12
0x18003442b  jmp     loc_18003437F
0x180034430  mov     edi, 490h
0x180034435  mov     rcx, cs:WPP_GLOBAL_Control
0x18003443c  cmp     rcx, rbx
0x18003443f  jz      loc_1800344DC
0x180034445  test    byte ptr [rcx+1Ch], 1
0x180034449  jz      loc_1800344DC
0x18003444f  cmp     byte ptr [rcx+19h], 1
0x180034453  jb      loc_1800344DC
0x180034459  mov     rcx, [rcx+10h]
0x18003445d  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180034464  mov     edx, 65h ; 'e'
0x180034469  call    WPP_SF_
0x18003446e  jmp     short loc_1800344DC
0x180034470  mov     rcx, cs:WPP_GLOBAL_Control
0x180034477  cmp     rcx, rbx
0x18003447a  jz      short loc_1800344D0
0x18003447c  test    byte ptr [rcx+1Ch], 1
0x180034480  jz      short loc_1800344A7
0x180034482  cmp     byte ptr [rcx+19h], 2
0x180034486  jb      short loc_1800344A7
0x180034488  mov     rcx, [rcx+10h]
0x18003448c  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180034493  mov     edx, 63h ; 'c'
0x180034498  mov     r9, rsi
0x18003449b  call    WPP_SF_q
0x1800344a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344a7  cmp     rcx, rbx
0x1800344aa  jz      short loc_1800344D0
0x1800344ac  test    byte ptr [rcx+1Ch], 1
0x1800344b0  jz      short loc_1800344D0
0x1800344b2  cmp     byte ptr [rcx+19h], 2
0x1800344b6  jb      short loc_1800344D0
0x1800344b8  mov     rcx, [rcx+10h]
0x1800344bc  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800344c3  mov     edx, 66h ; 'f'
0x1800344c8  mov     r9d, r14d
0x1800344cb  call    WPP_SF_d
0x1800344d0  mov     rax, [rsi+18h]
0x1800344d4  mov     rax, [rax+48h]
0x1800344d8  mov     [r13+0], rax
0x1800344dc  test    rsi, rsi
0x1800344df  jz      short loc_180034525
0x1800344e1  mov     rcx, rsi; pCertContext
0x1800344e4  call    cs:__imp_CertFreeCertificateContext
0x1800344ea  jmp     short loc_180034525
0x1800344ec  xor     r15d, r15d
0x1800344ef  lea     edi, [r15+57h]
0x1800344f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344fa  lea     rbx, WPP_GLOBAL_Control
0x180034501  cmp     rcx, rbx
0x180034504  jz      short loc_180034525
0x180034506  test    byte ptr [rcx+1Ch], 1
0x18003450a  jz      short loc_180034525
0x18003450c  cmp     byte ptr [rcx+19h], 1
0x180034510  jb      short loc_180034525
0x180034512  lea     edx, [rdi+8]
0x180034515  mov     rcx, [rcx+10h]
0x180034519  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180034520  call    WPP_SF_
0x180034525  mov     rcx, qword ptr [rbp+pvFindPara+8]; hMem
0x180034529  test    rcx, rcx
0x18003452c  jz      short loc_180034534
0x18003452e  call    cs:__imp_LocalFree
0x180034534  test    r15, r15
0x180034537  jz      short loc_180034583
0x180034539  mov     edx, 2; dwFlags
0x18003453e  mov     rcx, r15; hCertStore
0x180034541  call    cs:__imp_CertCloseStore
0x180034547  test    eax, eax
0x180034549  jnz     short loc_180034583
0x18003454b  call    cs:__imp_GetLastError
0x180034551  mov     edi, eax
0x180034553  mov     rcx, cs:WPP_GLOBAL_Control
0x18003455a  cmp     rcx, rbx
0x18003455d  jz      short loc_180034583
0x18003455f  test    byte ptr [rcx+1Ch], 1
0x180034563  jz      short loc_180034583
0x180034565  cmp     byte ptr [rcx+19h], 1
0x180034569  jb      short loc_180034583
0x18003456b  mov     rcx, [rcx+10h]
0x18003456f  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180034576  mov     edx, 67h ; 'g'
0x18003457b  mov     r9d, eax
0x18003457e  call    WPP_SF_d
0x180034583  mov     eax, edi
0x180034585  mov     rcx, [rbp+var_10]
0x180034589  xor     rcx, rsp; StackCookie
0x18003458c  call    __security_check_cookie
0x180034591  mov     rbx, [rsp+80h+arg_18]
0x180034599  add     rsp, 80h
0x1800345a0  pop     r15
0x1800345a2  pop     r14
0x1800345a4  pop     r13
0x1800345a6  pop     r12
0x1800345a8  pop     rdi
0x1800345a9  pop     rsi
0x1800345aa  pop     rbp
0x1800345ab  retn
```
