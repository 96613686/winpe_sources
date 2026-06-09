# SoftpubCallUI

- ea: `0x180018c30`
- end: `0x1800191b9`
- name: `SoftpubCallUI`
- size: `1417`
- prototype: `__int64 __fastcall(struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180018c00`

## callees

- `0x180018c30`
- `0x1800191c0`
- `0x180019840`
- `0x18001e4e0`
- `0x18001f600`
- `0x18001fc80`
- `0x18002daac`
- `0x180047678`
- `0x18004de6a`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `msvcrt!free` at `0x180018e00`
- `msvcrt!free` at `0x180018f8b`
- `msvcrt!free` at `0x180018e00`
- `msvcrt!free` at `0x180018f8b`
- `msvcrt!malloc` at `0x180018d10`
- `msvcrt!malloc` at `0x180018dc7`
- `msvcrt!malloc` at `0x180018d10`
- `msvcrt!malloc` at `0x180018dc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019132`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019132`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800191ab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800191ab`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18001911a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18001911a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180018cf2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180018d31`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180018dad`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180018de8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180018cf2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180018d31`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180018dad`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180018de8`
- `CRYPT32!CertCloseStore` at `0x180018ea8`
- `CRYPT32!CertCloseStore` at `0x180018f07`
- `CRYPT32!CertCloseStore` at `0x180018f78`
- `CRYPT32!CertCloseStore` at `0x180018ea8`
- `CRYPT32!CertCloseStore` at `0x180018f07`
- `CRYPT32!CertCloseStore` at `0x180018f78`
- `CRYPT32!CertFreeCertificateContext` at `0x180018f19`
- `CRYPT32!CertFreeCertificateContext` at `0x180018fe0`
- `CRYPT32!CertFreeCertificateContext` at `0x180018ff9`
- `CRYPT32!CertFreeCertificateContext` at `0x180018f19`
- `CRYPT32!CertFreeCertificateContext` at `0x180018fe0`
- `CRYPT32!CertFreeCertificateContext` at `0x180018ff9`
- `CRYPT32!CertFindCertificateInStore` at `0x180018e9a`
- `CRYPT32!CertFindCertificateInStore` at `0x180018ef9`
- `CRYPT32!CertFindCertificateInStore` at `0x180018f6a`
- `CRYPT32!CertFindCertificateInStore` at `0x180018e9a`
- `CRYPT32!CertFindCertificateInStore` at `0x180018ef9`
- `CRYPT32!CertFindCertificateInStore` at `0x180018f6a`

## string_xrefs

- `0x180019113`: `cryptui.dll`

## pseudocode

```c
__int64 __fastcall SoftpubCallUI(struct _CRYPT_PROVIDER_DATA *a1, unsigned int a2)
{
  __int64 result; // rax
  bool v5; // zf
  struct _CRYPT_PROVIDER_SGNR *pasSigners; // rax
  const CERT_CONTEXT *pCert; // rsi
  void *v8; // rax
  void *v9; // rbx
  int v10; // r14d
  struct _CRYPT_PROVIDER_SGNR *v11; // rax
  const CERT_CONTEXT *v12; // r14
  void *v13; // rax
  void *v14; // rsi
  unsigned int v15; // r14d
  DWORD dwUIChoice; // ecx
  void *v17; // r14
  const CERT_CONTEXT *v18; // r12
  void *v19; // r12
  const CERT_CONTEXT *v20; // r13
  void *v21; // rsi
  const CERT_CONTEXT *CertificateInStore; // r15
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // r12
  WINTRUST_DATA *pWintrustData; // rcx
  __int64 FileName; // rax
  void *v26; // rsi
  __int64 v27; // r14
  HMODULE LibraryA; // rax
  HMODULE v29; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v31; // r15d
  DWORD *padwTrustStepErrors; // rax
  DWORD pcbData[4]; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v34; // [rsp+40h] [rbp-49h] BYREF
  void *v35; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v36[3]; // [rsp+50h] [rbp-39h] BYREF
  struct _SPC_SP_OPUS_INFO *OpusInfo; // [rsp+68h] [rbp-21h] BYREF
  __int64 v38; // [rsp+70h] [rbp-19h]
  unsigned int v39; // [rsp+78h] [rbp-11h]
  _BYTE v40[20]; // [rsp+7Ch] [rbp-Dh] BYREF
  _BYTE pvData[24]; // [rsp+90h] [rbp+7h] BYREF

  if ( (a1->dwProvFlags & 0x100) == 0 && (a1->dwRegPolicySettings & 0x40000) == 0 && a1->pWintrustData->dwUIChoice == 2 )
  {
    if ( a2 && a2 != -2146762484 )
      return a2;
    result = _CheckTrustedCodeHash(a1);
    if ( (_DWORD)result == 1 )
    {
      v5 = a1->csSigners == 0;
      *(_OWORD *)pcbData = 0;
      if ( !v5 )
      {
        pasSigners = a1->pasSigners;
        if ( pasSigners )
        {
          if ( pasSigners->csCertChain )
          {
            pCert = pasSigners->pasCertChain->pCert;
            *(_QWORD *)&pcbData[2] = pvData;
            pcbData[0] = 20;
            if ( CertGetCertificateContextProperty(pCert, 0xFu, pvData, pcbData) )
            {
              v9 = 0;
              if ( pcbData[0] >= 0x10 )
                goto LABEL_39;
            }
            if ( pcbData[0] > 0x14 )
            {
              v8 = malloc(pcbData[0]);
              *(_QWORD *)&pcbData[2] = v8;
              v9 = v8;
              if ( !v8 || !CertGetCertificateContextProperty(pCert, 0xFu, v8, pcbData) )
              {
                v10 = -2146869247;
                goto LABEL_42;
              }
LABEL_39:
              v10 = 1;
              v21 = _OpenHKCUStore(L"Disallowed");
              if ( v21 )
              {
                CertificateInStore = CertFindCertificateInStore(v21, 0, 0, 0xE0000u, pcbData, 0);
                CertCloseStore(v21, 0);
                if ( CertificateInStore )
                {
                  CertFreeCertificateContext(CertificateInStore);
                  v10 = -2146762479;
                }
              }
LABEL_42:
              if ( v9 )
                free(v9);
              if ( v10 == -2146762479 )
                return 2148204817LL;
            }
          }
        }
      }
      return a2;
    }
    goto LABEL_48;
  }
  result = _CheckTrustedCodeHash(a1);
  if ( (_DWORD)result != 1 )
  {
LABEL_48:
    if ( !(_DWORD)result )
      a1->dwFinalError = 0;
    return result;
  }
  *(_OWORD *)pcbData = 0;
  if ( a1->csSigners )
  {
    v11 = a1->pasSigners;
    if ( v11 )
    {
      if ( v11->csCertChain )
      {
        v12 = v11->pasCertChain->pCert;
        *(_QWORD *)&pcbData[2] = pvData;
        pcbData[0] = 20;
        if ( CertGetCertificateContextProperty(v12, 0xFu, pvData, pcbData) )
        {
          v14 = 0;
          if ( pcbData[0] >= 0x10 )
            goto LABEL_32;
        }
        if ( pcbData[0] <= 0x14 )
          return (unsigned int)-2146869247;
        v13 = malloc(pcbData[0]);
        *(_QWORD *)&pcbData[2] = v13;
        v14 = v13;
        if ( v13 && CertGetCertificateContextProperty(v12, 0xFu, v13, pcbData) )
        {
LABEL_32:
          v17 = _OpenHKCUStore(L"Disallowed");
          if ( v17 && (v18 = CertFindCertificateInStore(v17, 0, 0, 0xE0000u, pcbData, 0), CertCloseStore(v17, 0), v18) )
          {
            CertFreeCertificateContext(v18);
            v15 = -2146762479;
          }
          else
          {
            v15 = 1;
            if ( !a2 )
            {
              v19 = _OpenHKCUStore(L"TrustedPublisher");
              if ( v19 )
              {
                v20 = CertFindCertificateInStore(v19, 0, 0, 0xE0000u, pcbData, 0);
                CertCloseStore(v19, 0);
                if ( v20 )
                {
                  CertFreeCertificateContext(v20);
                  v15 = 0;
                }
              }
            }
          }
        }
        else
        {
          v15 = -2146869247;
        }
        if ( v14 )
          free(v14);
        if ( v15 == 1 )
          goto LABEL_26;
        if ( !v15 )
          a1->dwFinalError = 0;
        return v15;
      }
    }
  }
LABEL_26:
  if ( (a1->dwRegPolicySettings & 0x40000) != 0 )
  {
    if ( !a2 )
      return 2148081702LL;
    return a2;
  }
  dwUIChoice = a1->pWintrustData->dwUIChoice;
  if ( dwUIChoice == 2 )
  {
    if ( a2 )
      return a2;
LABEL_50:
    a1->dwFinalError = -2146762748;
    return a2;
  }
  if ( dwUIChoice == 3 )
  {
    if ( a2 )
      return a2;
  }
  else if ( dwUIChoice == 4 && !a2 )
  {
    goto LABEL_50;
  }
  if ( a1->cbStruct >= 0xE0 && (a1->dwUIStateFlags & 3) == 2 )
    return 0;
  v34 = 0;
  v35 = 0;
  *(_QWORD *)pcbData = 0;
  memset_0(v36, 0, 0x40u);
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(a1, 0, 0, 0);
  CTrustDB::CreateInstance(&IID_IPersonalTrustDB, &v35);
  CTrustDB::CreateInstance(&IID_IPersonalDisallowDB, (void **)pcbData);
  pWintrustData = a1->pWintrustData;
  v36[1] = a1->hWndParent;
  v36[0] = 64;
  OpusInfo = 0;
  v38 = 0;
  memset(v40, 0, sizeof(v40));
  v36[2] = a1;
  v39 = a2;
  FileName = WTHelperGetFileName(pWintrustData);
  v26 = v35;
  v27 = *(_QWORD *)pcbData;
  *(_QWORD *)&v40[4] = v35;
  *(_QWORD *)&v40[12] = *(_QWORD *)pcbData;
  v38 = FileName;
  if ( ProvSignerFromChain )
    OpusInfo = _AllocGetOpusInfo(a1, ProvSignerFromChain, &v34);
  LibraryA = LoadLibraryA("cryptui.dll");
  v29 = LibraryA;
  if ( LibraryA && (ProcAddress = GetProcAddress(LibraryA, "ACUIProviderInvokeUI")) != 0 )
  {
    v31 = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v36);
  }
  else
  {
    padwTrustStepErrors = a1->padwTrustStepErrors;
    v31 = -2146762751;
    a1->dwError = -2146762751;
    padwTrustStepErrors[37] = -2146762751;
  }
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v26 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
  if ( OpusInfo )
    TrustFreeDecode(0x10000, &OpusInfo);
  if ( v29 )
    FreeLibrary(v29);
  return v31;
}

```

## disassembly

```asm
0x180018c30  mov     [rsp-8+arg_10], rbx
0x180018c35  push    rbp
0x180018c36  push    rsi
0x180018c37  push    rdi
0x180018c38  push    r12
0x180018c3a  push    r13
0x180018c3c  push    r14
0x180018c3e  push    r15
0x180018c40  lea     rbp, [rsp-27h]
0x180018c45  sub     rsp, 0B0h
0x180018c4c  mov     rax, cs:__security_cookie
0x180018c53  xor     rax, rsp
0x180018c56  mov     [rbp+57h+var_38], rax
0x180018c5a  test    dword ptr [rcx+0C8h], 100h
0x180018c64  mov     edi, edx
0x180018c66  mov     rbx, rcx
0x180018c69  jnz     loc_180018D4A
0x180018c6f  test    dword ptr [rcx+38h], 40000h
0x180018c76  jnz     loc_180018D4A
0x180018c7c  mov     rax, [rcx+8]
0x180018c80  cmp     dword ptr [rax+18h], 2
0x180018c84  jnz     loc_180018D4A
0x180018c8a  test    edx, edx
0x180018c8c  jnz     loc_180018FA6
0x180018c92  call    ?_CheckTrustedCodeHash@@YAJPEAU_CRYPT_PROVIDER_DATA@@@Z; _CheckTrustedCodeHash(_CRYPT_PROVIDER_DATA *)
0x180018c97  cmp     eax, 1
0x180018c9a  jnz     loc_180018FB7
0x180018ca0  cmp     dword ptr [rbx+78h], 0
0x180018ca4  xorps   xmm0, xmm0
0x180018ca7  movups  xmmword ptr [rbp+57h+pcbData], xmm0
0x180018cab  jbe     loc_180018E35
0x180018cb1  mov     rax, [rbx+80h]
0x180018cb8  test    rax, rax
0x180018cbb  jz      loc_180018E35
0x180018cc1  cmp     dword ptr [rax+0Ch], 0
0x180018cc5  jbe     loc_180018E35
0x180018ccb  mov     rax, [rax+10h]
0x180018ccf  lea     r9, [rbp+57h+pcbData]; pcbData
0x180018cd3  lea     r8, [rbp+57h+pvData]; pvData
0x180018cd7  mov     edx, 0Fh; dwPropId
0x180018cdc  mov     rsi, [rax+8]
0x180018ce0  lea     rax, [rbp+57h+pvData]
0x180018ce4  mov     rcx, rsi; pCertContext
0x180018ce7  mov     qword ptr [rbp+57h+pcbData+8], rax
0x180018ceb  mov     [rbp+57h+pcbData], 14h
0x180018cf2  call    cs:__imp_CertGetCertificateContextProperty
0x180018cf8  xor     r15d, r15d
0x180018cfb  test    eax, eax
0x180018cfd  jnz     loc_180018F27
0x180018d03  cmp     [rbp+57h+pcbData], 14h
0x180018d07  jbe     loc_180018E35
0x180018d0d  mov     ecx, [rbp+57h+pcbData]; Size
0x180018d10  call    cs:__imp_malloc
0x180018d16  mov     qword ptr [rbp+57h+pcbData+8], rax
0x180018d1a  mov     rbx, rax
0x180018d1d  test    rax, rax
0x180018d20  jz      short loc_180018D3F
0x180018d22  lea     r9, [rbp+57h+pcbData]; pcbData
0x180018d26  mov     r8, rax; pvData
0x180018d29  mov     edx, 0Fh; dwPropId
0x180018d2e  mov     rcx, rsi; pCertContext
0x180018d31  call    cs:__imp_CertGetCertificateContextProperty
0x180018d37  test    eax, eax
0x180018d39  jnz     loc_180018F34
0x180018d3f  mov     r14d, 80096001h
0x180018d45  jmp     loc_180018F83
0x180018d4a  call    ?_CheckTrustedCodeHash@@YAJPEAU_CRYPT_PROVIDER_DATA@@@Z; _CheckTrustedCodeHash(_CRYPT_PROVIDER_DATA *)
0x180018d4f  cmp     eax, 1
0x180018d52  jnz     loc_180018FB7
0x180018d58  xor     r15d, r15d
0x180018d5b  xorps   xmm0, xmm0
0x180018d5e  movups  xmmword ptr [rbp+57h+pcbData], xmm0
0x180018d62  cmp     [rbx+78h], r15d
0x180018d66  jbe     loc_180018E10
0x180018d6c  mov     rax, [rbx+80h]
0x180018d73  test    rax, rax
0x180018d76  jz      loc_180018E10
0x180018d7c  cmp     [rax+0Ch], r15d
0x180018d80  jbe     loc_180018E10
0x180018d86  mov     rax, [rax+10h]
0x180018d8a  lea     r9, [rbp+57h+pcbData]; pcbData
0x180018d8e  lea     r8, [rbp+57h+pvData]; pvData
0x180018d92  mov     edx, 0Fh; dwPropId
0x180018d97  mov     r14, [rax+8]
0x180018d9b  lea     rax, [rbp+57h+pvData]
0x180018d9f  mov     rcx, r14; pCertContext
0x180018da2  mov     qword ptr [rbp+57h+pcbData+8], rax
0x180018da6  mov     [rbp+57h+pcbData], 14h
0x180018dad  call    cs:__imp_CertGetCertificateContextProperty
0x180018db3  mov     ecx, [rbp+57h+pcbData]; Size
0x180018db6  test    eax, eax
0x180018db8  jnz     loc_180018E5E
0x180018dbe  cmp     ecx, 14h
0x180018dc1  jbe     loc_180018FEE
0x180018dc7  call    cs:__imp_malloc
0x180018dcd  mov     qword ptr [rbp+57h+pcbData+8], rax
0x180018dd1  mov     rsi, rax
0x180018dd4  test    rax, rax
0x180018dd7  jz      short loc_180018DF2
0x180018dd9  lea     r9, [rbp+57h+pcbData]; pcbData
0x180018ddd  mov     r8, rax; pvData
0x180018de0  mov     edx, 0Fh; dwPropId
0x180018de5  mov     rcx, r14; pCertContext
0x180018de8  call    cs:__imp_CertGetCertificateContextProperty
0x180018dee  test    eax, eax
0x180018df0  jnz     short loc_180018E6A
0x180018df2  mov     r14d, 80096001h
0x180018df8  test    rsi, rsi
0x180018dfb  jz      short loc_180018E06
0x180018dfd  mov     rcx, rsi; Block
0x180018e00  call    cs:__imp_free
0x180018e06  cmp     r14d, 1
0x180018e0a  jnz     loc_18001900A
0x180018e10  test    dword ptr [rbx+38h], 40000h
0x180018e17  jnz     loc_18001901E
0x180018e1d  mov     rax, [rbx+8]
0x180018e21  mov     ecx, [rax+18h]
0x180018e24  cmp     ecx, 2
0x180018e27  jnz     loc_180019030
0x180018e2d  test    edi, edi
0x180018e2f  jz      loc_180018FCE
0x180018e35  mov     eax, edi
0x180018e37  mov     rcx, [rbp+57h+var_38]
0x180018e3b  xor     rcx, rsp; StackCookie
0x180018e3e  call    __security_check_cookie
0x180018e43  mov     rbx, [rsp+0E0h+arg_10]
0x180018e4b  add     rsp, 0B0h
0x180018e52  pop     r15
0x180018e54  pop     r14
0x180018e56  pop     r13
0x180018e58  pop     r12
0x180018e5a  pop     rdi
0x180018e5b  pop     rsi
0x180018e5c  pop     rbp
0x180018e5d  retn
0x180018e5e  mov     rsi, r15
0x180018e61  cmp     ecx, 10h
0x180018e64  jb      loc_180018DBE
0x180018e6a  lea     rcx, pvPara; "Disallowed"
0x180018e71  call    ?_OpenHKCUStore@@YAPEAXPEBG@Z; _OpenHKCUStore(ushort const *)
0x180018e76  mov     r14, rax
0x180018e79  test    rax, rax
0x180018e7c  jz      short loc_180018EB7
0x180018e7e  lea     rax, [rbp+57h+pcbData]
0x180018e82  mov     [rsp+0E0h+pPrevCertContext], r15; pPrevCertContext
0x180018e87  mov     r9d, 0E0000h; dwFindType
0x180018e8d  mov     [rsp+0E0h+pvFindPara], rax; pvFindPara
0x180018e92  xor     r8d, r8d; dwFindFlags
0x180018e95  xor     edx, edx; dwCertEncodingType
0x180018e97  mov     rcx, r14; hCertStore
0x180018e9a  call    cs:__imp_CertFindCertificateInStore
0x180018ea0  xor     edx, edx; dwFlags
0x180018ea2  mov     rcx, r14; hCertStore
0x180018ea5  mov     r12, rax
0x180018ea8  call    cs:__imp_CertCloseStore
0x180018eae  test    r12, r12
0x180018eb1  jnz     loc_180018FF6
0x180018eb7  mov     r14d, 1
0x180018ebd  test    edi, edi
0x180018ebf  jnz     loc_180018DF8
0x180018ec5  lea     rcx, aTrustedpublish; "TrustedPublisher"
0x180018ecc  call    ?_OpenHKCUStore@@YAPEAXPEBG@Z; _OpenHKCUStore(ushort const *)
0x180018ed1  mov     r12, rax
0x180018ed4  test    rax, rax
0x180018ed7  jz      loc_180018DF8
0x180018edd  lea     rax, [rbp+57h+pcbData]
0x180018ee1  mov     [rsp+0E0h+pPrevCertContext], r15; pPrevCertContext
0x180018ee6  mov     r9d, 0E0000h; dwFindType
0x180018eec  mov     [rsp+0E0h+pvFindPara], rax; pvFindPara
0x180018ef1  xor     r8d, r8d; dwFindFlags
0x180018ef4  xor     edx, edx; dwCertEncodingType
0x180018ef6  mov     rcx, r12; hCertStore
0x180018ef9  call    cs:__imp_CertFindCertificateInStore
0x180018eff  xor     edx, edx; dwFlags
0x180018f01  mov     rcx, r12; hCertStore
0x180018f04  mov     r13, rax
0x180018f07  call    cs:__imp_CertCloseStore
0x180018f0d  test    r13, r13
0x180018f10  jz      loc_180018DF8
0x180018f16  mov     rcx, r13; pCertContext
0x180018f19  call    cs:__imp_CertFreeCertificateContext
0x180018f1f  mov     r14d, r15d
0x180018f22  jmp     loc_180018DF8
0x180018f27  cmp     [rbp+57h+pcbData], 10h
0x180018f2b  mov     rbx, r15
0x180018f2e  jb      loc_180018D03
0x180018f34  lea     rcx, pvPara; "Disallowed"
0x180018f3b  mov     r14d, 1
0x180018f41  call    ?_OpenHKCUStore@@YAPEAXPEBG@Z; _OpenHKCUStore(ushort const *)
0x180018f46  mov     rsi, rax
0x180018f49  test    rax, rax
0x180018f4c  jz      short loc_180018F83
0x180018f4e  lea     rax, [rbp+57h+pcbData]
0x180018f52  mov     [rsp+0E0h+pPrevCertContext], r15; pPrevCertContext
0x180018f57  mov     r9d, 0E0000h; dwFindType
0x180018f5d  mov     [rsp+0E0h+pvFindPara], rax; pvFindPara
0x180018f62  xor     r8d, r8d; dwFindFlags
0x180018f65  xor     edx, edx; dwCertEncodingType
0x180018f67  mov     rcx, rsi; hCertStore
0x180018f6a  call    cs:__imp_CertFindCertificateInStore
0x180018f70  xor     edx, edx; dwFlags
0x180018f72  mov     rcx, rsi; hCertStore
0x180018f75  mov     r15, rax
0x180018f78  call    cs:__imp_CertCloseStore
0x180018f7e  test    r15, r15
0x180018f81  jnz     short loc_180018FDD
0x180018f83  test    rbx, rbx
0x180018f86  jz      short loc_180018F91
0x180018f88  mov     rcx, rbx; Block
0x180018f8b  call    cs:__imp_free
0x180018f91  cmp     r14d, 800B0111h
0x180018f98  jnz     loc_180018E35
0x180018f9e  mov     eax, r14d
0x180018fa1  jmp     loc_180018E37
0x180018fa6  cmp     edi, 800B010Ch
0x180018fac  jnz     loc_180018E35
0x180018fb2  jmp     loc_180018C92
0x180018fb7  test    eax, eax
0x180018fb9  jnz     loc_180018E37
0x180018fbf  xor     r15d, r15d
0x180018fc2  mov     [rbx+0CCh], r15d
0x180018fc9  jmp     loc_180018E37
0x180018fce  mov     dword ptr [rbx+0CCh], 800B0004h
0x180018fd8  jmp     loc_180018E35
0x180018fdd  mov     rcx, r15; pCertContext
0x180018fe0  call    cs:__imp_CertFreeCertificateContext
0x180018fe6  mov     r14d, 800B0111h
0x180018fec  jmp     short loc_180018F83
0x180018fee  mov     r14d, 80096001h
0x180018ff4  jmp     short loc_180019016
0x180018ff6  mov     rcx, r12; pCertContext
0x180018ff9  call    cs:__imp_CertFreeCertificateContext
0x180018fff  mov     r14d, 800B0111h
0x180019005  jmp     loc_180018DF8
0x18001900a  test    r14d, r14d
0x18001900d  jnz     short loc_180019016
0x18001900f  mov     [rbx+0CCh], r15d
0x180019016  mov     eax, r14d
0x180019019  jmp     loc_180018E37
0x18001901e  test    edi, edi
0x180019020  jnz     loc_180018E35
0x180019026  mov     eax, 80092026h
0x18001902b  jmp     loc_180018E37
0x180019030  cmp     ecx, 3
0x180019033  jnz     short loc_18001903F
0x180019035  test    edi, edi
0x180019037  jnz     loc_180018E35
0x18001903d  jmp     short loc_180019048
0x18001903f  cmp     ecx, 4
0x180019042  jnz     short loc_180019048
0x180019044  test    edi, edi
0x180019046  jz      short loc_180018FCE
0x180019048  cmp     dword ptr [rbx], 0E0h
0x18001904e  jb      short loc_180019063
0x180019050  mov     eax, [rbx+0DCh]
0x180019056  and     al, 3
0x180019058  cmp     al, 2
0x18001905a  jnz     short loc_180019063
0x18001905c  xor     eax, eax
0x18001905e  jmp     loc_180018E37
0x180019063  xor     edx, edx; Val
0x180019065  mov     [rbp+57h+var_A0], r15d
0x180019069  mov     r8d, 40h ; '@'; Size
0x18001906f  mov     [rbp+57h+var_98], r15
0x180019073  lea     rcx, [rbp+57h+var_90]; void *
0x180019077  mov     qword ptr [rbp+57h+pcbData], r15
0x18001907b  call    memset_0
0x180019080  xor     r9d, r9d; idxCounterSigner
0x180019083  xor     r8d, r8d; fCounterSigner
0x180019086  xor     edx, edx; idxSigner
0x180019088  mov     rcx, rbx; pProvData
0x18001908b  call    WTHelperGetProvSignerFromChain
0x180019090  lea     rdx, [rbp+57h+var_98]; void **
0x180019094  mov     r12, rax
0x180019097  lea     rcx, ?IID_IPersonalTrustDB@@3U_GUID@@B; struct _GUID *
0x18001909e  call    ?CreateInstance@CTrustDB@@SAJAEBU_GUID@@PEAPEAX@Z; CTrustDB::CreateInstance(_GUID const &,void * *)
0x1800190a3  lea     rdx, [rbp+57h+pcbData]; void **
0x1800190a7  lea     rcx, ?IID_IPersonalDisallowDB@@3U_GUID@@B; struct _GUID *
0x1800190ae  call    ?CreateInstance@CTrustDB@@SAJAEBU_GUID@@PEAPEAX@Z; CTrustDB::CreateInstance(_GUID const &,void * *)
0x1800190b3  mov     rax, [rbx+18h]
0x1800190b7  mov     rcx, [rbx+8]
0x1800190bb  mov     [rbp+57h+var_88], rax
0x1800190bf  mov     [rbp+57h+var_90], 40h ; '@'
0x1800190c7  mov     [rbp+57h+var_78], r15
0x1800190cb  mov     [rbp+57h+var_70], r15
0x1800190cf  mov     [rbp+57h+var_64], r15
0x1800190d3  mov     [rbp+57h+var_5C], r15
0x1800190d7  mov     [rbp+57h+var_54], r15d
0x1800190db  mov     [rbp+57h+var_80], rbx
0x1800190df  mov     [rbp+57h+var_68], edi
0x1800190e2  call    WTHelperGetFileName
0x1800190e7  mov     rsi, [rbp+57h+var_98]
0x1800190eb  mov     r14, qword ptr [rbp+57h+pcbData]
0x1800190ef  mov     [rbp+57h+var_64+4], rsi
0x1800190f3  mov     [rbp+57h+var_5C+4], r14
0x1800190f7  mov     [rbp+57h+var_70], rax
0x1800190fb  test    r12, r12
0x1800190fe  jz      short loc_180019113
0x180019100  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x180019104  mov     rdx, r12; struct _CRYPT_PROVIDER_SGNR *
  ... truncated ...
```
