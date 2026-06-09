# IntfCreateRandomMac(_WLAN_INTERFACE_CONTEXT *,_DOT11_AC_PROFILE *,_DOT11_SSID *,uchar (*)[6])

- ea: `0x1800a2cf4`
- end: `0x1800a3265`
- name: `?IntfCreateRandomMac@@YAKPEAU_WLAN_INTERFACE_CONTEXT@@PEAU_DOT11_AC_PROFILE@@PEAU_DOT11_SSID@@PEAY05E@Z`
- size: `1393`
- prototype: `unsigned int __fastcall(struct _WLAN_INTERFACE_CONTEXT *, struct _DOT11_AC_PROFILE *, struct _DOT11_SSID *, unsigned __int8 (*)[6])`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800f9560`
- `0x18014c6b0`
- `0x18014d610`
- `0x18014f7c0`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1800a2cf4`
- `0x1800d9fd4`
- `0x180106340`
- `0x180106860`
- `0x18010722e`
- `0x180139a28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800a31b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800a31b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a307d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a307d`
- `bcrypt!BCryptGenRandom` at `0x1800a2e3d`
- `bcrypt!BCryptGenRandom` at `0x1800a2e3d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800a2eba`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800a3100`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800a2eba`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800a3100`
- `bcrypt!BCryptCreateHash` at `0x1800a2f99`
- `bcrypt!BCryptCreateHash` at `0x1800a2f99`
- `bcrypt!BCryptHashData` at `0x1800a2fbb`
- `bcrypt!BCryptHashData` at `0x1800a2fda`
- `bcrypt!BCryptHashData` at `0x1800a2ff9`
- `bcrypt!BCryptHashData` at `0x1800a301b`
- `bcrypt!BCryptHashData` at `0x1800a30aa`
- `bcrypt!BCryptHashData` at `0x1800a2fbb`
- `bcrypt!BCryptHashData` at `0x1800a2fda`
- `bcrypt!BCryptHashData` at `0x1800a2ff9`
- `bcrypt!BCryptHashData` at `0x1800a301b`
- `bcrypt!BCryptHashData` at `0x1800a30aa`
- `bcrypt!BCryptFinishHash` at `0x1800a30c5`
- `bcrypt!BCryptFinishHash` at `0x1800a30c5`
- `bcrypt!BCryptDestroyHash` at `0x1800a30ef`
- `bcrypt!BCryptDestroyHash` at `0x1800a30ef`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800a2dd4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800a2f70`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800a2dd4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800a2f70`

## pseudocode

```c
__int64 __fastcall IntfCreateRandomMac(
        struct _WLAN_INTERFACE_CONTEXT *a1,
        struct _DOT11_AC_PROFILE *a2,
        struct _DOT11_SSID *a3,
        unsigned __int8 (*a4)[6])
{
  int i; // eax
  unsigned int v9; // ebx
  int v10; // r14d
  PVOID *v11; // rcx
  _DWORD *v12; // rsi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  NTSTATUS v16; // eax
  __int64 v17; // r9
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  PVOID *v20; // rcx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-59h] BYREF
  UCHAR pbInput[8]; // [rsp+48h] [rbp-51h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-49h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+58h] [rbp-41h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int8 v27[6]; // [rsp+70h] [rbp-29h] BYREF
  UCHAR v28[2]; // [rsp+78h] [rbp-21h] BYREF
  WORD wMonth; // [rsp+7Ah] [rbp-1Fh]
  WORD wDay; // [rsp+7Ch] [rbp-1Dh]
  UCHAR pbOutput[4]; // [rsp+80h] [rbp-19h] BYREF
  __int16 v32; // [rsp+84h] [rbp-15h]

  phAlgorithm = 0;
  hAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)pbInput = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 945, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
  }
  *((_DWORD *)a1 + 1463) = 0;
  for ( i = 0; i < 6; ++i )
  {
    if ( (unsigned __int64)i >= 6 )
      _report_rangecheckfailure();
    v27[i] = 0;
  }
  v9 = 0;
  if ( g_bMacAddressRandomizationDisabled || !*((_DWORD *)a1 + 58) || *((_DWORD *)a1 + 59) )
    goto LABEL_68;
  if ( !a2 )
  {
    v10 = 0;
    v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
    if ( v9 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
LABEL_32:
        if ( v9 )
          goto LABEL_69;
        if ( v10 )
          goto LABEL_40;
LABEL_68:
        *(_DWORD *)v27 = *((_DWORD *)a1 + 34);
        *(_WORD *)&v27[4] = *((_WORD *)a1 + 70);
        goto LABEL_69;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 946, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v9);
LABEL_31:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_32;
    }
    v12 = (_DWORD *)((char *)a1 + 252);
    v9 = BCryptGenRandom(phAlgorithm, (PUCHAR)a1 + 252, 4u, 0);
    if ( v9 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v14 = 947;
        v15 = v9;
LABEL_28:
        WPP_SF_d(v13[12], v14, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v15);
      }
    }
    else
    {
      v15 = (unsigned int)*v12;
      v10 = *((_DWORD *)a1 + 60);
      *(_DWORD *)pbInput = *v12;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v14 = 948;
        goto LABEL_28;
      }
    }
    v16 = BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( !v9 )
      v9 = v16;
    goto LABEL_31;
  }
  if ( (*((_BYTE *)a2 + 24) & 0x10) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 950, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
    }
    goto LABEL_68;
  }
  v17 = *((unsigned int *)a2 + 16);
  *(_DWORD *)pbInput = *((_DWORD *)a2 + 16);
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 949, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v17);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_40:
    if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 105) >= 4u && (*((_BYTE *)v11 + 108) & 1) != 0 )
      WPP_SF_(v11[12], 951, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
  }
  *((_DWORD *)a1 + 1463) = 1;
  if ( !BCryptOpenAlgorithmProvider(&hAlgorithm, L"SHA256", 0, 0) )
  {
    v9 = BCryptCreateHash(hAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( !v9 )
    {
      v9 = BCryptHashData(phHash, (PUCHAR)a1 + 216, 0x10u, 0);
      if ( !v9 )
      {
        v9 = BCryptHashData(phHash, pbInput, 4u, 0);
        if ( !v9 )
        {
          v9 = BCryptHashData(phHash, a3->ucSSID, a3->uSSIDLength, 0);
          if ( !v9 )
          {
            v9 = BCryptHashData(phHash, (PUCHAR)a1 + 136, 6u, 0);
            if ( !v9 )
            {
              if ( !a2 || (*((_BYTE *)a2 + 24) & 0x20) == 0 )
                goto LABEL_57;
              SystemTime = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 952, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
              }
              *((_DWORD *)a1 + 1463) = 2;
              GetSystemTime(&SystemTime);
              *(_WORD *)v28 = SystemTime.wYear;
              wMonth = SystemTime.wMonth;
              wDay = SystemTime.wDay;
              v9 = BCryptHashData(phHash, v28, 6u, 0);
              if ( !v9 )
              {
LABEL_57:
                v9 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
                if ( !v9 )
                {
                  *(_DWORD *)v27 = *(_DWORD *)pbOutput;
                  *(_WORD *)&v27[4] = v32;
                  IntfApplyMaskRandomMac(a1, (unsigned __int8 (*)[6])v27);
                }
              }
            }
          }
        }
      }
      v18 = BCryptDestroyHash(phHash);
      if ( !v9 )
        v9 = v18;
    }
    v19 = BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    if ( !v9 )
      v9 = v19;
  }
LABEL_69:
  if ( !a4 )
  {
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF__MAC_(*((_QWORD *)WPP_GLOBAL_Control + 12), 953, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, 0);
    }
    if ( !v9 )
      v9 = 22;
    goto LABEL_81;
  }
  *(_DWORD *)a4 = *(_DWORD *)v27;
  *(_WORD *)&(*a4)[4] = *(_WORD *)&v27[4];
  if ( v9 )
  {
LABEL_81:
    *((_DWORD *)a1 + 1463) = 3;
    goto LABEL_82;
  }
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF__MAC_(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      954,
      &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
      (unsigned __int8 *)a4);
LABEL_82:
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v20 != &WPP_GLOBAL_Control && *((_BYTE *)v20 + 105) >= 4u && (*((_BYTE *)v20 + 108) & 1) != 0 )
    WPP_SF_d(v20[12], 955, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800a2cf4  push    rbp
0x1800a2cf6  push    rbx
0x1800a2cf7  push    rsi
0x1800a2cf8  push    rdi
0x1800a2cf9  push    r12
0x1800a2cfb  push    r13
0x1800a2cfd  push    r14
0x1800a2cff  push    r15
0x1800a2d01  lea     rbp, [rsp-1Fh]
0x1800a2d06  sub     rsp, 0B8h
0x1800a2d0d  mov     rax, cs:__security_cookie
0x1800a2d14  xor     rax, rsp
0x1800a2d17  mov     [rbp+57h+var_50], rax
0x1800a2d1b  xor     esi, esi
0x1800a2d1d  mov     r12, r9
0x1800a2d20  mov     [rbp+57h+phAlgorithm], rsi
0x1800a2d24  mov     r13, r8
0x1800a2d27  mov     [rbp+57h+hAlgorithm], rsi
0x1800a2d2b  mov     r15, rdx
0x1800a2d2e  mov     [rbp+57h+phHash], rsi
0x1800a2d32  mov     rdi, rcx
0x1800a2d35  mov     dword ptr [rbp+57h+pbInput], esi
0x1800a2d38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2d3f  lea     r14, WPP_GLOBAL_Control
0x1800a2d46  cmp     rcx, r14
0x1800a2d49  jz      short loc_1800A2D6C
0x1800a2d4b  cmp     byte ptr [rcx+69h], 4
0x1800a2d4f  jb      short loc_1800A2D6C
0x1800a2d51  test    byte ptr [rcx+6Ch], 1
0x1800a2d55  jz      short loc_1800A2D6C
0x1800a2d57  mov     rcx, [rcx+60h]
0x1800a2d5b  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x1800a2d62  mov     edx, 3B1h
0x1800a2d67  call    WPP_SF_
0x1800a2d6c  mov     [rdi+16DCh], esi
0x1800a2d72  mov     eax, esi
0x1800a2d74  cmp     eax, 6
0x1800a2d77  jge     short loc_1800A2D91
0x1800a2d79  movsxd  rcx, eax
0x1800a2d7c  cmp     rcx, 6
0x1800a2d80  jnb     short loc_1800A2D8B
0x1800a2d82  mov     [rbp+rcx+57h+var_80], sil
0x1800a2d87  inc     eax
0x1800a2d89  jmp     short loc_1800A2D74
0x1800a2d8b  call    __report_rangecheckfailure
0x1800a2d91  cmp     cs:?g_bMacAddressRandomizationDisabled@@3HA, esi; int g_bMacAddressRandomizationDisabled
0x1800a2d97  mov     ebx, esi
0x1800a2d99  jnz     loc_1800A313A
0x1800a2d9f  cmp     [rdi+0E8h], esi
0x1800a2da5  jz      loc_1800A313A
0x1800a2dab  cmp     [rdi+0ECh], esi
0x1800a2db1  jnz     loc_1800A313A
0x1800a2db7  test    r15, r15
0x1800a2dba  jnz     loc_1800A2EE8
0x1800a2dc0  xor     r9d, r9d; dwFlags
0x1800a2dc3  lea     rdx, pszAlgId; "RNG"
0x1800a2dca  xor     r8d, r8d; pszImplementation
0x1800a2dcd  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800a2dd1  mov     r14d, esi
0x1800a2dd4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800a2dda  mov     ebx, eax
0x1800a2ddc  test    eax, eax
0x1800a2dde  jz      short loc_1800A2E28
0x1800a2de0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2de7  lea     rax, WPP_GLOBAL_Control
0x1800a2dee  cmp     rcx, rax
0x1800a2df1  jz      loc_1800A2ECE
0x1800a2df7  cmp     byte ptr [rcx+69h], 1
0x1800a2dfb  jb      loc_1800A2ECE
0x1800a2e01  test    byte ptr [rcx+6Ch], 1
0x1800a2e05  jz      loc_1800A2ECE
0x1800a2e0b  mov     rcx, [rcx+60h]
0x1800a2e0f  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x1800a2e16  mov     edx, 3B2h
0x1800a2e1b  mov     r9d, ebx
0x1800a2e1e  call    WPP_SF_d
0x1800a2e23  jmp     loc_1800A2EC7
0x1800a2e28  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800a2e2c  lea     rsi, [rdi+0FCh]
0x1800a2e33  xor     r9d, r9d; dwFlags
0x1800a2e36  mov     rdx, rsi; pbBuffer
0x1800a2e39  lea     r8d, [r9+4]; cbBuffer
0x1800a2e3d  call    cs:__imp_BCryptGenRandom
0x1800a2e43  mov     ebx, eax
0x1800a2e45  test    eax, eax
0x1800a2e47  jz      short loc_1800A2E72
0x1800a2e49  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2e50  lea     rax, WPP_GLOBAL_Control
0x1800a2e57  cmp     rcx, rax
0x1800a2e5a  jz      short loc_1800A2EB4
0x1800a2e5c  cmp     byte ptr [rcx+69h], 1
0x1800a2e60  jb      short loc_1800A2EB4
0x1800a2e62  test    byte ptr [rcx+6Ch], 1
0x1800a2e66  jz      short loc_1800A2EB4
0x1800a2e68  mov     edx, 3B3h
0x1800a2e6d  mov     r9d, ebx
0x1800a2e70  jmp     short loc_1800A2EA4
0x1800a2e72  mov     r9d, [rsi]
0x1800a2e75  mov     r14d, [rdi+0F0h]
0x1800a2e7c  mov     dword ptr [rbp+57h+pbInput], r9d
0x1800a2e80  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2e87  lea     rax, WPP_GLOBAL_Control
0x1800a2e8e  cmp     rcx, rax
0x1800a2e91  jz      short loc_1800A2EB4
0x1800a2e93  cmp     byte ptr [rcx+69h], 4
0x1800a2e97  jb      short loc_1800A2EB4
0x1800a2e99  test    byte ptr [rcx+6Ch], 1
0x1800a2e9d  jz      short loc_1800A2EB4
0x1800a2e9f  mov     edx, 3B4h
0x1800a2ea4  mov     rcx, [rcx+60h]
0x1800a2ea8  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x1800a2eaf  call    WPP_SF_d
0x1800a2eb4  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800a2eb8  xor     edx, edx; dwFlags
0x1800a2eba  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800a2ec0  xor     esi, esi
0x1800a2ec2  test    ebx, ebx
0x1800a2ec4  cmovz   ebx, eax
0x1800a2ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2ece  test    ebx, ebx
0x1800a2ed0  jnz     loc_1800A314E
0x1800a2ed6  test    r14d, r14d
0x1800a2ed9  jz      loc_1800A313A
0x1800a2edf  lea     r14, WPP_GLOBAL_Control
0x1800a2ee6  jmp     short loc_1800A2F2F
0x1800a2ee8  test    byte ptr [r15+18h], 10h
0x1800a2eed  jnz     loc_1800A310D
0x1800a2ef3  mov     r9d, [r15+40h]
0x1800a2ef7  mov     dword ptr [rbp+57h+pbInput], r9d
0x1800a2efb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2f02  cmp     rcx, r14
0x1800a2f05  jz      short loc_1800A2F55
0x1800a2f07  cmp     byte ptr [rcx+69h], 4
0x1800a2f0b  jb      short loc_1800A2F2F
0x1800a2f0d  test    byte ptr [rcx+6Ch], 1
0x1800a2f11  jz      short loc_1800A2F2F
0x1800a2f13  mov     rcx, [rcx+60h]
0x1800a2f17  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x1800a2f1e  mov     edx, 3B5h
0x1800a2f23  call    WPP_SF_d
0x1800a2f28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2f2f  cmp     rcx, r14
0x1800a2f32  jz      short loc_1800A2F55
0x1800a2f34  cmp     byte ptr [rcx+69h], 4
0x1800a2f38  jb      short loc_1800A2F55
0x1800a2f3a  test    byte ptr [rcx+6Ch], 1
0x1800a2f3e  jz      short loc_1800A2F55
0x1800a2f40  mov     rcx, [rcx+60h]
0x1800a2f44  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x1800a2f4b  mov     edx, 3B7h
0x1800a2f50  call    WPP_SF_
0x1800a2f55  xor     r9d, r9d; dwFlags
0x1800a2f58  mov     dword ptr [rdi+16DCh], 1
0x1800a2f62  xor     r8d, r8d; pszImplementation
0x1800a2f65  lea     rdx, aSha256; "SHA256"
0x1800a2f6c  lea     rcx, [rbp+57h+hAlgorithm]; phAlgorithm
0x1800a2f70  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800a2f76  test    eax, eax
0x1800a2f78  jnz     loc_1800A314E
0x1800a2f7e  mov     rcx, [rbp+57h+hAlgorithm]; hAlgorithm
0x1800a2f82  lea     rdx, [rbp+57h+phHash]; phHash
0x1800a2f86  mov     [rsp+0F0h+dwFlags], esi; dwFlags
0x1800a2f8a  xor     r9d, r9d; cbHashObject
0x1800a2f8d  mov     [rsp+0F0h+cbSecret], esi; cbSecret
0x1800a2f91  xor     r8d, r8d; pbHashObject
0x1800a2f94  mov     [rsp+0F0h+pbSecret], rsi; pbSecret
0x1800a2f99  call    cs:__imp_BCryptCreateHash
0x1800a2f9f  mov     ebx, eax
0x1800a2fa1  test    eax, eax
0x1800a2fa3  jnz     loc_1800A30FA
0x1800a2fa9  mov     rcx, [rbp+57h+phHash]; hHash
0x1800a2fad  lea     rdx, [rdi+0D8h]; pbInput
0x1800a2fb4  xor     r9d, r9d; dwFlags
0x1800a2fb7  lea     r8d, [rax+10h]; cbInput
0x1800a2fbb  call    cs:__imp_BCryptHashData
0x1800a2fc1  mov     ebx, eax
0x1800a2fc3  test    eax, eax
0x1800a2fc5  jnz     loc_1800A30EB
0x1800a2fcb  mov     rcx, [rbp+57h+phHash]; hHash
0x1800a2fcf  lea     r8d, [rax+4]; cbInput
0x1800a2fd3  xor     r9d, r9d; dwFlags
0x1800a2fd6  lea     rdx, [rbp+57h+pbInput]; pbInput
0x1800a2fda  call    cs:__imp_BCryptHashData
0x1800a2fe0  mov     ebx, eax
0x1800a2fe2  test    eax, eax
0x1800a2fe4  jnz     loc_1800A30EB
0x1800a2fea  mov     r8d, [r13+0]; cbInput
0x1800a2fee  lea     rdx, [r13+4]; pbInput
0x1800a2ff2  mov     rcx, [rbp+57h+phHash]; hHash
0x1800a2ff6  xor     r9d, r9d; dwFlags
0x1800a2ff9  call    cs:__imp_BCryptHashData
0x1800a2fff  mov     ebx, eax
0x1800a3001  test    eax, eax
0x1800a3003  jnz     loc_1800A30EB
0x1800a3009  mov     rcx, [rbp+57h+phHash]; hHash
0x1800a300d  lea     rdx, [rdi+88h]; pbInput
0x1800a3014  xor     r9d, r9d; dwFlags
0x1800a3017  lea     r8d, [rax+6]; cbInput
0x1800a301b  call    cs:__imp_BCryptHashData
0x1800a3021  mov     ebx, eax
0x1800a3023  test    eax, eax
0x1800a3025  jnz     loc_1800A30EB
0x1800a302b  test    r15, r15
0x1800a302e  jz      loc_1800A30B6
0x1800a3034  test    byte ptr [r15+18h], 20h
0x1800a3039  jz      short loc_1800A30B6
0x1800a303b  xorps   xmm0, xmm0
0x1800a303e  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800a3042  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3049  cmp     rcx, r14
0x1800a304c  jz      short loc_1800A306F
0x1800a304e  cmp     byte ptr [rcx+69h], 4
0x1800a3052  jb      short loc_1800A306F
0x1800a3054  test    byte ptr [rcx+6Ch], 1
0x1800a3058  jz      short loc_1800A306F
0x1800a305a  mov     rcx, [rcx+60h]
0x1800a305e  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x1800a3065  mov     edx, 3B8h
0x1800a306a  call    WPP_SF_
0x1800a306f  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800a3073  mov     dword ptr [rdi+16DCh], 2
0x1800a307d  call    cs:__imp_GetSystemTime
0x1800a3083  movzx   eax, [rbp+57h+SystemTime.wYear]
0x1800a3087  lea     rdx, [rbp+57h+var_78]; pbInput
0x1800a308b  mov     rcx, [rbp+57h+phHash]; hHash
0x1800a308f  xor     r9d, r9d; dwFlags
0x1800a3092  mov     word ptr [rbp+57h+var_78], ax
0x1800a3096  movzx   eax, [rbp+57h+SystemTime.wMonth]
0x1800a309a  mov     [rbp+57h+var_76], ax
0x1800a309e  movzx   eax, [rbp+57h+SystemTime.wDay]
0x1800a30a2  lea     r8d, [r9+6]; cbInput
0x1800a30a6  mov     [rbp+57h+var_74], ax
0x1800a30aa  call    cs:__imp_BCryptHashData
0x1800a30b0  mov     ebx, eax
0x1800a30b2  test    eax, eax
0x1800a30b4  jnz     short loc_1800A30EB
0x1800a30b6  mov     rcx, [rbp+57h+phHash]; hHash
0x1800a30ba  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x1800a30be  xor     r9d, r9d; dwFlags
0x1800a30c1  lea     r8d, [r9+20h]; cbOutput
0x1800a30c5  call    cs:__imp_BCryptFinishHash
0x1800a30cb  mov     ebx, eax
0x1800a30cd  test    eax, eax
0x1800a30cf  jnz     short loc_1800A30EB
0x1800a30d1  mov     eax, dword ptr [rbp+57h+pbOutput]
0x1800a30d4  lea     rdx, [rbp+57h+var_80]; unsigned __int8 (*)[6]
0x1800a30d8  mov     dword ptr [rbp+57h+var_80], eax
0x1800a30db  mov     rcx, rdi; struct _WLAN_INTERFACE_CONTEXT *
0x1800a30de  movzx   eax, [rbp+57h+var_6C]
0x1800a30e2  mov     word ptr [rbp+57h+var_80+4], ax
0x1800a30e6  call    ?IntfApplyMaskRandomMac@@YAXPEAU_WLAN_INTERFACE_CONTEXT@@PEAY05E@Z; IntfApplyMaskRandomMac(_WLAN_INTERFACE_CONTEXT *,uchar (*)[6])
0x1800a30eb  mov     rcx, [rbp+57h+phHash]; hHash
0x1800a30ef  call    cs:__imp_BCryptDestroyHash
0x1800a30f5  test    ebx, ebx
0x1800a30f7  cmovz   ebx, eax
0x1800a30fa  mov     rcx, [rbp+57h+hAlgorithm]; hAlgorithm
0x1800a30fe  xor     edx, edx; dwFlags
0x1800a3100  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800a3106  test    ebx, ebx
0x1800a3108  cmovz   ebx, eax
0x1800a310b  jmp     short loc_1800A314E
0x1800a310d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3114  cmp     rcx, r14
0x1800a3117  jz      short loc_1800A313A
0x1800a3119  cmp     byte ptr [rcx+69h], 4
0x1800a311d  jb      short loc_1800A313A
0x1800a311f  test    byte ptr [rcx+6Ch], 1
0x1800a3123  jz      short loc_1800A313A
0x1800a3125  mov     rcx, [rcx+60h]
0x1800a3129  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x1800a3130  mov     edx, 3B6h
0x1800a3135  call    WPP_SF_
0x1800a313a  mov     eax, [rdi+88h]
0x1800a3140  mov     dword ptr [rbp+57h+var_80], eax
0x1800a3143  movzx   eax, word ptr [rdi+8Ch]
0x1800a314a  mov     word ptr [rbp+57h+var_80+4], ax
0x1800a314e  test    r12, r12
0x1800a3151  jz      short loc_1800A31B1
0x1800a3153  mov     eax, dword ptr [rbp+57h+var_80]
0x1800a3156  mov     [r12], eax
0x1800a315a  movzx   eax, word ptr [rbp+57h+var_80+4]
0x1800a315e  mov     [r12+4], ax
0x1800a3164  test    ebx, ebx
0x1800a3166  jnz     loc_1800A3202
0x1800a316c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3173  lea     rdi, WPP_GLOBAL_Control
0x1800a317a  cmp     rcx, rdi
0x1800a317d  jz      loc_1800A3243
0x1800a3183  cmp     byte ptr [rcx+69h], 4
0x1800a3187  jb      loc_1800A321A
0x1800a318d  test    byte ptr [rcx+6Ch], 1
0x1800a3191  jz      loc_1800A321A
0x1800a3197  mov     rcx, [rcx+60h]
0x1800a319b  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x1800a31a2  mov     edx, 3BAh
0x1800a31a7  mov     r9, r12
0x1800a31aa  call    WPP_SF__MAC_
0x1800a31af  jmp     short loc_1800A3213
0x1800a31b1  call    cs:__imp__o__errno
0x1800a31b7  mov     r14d, 16h
  ... truncated ...
```
