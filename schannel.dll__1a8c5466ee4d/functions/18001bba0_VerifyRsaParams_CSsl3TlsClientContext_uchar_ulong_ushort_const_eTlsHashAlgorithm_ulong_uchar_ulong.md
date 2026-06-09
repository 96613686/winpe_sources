# VerifyRsaParams(CSsl3TlsClientContext *,uchar *,ulong,ushort const *,_eTlsHashAlgorithm,ulong,uchar *,ulong)

- ea: `0x18001bba0`
- end: `0x18001c056`
- name: `?VerifyRsaParams@@YAKPEAVCSsl3TlsClientContext@@PEAEKPEBGW4_eTlsHashAlgorithm@@K1K@Z`
- size: `1206`
- prototype: `__int64 __fastcall(UCHAR *, unsigned __int8 *, ULONG, const unsigned __int16 *, enum _eTlsHashAlgorithm, ULONG, unsigned __int8 *, ULONG cbSignature)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004eae8`

## callees

- `0x18001bba0`
- `0x18001d960`
- `0x18001db60`
- `0x1800214f0`
- `0x1800597b0`
- `0x18005a160`
- `0x1800889d0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf26`
- `ntdll!RtlReleaseResource` at `0x18001be83`
- `ntdll!RtlReleaseResource` at `0x18001bf20`
- `ntdll!RtlReleaseResource` at `0x18001be83`
- `ntdll!RtlReleaseResource` at `0x18001bf20`
- `ntdll!RtlAcquireResourceShared` at `0x18001be39`
- `ntdll!RtlAcquireResourceShared` at `0x18001be39`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18001be67`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18001be67`
- `bcrypt!BCryptGetProperty` at `0x18001bce8`
- `bcrypt!BCryptGetProperty` at `0x18001bce8`
- `bcrypt!BCryptCreateHash` at `0x18001bd98`
- `bcrypt!BCryptCreateHash` at `0x18001bd98`
- `bcrypt!BCryptHashData` at `0x18001bdb8`
- `bcrypt!BCryptHashData` at `0x18001bdd2`
- `bcrypt!BCryptHashData` at `0x18001bdb8`
- `bcrypt!BCryptHashData` at `0x18001bdd2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008bb05`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008bb05`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008baca`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008baca`
- `bcrypt!BCryptFinishHash` at `0x18001bdec`
- `bcrypt!BCryptFinishHash` at `0x18001bdec`
- `bcrypt!BCryptDestroyKey` at `0x18001bed0`
- `bcrypt!BCryptDestroyKey` at `0x18001bed0`
- `bcrypt!BCryptDestroyHash` at `0x18001bdfd`
- `bcrypt!BCryptDestroyHash` at `0x18001bdfd`
- `bcrypt!BCryptVerifySignature` at `0x18001beb7`
- `bcrypt!BCryptVerifySignature` at `0x18001beb7`

## pseudocode

```c
__int64 __fastcall VerifyRsaParams(
        UCHAR *a1,
        unsigned __int8 *a2,
        ULONG a3,
        const unsigned __int16 *a4,
        enum _eTlsHashAlgorithm a5,
        ULONG a6,
        unsigned __int8 *a7,
        ULONG cbSignature)
{
  UCHAR *v8; // r14
  __int64 v13; // r9
  unsigned int v14; // eax
  int v15; // edi
  __int64 v16; // rdx
  BCRYPT_ALG_HANDLE v17; // rax
  __int64 v18; // rcx
  BCRYPT_HANDLE v19; // r14
  ULONG v20; // esi
  unsigned int Hash; // ebx
  unsigned __int64 v22; // rbx
  UCHAR *p_hObject; // rdi
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  BOOL v29; // eax
  struct _RTL_RESOURCE *v30; // rcx
  const unsigned __int16 **p_pPaddingInfo; // rdx
  DWORD LastError; // eax
  __int64 v33; // r9
  _DWORD *v35; // rax
  __int64 v36; // [rsp+0h] [rbp-40h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+40h] [rbp+0h] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp+8h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp+10h] BYREF
  ULONG pcbResult; // [rsp+58h] [rbp+18h] BYREF
  ULONG cbInput; // [rsp+5Ch] [rbp+1Ch]
  PUCHAR pbSignature; // [rsp+60h] [rbp+20h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp+28h] BYREF
  const unsigned __int16 *v44; // [rsp+70h] [rbp+30h] BYREF
  __int128 pPaddingInfo; // [rsp+78h] [rbp+38h] BYREF
  UCHAR pbHash[16]; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int8 v47[48]; // [rsp+A0h] [rbp+60h] BYREF

  v8 = a7;
  cbInput = a3;
  pbSignature = a7;
  phKey = 0;
  memset_0(pbHash, 0, 0x40u);
  v13 = (unsigned int)a5;
  v44 = 0;
  pPaddingInfo = 0;
  if ( a5 == TlsHashAlgorithm_None )
  {
    v20 = 36;
    Hash = GenerateHash(g_hMD5Provider, (struct CSsl3TlsContext *)a1, a2, a3, pbHash, 0x10u);
    if ( !Hash )
      Hash = GenerateHash(g_hSHAProvider, (struct CSsl3TlsContext *)a1, a2, a3, v47, 0x14u);
    a6 = 2;
    goto LABEL_35;
  }
  v14 = 0;
  v15 = g_dwHashInfoTotalCount;
  hObject = 0;
  while ( v14 < g_dwHashInfoTotalCount )
  {
    v16 = g_pHashInfo[v14];
    if ( v16 && *(_DWORD *)(v16 + 20) == a5 )
    {
      v15 = v14;
      break;
    }
    ++v14;
  }
  if ( v15 < 0 || v15 >= g_dwHashInfoTotalCount )
  {
    v15 = 0;
  }
  else
  {
    if ( v15 == 1 )
    {
      v17 = g_hMD5Provider;
      goto LABEL_13;
    }
    if ( v15 == 2 )
    {
      v17 = g_hSHAProvider;
      goto LABEL_13;
    }
  }
  v17 = (BCRYPT_ALG_HANDLE)qword_1800AE610[v15];
LABEL_13:
  hObject = v17;
  if ( v15 < (unsigned int)g_dwHashInfoTotalCount && (_mm_lfence(), (v18 = g_pHashInfo[v15]) != 0) )
  {
    v19 = hObject;
    v20 = *(_DWORD *)(v18 + 8);
    if ( hObject )
      goto LABEL_16;
    if ( *(_QWORD *)v18 )
    {
      Hash = BCryptOpenAlgorithmProvider(&hObject, *(LPCWSTR *)v18, 0, 0);
      if ( Hash )
        goto LABEL_34;
      v19 = (BCRYPT_HANDLE)_InterlockedCompareExchange64(&qword_1800AE610[v15], (signed __int64)hObject, 0);
      if ( v19 )
      {
        BCryptCloseAlgorithmProvider(hObject, 0);
        hObject = v19;
      }
      else
      {
        v19 = hObject;
      }
LABEL_16:
      *(_DWORD *)pbOutput = 0;
      pcbResult = 0;
      phHash = 0;
      Hash = BCryptGetProperty(v19, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
      if ( Hash )
      {
LABEL_34:
        v8 = pbSignature;
        goto LABEL_35;
      }
      v22 = *(unsigned int *)pbOutput;
      p_hObject = 0;
      if ( *(_DWORD *)pbOutput
        && *(unsigned int *)pbOutput <= (unsigned __int64)g_ulMaxStackAllocSize
        && (unsigned __int64)*(unsigned int *)pbOutput + g_ulAdditionalProbeSize + 8 >= *(unsigned int *)pbOutput
        && (unsigned int)VerifyStackAvailable() )
      {
        v24 = v22 + 23;
        if ( v22 + 23 <= v22 + 8 )
          v24 = 0xFFFFFFFFFFFFFF0LL;
        v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
        v26 = alloca(v25);
        v27 = alloca(v25);
        p_hObject = (UCHAR *)&hObject;
        if ( &v36 != (__int64 *)-64LL )
        {
          LODWORD(hObject) = 1801679955;
          p_hObject = pbOutput;
          if ( pbOutput )
            goto LABEL_25;
        }
      }
      if ( v22 + 8 >= v22 )
      {
        v35 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        if ( !v35 )
        {
LABEL_55:
          Hash = 14;
          goto LABEL_34;
        }
        *v35 = 1885431112;
        p_hObject = (UCHAR *)(v35 + 2);
      }
      if ( p_hObject )
      {
LABEL_25:
        Hash = BCryptCreateHash(v19, &phHash, p_hObject, *(ULONG *)pbOutput, 0, 0, 0);
        if ( !Hash )
        {
          Hash = BCryptHashData(phHash, a1 + 1992, 0x40u, 0);
          if ( !Hash )
          {
            Hash = BCryptHashData(phHash, a2, cbInput, 0);
            if ( !Hash )
              Hash = BCryptFinishHash(phHash, pbHash, v20, 0);
          }
        }
        if ( phHash )
          BCryptDestroyHash(phHash);
        if ( p_hObject && *((_DWORD *)p_hObject - 2) == 1885431112 )
          ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_hObject - 8);
        goto LABEL_34;
      }
      goto LABEL_55;
    }
    v8 = pbSignature;
    Hash = 1359;
  }
  else
  {
    Hash = 1168;
    v20 = 0;
  }
LABEL_35:
  if ( Hash )
  {
    LOBYTE(v13) = 80;
    CSslContext::SetErrorAndFatalAlert(a1, 1105, Hash, v13);
  }
  else
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 40LL) + 80LL), 1u);
    v29 = CryptImportPublicKeyInfoEx2(
            **(_DWORD **)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 40LL) + 40LL),
            (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 40LL) + 40LL) + 24LL)
                                  + 96LL),
            0x80000000,
            0,
            &phKey);
    v30 = (struct _RTL_RESOURCE *)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 40LL) + 80LL);
    if ( !v29 )
    {
      RtlReleaseResource(v30);
      LastError = GetLastError();
      Hash = LastError;
      LOBYTE(v33) = 43;
LABEL_47:
      CSslContext::SetErrorAndFatalAlert(a1, 1106, LastError, v33);
      goto LABEL_40;
    }
    RtlReleaseResource(v30);
    if ( a6 == 8 )
    {
      p_pPaddingInfo = (const unsigned __int16 **)&pPaddingInfo;
      *(_QWORD *)&pPaddingInfo = a4;
      DWORD2(pPaddingInfo) = v20;
LABEL_39:
      LastError = BCryptVerifySignature(phKey, p_pPaddingInfo, pbHash, v20, v8, cbSignature, a6);
      Hash = LastError;
      if ( !LastError )
        goto LABEL_40;
      LOBYTE(v33) = 51;
      goto LABEL_47;
    }
    if ( a6 == 2 )
    {
      p_pPaddingInfo = &v44;
      v44 = a4;
      goto LABEL_39;
    }
    Hash = -2146893052;
  }
LABEL_40:
  if ( phKey )
    BCryptDestroyKey(phKey);
  return Hash;
}

```

## disassembly

```asm
0x18001bba0  push    rbp
0x18001bba2  push    rsi
0x18001bba3  push    rdi
0x18001bba4  push    r12
0x18001bba6  push    r13
0x18001bba8  push    r14
0x18001bbaa  push    r15
0x18001bbac  sub     rsp, 0E0h
0x18001bbb3  lea     rbp, [rsp+40h]
0x18001bbb8  mov     [rbp+0D0h+arg_18], rbx
0x18001bbbf  mov     rax, cs:__security_cookie
0x18001bbc6  xor     rax, rbp
0x18001bbc9  mov     [rbp+0D0h+var_40], rax
0x18001bbd0  mov     r14, [rbp+0D0h+arg_30]
0x18001bbd7  mov     edi, r8d
0x18001bbda  mov     [rbp+0D0h+cbInput], r8d
0x18001bbde  mov     r12, rdx
0x18001bbe1  mov     r13, rcx
0x18001bbe4  mov     [rbp+0D0h+pbSignature], r14
0x18001bbe8  xor     ebx, ebx
0x18001bbea  lea     rcx, [rbp+0D0h+pbHash]; void *
0x18001bbee  xor     edx, edx; Val
0x18001bbf0  mov     [rbp+0D0h+phKey], rbx
0x18001bbf4  mov     r8d, 40h ; '@'; Size
0x18001bbfa  mov     r15, r9
0x18001bbfd  call    memset_0
0x18001bc02  mov     r9d, [rbp+0D0h+arg_20]
0x18001bc09  xorps   xmm0, xmm0
0x18001bc0c  mov     [rbp+0D0h+var_A0], rbx
0x18001bc10  movups  [rbp+0D0h+pPaddingInfo], xmm0
0x18001bc14  test    r9d, r9d
0x18001bc17  jz      loc_18001BF5B
0x18001bc1d  mov     r8d, cs:g_dwHashInfoTotalCount
0x18001bc24  mov     eax, ebx
0x18001bc26  mov     edi, r8d
0x18001bc29  mov     [rbp+0D0h+hObject], rbx
0x18001bc2d  lea     rdx, __ImageBase
0x18001bc34  cmp     eax, r8d
0x18001bc37  jnb     short loc_18001BC5B
0x18001bc39  mov     ecx, eax
0x18001bc3b  mov     rdx, rva g_pHashInfo[rdx+rcx*8]
0x18001bc43  test    rdx, rdx
0x18001bc46  jz      short loc_18001BC4E
0x18001bc48  cmp     [rdx+14h], r9d
0x18001bc4c  jz      short loc_18001BC52
0x18001bc4e  inc     eax
0x18001bc50  jmp     short loc_18001BC2D
0x18001bc52  mov     edi, eax
0x18001bc54  lea     rdx, __ImageBase
0x18001bc5b  test    edi, edi
0x18001bc5d  js      loc_18001BFF3
0x18001bc63  cmp     edi, r8d
0x18001bc66  jge     loc_18001BFF3
0x18001bc6c  mov     ecx, edi
0x18001bc6e  sub     ecx, 1
0x18001bc71  jz      loc_18001BF14
0x18001bc77  cmp     ecx, 1
0x18001bc7a  jz      loc_18001BFE7
0x18001bc80  mov     eax, edi
0x18001bc82  mov     rax, rva qword_1800AE610[rdx+rax*8]
0x18001bc8a  mov     [rbp+0D0h+hObject], rax
0x18001bc8e  cmp     edi, r8d
0x18001bc91  jnb     loc_18001BFBE
0x18001bc97  lfence
0x18001bc9a  mov     eax, edi
0x18001bc9c  mov     rcx, rva g_pHashInfo[rdx+rax*8]
0x18001bca4  test    rcx, rcx
0x18001bca7  jz      loc_18001BFBE
0x18001bcad  mov     r14, [rbp+0D0h+hObject]
0x18001bcb1  mov     esi, [rcx+8]
0x18001bcb4  test    r14, r14
0x18001bcb7  jz      loc_18001BFFA
0x18001bcbd  lea     rax, [rbp+0D0h+var_B8]
0x18001bcc1  mov     [rsp+110h+dwFlags], ebx; dwFlags
0x18001bcc5  mov     r9d, 4; cbOutput
0x18001bccb  mov     [rsp+110h+pcbResult], rax; pcbResult
0x18001bcd0  lea     r8, [rbp+0D0h+pbOutput]; pbOutput
0x18001bcd4  mov     dword ptr [rbp+0D0h+pbOutput], ebx
0x18001bcd7  lea     rdx, pszProperty; "ObjectLength"
0x18001bcde  mov     [rbp+0D0h+var_B8], ebx
0x18001bce1  mov     rcx, r14; hObject
0x18001bce4  mov     [rbp+0D0h+phHash], rbx
0x18001bce8  call    cs:__imp_BCryptGetProperty
0x18001bcee  mov     ebx, eax
0x18001bcf0  test    eax, eax
0x18001bcf2  jnz     loc_18001BE19
0x18001bcf8  mov     ebx, dword ptr [rbp+0D0h+pbOutput]
0x18001bcfb  xor     edi, edi
0x18001bcfd  test    rbx, rbx
0x18001bd00  jz      loc_18001C014
0x18001bd06  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001bd0d  ja      loc_18001C014
0x18001bd13  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001bd1a  add     rcx, 8
0x18001bd1e  add     rcx, rbx
0x18001bd21  cmp     rcx, rbx
0x18001bd24  jb      loc_18001C014
0x18001bd2a  call    VerifyStackAvailable
0x18001bd2f  test    eax, eax
0x18001bd31  jz      loc_18001C014
0x18001bd37  lea     rax, [rbx+8]
0x18001bd3b  lea     rcx, [rax+0Fh]
0x18001bd3f  cmp     rcx, rax
0x18001bd42  ja      short loc_18001BD4E
0x18001bd44  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001bd4e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001bd52  mov     rax, rcx
0x18001bd55  call    _alloca_probe
0x18001bd5a  sub     rsp, rcx
0x18001bd5d  lea     rdi, [rsp+110h+hObject]
0x18001bd62  test    rdi, rdi
0x18001bd65  jz      loc_18001C014
0x18001bd6b  mov     dword ptr [rdi], 6B637453h
0x18001bd71  add     rdi, 8
0x18001bd75  jz      loc_18001C014
0x18001bd7b  mov     r9d, dword ptr [rbp+0D0h+pbOutput]; cbHashObject
0x18001bd7f  lea     rdx, [rbp+0D0h+phHash]; phHash
0x18001bd83  xor     eax, eax
0x18001bd85  mov     r8, rdi; pbHashObject
0x18001bd88  mov     [rsp+110h+var_E0], eax; dwFlags
0x18001bd8c  mov     rcx, r14; hAlgorithm
0x18001bd8f  mov     [rsp+110h+dwFlags], eax; cbSecret
0x18001bd93  mov     [rsp+110h+pcbResult], rax; pbSecret
0x18001bd98  call    cs:__imp_BCryptCreateHash
0x18001bd9e  mov     ebx, eax
0x18001bda0  test    eax, eax
0x18001bda2  jnz     short loc_18001BDF4
0x18001bda4  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18001bda8  lea     rdx, [r13+7C8h]; pbInput
0x18001bdaf  xor     r9d, r9d; dwFlags
0x18001bdb2  mov     r8d, 40h ; '@'; cbInput
0x18001bdb8  call    cs:__imp_BCryptHashData
0x18001bdbe  mov     ebx, eax
0x18001bdc0  test    eax, eax
0x18001bdc2  jnz     short loc_18001BDF4
0x18001bdc4  mov     r8d, [rbp+0D0h+cbInput]; cbInput
0x18001bdc8  xor     r9d, r9d; dwFlags
0x18001bdcb  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18001bdcf  mov     rdx, r12; pbInput
0x18001bdd2  call    cs:__imp_BCryptHashData
0x18001bdd8  mov     ebx, eax
0x18001bdda  test    eax, eax
0x18001bddc  jnz     short loc_18001BDF4
0x18001bdde  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18001bde2  lea     rdx, [rbp+0D0h+pbHash]; pbOutput
0x18001bde6  xor     r9d, r9d; dwFlags
0x18001bde9  mov     r8d, esi; cbOutput
0x18001bdec  call    cs:__imp_BCryptFinishHash
0x18001bdf2  mov     ebx, eax
0x18001bdf4  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18001bdf8  test    rcx, rcx
0x18001bdfb  jz      short loc_18001BE03
0x18001bdfd  call    cs:__imp_BCryptDestroyHash
0x18001be03  test    rdi, rdi
0x18001be06  jz      short loc_18001BE19
0x18001be08  cmp     dword ptr [rdi-8], 70616548h
0x18001be0f  lea     rcx, [rdi-8]
0x18001be13  jz      loc_18001C03D
0x18001be19  mov     r14, [rbp+0D0h+pbSignature]
0x18001be1d  mov     edi, [rbp+0D0h+arg_28]
0x18001be23  test    ebx, ebx
0x18001be25  jnz     loc_18001BF43
0x18001be2b  mov     rax, [r13+70h]
0x18001be2f  mov     dl, 1; Wait
0x18001be31  mov     rcx, [rax+28h]
0x18001be35  add     rcx, 50h ; 'P'; Resource
0x18001be39  call    cs:__imp_RtlAcquireResourceShared
0x18001be3f  mov     rax, [r13+70h]
0x18001be43  xor     r9d, r9d; pvAuxInfo
0x18001be46  mov     r8d, 80000000h; dwFlags
0x18001be4c  mov     rcx, [rax+28h]
0x18001be50  lea     rax, [rbp+0D0h+phKey]
0x18001be54  mov     [rsp+110h+pcbResult], rax; phKey
0x18001be59  mov     rcx, [rcx+28h]
0x18001be5d  mov     rdx, [rcx+18h]
0x18001be61  mov     ecx, [rcx]; dwCertEncodingType
0x18001be63  add     rdx, 60h ; '`'; pInfo
0x18001be67  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x18001be6d  mov     edx, eax
0x18001be6f  mov     rax, [r13+70h]
0x18001be73  mov     rcx, [rax+28h]
0x18001be77  add     rcx, 50h ; 'P'; Resource
0x18001be7b  test    edx, edx
0x18001be7d  jz      loc_18001BF20
0x18001be83  call    cs:__imp_RtlReleaseResource
0x18001be89  cmp     edi, 8
0x18001be8c  jnz     short loc_18001BF01
0x18001be8e  lea     rdx, [rbp+0D0h+pPaddingInfo]; pPaddingInfo
0x18001be92  mov     qword ptr [rbp+0D0h+pPaddingInfo], r15
0x18001be96  mov     dword ptr [rbp+0D0h+pPaddingInfo+8], esi
0x18001be99  mov     eax, [rbp+0D0h+cbSignature]
0x18001be9f  lea     r8, [rbp+0D0h+pbHash]; pbHash
0x18001bea3  mov     rcx, [rbp+0D0h+phKey]; hKey
0x18001bea7  mov     r9d, esi; cbHash
0x18001beaa  mov     [rsp+110h+var_E0], edi; dwFlags
0x18001beae  mov     [rsp+110h+dwFlags], eax; cbSignature
0x18001beb2  mov     [rsp+110h+pcbResult], r14; pbSignature
0x18001beb7  call    cs:__imp_BCryptVerifySignature
0x18001bebd  mov     ebx, eax
0x18001bebf  test    eax, eax
0x18001bec1  jnz     loc_18001C04E
0x18001bec7  mov     rcx, [rbp+0D0h+phKey]; hKey
0x18001becb  test    rcx, rcx
0x18001bece  jz      short loc_18001BED6
0x18001bed0  call    cs:__imp_BCryptDestroyKey
0x18001bed6  mov     eax, ebx
0x18001bed8  mov     rcx, [rbp+0D0h+var_40]
0x18001bedf  xor     rcx, rbp; StackCookie
0x18001bee2  call    __security_check_cookie
0x18001bee7  mov     rbx, [rbp+0D0h+arg_18]
0x18001beee  lea     rsp, [rbp+0A0h]
0x18001bef5  pop     r15
0x18001bef7  pop     r14
0x18001bef9  pop     r13
0x18001befb  pop     r12
0x18001befd  pop     rdi
0x18001befe  pop     rsi
0x18001beff  pop     rbp
0x18001bf00  retn
0x18001bf01  cmp     edi, 2
0x18001bf04  jnz     loc_18001BFCA
0x18001bf0a  lea     rdx, [rbp+0D0h+var_A0]
0x18001bf0e  mov     [rbp+0D0h+var_A0], r15
0x18001bf12  jmp     short loc_18001BE99
0x18001bf14  mov     rax, cs:?g_hMD5Provider@@3PEAXEA; void * g_hMD5Provider
0x18001bf1b  jmp     loc_18001BC8A
0x18001bf20  call    cs:__imp_RtlReleaseResource
0x18001bf26  call    cs:__imp_GetLastError
0x18001bf2c  mov     ebx, eax
0x18001bf2e  mov     r9b, 2Bh ; '+'
0x18001bf31  mov     r8d, eax
0x18001bf34  mov     edx, 452h
0x18001bf39  mov     rcx, r13
0x18001bf3c  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18001bf41  jmp     short loc_18001BEC7
0x18001bf43  mov     r9b, 50h ; 'P'
0x18001bf46  mov     r8d, ebx
0x18001bf49  mov     edx, 451h
0x18001bf4e  mov     rcx, r13
0x18001bf51  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18001bf56  jmp     loc_18001BEC7
0x18001bf5b  mov     rcx, cs:?g_hMD5Provider@@3PEAXEA; hAlgorithm
0x18001bf62  lea     rax, [rbp+0D0h+pbHash]
0x18001bf66  mov     [rsp+110h+dwFlags], 10h; unsigned int
0x18001bf6e  mov     r9d, edi; unsigned int
0x18001bf71  mov     r8, r12; unsigned __int8 *
0x18001bf74  mov     [rsp+110h+pcbResult], rax; unsigned __int8 *
0x18001bf79  mov     rdx, r13; struct CSsl3TlsContext *
0x18001bf7c  mov     esi, 24h ; '$'
0x18001bf81  call    ?GenerateHash@@YAKPEAXPEAVCSsl3TlsContext@@PEAEK2K@Z; GenerateHash(void *,CSsl3TlsContext *,uchar *,ulong,uchar *,ulong)
0x18001bf86  mov     ebx, eax
0x18001bf88  test    eax, eax
0x18001bf8a  jnz     short loc_18001BFB4
0x18001bf8c  mov     rcx, cs:?g_hSHAProvider@@3PEAXEA; hAlgorithm
0x18001bf93  lea     rax, [rbp+0D0h+var_70]
0x18001bf97  mov     [rsp+110h+dwFlags], 14h; unsigned int
0x18001bf9f  mov     r9d, edi; unsigned int
0x18001bfa2  mov     r8, r12; unsigned __int8 *
0x18001bfa5  mov     [rsp+110h+pcbResult], rax; unsigned __int8 *
0x18001bfaa  mov     rdx, r13; struct CSsl3TlsContext *
0x18001bfad  call    ?GenerateHash@@YAKPEAXPEAVCSsl3TlsContext@@PEAEK2K@Z; GenerateHash(void *,CSsl3TlsContext *,uchar *,ulong,uchar *,ulong)
0x18001bfb2  mov     ebx, eax
0x18001bfb4  mov     edi, 2
0x18001bfb9  jmp     loc_18001BE23
0x18001bfbe  mov     ebx, 490h
0x18001bfc3  xor     esi, esi
0x18001bfc5  jmp     loc_18001BE1D
0x18001bfca  mov     ebx, 80090304h
0x18001bfcf  jmp     loc_18001BEC7
0x18001bfd4  test    rdi, rdi
0x18001bfd7  jnz     loc_18001BD7B
0x18001bfdd  mov     ebx, 0Eh
0x18001bfe2  jmp     loc_18001BE19
0x18001bfe7  mov     rax, cs:?g_hSHAProvider@@3PEAXEA; void * g_hSHAProvider
0x18001bfee  jmp     loc_18001BC8A
0x18001bff3  mov     edi, ebx
0x18001bff5  jmp     loc_18001BC80
0x18001bffa  mov     rdx, [rcx]; pszAlgId
0x18001bffd  test    rdx, rdx
0x18001c000  jnz     loc_18008BAC0
0x18001c006  mov     r14, [rbp+0D0h+pbSignature]
0x18001c00a  mov     ebx, 54Fh
0x18001c00f  jmp     loc_18001BE1D
0x18001c014  lea     rcx, [rbx+8]
0x18001c018  cmp     rcx, rbx
0x18001c01b  jb      short loc_18001BFD4
0x18001c01d  mov     rax, cs:g_pfnAllocate
0x18001c024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c029  mov     rdi, rax
0x18001c02c  test    rax, rax
0x18001c02f  jz      short loc_18001BFDD
0x18001c031  mov     dword ptr [rax], 70616548h
0x18001c037  add     rdi, 8
0x18001c03b  jmp     short loc_18001BFD4
0x18001c03d  mov     rax, cs:g_pfnFree
0x18001c044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c049  jmp     loc_18001BE19
0x18001c04e  mov     r9b, 33h ; '3'
0x18001c051  jmp     loc_18001BF31
0x18008bac0  xor     r9d, r9d; dwFlags
  ... truncated ...
```
