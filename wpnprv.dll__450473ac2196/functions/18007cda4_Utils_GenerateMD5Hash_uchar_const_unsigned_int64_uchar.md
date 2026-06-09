# Utils::GenerateMD5Hash(uchar * const,unsigned __int64,uchar *)

- ea: `0x18007cda4`
- end: `0x18007d28f`
- name: `?GenerateMD5Hash@Utils@@CAJQEAE_KPEAE@Z`
- size: `1259`
- prototype: `__int64 __fastcall(BYTE *pbData, unsigned __int64, BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007c7d8`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x18002e0b4`
- `0x18007cda4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ceea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cfc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d08e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d1bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ceea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cfc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d08e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d1bd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18007cedc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18007cedc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007cfb3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007cfb3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007d080`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007d080`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007d155`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007d155`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007d221`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007d221`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18007d244`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18007d244`

## pseudocode

```c
__int64 __fastcall Utils::GenerateMD5Hash(BYTE *pbData, unsigned __int64 a2, BYTE *a3)
{
  int v6; // eax
  __int64 v7; // r10
  unsigned int v8; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  signed int v11; // eax
  bool v12; // sf
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  bool v16; // sf
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  bool v20; // sf
  signed int v21; // eax
  signed int v22; // eax
  signed int LastError; // eax
  bool v24; // sf
  signed int v25; // eax
  signed int v26; // eax
  int dwFlags; // [rsp+20h] [rbp-20h]
  int dwFlagsa; // [rsp+20h] [rbp-20h]
  int dwFlagsb; // [rsp+20h] [rbp-20h]
  int dwFlagsc; // [rsp+20h] [rbp-20h]
  HCRYPTPROV phProv[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  DWORD dwDataLen; // [rsp+80h] [rbp+40h] BYREF
  DWORD pdwDataLen; // [rsp+90h] [rbp+50h] BYREF
  HCRYPTHASH phHash; // [rsp+98h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_7c10823e5faa3471b545c0b9eac154d0_Traceguids);
  }
  if ( !pbData )
    MicrosoftTelemetryAssertTriggeredNoArgs(pbData);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(pbData);
  dwDataLen = 0;
  pdwDataLen = 16;
  phProv[0] = 0;
  phHash = 0;
  v6 = ULongLongToULong(a2, &dwDataLen);
  v8 = v6;
  if ( v6 >= 0 )
  {
    if ( CryptAcquireContextW(phProv, 0, 0, 1u, 0xF0000000) )
    {
      if ( CryptCreateHash(phProv[0], 0x8003u, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, pbData, dwDataLen, 0) )
        {
          if ( CryptGetHashParam(phHash, 2u, a3, &pdwDataLen, 0) )
          {
            v8 = 0;
            goto LABEL_87;
          }
          LastError = GetLastError();
          v24 = LastError < 0;
          if ( LastError > 0 )
            v24 = 1;
          if ( v24
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = GetLastError();
            if ( v25 > 0 )
              v25 = (unsigned __int16)v25 | 0x80070000;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              WPP_7c10823e5faa3471b545c0b9eac154d0_Traceguids,
              (unsigned int)v25);
          }
          v26 = GetLastError();
          v8 = v26;
          if ( v26 > 0 )
            v8 = (unsigned __int16)v26 | 0x80070000;
          if ( (v8 & 0x80000000) == 0 )
            v8 = -2147467259;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1B2,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\utils.cpp",
            (const char *)v8,
            dwFlagsc);
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v10 = 56;
            goto LABEL_17;
          }
        }
        else
        {
          v19 = GetLastError();
          v20 = v19 < 0;
          if ( v19 > 0 )
            v20 = 1;
          if ( v20
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v21 = GetLastError();
            if ( v21 > 0 )
              v21 = (unsigned __int16)v21 | 0x80070000;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              53,
              WPP_7c10823e5faa3471b545c0b9eac154d0_Traceguids,
              (unsigned int)v21);
          }
          v22 = GetLastError();
          v8 = v22;
          if ( v22 > 0 )
            v8 = (unsigned __int16)v22 | 0x80070000;
          if ( (v8 & 0x80000000) == 0 )
            v8 = -2147467259;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1AB,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\utils.cpp",
            (const char *)v8,
            dwFlagsb);
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v10 = 54;
            goto LABEL_17;
          }
        }
      }
      else
      {
        v15 = GetLastError();
        v16 = v15 < 0;
        if ( v15 > 0 )
          v16 = 1;
        if ( v16
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = GetLastError();
          if ( v17 > 0 )
            v17 = (unsigned __int16)v17 | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            WPP_7c10823e5faa3471b545c0b9eac154d0_Traceguids,
            (unsigned int)v17);
        }
        v18 = GetLastError();
        v8 = v18;
        if ( v18 > 0 )
          v8 = (unsigned __int16)v18 | 0x80070000;
        if ( (v8 & 0x80000000) == 0 )
          v8 = -2147467259;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1A4,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\utils.cpp",
          (const char *)v8,
          dwFlagsb);
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v10 = 52;
          goto LABEL_17;
        }
      }
    }
    else
    {
      v11 = GetLastError();
      v12 = v11 < 0;
      if ( v11 > 0 )
        v12 = 1;
      if ( v12
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          WPP_7c10823e5faa3471b545c0b9eac154d0_Traceguids,
          (unsigned int)v13);
      }
      v14 = GetLastError();
      v8 = v14;
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      if ( (v8 & 0x80000000) == 0 )
        v8 = -2147467259;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x19D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\utils.cpp",
        (const char *)v8,
        dwFlagsa);
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v10 = 50;
        goto LABEL_17;
      }
    }
  }
  else
  {
    if ( (PVOID *)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 && *(_BYTE *)(v7 + 25) >= 2u )
      WPP_SF_d(*(_QWORD *)(v7 + 16), 47, WPP_7c10823e5faa3471b545c0b9eac154d0_Traceguids, (unsigned int)v6);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\utils.cpp",
      (const char *)v8,
      dwFlags);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v10 = 48;
LABEL_17:
      WPP_SF_d(v9[2], v10, WPP_7c10823e5faa3471b545c0b9eac154d0_Traceguids, v8);
LABEL_87:
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    phHash = 0;
  }
  if ( phProv[0] )
  {
    CryptReleaseContext(phProv[0], 0);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    phProv[0] = 0;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_d(v9[2], 57, WPP_7c10823e5faa3471b545c0b9eac154d0_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18007cda4  push    rbp
0x18007cda6  push    rbx
0x18007cda7  push    rsi
0x18007cda8  push    rdi
0x18007cda9  push    r12
0x18007cdab  push    r13
0x18007cdad  push    r15
0x18007cdaf  mov     rbp, rsp
0x18007cdb2  sub     rsp, 40h
0x18007cdb6  mov     rsi, r8
0x18007cdb9  mov     rbx, rdx
0x18007cdbc  mov     rdi, rcx
0x18007cdbf  mov     r10, cs:WPP_GLOBAL_Control
0x18007cdc6  lea     r13, WPP_GLOBAL_Control
0x18007cdcd  lea     r12, WPP_7c10823e5faa3471b545c0b9eac154d0_Traceguids
0x18007cdd4  mov     r15d, 2
0x18007cdda  cmp     r10, r13
0x18007cddd  jz      short loc_18007CE03
0x18007cddf  test    [r10+1Ch], r15b
0x18007cde3  jz      short loc_18007CE03
0x18007cde5  cmp     byte ptr [r10+19h], 6
0x18007cdea  jb      short loc_18007CE03
0x18007cdec  mov     rcx, [r10+10h]
0x18007cdf0  lea     edx, [r15+2Ch]
0x18007cdf4  mov     r8, r12
0x18007cdf7  call    WPP_SF_
0x18007cdfc  mov     r10, cs:WPP_GLOBAL_Control
0x18007ce03  test    rdi, rdi
0x18007ce06  jnz     short loc_18007CE14
0x18007ce08  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007ce0d  mov     r10, cs:WPP_GLOBAL_Control
0x18007ce14  test    rsi, rsi
0x18007ce17  jnz     short loc_18007CE25
0x18007ce19  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007ce1e  mov     r10, cs:WPP_GLOBAL_Control
0x18007ce25  lea     rdx, [rbp+dwDataLen]; unsigned int *
0x18007ce29  mov     [rbp+dwDataLen], 0
0x18007ce30  mov     rcx, rbx; unsigned __int64
0x18007ce33  mov     [rbp+pdwDataLen], 10h
0x18007ce3a  mov     [rbp+phProv], 0
0x18007ce42  mov     [rbp+phHash], 0
0x18007ce4a  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18007ce4f  mov     ebx, eax
0x18007ce51  test    eax, eax
0x18007ce53  jns     short loc_18007CEC5
0x18007ce55  cmp     r10, r13
0x18007ce58  jz      short loc_18007CE7A
0x18007ce5a  test    [r10+1Ch], r15b
0x18007ce5e  jz      short loc_18007CE7A
0x18007ce60  cmp     [r10+19h], r15b
0x18007ce64  jb      short loc_18007CE7A
0x18007ce66  mov     rcx, [r10+10h]
0x18007ce6a  mov     edx, 2Fh ; '/'
0x18007ce6f  mov     r9d, eax
0x18007ce72  mov     r8, r12
0x18007ce75  call    WPP_SF_d
0x18007ce7a  mov     rcx, [rbp+38h]; this
0x18007ce7e  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007ce85  mov     r9d, ebx; char *
0x18007ce88  mov     edx, 195h; void *
0x18007ce8d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007ce92  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce99  cmp     rcx, r13
0x18007ce9c  jz      loc_18007D215
0x18007cea2  test    byte ptr [rcx+1Ch], 80h
0x18007cea6  jz      loc_18007D215
0x18007ceac  mov     edx, 30h ; '0'
0x18007ceb1  mov     rcx, [rcx+10h]
0x18007ceb5  mov     r9d, ebx
0x18007ceb8  mov     r8, r12
0x18007cebb  call    WPP_SF_d
0x18007cec0  jmp     loc_18007D20E
0x18007cec5  mov     r9d, 1; dwProvType
0x18007cecb  mov     [rsp+40h+dwFlags], 0F0000000h; int
0x18007ced3  xor     r8d, r8d; szProvider
0x18007ced6  lea     rcx, [rbp+phProv]; phProv
0x18007ceda  xor     edx, edx; szContainer
0x18007cedc  call    cs:__imp_CryptAcquireContextW
0x18007cee2  test    eax, eax
0x18007cee4  jnz     loc_18007CF9B
0x18007ceea  call    cs:__imp_GetLastError
0x18007cef0  mov     edi, 80070000h
0x18007cef5  test    eax, eax
0x18007cef7  jle     short loc_18007CF00
0x18007cef9  movzx   eax, ax
0x18007cefc  or      eax, edi
0x18007cefe  test    eax, eax
0x18007cf00  jns     short loc_18007CF44
0x18007cf02  mov     rax, cs:WPP_GLOBAL_Control
0x18007cf09  cmp     rax, r13
0x18007cf0c  jz      short loc_18007CF44
0x18007cf0e  test    [rax+1Ch], r15b
0x18007cf12  jz      short loc_18007CF44
0x18007cf14  cmp     [rax+19h], r15b
0x18007cf18  jb      short loc_18007CF44
0x18007cf1a  call    cs:__imp_GetLastError
0x18007cf20  test    eax, eax
0x18007cf22  jle     short loc_18007CF29
0x18007cf24  movzx   eax, ax
0x18007cf27  or      eax, edi
0x18007cf29  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cf30  mov     edx, 31h ; '1'
0x18007cf35  mov     r9d, eax
0x18007cf38  mov     r8, r12
0x18007cf3b  mov     rcx, [rcx+10h]
0x18007cf3f  call    WPP_SF_d
0x18007cf44  call    cs:__imp_GetLastError
0x18007cf4a  mov     ebx, eax
0x18007cf4c  test    eax, eax
0x18007cf4e  jle     short loc_18007CF55
0x18007cf50  movzx   ebx, ax
0x18007cf53  or      ebx, edi
0x18007cf55  mov     rcx, [rbp+38h]; this
0x18007cf59  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007cf60  test    ebx, ebx
0x18007cf62  mov     eax, 80004005h
0x18007cf67  mov     edx, 19Dh; void *
0x18007cf6c  cmovns  ebx, eax
0x18007cf6f  mov     r9d, ebx; char *
0x18007cf72  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007cf77  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cf7e  cmp     rcx, r13
0x18007cf81  jz      loc_18007D215
0x18007cf87  test    byte ptr [rcx+1Ch], 80h
0x18007cf8b  jz      loc_18007D215
0x18007cf91  mov     edx, 32h ; '2'
0x18007cf96  jmp     loc_18007CEB1
0x18007cf9b  mov     rcx, [rbp+phProv]; hProv
0x18007cf9f  lea     rax, [rbp+phHash]
0x18007cfa3  xor     r9d, r9d; dwFlags
0x18007cfa6  mov     qword ptr [rsp+40h+dwFlags], rax; int
0x18007cfab  xor     r8d, r8d; hKey
0x18007cfae  mov     edx, 8003h; Algid
0x18007cfb3  call    cs:__imp_CryptCreateHash
0x18007cfb9  test    eax, eax
0x18007cfbb  jnz     loc_18007D072
0x18007cfc1  call    cs:__imp_GetLastError
0x18007cfc7  mov     edi, 80070000h
0x18007cfcc  test    eax, eax
0x18007cfce  jle     short loc_18007CFD7
0x18007cfd0  movzx   eax, ax
0x18007cfd3  or      eax, edi
0x18007cfd5  test    eax, eax
0x18007cfd7  jns     short loc_18007D01B
0x18007cfd9  mov     rax, cs:WPP_GLOBAL_Control
0x18007cfe0  cmp     rax, r13
0x18007cfe3  jz      short loc_18007D01B
0x18007cfe5  test    [rax+1Ch], r15b
0x18007cfe9  jz      short loc_18007D01B
0x18007cfeb  cmp     [rax+19h], r15b
0x18007cfef  jb      short loc_18007D01B
0x18007cff1  call    cs:__imp_GetLastError
0x18007cff7  test    eax, eax
0x18007cff9  jle     short loc_18007D000
0x18007cffb  movzx   eax, ax
0x18007cffe  or      eax, edi
0x18007d000  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d007  mov     edx, 33h ; '3'
0x18007d00c  mov     r9d, eax
0x18007d00f  mov     r8, r12
0x18007d012  mov     rcx, [rcx+10h]
0x18007d016  call    WPP_SF_d
0x18007d01b  call    cs:__imp_GetLastError
0x18007d021  mov     ebx, eax
0x18007d023  test    eax, eax
0x18007d025  jle     short loc_18007D02C
0x18007d027  movzx   ebx, ax
0x18007d02a  or      ebx, edi
0x18007d02c  mov     rcx, [rbp+38h]; this
0x18007d030  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007d037  test    ebx, ebx
0x18007d039  mov     eax, 80004005h
0x18007d03e  mov     edx, 1A4h; void *
0x18007d043  cmovns  ebx, eax
0x18007d046  mov     r9d, ebx; char *
0x18007d049  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007d04e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d055  cmp     rcx, r13
0x18007d058  jz      loc_18007D215
0x18007d05e  test    byte ptr [rcx+1Ch], 80h
0x18007d062  jz      loc_18007D215
0x18007d068  mov     edx, 34h ; '4'
0x18007d06d  jmp     loc_18007CEB1
0x18007d072  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x18007d076  xor     r9d, r9d; dwFlags
0x18007d079  mov     rcx, [rbp+phHash]; hHash
0x18007d07d  mov     rdx, rdi; pbData
0x18007d080  call    cs:__imp_CryptHashData
0x18007d086  test    eax, eax
0x18007d088  jnz     loc_18007D13F
0x18007d08e  call    cs:__imp_GetLastError
0x18007d094  mov     edi, 80070000h
0x18007d099  test    eax, eax
0x18007d09b  jle     short loc_18007D0A4
0x18007d09d  movzx   eax, ax
0x18007d0a0  or      eax, edi
0x18007d0a2  test    eax, eax
0x18007d0a4  jns     short loc_18007D0E8
0x18007d0a6  mov     rax, cs:WPP_GLOBAL_Control
0x18007d0ad  cmp     rax, r13
0x18007d0b0  jz      short loc_18007D0E8
0x18007d0b2  test    [rax+1Ch], r15b
0x18007d0b6  jz      short loc_18007D0E8
0x18007d0b8  cmp     [rax+19h], r15b
0x18007d0bc  jb      short loc_18007D0E8
0x18007d0be  call    cs:__imp_GetLastError
0x18007d0c4  test    eax, eax
0x18007d0c6  jle     short loc_18007D0CD
0x18007d0c8  movzx   eax, ax
0x18007d0cb  or      eax, edi
0x18007d0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d0d4  mov     edx, 35h ; '5'
0x18007d0d9  mov     r9d, eax
0x18007d0dc  mov     r8, r12
0x18007d0df  mov     rcx, [rcx+10h]
0x18007d0e3  call    WPP_SF_d
0x18007d0e8  call    cs:__imp_GetLastError
0x18007d0ee  mov     ebx, eax
0x18007d0f0  test    eax, eax
0x18007d0f2  jle     short loc_18007D0F9
0x18007d0f4  movzx   ebx, ax
0x18007d0f7  or      ebx, edi
0x18007d0f9  mov     rcx, [rbp+38h]; this
0x18007d0fd  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007d104  test    ebx, ebx
0x18007d106  mov     eax, 80004005h
0x18007d10b  mov     edx, 1ABh; void *
0x18007d110  cmovns  ebx, eax
0x18007d113  mov     r9d, ebx; char *
0x18007d116  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007d11b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d122  cmp     rcx, r13
0x18007d125  jz      loc_18007D215
0x18007d12b  test    byte ptr [rcx+1Ch], 80h
0x18007d12f  jz      loc_18007D215
0x18007d135  mov     edx, 36h ; '6'
0x18007d13a  jmp     loc_18007CEB1
0x18007d13f  mov     rcx, [rbp+phHash]; hHash
0x18007d143  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18007d147  mov     r8, rsi; pbData
0x18007d14a  mov     [rsp+40h+dwFlags], 0; int
0x18007d152  mov     edx, r15d; dwParam
0x18007d155  call    cs:__imp_CryptGetHashParam
0x18007d15b  test    eax, eax
0x18007d15d  jnz     loc_18007D20C
0x18007d163  call    cs:__imp_GetLastError
0x18007d169  mov     edi, 80070000h
0x18007d16e  test    eax, eax
0x18007d170  jle     short loc_18007D179
0x18007d172  movzx   eax, ax
0x18007d175  or      eax, edi
0x18007d177  test    eax, eax
0x18007d179  jns     short loc_18007D1BD
0x18007d17b  mov     rax, cs:WPP_GLOBAL_Control
0x18007d182  cmp     rax, r13
0x18007d185  jz      short loc_18007D1BD
0x18007d187  test    [rax+1Ch], r15b
0x18007d18b  jz      short loc_18007D1BD
0x18007d18d  cmp     [rax+19h], r15b
0x18007d191  jb      short loc_18007D1BD
0x18007d193  call    cs:__imp_GetLastError
0x18007d199  test    eax, eax
0x18007d19b  jle     short loc_18007D1A2
0x18007d19d  movzx   eax, ax
0x18007d1a0  or      eax, edi
0x18007d1a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d1a9  mov     edx, 37h ; '7'
0x18007d1ae  mov     r9d, eax
0x18007d1b1  mov     r8, r12
0x18007d1b4  mov     rcx, [rcx+10h]
0x18007d1b8  call    WPP_SF_d
0x18007d1bd  call    cs:__imp_GetLastError
0x18007d1c3  mov     ebx, eax
0x18007d1c5  test    eax, eax
0x18007d1c7  jle     short loc_18007D1CE
0x18007d1c9  movzx   ebx, ax
0x18007d1cc  or      ebx, edi
0x18007d1ce  mov     rcx, [rbp+38h]; this
0x18007d1d2  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007d1d9  test    ebx, ebx
0x18007d1db  mov     eax, 80004005h
0x18007d1e0  mov     edx, 1B2h; void *
0x18007d1e5  cmovns  ebx, eax
0x18007d1e8  mov     r9d, ebx; char *
0x18007d1eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007d1f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d1f7  cmp     rcx, r13
0x18007d1fa  jz      short loc_18007D215
0x18007d1fc  test    byte ptr [rcx+1Ch], 80h
0x18007d200  jz      short loc_18007D215
0x18007d202  mov     edx, 38h ; '8'
0x18007d207  jmp     loc_18007CEB1
0x18007d20c  xor     ebx, ebx
0x18007d20e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d215  mov     rax, [rbp+phHash]
0x18007d219  test    rax, rax
0x18007d21c  jz      short loc_18007D236
0x18007d21e  mov     rcx, rax; hHash
0x18007d221  call    cs:__imp_CryptDestroyHash
0x18007d227  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
