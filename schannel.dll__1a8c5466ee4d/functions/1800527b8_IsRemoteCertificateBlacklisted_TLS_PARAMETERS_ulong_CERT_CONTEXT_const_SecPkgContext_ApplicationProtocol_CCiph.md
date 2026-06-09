# IsRemoteCertificateBlacklisted(_TLS_PARAMETERS *,ulong,_CERT_CONTEXT const *,_SecPkgContext_ApplicationProtocol *,CCipherSuiteInfo *,uchar,uchar)

- ea: `0x1800527b8`
- end: `0x180052c0a`
- name: `?IsRemoteCertificateBlacklisted@@YAJPEAU_TLS_PARAMETERS@@KPEBU_CERT_CONTEXT@@PEAU_SecPkgContext_ApplicationProtocol@@PEAVCCipherSuiteInfo@@EE@Z`
- size: `1106`
- prototype: `__int64 __usercall@<rax>(struct _TLS_PARAMETERS *@<rcx>, unsigned int@<edx>, PCCERT_CONTEXT pCertContext@<r8>, struct _SecPkgContext_ApplicationProtocol *@<r9>, struct CCipherSuiteInfo *, unsigned __int8, unsigned __int8)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180022aa0`
- `0x18003c190`
- `0x18007e8e8`

## callees

- `0x18000e200`
- `0x18000e250`
- `0x18000e510`
- `0x180021da8`
- `0x18002ebc0`
- `0x1800403f0`
- `0x180041d90`
- `0x18004395c`
- `0x1800527b8`
- `0x1800532f8`
- `0x1800597b0`
- `0x18005a160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529f8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800529eb`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800529eb`
- `CRYPT32!CertGetPublicKeyLength` at `0x1800528b0`
- `CRYPT32!CertGetPublicKeyLength` at `0x1800528b0`

## pseudocode

```c
__int64 __fastcall IsRemoteCertificateBlacklisted(
        struct _TLS_PARAMETERS *a1,
        unsigned int a2,
        PCCERT_CONTEXT pCertContext,
        struct _SecPkgContext_ApplicationProtocol *a4,
        struct CCipherSuiteInfo *a5,
        unsigned __int8 a6)
{
  char v10; // bl
  struct _UNICODE_STRING *v11; // r13
  ULONG v12; // eax
  __int64 v13; // r9
  DWORD PublicKeyLength; // r15d
  PCERT_INFO pCertInfo; // rax
  unsigned int v16; // edi
  CCipherMill *v17; // rcx
  __int64 v18; // rdx
  const char **p_pszObjId; // rax
  enum _eTlsSignatureAlgorithm v20; // edi
  unsigned int EccCurveType; // eax
  CCipherMill *v23; // rcx
  unsigned int CurveInfo; // eax
  DWORD LastError; // eax
  DWORD v26; // r8d
  DWORD v27; // edx
  DWORD v28; // r8d
  unsigned __int8 v29; // al
  int v30; // [rsp+28h] [rbp-D8h]
  int v31; // [rsp+38h] [rbp-C8h]
  int v32; // [rsp+38h] [rbp-C8h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  struct CEccCurveInfo *v34; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 pvData[64]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v37[64]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v38[512]; // [rsp+160h] [rbp+60h] BYREF

  pcbData = 0;
  v34 = 0;
  memset_0(v37, 0, sizeof(v37));
  memset_0(pvData, 0, sizeof(pvData));
  memset_0(v38, 0, sizeof(v38));
  *(_QWORD *)&v35.Length = 0x2000000;
  v35.Buffer = (PWSTR)v38;
  if ( !a1 || !a2 || !pCertContext || !a5 || !pCertContext->pCertInfo )
    return 2148074244LL;
  v10 = 1;
  v11 = 0;
  if ( a4 && *(_QWORD *)&a4->ProtoNegoStatus == 0x200000001LL )
  {
    v12 = CreateUnicodeStringFromAlpnId((CHAR *)a4->ProtocolId, a4->ProtocolIdSize, &v35);
    v13 = v12;
    if ( v12 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 2148074244LL;
      v18 = 16;
      goto LABEL_65;
    }
    v11 = &v35;
  }
  PublicKeyLength = CertGetPublicKeyLength(1u, &pCertContext->pCertInfo->SubjectPublicKeyInfo);
  pCertInfo = pCertContext->pCertInfo;
  if ( !pCertInfo
    || (p_pszObjId = (const char **)&pCertInfo->SubjectPublicKeyInfo.Algorithm.pszObjId) == 0
    || !*p_pszObjId )
  {
    v16 = -2146893052;
LABEL_19:
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_89c254830434370c9b8c7f7d2950a963_Traceguids, v16);
    return v16;
  }
  v20 = MapOidToSignatureAlgorithm(*p_pszObjId);
  if ( v20 == TlsSignatureAlgorithm_Anonymous )
  {
    v16 = -2146893043;
    goto LABEL_19;
  }
  if ( !PublicKeyLength )
    return 2148074244LL;
  if ( v20 == TlsSignatureAlgorithm_Ecdsa )
  {
    EccCurveType = CertGetEccCurveType(pCertContext, &pcbData);
    v13 = EccCurveType;
    if ( EccCurveType )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 2148074244LL;
      v18 = 18;
      goto LABEL_65;
    }
    CurveInfo = CCipherMill::GetCurveInfo(v23, pcbData, &v34);
    v13 = CurveInfo;
    if ( CurveInfo )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 2148074244LL;
      v18 = 19;
      goto LABEL_65;
    }
  }
  pcbData = 128;
  if ( !CertGetCertificateContextProperty(pCertContext, 0x59u, pvData, &pcbData) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( !LastError )
      goto LABEL_45;
LABEL_62:
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 2148074244LL;
    v18 = 20;
LABEL_65:
    WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_89c254830434370c9b8c7f7d2950a963_Traceguids, v13);
    return 2148074244LL;
  }
  v26 = 0;
  v27 = pcbData >> 1;
  pvData[(pcbData >> 1) - 1] = 0;
  while ( 1 )
  {
    if ( v26 >= v27 )
    {
      if ( v26 != v27 )
        goto LABEL_42;
      goto LABEL_61;
    }
    if ( pvData[v26] == 47 )
      break;
    ++v26;
  }
  pvData[v26] = 0;
LABEL_42:
  v28 = v26 + 1;
  if ( v28 == v27 || v27 - v28 < 0x40 && (unsigned int)StringCchCopyW(v37, 0x40u, &pvData[v28]) )
  {
LABEL_61:
    v13 = 1359;
    goto LABEL_62;
  }
LABEL_45:
  if ( a6 || v20 != TlsSignatureAlgorithm_Rsa )
  {
    switch ( v20 )
    {
      case TlsSignatureAlgorithm_Ecdsa:
        if ( v34 )
        {
          v29 = IsEcdsaAlgorithmBlacklisted(
                  a1,
                  a2,
                  (const unsigned __int16 *)v34,
                  *((_DWORD *)v34 + 193),
                  PublicKeyLength,
                  v11,
                  1);
          goto LABEL_53;
        }
        break;
      case TlsSignatureAlgorithm_Dsa:
        v29 = IsCngAlgorithmBlacklisted(a1, a2, 1, L"DSA", 0, PublicKeyLength, v11, 1);
        goto LABEL_53;
      case TlsSignatureAlgorithm_Rsa:
        goto LABEL_60;
    }
LABEL_54:
    LOBYTE(v31) = 1;
    if ( !(unsigned __int8)IsCngAlgorithmBlacklisted(a1, a2, 4, v37, 0, 0, 0, v31) )
    {
      LOBYTE(v32) = 1;
      v10 = IsCngAlgorithmBlacklisted(a1, a2, 4, pvData, 0, 0, 0, v32);
    }
  }
  else if ( *((_DWORD *)a5 + 8) != 41984
         || !(unsigned __int8)IsRsaAlgorithmBlacklisted(a1, a2, 0, PublicKeyLength, v11, 1) )
  {
LABEL_60:
    LOBYTE(v30) = 1;
    v29 = IsRsaAlgorithmBlacklisted(a1, a2, 1, PublicKeyLength, v11, v30);
LABEL_53:
    if ( !v29 )
      goto LABEL_54;
  }
  return v10 != 0 ? 0x80090331 : 0;
}

```

## disassembly

```asm
0x1800527b8  push    rbp
0x1800527ba  push    rbx
0x1800527bb  push    rsi
0x1800527bc  push    rdi
0x1800527bd  push    r12
0x1800527bf  push    r13
0x1800527c1  push    r14
0x1800527c3  push    r15
0x1800527c5  lea     rbp, [rsp-278h]
0x1800527cd  sub     rsp, 378h
0x1800527d4  mov     rax, cs:__security_cookie
0x1800527db  xor     rax, rsp
0x1800527de  mov     [rbp+2B0h+var_50], rax
0x1800527e5  mov     r14, r8
0x1800527e8  mov     esi, edx
0x1800527ea  mov     r12, rcx
0x1800527ed  xor     r15d, r15d
0x1800527f0  mov     ebx, 80h
0x1800527f5  mov     [rsp+3B0h+pcbData], r15d
0x1800527fa  mov     r8d, ebx; Size
0x1800527fd  mov     [rsp+3B0h+var_368], r15
0x180052802  xor     edx, edx; Val
0x180052804  lea     rcx, [rbp+2B0h+var_2D0]; void *
0x180052808  mov     rdi, r9
0x18005280b  call    memset_0
0x180052810  mov     r8d, ebx; Size
0x180052813  lea     rcx, [rsp+3B0h+pvData]; void *
0x180052818  xor     edx, edx; Val
0x18005281a  call    memset_0
0x18005281f  xor     edx, edx; Val
0x180052821  lea     rcx, [rbp+2B0h+var_250]; void *
0x180052825  mov     r8d, 200h; Size
0x18005282b  call    memset_0
0x180052830  mov     qword ptr [rsp+3B0h+var_360.Length], 2000000h
0x180052839  lea     rax, [rbp+2B0h+var_250]
0x18005283d  mov     [rsp+3B0h+var_360.Buffer], rax
0x180052842  test    r12, r12
0x180052845  jz      loc_180052BE2
0x18005284b  test    esi, esi
0x18005284d  jz      loc_180052BE2
0x180052853  test    r14, r14
0x180052856  jz      loc_180052BE2
0x18005285c  cmp     [rbp+2B0h+arg_20], r15
0x180052863  jz      loc_180052BE2
0x180052869  cmp     [r14+18h], r15
0x18005286d  jz      loc_180052BE2
0x180052873  lea     ebx, [r15+1]
0x180052877  mov     r13d, r15d
0x18005287a  test    rdi, rdi
0x18005287d  jz      short loc_1800528A6
0x18005287f  cmp     [rdi], ebx
0x180052881  jnz     short loc_1800528A6
0x180052883  cmp     dword ptr [rdi+4], 2
0x180052887  jnz     short loc_1800528A6
0x180052889  mov     dl, [rdi+8]; unsigned __int8
0x18005288c  lea     rcx, [rdi+9]; unsigned __int8 *
0x180052890  lea     r8, [rsp+3B0h+var_360]; struct _UNICODE_STRING *
0x180052895  call    ?CreateUnicodeStringFromAlpnId@@YAKPEAEEPEAU_UNICODE_STRING@@@Z; CreateUnicodeStringFromAlpnId(uchar *,uchar,_UNICODE_STRING *)
0x18005289a  mov     r9d, eax
0x18005289d  test    eax, eax
0x18005289f  jnz     short loc_1800528C9
0x1800528a1  lea     r13, [rsp+3B0h+var_360]
0x1800528a6  mov     rdx, [r14+18h]
0x1800528aa  mov     ecx, ebx; dwCertEncodingType
0x1800528ac  add     rdx, 60h ; '`'; pPublicKey
0x1800528b0  call    cs:__imp_CertGetPublicKeyLength
0x1800528b6  mov     r15d, eax
0x1800528b9  mov     rax, [r14+18h]
0x1800528bd  test    rax, rax
0x1800528c0  jnz     short loc_1800528F3
0x1800528c2  mov     edi, 80090304h
0x1800528c7  jmp     short loc_180052911
0x1800528c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800528d0  lea     rax, WPP_GLOBAL_Control
0x1800528d7  cmp     rcx, rax
0x1800528da  jz      loc_180052BE2
0x1800528e0  test    [rcx+1Ch], bl
0x1800528e3  jz      loc_180052BE2
0x1800528e9  mov     edx, 10h
0x1800528ee  jmp     loc_180052BD2
0x1800528f3  add     rax, 60h ; '`'
0x1800528f7  jz      short loc_1800528C2
0x1800528f9  mov     rcx, [rax]; char *
0x1800528fc  test    rcx, rcx
0x1800528ff  jz      short loc_1800528C2
0x180052901  call    ?MapOidToSignatureAlgorithm@@YA?AW4_eTlsSignatureAlgorithm@@PEBD@Z; MapOidToSignatureAlgorithm(char const *)
0x180052906  mov     edi, eax
0x180052908  test    eax, eax
0x18005290a  jnz     short loc_180052948
0x18005290c  mov     edi, 8009030Dh
0x180052911  mov     rcx, cs:WPP_GLOBAL_Control
0x180052918  lea     rax, WPP_GLOBAL_Control
0x18005291f  cmp     rcx, rax
0x180052922  jz      short loc_180052941
0x180052924  test    [rcx+1Ch], bl
0x180052927  jz      short loc_180052941
0x180052929  mov     rcx, [rcx+10h]
0x18005292d  lea     r8, WPP_89c254830434370c9b8c7f7d2950a963_Traceguids
0x180052934  mov     edx, 11h
0x180052939  mov     r9d, edi
0x18005293c  call    WPP_SF_d
0x180052941  mov     eax, edi
0x180052943  jmp     loc_180052BE7
0x180052948  test    r15d, r15d
0x18005294b  jz      loc_180052BE2
0x180052951  cmp     edi, 3
0x180052954  jnz     short loc_1800529D1
0x180052956  lea     rdx, [rsp+3B0h+pcbData]
0x18005295b  mov     rcx, r14
0x18005295e  call    CertGetEccCurveType
0x180052963  mov     r9d, eax
0x180052966  test    eax, eax
0x180052968  jz      short loc_180052992
0x18005296a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052971  lea     rax, WPP_GLOBAL_Control
0x180052978  cmp     rcx, rax
0x18005297b  jz      loc_180052BE2
0x180052981  test    [rcx+1Ch], bl
0x180052984  jz      loc_180052BE2
0x18005298a  lea     edx, [rdi+0Fh]
0x18005298d  jmp     loc_180052BD2
0x180052992  mov     edx, [rsp+3B0h+pcbData]; unsigned int
0x180052996  lea     r8, [rsp+3B0h+var_368]; struct CEccCurveInfo **
0x18005299b  call    ?GetCurveInfo@CCipherMill@@QEAAKKPEAPEAVCEccCurveInfo@@@Z; CCipherMill::GetCurveInfo(ulong,CEccCurveInfo * *)
0x1800529a0  mov     r9d, eax
0x1800529a3  test    eax, eax
0x1800529a5  jz      short loc_1800529D1
0x1800529a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800529ae  lea     rax, WPP_GLOBAL_Control
0x1800529b5  cmp     rcx, rax
0x1800529b8  jz      loc_180052BE2
0x1800529be  test    [rcx+1Ch], bl
0x1800529c1  jz      loc_180052BE2
0x1800529c7  mov     edx, 13h
0x1800529cc  jmp     loc_180052BD2
0x1800529d1  lea     r9, [rsp+3B0h+pcbData]; pcbData
0x1800529d6  mov     [rsp+3B0h+pcbData], 80h
0x1800529de  lea     r8, [rsp+3B0h+pvData]; pvData
0x1800529e3  mov     edx, 59h ; 'Y'; dwPropId
0x1800529e8  mov     rcx, r14; pCertContext
0x1800529eb  call    cs:__imp_CertGetCertificateContextProperty
0x1800529f1  xor     r14d, r14d
0x1800529f4  test    eax, eax
0x1800529f6  jnz     short loc_180052A0B
0x1800529f8  call    cs:__imp_GetLastError
0x1800529fe  mov     r9d, eax
0x180052a01  test    eax, eax
0x180052a03  jnz     loc_180052BB5
0x180052a09  jmp     short loc_180052A76
0x180052a0b  mov     edx, [rsp+3B0h+pcbData]
0x180052a0f  mov     r8d, r14d
0x180052a12  shr     edx, 1
0x180052a14  lea     eax, [rdx-1]
0x180052a17  mov     [rsp+rax*2+3B0h+pvData], r14w
0x180052a1d  cmp     r8d, edx
0x180052a20  jnb     short loc_180052A3A
0x180052a22  mov     ecx, r8d
0x180052a25  cmp     [rsp+rcx*2+3B0h+pvData], 2Fh ; '/'
0x180052a2b  jz      short loc_180052A32
0x180052a2d  add     r8d, ebx
0x180052a30  jmp     short loc_180052A1D
0x180052a32  mov     [rsp+rcx*2+3B0h+pvData], r14w
0x180052a38  jmp     short loc_180052A40
0x180052a3a  jz      loc_180052BAF
0x180052a40  inc     r8d
0x180052a43  cmp     r8d, edx
0x180052a46  jz      loc_180052BAF
0x180052a4c  sub     edx, r8d
0x180052a4f  cmp     edx, 40h ; '@'
0x180052a52  jnb     short loc_180052A76
0x180052a54  mov     eax, r8d
0x180052a57  lea     rcx, [rbp+2B0h+var_2D0]; unsigned __int16 *
0x180052a5b  lea     r8, [rsp+3B0h+pvData]
0x180052a60  mov     edx, 40h ; '@'; unsigned __int64
0x180052a65  lea     r8, [r8+rax*2]; unsigned __int16 *
0x180052a69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052a6e  test    eax, eax
0x180052a70  jnz     loc_180052BAF
0x180052a76  cmp     [rbp+2B0h+arg_28], r14b
0x180052a7d  jnz     short loc_180052ABD
0x180052a7f  cmp     edi, ebx
0x180052a81  jnz     short loc_180052ABD
0x180052a83  mov     rax, [rbp+2B0h+arg_20]
0x180052a8a  cmp     dword ptr [rax+20h], 0A400h
0x180052a91  jnz     loc_180052B91
0x180052a97  mov     byte ptr [rsp+3B0h+var_388], bl
0x180052a9b  mov     r9d, r15d
0x180052a9e  xor     r8d, r8d
0x180052aa1  mov     qword ptr [rsp+3B0h+var_390], r13
0x180052aa6  mov     edx, esi
0x180052aa8  mov     rcx, r12
0x180052aab  call    ?IsRsaAlgorithmBlacklisted@@YAEPEAU_TLS_PARAMETERS@@KW4_eTlsAlgorithmUsage@@KPEAU_UNICODE_STRING@@E@Z; IsRsaAlgorithmBlacklisted(_TLS_PARAMETERS *,ulong,_eTlsAlgorithmUsage,ulong,_UNICODE_STRING *,uchar)
0x180052ab0  test    al, al
0x180052ab2  jnz     loc_180052B4A
0x180052ab8  jmp     loc_180052B91
0x180052abd  cmp     edi, 3
0x180052ac0  jnz     loc_180052B58
0x180052ac6  mov     rax, [rsp+3B0h+var_368]
0x180052acb  test    rax, rax
0x180052ace  jz      short loc_180052AF6
0x180052ad0  mov     r9d, [rax+304h]; unsigned int
0x180052ad7  mov     r8, rax; unsigned __int16 *
0x180052ada  mov     [rsp+3B0h+var_380], bl; char
0x180052ade  mov     edx, esi; unsigned int
0x180052ae0  mov     [rsp+3B0h+var_388], r13; struct _UNICODE_STRING *
0x180052ae5  mov     rcx, r12; struct _TLS_PARAMETERS *
0x180052ae8  mov     [rsp+3B0h+var_390], r15d; unsigned int
0x180052aed  call    ?IsEcdsaAlgorithmBlacklisted@@YAEPEAU_TLS_PARAMETERS@@KPEBGKKPEAU_UNICODE_STRING@@E@Z; IsEcdsaAlgorithmBlacklisted(_TLS_PARAMETERS *,ulong,ushort const *,ulong,ulong,_UNICODE_STRING *,uchar)
0x180052af2  test    al, al
0x180052af4  jnz     short loc_180052B4A
0x180052af6  mov     [rsp+3B0h+var_378], bl
0x180052afa  lea     r9, [rbp+2B0h+var_2D0]
0x180052afe  mov     qword ptr [rsp+3B0h+var_380], r14
0x180052b03  mov     edi, 4
0x180052b08  mov     dword ptr [rsp+3B0h+var_388], r14d
0x180052b0d  mov     r8d, edi
0x180052b10  mov     edx, esi
0x180052b12  mov     qword ptr [rsp+3B0h+var_390], r14
0x180052b17  mov     rcx, r12
0x180052b1a  call    ?IsCngAlgorithmBlacklisted@@YAEPEAU_TLS_PARAMETERS@@KW4_eTlsAlgorithmUsage@@PEBG2KPEAU_UNICODE_STRING@@E@Z; IsCngAlgorithmBlacklisted(_TLS_PARAMETERS *,ulong,_eTlsAlgorithmUsage,ushort const *,ushort const *,ulong,_UNICODE_STRING *,uchar)
0x180052b1f  test    al, al
0x180052b21  jnz     short loc_180052B4A
0x180052b23  mov     [rsp+3B0h+var_378], bl
0x180052b27  lea     r9, [rsp+3B0h+pvData]
0x180052b2c  mov     qword ptr [rsp+3B0h+var_380], r14
0x180052b31  mov     r8d, edi
0x180052b34  mov     dword ptr [rsp+3B0h+var_388], r14d
0x180052b39  mov     edx, esi
0x180052b3b  mov     rcx, r12
0x180052b3e  mov     qword ptr [rsp+3B0h+var_390], r14
0x180052b43  call    ?IsCngAlgorithmBlacklisted@@YAEPEAU_TLS_PARAMETERS@@KW4_eTlsAlgorithmUsage@@PEBG2KPEAU_UNICODE_STRING@@E@Z; IsCngAlgorithmBlacklisted(_TLS_PARAMETERS *,ulong,_eTlsAlgorithmUsage,ushort const *,ushort const *,ulong,_UNICODE_STRING *,uchar)
0x180052b48  mov     bl, al
0x180052b4a  neg     bl
0x180052b4c  sbb     eax, eax
0x180052b4e  and     eax, 80090331h
0x180052b53  jmp     loc_180052BE7
0x180052b58  cmp     edi, 2
0x180052b5b  jnz     short loc_180052B89
0x180052b5d  mov     [rsp+3B0h+var_378], bl
0x180052b61  lea     r9, aDsa; "DSA"
0x180052b68  mov     qword ptr [rsp+3B0h+var_380], r13
0x180052b6d  mov     r8d, ebx
0x180052b70  mov     dword ptr [rsp+3B0h+var_388], r15d
0x180052b75  mov     edx, esi
0x180052b77  mov     rcx, r12
0x180052b7a  mov     qword ptr [rsp+3B0h+var_390], r14
0x180052b7f  call    ?IsCngAlgorithmBlacklisted@@YAEPEAU_TLS_PARAMETERS@@KW4_eTlsAlgorithmUsage@@PEBG2KPEAU_UNICODE_STRING@@E@Z; IsCngAlgorithmBlacklisted(_TLS_PARAMETERS *,ulong,_eTlsAlgorithmUsage,ushort const *,ushort const *,ulong,_UNICODE_STRING *,uchar)
0x180052b84  jmp     loc_180052AF2
0x180052b89  cmp     edi, ebx
0x180052b8b  jnz     loc_180052AF6
0x180052b91  mov     byte ptr [rsp+3B0h+var_388], bl
0x180052b95  mov     r9d, r15d
0x180052b98  mov     r8d, ebx
0x180052b9b  mov     qword ptr [rsp+3B0h+var_390], r13
0x180052ba0  mov     edx, esi
0x180052ba2  mov     rcx, r12
0x180052ba5  call    ?IsRsaAlgorithmBlacklisted@@YAEPEAU_TLS_PARAMETERS@@KW4_eTlsAlgorithmUsage@@KPEAU_UNICODE_STRING@@E@Z; IsRsaAlgorithmBlacklisted(_TLS_PARAMETERS *,ulong,_eTlsAlgorithmUsage,ulong,_UNICODE_STRING *,uchar)
0x180052baa  jmp     loc_180052AF2
0x180052baf  mov     r9d, 54Fh
0x180052bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180052bbc  lea     rax, WPP_GLOBAL_Control
0x180052bc3  cmp     rcx, rax
0x180052bc6  jz      short loc_180052BE2
0x180052bc8  test    [rcx+1Ch], bl
0x180052bcb  jz      short loc_180052BE2
0x180052bcd  mov     edx, 14h
0x180052bd2  mov     rcx, [rcx+10h]
0x180052bd6  lea     r8, WPP_89c254830434370c9b8c7f7d2950a963_Traceguids
0x180052bdd  call    WPP_SF_d
0x180052be2  mov     eax, 80090304h
0x180052be7  mov     rcx, [rbp+2B0h+var_50]
0x180052bee  xor     rcx, rsp; StackCookie
0x180052bf1  call    __security_check_cookie
0x180052bf6  add     rsp, 378h
0x180052bfd  pop     r15
0x180052bff  pop     r14
0x180052c01  pop     r13
0x180052c03  pop     r12
0x180052c05  pop     rdi
0x180052c06  pop     rsi
0x180052c07  pop     rbx
0x180052c08  pop     rbp
0x180052c09  retn
```
