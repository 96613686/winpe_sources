# SignHashCallback

- ea: `0x18006e7b0`
- end: `0x18006ee7a`
- name: `SignHashCallback`
- size: `1738`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180014240`
- `0x180021da8`
- `0x180021eb0`
- `0x180025c38`
- `0x180057c8c`
- `0x18005c3a0`
- `0x18006de50`
- `0x18006e7b0`
- `0x180088a3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ec64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ecae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ecfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ede3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ec64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ecae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ecfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ede3`
- `ncrypt!NCryptSetProperty` at `0x18006ea9e`
- `ncrypt!NCryptSetProperty` at `0x18006ea9e`
- `ncrypt!NCryptSignHash` at `0x18006eb09`
- `ncrypt!NCryptSignHash` at `0x18006eb91`
- `ncrypt!NCryptSignHash` at `0x18006eb09`
- `ncrypt!NCryptSignHash` at `0x18006eb91`
- `CRYPTSP!CryptSetProvParam` at `0x18006ec48`
- `CRYPTSP!CryptSetProvParam` at `0x18006ec48`
- `CRYPTSP!CryptCreateHash` at `0x18006eca4`
- `CRYPTSP!CryptCreateHash` at `0x18006eca4`
- `CRYPTSP!CryptHashData` at `0x18006ed29`
- `CRYPTSP!CryptHashData` at `0x18006ed29`
- `CRYPTSP!CryptSetHashParam` at `0x18006ecf0`
- `CRYPTSP!CryptSetHashParam` at `0x18006ecf0`
- `CRYPTSP!CryptDestroyHash` at `0x18006ee49`
- `CRYPTSP!CryptDestroyHash` at `0x18006ee49`
- `CRYPTSP!CryptSignHashW` at `0x18006ed78`
- `CRYPTSP!CryptSignHashW` at `0x18006edd9`
- `CRYPTSP!CryptSignHashW` at `0x18006ed78`
- `CRYPTSP!CryptSignHashW` at `0x18006edd9`

## pseudocode

```c
__int64 __fastcall SignHashCallback(NCRYPT_HANDLE a1, __int64 a2, __int64 a3, DWORD *a4)
{
  unsigned int v4; // r14d
  unsigned int v7; // r15d
  CCipherMill *v8; // rbx
  unsigned int v9; // r14d
  unsigned int *v11; // rcx
  __int64 v12; // r9
  DWORD v13; // r8d
  DWORD v14; // r12d
  __int64 v15; // rsi
  __int64 v16; // r15
  DWORD v17; // r13d
  unsigned int v18; // eax
  unsigned int v19; // ecx
  __int64 v20; // r14
  __int64 v21; // rcx
  const wchar_t *v22; // r9
  __int64 *v23; // rsi
  BYTE *v24; // r15
  NCRYPT_KEY_HANDLE v25; // r14
  unsigned int v26; // eax
  unsigned int v27; // ebx
  BYTE *v28; // rax
  CCipherMill *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r9
  HCRYPTPROV v32; // r14
  DWORD LastError; // eax
  DWORD v34; // eax
  DWORD v35; // ebx
  BYTE *v36; // rax
  void *v37; // rcx
  DWORD cbSignature; // [rsp+28h] [rbp-48h]
  DWORD dwKeySpec; // [rsp+40h] [rbp-30h] BYREF
  ALG_ID Algid; // [rsp+44h] [rbp-2Ch]
  __int64 v41; // [rsp+48h] [rbp-28h] BYREF
  HCRYPTHASH phHash; // [rsp+50h] [rbp-20h] BYREF
  BYTE pbInput[8]; // [rsp+58h] [rbp-18h] BYREF
  __int128 v44; // [rsp+60h] [rbp-10h] BYREF

  v4 = a1;
  phHash = 0;
  *(_QWORD *)pbInput = 0;
  v7 = a2;
  if ( !(unsigned int)SchannelInit(1) || !a3 || !a4 )
    return 1359;
  *(_QWORD *)a4 = 0;
  *((_QWORD *)a4 + 1) = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != (CCipherMill *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v8 + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v8 + 2), 21, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, v4);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v8 + 2), 22, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, v7);
        v8 = WPP_GLOBAL_Control;
      }
    }
  }
  v9 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 < 0x24u )
    return 2148074264LL;
  v11 = *(unsigned int **)(a3 + 8);
  v12 = *v11;
  v13 = v11[2];
  v14 = v11[1];
  *(_QWORD *)pbInput = *(_QWORD *)(v11 + 3);
  LODWORD(v41) = v11[5];
  v15 = v11[6];
  Algid = v12;
  dwKeySpec = v13;
  *(_QWORD *)&v44 = v11 + 7;
  v16 = v11[7];
  v17 = v11[8];
  if ( v8 != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v8 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v8 + 2), 23, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, v12);
      v13 = dwKeySpec;
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v8 + 2), 24, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, v13);
      v8 = WPP_GLOBAL_Control;
    }
  }
  v18 = v15 + 24;
  if ( (unsigned int)v15 < 0xFFFFFFE8 )
  {
    v19 = v18 + v16;
    if ( v18 + (unsigned int)v16 >= v18 && v19 + v17 >= v19 )
    {
      if ( v9 < v19 + v17 )
        return 1359;
      v20 = 0;
      v21 = v44 + 8 + v15;
      if ( !(_DWORD)v15 )
        v21 = v44 + 8;
      v22 = (const wchar_t *)((v44 + 8) & -(__int64)((_DWORD)v15 != 0));
      if ( (_DWORD)v16 )
      {
        if ( (v15 & 1) != 0 )
          return 1359;
        v20 = v21;
        v21 += v16;
      }
      v23 = 0;
      v24 = (BYTE *)(v21 & -(__int64)(v17 != 0));
      if ( a2 )
      {
        dwKeySpec = 0;
        v41 = 0;
        v44 = 0;
        if ( !v22 || !v24 )
          return 1359;
        if ( wcsncmp_0(v22, L"RSA", 3u) )
          goto LABEL_43;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH>::GetImpl'::`2'::impl) )
        {
          if ( (v14 & 8) != 0 )
          {
LABEL_36:
            v23 = (__int64 *)&v44;
            *(_QWORD *)&v44 = v20;
            DWORD2(v44) = v17;
LABEL_42:
            v8 = WPP_GLOBAL_Control;
LABEL_43:
            if ( *(_QWORD *)pbInput )
            {
              if ( v8 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
                WPP_SF_q(*((_QWORD *)v8 + 2), 25, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, *(_QWORD *)pbInput);
              v25 = a1;
              v26 = NCryptSetProperty(a1, L"HWND Handle", pbInput, 8u, 0);
              if ( v26
                && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, v26);
              }
            }
            else
            {
              v25 = a1;
            }
            v27 = NCryptSignHash(v25, v23, v24, v17, 0, dwKeySpec, &dwKeySpec, v14);
            if ( v27 )
            {
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, v27);
              }
              return v27;
            }
            v28 = (BYTE *)SPExternalAlloc(dwKeySpec);
            *((_QWORD *)a4 + 1) = v28;
            if ( !v28 )
              return 14;
            cbSignature = dwKeySpec;
            *a4 = dwKeySpec;
            v27 = NCryptSignHash(v25, v23, v24, v17, v28, cbSignature, &dwKeySpec, v14);
            if ( v27 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_104;
              }
              v30 = 28;
              v31 = v27;
              goto LABEL_63;
            }
LABEL_101:
            a4[1] = 1;
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids);
            }
            goto LABEL_104;
          }
          if ( (v14 & 2) == 0 )
            return 1359;
        }
        else
        {
          if ( v14 == 8 )
            goto LABEL_36;
          if ( v14 != 2 )
            return 1359;
        }
        v41 = v20;
        v23 = &v41;
        goto LABEL_42;
      }
      if ( v8 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)v8 + 2), 29, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids);
        v8 = WPP_GLOBAL_Control;
      }
      if ( *(_QWORD *)pbInput )
      {
        if ( v8 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
          WPP_SF_q(*((_QWORD *)v8 + 2), 30, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, *(_QWORD *)pbInput);
        v32 = a1;
        if ( !CryptSetProvParam(a1, 1u, pbInput, 0)
          && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, LastError);
        }
      }
      else
      {
        v32 = a1;
      }
      if ( !CryptCreateHash(v32, Algid, 0, 0, &phHash) )
      {
        v34 = GetLastError();
        v27 = v34;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_104;
        v30 = 32;
        goto LABEL_80;
      }
      if ( (_DWORD)v41 )
      {
        if ( !CryptHashData(phHash, v24, v17, 0) )
        {
          v34 = GetLastError();
          v27 = v34;
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_104;
          }
          v30 = 34;
          goto LABEL_80;
        }
      }
      else if ( !CryptSetHashParam(phHash, 2u, v24, 0) )
      {
        v34 = GetLastError();
        v27 = v34;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_104;
        v30 = 33;
        goto LABEL_80;
      }
      v35 = dwKeySpec;
      if ( CryptSignHashW(phHash, dwKeySpec, 0, 0, 0, a4) )
      {
        v36 = (BYTE *)SPExternalAlloc(*a4);
        *((_QWORD *)a4 + 1) = v36;
        if ( !v36 )
        {
          v27 = 14;
          goto LABEL_104;
        }
        if ( CryptSignHashW(phHash, v35, 0, 0, v36, a4) )
        {
          v27 = 0;
          goto LABEL_101;
        }
        v34 = GetLastError();
        v27 = v34;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_104;
        v30 = 36;
      }
      else
      {
        v34 = GetLastError();
        v27 = v34;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_104;
        v30 = 35;
      }
LABEL_80:
      v31 = v34;
LABEL_63:
      WPP_SF_d(*((_QWORD *)v29 + 2), v30, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, v31);
LABEL_104:
      if ( phHash )
        CryptDestroyHash(phHash);
      if ( v27 )
      {
        v37 = (void *)*((_QWORD *)a4 + 1);
        if ( v37 )
        {
          SPExternalFree(v37);
          *((_QWORD *)a4 + 1) = 0;
        }
        *a4 = 0;
      }
      return v27;
    }
  }
  return 534;
}

```

## disassembly

```asm
0x18006e7b0  mov     [rsp-38h+arg_10], rbx
0x18006e7b5  mov     [rsp-38h+arg_8], rdx
0x18006e7ba  mov     [rsp-38h+hObject], rcx
0x18006e7bf  push    rbp
0x18006e7c0  push    rsi
0x18006e7c1  push    rdi
0x18006e7c2  push    r12
0x18006e7c4  push    r13
0x18006e7c6  push    r14
0x18006e7c8  push    r15
0x18006e7ca  mov     rbp, rsp
0x18006e7cd  sub     rsp, 70h
0x18006e7d1  xor     ebx, ebx
0x18006e7d3  mov     r14, rcx
0x18006e7d6  mov     rdi, r9
0x18006e7d9  mov     [rbp+phHash], rbx
0x18006e7dd  mov     rsi, r8
0x18006e7e0  mov     qword ptr [rbp+pbInput], rbx
0x18006e7e4  mov     r15, rdx
0x18006e7e7  lea     ecx, [rbx+1]; int
0x18006e7ea  call    ?SchannelInit@@YAHH@Z; SchannelInit(int)
0x18006e7ef  test    eax, eax
0x18006e7f1  jz      loc_18006EA12
0x18006e7f7  test    rsi, rsi
0x18006e7fa  jz      loc_18006EA12
0x18006e800  test    rdi, rdi
0x18006e803  jz      loc_18006EA12
0x18006e809  mov     [rdi], rbx
0x18006e80c  mov     [rdi+8], rbx
0x18006e810  mov     rbx, cs:WPP_GLOBAL_Control
0x18006e817  lea     r12, WPP_GLOBAL_Control
0x18006e81e  lea     r13, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006e825  cmp     rbx, r12
0x18006e828  jz      short loc_18006E894
0x18006e82a  test    byte ptr [rbx+1Ch], 4
0x18006e82e  jz      short loc_18006E848
0x18006e830  mov     rcx, [rbx+10h]
0x18006e834  mov     edx, 14h
0x18006e839  mov     r8, r13
0x18006e83c  call    WPP_SF_
0x18006e841  mov     rbx, cs:WPP_GLOBAL_Control
0x18006e848  cmp     rbx, r12
0x18006e84b  jz      short loc_18006E894
0x18006e84d  test    byte ptr [rbx+1Ch], 4
0x18006e851  jz      short loc_18006E86E
0x18006e853  mov     rcx, [rbx+10h]
0x18006e857  mov     r9d, r14d
0x18006e85a  mov     edx, 15h
0x18006e85f  mov     r8, r13
0x18006e862  call    WPP_SF_d
0x18006e867  mov     rbx, cs:WPP_GLOBAL_Control
0x18006e86e  cmp     rbx, r12
0x18006e871  jz      short loc_18006E894
0x18006e873  test    byte ptr [rbx+1Ch], 4
0x18006e877  jz      short loc_18006E894
0x18006e879  mov     rcx, [rbx+10h]
0x18006e87d  mov     r9d, r15d
0x18006e880  mov     edx, 16h
0x18006e885  mov     r8, r13
0x18006e888  call    WPP_SF_d
0x18006e88d  mov     rbx, cs:WPP_GLOBAL_Control
0x18006e894  mov     r14d, [rsi]
0x18006e897  cmp     r14d, 24h ; '$'
0x18006e89b  jnb     short loc_18006E8A7
0x18006e89d  mov     eax, 80090318h
0x18006e8a2  jmp     loc_18006EA17
0x18006e8a7  mov     rcx, [rsi+8]
0x18006e8ab  mov     rax, [rcx+0Ch]
0x18006e8af  mov     r9d, [rcx]
0x18006e8b2  mov     r8d, [rcx+8]
0x18006e8b6  mov     r12d, [rcx+4]
0x18006e8ba  mov     qword ptr [rbp+pbInput], rax
0x18006e8be  mov     eax, [rcx+14h]
0x18006e8c1  mov     dword ptr [rbp+var_28], eax
0x18006e8c4  lea     rax, [rcx+18h]
0x18006e8c8  mov     esi, [rax]
0x18006e8ca  add     rax, 4
0x18006e8ce  mov     [rbp+Algid], r9d
0x18006e8d2  mov     [rbp+dwKeySpec], r8d
0x18006e8d6  mov     qword ptr [rbp+var_10], rax
0x18006e8da  mov     r15d, [rax]
0x18006e8dd  mov     r13d, [rax+4]
0x18006e8e1  lea     rax, WPP_GLOBAL_Control
0x18006e8e8  cmp     rbx, rax
0x18006e8eb  jz      short loc_18006E944
0x18006e8ed  test    byte ptr [rbx+1Ch], 4
0x18006e8f1  jz      short loc_18006E91A
0x18006e8f3  mov     rcx, [rbx+10h]
0x18006e8f7  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006e8fe  mov     edx, 17h
0x18006e903  call    WPP_SF_d
0x18006e908  mov     r8d, [rbp+dwKeySpec]
0x18006e90c  lea     rax, WPP_GLOBAL_Control
0x18006e913  mov     rbx, cs:WPP_GLOBAL_Control
0x18006e91a  cmp     rbx, rax
0x18006e91d  jz      short loc_18006E944
0x18006e91f  test    byte ptr [rbx+1Ch], 4
0x18006e923  jz      short loc_18006E944
0x18006e925  mov     rcx, [rbx+10h]
0x18006e929  mov     r9d, r8d
0x18006e92c  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006e933  mov     edx, 18h
0x18006e938  call    WPP_SF_d
0x18006e93d  mov     rbx, cs:WPP_GLOBAL_Control
0x18006e944  lea     eax, [rsi+18h]
0x18006e947  cmp     eax, 18h
0x18006e94a  jb      loc_18006EE70
0x18006e950  lea     ecx, [rax+r15]
0x18006e954  cmp     ecx, eax
0x18006e956  jb      loc_18006EE70
0x18006e95c  lea     eax, [rcx+r13]
0x18006e960  cmp     eax, ecx
0x18006e962  jb      loc_18006EE70
0x18006e968  cmp     r14d, eax
0x18006e96b  jb      loc_18006EA12
0x18006e971  mov     rdx, qword ptr [rbp+var_10]
0x18006e975  xor     r14d, r14d
0x18006e978  add     rdx, 8
0x18006e97c  lea     rcx, [rdx+rsi]
0x18006e980  test    esi, esi
0x18006e982  jnz     short loc_18006E987
0x18006e984  mov     rcx, rdx
0x18006e987  mov     eax, esi
0x18006e989  neg     eax
0x18006e98b  sbb     r9, r9
0x18006e98e  and     r9, rdx
0x18006e991  test    r15d, r15d
0x18006e994  jz      short loc_18006E9A2
0x18006e996  test    sil, 1
0x18006e99a  jnz     short loc_18006EA12
0x18006e99c  mov     r14, rcx
0x18006e99f  add     rcx, r15
0x18006e9a2  mov     eax, r13d
0x18006e9a5  neg     eax
0x18006e9a7  sbb     r15, r15
0x18006e9aa  xor     esi, esi
0x18006e9ac  and     r15, rcx
0x18006e9af  cmp     [rbp+arg_8], rsi
0x18006e9b3  jz      loc_18006EBDF
0x18006e9b9  mov     [rbp+dwKeySpec], esi
0x18006e9bc  xorps   xmm0, xmm0
0x18006e9bf  mov     [rbp+var_28], rsi
0x18006e9c3  movups  [rbp+var_10], xmm0
0x18006e9c7  test    r9, r9
0x18006e9ca  jz      short loc_18006EA12
0x18006e9cc  test    r15, r15
0x18006e9cf  jz      short loc_18006EA12
0x18006e9d1  lea     r8d, [rsi+3]; MaxCount
0x18006e9d5  mov     rcx, r9; String1
0x18006e9d8  lea     rdx, aRsa; "RSA"
0x18006e9df  call    wcsncmp_0
0x18006e9e4  test    eax, eax
0x18006e9e6  jnz     short loc_18006EA4A
0x18006e9e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH> `wil::Feature<__WilFeatureTraits_Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH>::GetImpl(void)'::`2'::impl
0x18006e9ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH>::__private_IsEnabled(void)
0x18006e9f4  test    al, al
0x18006e9f6  jz      short loc_18006EA2F
0x18006e9f8  test    r12b, 8
0x18006e9fc  jz      short loc_18006EA0C
0x18006e9fe  lea     rsi, [rbp+var_10]
0x18006ea02  mov     qword ptr [rbp+var_10], r14
0x18006ea06  mov     dword ptr [rbp+var_10+8], r13d
0x18006ea0a  jmp     short loc_18006EA43
0x18006ea0c  test    r12b, 2
0x18006ea10  jnz     short loc_18006EA3B
0x18006ea12  mov     eax, 54Fh
0x18006ea17  mov     rbx, [rsp+70h+arg_10]
0x18006ea1f  add     rsp, 70h
0x18006ea23  pop     r15
0x18006ea25  pop     r14
0x18006ea27  pop     r13
0x18006ea29  pop     r12
0x18006ea2b  pop     rdi
0x18006ea2c  pop     rsi
0x18006ea2d  pop     rbp
0x18006ea2e  retn
0x18006ea2f  cmp     r12d, 8
0x18006ea33  jz      short loc_18006E9FE
0x18006ea35  cmp     r12d, 2
0x18006ea39  jnz     short loc_18006EA12
0x18006ea3b  mov     [rbp+var_28], r14
0x18006ea3f  lea     rsi, [rbp+var_28]
0x18006ea43  mov     rbx, cs:WPP_GLOBAL_Control
0x18006ea4a  mov     r9, qword ptr [rbp+pbInput]
0x18006ea4e  test    r9, r9
0x18006ea51  jz      loc_18006EADB
0x18006ea57  lea     rax, WPP_GLOBAL_Control
0x18006ea5e  cmp     rbx, rax
0x18006ea61  jz      short loc_18006EA7E
0x18006ea63  test    byte ptr [rbx+1Ch], 4
0x18006ea67  jz      short loc_18006EA7E
0x18006ea69  mov     rcx, [rbx+10h]
0x18006ea6d  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006ea74  mov     edx, 19h
0x18006ea79  call    WPP_SF_q
0x18006ea7e  mov     r14, [rbp+hObject]
0x18006ea82  lea     r8, [rbp+pbInput]; pbInput
0x18006ea86  mov     rcx, r14; hObject
0x18006ea89  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18006ea91  mov     r9d, 8; cbInput
0x18006ea97  lea     rdx, aHwndHandle; "HWND Handle"
0x18006ea9e  call    cs:__imp_NCryptSetProperty
0x18006eaa4  test    eax, eax
0x18006eaa6  jz      short loc_18006EADF
0x18006eaa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eaaf  lea     rdx, WPP_GLOBAL_Control
0x18006eab6  cmp     rcx, rdx
0x18006eab9  jz      short loc_18006EADF
0x18006eabb  test    byte ptr [rcx+1Ch], 1
0x18006eabf  jz      short loc_18006EADF
0x18006eac1  mov     rcx, [rcx+10h]
0x18006eac5  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006eacc  mov     edx, 1Ah
0x18006ead1  mov     r9d, eax
0x18006ead4  call    WPP_SF_d
0x18006ead9  jmp     short loc_18006EADF
0x18006eadb  mov     r14, [rbp+hObject]
0x18006eadf  lea     rax, [rbp+dwKeySpec]
0x18006eae3  mov     [rsp+70h+var_38], r12d; dwFlags
0x18006eae8  mov     [rsp+70h+pcbResult], rax; pcbResult
0x18006eaed  mov     r9d, r13d; cbHashValue
0x18006eaf0  mov     eax, [rbp+dwKeySpec]
0x18006eaf3  mov     r8, r15; pbHashValue
0x18006eaf6  mov     [rsp+70h+cbSignature], eax; cbSignature
0x18006eafa  mov     rdx, rsi; pPaddingInfo
0x18006eafd  mov     rcx, r14; hKey
0x18006eb00  mov     qword ptr [rsp+70h+dwFlags], 0; pbSignature
0x18006eb09  call    cs:__imp_NCryptSignHash
0x18006eb0f  mov     ebx, eax
0x18006eb11  test    eax, eax
0x18006eb13  jz      short loc_18006EB4D
0x18006eb15  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eb1c  lea     rax, WPP_GLOBAL_Control
0x18006eb23  cmp     rcx, rax
0x18006eb26  jz      short loc_18006EB46
0x18006eb28  test    byte ptr [rcx+1Ch], 1
0x18006eb2c  jz      short loc_18006EB46
0x18006eb2e  mov     rcx, [rcx+10h]
0x18006eb32  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006eb39  mov     edx, 1Bh
0x18006eb3e  mov     r9d, ebx
0x18006eb41  call    WPP_SF_d
0x18006eb46  mov     eax, ebx
0x18006eb48  jmp     loc_18006EA17
0x18006eb4d  mov     ecx, [rbp+dwKeySpec]; uBytes
0x18006eb50  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18006eb55  mov     [rdi+8], rax
0x18006eb59  mov     rcx, rax
0x18006eb5c  test    rax, rax
0x18006eb5f  jnz     short loc_18006EB69
0x18006eb61  lea     eax, [rcx+0Eh]
0x18006eb64  jmp     loc_18006EA17
0x18006eb69  mov     eax, [rbp+dwKeySpec]
0x18006eb6c  lea     rdx, [rbp+dwKeySpec]
0x18006eb70  mov     [rsp+70h+var_38], r12d; dwFlags
0x18006eb75  mov     r9d, r13d; cbHashValue
0x18006eb78  mov     [rsp+70h+pcbResult], rdx; pcbResult
0x18006eb7d  mov     r8, r15; pbHashValue
0x18006eb80  mov     [rsp+70h+cbSignature], eax; cbSignature
0x18006eb84  mov     rdx, rsi; pPaddingInfo
0x18006eb87  mov     qword ptr [rsp+70h+dwFlags], rcx; pbSignature
0x18006eb8c  mov     rcx, r14; hKey
0x18006eb8f  mov     [rdi], eax
0x18006eb91  call    cs:__imp_NCryptSignHash
0x18006eb97  xor     esi, esi
0x18006eb99  mov     ebx, eax
0x18006eb9b  test    eax, eax
0x18006eb9d  jz      loc_18006EE0B
0x18006eba3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ebaa  lea     rax, WPP_GLOBAL_Control
0x18006ebb1  cmp     rcx, rax
0x18006ebb4  jz      loc_18006EE40
0x18006ebba  test    byte ptr [rcx+1Ch], 1
0x18006ebbe  jz      loc_18006EE40
0x18006ebc4  lea     edx, [rsi+1Ch]
0x18006ebc7  mov     r9d, ebx
0x18006ebca  mov     rcx, [rcx+10h]
0x18006ebce  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006ebd5  call    WPP_SF_d
0x18006ebda  jmp     loc_18006EE40
0x18006ebdf  lea     r12, WPP_GLOBAL_Control
0x18006ebe6  cmp     rbx, r12
0x18006ebe9  jz      short loc_18006EC0D
0x18006ebeb  test    byte ptr [rbx+1Ch], 4
0x18006ebef  jz      short loc_18006EC0D
0x18006ebf1  mov     rcx, [rbx+10h]
0x18006ebf5  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006ebfc  mov     edx, 1Dh
0x18006ec01  call    WPP_SF_
0x18006ec06  mov     rbx, cs:WPP_GLOBAL_Control
0x18006ec0d  mov     r9, qword ptr [rbp+pbInput]
0x18006ec11  test    r9, r9
0x18006ec14  jz      short loc_18006EC8B
0x18006ec16  cmp     rbx, r12
0x18006ec19  jz      short loc_18006EC36
0x18006ec1b  test    byte ptr [rbx+1Ch], 4
0x18006ec1f  jz      short loc_18006EC36
0x18006ec21  mov     rcx, [rbx+10h]
0x18006ec25  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006ec2c  mov     edx, 1Eh
  ... truncated ...
```
