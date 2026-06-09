# SpQueryEndpointBindings(CSslUserContext *,_SecPkgContext_Bindings *)

- ea: `0x180013a00`
- end: `0x180013f8a`
- name: `?SpQueryEndpointBindings@@YAJPEAUCSslUserContext@@PEAU_SecPkgContext_Bindings@@@Z`
- size: `1418`
- prototype: `__int64 __fastcall(struct CSslUserContext *, struct _SecPkgContext_Bindings *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180026d30`

## callees

- `0x180013a00`
- `0x180014240`
- `0x180014270`
- `0x180021da8`
- `0x180021e64`
- `0x180057c8c`
- `0x180088a30`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013c93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013e1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013c93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ecc`
- `CRYPT32!CertOpenStore` at `0x180013aaf`
- `CRYPT32!CertOpenStore` at `0x180013aaf`
- `CRYPT32!CertCloseStore` at `0x180013b29`
- `CRYPT32!CertCloseStore` at `0x180013b29`
- `CRYPT32!CertFreeCertificateContext` at `0x180013c51`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ad89`
- `CRYPT32!CertFreeCertificateContext` at `0x180013c51`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ad89`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180013aca`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180013aca`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180013b07`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180013b07`
- `CRYPT32!CryptHashCertificate2` at `0x180013bd3`
- `CRYPT32!CryptHashCertificate2` at `0x180013c33`
- `CRYPT32!CryptHashCertificate2` at `0x180013bd3`
- `CRYPT32!CryptHashCertificate2` at `0x180013c33`
- `CRYPT32!CryptFindOIDInfo` at `0x180013b59`
- `CRYPT32!CryptFindOIDInfo` at `0x180013b59`

## pseudocode

```c
__int64 __fastcall SpQueryEndpointBindings(struct CSslUserContext *a1, struct _SecPkgContext_Bindings *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  const struct _CERT_CONTEXT *v5; // r15
  BYTE *v6; // r14
  bool v7; // zf
  HCERTSTORE v8; // r12
  const CERT_CONTEXT *v9; // rbp
  const CERT_CONTEXT *v10; // rax
  DWORD v11; // esi
  PCERT_INFO pCertInfo; // rdx
  PCCRYPT_OID_INFO OIDInfo; // rax
  const wchar_t *v14; // rsi
  BYTE *pbComputedHash; // rax
  BYTE *v16; // rbp
  BYTE *v17; // rbp
  unsigned int v18; // esi
  SEC_CHANNEL_BINDINGS *v19; // rax
  SEC_CHANNEL_BINDINGS *Bindings; // rcx
  int v21; // ecx
  DWORD v23; // eax
  unsigned int v24; // eax
  DWORD LastError; // eax
  __int128 v26; // [rsp+40h] [rbp-48h] BYREF
  const struct _CERT_CONTEXT *pvData; // [rsp+90h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+10h] BYREF

  a2->BindingsLength = 0;
  a2->Bindings = 0;
  v3 = *((_DWORD *)a1 + 6);
  if ( (v3 & 0xC) != 0 )
  {
    v11 = -2146893054;
    goto LABEL_41;
  }
  v4 = *((_DWORD *)a1 + 64);
  if ( v4 )
  {
    v6 = (BYTE *)*((_QWORD *)a1 + 31);
    v17 = 0;
    goto LABEL_32;
  }
  pvData = 0;
  v5 = 0;
  v6 = 0;
  v4 = 0;
  if ( (v3 & 0x40051555) != 0 )
    goto LABEL_31;
  if ( !*((_DWORD *)a1 + 3) )
  {
    if ( *((_QWORD *)a1 + 19) )
    {
      v24 = SPLoadCertificate(*((unsigned __int8 **)a1 + 19), *((_DWORD *)a1 + 40), &pvData);
      v5 = pvData;
      v11 = v24;
      goto LABEL_14;
    }
LABEL_31:
    v17 = v6;
LABEL_32:
    if ( !v6 || !v4 )
      goto LABEL_37;
    v18 = v4 + 53;
    if ( v4 + 53 < v4 )
    {
      v11 = -2146893052;
    }
    else
    {
      v19 = (SEC_CHANNEL_BINDINGS *)LocalAlloc(0x40u, v18);
      a2->Bindings = v19;
      if ( v19 )
      {
        v19->cbApplicationDataLength = v4 + 21;
        a2->Bindings->dwApplicationDataOffset = 32;
        Bindings = a2->Bindings;
        qmemcpy(&Bindings[1], "tls-server-end-point:", 21);
        memcpy_0((char *)&Bindings[1].dwAcceptorOffset + 1, v6, v4);
        a2->BindingsLength = v18;
LABEL_37:
        v11 = 0;
        goto LABEL_38;
      }
      v11 = -2146893056;
    }
LABEL_38:
    if ( v17 )
    {
      if ( LsaTable )
        (*(void (__fastcall **)(BYTE *))(LsaTable + 48))(v17);
      else
        LocalFree(v17);
    }
    goto LABEL_41;
  }
  v7 = *((_QWORD *)a1 + 30) == 0;
  if ( !*((_QWORD *)a1 + 30) )
  {
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
    goto LABEL_31;
  }
  v26 = *(_OWORD *)((char *)a1 + 232);
  if ( v7 )
  {
    v11 = -2146893042;
  }
  else
  {
    v8 = CertOpenStore((LPCSTR)6, 1u, 0, 4u, &v26);
    if ( v8 )
    {
      v9 = 0;
      while ( 1 )
      {
        v10 = CertEnumCertificatesInStore(v8, v9);
        v9 = v10;
        if ( !v10 )
          break;
        pcbData = 4;
        LODWORD(pvData) = 0;
        if ( !CertGetCertificateContextProperty(v10, 0xE697u, &pvData, &pcbData) )
        {
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_39e7268a77b0313df132bc71a3d61242_Traceguids,
              LastError);
          }
          CertFreeCertificateContext(v9);
          v11 = -2146892963;
          goto LABEL_13;
        }
        if ( !(_DWORD)pvData )
        {
          v11 = 0;
          v5 = v9;
          goto LABEL_13;
        }
      }
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids);
      v11 = -2146893052;
LABEL_13:
      CertCloseStore(v8, 0);
    }
    else
    {
      v23 = GetLastError();
      if ( v23 == 14 || v23 == 8 )
      {
        v11 = -2146893056;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids, v23);
        v11 = -2146893048;
      }
    }
  }
LABEL_14:
  if ( !v11 )
  {
    pCertInfo = v5->pCertInfo;
    LODWORD(pvData) = 0;
    OIDInfo = CryptFindOIDInfo(1u, pCertInfo->SignatureAlgorithm.pszObjId, 0x40000004u);
    if ( !OIDInfo
      || OIDInfo->dwValue != -1
      || (v14 = *(const wchar_t **)&OIDInfo[1].cbSize) == 0
      || !wcscmp_0(*(const wchar_t **)&OIDInfo[1].cbSize, L"SHA1")
      || !wcscmp_0(v14, L"MD5") )
    {
      v14 = L"SHA256";
    }
    if ( CryptHashCertificate2(v14, 0, 0, v5->pbCertEncoded, v5->cbCertEncoded, 0, (DWORD *)&pvData) )
    {
      if ( LsaTable )
        pbComputedHash = (BYTE *)(*(__int64 (__fastcall **)(_QWORD))(LsaTable + 40))((unsigned int)pvData);
      else
        pbComputedHash = (BYTE *)LocalAlloc(0x40u, (unsigned int)pvData);
      v16 = pbComputedHash;
      if ( pbComputedHash )
      {
        if ( CryptHashCertificate2(v14, 0, 0, v5->pbCertEncoded, v5->cbCertEncoded, pbComputedHash, (DWORD *)&pvData) )
        {
          v4 = (unsigned int)pvData;
          v6 = v16;
          v11 = 0;
        }
        else
        {
          v11 = GetLastError();
          SPExternalFree(v16);
        }
      }
      else
      {
        v11 = -2146893056;
      }
    }
    else
    {
      v11 = GetLastError();
    }
    CertFreeCertificateContext(v5);
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v11);
  if ( !v11 )
    goto LABEL_31;
LABEL_41:
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (v21 = *((_DWORD *)WPP_GLOBAL_Control + 7), (v21 & 1) != 0) && v11 || (v21 & 4) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v11, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180013a00  mov     r11, rsp
0x180013a03  push    rsi
0x180013a04  sub     rsp, 80h
0x180013a0b  mov     [r11-18h], rdi
0x180013a0f  mov     rdi, rdx
0x180013a12  mov     [r11-20h], r12
0x180013a16  lea     r12, WPP_GLOBAL_Control
0x180013a1d  mov     [r11-28h], r13
0x180013a21  xor     r13d, r13d
0x180013a24  mov     [rdx], r13d
0x180013a27  mov     [rdx+8], r13
0x180013a2b  mov     eax, [rcx+18h]
0x180013a2e  test    al, 0Ch
0x180013a30  jnz     loc_180013DFF
0x180013a36  mov     [r11+18h], rbx
0x180013a3a  mov     ebx, [rcx+100h]
0x180013a40  mov     [r11-10h], rbp
0x180013a44  mov     [r11-30h], r14
0x180013a48  mov     [r11-38h], r15
0x180013a4c  test    ebx, ebx
0x180013a4e  jnz     loc_180013D5D
0x180013a54  mov     [r11+8], r13
0x180013a58  mov     r15d, r13d
0x180013a5b  mov     r14d, r13d
0x180013a5e  mov     ebx, r13d
0x180013a61  test    eax, 40051555h
0x180013a66  jnz     loc_180013C75
0x180013a6c  cmp     [rcx+0Ch], ebx
0x180013a6f  jz      loc_180013DA7
0x180013a75  cmp     [rcx+0F0h], rbx
0x180013a7c  jz      loc_180013E31
0x180013a82  movups  xmm0, xmmword ptr [rcx+0E8h]
0x180013a89  movaps  [rsp+88h+var_48], xmm0
0x180013a8e  jz      loc_180013E09
0x180013a94  lea     rax, [r11-48h]
0x180013a98  mov     r9d, 4; dwFlags
0x180013a9e  xor     r8d, r8d; hCryptProv
0x180013aa1  mov     [r11-68h], rax
0x180013aa5  mov     edx, 1; dwEncodingType
0x180013aaa  mov     ecx, 6; lpszStoreProvider
0x180013aaf  call    cs:__imp_CertOpenStore
0x180013ab5  mov     r12, rax
0x180013ab8  test    rax, rax
0x180013abb  jz      loc_180013D6C
0x180013ac1  mov     ebp, r13d
0x180013ac4  mov     rdx, rbp; pPrevCertContext
0x180013ac7  mov     rcx, r12; hCertStore
0x180013aca  call    cs:__imp_CertEnumCertificatesInStore
0x180013ad0  mov     rbp, rax
0x180013ad3  test    rax, rax
0x180013ad6  jz      loc_180013EF7
0x180013adc  lea     r9, [rsp+88h+pcbData]; pcbData
0x180013ae4  mov     [rsp+88h+pcbData], 4
0x180013aef  lea     r8, [rsp+88h+pvData]; pvData
0x180013af7  mov     dword ptr [rsp+88h+pvData], r13d
0x180013aff  mov     edx, 0E697h; dwPropId
0x180013b04  mov     rcx, rax; pCertContext
0x180013b07  call    cs:__imp_CertGetCertificateContextProperty
0x180013b0d  test    eax, eax
0x180013b0f  jz      loc_180013EAB
0x180013b15  cmp     dword ptr [rsp+88h+pvData], ebx
0x180013b1c  jnz     short loc_180013AC4
0x180013b1e  mov     esi, r13d
0x180013b21  mov     r15, rbp
0x180013b24  xor     edx, edx; dwFlags
0x180013b26  mov     rcx, r12; hCertStore
0x180013b29  call    cs:__imp_CertCloseStore
0x180013b2f  lea     r12, WPP_GLOBAL_Control
0x180013b36  test    esi, esi
0x180013b38  jnz     loc_180013C57
0x180013b3e  mov     rdx, [r15+18h]
0x180013b42  mov     r8d, 40000004h; dwGroupId
0x180013b48  mov     dword ptr [rsp+88h+pvData], r13d
0x180013b50  mov     ecx, 1; dwKeyType
0x180013b55  mov     rdx, [rdx+18h]; pvKey
0x180013b59  call    cs:__imp_CryptFindOIDInfo
0x180013b5f  test    rax, rax
0x180013b62  jz      loc_180013DE6
0x180013b68  cmp     dword ptr [rax+1Ch], 0FFFFFFFFh
0x180013b6c  jnz     loc_180013DE6
0x180013b72  mov     rsi, [rax+30h]
0x180013b76  test    rsi, rsi
0x180013b79  jz      loc_180013DE6
0x180013b7f  lea     rdx, aSha1; "SHA1"
0x180013b86  mov     rcx, rsi; String1
0x180013b89  call    wcscmp_0
0x180013b8e  test    eax, eax
0x180013b90  jz      loc_180013DE6
0x180013b96  lea     rdx, aMd5_0; "MD5"
0x180013b9d  mov     rcx, rsi; String1
0x180013ba0  call    wcscmp_0
0x180013ba5  test    eax, eax
0x180013ba7  jz      loc_180013DE6
0x180013bad  mov     r9, [r15+8]; pbEncoded
0x180013bb1  lea     rax, [rsp+88h+pvData]
0x180013bb9  mov     [rsp+88h+pcbComputedHash], rax; pcbComputedHash
0x180013bbe  xor     r8d, r8d; pvReserved
0x180013bc1  mov     eax, [r15+10h]
0x180013bc5  xor     edx, edx; dwFlags
0x180013bc7  mov     [rsp+88h+pbComputedHash], r13; pbComputedHash
0x180013bcc  mov     rcx, rsi; pwszCNGHashAlgid
0x180013bcf  mov     [rsp+88h+cbEncoded], eax; cbEncoded
0x180013bd3  call    cs:__imp_CryptHashCertificate2
0x180013bd9  test    eax, eax
0x180013bdb  jz      loc_180013DF2
0x180013be1  mov     rax, cs:LsaTable
0x180013be8  mov     ecx, dword ptr [rsp+88h+pvData]
0x180013bef  test    rax, rax
0x180013bf2  jz      loc_180013E13
0x180013bf8  mov     rax, [rax+28h]
0x180013bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c01  mov     rbp, rax
0x180013c04  test    rax, rax
0x180013c07  jz      loc_180013DDC
0x180013c0d  mov     r9, [r15+8]; pbEncoded
0x180013c11  lea     rax, [rsp+88h+pvData]
0x180013c19  mov     [rsp+88h+pcbComputedHash], rax; pcbComputedHash
0x180013c1e  xor     r8d, r8d; pvReserved
0x180013c21  mov     eax, [r15+10h]
0x180013c25  xor     edx, edx; dwFlags
0x180013c27  mov     [rsp+88h+pbComputedHash], rbp; pbComputedHash
0x180013c2c  mov     rcx, rsi; pwszCNGHashAlgid
0x180013c2f  mov     [rsp+88h+cbEncoded], eax; cbEncoded
0x180013c33  call    cs:__imp_CryptHashCertificate2
0x180013c39  test    eax, eax
0x180013c3b  jz      loc_180013D92
0x180013c41  mov     ebx, dword ptr [rsp+88h+pvData]
0x180013c48  mov     r14, rbp
0x180013c4b  mov     esi, r13d
0x180013c4e  mov     rcx, r15; pCertContext
0x180013c51  call    cs:__imp_CertFreeCertificateContext
0x180013c57  mov     rax, cs:WPP_GLOBAL_Control
0x180013c5e  cmp     rax, r12
0x180013c61  jz      short loc_180013C6D
0x180013c63  test    byte ptr [rax+1Ch], 4
0x180013c67  jnz     loc_180013F33
0x180013c6d  test    esi, esi
0x180013c6f  jnz     loc_180013D0B
0x180013c75  mov     rbp, r14
0x180013c78  test    r14, r14
0x180013c7b  jz      short loc_180013CE7
0x180013c7d  test    ebx, ebx
0x180013c7f  jz      short loc_180013CE7
0x180013c81  lea     esi, [rbx+35h]
0x180013c84  cmp     esi, ebx
0x180013c86  jb      loc_180013F50
0x180013c8c  mov     edx, esi; uBytes
0x180013c8e  mov     ecx, 40h ; '@'; uFlags
0x180013c93  call    cs:__imp_LocalAlloc
0x180013c99  mov     [rdi+8], rax
0x180013c9d  mov     rcx, rax
0x180013ca0  test    rax, rax
0x180013ca3  jz      loc_180013D88
0x180013ca9  lea     eax, [rbx+15h]
0x180013cac  mov     r8d, ebx; Size
0x180013caf  mov     [rcx+18h], eax
0x180013cb2  mov     rdx, r14; Src
0x180013cb5  mov     rax, [rdi+8]
0x180013cb9  mov     dword ptr [rax+1Ch], 20h ; ' '
0x180013cc0  mov     rcx, [rdi+8]
0x180013cc4  movups  xmm0, xmmword ptr cs:aTlsServerEndPo; "tls-server-end-point:"
0x180013ccb  movups  xmmword ptr [rcx+20h], xmm0
0x180013ccf  movsd   xmm1, qword ptr cs:aTlsServerEndPo+0Dh; "d-point:"
0x180013cd7  movsd   qword ptr [rcx+2Dh], xmm1
0x180013cdc  add     rcx, 35h ; '5'; void *
0x180013ce0  call    memcpy_0
0x180013ce5  mov     [rdi], esi
0x180013ce7  mov     esi, r13d
0x180013cea  test    rbp, rbp
0x180013ced  jz      short loc_180013D0B
0x180013cef  mov     rax, cs:LsaTable
0x180013cf6  mov     rcx, rbp; hMem
0x180013cf9  test    rax, rax
0x180013cfc  jz      loc_180013E26
0x180013d02  mov     rax, [rax+30h]
0x180013d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d0b  mov     r14, [rsp+88h+var_30]
0x180013d10  mov     rbp, [rsp+88h+var_10]
0x180013d15  mov     rbx, [rsp+88h+arg_10]
0x180013d1d  mov     r15, [rsp+88h+var_38]
0x180013d22  mov     rax, cs:WPP_GLOBAL_Control
0x180013d29  mov     r13, [rsp+88h+var_28]
0x180013d2e  cmp     rax, r12
0x180013d31  mov     r12, [rsp+88h+var_20]
0x180013d36  mov     rdi, [rsp+88h+var_18]
0x180013d3b  jz      short loc_180013D52
0x180013d3d  mov     ecx, [rax+1Ch]
0x180013d40  test    cl, 1
0x180013d43  jnz     loc_180013F5A
0x180013d49  test    cl, 4
0x180013d4c  jnz     loc_180013F62
0x180013d52  mov     eax, esi
0x180013d54  add     rsp, 80h
0x180013d5b  pop     rsi
0x180013d5c  retn
0x180013d5d  mov     r14, [rcx+0F8h]
0x180013d64  mov     rbp, r13
0x180013d67  jmp     loc_180013C78
0x180013d6c  call    cs:__imp_GetLastError
0x180013d72  mov     r9d, eax
0x180013d75  cmp     eax, 0Eh
0x180013d78  jnz     loc_180013E65
0x180013d7e  mov     esi, 80090300h
0x180013d83  jmp     loc_180013B2F
0x180013d88  mov     esi, 80090300h
0x180013d8d  jmp     loc_180013CEA
0x180013d92  call    cs:__imp_GetLastError
0x180013d98  mov     rcx, rbp; void *
0x180013d9b  mov     esi, eax
0x180013d9d  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180013da2  jmp     loc_180013C4E
0x180013da7  mov     rax, [rcx+98h]
0x180013dae  test    rax, rax
0x180013db1  jz      loc_180013C75
0x180013db7  mov     edx, [rcx+0A0h]; unsigned int
0x180013dbd  lea     r8, [rsp+88h+pvData]; struct _CERT_CONTEXT **
0x180013dc5  mov     rcx, rax; unsigned __int8 *
0x180013dc8  call    ?SPLoadCertificate@@YAKPEAEKPEAPEBU_CERT_CONTEXT@@@Z; SPLoadCertificate(uchar *,ulong,_CERT_CONTEXT const * *)
0x180013dcd  mov     r15, [rsp+88h+pvData]
0x180013dd5  mov     esi, eax
0x180013dd7  jmp     loc_180013B36
0x180013ddc  mov     esi, 80090300h
0x180013de1  jmp     loc_180013C4E
0x180013de6  lea     rsi, aSha256_0; "SHA256"
0x180013ded  jmp     loc_180013BAD
0x180013df2  call    cs:__imp_GetLastError
0x180013df8  mov     esi, eax
0x180013dfa  jmp     loc_180013C4E
0x180013dff  mov     esi, 80090302h
0x180013e04  jmp     loc_180013D22
0x180013e09  mov     esi, 8009030Eh
0x180013e0e  jmp     loc_180013B36
0x180013e13  mov     rdx, rcx; uBytes
0x180013e16  mov     ecx, 40h ; '@'; uFlags
0x180013e1b  call    cs:__imp_LocalAlloc
0x180013e21  jmp     loc_180013C01
0x180013e26  call    cs:__imp_LocalFree
0x180013e2c  jmp     loc_180013D0B
0x180013e31  mov     rax, cs:WPP_GLOBAL_Control
0x180013e38  cmp     rax, r12
0x180013e3b  jz      loc_180013C75
0x180013e41  test    byte ptr [rax+1Ch], 4
0x180013e45  jz      loc_180013C75
0x180013e4b  mov     rcx, [rax+10h]
0x180013e4f  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180013e56  mov     edx, 67h ; 'g'
0x180013e5b  call    WPP_SF_
0x180013e60  jmp     loc_180013C75
0x180013e65  cmp     r9d, 8
0x180013e69  jz      loc_180013D7E
0x180013e6f  mov     rax, cs:WPP_GLOBAL_Control
0x180013e76  lea     r12, WPP_GLOBAL_Control
0x180013e7d  cmp     rax, r12
0x180013e80  jz      loc_18008AD7C
0x180013e86  test    byte ptr [rax+1Ch], 1
0x180013e8a  jz      loc_18008AD7C
0x180013e90  mov     rcx, [rax+10h]
0x180013e94  lea     r8, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids
0x180013e9b  mov     edx, 0Dh
0x180013ea0  call    WPP_SF_d
0x180013ea5  nop
0x180013ea6  jmp     loc_18008AD7C
0x180013eab  mov     rax, cs:WPP_GLOBAL_Control
0x180013eb2  lea     rdx, WPP_GLOBAL_Control
0x180013eb9  cmp     rax, rdx
0x180013ebc  jz      loc_18008AD86
0x180013ec2  test    byte ptr [rax+1Ch], 1
0x180013ec6  jz      loc_18008AD86
0x180013ecc  call    cs:__imp_GetLastError
0x180013ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ed9  lea     r8, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids
0x180013ee0  mov     edx, 0Eh
0x180013ee5  mov     r9d, eax
0x180013ee8  mov     rcx, [rcx+10h]
0x180013eec  call    WPP_SF_d
0x180013ef1  nop
0x180013ef2  jmp     loc_18008AD86
0x180013ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x180013efe  lea     rdx, WPP_GLOBAL_Control
0x180013f05  cmp     rcx, rdx
0x180013f08  jz      loc_18008AD99
0x180013f0e  test    byte ptr [rcx+1Ch], 1
0x180013f12  jz      loc_18008AD99
0x180013f18  mov     rcx, [rcx+10h]
0x180013f1c  lea     r8, WPP_39e7268a77b0313df132bc71a3d61242_Traceguids
0x180013f23  mov     edx, 0Fh
0x180013f28  call    WPP_SF_
0x180013f2d  nop
0x180013f2e  jmp     loc_18008AD99
0x180013f33  mov     rcx, [rax+10h]
0x180013f37  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180013f3e  mov     edx, 68h ; 'h'
0x180013f43  mov     r9d, esi
0x180013f46  call    WPP_SF_d
0x180013f4b  jmp     loc_180013C6D
0x180013f50  mov     esi, 80090304h
0x180013f55  jmp     loc_180013CEA
0x180013f5a  test    esi, esi
0x180013f5c  jz      loc_180013D49
0x180013f62  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
