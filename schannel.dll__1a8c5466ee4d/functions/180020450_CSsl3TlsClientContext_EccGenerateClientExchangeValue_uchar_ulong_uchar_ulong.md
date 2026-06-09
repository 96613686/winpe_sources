# CSsl3TlsClientContext::EccGenerateClientExchangeValue(uchar *,ulong,uchar *,ulong *)

- ea: `0x180020450`
- end: `0x1800214e8`
- name: `?EccGenerateClientExchangeValue@CSsl3TlsClientContext@@AEAAKPEAEK0PEAK@Z`
- size: `4248`
- prototype: `unsigned int __usercall@<eax>(CSsl3TlsClientContext *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020300`

## callees

- `0x180014240`
- `0x1800165a4`
- `0x18001d960`
- `0x18001db60`
- `0x180020450`
- `0x1800214f0`
- `0x180021da8`
- `0x180021ef0`
- `0x18003dbe0`
- `0x180041960`
- `0x1800429f0`
- `0x18004bca4`
- `0x1800525bc`
- `0x180052620`
- `0x1800526ac`
- `0x1800597b0`
- `0x18005a160`
- `0x18005f1e4`
- `0x18007be38`
- `0x1800889d0`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021138`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021138`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800212ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800212ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021019`
- `ntdll!RtlReleaseResource` at `0x1800209cb`
- `ntdll!RtlReleaseResource` at `0x180020f48`
- `ntdll!RtlReleaseResource` at `0x180021013`
- `ntdll!RtlReleaseResource` at `0x180021040`
- `ntdll!RtlReleaseResource` at `0x18008c259`
- `ntdll!RtlReleaseResource` at `0x1800209cb`
- `ntdll!RtlReleaseResource` at `0x180020f48`
- `ntdll!RtlReleaseResource` at `0x180021013`
- `ntdll!RtlReleaseResource` at `0x180021040`
- `ntdll!RtlReleaseResource` at `0x18008c259`
- `ntdll!RtlAcquireResourceShared` at `0x180020963`
- `ntdll!RtlAcquireResourceShared` at `0x180020f00`
- `ntdll!RtlAcquireResourceShared` at `0x18008c238`
- `ntdll!RtlAcquireResourceShared` at `0x180020963`
- `ntdll!RtlAcquireResourceShared` at `0x180020f00`
- `ntdll!RtlAcquireResourceShared` at `0x18008c238`
- `ntdll!RtlInitUnicodeString` at `0x18008c154`
- `ntdll!RtlInitUnicodeString` at `0x18008c161`
- `ntdll!RtlInitUnicodeString` at `0x18008c154`
- `ntdll!RtlInitUnicodeString` at `0x18008c161`
- `ncrypt!SslExportKey` at `0x180021224`
- `ncrypt!SslExportKey` at `0x180021284`
- `ncrypt!SslExportKey` at `0x180021224`
- `ncrypt!SslExportKey` at `0x180021284`
- `ncrypt!SslCreateEphemeralKey` at `0x180021199`
- `ncrypt!SslCreateEphemeralKey` at `0x180021199`
- `ncrypt!SslFreeObject` at `0x1800208bd`
- `ncrypt!SslFreeObject` at `0x1800208ce`
- `ncrypt!SslFreeObject` at `0x1800208bd`
- `ncrypt!SslFreeObject` at `0x1800208ce`
- `ncrypt!SslImportKey` at `0x1800207a9`
- `ncrypt!SslImportKey` at `0x180020d2c`
- `ncrypt!SslImportKey` at `0x1800207a9`
- `ncrypt!SslImportKey` at `0x180020d2c`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180020f2e`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180020f2e`
- `bcrypt!BCryptGetProperty` at `0x180020c07`
- `bcrypt!BCryptGetProperty` at `0x180020c07`
- `bcrypt!BCryptCreateHash` at `0x180020e5f`
- `bcrypt!BCryptCreateHash` at `0x180020e5f`
- `bcrypt!BCryptHashData` at `0x180020e7f`
- `bcrypt!BCryptHashData` at `0x180020e98`
- `bcrypt!BCryptHashData` at `0x180020e7f`
- `bcrypt!BCryptHashData` at `0x180020e98`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008c1ec`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008c1ec`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008c1b0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008c1b0`
- `bcrypt!BCryptFinishHash` at `0x180020eb5`
- `bcrypt!BCryptFinishHash` at `0x180020eb5`
- `bcrypt!BCryptDestroyKey` at `0x180020fa1`
- `bcrypt!BCryptDestroyKey` at `0x180020fa1`
- `bcrypt!BCryptDestroyHash` at `0x180020ec6`
- `bcrypt!BCryptDestroyHash` at `0x180020ec6`
- `bcrypt!BCryptVerifySignature` at `0x180020f88`
- `bcrypt!BCryptVerifySignature` at `0x180020f88`

## pseudocode

```c
__int64 __fastcall CSsl3TlsClientContext::EccGenerateClientExchangeValue(
        CSsl3TlsClientContext *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  __int64 v5; // r15
  __int64 v6; // rsi
  __int64 v9; // r8
  int v10; // eax
  int v11; // r11d
  int v12; // eax
  int v13; // r12d
  unsigned int v14; // eax
  int v15; // edi
  unsigned int v16; // edx
  __int64 v17; // r8
  unsigned int i; // edx
  __int64 v19; // rax
  int v20; // r10d
  unsigned __int8 *v21; // r13
  enum _eTlsHashAlgorithm v22; // r12d
  BYTE *v23; // r15
  __int64 v24; // rcx
  unsigned int v25; // r13d
  unsigned int Hash; // esi
  int v27; // r11d
  __int64 *v28; // rax
  unsigned int v29; // r12d
  __int64 v30; // r15
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v34; // rcx
  void *v35; // rsp
  void *v36; // rsp
  UCHAR *p_Size_4; // r15
  unsigned __int8 *v38; // r14
  size_t v39; // r8
  unsigned __int8 *v40; // rdx
  __int64 *v41; // rcx
  __int64 v42; // rax
  int v43; // esi
  __int64 *v44; // rax
  __int64 v45; // rcx
  unsigned int *v46; // rsi
  unsigned __int8 *v47; // r14
  _BYTE *v48; // rcx
  bool v49; // zf
  UCHAR v50; // dl
  UCHAR v51; // di
  unsigned int cbKey; // eax
  unsigned int KeyExchangeBlob; // eax
  __int64 *v54; // r11
  __int64 *v55; // rax
  unsigned __int8 k; // r8
  __int16 v57; // dx
  unsigned int j; // r11d
  unsigned int v59; // edx
  __int64 v60; // r8
  int v61; // r13d
  __int64 v62; // r9
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rcx
  const WCHAR *v67; // rdx
  const WCHAR *v68; // rdi
  __int64 v69; // rax
  unsigned int v70; // esi
  __int64 v71; // rdx
  int v72; // edi
  int v73; // esi
  __int64 v74; // r15
  __int64 v75; // rdx
  __int64 v76; // r9
  unsigned int v77; // ecx
  int v78; // r15d
  __int64 v79; // rdx
  BCRYPT_ALG_HANDLE v80; // rax
  __int64 v81; // rcx
  BCRYPT_HANDLE v82; // rdx
  ULONG v83; // r12d
  BCRYPT_ALG_HANDLE v84; // rcx
  unsigned __int64 v85; // rsi
  UCHAR *v86; // r15
  _DWORD *v87; // rax
  int v88; // eax
  int v89; // eax
  ULONG v90; // ecx
  __int64 v91; // rdx
  __int64 v92; // rcx
  unsigned int v93; // eax
  __int64 v94; // r9
  unsigned int v95; // eax
  __int64 v96; // rcx
  unsigned __int64 v97; // rcx
  void *v98; // rsp
  void *v99; // rsp
  BOOL v100; // eax
  struct _RTL_RESOURCE *v101; // rcx
  struct _UNICODE_STRING *p_pPaddingInfo; // rdx
  DWORD LastError; // eax
  __int64 *v104; // rax
  unsigned __int64 v105; // r13
  __int64 v106; // r15
  __int64 v107; // r9
  struct _BCRYPT_ECCKEY_BLOB *v108; // rax
  struct _BCRYPT_ECCKEY_BLOB *v109; // r12
  unsigned __int64 v110; // rsi
  UCHAR *v111; // rax
  __int64 *v112; // rax
  int v113; // edx
  __int64 v114; // r8
  CCipherMill *v115; // rcx
  KeyExchangeGroup *KeyExchangeGroup; // rcx
  unsigned int KeyExchangeSize; // eax
  MasterKeyExchangeInfo **v118; // rcx
  MasterKeyExchangeInfo *v119; // rcx
  ULONG v120; // r13d
  _BYTE v121[32]; // [rsp+0h] [rbp-50h] BYREF
  ULONG *pcbResult; // [rsp+20h] [rbp-30h]
  ULONG dwFlags[2]; // [rsp+28h] [rbp-28h]
  UCHAR pbOutput[4]; // [rsp+50h] [rbp+0h] BYREF
  unsigned int Size; // [rsp+54h] [rbp+4h] BYREF
  ULONG Size_4; // [rsp+58h] [rbp+8h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+60h] [rbp+10h] BYREF
  unsigned __int64 v128; // [rsp+68h] [rbp+18h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+70h] [rbp+20h]
  unsigned __int64 v130; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v131; // [rsp+80h] [rbp+30h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+88h] [rbp+38h] BYREF
  __int64 v133; // [rsp+90h] [rbp+40h]
  ULONG v134; // [rsp+98h] [rbp+48h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+A0h] [rbp+50h] BYREF
  struct _UNICODE_STRING pPaddingInfo; // [rsp+A8h] [rbp+58h] BYREF
  __int64 v137; // [rsp+B8h] [rbp+68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp+70h] BYREF
  PUCHAR pbSignature; // [rsp+D0h] [rbp+80h]
  ULONG cbSignature[2]; // [rsp+D8h] [rbp+88h]
  unsigned int *v141; // [rsp+E0h] [rbp+90h]
  unsigned __int8 *v142; // [rsp+E8h] [rbp+98h]
  char v143[8]; // [rsp+F0h] [rbp+A0h] BYREF
  int v144; // [rsp+F8h] [rbp+A8h]
  int v145; // [rsp+FCh] [rbp+ACh]
  UCHAR pbHash[16]; // [rsp+770h] [rbp+720h] BYREF
  unsigned __int8 v147[48]; // [rsp+780h] [rbp+730h] BYREF

  v5 = 0;
  v6 = a3;
  v128 = 0;
  v130 = 0;
  Size = 0;
  v9 = *((_QWORD *)this + 1);
  v142 = a4;
  v141 = a5;
  v10 = *(_DWORD *)(v9 + 52);
  if ( v10 == 1 )
  {
    v11 = 1;
  }
  else
  {
    if ( v10 != 3 )
      return 2148074248LL;
    v11 = 3;
  }
  *(_DWORD *)pbOutput = v11;
  if ( !a2 )
    return 2148074248LL;
  if ( (unsigned int)v6 < 4 )
    goto LABEL_262;
  if ( *a2 != 3 )
  {
    LOBYTE(a4) = 47;
    goto LABEL_275;
  }
  v12 = a2[3];
  if ( (unsigned __int8)v12 < 2u || (v13 = v12 + 4, v131 = a2[3], v12 + 4 > (unsigned int)v6) )
  {
LABEL_262:
    LOBYTE(a4) = 50;
LABEL_275:
    v75 = 800;
LABEL_113:
    CSslContext::SetErrorAndFatalAlert(this, v75, 2148074248LL, a4);
    return 2148074248LL;
  }
  v14 = v12 + 6;
  if ( !a4 )
  {
    *a5 = v14;
    return 0;
  }
  if ( *a5 < v14 )
    return 2148074273LL;
  v15 = a2[2] | (a2[1] << 8);
  if ( *((_WORD *)this + 1320) )
  {
    v16 = 0;
    a4 = (unsigned __int8 *)*((unsigned __int16 *)this + 1320);
    while ( v16 < (unsigned int)a4 )
    {
      if ( *(unsigned __int16 *)(*((_QWORD *)this + 329) + 2LL * v16) == v15 )
        goto LABEL_15;
      ++v16;
    }
    goto LABEL_192;
  }
LABEL_15:
  *((_DWORD *)this + 4) = v15;
  v17 = *(_QWORD *)(v9 + 848);
  if ( v17 )
  {
    for ( i = 0; i < *(_DWORD *)(v17 + 8); ++i )
    {
      v19 = 780LL * i + *(_QWORD *)v17;
      if ( *(_DWORD *)(v19 + 772) == v15 )
      {
        if ( v19 )
          *((_DWORD *)this + 5) = *(_DWORD *)(v19 + 776);
        break;
      }
    }
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 13) + 260LL) )
  {
    RtlAcquireResourceShared(&Resource, 1u);
    if ( v15 && qword_1800AE5C8 )
    {
      for ( j = 0; j < *((_DWORD *)qword_1800AE5C8 + 2); ++j )
      {
        v59 = 0;
        v60 = *(_QWORD *)qword_1800AE5C8 + 32LL * j;
        while ( v59 < *(_DWORD *)(v60 + 8) )
        {
          v5 = *(_QWORD *)v60 + 780LL * v59;
          if ( *(_DWORD *)(v5 + 772) == v15 )
          {
            v61 = 0;
            goto LABEL_95;
          }
          ++v59;
        }
        v5 = 0;
      }
      v61 = 1168;
LABEL_95:
      RtlReleaseResource(&Resource);
      if ( !v61 )
      {
        v63 = *((_QWORD *)this + 13);
        v64 = *(_QWORD *)(v63 + 264);
        if ( v64 )
        {
          v113 = *(_DWORD *)(v63 + 260);
          if ( v113 )
          {
            if ( v5
              && (unsigned __int8)IsKeyExchangeAlgorithmBlacklisted(
                                    v64,
                                    v113,
                                    v5,
                                    *(_DWORD *)(v5 + 772),
                                    (__int64)L"ECDH",
                                    *(_DWORD *)(v5 + 768),
                                    0,
                                    1) )
            {
LABEL_192:
              v91 = 801;
              goto LABEL_193;
            }
          }
        }
        v11 = *(_DWORD *)pbOutput;
        goto LABEL_23;
      }
    }
    else
    {
      RtlReleaseResource(&Resource);
    }
    Hash = -2146893052;
    LOBYTE(v62) = 80;
    CSslContext::SetErrorAndFatalAlert(this, 800, 2148074244LL, v62);
    goto LABEL_76;
  }
LABEL_23:
  v20 = *((_DWORD *)this + 22);
  v21 = &a2[v13];
  a4 = v21;
  if ( (v20 & 0x80800) != 0 )
  {
    if ( v21 + 2 > &a2[v6] )
    {
      LOBYTE(a4) = 50;
      v91 = 821;
      goto LABEL_194;
    }
    v54 = qword_1800931C0;
    a4 = v21 + 2;
    v55 = qword_1800931C0;
    for ( k = 0; ; ++k )
    {
      if ( v55 >= (__int64 *)&off_180093580 )
        goto LABEL_112;
      v57 = __ROR2__(*(_WORD *)v21, 8);
      if ( v57 == *(_WORD *)v55 )
        break;
      v55 += 10;
    }
    if ( k >= 0xCu
      || (v88 = *((unsigned __int16 *)this + 1114), !_bittest(&v88, k))
      || (v20 & 0x3000) != 0 && HIDWORD(qword_1800931C0[10 * k + 3]) == 3 && LODWORD(qword_1800931C0[10 * k + 9])
      || (v20 & qword_1800931C0[10 * k + 3]) == 0 )
    {
LABEL_112:
      LOBYTE(a4) = 47;
      v75 = 821;
      goto LABEL_113;
    }
    v89 = 0;
    while ( 1 )
    {
      v133 = 0;
      v22 = TlsHashAlgorithm_None;
      Size_4 = 0;
      if ( v54 >= (__int64 *)&off_180093580 )
        break;
      if ( v57 == *(_WORD *)v54 )
      {
        v90 = *((_DWORD *)v54 + 15);
        v89 = *((_DWORD *)v54 + 7);
        v22 = *((_DWORD *)v54 + 10);
        v133 = v54[6];
        Size_4 = v90;
        break;
      }
      v54 += 10;
    }
    v11 = *(_DWORD *)pbOutput;
    if ( v89 != *(_DWORD *)pbOutput )
    {
      v91 = 821;
LABEL_193:
      LOBYTE(a4) = 40;
LABEL_194:
      CSslContext::SetErrorAndFatalAlert(this, v91, 2148074248LL, a4);
      Hash = -2146893048;
      goto LABEL_76;
    }
  }
  else
  {
    v133 = 0;
    v22 = TlsHashAlgorithm_None;
    Size_4 = 0;
  }
  v23 = a4 + 2;
  pbSignature = a4 + 2;
  if ( a4 + 2 <= &a2[v6] )
  {
    v24 = (*a4 << 8) | (unsigned int)a4[1];
    *(_QWORD *)cbSignature = v24;
    if ( &a4[v24 + 2] <= &a2[v6] )
    {
      v25 = (_DWORD)v21 - (_DWORD)a2;
      Hash = 1359;
      v27 = v11 - 1;
      if ( v27 )
      {
        if ( v27 == 2 )
        {
          v95 = VerifyEcdsaParams(this, a2, v25, v22, v23, v24);
          Hash = v95;
          if ( v95 )
          {
            LOBYTE(a4) = 51;
            v32 = v95;
            v31 = 803;
            goto LABEL_40;
          }
        }
        goto LABEL_29;
      }
      phKey = 0;
      memset_0(pbHash, 0, 0x40u);
      v76 = 0;
      v137 = 0;
      pPaddingInfo = 0;
      if ( v22 == TlsHashAlgorithm_None )
      {
        v83 = 36;
        Hash = GenerateHash(g_hMD5Provider, this, a2, v25, pbHash, 0x10u);
        if ( !Hash )
          Hash = GenerateHash(g_hSHAProvider, this, a2, v25, v147, 0x14u);
        Size_4 = 2;
LABEL_181:
        if ( Hash )
        {
          LOBYTE(v76) = 80;
          CSslContext::SetErrorAndFatalAlert(this, 1105, Hash, v76);
        }
        else
        {
          RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL), 1u);
          v100 = CryptImportPublicKeyInfoEx2(
                   **(_DWORD **)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 40LL),
                   (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 40LL)
                                                     + 24LL)
                                         + 96LL),
                   0x80000000,
                   0,
                   &phKey);
          v101 = (struct _RTL_RESOURCE *)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL);
          if ( !v100 )
          {
            RtlReleaseResource(v101);
            LastError = GetLastError();
            Hash = LastError;
            LOBYTE(a4) = 43;
LABEL_198:
            CSslContext::SetErrorAndFatalAlert(this, 1106, LastError, a4);
            goto LABEL_186;
          }
          RtlReleaseResource(v101);
          if ( Size_4 == 8 )
          {
            p_pPaddingInfo = &pPaddingInfo;
            *(_QWORD *)&pPaddingInfo.Length = v133;
            LODWORD(pPaddingInfo.Buffer) = v83;
LABEL_185:
            LastError = BCryptVerifySignature(phKey, p_pPaddingInfo, pbHash, v83, v23, cbSignature[0], Size_4);
            Hash = LastError;
            if ( !LastError )
              goto LABEL_186;
            LOBYTE(a4) = 51;
            goto LABEL_198;
          }
          if ( Size_4 == 2 )
          {
            p_pPaddingInfo = (struct _UNICODE_STRING *)&v137;
            v137 = v133;
            goto LABEL_185;
          }
          Hash = -2146893052;
        }
LABEL_186:
        if ( phKey )
          BCryptDestroyKey(phKey);
        if ( Hash )
        {
          v31 = 802;
          goto LABEL_39;
        }
LABEL_29:
        if ( (*((_BYTE *)this + 32) & 1) != 0 && (v28 = (__int64 *)*((_QWORD *)this + 1)) != 0 )
        {
          v29 = *((_DWORD *)v28 + 7);
        }
        else
        {
          v28 = (__int64 *)*((_QWORD *)this + 1);
          v29 = 0;
          if ( !v28 )
          {
            v30 = 0;
            goto LABEL_36;
          }
        }
        v30 = *v28;
LABEL_36:
        if ( !v15 || !qword_1800AE5C8 )
        {
          Hash = 87;
LABEL_38:
          v31 = 805;
LABEL_39:
          LOBYTE(a4) = 51;
          v32 = Hash;
LABEL_40:
          CSslContext::SetErrorAndFatalAlert(this, v31, v32, a4);
LABEL_76:
          if ( v130 )
            SslFreeObject(v130, 0);
          if ( v128 )
            SslFreeObject(v128, 0);
          return Hash;
        }
        *(_WORD *)pbOutput = *((_WORD *)this + 17);
        Size_4 = 0;
        RtlAcquireResourceShared(&Resource, 1u);
        Hash = CMasterEccCurveInfo::GetPublicKeyLength(qword_1800AE5C8, v15, &Size_4);
        RtlReleaseResource(&Resource);
        if ( Hash == 1168 && (KeyExchangeGroup = CCipherMill::GetKeyExchangeGroup(v115, v15)) != 0 )
        {
          KeyExchangeSize = KeyExchangeGroup::GetKeyExchangeSize(KeyExchangeGroup, 0);
          v119 = *v118;
          Hash = 0;
          v120 = KeyExchangeSize;
          if ( !KeyExchangeSize )
            Hash = 1168;
          MasterKeyExchangeInfo::Dereference(v119);
        }
        else
        {
          v120 = Size_4;
        }
        if ( Hash )
          goto LABEL_38;
        Hash = SslCreateEphemeralKey(v30, &v130, *(unsigned __int16 *)pbOutput, v29, v15, v120, 0, 0, 0);
        if ( Hash )
        {
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_3e0ca11e9b65363ec3903422d835754d_Traceguids, Hash);
          }
          goto LABEL_38;
        }
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 380) + 40LL) + 8LL) = v120;
        v104 = (__int64 *)*((_QWORD *)this + 1);
        v105 = v130;
        if ( v104 )
          v106 = *v104;
        else
          v106 = 0;
        Hash = SslExportKey(v106, v130, L"ECCPUBLICBLOB", 0, 0, &Size, 0);
        if ( Hash )
        {
          v109 = 0;
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_039d3513f02f369a5a975d378c49ef62_Traceguids, Hash);
          }
          goto LABEL_238;
        }
        if ( LsaTable )
          v108 = (struct _BCRYPT_ECCKEY_BLOB *)(*(__int64 (__fastcall **)(_QWORD))(LsaTable + 40))(Size);
        else
          v108 = (struct _BCRYPT_ECCKEY_BLOB *)LocalAlloc(0x40u, Size);
        v109 = v108;
        if ( !v108 )
        {
          Hash = 14;
          goto LABEL_238;
        }
        Hash = SslExportKey(v106, v105, L"ECCPUBLICBLOB", v108, Size, &Size, 0);
        if ( Hash )
        {
          SPExternalFree(v109);
          v109 = 0;
LABEL_238:
          LOBYTE(v107) = 51;
          p_Size_4 = 0;
          CSslContext::SetErrorAndFatalAlert(this, 806, Hash, v107);
          goto LABEL_70;
        }
        v110 = Size;
        p_Size_4 = 0;
        if ( !Size
          || Size > (unsigned __int64)g_ulMaxStackAllocSize
          || (unsigned __int64)Size + g_ulAdditionalProbeSize + 8 < Size
          || !(unsigned int)VerifyStackAvailable() )
        {
          goto LABEL_278;
        }
        v34 = v110 + 23;
        if ( v110 + 23 <= v110 + 8 )
          v34 = 0xFFFFFFFFFFFFFF0LL;
        v35 = alloca(v34 & 0xFFFFFFFFFFFFFFF0uLL);
        v36 = alloca(v34 & 0xFFFFFFFFFFFFFFF0uLL);
        p_Size_4 = pbOutput;
        if ( v121 == (_BYTE *)-80LL || (*(_DWORD *)pbOutput = 1801679955, (p_Size_4 = (UCHAR *)&Size_4) == 0) )
        {
LABEL_278:
          if ( v110 + 8 >= v110 )
          {
            v111 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
            p_Size_4 = v111;
            if ( v111 )
            {
              *(_DWORD *)v111 = 1885431112;
              p_Size_4 = v111 + 8;
            }
          }
        }
        if ( !p_Size_4 )
        {
          Hash = 14;
          goto LABEL_70;
        }
        memset_0(p_Size_4, 0, Size);
        *(struct _BCRYPT_ECCKEY_BLOB *)p_Size_4 = *v109;
        v38 = a2 + 4;
        if ( !v38 )
        {
          Hash = 87;
          goto LABEL_70;
        }
        if ( (*((_BYTE *)this + 20) & 8) != 0 )
        {
          v39 = v131;
          if ( (unsigned __int64)(2 * v131) + 8 <= Size )
          {
            v40 = v38;
            goto LABEL_54;
          }
        }
        else if ( *v38 == 4 && (unsigned __int64)v131 + 7 <= Size )
        {
          v39 = v131 - 1;
          v40 = v38 + 1;
LABEL_54:
          Hash = 0;
          memcpy_0(p_Size_4 + 8, v40, v39);
          goto LABEL_55;
        }
        Hash = -2146893048;
LABEL_55:
        if ( !Hash )
        {
          v41 = (__int64 *)*((_QWORD *)this + 1);
          v42 = v41[106];
          if ( v42 && *(_BYTE *)(v42 + 24) )
          {
            v43 = *(_DWORD *)p_Size_4;
            *(_DWORD *)p_Size_4 = v15;
            v44 = (__int64 *)*((_QWORD *)this + 1);
            if ( v44 )
              v45 = *v44;
            else
              v45 = 0;
            if ( !(unsigned int)SslImportKey(v45, &v128, L"SSLECCPUBLICBLOB", p_Size_4, Size, 0) )
            {
LABEL_61:
              v46 = v141;
              v47 = v142;
              v48 = v142 + 1;
              v49 = (*((_BYTE *)this + 20) & 8) == 0;
              v50 = *(_BYTE *)v141 - 1;
              v51 = v50;
              pbOutput[0] = v50;
              if ( v49 )
              {
                cbKey = v109->cbKey;
                if ( cbKey > 0x7F )
                {
                  KeyExchangeBlob = 1359;
                }
                else
                {
                  v51 = 2 * cbKey + 1;
                  if ( v142 == (unsigned __int8 *)-1LL )
                  {
LABEL_66:
                    KeyExchangeBlob = 0;
                    goto LABEL_67;
                  }
                  if ( v50 >= v51 )
                  {
                    *v48 = 4;
                    memcpy_0(v48 + 1, &v109[1], v51 - 1LL);
                    goto LABEL_66;
                  }
                  KeyExchangeBlob = -2146893023;
                }
              }
              else
              {
                KeyExchangeBlob = MontgomeryGetKeyExchangeBlob(v109, v142 + 1, pbOutput);
                v51 = pbOutput[0];
              }
LABEL_67:
              if ( KeyExchangeBlob )
              {
                Hash = -2146893048;
              }
              else
              {
                *v47 = v51;
                *v46 = v51 + 1;
                if ( (*((_DWORD *)this + 464) & 0x8000000) != 0 )
                {
                  (*(void (__fastcall **)(CSsl3TlsClientContext *, unsigned __int64))(*(_QWORD *)this + 168LL))(
                    this,
                    v128);
                  Hash = (*(__int64 (__fastcall **)(CSsl3TlsClientContext *, unsigned __int64))(*(_QWORD *)this + 184LL))(
                           this,
                           v130);
                  v128 = 0;
                  v130 = 0;
                }
                else
                {
                  Hash = MakeEccDhPskSessionKeysHelper(this, v130, v128, 0);
                }
              }
              goto LABEL_70;
            }
            *(_DWORD *)p_Size_4 = v43;
            v112 = (__int64 *)*((_QWORD *)this + 1);
            if ( v112 )
              v92 = *v112;
            else
              v92 = 0;
            dwFlags[0] = 0;
            LODWORD(pcbResult) = Size;
          }
          else
          {
            if ( v41 )
              v92 = *v41;
            else
              v92 = 0;
            dwFlags[0] = 0;
            LODWORD(pcbResult) = Size;
          }
          v93 = SslImportKey(v92, &v128, L"ECCPUBLICBLOB", p_Size_4, (_DWORD)pcbResult, dwFlags[0]);
          Hash = v93;
          if ( !v93 )
            goto LABEL_61;
          LOBYTE(v94) = 51;
          CSslContext::SetErrorAndFatalAlert(this, 804, v93, v94);
        }
LABEL_70:
        if ( v109 )
        {
          if ( LsaTable )
            (*(void (__fastcall **)(struct _BCRYPT_ECCKEY_BLOB *))(LsaTable + 48))(v109);
          else
            LocalFree(v109);
        }
        if ( p_Size_4 && *((_DWORD *)p_Size_4 - 2) == 1885431112 )
          ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_Size_4 - 8);
        goto LABEL_76;
      }
      v77 = 0;
      v78 = g_dwHashInfoTotalCount;
      hObject = 0;
      while ( v77 < g_dwHashInfoTotalCount )
      {
        v79 = g_pHashInfo[v77];
        if ( v79 && *(_DWORD *)(v79 + 20) == v22 )
        {
          v78 = v77;
          break;
        }
        ++v77;
      }
      if ( v78 < 0 || v78 >= g_dwHashInfoTotalCount )
      {
        v78 = 0;
      }
      else
      {
        if ( v78 == 1 )
        {
          v80 = g_hMD5Provider;
          goto LABEL_127;
        }
        if ( v78 == 2 )
        {
          v80 = g_hSHAProvider;
          goto LABEL_127;
        }
      }
      v80 = (BCRYPT_ALG_HANDLE)qword_1800AE610[v78];
LABEL_127:
      hObject = v80;
      if ( v78 >= (unsigned int)g_dwHashInfoTotalCount || (_mm_lfence(), (v81 = g_pHashInfo[v78]) == 0) )
      {
        Hash = 1168;
        v83 = 0;
        goto LABEL_180;
      }
      v82 = hObject;
      v83 = *(_DWORD *)(v81 + 8);
      hAlgorithm = hObject;
      if ( !hObject )
      {
        if ( !*(_QWORD *)v81 )
          goto LABEL_180;
        Hash = BCryptOpenAlgorithmProvider(&hObject, *(LPCWSTR *)v81, 0, 0);
        if ( Hash )
          goto LABEL_180;
        hAlgorithm = (BCRYPT_ALG_HANDLE)_InterlockedCompareExchange64(&qword_1800AE610[v78], (signed __int64)hObject, 0);
        if ( hAlgorithm )
        {
          BCryptCloseAlgorithmProvider(hObject, 0);
          v84 = hAlgorithm;
          hObject = hAlgorithm;
LABEL_131:
          *(_DWORD *)pbOutput = 0;
          v134 = 0;
          phHash = 0;
          Hash = BCryptGetProperty(v84, L"ObjectLength", pbOutput, 4u, &v134, 0);
          if ( Hash )
          {
LABEL_180:
            v23 = pbSignature;
            goto LABEL_181;
          }
          v85 = *(unsigned int *)pbOutput;
          v86 = 0;
          if ( *(_DWORD *)pbOutput
            && *(unsigned int *)pbOutput <= (unsigned __int64)g_ulMaxStackAllocSize
            && (unsigned __int64)*(unsigned int *)pbOutput + g_ulAdditionalProbeSize + 8 >= *(unsigned int *)pbOutput
            && (unsigned int)VerifyStackAvailable() )
          {
            v96 = v85 + 23;
            if ( v85 + 23 <= v85 + 8 )
              v96 = 0xFFFFFFFFFFFFFF0LL;
            v97 = v96 & 0xFFFFFFFFFFFFFFF0uLL;
            v98 = alloca(v97);
            v99 = alloca(v97);
            v86 = pbOutput;
            if ( v121 != (_BYTE *)-80LL )
            {
              *(_DWORD *)pbOutput = 1801679955;
              v86 = (UCHAR *)&Size_4;
              if ( &Size_4 )
                goto LABEL_171;
            }
          }
          if ( v85 + 8 >= v85 )
          {
            v87 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
            if ( !v87 )
            {
LABEL_138:
              Hash = 14;
              goto LABEL_180;
            }
            *v87 = 1885431112;
            v86 = (UCHAR *)(v87 + 2);
          }
          if ( v86 )
          {
LABEL_171:
            Hash = BCryptCreateHash(hAlgorithm, &phHash, v86, *(ULONG *)pbOutput, 0, 0, 0);
            if ( !Hash )
            {
              Hash = BCryptHashData(phHash, (PUCHAR)this + 1992, 0x40u, 0);
              if ( !Hash )
              {
                Hash = BCryptHashData(phHash, a2, v25, 0);
                if ( !Hash )
                  Hash = BCryptFinishHash(phHash, pbHash, v83, 0);
              }
            }
            if ( phHash )
              BCryptDestroyHash(phHash);
            if ( v86 && *((_DWORD *)v86 - 2) == 1885431112 )
              ((void (__fastcall *)(UCHAR *))g_pfnFree)(v86 - 8);
            goto LABEL_180;
          }
          goto LABEL_138;
        }
        v82 = hObject;
        hAlgorithm = hObject;
      }
      v84 = v82;
      goto LABEL_131;
    }
    goto LABEL_262;
  }
  v65 = (*(__int64 (__fastcall **)(CSsl3TlsClientContext *))(*(_QWORD *)this + 352LL))(this);
  v66 = *((_QWORD *)this + 231);
  if ( !*(_WORD *)(v66 + 34) )
  {
    *(_WORD *)(v66 + 34) = 800;
    *(_DWORD *)(v66 + 36) = -2146893048;
  }
  *((_WORD *)this + 60) = 12802;
  v67 = &Class;
  v68 = &Class;
  if ( v65 )
    v68 = (const WCHAR *)v65;
  v69 = *((_QWORD *)this + 13);
  if ( v69 )
  {
    v70 = *(_DWORD *)(v69 + 276);
    v67 = (const WCHAR *)(v69 + 280);
  }
  else
  {
    v70 = 0;
  }
  if ( (g_dwEventLogging & 4) != 0 )
  {
    DestinationString = 0;
    pPaddingInfo = 0;
    RtlInitUnicodeString(&DestinationString, v67);
    RtlInitUnicodeString(&pPaddingInfo, v68);
    dwFlags[0] = 800;
    LODWORD(pcbResult) = 50;
    SchEventWrite(
      &SSLEVENT_GENERATE_FATAL_ALERT,
      L"duddu",
      v70,
      &DestinationString,
      pcbResult,
      *(_QWORD *)dwFlags,
      &pPaddingInfo);
  }
  memset_0(v143, 0, 0x680u);
  v71 = *((_QWORD *)this + 1);
  if ( v71 )
    v72 = *(_DWORD *)(v71 + 28);
  else
    v72 = 0;
  v73 = *((unsigned __int16 *)this + 17);
  v74 = *((_QWORD *)this + 232);
  v145 = *((_DWORD *)this + 4);
  v144 = v72;
  if ( v71 )
  {
    v114 = *((_QWORD *)this + 14);
    if ( v114 )
      CSchannelTelemetryContext::LogKeyExchange(
        (CSsl3TlsClientContext *)((char *)this + 144),
        *(_DWORD *)(v71 + 32),
        *(_DWORD *)(*(_QWORD *)(v114 + 40) + 8LL));
  }
  if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
  {
    *((_DWORD *)this + 47) = v145;
    *((_BYTE *)this + 260) = 50;
    *((_DWORD *)this + 64) = -2146893048;
    *((_DWORD *)this + 66) = 800;
    *((_DWORD *)this + 46) = v72;
    *((_DWORD *)this + 48) = v73;
    *((_QWORD *)this + 35) = v74;
    *((_BYTE *)this + 169) = 1;
  }
  CSchannelTelemetryContext::LogDebugTraceHandshakeInfo((CSsl3TlsClientContext *)((char *)this + 144), L"Fatal Error");
  return 2148074248LL;
}

```

## disassembly

```asm
0x180020450  push    rbp
0x180020452  push    rsi
0x180020453  push    rdi
0x180020454  push    r12
0x180020456  push    r13
0x180020458  push    r14
0x18002045a  push    r15
0x18002045c  sub     rsp, 7C0h
0x180020463  lea     rbp, [rsp+50h]
0x180020468  mov     [rbp+7A0h+arg_10], rbx
0x18002046f  mov     rax, cs:__security_cookie
0x180020476  xor     rax, rbp
0x180020479  mov     [rbp+7A0h+var_40], rax
0x180020480  xor     r15d, r15d
0x180020483  mov     esi, r8d
0x180020486  mov     rbx, rcx
0x180020489  mov     [rbp+7A0h+var_788], r15
0x18002048d  mov     rcx, [rbp+7A0h+arg_20]
0x180020494  mov     r14, rdx
0x180020497  mov     [rbp+7A0h+var_778], r15
0x18002049b  mov     dword ptr [rbp+7A0h+Size], r15d
0x18002049f  mov     r8, [rbx+8]
0x1800204a3  mov     [rbp+7A0h+var_708], r9
0x1800204aa  mov     [rbp+7A0h+var_710], rcx
0x1800204b1  mov     eax, [r8+34h]
0x1800204b5  cmp     eax, 1
0x1800204b8  jnz     loc_180020635
0x1800204be  mov     r11d, eax
0x1800204c1  mov     dword ptr [rbp+7A0h+pbOutput], r11d
0x1800204c5  test    r14, r14
0x1800204c8  jz      loc_180020AF1
0x1800204ce  cmp     esi, 4
0x1800204d1  jb      loc_1800214E0
0x1800204d7  cmp     byte ptr [rdx], 3
0x1800204da  jnz     loc_18002138B
0x1800204e0  movzx   eax, byte ptr [rdx+3]
0x1800204e4  cmp     al, 2
0x1800204e6  jb      loc_1800214E0
0x1800204ec  lea     r12d, [rax+4]
0x1800204f0  mov     [rbp+7A0h+var_770], eax
0x1800204f3  cmp     r12d, esi
0x1800204f6  ja      loc_1800214E0
0x1800204fc  add     eax, 6
0x1800204ff  test    r9, r9
0x180020502  jz      loc_18002067E
0x180020508  cmp     [rcx], eax
0x18002050a  jb      loc_180021393
0x180020510  movzx   eax, byte ptr [rdx+2]
0x180020514  movzx   edi, byte ptr [rdx+1]
0x180020518  shl     edi, 8
0x18002051b  or      edi, eax
0x18002051d  movzx   eax, word ptr [rbx+0A50h]
0x180020524  test    ax, ax
0x180020527  jz      short loc_18002054D
0x180020529  mov     edx, r15d
0x18002052c  mov     r9d, eax
0x18002052f  cmp     edx, r9d
0x180020532  jnb     loc_180020FD0
0x180020538  mov     rax, [rbx+0A48h]
0x18002053f  mov     ecx, edx
0x180020541  movzx   ecx, word ptr [rax+rcx*2]
0x180020545  cmp     ecx, edi
0x180020547  jz      short loc_18002054D
0x180020549  inc     edx
0x18002054b  jmp     short loc_18002052F
0x18002054d  mov     [rbx+10h], edi
0x180020550  mov     r8, [r8+350h]
0x180020557  test    r8, r8
0x18002055a  jz      short loc_180020591
0x18002055c  mov     r9d, [r8+8]
0x180020560  mov     edx, r15d
0x180020563  cmp     edx, r9d
0x180020566  jnb     short loc_180020591
0x180020568  mov     eax, edx
0x18002056a  imul    rcx, rax, 30Ch
0x180020571  mov     rax, [r8]
0x180020574  add     rax, rcx
0x180020577  cmp     [rax+304h], edi
0x18002057d  jz      short loc_180020583
0x18002057f  inc     edx
0x180020581  jmp     short loc_180020563
0x180020583  test    rax, rax
0x180020586  jz      short loc_180020591
0x180020588  mov     eax, [rax+308h]
0x18002058e  mov     [rbx+14h], eax
0x180020591  mov     rax, [rbx+68h]
0x180020595  cmp     [rax+104h], r15d
0x18002059c  ja      loc_18002095A
0x1800205a2  mov     r10d, [rbx+58h]
0x1800205a6  mov     r13d, r12d
0x1800205a9  add     r13, r14
0x1800205ac  mov     r9, r13
0x1800205af  test    r10d, 80800h
0x1800205b6  jnz     loc_1800208FF
0x1800205bc  mov     [rbp+7A0h+var_760], r15
0x1800205c0  mov     r12d, r15d
0x1800205c3  mov     dword ptr [rbp+7A0h+Size+4], r15d
0x1800205c7  lea     r15, [r9+2]
0x1800205cb  lea     rdx, [rsi+r14]
0x1800205cf  mov     [rbp+7A0h+pbSignature], r15
0x1800205d6  cmp     r15, rdx
0x1800205d9  ja      loc_1800209FA
0x1800205df  movzx   ecx, byte ptr [r9+1]
0x1800205e4  movzx   eax, byte ptr [r9]
0x1800205e8  shl     eax, 8
0x1800205eb  or      ecx, eax
0x1800205ed  mov     qword ptr [rbp+7A0h+cbSignature], rcx
0x1800205f4  lea     rax, [rcx+2]
0x1800205f8  add     rax, r9
0x1800205fb  cmp     rax, rdx
0x1800205fe  ja      loc_1800214E0
0x180020604  sub     r13d, r14d
0x180020607  mov     esi, 54Fh
0x18002060c  sub     r11d, 1
0x180020610  jz      loc_180020AFB
0x180020616  cmp     r11d, 2
0x18002061a  jz      loc_180020DA4
0x180020620  test    byte ptr [rbx+20h], 1
0x180020624  jz      short loc_180020646
0x180020626  mov     rax, [rbx+8]
0x18002062a  test    rax, rax
0x18002062d  jz      short loc_180020646
0x18002062f  mov     r12d, [rax+1Ch]
0x180020633  jmp     short loc_180020656
0x180020635  cmp     eax, 3
0x180020638  jnz     loc_180020AF1
0x18002063e  mov     r11d, eax
0x180020641  jmp     loc_1800204C1
0x180020646  mov     rax, [rbx+8]
0x18002064a  xor     r12d, r12d
0x18002064d  test    rax, rax
0x180020650  jz      loc_180021130
0x180020656  mov     r15, [rax]
0x180020659  test    edi, edi
0x18002065b  jnz     loc_18008C212
0x180020661  mov     esi, 57h ; 'W'
0x180020666  mov     edx, 325h
0x18002066b  mov     r9b, 33h ; '3'
0x18002066e  mov     r8d, esi
0x180020671  mov     rcx, rbx
0x180020674  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x180020679  jmp     loc_1800208B2
0x18002067e  mov     [rcx], eax
0x180020680  xor     eax, eax
0x180020682  jmp     loc_1800208D6
0x180020687  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002068e  add     rcx, 8
0x180020692  add     rcx, rsi
0x180020695  cmp     rcx, rsi
0x180020698  jb      loc_1800212B3
0x18002069e  call    VerifyStackAvailable
0x1800206a3  test    eax, eax
0x1800206a5  jz      loc_1800212B3
0x1800206ab  lea     rax, [rsi+8]
0x1800206af  lea     rcx, [rax+0Fh]
0x1800206b3  cmp     rcx, rax
0x1800206b6  ja      short loc_1800206C2
0x1800206b8  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800206c2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800206c6  mov     rax, rcx
0x1800206c9  call    _alloca_probe
0x1800206ce  sub     rsp, rcx
0x1800206d1  lea     r15, [rsp+7F0h+pbOutput]
0x1800206d6  test    r15, r15
0x1800206d9  jz      loc_1800212B3
0x1800206df  mov     dword ptr [r15], 6B637453h
0x1800206e6  add     r15, 8
0x1800206ea  jz      loc_1800212B3
0x1800206f0  test    r15, r15
0x1800206f3  jz      loc_1800214BB
0x1800206f9  mov     r8d, dword ptr [rbp+7A0h+Size]; Size
0x1800206fd  xor     edx, edx; Val
0x1800206ff  mov     rcx, r15; void *
0x180020702  call    memset_0
0x180020707  mov     rax, [r12]
0x18002070b  mov     [r15], rax
0x18002070e  add     r14, 4
0x180020712  jz      loc_1800210E7
0x180020718  test    byte ptr [rbx+14h], 8
0x18002071c  mov     edx, dword ptr [rbp+7A0h+Size]
0x18002071f  jnz     loc_180020D82
0x180020725  cmp     byte ptr [r14], 4
0x180020729  jnz     loc_180020D78
0x18002072f  mov     r8d, [rbp+7A0h+var_770]
0x180020733  lea     rcx, [r8+7]
0x180020737  cmp     rcx, rdx
0x18002073a  ja      loc_180020D78
0x180020740  dec     r8d; Size
0x180020743  lea     rdx, [r14+1]; Src
0x180020747  lea     rcx, [r15+8]; void *
0x18002074b  mov     esi, r13d
0x18002074e  call    memcpy_0
0x180020753  test    esi, esi
0x180020755  jnz     loc_18002087A
0x18002075b  mov     rcx, [rbx+8]
0x18002075f  mov     rax, [rcx+350h]
0x180020766  test    rax, rax
0x180020769  jz      loc_180020D06
0x18002076f  cmp     [rax+18h], sil
0x180020773  jz      loc_180020D06
0x180020779  mov     esi, [r15]
0x18002077c  mov     [r15], edi
0x18002077f  mov     rax, [rbx+8]
0x180020783  mov     edx, dword ptr [rbp+7A0h+Size]
0x180020786  test    rax, rax
0x180020789  jz      loc_180021143
0x18002078f  mov     rcx, [rax]
0x180020792  mov     [rsp+7F0h+dwFlags], r13d
0x180020797  lea     r8, aSsleccpublicbl; "SSLECCPUBLICBLOB"
0x18002079e  mov     dword ptr [rsp+7F0h+pcbResult], edx
0x1800207a2  mov     r9, r15
0x1800207a5  lea     rdx, [rbp+7A0h+var_788]
0x1800207a9  call    cs:__imp_SslImportKey
0x1800207af  test    eax, eax
0x1800207b1  jnz     loc_180021366
0x1800207b7  mov     rsi, [rbp+7A0h+var_710]
0x1800207be  mov     r14, [rbp+7A0h+var_708]
0x1800207c5  movzx   eax, byte ptr [rsi]
0x1800207c8  dec     al
0x1800207ca  lea     rcx, [r14+1]
0x1800207ce  test    byte ptr [rbx+14h], 8
0x1800207d2  movzx   edx, al
0x1800207d5  movzx   edi, al
0x1800207d8  mov     [rbp+7A0h+pbOutput], al
0x1800207db  jnz     loc_1800210F1
0x1800207e1  mov     eax, [r12+4]
0x1800207e6  cmp     eax, 7Fh
0x1800207e9  ja      loc_180020CFC
0x1800207ef  movzx   edi, al
0x1800207f2  add     dil, dil
0x1800207f5  inc     dil
0x1800207f8  test    rcx, rcx
0x1800207fb  jz      short loc_18002081D
0x1800207fd  cmp     dl, dil
0x180020800  jb      loc_1800214C5
0x180020806  mov     byte ptr [rcx], 4
0x180020809  lea     rdx, [r12+8]; Src
0x18002080e  movzx   r8d, dil
0x180020812  dec     r8; Size
0x180020815  inc     rcx; void *
0x180020818  call    memcpy_0
0x18002081d  mov     eax, r13d
0x180020820  test    eax, eax
0x180020822  jnz     loc_180021126
0x180020828  movzx   eax, dil
0x18002082c  mov     rcx, rbx; struct CSsl3TlsContext *
0x18002082f  inc     eax
0x180020831  mov     [r14], dil
0x180020834  mov     [rsi], eax
0x180020836  mov     eax, [rbx+740h]
0x18002083c  bt      rax, 1Bh
0x180020841  jnb     loc_180020FFC
0x180020847  mov     rax, [rbx]
0x18002084a  mov     rdx, [rbp+7A0h+var_788]
0x18002084e  mov     rax, [rax+0A8h]
0x180020855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002085a  mov     rax, [rbx]
0x18002085d  mov     rcx, rbx
0x180020860  mov     rdx, [rbp+7A0h+var_778]
0x180020864  mov     rax, [rax+0B8h]
0x18002086b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020870  mov     esi, eax
0x180020872  mov     [rbp+7A0h+var_788], r13
0x180020876  mov     [rbp+7A0h+var_778], r13
0x18002087a  test    r12, r12
0x18002087d  jz      short loc_18002089B
0x18002087f  mov     rax, cs:LsaTable
0x180020886  mov     rcx, r12; hMem
0x180020889  test    rax, rax
0x18002088c  jz      loc_180021138
0x180020892  mov     rax, [rax+30h]
0x180020896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002089b  test    r15, r15
0x18002089e  jz      short loc_1800208B2
0x1800208a0  cmp     dword ptr [r15-8], 70616548h
0x1800208a8  lea     rcx, [r15-8]
0x1800208ac  jz      loc_1800214CF
0x1800208b2  mov     rcx, [rbp+7A0h+var_778]
0x1800208b6  test    rcx, rcx
0x1800208b9  jz      short loc_1800208C3
0x1800208bb  xor     edx, edx
0x1800208bd  call    cs:__imp_SslFreeObject
0x1800208c3  mov     rcx, [rbp+7A0h+var_788]
0x1800208c7  test    rcx, rcx
0x1800208ca  jz      short loc_1800208D4
0x1800208cc  xor     edx, edx
0x1800208ce  call    cs:__imp_SslFreeObject
0x1800208d4  mov     eax, esi
0x1800208d6  mov     rcx, [rbp+7A0h+var_40]
0x1800208dd  xor     rcx, rbp; StackCookie
0x1800208e0  call    __security_check_cookie
0x1800208e5  mov     rbx, [rbp+7A0h+arg_10]
0x1800208ec  lea     rsp, [rbp+770h]
0x1800208f3  pop     r15
0x1800208f5  pop     r14
0x1800208f7  pop     r13
0x1800208f9  pop     r12
0x1800208fb  pop     rdi
0x1800208fc  pop     rsi
0x1800208fd  pop     rbp
  ... truncated ...
```
