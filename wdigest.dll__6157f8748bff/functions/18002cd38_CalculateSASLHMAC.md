# CalculateSASLHMAC

- ea: `0x18002cd38`
- end: `0x18002d337`
- name: `CalculateSASLHMAC`
- size: `1535`
- prototype: `__int64 __fastcall(int, int, int, int, BYTE *, DWORD dwDataLen, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002f43c`
- `0x18002fe90`

## callees

- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x18002cd38`
- `0x18002d938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d11f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d11f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d209`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002ce96`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002cedc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d13b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d18a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002ce96`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002cedc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d13b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002d18a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18002d24f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18002d2c6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18002d24f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18002d2c6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002ce25`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002d085`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002ce25`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002d085`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002cf72`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d25d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d2e3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002cf72`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d25d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002d2e3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x18002d0fc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x18002d0fc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002cf33`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002d1de`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002cf33`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002d1de`

## pseudocode

```c
__int64 __fastcall CalculateSASLHMAC(
        __int64 a1,
        __int64 a2,
        const BYTE **a3,
        unsigned int a4,
        BYTE *a5,
        DWORD dwDataLen,
        __int64 a7)
{
  PVOID *v10; // rcx
  PVOID *v11; // rcx
  DWORD LastError; // eax
  __int64 v13; // rdx
  unsigned int v14; // ebx
  __int128 v15; // xmm0
  int v16; // eax
  DWORD v17; // eax
  __int64 v18; // rdx
  __int16 epi16; // ax
  HCRYPTHASH hHash; // [rsp+30h] [rbp-61h] BYREF
  DWORD v22; // [rsp+38h] [rbp-59h] BYREF
  DWORD pdwDataLen; // [rsp+3Ch] [rbp-55h] BYREF
  HCRYPTKEY hKey; // [rsp+40h] [rbp-51h] BYREF
  BYTE v25[16]; // [rsp+48h] [rbp-49h] BYREF
  __int128 v26; // [rsp+58h] [rbp-39h]
  __int64 v27; // [rsp+68h] [rbp-29h]
  BYTE pbData[16]; // [rsp+70h] [rbp-21h] BYREF
  BYTE v29[16]; // [rsp+80h] [rbp-11h] BYREF

  hHash = 0;
  v27 = 0;
  hKey = 0;
  pdwDataLen = 0;
  *(_OWORD *)v25 = 0;
  v22 = 0;
  v26 = 0;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
      WPP_SF_d(v10[2], 279, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, dwDataLen);
  }
  *(_OWORD *)a7 = 0;
  *(_OWORD *)pbData = 0;
  *(_OWORD *)v29 = 0;
  if ( a4 )
  {
    v15 = *(_OWORD *)(a1 + 164);
    pdwDataLen = 16;
    *(_OWORD *)pbData = v15;
  }
  else
  {
    if ( !CryptCreateHash(g_hCryptProv, 0x8003u, 0, 0, &hHash) )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      LastError = GetLastError();
      v13 = 280;
LABEL_12:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, LastError);
      v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_13:
      v14 = -1073741174;
      goto LABEL_72;
    }
    if ( !CryptHashData(hHash, (const BYTE *)(a1 + 248), 0x10u, 0) )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      LastError = GetLastError();
      v13 = 281;
      goto LABEL_12;
    }
    if ( *(_WORD *)a3 && !CryptHashData(hHash, a3[1], *(unsigned __int16 *)a3, 0) )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      LastError = GetLastError();
      v13 = 282;
      goto LABEL_12;
    }
    pdwDataLen = 16;
    if ( !CryptGetHashParam(hHash, 2u, pbData, &pdwDataLen, 0) )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      LastError = GetLastError();
      v13 = 283;
      goto LABEL_12;
    }
    CryptDestroyHash(hHash);
    hHash = 0;
    *(_OWORD *)(a1 + 164) = *(_OWORD *)pbData;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 286, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
  *(_WORD *)(a7 + 10) = 256;
  *(_DWORD *)(a7 + 12) = _byteswap_ulong(a4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 287, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, a4);
  v16 = CreateSymmetricKey(26625, 16, pbData, 0, &hKey);
  v14 = v16;
  if ( v16 >= 0 )
  {
    if ( CryptCreateHash(g_hCryptProv, 0x8009u, hKey, 0, &hHash) )
    {
      *(_DWORD *)v25 = 32771;
      LODWORD(v27) = 0;
      LODWORD(v26) = 0;
      if ( CryptSetHashParam(hHash, 5u, v25, 0) )
      {
        if ( CryptHashData(hHash, (const BYTE *)(a7 + 12), 4u, 0) )
        {
          if ( !dwDataLen || CryptHashData(hHash, a5, dwDataLen, 0) )
          {
            v22 = 16;
            if ( CryptGetHashParam(hHash, 2u, v29, &v22, 0) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  296,
                  &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids,
                  v22);
              CryptDestroyKey(hKey);
              hKey = 0;
              CryptDestroyHash(hHash);
              hHash = 0;
              if ( v22 == 16 )
              {
                epi16 = _mm_extract_epi16(*(__m128i *)v29, 4);
                *(_QWORD *)a7 = *(_QWORD *)v29;
                *(_WORD *)(a7 + 8) = epi16;
                goto LABEL_71;
              }
              v11 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
LABEL_45:
                v14 = -1073741174;
                goto LABEL_72;
              }
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 297, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
LABEL_44:
              v11 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_45;
            }
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_45;
            v17 = GetLastError();
            v18 = 295;
          }
          else
          {
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_45;
            v17 = GetLastError();
            v18 = 294;
          }
        }
        else
        {
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_45;
          v17 = GetLastError();
          v18 = 292;
        }
      }
      else
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_45;
        v17 = GetLastError();
        v18 = 290;
      }
    }
    else
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_45;
      v17 = GetLastError();
      v18 = 289;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v17);
    goto LABEL_44;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      288,
      &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids,
      (unsigned int)v16);
LABEL_71:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_72:
  if ( hKey )
  {
    CryptDestroyKey(hKey);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( hHash )
  {
    CryptDestroyHash(hHash);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    hHash = 0;
  }
  if ( v11 != &WPP_GLOBAL_Control && *((char *)v11 + 28) < 0 )
    WPP_SF_d(v11[2], 300, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18002cd38  push    rbp
0x18002cd3a  push    rbx
0x18002cd3b  push    rsi
0x18002cd3c  push    rdi
0x18002cd3d  push    r13
0x18002cd3f  push    r14
0x18002cd41  push    r15
0x18002cd43  lea     rbp, [rsp-0Fh]
0x18002cd48  sub     rsp, 0A0h
0x18002cd4f  mov     rax, cs:__security_cookie
0x18002cd56  xor     rax, rsp
0x18002cd59  mov     [rbp+3Fh+var_40], rax
0x18002cd5d  mov     r14, [rbp+3Fh+arg_30]
0x18002cd61  xor     edi, edi
0x18002cd63  mov     r13, [rbp+3Fh+arg_20]
0x18002cd67  xorps   xmm0, xmm0
0x18002cd6a  xor     eax, eax
0x18002cd6c  mov     [rbp+3Fh+hHash], rdi
0x18002cd70  mov     [rbp+3Fh+var_68], rax
0x18002cd74  mov     r15d, r9d
0x18002cd77  mov     rsi, r8
0x18002cd7a  mov     [rbp+3Fh+hKey], rdi
0x18002cd7e  mov     rbx, rcx
0x18002cd81  mov     [rbp+3Fh+pdwDataLen], edi
0x18002cd84  movups  xmmword ptr [rbp+3Fh+var_88], xmm0
0x18002cd88  mov     [rbp+3Fh+var_98], edi
0x18002cd8b  movups  [rbp+3Fh+var_78], xmm0
0x18002cd8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd96  lea     rax, WPP_GLOBAL_Control
0x18002cd9d  cmp     rcx, rax
0x18002cda0  jz      short loc_18002CDEF
0x18002cda2  test    byte ptr [rcx+1Ch], 80h
0x18002cda6  jz      short loc_18002CDCB
0x18002cda8  mov     rcx, [rcx+10h]
0x18002cdac  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002cdb3  mov     edx, 116h
0x18002cdb8  call    WPP_SF_
0x18002cdbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cdc4  lea     rax, WPP_GLOBAL_Control
0x18002cdcb  cmp     rcx, rax
0x18002cdce  jz      short loc_18002CDEF
0x18002cdd0  test    byte ptr [rcx+1Ch], 4
0x18002cdd4  jz      short loc_18002CDEF
0x18002cdd6  mov     r9d, [rbp+3Fh+dwDataLen]
0x18002cdda  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002cde1  mov     rcx, [rcx+10h]
0x18002cde5  mov     edx, 117h
0x18002cdea  call    WPP_SF_d
0x18002cdef  xorps   xmm0, xmm0
0x18002cdf2  xorps   xmm1, xmm1
0x18002cdf5  movups  xmmword ptr [r14], xmm0
0x18002cdf9  movups  xmmword ptr [rbp+3Fh+pbData], xmm0
0x18002cdfd  movups  xmmword ptr [rbp+3Fh+var_50], xmm1
0x18002ce01  test    r15d, r15d
0x18002ce04  jnz     loc_18002CF8A
0x18002ce0a  mov     rcx, cs:g_hCryptProv; hProv
0x18002ce11  lea     rax, [rbp+3Fh+hHash]
0x18002ce15  xor     r9d, r9d; dwFlags
0x18002ce18  mov     [rsp+0D0h+phHash], rax; phHash
0x18002ce1d  xor     r8d, r8d; hKey
0x18002ce20  mov     edx, 8003h; Algid
0x18002ce25  call    cs:__imp_CryptCreateHash
0x18002ce2b  test    eax, eax
0x18002ce2d  jnz     short loc_18002CE81
0x18002ce2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce36  lea     rsi, WPP_GLOBAL_Control
0x18002ce3d  cmp     rcx, rsi
0x18002ce40  jz      short loc_18002CE74
0x18002ce42  test    byte ptr [rcx+1Ch], 1
0x18002ce46  jz      short loc_18002CE74
0x18002ce48  call    cs:__imp_GetLastError
0x18002ce4e  mov     edx, 118h
0x18002ce53  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce5a  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002ce61  mov     r9d, eax
0x18002ce64  mov     rcx, [rcx+10h]
0x18002ce68  call    WPP_SF_d
0x18002ce6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce74  mov     ebx, 0C000028Ah
0x18002ce79  xor     r15d, r15d
0x18002ce7c  jmp     loc_18002D2BA
0x18002ce81  mov     rcx, [rbp+3Fh+hHash]; hHash
0x18002ce85  lea     rdx, [rbx+0F8h]; pbData
0x18002ce8c  xor     r9d, r9d; dwFlags
0x18002ce8f  lea     edi, [r9+10h]
0x18002ce93  mov     r8d, edi; dwDataLen
0x18002ce96  call    cs:__imp_CryptHashData
0x18002ce9c  xor     ecx, ecx
0x18002ce9e  test    eax, eax
0x18002cea0  jnz     short loc_18002CEC8
0x18002cea2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cea9  lea     rsi, WPP_GLOBAL_Control
0x18002ceb0  cmp     rcx, rsi
0x18002ceb3  jz      short loc_18002CE74
0x18002ceb5  test    byte ptr [rcx+1Ch], 1
0x18002ceb9  jz      short loc_18002CE74
0x18002cebb  call    cs:__imp_GetLastError
0x18002cec1  mov     edx, 119h
0x18002cec6  jmp     short loc_18002CE53
0x18002cec8  cmp     [rsi], cx
0x18002cecb  jz      short loc_18002CF19
0x18002cecd  movzx   r8d, word ptr [rsi]; dwDataLen
0x18002ced1  xor     r9d, r9d; dwFlags
0x18002ced4  mov     rdx, [rsi+8]; pbData
0x18002ced8  mov     rcx, [rbp+3Fh+hHash]; hHash
0x18002cedc  call    cs:__imp_CryptHashData
0x18002cee2  xor     esi, esi
0x18002cee4  test    eax, eax
0x18002cee6  jnz     short loc_18002CF1B
0x18002cee8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ceef  lea     rsi, WPP_GLOBAL_Control
0x18002cef6  cmp     rcx, rsi
0x18002cef9  jz      loc_18002CE74
0x18002ceff  test    byte ptr [rcx+1Ch], 1
0x18002cf03  jz      loc_18002CE74
0x18002cf09  call    cs:__imp_GetLastError
0x18002cf0f  mov     edx, 11Ah
0x18002cf14  jmp     loc_18002CE53
0x18002cf19  xor     esi, esi
0x18002cf1b  mov     rcx, [rbp+3Fh+hHash]; hHash
0x18002cf1f  lea     r9, [rbp+3Fh+pdwDataLen]; pdwDataLen
0x18002cf23  lea     r8, [rbp+3Fh+pbData]; pbData
0x18002cf27  mov     [rbp+3Fh+pdwDataLen], edi
0x18002cf2a  mov     edx, 2; dwParam
0x18002cf2f  mov     dword ptr [rsp+0D0h+phHash], esi; dwFlags
0x18002cf33  call    cs:__imp_CryptGetHashParam
0x18002cf39  test    eax, eax
0x18002cf3b  jnz     short loc_18002CF6E
0x18002cf3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf44  lea     rsi, WPP_GLOBAL_Control
0x18002cf4b  cmp     rcx, rsi
0x18002cf4e  jz      loc_18002CE74
0x18002cf54  test    byte ptr [rcx+1Ch], 1
0x18002cf58  jz      loc_18002CE74
0x18002cf5e  call    cs:__imp_GetLastError
0x18002cf64  mov     edx, 11Bh
0x18002cf69  jmp     loc_18002CE53
0x18002cf6e  mov     rcx, [rbp+3Fh+hHash]; hHash
0x18002cf72  call    cs:__imp_CryptDestroyHash
0x18002cf78  movups  xmm0, xmmword ptr [rbp+3Fh+pbData]
0x18002cf7c  mov     [rbp+3Fh+hHash], rsi
0x18002cf80  movdqu  xmmword ptr [rbx+0A4h], xmm0
0x18002cf88  jmp     short loc_18002CF9E
0x18002cf8a  movups  xmm0, xmmword ptr [rbx+0A4h]
0x18002cf91  mov     edi, 10h
0x18002cf96  mov     [rbp+3Fh+pdwDataLen], edi
0x18002cf99  movdqu  xmmword ptr [rbp+3Fh+pbData], xmm0
0x18002cf9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfa5  lea     rbx, WPP_GLOBAL_Control
0x18002cfac  cmp     rcx, rbx
0x18002cfaf  jz      short loc_18002CFCC
0x18002cfb1  test    byte ptr [rcx+1Ch], 4
0x18002cfb5  jz      short loc_18002CFCC
0x18002cfb7  mov     rcx, [rcx+10h]
0x18002cfbb  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002cfc2  mov     edx, 11Eh
0x18002cfc7  call    WPP_SF_
0x18002cfcc  mov     eax, r15d
0x18002cfcf  mov     word ptr [r14+0Ah], 100h
0x18002cfd6  bswap   eax
0x18002cfd8  mov     [r14+0Ch], eax
0x18002cfdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfe3  cmp     rcx, rbx
0x18002cfe6  jz      short loc_18002D006
0x18002cfe8  test    byte ptr [rcx+1Ch], 4
0x18002cfec  jz      short loc_18002D006
0x18002cfee  mov     rcx, [rcx+10h]
0x18002cff2  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002cff9  mov     edx, 11Fh
0x18002cffe  mov     r9d, r15d
0x18002d001  call    WPP_SF_d
0x18002d006  lea     rax, [rbp+3Fh+hKey]
0x18002d00a  xor     r9d, r9d
0x18002d00d  lea     r8, [rbp+3Fh+pbData]
0x18002d011  mov     [rsp+0D0h+phHash], rax
0x18002d016  mov     edx, edi
0x18002d018  mov     ecx, 6801h
0x18002d01d  call    CreateSymmetricKey
0x18002d022  xor     r15d, r15d
0x18002d025  mov     ebx, eax
0x18002d027  test    eax, eax
0x18002d029  jns     short loc_18002D069
0x18002d02b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d032  lea     rsi, WPP_GLOBAL_Control
0x18002d039  cmp     rcx, rsi
0x18002d03c  jz      loc_18002D2BA
0x18002d042  test    byte ptr [rcx+1Ch], 1
0x18002d046  jz      loc_18002D2BA
0x18002d04c  mov     rcx, [rcx+10h]
0x18002d050  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002d057  mov     edx, 120h
0x18002d05c  mov     r9d, eax
0x18002d05f  call    WPP_SF_d
0x18002d064  jmp     loc_18002D2B3
0x18002d069  mov     r8, [rbp+3Fh+hKey]; hKey
0x18002d06d  lea     rax, [rbp+3Fh+hHash]
0x18002d071  mov     rcx, cs:g_hCryptProv; hProv
0x18002d078  xor     r9d, r9d; dwFlags
0x18002d07b  mov     edx, 8009h; Algid
0x18002d080  mov     [rsp+0D0h+phHash], rax; phHash
0x18002d085  call    cs:__imp_CryptCreateHash
0x18002d08b  test    eax, eax
0x18002d08d  jnz     short loc_18002D0DE
0x18002d08f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d096  lea     rsi, WPP_GLOBAL_Control
0x18002d09d  cmp     rcx, rsi
0x18002d0a0  jz      short loc_18002D0D4
0x18002d0a2  test    byte ptr [rcx+1Ch], 1
0x18002d0a6  jz      short loc_18002D0D4
0x18002d0a8  call    cs:__imp_GetLastError
0x18002d0ae  mov     edx, 121h
0x18002d0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0ba  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002d0c1  mov     r9d, eax
0x18002d0c4  mov     rcx, [rcx+10h]
0x18002d0c8  call    WPP_SF_d
0x18002d0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0d4  mov     ebx, 0C000028Ah
0x18002d0d9  jmp     loc_18002D2BA
0x18002d0de  mov     rcx, [rbp+3Fh+hHash]; hHash
0x18002d0e2  lea     r8, [rbp+3Fh+var_88]; pbData
0x18002d0e6  xor     r9d, r9d; dwFlags
0x18002d0e9  mov     dword ptr [rbp+3Fh+var_88], 8003h
0x18002d0f0  mov     dword ptr [rbp+3Fh+var_68], r15d
0x18002d0f4  mov     dword ptr [rbp+3Fh+var_78], r15d
0x18002d0f8  lea     edx, [r9+5]; dwParam
0x18002d0fc  call    cs:__imp_CryptSetHashParam
0x18002d102  test    eax, eax
0x18002d104  jnz     short loc_18002D12C
0x18002d106  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d10d  lea     rsi, WPP_GLOBAL_Control
0x18002d114  cmp     rcx, rsi
0x18002d117  jz      short loc_18002D0D4
0x18002d119  test    byte ptr [rcx+1Ch], 1
0x18002d11d  jz      short loc_18002D0D4
0x18002d11f  call    cs:__imp_GetLastError
0x18002d125  mov     edx, 122h
0x18002d12a  jmp     short loc_18002D0B3
0x18002d12c  mov     rcx, [rbp+3Fh+hHash]; hHash
0x18002d130  lea     rdx, [r14+0Ch]; pbData
0x18002d134  xor     r9d, r9d; dwFlags
0x18002d137  lea     r8d, [r9+4]; dwDataLen
0x18002d13b  call    cs:__imp_CryptHashData
0x18002d141  test    eax, eax
0x18002d143  jnz     short loc_18002D176
0x18002d145  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d14c  lea     rsi, WPP_GLOBAL_Control
0x18002d153  cmp     rcx, rsi
0x18002d156  jz      loc_18002D0D4
0x18002d15c  test    byte ptr [rcx+1Ch], 1
0x18002d160  jz      loc_18002D0D4
0x18002d166  call    cs:__imp_GetLastError
0x18002d16c  mov     edx, 124h
0x18002d171  jmp     loc_18002D0B3
0x18002d176  cmp     [rbp+3Fh+dwDataLen], r15d
0x18002d17a  jz      short loc_18002D1C5
0x18002d17c  mov     r8d, [rbp+3Fh+dwDataLen]; dwDataLen
0x18002d180  xor     r9d, r9d; dwFlags
0x18002d183  mov     rcx, [rbp+3Fh+hHash]; hHash
0x18002d187  mov     rdx, r13; pbData
0x18002d18a  call    cs:__imp_CryptHashData
0x18002d190  test    eax, eax
0x18002d192  jnz     short loc_18002D1C5
0x18002d194  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d19b  lea     rsi, WPP_GLOBAL_Control
0x18002d1a2  cmp     rcx, rsi
0x18002d1a5  jz      loc_18002D0D4
0x18002d1ab  test    byte ptr [rcx+1Ch], 1
0x18002d1af  jz      loc_18002D0D4
0x18002d1b5  call    cs:__imp_GetLastError
0x18002d1bb  mov     edx, 126h
0x18002d1c0  jmp     loc_18002D0B3
0x18002d1c5  mov     rcx, [rbp+3Fh+hHash]; hHash
0x18002d1c9  lea     r9, [rbp+3Fh+var_98]; pdwDataLen
0x18002d1cd  lea     r8, [rbp+3Fh+var_50]; pbData
0x18002d1d1  mov     [rbp+3Fh+var_98], edi
0x18002d1d4  mov     edx, 2; dwParam
0x18002d1d9  mov     dword ptr [rsp+0D0h+phHash], r15d; dwFlags
0x18002d1de  call    cs:__imp_CryptGetHashParam
0x18002d1e4  test    eax, eax
0x18002d1e6  jnz     short loc_18002D219
0x18002d1e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1ef  lea     rsi, WPP_GLOBAL_Control
0x18002d1f6  cmp     rcx, rsi
0x18002d1f9  jz      loc_18002D0D4
0x18002d1ff  test    byte ptr [rcx+1Ch], 1
0x18002d203  jz      loc_18002D0D4
0x18002d209  call    cs:__imp_GetLastError
0x18002d20f  mov     edx, 127h
0x18002d214  jmp     loc_18002D0B3
0x18002d219  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d220  lea     rsi, WPP_GLOBAL_Control
0x18002d227  cmp     rcx, rsi
0x18002d22a  jz      short loc_18002D24B
0x18002d22c  test    byte ptr [rcx+1Ch], 4
0x18002d230  jz      short loc_18002D24B
0x18002d232  mov     r9d, [rbp+3Fh+var_98]
0x18002d236  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002d23d  mov     rcx, [rcx+10h]
0x18002d241  mov     edx, 128h
  ... truncated ...
```
