# VerifyEcdsaParams(CSsl3TlsClientContext *,uchar *,ulong,_eTlsHashAlgorithm,uchar *,ulong)

- ea: `0x180021ef0`
- end: `0x18002255e`
- name: `?VerifyEcdsaParams@@YAKPEAVCSsl3TlsClientContext@@PEAEKW4_eTlsHashAlgorithm@@1K@Z`
- size: `1646`
- prototype: `unsigned int __fastcall(struct CSsl3TlsClientContext *, unsigned __int8 *, unsigned int, enum _eTlsHashAlgorithm, BYTE *pbEncoded, DWORD cbEncoded)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020450`

## callees

- `0x180014240`
- `0x18001db60`
- `0x1800214f0`
- `0x180021eb0`
- `0x180021ef0`
- `0x18003e610`
- `0x1800597b0`
- `0x180071fdc`
- `0x1800889d0`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022496`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224cb`
- `ntdll!RtlReleaseResource` at `0x180021fa6`
- `ntdll!RtlReleaseResource` at `0x1800222ec`
- `ntdll!RtlReleaseResource` at `0x180021fa6`
- `ntdll!RtlReleaseResource` at `0x1800222ec`
- `ntdll!RtlAcquireResourceShared` at `0x180021f5a`
- `ntdll!RtlAcquireResourceShared` at `0x180021f5a`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180021f88`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180021f88`
- `CRYPT32!CryptDecodeObject` at `0x180022032`
- `CRYPT32!CryptDecodeObject` at `0x18002207a`
- `CRYPT32!CryptDecodeObject` at `0x180022032`
- `CRYPT32!CryptDecodeObject` at `0x18002207a`
- `bcrypt!BCryptGetProperty` at `0x180021fcf`
- `bcrypt!BCryptGetProperty` at `0x1800221ff`
- `bcrypt!BCryptGetProperty` at `0x180021fcf`
- `bcrypt!BCryptGetProperty` at `0x1800221ff`
- `bcrypt!BCryptCreateHash` at `0x18002239e`
- `bcrypt!BCryptCreateHash` at `0x18002239e`
- `bcrypt!BCryptHashData` at `0x1800223c2`
- `bcrypt!BCryptHashData` at `0x1800223dd`
- `bcrypt!BCryptHashData` at `0x1800223c2`
- `bcrypt!BCryptHashData` at `0x1800223dd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008c5f2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008c5f2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008c5c4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008c5c4`
- `bcrypt!BCryptFinishHash` at `0x1800223f7`
- `bcrypt!BCryptFinishHash` at `0x1800223f7`
- `bcrypt!BCryptDestroyKey` at `0x18002229b`
- `bcrypt!BCryptDestroyKey` at `0x18002229b`
- `bcrypt!BCryptDestroyHash` at `0x180022408`
- `bcrypt!BCryptDestroyHash` at `0x180022408`
- `bcrypt!BCryptVerifySignature` at `0x180022282`
- `bcrypt!BCryptVerifySignature` at `0x180022282`

## pseudocode

```c
__int64 __fastcall VerifyEcdsaParams(
        struct CSsl3TlsClientContext *a1,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned int a4,
        BYTE *pbEncoded,
        DWORD cbEncoded)
{
  __int64 v6; // rax
  char *v9; // rbx
  const void **v10; // r13
  __int64 v11; // rcx
  BOOL v12; // eax
  struct _RTL_RESOURCE *v13; // rcx
  unsigned int Property; // eax
  __int64 v15; // r9
  __int64 v16; // rdi
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int i; // eax
  unsigned int v21; // ecx
  __int64 v22; // rcx
  char v23; // r9
  __int64 v24; // r9
  DWORD v25; // r11d
  char *v26; // r10
  DWORD j; // edi
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // esi
  int v33; // eax
  BCRYPT_ALG_HANDLE v34; // rax
  __int64 v35; // rcx
  BCRYPT_HANDLE v36; // r14
  ULONG v37; // r12d
  unsigned __int64 v38; // rdi
  UCHAR *p_cbSignature; // rsi
  _DWORD *v40; // rax
  struct CSsl3TlsClientContext *v41; // r14
  unsigned int v42; // eax
  DWORD LastError; // eax
  __int64 v45; // rdx
  __int64 v46; // r8
  struct CSsl3TlsClientContext *v47; // rcx
  unsigned __int64 v48; // rcx
  __int64 v49; // rcx
  unsigned __int64 v50; // rcx
  void *v51; // rsp
  void *v52; // rsp
  NTSTATUS v53; // eax
  unsigned int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // [rsp+0h] [rbp-40h] BYREF
  BCRYPT_KEY_HANDLE *phKey; // [rsp+20h] [rbp-20h]
  ULONG dwFlags[2]; // [rsp+28h] [rbp-18h]
  DWORD cbSignature; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_HANDLE hAlgorithm; // [rsp+48h] [rbp+8h] BYREF
  UCHAR v61[4]; // [rsp+50h] [rbp+10h] BYREF
  struct CSsl3TlsClientContext *v62; // [rsp+58h] [rbp+18h]
  UCHAR pbOutput[8]; // [rsp+60h] [rbp+20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+68h] [rbp+28h] BYREF
  BCRYPT_KEY_HANDLE hObject; // [rsp+70h] [rbp+30h] BYREF
  ULONG pcbResult; // [rsp+78h] [rbp+38h] BYREF
  ULONG v67; // [rsp+7Ch] [rbp+3Ch] BYREF
  ULONG cbInput; // [rsp+80h] [rbp+40h]
  PUCHAR pbInput; // [rsp+88h] [rbp+48h]
  UCHAR pbHash[64]; // [rsp+A0h] [rbp+60h] BYREF

  v6 = *((_QWORD *)a1 + 14);
  v62 = a1;
  hObject = 0;
  v9 = 0;
  pcbResult = 0;
  v10 = 0;
  *(_DWORD *)pbOutput = 0;
  cbSignature = 0;
  v11 = *(_QWORD *)(v6 + 40);
  pbInput = a2;
  cbInput = a3;
  RtlAcquireResourceShared((PRTL_RESOURCE)(v11 + 80), 1u);
  v12 = CryptImportPublicKeyInfoEx2(
          **(_DWORD **)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 40LL) + 40LL),
          (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 40LL) + 40LL) + 24LL) + 96LL),
          0x80000000,
          0,
          &hObject);
  v13 = (struct _RTL_RESOURCE *)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 40LL) + 80LL);
  if ( !v12 )
  {
    RtlReleaseResource(v13);
    LastError = GetLastError();
    LOBYTE(v15) = 43;
    v45 = 1107;
    LODWORD(v16) = LastError;
    v46 = LastError;
    v47 = a1;
LABEL_43:
    CSslContext::SetErrorAndFatalAlert(v47, v45, v46, v15);
    goto LABEL_34;
  }
  RtlReleaseResource(v13);
  Property = BCryptGetProperty(hObject, L"KeyLength", pbOutput, 4u, &pcbResult, 0);
  LODWORD(v16) = Property;
  if ( Property )
  {
    LOBYTE(v15) = 80;
    v46 = Property;
    v45 = 1107;
    v47 = a1;
    goto LABEL_43;
  }
  v17 = (*(_DWORD *)pbOutput >> 3) + ((pbOutput[0] & 7) != 0);
  v9 = (char *)SPExternalAlloc(2 * v17);
  if ( v9 )
  {
    if ( !CryptDecodeObject(1u, (LPCSTR)0x2F, pbEncoded, cbEncoded, 0, 0, &cbSignature) )
    {
      v16 = GetLastError();
      v46 = v16;
LABEL_63:
      v47 = v62;
      v45 = 1108;
      LOBYTE(v15) = 50;
      goto LABEL_43;
    }
    v10 = (const void **)SPExternalAlloc(cbSignature);
    if ( v10 )
    {
      if ( CryptDecodeObject(1u, (LPCSTR)0x2F, pbEncoded, cbEncoded, 0, v10, &cbSignature) )
      {
        v15 = *(unsigned int *)v10;
        if ( (unsigned int)v15 <= v17 && *((_DWORD *)v10 + 4) <= v17 )
        {
          memcpy_0(v9, v10[1], (unsigned int)v15);
          memcpy_0(&v9[v17], v10[3], *((unsigned int *)v10 + 4));
          cbSignature = 2 * v17;
          for ( i = 0; i < v17 >> 1; v9[(unsigned int)v22] = v23 )
          {
            v19 = i;
            v21 = v17 - i++;
            v22 = v21 - 1;
            v18 = (unsigned int)v22;
            v23 = v9[v19];
            v9[v19] = v9[v22];
          }
          v24 = 0;
          v25 = cbSignature >> 1;
          v26 = &v9[(unsigned __int64)cbSignature >> 1];
          for ( j = cbSignature >> 2; (unsigned int)v24 < j; v26[(unsigned int)v29] = v19 )
          {
            v18 = (unsigned int)v24;
            v28 = v25 - v24;
            v24 = (unsigned int)(v24 + 1);
            v29 = (unsigned int)(v28 - 1);
            v19 = (unsigned __int8)v26[v18];
            v26[v18] = v26[v29];
          }
          hAlgorithm = 0;
          v30 = 2;
          if ( a4 )
            v30 = a4;
          v31 = MapTlsHashAlgorithmToIndex(v30, v18, v19, v24);
          v32 = v31;
          if ( v31 < 0 || v31 >= g_dwHashInfoTotalCount )
          {
            v32 = 0;
          }
          else
          {
            v33 = v31 - 1;
            if ( !v33 )
            {
              v34 = g_hMD5Provider;
              goto LABEL_20;
            }
            if ( v33 == 1 )
            {
              v34 = g_hSHAProvider;
              goto LABEL_20;
            }
          }
          v34 = (BCRYPT_ALG_HANDLE)qword_1800AE610[v32];
LABEL_20:
          hAlgorithm = v34;
          if ( v32 >= g_dwHashInfoTotalCount || (_mm_lfence(), (v35 = g_pHashInfo[v32]) == 0) )
          {
            LODWORD(v16) = 1168;
            v37 = 0;
            goto LABEL_31;
          }
          v36 = hAlgorithm;
          v37 = *(_DWORD *)(v35 + 8);
          if ( !hAlgorithm )
          {
            if ( !*(_QWORD *)v35 )
            {
              LODWORD(v16) = 1359;
              goto LABEL_31;
            }
            LODWORD(v16) = BCryptOpenAlgorithmProvider(&hAlgorithm, *(LPCWSTR *)v35, 0, 0);
            if ( (_DWORD)v16 )
              goto LABEL_31;
            v36 = (BCRYPT_HANDLE)_InterlockedCompareExchange64(
                                   (volatile signed __int64 *)&_ImageBase[4 * v32 + 357128],
                                   (signed __int64)hAlgorithm,
                                   0);
            if ( v36 )
            {
              BCryptCloseAlgorithmProvider(hAlgorithm, 0);
              hAlgorithm = v36;
            }
            else
            {
              v36 = hAlgorithm;
            }
          }
          *(_DWORD *)v61 = 0;
          v67 = 0;
          phHash = 0;
          LODWORD(v16) = BCryptGetProperty(v36, L"ObjectLength", v61, 4u, &v67, 0);
          if ( (_DWORD)v16 )
          {
LABEL_31:
            v41 = v62;
            goto LABEL_32;
          }
          v38 = *(unsigned int *)v61;
          p_cbSignature = 0;
          if ( *(_DWORD *)v61 )
          {
            if ( *(unsigned int *)v61 <= (unsigned __int64)g_ulMaxStackAllocSize )
            {
              v48 = *(unsigned int *)v61 + g_ulAdditionalProbeSize + 8;
              if ( v48 >= *(unsigned int *)v61 )
              {
                if ( (unsigned int)VerifyStackAvailable(v48) )
                {
                  v49 = v38 + 23;
                  if ( v38 + 23 <= v38 + 8 )
                    v49 = 0xFFFFFFFFFFFFFF0LL;
                  v50 = v49 & 0xFFFFFFFFFFFFFFF0uLL;
                  v51 = alloca(v50);
                  v52 = alloca(v50);
                  p_cbSignature = (UCHAR *)&cbSignature;
                  if ( &v56 != (__int64 *)-64LL )
                  {
                    cbSignature = 1801679955;
                    p_cbSignature = (UCHAR *)&hAlgorithm;
                    if ( &hAlgorithm )
                      goto LABEL_50;
                  }
                }
              }
            }
          }
          if ( v38 + 8 >= v38 )
          {
            v40 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
            if ( !v40 )
            {
LABEL_30:
              LODWORD(v16) = 14;
              goto LABEL_31;
            }
            *v40 = 1885431112;
            p_cbSignature = (UCHAR *)(v40 + 2);
          }
          if ( p_cbSignature )
          {
LABEL_50:
            v53 = BCryptCreateHash(v36, &phHash, p_cbSignature, *(ULONG *)v61, 0, 0, 0);
            v41 = v62;
            LODWORD(v16) = v53;
            if ( !v53 )
            {
              LODWORD(v16) = BCryptHashData(phHash, (PUCHAR)v62 + 1992, 0x40u, 0);
              if ( !(_DWORD)v16 )
              {
                LODWORD(v16) = BCryptHashData(phHash, pbInput, cbInput, 0);
                if ( !(_DWORD)v16 )
                  LODWORD(v16) = BCryptFinishHash(phHash, pbHash, v37, 0);
              }
            }
            if ( phHash )
              BCryptDestroyHash(phHash);
            if ( p_cbSignature && *((_DWORD *)p_cbSignature - 2) == 1885431112 )
              ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_cbSignature - 8);
LABEL_32:
            if ( (_DWORD)v16 )
            {
              LOBYTE(v15) = 80;
              v46 = (unsigned int)v16;
              v45 = 1109;
              v47 = v41;
            }
            else
            {
              v42 = BCryptVerifySignature(hObject, 0, pbHash, v37, (PUCHAR)v9, cbSignature, 0);
              LODWORD(v16) = v42;
              if ( !v42 )
                goto LABEL_34;
              LOBYTE(v15) = 51;
              v46 = v42;
              v45 = 1110;
              v47 = v41;
            }
            goto LABEL_43;
          }
          goto LABEL_30;
        }
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v54 = *((_DWORD *)v10 + 4);
          v55 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          dwFlags[0] = v17;
          LODWORD(phKey) = v54;
          WPP_SF_dDD(v55, 10, WPP_3e0ca11e9b65363ec3903422d835754d_Traceguids);
        }
        LODWORD(v16) = 13;
        v46 = 13;
        goto LABEL_63;
      }
      LODWORD(v16) = GetLastError();
    }
    else
    {
      LODWORD(v16) = -2146893056;
    }
  }
  else
  {
    LODWORD(v16) = 14;
  }
LABEL_34:
  if ( hObject )
    BCryptDestroyKey(hObject);
  if ( v9 )
    SPExternalFree(v9);
  if ( v10 )
  {
    if ( LsaTable )
      (*(void (__fastcall **)(const void **))(LsaTable + 48))(v10);
    else
      LocalFree(v10);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180021ef0  push    rbp
0x180021ef2  push    rbx
0x180021ef3  push    rsi
0x180021ef4  push    rdi
0x180021ef5  push    r12
0x180021ef7  push    r13
0x180021ef9  push    r14
0x180021efb  push    r15
0x180021efd  sub     rsp, 0F8h
0x180021f04  lea     rbp, [rsp+40h]
0x180021f09  mov     rax, cs:__security_cookie
0x180021f10  xor     rax, rbp
0x180021f13  mov     [rbp+0F0h+var_50], rax
0x180021f1a  mov     rax, [rcx+70h]
0x180021f1e  xor     r14d, r14d
0x180021f21  mov     r15, [rbp+0F0h+pbEncoded]
0x180021f28  mov     rsi, rcx
0x180021f2b  mov     [rbp+0F0h+var_D8], rcx
0x180021f2f  mov     r12d, r9d
0x180021f32  mov     [rbp+0F0h+hObject], r14
0x180021f36  mov     ebx, r14d
0x180021f39  mov     [rbp+0F0h+pcbResult], r14d
0x180021f3d  mov     r13d, r14d
0x180021f40  mov     dword ptr [rbp+0F0h+pbOutput], r14d
0x180021f44  mov     [rbp+0F0h+cbSignature], r14d
0x180021f48  mov     rcx, [rax+28h]
0x180021f4c  mov     [rbp+0F0h+pbInput], rdx
0x180021f50  add     rcx, 50h ; 'P'; Resource
0x180021f54  mov     dl, 1; Wait
0x180021f56  mov     [rbp+0F0h+cbInput], r8d
0x180021f5a  call    cs:__imp_RtlAcquireResourceShared
0x180021f60  mov     rax, [rsi+70h]
0x180021f64  xor     r9d, r9d; pvAuxInfo
0x180021f67  mov     r8d, 80000000h; dwFlags
0x180021f6d  mov     rcx, [rax+28h]
0x180021f71  lea     rax, [rbp+0F0h+hObject]
0x180021f75  mov     [rsp+130h+phKey], rax; phKey
0x180021f7a  mov     rcx, [rcx+28h]
0x180021f7e  mov     rdx, [rcx+18h]
0x180021f82  mov     ecx, [rcx]; dwCertEncodingType
0x180021f84  add     rdx, 60h ; '`'; pInfo
0x180021f88  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x180021f8e  mov     r8d, eax
0x180021f91  mov     rax, [rsi+70h]
0x180021f95  mov     rcx, [rax+28h]
0x180021f99  add     rcx, 50h ; 'P'; Resource
0x180021f9d  test    r8d, r8d
0x180021fa0  jz      loc_1800222EC
0x180021fa6  call    cs:__imp_RtlReleaseResource
0x180021fac  mov     rcx, [rbp+0F0h+hObject]; hObject
0x180021fb0  lea     rax, [rbp+0F0h+pcbResult]
0x180021fb4  mov     [rsp+130h+dwFlags], r14d; dwFlags
0x180021fb9  lea     r8, [rbp+0F0h+pbOutput]; pbOutput
0x180021fbd  mov     r9d, 4; cbOutput
0x180021fc3  mov     [rsp+130h+phKey], rax; pcbResult
0x180021fc8  lea     rdx, aKeylength; "KeyLength"
0x180021fcf  call    cs:__imp_BCryptGetProperty
0x180021fd5  mov     edi, eax
0x180021fd7  test    eax, eax
0x180021fd9  jnz     loc_1800224AB
0x180021fdf  mov     eax, dword ptr [rbp+0F0h+pbOutput]
0x180021fe2  mov     edi, r14d
0x180021fe5  test    al, 7
0x180021fe7  setnz   dil
0x180021feb  shr     eax, 3
0x180021fee  add     edi, eax
0x180021ff0  lea     r14d, [rdi+rdi]
0x180021ff4  mov     ecx, r14d; uBytes
0x180021ff7  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x180021ffc  mov     rbx, rax
0x180021fff  test    rax, rax
0x180022002  jz      loc_18002244C
0x180022008  mov     esi, [rbp+0F0h+cbEncoded]
0x18002200e  lea     rax, [rbp+0F0h+cbSignature]
0x180022012  mov     [rsp+130h+pcbStructInfo], rax; pcbStructInfo
0x180022017  mov     r9d, esi; cbEncoded
0x18002201a  xor     eax, eax
0x18002201c  mov     r8, r15; pbEncoded
0x18002201f  mov     qword ptr [rsp+130h+dwFlags], rax; pvStructInfo
0x180022024  mov     edx, 2Fh ; '/'; lpszStructType
0x180022029  mov     ecx, 1; dwCertEncodingType
0x18002202e  mov     dword ptr [rsp+130h+phKey], eax; dwFlags
0x180022032  call    cs:__imp_CryptDecodeObject
0x180022038  test    eax, eax
0x18002203a  jz      loc_1800224BE
0x180022040  mov     ecx, [rbp+0F0h+cbSignature]; uBytes
0x180022043  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x180022048  mov     r13, rax
0x18002204b  test    rax, rax
0x18002204e  jz      loc_1800224A1
0x180022054  lea     rax, [rbp+0F0h+cbSignature]
0x180022058  mov     r9d, esi; cbEncoded
0x18002205b  mov     [rsp+130h+pcbStructInfo], rax; pcbStructInfo
0x180022060  mov     r8, r15; pbEncoded
0x180022063  mov     qword ptr [rsp+130h+dwFlags], r13; pvStructInfo
0x180022068  mov     edx, 2Fh ; '/'; lpszStructType
0x18002206d  mov     ecx, 1; dwCertEncodingType
0x180022072  mov     dword ptr [rsp+130h+phKey], 0; dwFlags
0x18002207a  call    cs:__imp_CryptDecodeObject
0x180022080  test    eax, eax
0x180022082  jz      loc_1800224CB
0x180022088  mov     r9d, [r13+0]
0x18002208c  cmp     r9d, edi
0x18002208f  ja      loc_180022456
0x180022095  cmp     [r13+10h], edi
0x180022099  ja      loc_180022456
0x18002209f  mov     rdx, [r13+8]; Src
0x1800220a3  mov     r8d, r9d; Size
0x1800220a6  mov     rcx, rbx; void *
0x1800220a9  call    memcpy_0
0x1800220ae  mov     r8d, [r13+10h]; Size
0x1800220b2  mov     rdx, [r13+18h]; Src
0x1800220b6  mov     ecx, edi
0x1800220b8  add     rcx, rbx; void *
0x1800220bb  call    memcpy_0
0x1800220c0  mov     r10d, edi
0x1800220c3  mov     [rbp+0F0h+cbSignature], r14d
0x1800220c7  shr     r10d, 1
0x1800220ca  mov     eax, 0
0x1800220cf  jz      short loc_1800220F4
0x1800220d1  mov     r8d, eax
0x1800220d4  mov     ecx, edi
0x1800220d6  sub     ecx, eax
0x1800220d8  inc     eax
0x1800220da  dec     ecx
0x1800220dc  mov     edx, ecx
0x1800220de  movzx   r9d, byte ptr [r8+rbx]
0x1800220e3  movzx   ecx, byte ptr [rcx+rbx]
0x1800220e7  mov     [r8+rbx], cl
0x1800220eb  mov     [rdx+rbx], r9b
0x1800220ef  cmp     eax, r10d
0x1800220f2  jb      short loc_1800220D1
0x1800220f4  mov     eax, [rbp+0F0h+cbSignature]
0x1800220f7  mov     r9d, 0
0x1800220fd  mov     r11d, eax
0x180022100  mov     r10d, eax
0x180022103  shr     r11d, 1
0x180022106  shr     r10, 1
0x180022109  mov     edi, r11d
0x18002210c  add     r10, rbx
0x18002210f  shr     edi, 1
0x180022111  jz      short loc_180022147
0x180022113  nop     dword ptr [rax+00h]
0x180022117  nop     word ptr [rax+rax+00000000h]
0x180022120  mov     edx, r9d
0x180022123  mov     eax, r11d
0x180022126  sub     eax, r9d
0x180022129  inc     r9d
0x18002212c  dec     eax
0x18002212e  mov     ecx, eax
0x180022130  movzx   r8d, byte ptr [rdx+r10]
0x180022135  movzx   eax, byte ptr [rax+r10]
0x18002213a  mov     [rdx+r10], al
0x18002213e  mov     [rcx+r10], r8b
0x180022142  cmp     r9d, edi
0x180022145  jb      short loc_180022120
0x180022147  test    r12d, r12d
0x18002214a  mov     [rbp+0F0h+hAlgorithm], 0
0x180022152  mov     ecx, 2
0x180022157  cmovnz  ecx, r12d
0x18002215b  call    MapTlsHashAlgorithmToIndex
0x180022160  mov     edx, cs:g_dwHashInfoTotalCount
0x180022166  mov     esi, eax
0x180022168  test    eax, eax
0x18002216a  js      loc_1800224EB
0x180022170  cmp     eax, edx
0x180022172  jge     loc_1800224EB
0x180022178  sub     eax, 1
0x18002217b  jz      loc_180022439
0x180022181  cmp     eax, 1
0x180022184  jz      loc_1800224D8
0x18002218a  mov     eax, esi
0x18002218c  lea     r15, __ImageBase
0x180022193  mov     rax, rva qword_1800AE610[r15+rax*8]
0x18002219b  mov     [rbp+0F0h+hAlgorithm], rax
0x18002219f  cmp     esi, edx
0x1800221a1  jnb     loc_180022486
0x1800221a7  lfence
0x1800221aa  mov     eax, esi
0x1800221ac  mov     rcx, rva g_pHashInfo[r15+rax*8]
0x1800221b4  test    rcx, rcx
0x1800221b7  jz      loc_180022486
0x1800221bd  mov     r14, [rbp+0F0h+hAlgorithm]
0x1800221c1  mov     r12d, [rcx+8]
0x1800221c5  test    r14, r14
0x1800221c8  jz      loc_1800224F2
0x1800221ce  xor     r15d, r15d
0x1800221d1  lea     rax, [rbp+0F0h+var_B4]
0x1800221d5  mov     [rsp+130h+dwFlags], r15d; dwFlags
0x1800221da  lea     r8, [rbp+0F0h+var_E0]; pbOutput
0x1800221de  mov     r9d, 4; cbOutput
0x1800221e4  mov     [rsp+130h+phKey], rax; pcbResult
0x1800221e9  lea     rdx, pszProperty; "ObjectLength"
0x1800221f0  mov     dword ptr [rbp+0F0h+var_E0], r15d
0x1800221f4  mov     rcx, r14; hObject
0x1800221f7  mov     [rbp+0F0h+var_B4], r15d
0x1800221fb  mov     [rbp+0F0h+phHash], r15
0x1800221ff  call    cs:__imp_BCryptGetProperty
0x180022205  mov     edi, eax
0x180022207  test    eax, eax
0x180022209  jnz     short loc_180022258
0x18002220b  mov     edi, dword ptr [rbp+0F0h+var_E0]
0x18002220e  mov     esi, r15d
0x180022211  test    rdi, rdi
0x180022214  jz      short loc_180022223
0x180022216  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18002221d  jbe     loc_180022319
0x180022223  lea     rcx, [rdi+8]
0x180022227  cmp     rcx, rdi
0x18002222a  jb      short loc_18002224A
0x18002222c  mov     rax, cs:g_pfnAllocate
0x180022233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022238  mov     rsi, rax
0x18002223b  test    rax, rax
0x18002223e  jz      short loc_180022253
0x180022240  mov     dword ptr [rax], 70616548h
0x180022246  add     rsi, 8
0x18002224a  test    rsi, rsi
0x18002224d  jnz     loc_180022381
0x180022253  mov     edi, 0Eh
0x180022258  mov     r14, [rbp+0F0h+var_D8]
0x18002225c  test    edi, edi
0x18002225e  jnz     loc_180022508
0x180022264  mov     eax, [rbp+0F0h+cbSignature]
0x180022267  lea     r8, [rbp+0F0h+pbHash]; pbHash
0x18002226b  mov     rcx, [rbp+0F0h+hObject]; hKey
0x18002226f  mov     r9d, r12d; cbHash
0x180022272  mov     dword ptr [rsp+130h+pcbStructInfo], r15d; dwFlags
0x180022277  xor     edx, edx; pPaddingInfo
0x180022279  mov     [rsp+130h+dwFlags], eax; cbSignature
0x18002227d  mov     [rsp+130h+phKey], rbx; pbSignature
0x180022282  call    cs:__imp_BCryptVerifySignature
0x180022288  mov     edi, eax
0x18002228a  test    eax, eax
0x18002228c  jnz     loc_18002251B
0x180022292  mov     rcx, [rbp+0F0h+hObject]; hKey
0x180022296  test    rcx, rcx
0x180022299  jz      short loc_1800222A1
0x18002229b  call    cs:__imp_BCryptDestroyKey
0x1800222a1  test    rbx, rbx
0x1800222a4  jnz     short loc_18002230F
0x1800222a6  test    r13, r13
0x1800222a9  jz      short loc_1800222C7
0x1800222ab  mov     rax, cs:LsaTable
0x1800222b2  mov     rcx, r13; hMem
0x1800222b5  test    rax, rax
0x1800222b8  jz      loc_180022496
0x1800222be  mov     rax, [rax+30h]
0x1800222c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222c7  mov     eax, edi
0x1800222c9  mov     rcx, [rbp+0F0h+var_50]
0x1800222d0  xor     rcx, rbp; StackCookie
0x1800222d3  call    __security_check_cookie
0x1800222d8  lea     rsp, [rbp+0B8h]
0x1800222df  pop     r15
0x1800222e1  pop     r14
0x1800222e3  pop     r13
0x1800222e5  pop     r12
0x1800222e7  pop     rdi
0x1800222e8  pop     rsi
0x1800222e9  pop     rbx
0x1800222ea  pop     rbp
0x1800222eb  retn
0x1800222ec  call    cs:__imp_RtlReleaseResource
0x1800222f2  call    cs:__imp_GetLastError
0x1800222f8  mov     r9b, 2Bh ; '+'
0x1800222fb  mov     edx, 453h
0x180022300  mov     edi, eax
0x180022302  mov     r8d, eax
0x180022305  mov     rcx, rsi
0x180022308  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18002230d  jmp     short loc_180022292
0x18002230f  mov     rcx, rbx; void *
0x180022312  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180022317  jmp     short loc_1800222A6
0x180022319  mov     rcx, cs:g_ulAdditionalProbeSize
0x180022320  add     rcx, 8
0x180022324  add     rcx, rdi
0x180022327  cmp     rcx, rdi
0x18002232a  jb      loc_180022223
0x180022330  call    VerifyStackAvailable
0x180022335  test    eax, eax
0x180022337  jz      loc_180022223
0x18002233d  lea     rax, [rdi+8]
0x180022341  lea     rcx, [rax+0Fh]
0x180022345  cmp     rcx, rax
0x180022348  ja      short loc_180022354
0x18002234a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180022354  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180022358  mov     rax, rcx
0x18002235b  call    _alloca_probe
0x180022360  sub     rsp, rcx
0x180022363  lea     rsi, [rsp+130h+cbSignature]
0x180022368  test    rsi, rsi
0x18002236b  jz      loc_180022223
0x180022371  mov     dword ptr [rsi], 6B637453h
0x180022377  add     rsi, 8
0x18002237b  jz      loc_180022223
0x180022381  mov     r9d, dword ptr [rbp+0F0h+var_E0]; cbHashObject
0x180022385  lea     rdx, [rbp+0F0h+phHash]; phHash
  ... truncated ...
```
