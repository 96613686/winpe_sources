# CalculateSASLHMACMulti

- ea: `0x18002d340`
- end: `0x18002d932`
- name: `CalculateSASLHMACMulti`
- size: `1522`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002eb94`
- `0x18002f1ac`

## callees

- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x18002d340`
- `0x18002d938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d52e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d52e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7f5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d46a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d4af`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d6fd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d772`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d46a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d4af`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d6fd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d772`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18002d837`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18002d8b8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18002d837`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18002d8b8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002d403`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002d65a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002d403`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002d65a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d542`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d845`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d8d5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d542`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d845`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d8d5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x18002d6b6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x18002d6b6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002d503`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002d7ca`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002d503`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002d7ca`

## pseudocode

```c
__int64 __fastcall CalculateSASLHMACMulti(
        __int64 a1,
        __int64 a2,
        const BYTE **a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  PVOID *v9; // rcx
  DWORD LastError; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  __int128 v13; // xmm0
  int v14; // eax
  unsigned int i; // edi
  __int64 v16; // rdx
  DWORD v17; // r8d
  const BYTE *v18; // rdx
  __int16 epi16; // ax
  HCRYPTHASH hHash; // [rsp+30h] [rbp-59h] BYREF
  DWORD v22; // [rsp+38h] [rbp-51h] BYREF
  DWORD pdwDataLen; // [rsp+3Ch] [rbp-4Dh] BYREF
  HCRYPTKEY hKey; // [rsp+40h] [rbp-49h] BYREF
  BYTE v25[16]; // [rsp+48h] [rbp-41h] BYREF
  __int128 v26; // [rsp+58h] [rbp-31h]
  __int64 v27; // [rsp+68h] [rbp-21h]
  BYTE pbData[16]; // [rsp+70h] [rbp-19h] BYREF
  BYTE v29[16]; // [rsp+80h] [rbp-9h] BYREF

  hHash = 0;
  v27 = 0;
  hKey = 0;
  pdwDataLen = 0;
  *(_OWORD *)v25 = 0;
  v22 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 315, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
  *(_OWORD *)a6 = 0;
  *(_OWORD *)pbData = 0;
  *(_OWORD *)v29 = 0;
  if ( a4 )
  {
    v13 = *(_OWORD *)(a1 + 132);
    pdwDataLen = 16;
    *(_OWORD *)pbData = v13;
  }
  else
  {
    if ( !CryptCreateHash(g_hCryptProv, 0x8003u, 0, 0, &hHash) )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        v11 = 316;
        goto LABEL_9;
      }
LABEL_11:
      v12 = -1073741174;
      goto LABEL_72;
    }
    if ( !CryptHashData(hHash, (const BYTE *)(a1 + 248), 0x10u, 0) )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      LastError = GetLastError();
      v11 = 317;
      goto LABEL_9;
    }
    if ( *(_WORD *)a3 && !CryptHashData(hHash, a3[1], *(unsigned __int16 *)a3, 0) )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      LastError = GetLastError();
      v11 = 318;
      goto LABEL_9;
    }
    pdwDataLen = 16;
    if ( !CryptGetHashParam(hHash, 2u, pbData, &pdwDataLen, 0) )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      LastError = GetLastError();
      v11 = 319;
      goto LABEL_9;
    }
    CryptDestroyHash(hHash);
    hHash = 0;
    *(_OWORD *)(a1 + 132) = *(_OWORD *)pbData;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
  *(_WORD *)(a6 + 10) = 256;
  *(_DWORD *)(a6 + 12) = _byteswap_ulong(a4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 323, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, a4);
  v14 = CreateSymmetricKey(26625, 16, pbData, 0, &hKey);
  v12 = v14;
  if ( v14 >= 0 )
  {
    if ( CryptCreateHash(g_hCryptProv, 0x8009u, hKey, 0, &hHash) )
    {
      *(_DWORD *)v25 = 32771;
      LODWORD(v27) = 0;
      LODWORD(v26) = 0;
      if ( CryptSetHashParam(hHash, 5u, v25, 0) )
      {
        if ( CryptHashData(hHash, (const BYTE *)(a6 + 12), 4u, 0) )
        {
          for ( i = 0; i < *(_DWORD *)(a5 + 4); ++i )
          {
            v16 = *(_QWORD *)(a5 + 8);
            if ( (*(_DWORD *)(v16 + 16LL * i + 4) & 0xFFFFFFF) == 1 )
            {
              v17 = *(_DWORD *)(v16 + 16LL * i);
              if ( v17 )
              {
                v18 = *(const BYTE **)(v16 + 16LL * i + 8);
                if ( v18 )
                {
                  if ( !CryptHashData(hHash, v18, v17, 0) )
                  {
                    v9 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      LastError = GetLastError();
                      v11 = 329;
                      goto LABEL_9;
                    }
                    goto LABEL_11;
                  }
                }
              }
            }
          }
          v22 = 16;
          if ( CryptGetHashParam(hHash, 2u, v29, &v22, 0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 331, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v22);
            CryptDestroyKey(hKey);
            hKey = 0;
            CryptDestroyHash(hHash);
            hHash = 0;
            if ( v22 == 16 )
            {
              epi16 = _mm_extract_epi16(*(__m128i *)v29, 4);
              *(_QWORD *)a6 = *(_QWORD *)v29;
              *(_WORD *)(a6 + 8) = epi16;
              goto LABEL_71;
            }
            v9 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 332, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
              goto LABEL_10;
            }
          }
          else
          {
            v9 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              LastError = GetLastError();
              v11 = 330;
              goto LABEL_9;
            }
          }
          goto LABEL_11;
        }
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_11;
        LastError = GetLastError();
        v11 = 328;
      }
      else
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_11;
        LastError = GetLastError();
        v11 = 326;
      }
    }
    else
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      LastError = GetLastError();
      v11 = 325;
    }
LABEL_9:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, LastError);
LABEL_10:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      324,
      &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids,
      (unsigned int)v14);
LABEL_71:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_72:
  if ( hKey )
  {
    CryptDestroyKey(hKey);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( hHash )
  {
    CryptDestroyHash(hHash);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    hHash = 0;
  }
  if ( v9 != &WPP_GLOBAL_Control && *((char *)v9 + 28) < 0 )
    WPP_SF_d(v9[2], 335, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18002d340  mov     [rsp-8+arg_8], rbx
0x18002d345  push    rbp
0x18002d346  push    rsi
0x18002d347  push    rdi
0x18002d348  push    r12
0x18002d34a  push    r13
0x18002d34c  push    r14
0x18002d34e  push    r15
0x18002d350  lea     rbp, [rsp-17h]
0x18002d355  sub     rsp, 0A0h
0x18002d35c  mov     rax, cs:__security_cookie
0x18002d363  xor     rax, rsp
0x18002d366  mov     [rbp+47h+var_40], rax
0x18002d36a  mov     r15, [rbp+47h+arg_28]
0x18002d36e  xor     r12d, r12d
0x18002d371  mov     r13, [rbp+47h+arg_20]
0x18002d375  xorps   xmm0, xmm0
0x18002d378  xor     eax, eax
0x18002d37a  mov     [rbp+47h+hHash], r12
0x18002d37e  mov     [rbp+47h+var_68], rax
0x18002d382  mov     r14d, r9d
0x18002d385  mov     rdi, r8
0x18002d388  mov     [rbp+47h+hKey], r12
0x18002d38c  mov     rbx, rcx
0x18002d38f  mov     [rbp+47h+pdwDataLen], r12d
0x18002d393  movups  xmmword ptr [rbp+47h+var_88], xmm0
0x18002d397  mov     [rbp+47h+var_98], r12d
0x18002d39b  movups  [rbp+47h+var_78], xmm0
0x18002d39f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3a6  lea     rsi, WPP_GLOBAL_Control
0x18002d3ad  cmp     rcx, rsi
0x18002d3b0  jz      short loc_18002D3CD
0x18002d3b2  test    byte ptr [rcx+1Ch], 80h
0x18002d3b6  jz      short loc_18002D3CD
0x18002d3b8  mov     rcx, [rcx+10h]
0x18002d3bc  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002d3c3  mov     edx, 13Bh
0x18002d3c8  call    WPP_SF_
0x18002d3cd  xorps   xmm0, xmm0
0x18002d3d0  xorps   xmm1, xmm1
0x18002d3d3  movups  xmmword ptr [r15], xmm0
0x18002d3d7  movups  xmmword ptr [rbp+47h+pbData], xmm0
0x18002d3db  movups  xmmword ptr [rbp+47h+var_50], xmm1
0x18002d3df  test    r14d, r14d
0x18002d3e2  jnz     loc_18002D55A
0x18002d3e8  mov     rcx, cs:g_hCryptProv; hProv
0x18002d3ef  lea     rax, [rbp+47h+hHash]
0x18002d3f3  xor     r9d, r9d; dwFlags
0x18002d3f6  mov     [rsp+0D0h+phHash], rax; phHash
0x18002d3fb  xor     r8d, r8d; hKey
0x18002d3fe  mov     edx, 8003h; Algid
0x18002d403  call    cs:__imp_CryptCreateHash
0x18002d409  test    eax, eax
0x18002d40b  jnz     short loc_18002D455
0x18002d40d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d414  cmp     rcx, rsi
0x18002d417  jz      short loc_18002D44B
0x18002d419  test    byte ptr [rcx+1Ch], 1
0x18002d41d  jz      short loc_18002D44B
0x18002d41f  call    cs:__imp_GetLastError
0x18002d425  mov     edx, 13Ch
0x18002d42a  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002d431  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d438  mov     r9d, eax
0x18002d43b  mov     rcx, [rcx+10h]
0x18002d43f  call    WPP_SF_d
0x18002d444  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d44b  mov     ebx, 0C000028Ah
0x18002d450  jmp     loc_18002D8AC
0x18002d455  mov     rcx, [rbp+47h+hHash]; hHash
0x18002d459  lea     rdx, [rbx+0F8h]; pbData
0x18002d460  xor     r9d, r9d; dwFlags
0x18002d463  lea     esi, [r9+10h]
0x18002d467  mov     r8d, esi; dwDataLen
0x18002d46a  call    cs:__imp_CryptHashData
0x18002d470  test    eax, eax
0x18002d472  jnz     short loc_18002D49A
0x18002d474  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d47b  lea     rsi, WPP_GLOBAL_Control
0x18002d482  cmp     rcx, rsi
0x18002d485  jz      short loc_18002D44B
0x18002d487  test    byte ptr [rcx+1Ch], 1
0x18002d48b  jz      short loc_18002D44B
0x18002d48d  call    cs:__imp_GetLastError
0x18002d493  mov     edx, 13Dh
0x18002d498  jmp     short loc_18002D42A
0x18002d49a  cmp     [rdi], r12w
0x18002d49e  jz      short loc_18002D4EA
0x18002d4a0  movzx   r8d, word ptr [rdi]; dwDataLen
0x18002d4a4  xor     r9d, r9d; dwFlags
0x18002d4a7  mov     rdx, [rdi+8]; pbData
0x18002d4ab  mov     rcx, [rbp+47h+hHash]; hHash
0x18002d4af  call    cs:__imp_CryptHashData
0x18002d4b5  test    eax, eax
0x18002d4b7  jnz     short loc_18002D4EA
0x18002d4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4c0  lea     rsi, WPP_GLOBAL_Control
0x18002d4c7  cmp     rcx, rsi
0x18002d4ca  jz      loc_18002D44B
0x18002d4d0  test    byte ptr [rcx+1Ch], 1
0x18002d4d4  jz      loc_18002D44B
0x18002d4da  call    cs:__imp_GetLastError
0x18002d4e0  mov     edx, 13Eh
0x18002d4e5  jmp     loc_18002D42A
0x18002d4ea  mov     rcx, [rbp+47h+hHash]; hHash
0x18002d4ee  lea     r9, [rbp+47h+pdwDataLen]; pdwDataLen
0x18002d4f2  lea     r8, [rbp+47h+pbData]; pbData
0x18002d4f6  mov     [rbp+47h+pdwDataLen], esi
0x18002d4f9  mov     edx, 2; dwParam
0x18002d4fe  mov     dword ptr [rsp+0D0h+phHash], r12d; dwFlags
0x18002d503  call    cs:__imp_CryptGetHashParam
0x18002d509  test    eax, eax
0x18002d50b  jnz     short loc_18002D53E
0x18002d50d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d514  lea     rsi, WPP_GLOBAL_Control
0x18002d51b  cmp     rcx, rsi
0x18002d51e  jz      loc_18002D44B
0x18002d524  test    byte ptr [rcx+1Ch], 1
0x18002d528  jz      loc_18002D44B
0x18002d52e  call    cs:__imp_GetLastError
0x18002d534  mov     edx, 13Fh
0x18002d539  jmp     loc_18002D42A
0x18002d53e  mov     rcx, [rbp+47h+hHash]; hHash
0x18002d542  call    cs:__imp_CryptDestroyHash
0x18002d548  movups  xmm0, xmmword ptr [rbp+47h+pbData]
0x18002d54c  mov     [rbp+47h+hHash], r12
0x18002d550  movdqu  xmmword ptr [rbx+84h], xmm0
0x18002d558  jmp     short loc_18002D56E
0x18002d55a  movups  xmm0, xmmword ptr [rbx+84h]
0x18002d561  mov     esi, 10h
0x18002d566  mov     [rbp+47h+pdwDataLen], esi
0x18002d569  movdqu  xmmword ptr [rbp+47h+pbData], xmm0
0x18002d56e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d575  lea     rbx, WPP_GLOBAL_Control
0x18002d57c  cmp     rcx, rbx
0x18002d57f  jz      short loc_18002D59C
0x18002d581  test    byte ptr [rcx+1Ch], 4
0x18002d585  jz      short loc_18002D59C
0x18002d587  mov     rcx, [rcx+10h]
0x18002d58b  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002d592  mov     edx, 142h
0x18002d597  call    WPP_SF_
0x18002d59c  mov     eax, r14d
0x18002d59f  mov     word ptr [r15+0Ah], 100h
0x18002d5a6  bswap   eax
0x18002d5a8  mov     [r15+0Ch], eax
0x18002d5ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5b3  cmp     rcx, rbx
0x18002d5b6  jz      short loc_18002D5DB
0x18002d5b8  test    byte ptr [rcx+1Ch], 4
0x18002d5bc  jz      short loc_18002D5DB
0x18002d5be  mov     rcx, [rcx+10h]
0x18002d5c2  mov     r9d, r14d
0x18002d5c5  lea     r14, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002d5cc  mov     edx, 143h
0x18002d5d1  mov     r8, r14
0x18002d5d4  call    WPP_SF_d
0x18002d5d9  jmp     short loc_18002D5E2
0x18002d5db  lea     r14, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002d5e2  lea     rax, [rbp+47h+hKey]
0x18002d5e6  xor     r9d, r9d
0x18002d5e9  lea     r8, [rbp+47h+pbData]
0x18002d5ed  mov     [rsp+0D0h+phHash], rax
0x18002d5f2  mov     edx, esi
0x18002d5f4  mov     ecx, 6801h
0x18002d5f9  call    CreateSymmetricKey
0x18002d5fe  mov     ebx, eax
0x18002d600  test    eax, eax
0x18002d602  jns     short loc_18002D63E
0x18002d604  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d60b  lea     rsi, WPP_GLOBAL_Control
0x18002d612  cmp     rcx, rsi
0x18002d615  jz      loc_18002D8AC
0x18002d61b  test    byte ptr [rcx+1Ch], 1
0x18002d61f  jz      loc_18002D8AC
0x18002d625  mov     rcx, [rcx+10h]
0x18002d629  mov     edx, 144h
0x18002d62e  mov     r9d, eax
0x18002d631  mov     r8, r14
0x18002d634  call    WPP_SF_d
0x18002d639  jmp     loc_18002D8A5
0x18002d63e  mov     r8, [rbp+47h+hKey]; hKey
0x18002d642  lea     rax, [rbp+47h+hHash]
0x18002d646  mov     rcx, cs:g_hCryptProv; hProv
0x18002d64d  xor     r9d, r9d; dwFlags
0x18002d650  mov     edx, 8009h; Algid
0x18002d655  mov     [rsp+0D0h+phHash], rax; phHash
0x18002d65a  call    cs:__imp_CryptCreateHash
0x18002d660  test    eax, eax
0x18002d662  jnz     short loc_18002D698
0x18002d664  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d66b  lea     rsi, WPP_GLOBAL_Control
0x18002d672  cmp     rcx, rsi
0x18002d675  jz      loc_18002D44B
0x18002d67b  test    byte ptr [rcx+1Ch], 1
0x18002d67f  jz      loc_18002D44B
0x18002d685  call    cs:__imp_GetLastError
0x18002d68b  mov     edx, 145h
0x18002d690  mov     r8, r14
0x18002d693  jmp     loc_18002D431
0x18002d698  mov     rcx, [rbp+47h+hHash]; hHash
0x18002d69c  lea     r8, [rbp+47h+var_88]; pbData
0x18002d6a0  xor     r9d, r9d; dwFlags
0x18002d6a3  mov     dword ptr [rbp+47h+var_88], 8003h
0x18002d6aa  mov     dword ptr [rbp+47h+var_68], r12d
0x18002d6ae  mov     dword ptr [rbp+47h+var_78], r12d
0x18002d6b2  lea     edx, [r9+5]; dwParam
0x18002d6b6  call    cs:__imp_CryptSetHashParam
0x18002d6bc  test    eax, eax
0x18002d6be  jnz     short loc_18002D6EE
0x18002d6c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6c7  lea     rsi, WPP_GLOBAL_Control
0x18002d6ce  cmp     rcx, rsi
0x18002d6d1  jz      loc_18002D44B
0x18002d6d7  test    byte ptr [rcx+1Ch], 1
0x18002d6db  jz      loc_18002D44B
0x18002d6e1  call    cs:__imp_GetLastError
0x18002d6e7  mov     edx, 146h
0x18002d6ec  jmp     short loc_18002D690
0x18002d6ee  mov     rcx, [rbp+47h+hHash]; hHash
0x18002d6f2  lea     rdx, [r15+0Ch]; pbData
0x18002d6f6  xor     r9d, r9d; dwFlags
0x18002d6f9  lea     r8d, [r9+4]; dwDataLen
0x18002d6fd  call    cs:__imp_CryptHashData
0x18002d703  test    eax, eax
0x18002d705  jnz     short loc_18002D738
0x18002d707  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d70e  lea     rsi, WPP_GLOBAL_Control
0x18002d715  cmp     rcx, rsi
0x18002d718  jz      loc_18002D44B
0x18002d71e  test    byte ptr [rcx+1Ch], 1
0x18002d722  jz      loc_18002D44B
0x18002d728  call    cs:__imp_GetLastError
0x18002d72e  mov     edx, 148h
0x18002d733  jmp     loc_18002D690
0x18002d738  mov     edi, r12d
0x18002d73b  cmp     edi, [r13+4]
0x18002d73f  jnb     short loc_18002D7B1
0x18002d741  mov     rdx, [r13+8]
0x18002d745  mov     ecx, edi
0x18002d747  add     rcx, rcx
0x18002d74a  mov     eax, [rdx+rcx*8+4]
0x18002d74e  and     eax, 0FFFFFFFh
0x18002d753  cmp     eax, 1
0x18002d756  jnz     short loc_18002D77C
0x18002d758  mov     r8d, [rdx+rcx*8]; dwDataLen
0x18002d75c  test    r8d, r8d
0x18002d75f  jz      short loc_18002D77C
0x18002d761  mov     rdx, [rdx+rcx*8+8]; pbData
0x18002d766  test    rdx, rdx
0x18002d769  jz      short loc_18002D77C
0x18002d76b  mov     rcx, [rbp+47h+hHash]; hHash
0x18002d76f  xor     r9d, r9d; dwFlags
0x18002d772  call    cs:__imp_CryptHashData
0x18002d778  test    eax, eax
0x18002d77a  jz      short loc_18002D780
0x18002d77c  inc     edi
0x18002d77e  jmp     short loc_18002D73B
0x18002d780  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d787  lea     rsi, WPP_GLOBAL_Control
0x18002d78e  cmp     rcx, rsi
0x18002d791  jz      loc_18002D44B
0x18002d797  test    byte ptr [rcx+1Ch], 1
0x18002d79b  jz      loc_18002D44B
0x18002d7a1  call    cs:__imp_GetLastError
0x18002d7a7  mov     edx, 149h
0x18002d7ac  jmp     loc_18002D690
0x18002d7b1  mov     rcx, [rbp+47h+hHash]; hHash
0x18002d7b5  lea     r9, [rbp+47h+var_98]; pdwDataLen
0x18002d7b9  lea     r8, [rbp+47h+var_50]; pbData
0x18002d7bd  mov     [rbp+47h+var_98], esi
0x18002d7c0  mov     edx, 2; dwParam
0x18002d7c5  mov     dword ptr [rsp+0D0h+phHash], r12d; dwFlags
0x18002d7ca  call    cs:__imp_CryptGetHashParam
0x18002d7d0  test    eax, eax
0x18002d7d2  jnz     short loc_18002D805
0x18002d7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7db  lea     rsi, WPP_GLOBAL_Control
0x18002d7e2  cmp     rcx, rsi
0x18002d7e5  jz      loc_18002D44B
0x18002d7eb  test    byte ptr [rcx+1Ch], 1
0x18002d7ef  jz      loc_18002D44B
0x18002d7f5  call    cs:__imp_GetLastError
0x18002d7fb  mov     edx, 14Ah
0x18002d800  jmp     loc_18002D690
0x18002d805  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d80c  lea     rax, WPP_GLOBAL_Control
0x18002d813  cmp     rcx, rax
0x18002d816  jz      short loc_18002D833
0x18002d818  test    byte ptr [rcx+1Ch], 4
0x18002d81c  jz      short loc_18002D833
0x18002d81e  mov     r9d, [rbp+47h+var_98]
0x18002d822  mov     edx, 14Bh
0x18002d827  mov     rcx, [rcx+10h]
0x18002d82b  mov     r8, r14
0x18002d82e  call    WPP_SF_d
0x18002d833  mov     rcx, [rbp+47h+hKey]; hKey
0x18002d837  call    cs:__imp_CryptDestroyKey
0x18002d83d  mov     rcx, [rbp+47h+hHash]; hHash
0x18002d841  mov     [rbp+47h+hKey], r12
  ... truncated ...
```
