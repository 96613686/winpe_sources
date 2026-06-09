# WTSSetUserConfigW

- ea: `0x180004b80`
- end: `0x180005018`
- name: `WTSSetUserConfigW`
- size: `1176`
- prototype: `BOOL __stdcall(LPWSTR pServerName, LPWSTR pUserName, WTS_CONFIG_CLASS WTSConfigClass, LPWSTR pBuffer, DWORD DataLength)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009fd0`

## callees

- `0x180004b80`
- `0x18000869c`
- `0x18000996c`
- `0x180009d28`
- `0x18001558e`
- `0x1800155c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004cee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004cee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004d73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004d73`
- `REGAPI!RegUserConfigQuery` at `0x180004db0`
- `REGAPI!RegUserConfigQuery` at `0x180004db0`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x180004dcd`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x180004dcd`
- `REGAPI!RegUserConfigSet` at `0x180004f9e`
- `REGAPI!RegUserConfigSet` at `0x180004f9e`
- `netutils!NetApiBufferFree` at `0x180004fbd`
- `netutils!NetApiBufferFree` at `0x180004fbd`
- `samcli!NetUserGetInfo` at `0x180004ce3`
- `samcli!NetUserGetInfo` at `0x180004d30`
- `samcli!NetUserGetInfo` at `0x180004d4f`
- `samcli!NetUserGetInfo` at `0x180004ce3`
- `samcli!NetUserGetInfo` at `0x180004d30`
- `samcli!NetUserGetInfo` at `0x180004d4f`

## pseudocode

```c
BOOL __stdcall WTSSetUserConfigW(
        LPWSTR pServerName,
        LPWSTR pUserName,
        WTS_CONFIG_CLASS WTSConfigClass,
        LPWSTR pBuffer,
        DWORD DataLength)
{
  const WCHAR *v7; // r14
  int v9; // r15d
  __int64 v10; // rsi
  unsigned __int64 v11; // rax
  DWORD v12; // ecx
  __int64 v14; // rcx
  const wchar_t *v15; // r8
  size_t v16; // rdx
  wchar_t *v17; // rcx
  DWORD Info; // esi
  wchar_t *v19; // rax
  SIZE_T v21; // rdx
  size_t v22; // rsi
  wchar_t *v23; // r14
  wchar_t *p_pszDest; // r8
  size_t v25; // rdx
  DWORD v26; // eax
  __int64 v27; // [rsp+38h] [rbp-D0h] BYREF
  LPBYTE bufptr; // [rsp+40h] [rbp-C8h] BYREF
  LPCWSTR username; // [rsp+48h] [rbp-C0h]
  _DWORD v30[29]; // [rsp+58h] [rbp-B0h] BYREF
  char v31; // [rsp+CCh] [rbp-3Ch] BYREF
  char v32; // [rsp+2CEh] [rbp+1C6h] BYREF
  char v33; // [rsp+4D0h] [rbp+3C8h] BYREF
  int v34; // [rsp+538h] [rbp+430h]
  int v35; // [rsp+53Ch] [rbp+434h]
  int v36; // [rsp+540h] [rbp+438h]
  int v37; // [rsp+544h] [rbp+43Ch]
  int v38; // [rsp+548h] [rbp+440h]
  char v39; // [rsp+634h] [rbp+52Ch] BYREF
  char v40; // [rsp+836h] [rbp+72Eh] BYREF
  wchar_t pszDest; // [rsp+A38h] [rbp+930h] BYREF

  v7 = pUserName;
  username = pUserName;
  memset_0(v30, 0, 0x9E8u);
  LODWORD(v27) = 0;
  v9 = 0;
  bufptr = 0;
  if ( !pBuffer )
    goto LABEL_7;
  if ( !DataLength )
    goto LABEL_7;
  v10 = -1;
  if ( pServerName )
  {
    v11 = -1;
    do
      ++v11;
    while ( pServerName[v11] );
    if ( v11 > 0x11 )
    {
LABEL_7:
      v12 = 87;
LABEL_8:
      SetLastError(v12);
      goto LABEL_9;
    }
  }
  if ( NetUserGetInfo(pServerName, v7, 0, &bufptr) )
  {
    if ( pServerName )
    {
      while ( pServerName[++v10] != 0 )
        ;
      v21 = 2LL * (unsigned int)(v10 + 3);
      v22 = (unsigned int)(v10 + 3);
      v19 = (wchar_t *)LocalAlloc(0x40u, v21);
      v23 = v19;
      if ( !v19 )
        goto LABEL_9;
      if ( v22 )
      {
        if ( v22 > 0x7FFFFFFF )
        {
          *v19 = 0;
        }
        else
        {
          v14 = 2147483646;
          v15 = L"\\\\";
          v16 = v22;
          do
          {
            if ( !v14 )
              break;
            if ( !*v15 )
              break;
            *v19++ = *v15++;
            --v14;
            --v16;
          }
          while ( v16 );
          v17 = v19 - 1;
          if ( v16 )
            v17 = v19;
          *v17 = 0;
        }
      }
      StringCchCatW(v23, v22, pServerName);
      Info = NetUserGetInfo(v23, username, 3u, &bufptr);
      LocalFree(v23);
      v7 = username;
    }
    else
    {
      Info = NetUserGetInfo(0, v7, 3u, &bufptr);
    }
    if ( Info )
    {
      v12 = 1317;
      goto LABEL_8;
    }
  }
  if ( !(unsigned int)RegUserConfigQuery(pServerName, v7, v30, 2536, &v27)
    || !(unsigned int)RegDefaultUserConfigQueryW(pServerName, v30, 2536, &v27) )
  {
    switch ( WTSConfigClass )
    {
      case WTSUserConfigInitialProgram:
        p_pszDest = (wchar_t *)&v32;
        goto LABEL_37;
      case WTSUserConfigWorkingDirectory:
        p_pszDest = (wchar_t *)&v31;
        goto LABEL_37;
      case WTSUserConfigfInheritInitialProgram:
        v30[0] = v30[0] & 0xFFFFFFF7 | (8 * (*(_DWORD *)pBuffer & 1));
        goto LABEL_60;
      case WTSUserConfigfAllowLogonTerminalServer:
        if ( *(_DWORD *)pBuffer )
          v30[0] &= ~0x8000u;
        else
          v30[0] |= 0x8000u;
        goto LABEL_60;
      case WTSUserConfigTimeoutSettingsConnections:
        v36 = *(_DWORD *)pBuffer;
        goto LABEL_60;
      case WTSUserConfigTimeoutSettingsDisconnections:
        v37 = *(_DWORD *)pBuffer;
        goto LABEL_60;
      case WTSUserConfigTimeoutSettingsIdle:
        v38 = *(_DWORD *)pBuffer;
        goto LABEL_60;
      case WTSUserConfigfDeviceClientDrives:
        v30[0] = v30[0] & 0xFFFDFFFF | ((*(_DWORD *)pBuffer & 1) << 17);
        goto LABEL_60;
      case WTSUserConfigfDeviceClientPrinters:
        v30[0] = v30[0] & 0xFFFBFFFF | ((*(_DWORD *)pBuffer & 1) << 18);
        goto LABEL_60;
      case WTSUserConfigfDeviceClientDefaultPrinter:
        v30[0] = v30[0] & 0xFFF7FFFF | ((*(_DWORD *)pBuffer & 1) << 19);
        goto LABEL_60;
      case WTSUserConfigBrokenTimeoutSettings:
        v30[0] = v30[0] & 0xFFFFDFFF | ((*(_DWORD *)pBuffer & 1) << 13);
        goto LABEL_60;
      case WTSUserConfigReconnectSettings:
        v30[0] = v30[0] & 0xFFFFBFFF | ((*(_DWORD *)pBuffer & 1) << 14);
        goto LABEL_60;
      case WTSUserConfigModemCallbackSettings:
        v34 = *(_DWORD *)pBuffer;
        goto LABEL_60;
      case WTSUserConfigModemCallbackPhoneNumber:
        p_pszDest = (wchar_t *)&v33;
        v25 = 50;
        goto LABEL_39;
      case WTSUserConfigShadowingSettings:
        v35 = *(_DWORD *)pBuffer;
        goto LABEL_60;
      case WTSUserConfigTerminalServerProfilePath:
        p_pszDest = (wchar_t *)&v39;
        goto LABEL_37;
      case WTSUserConfigTerminalServerHomeDir:
        p_pszDest = (wchar_t *)&v40;
LABEL_37:
        v25 = 256;
        goto LABEL_39;
      case WTSUserConfigTerminalServerHomeDirDrive:
        p_pszDest = &pszDest;
        v25 = 3;
LABEL_39:
        v9 = ValidateCopyUnicodeToUnicode(pBuffer, v25, p_pszDest);
        if ( v9 )
          goto LABEL_60;
        v12 = 13;
        goto LABEL_8;
      case WTSUserConfigUser:
        if ( DataLength < 0x864 )
          goto LABEL_7;
        if ( !(unsigned int)CollectUserInfoForSet(pBuffer, v30) )
          goto LABEL_9;
LABEL_60:
        v26 = RegUserConfigSet(pServerName, v7, v30, 2536);
        if ( !v26 )
        {
          v9 = 1;
          goto LABEL_9;
        }
        v9 = 0;
        v12 = v26;
        break;
      default:
        goto LABEL_7;
    }
    goto LABEL_8;
  }
LABEL_9:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return v9;
}

```

## disassembly

```asm
0x180004b80  mov     r11, rsp
0x180004b83  push    rbp
0x180004b84  push    r15
0x180004b86  lea     rbp, [r11-988h]
0x180004b8d  sub     rsp, 0A78h
0x180004b94  mov     rax, cs:__security_cookie
0x180004b9b  xor     rax, rsp
0x180004b9e  mov     [rbp+980h+var_40], rax
0x180004ba5  mov     [r11-18h], rbx
0x180004ba9  mov     rbx, rcx
0x180004bac  mov     [r11-20h], rsi
0x180004bb0  lea     rcx, [rsp+0A80h+var_A30]; void *
0x180004bb5  mov     [r11-28h], r12
0x180004bb9  mov     r12, r9
0x180004bbc  mov     [r11-30h], r13
0x180004bc0  mov     [r11-38h], r14
0x180004bc4  mov     r14, rdx
0x180004bc7  movsxd  r13, r8d
0x180004bca  mov     r8d, 9E8h; Size
0x180004bd0  mov     [rsp+0A80h+username], rdx
0x180004bd5  xor     edx, edx; Val
0x180004bd7  call    memset_0
0x180004bdc  xor     eax, eax
0x180004bde  mov     dword ptr [rsp+0A80h+var_A50], eax
0x180004be2  mov     r15d, eax
0x180004be5  mov     [rsp+0A80h+bufptr], rax
0x180004bea  test    r12, r12
0x180004bed  jz      short def_180004DF7; jumptable 0000000180004DF7 default case, case 18
0x180004bef  cmp     [rbp+980h+DataLength], eax
0x180004bf5  jz      short def_180004DF7; jumptable 0000000180004DF7 default case, case 18
0x180004bf7  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180004bfe  test    rbx, rbx
0x180004c01  jz      loc_180004D22
0x180004c07  mov     rax, rsi
0x180004c0a  nop     word ptr [rax+rax+00h]
0x180004c10  inc     rax
0x180004c13  cmp     [rbx+rax*2], r15w
0x180004c18  jnz     short loc_180004C10
0x180004c1a  cmp     rax, 11h
0x180004c1e  jbe     loc_180004D22
0x180004c24  mov     ecx, 57h ; 'W'; jumptable 0000000180004DF7 default case, case 18
0x180004c29  call    cs:__imp_SetLastError
0x180004c2f  mov     rcx, [rsp+0A80h+bufptr]; Buffer
0x180004c34  mov     r14, [rsp+0A80h+var_30]
0x180004c3c  mov     r13, [rsp+0A80h+var_28]
0x180004c44  mov     r12, [rsp+0A80h+var_20]
0x180004c4c  mov     rsi, [rsp+0A80h+var_18]
0x180004c54  mov     rbx, [rsp+0A80h+var_10]
0x180004c5c  test    rcx, rcx
0x180004c5f  jnz     loc_180004FBD
0x180004c65  mov     eax, r15d
0x180004c68  mov     rcx, [rbp+980h+var_40]
0x180004c6f  xor     rcx, rsp; StackCookie
0x180004c72  call    __security_check_cookie
0x180004c77  add     rsp, 0A78h
0x180004c7e  pop     r15
0x180004c80  pop     rbp
0x180004c81  retn
0x180004c82  test    rsi, rsi
0x180004c85  jz      short loc_180004CC2
0x180004c87  cmp     rsi, 7FFFFFFFh
0x180004c8e  ja      loc_180004D8A
0x180004c94  mov     ecx, 7FFFFFFEh
0x180004c99  lea     r8, asc_180017D70; "\\\\"
0x180004ca0  mov     rdx, rsi
0x180004ca3  test    rcx, rcx
0x180004ca6  jz      short loc_180004CB2
0x180004ca8  movzx   r9d, word ptr [r8]
0x180004cac  test    r9w, r9w
0x180004cb0  jnz     short loc_180004D0B
0x180004cb2  test    rdx, rdx
0x180004cb5  lea     rcx, [rax-2]
0x180004cb9  cmovnz  rcx, rax
0x180004cbd  xor     eax, eax
0x180004cbf  mov     [rcx], ax
0x180004cc2  mov     r8, rbx; pszSrc
0x180004cc5  mov     rdx, rsi; cchDest
0x180004cc8  mov     rcx, r14; pszDest
0x180004ccb  call    StringCchCatW
0x180004cd0  mov     rdx, [rsp+0A80h+username]; username
0x180004cd5  lea     r9, [rsp+0A80h+bufptr]; bufptr
0x180004cda  mov     r8d, 3; level
0x180004ce0  mov     rcx, r14; servername
0x180004ce3  call    cs:__imp_NetUserGetInfo
0x180004ce9  mov     rcx, r14; hMem
0x180004cec  mov     esi, eax
0x180004cee  call    cs:__imp_LocalFree
0x180004cf4  mov     r14, [rsp+0A80h+username]
0x180004cf9  test    esi, esi
0x180004cfb  jz      loc_180004D95
0x180004d01  mov     ecx, 525h
0x180004d06  jmp     loc_180004C29
0x180004d0b  mov     [rax], r9w
0x180004d0f  add     r8, 2
0x180004d13  add     rax, 2
0x180004d17  dec     rcx
0x180004d1a  sub     rdx, 1
0x180004d1e  jnz     short loc_180004CA3
0x180004d20  jmp     short loc_180004CB2
0x180004d22  lea     r9, [rsp+0A80h+bufptr]; bufptr
0x180004d27  xor     r8d, r8d; level
0x180004d2a  mov     rdx, r14; username
0x180004d2d  mov     rcx, rbx; servername
0x180004d30  call    cs:__imp_NetUserGetInfo
0x180004d36  test    eax, eax
0x180004d38  jz      short loc_180004D95
0x180004d3a  test    rbx, rbx
0x180004d3d  jnz     short loc_180004D59
0x180004d3f  lea     r9, [rsp+0A80h+bufptr]; bufptr
0x180004d44  mov     r8d, 3; level
0x180004d4a  mov     rdx, r14; username
0x180004d4d  xor     ecx, ecx; servername
0x180004d4f  call    cs:__imp_NetUserGetInfo
0x180004d55  mov     esi, eax
0x180004d57  jmp     short loc_180004CF9
0x180004d59  cmp     [rbx+rsi*2+2], r15w
0x180004d5f  lea     rsi, [rsi+1]
0x180004d63  jnz     short loc_180004D59
0x180004d65  lea     eax, [rsi+3]
0x180004d68  mov     ecx, 40h ; '@'; uFlags
0x180004d6d  lea     rdx, [rax+rax]; uBytes
0x180004d71  mov     esi, eax
0x180004d73  call    cs:__imp_LocalAlloc
0x180004d79  mov     r14, rax
0x180004d7c  test    rax, rax
0x180004d7f  jz      loc_180004C2F
0x180004d85  jmp     loc_180004C82
0x180004d8a  xor     eax, eax
0x180004d8c  mov     [r14], ax
0x180004d90  jmp     loc_180004CC2
0x180004d95  lea     rax, [rsp+0A80h+var_A50]
0x180004d9a  mov     r9d, 9E8h
0x180004da0  lea     r8, [rsp+0A80h+var_A30]
0x180004da5  mov     [rsp+0A80h+var_A60], rax
0x180004daa  mov     rdx, r14
0x180004dad  mov     rcx, rbx
0x180004db0  call    cs:__imp_RegUserConfigQuery
0x180004db6  test    eax, eax
0x180004db8  jz      short loc_180004DDB
0x180004dba  lea     r9, [rsp+0A80h+var_A50]
0x180004dbf  mov     r8d, 9E8h
0x180004dc5  lea     rdx, [rsp+0A80h+var_A30]
0x180004dca  mov     rcx, rbx
0x180004dcd  call    cs:__imp_RegDefaultUserConfigQueryW
0x180004dd3  test    eax, eax
0x180004dd5  jnz     loc_180004C2F
0x180004ddb  cmp     r13d, 13h; switch 20 cases
0x180004ddf  ja      def_180004DF7; jumptable 0000000180004DF7 default case, case 18
0x180004de5  lea     rdx, __ImageBase
0x180004dec  mov     ecx, ds:(jpt_180004DF7 - 180000000h)[rdx+r13*4]
0x180004df4  add     rcx, rdx
0x180004df7  jmp     rcx; switch jump
0x180004df9  lea     r8, [rbp+980h+var_7BA]; jumptable 0000000180004DF7 case 0
0x180004e00  jmp     short loc_180004E09
0x180004e02  lea     r8, [rbp+980h+var_252]; jumptable 0000000180004DF7 case 16
0x180004e09  mov     edx, 100h
0x180004e0e  jmp     short loc_180004E1C
0x180004e10  lea     r8, [rbp+980h+pszDest]; jumptable 0000000180004DF7 case 17
0x180004e17  mov     edx, 3; cchDest
0x180004e1c  mov     rcx, r12; pszSrc
0x180004e1f  call    ValidateCopyUnicodeToUnicode
0x180004e24  mov     r15d, eax
0x180004e27  test    eax, eax
0x180004e29  jnz     loc_180004F8D
0x180004e2f  mov     ecx, 0Dh
0x180004e34  jmp     loc_180004C29
0x180004e39  lea     r8, [rbp+980h+var_9BC]; jumptable 0000000180004DF7 case 1
0x180004e3d  jmp     short loc_180004E09
0x180004e3f  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180004DF7 case 2
0x180004e43  mov     ecx, [r12]
0x180004e47  and     eax, 0FFFFFFF7h
0x180004e4a  and     ecx, 1
0x180004e4d  shl     ecx, 3
0x180004e50  or      ecx, eax
0x180004e52  mov     [rsp+0A80h+var_A30], ecx
0x180004e56  jmp     loc_180004F8D
0x180004e5b  cmp     [r12], r15d; jumptable 0000000180004DF7 case 3
0x180004e5f  jz      short loc_180004E6E
0x180004e61  and     [rsp+0A80h+var_A30], 0FFFF7FFFh
0x180004e69  jmp     loc_180004F8D
0x180004e6e  or      [rsp+0A80h+var_A30], 8000h
0x180004e76  jmp     loc_180004F8D
0x180004e7b  mov     eax, [r12]; jumptable 0000000180004DF7 case 4
0x180004e7f  mov     [rbp+980h+var_548], eax
0x180004e85  jmp     loc_180004F8D
0x180004e8a  mov     eax, [r12]; jumptable 0000000180004DF7 case 5
0x180004e8e  mov     [rbp+980h+var_544], eax
0x180004e94  jmp     loc_180004F8D
0x180004e99  mov     eax, [r12]; jumptable 0000000180004DF7 case 6
0x180004e9d  mov     [rbp+980h+var_540], eax
0x180004ea3  jmp     loc_180004F8D
0x180004ea8  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180004DF7 case 7
0x180004eac  mov     ecx, [r12]
0x180004eb0  btr     eax, 11h
0x180004eb4  and     ecx, 1
0x180004eb7  shl     ecx, 11h
0x180004eba  or      ecx, eax
0x180004ebc  mov     [rsp+0A80h+var_A30], ecx
0x180004ec0  jmp     loc_180004F8D
0x180004ec5  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180004DF7 case 8
0x180004ec9  mov     ecx, [r12]
0x180004ecd  btr     eax, 12h
0x180004ed1  and     ecx, 1
0x180004ed4  shl     ecx, 12h
0x180004ed7  or      ecx, eax
0x180004ed9  mov     [rsp+0A80h+var_A30], ecx
0x180004edd  jmp     loc_180004F8D
0x180004ee2  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180004DF7 case 9
0x180004ee6  mov     ecx, [r12]
0x180004eea  btr     eax, 13h
0x180004eee  and     ecx, 1
0x180004ef1  shl     ecx, 13h
0x180004ef4  or      ecx, eax
0x180004ef6  mov     [rsp+0A80h+var_A30], ecx
0x180004efa  jmp     loc_180004F8D
0x180004eff  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180004DF7 case 10
0x180004f03  mov     ecx, [r12]
0x180004f07  btr     eax, 0Dh
0x180004f0b  and     ecx, 1
0x180004f0e  shl     ecx, 0Dh
0x180004f11  or      ecx, eax
0x180004f13  mov     [rsp+0A80h+var_A30], ecx
0x180004f17  jmp     short loc_180004F8D
0x180004f19  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180004DF7 case 11
0x180004f1d  mov     ecx, [r12]
0x180004f21  btr     eax, 0Eh
0x180004f25  and     ecx, 1
0x180004f28  shl     ecx, 0Eh
0x180004f2b  or      ecx, eax
0x180004f2d  mov     [rsp+0A80h+var_A30], ecx
0x180004f31  jmp     short loc_180004F8D
0x180004f33  mov     eax, [r12]; jumptable 0000000180004DF7 case 12
0x180004f37  mov     [rbp+980h+var_550], eax
0x180004f3d  jmp     short loc_180004F8D
0x180004f3f  lea     r8, [rbp+980h+var_5B8]; jumptable 0000000180004DF7 case 13
0x180004f46  mov     edx, 32h ; '2'
0x180004f4b  jmp     loc_180004E1C
0x180004f50  mov     eax, [r12]; jumptable 0000000180004DF7 case 14
0x180004f54  mov     [rbp+980h+var_54C], eax
0x180004f5a  jmp     short loc_180004F8D
0x180004f5c  lea     r8, [rbp+980h+var_454]; jumptable 0000000180004DF7 case 15
0x180004f63  jmp     loc_180004E09
0x180004f68  cmp     [rbp+980h+DataLength], 864h; jumptable 0000000180004DF7 case 19
0x180004f72  jb      def_180004DF7; jumptable 0000000180004DF7 default case, case 18
0x180004f78  lea     rdx, [rsp+0A80h+var_A30]
0x180004f7d  mov     rcx, r12
0x180004f80  call    CollectUserInfoForSet
0x180004f85  test    eax, eax
0x180004f87  jz      loc_180004C2F
0x180004f8d  mov     r9d, 9E8h
0x180004f93  lea     r8, [rsp+0A80h+var_A30]
0x180004f98  mov     rdx, r14
0x180004f9b  mov     rcx, rbx
0x180004f9e  call    cs:__imp_RegUserConfigSet
0x180004fa4  test    eax, eax
0x180004fa6  jnz     short loc_180004FB3
0x180004fa8  mov     r15d, 1
0x180004fae  jmp     loc_180004C2F
0x180004fb3  xor     r15d, r15d
0x180004fb6  mov     ecx, eax
0x180004fb8  jmp     loc_180004C29
0x180004fbd  call    cs:__imp_NetApiBufferFree
0x180004fc3  jmp     loc_180004C65
```
