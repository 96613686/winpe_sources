# WTSQueryUserConfigW

- ea: `0x180005c60`
- end: `0x18000608c`
- name: `WTSQueryUserConfigW`
- size: `1068`
- prototype: `BOOL __stdcall(LPWSTR pServerName, LPWSTR pUserName, WTS_CONFIG_CLASS WTSConfigClass, LPWSTR *ppBuffer, DWORD *pBytesReturned)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009df0`

## callees

- `0x180004090`
- `0x1800041d0`
- `0x180005c60`
- `0x1800097d4`
- `0x180009d28`
- `0x18001558e`
- `0x1800155c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d8a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d8a`
- `REGAPI!RegUserConfigQuery` at `0x180005e58`
- `REGAPI!RegUserConfigQuery` at `0x180005e58`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x180005cfd`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x180005e79`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x180005cfd`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x180005e79`
- `netutils!NetApiBufferFree` at `0x18000601b`
- `netutils!NetApiBufferFree` at `0x18000601b`
- `samcli!NetUserGetInfo` at `0x180005d53`
- `samcli!NetUserGetInfo` at `0x180005e15`
- `samcli!NetUserGetInfo` at `0x180005d53`
- `samcli!NetUserGetInfo` at `0x180005e15`

## pseudocode

```c
BOOL __stdcall WTSQueryUserConfigW(
        LPWSTR pServerName,
        LPWSTR pUserName,
        WTS_CONFIG_CLASS WTSConfigClass,
        LPWSTR *ppBuffer,
        DWORD *pBytesReturned)
{
  int v9; // ebx
  __int64 v10; // r13
  unsigned __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  size_t v14; // r13
  WCHAR *v15; // rax
  wchar_t *v16; // r10
  __int64 v17; // rdx
  const wchar_t *v18; // r8
  size_t v19; // r9
  WCHAR *v20; // rcx
  DWORD Info; // r13d
  DWORD v22; // ecx
  DWORD v23; // eax
  int v24; // eax
  _BOOL8 v25; // rax
  int v26; // eax
  LPCWSTR servername; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C8h] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-C0h] BYREF
  _DWORD v31[29]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v32[514]; // [rsp+CCh] [rbp-3Ch] BYREF
  _BYTE Src[514]; // [rsp+2CEh] [rbp+1C6h] BYREF
  _BYTE v34[104]; // [rsp+4D0h] [rbp+3C8h] BYREF
  int v35; // [rsp+538h] [rbp+430h]
  int v36; // [rsp+53Ch] [rbp+434h]
  int v37; // [rsp+540h] [rbp+438h]
  int v38; // [rsp+544h] [rbp+43Ch]
  int v39; // [rsp+548h] [rbp+440h]
  _BYTE v40[514]; // [rsp+634h] [rbp+52Ch] BYREF
  _BYTE v41[514]; // [rsp+836h] [rbp+72Eh] BYREF
  _WORD v42[8]; // [rsp+A38h] [rbp+930h] BYREF

  memset_0(v31, 0, 0x9E8u);
  v9 = 0;
  LODWORD(v29) = 0;
  bufptr = 0;
  if ( !ppBuffer || !pBytesReturned )
    goto LABEL_55;
  v10 = -1;
  if ( !pUserName )
  {
    if ( (unsigned int)RegDefaultUserConfigQueryW(pServerName, v31, 2536, &v29) )
      goto LABEL_57;
    goto LABEL_5;
  }
  if ( pServerName )
  {
    v11 = -1;
    do
      ++v11;
    while ( pServerName[v11] );
    if ( v11 > 0x11 )
    {
LABEL_55:
      v22 = 87;
      goto LABEL_56;
    }
  }
  if ( NetUserGetInfo(pServerName, pUserName, 0, &bufptr) && pServerName )
  {
    v12 = -1;
    do
      ++v12;
    while ( pServerName[v12] );
    v13 = (unsigned int)(v12 + 3);
    v14 = (unsigned int)v13;
    v15 = (WCHAR *)LocalAlloc(0x40u, 2 * v13);
    servername = v15;
    v16 = v15;
    if ( !v15 )
      goto LABEL_57;
    if ( v14 )
    {
      if ( v14 <= 0x7FFFFFFF )
      {
        v17 = 2147483646;
        v18 = L"\\\\";
        v19 = v14;
        do
        {
          if ( !v17 )
            break;
          if ( !*v18 )
            break;
          *v15++ = *v18++;
          --v17;
          --v19;
        }
        while ( v19 );
        v20 = v15 - 1;
        if ( v19 )
          v20 = v15;
        *v20 = 0;
      }
      else
      {
        *v15 = 0;
      }
    }
    StringCchCatW(v16, v14, pServerName);
    Info = NetUserGetInfo(servername, pUserName, 0, &bufptr);
    LocalFree((HLOCAL)servername);
    if ( Info )
    {
      v22 = Info;
LABEL_56:
      SetLastError(v22);
      goto LABEL_57;
    }
    v10 = -1;
  }
  if ( (unsigned int)RegUserConfigQuery(pServerName, pUserName, v31, 2536, &v29) )
  {
    v23 = RegDefaultUserConfigQueryW(pServerName, v31, 2536, &v29);
    if ( v23 )
    {
      v22 = v23;
      goto LABEL_56;
    }
  }
LABEL_5:
  switch ( WTSConfigClass )
  {
    case WTSUserConfigInitialProgram:
      v9 = CopyStringW(Src);
      break;
    case WTSUserConfigWorkingDirectory:
      v9 = CopyStringW(v32);
      break;
    case WTSUserConfigfInheritInitialProgram:
      v24 = v31[0] >> 3;
      goto LABEL_34;
    case WTSUserConfigfAllowLogonTerminalServer:
      v24 = ~(v31[0] >> 15);
      goto LABEL_34;
    case WTSUserConfigTimeoutSettingsConnections:
      LODWORD(v25) = v37;
      goto LABEL_35;
    case WTSUserConfigTimeoutSettingsDisconnections:
      LODWORD(v25) = v38;
      goto LABEL_35;
    case WTSUserConfigTimeoutSettingsIdle:
      LODWORD(v25) = v39;
      goto LABEL_35;
    case WTSUserConfigfDeviceClientDrives:
      v24 = v31[0] >> 17;
      goto LABEL_34;
    case WTSUserConfigfDeviceClientPrinters:
      v24 = v31[0] >> 18;
      goto LABEL_34;
    case WTSUserConfigfDeviceClientDefaultPrinter:
      v24 = v31[0] >> 19;
      goto LABEL_34;
    case WTSUserConfigBrokenTimeoutSettings:
      v24 = v31[0] >> 13;
      goto LABEL_34;
    case WTSUserConfigReconnectSettings:
      v24 = v31[0] >> 14;
LABEL_34:
      LODWORD(v25) = v24 & 1;
      goto LABEL_35;
    case WTSUserConfigModemCallbackSettings:
      LODWORD(v25) = v35;
      goto LABEL_35;
    case WTSUserConfigModemCallbackPhoneNumber:
      v26 = CopyStringW(v34);
      goto LABEL_36;
    case WTSUserConfigShadowingSettings:
      LODWORD(v25) = v36;
      goto LABEL_35;
    case WTSUserConfigTerminalServerProfilePath:
      v26 = CopyStringW(v40);
      goto LABEL_36;
    case WTSUserConfigTerminalServerHomeDir:
      v26 = CopyStringW(v41);
      goto LABEL_36;
    case WTSUserConfigTerminalServerHomeDirDrive:
      v26 = CopyStringW(v42);
      goto LABEL_36;
    case WTSUserConfigfTerminalServerRemoteHomeDir:
      do
        ++v10;
      while ( v42[v10] );
      v25 = v10 != 0;
LABEL_35:
      LODWORD(servername) = v25;
      v26 = CopyData(&servername, 4u);
      goto LABEL_36;
    case WTSUserConfigUser:
      v26 = CollectUserInfoForQuery(v31, ppBuffer, pBytesReturned);
LABEL_36:
      v9 = v26;
      break;
    default:
      break;
  }
LABEL_57:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return v9;
}

```

## disassembly

```asm
0x180005c60  mov     r11, rsp
0x180005c63  push    rbp
0x180005c64  push    rbx
0x180005c65  lea     rbp, [r11-988h]
0x180005c6c  sub     rsp, 0A78h
0x180005c73  mov     rax, cs:__security_cookie
0x180005c7a  xor     rax, rsp
0x180005c7d  mov     [rbp+980h+var_40], rax
0x180005c84  mov     [r11+18h], rsi
0x180005c88  mov     rsi, [rbp+980h+pBytesReturned]
0x180005c8f  mov     [r11-18h], rdi
0x180005c93  mov     rdi, r9
0x180005c96  mov     [r11-20h], r12
0x180005c9a  mov     [r11-28h], r13
0x180005c9e  mov     [r11-30h], r14
0x180005ca2  mov     r14, rcx
0x180005ca5  mov     [r11-38h], r15
0x180005ca9  lea     rcx, [rsp+0A80h+var_A30]; void *
0x180005cae  mov     r15, rdx
0x180005cb1  movsxd  r12, r8d
0x180005cb4  xor     edx, edx; Val
0x180005cb6  mov     r8d, 9E8h; Size
0x180005cbc  call    memset_0
0x180005cc1  xor     ebx, ebx
0x180005cc3  mov     dword ptr [rsp+0A80h+var_A48], ebx
0x180005cc7  mov     [rsp+0A80h+bufptr], rbx
0x180005ccc  test    rdi, rdi
0x180005ccf  jz      loc_180005FD6
0x180005cd5  test    rsi, rsi
0x180005cd8  jz      loc_180005FD6
0x180005cde  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180005ce5  test    r15, r15
0x180005ce8  jnz     short loc_180005D29
0x180005cea  lea     r9, [rsp+0A80h+var_A48]
0x180005cef  mov     r8d, 9E8h
0x180005cf5  lea     rdx, [rsp+0A80h+var_A30]
0x180005cfa  mov     rcx, r14
0x180005cfd  call    cs:__imp_RegDefaultUserConfigQueryW
0x180005d03  test    eax, eax
0x180005d05  jnz     def_180005D27; jumptable 0000000180005D27 default case
0x180005d0b  cmp     r12d, 13h; switch 20 cases
0x180005d0f  ja      def_180005D27; jumptable 0000000180005D27 default case
0x180005d15  lea     rdx, __ImageBase
0x180005d1c  mov     ecx, ds:(jpt_180005D27 - 180000000h)[rdx+r12*4]
0x180005d24  add     rcx, rdx
0x180005d27  jmp     rcx; switch jump
0x180005d29  test    r14, r14
0x180005d2c  jz      short loc_180005D45
0x180005d2e  mov     rax, r13
0x180005d31  inc     rax
0x180005d34  cmp     [r14+rax*2], bx
0x180005d39  jnz     short loc_180005D31
0x180005d3b  cmp     rax, 11h
0x180005d3f  ja      loc_180005FD6
0x180005d45  lea     r9, [rsp+0A80h+bufptr]; bufptr
0x180005d4a  xor     r8d, r8d; level
0x180005d4d  mov     rdx, r15; username
0x180005d50  mov     rcx, r14; servername
0x180005d53  call    cs:__imp_NetUserGetInfo
0x180005d59  test    eax, eax
0x180005d5b  jz      loc_180005E3D
0x180005d61  test    r14, r14
0x180005d64  jz      loc_180005E3D
0x180005d6a  mov     rax, r13
0x180005d6d  inc     rax
0x180005d70  cmp     [r14+rax*2], bx
0x180005d75  jnz     short loc_180005D6D
0x180005d77  add     eax, 3
0x180005d7a  mov     ecx, 40h ; '@'; uFlags
0x180005d7f  mov     r13d, eax
0x180005d82  lea     rdx, ds:0[rax*2]; uBytes
0x180005d8a  call    cs:__imp_LocalAlloc
0x180005d90  mov     [rsp+0A80h+servername], rax
0x180005d95  mov     r10, rax
0x180005d98  test    rax, rax
0x180005d9b  jz      def_180005D27; jumptable 0000000180005D27 default case
0x180005da1  test    r13, r13
0x180005da4  jz      short loc_180005DF7
0x180005da6  cmp     r13, 7FFFFFFFh
0x180005dad  jbe     short loc_180005DB6
0x180005daf  xor     ecx, ecx
0x180005db1  mov     [rax], cx
0x180005db4  jmp     short loc_180005DF7
0x180005db6  mov     edx, 7FFFFFFEh
0x180005dbb  lea     r8, asc_180017D70; "\\\\"
0x180005dc2  mov     r9, r13
0x180005dc5  test    rdx, rdx
0x180005dc8  jz      short loc_180005DE7
0x180005dca  movzx   ecx, word ptr [r8]
0x180005dce  test    cx, cx
0x180005dd1  jz      short loc_180005DE7
0x180005dd3  mov     [rax], cx
0x180005dd6  add     r8, 2
0x180005dda  add     rax, 2
0x180005dde  dec     rdx
0x180005de1  sub     r9, 1
0x180005de5  jnz     short loc_180005DC5
0x180005de7  test    r9, r9
0x180005dea  lea     rcx, [rax-2]
0x180005dee  cmovnz  rcx, rax
0x180005df2  xor     eax, eax
0x180005df4  mov     [rcx], ax
0x180005df7  mov     r8, r14; pszSrc
0x180005dfa  mov     rdx, r13; cchDest
0x180005dfd  mov     rcx, r10; pszDest
0x180005e00  call    StringCchCatW
0x180005e05  mov     rcx, [rsp+0A80h+servername]; servername
0x180005e0a  lea     r9, [rsp+0A80h+bufptr]; bufptr
0x180005e0f  xor     r8d, r8d; level
0x180005e12  mov     rdx, r15; username
0x180005e15  call    cs:__imp_NetUserGetInfo
0x180005e1b  mov     rcx, [rsp+0A80h+servername]; hMem
0x180005e20  mov     r13d, eax
0x180005e23  call    cs:__imp_LocalFree
0x180005e29  test    r13d, r13d
0x180005e2c  jz      short loc_180005E36
0x180005e2e  mov     ecx, r13d
0x180005e31  jmp     loc_180005FDB
0x180005e36  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180005e3d  lea     rax, [rsp+0A80h+var_A48]
0x180005e42  mov     r9d, 9E8h
0x180005e48  lea     r8, [rsp+0A80h+var_A30]
0x180005e4d  mov     [rsp+20h], rax
0x180005e52  mov     rdx, r15
0x180005e55  mov     rcx, r14
0x180005e58  call    cs:__imp_RegUserConfigQuery
0x180005e5e  test    eax, eax
0x180005e60  jz      loc_180005D0B
0x180005e66  lea     r9, [rsp+0A80h+var_A48]
0x180005e6b  mov     r8d, 9E8h
0x180005e71  lea     rdx, [rsp+0A80h+var_A30]
0x180005e76  mov     rcx, r14
0x180005e79  call    cs:__imp_RegDefaultUserConfigQueryW
0x180005e7f  test    eax, eax
0x180005e81  jz      loc_180005D0B
0x180005e87  mov     ecx, eax
0x180005e89  jmp     loc_180005FDB
0x180005e8e  mov     r8, rsi; jumptable 0000000180005D27 case 0
0x180005e91  lea     rcx, [rbp+980h+Src]; Src
0x180005e98  mov     rdx, rdi
0x180005e9b  call    _CopyStringW
0x180005ea0  mov     ebx, eax
0x180005ea2  jmp     def_180005D27; jumptable 0000000180005D27 default case
0x180005ea7  mov     r8, rsi; jumptable 0000000180005D27 case 1
0x180005eaa  lea     rcx, [rbp+980h+var_9BC]; Src
0x180005eae  mov     rdx, rdi
0x180005eb1  call    _CopyStringW
0x180005eb6  mov     ebx, eax
0x180005eb8  jmp     def_180005D27; jumptable 0000000180005D27 default case
0x180005ebd  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180005D27 case 2
0x180005ec1  shr     eax, 3
0x180005ec4  and     eax, 1
0x180005ec7  mov     r9, rsi
0x180005eca  mov     dword ptr [rsp+0A80h+servername], eax
0x180005ece  mov     r8, rdi
0x180005ed1  lea     rcx, [rsp+0A80h+servername]; Src
0x180005ed6  mov     edx, 4; Size
0x180005edb  call    _CopyData
0x180005ee0  mov     ebx, eax
0x180005ee2  jmp     def_180005D27; jumptable 0000000180005D27 default case
0x180005ee7  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180005D27 case 3
0x180005eeb  shr     eax, 0Fh
0x180005eee  not     eax
0x180005ef0  jmp     short loc_180005EC4
0x180005ef2  mov     eax, [rbp+980h+var_548]; jumptable 0000000180005D27 case 4
0x180005ef8  jmp     short loc_180005EC7
0x180005efa  mov     eax, [rbp+980h+var_544]; jumptable 0000000180005D27 case 5
0x180005f00  jmp     short loc_180005EC7
0x180005f02  mov     eax, [rbp+980h+var_540]; jumptable 0000000180005D27 case 6
0x180005f08  jmp     short loc_180005EC7
0x180005f0a  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180005D27 case 7
0x180005f0e  shr     eax, 11h
0x180005f11  jmp     short loc_180005EC4
0x180005f13  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180005D27 case 8
0x180005f17  shr     eax, 12h
0x180005f1a  jmp     short loc_180005EC4
0x180005f1c  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180005D27 case 9
0x180005f20  shr     eax, 13h
0x180005f23  jmp     short loc_180005EC4
0x180005f25  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180005D27 case 10
0x180005f29  shr     eax, 0Dh
0x180005f2c  jmp     short loc_180005EC4
0x180005f2e  mov     eax, [rsp+0A80h+var_A30]; jumptable 0000000180005D27 case 11
0x180005f32  shr     eax, 0Eh
0x180005f35  jmp     short loc_180005EC4
0x180005f37  mov     eax, [rbp+980h+var_550]; jumptable 0000000180005D27 case 12
0x180005f3d  jmp     short loc_180005EC7
0x180005f3f  mov     r8, rsi; jumptable 0000000180005D27 case 13
0x180005f42  lea     rcx, [rbp+980h+var_5B8]; Src
0x180005f49  mov     rdx, rdi
0x180005f4c  call    _CopyStringW
0x180005f51  jmp     short loc_180005EE0
0x180005f53  mov     eax, [rbp+980h+var_54C]; jumptable 0000000180005D27 case 14
0x180005f59  jmp     loc_180005EC7
0x180005f5e  mov     r8, rsi; jumptable 0000000180005D27 case 15
0x180005f61  lea     rcx, [rbp+980h+var_454]; Src
0x180005f68  mov     rdx, rdi
0x180005f6b  call    _CopyStringW
0x180005f70  jmp     loc_180005EE0
0x180005f75  mov     r8, rsi; jumptable 0000000180005D27 case 16
0x180005f78  lea     rcx, [rbp+980h+var_252]; Src
0x180005f7f  mov     rdx, rdi
0x180005f82  call    _CopyStringW
0x180005f87  jmp     loc_180005EE0
0x180005f8c  mov     r8, rsi; jumptable 0000000180005D27 case 17
0x180005f8f  lea     rcx, [rbp+980h+var_50]; Src
0x180005f96  mov     rdx, rdi
0x180005f99  call    _CopyStringW
0x180005f9e  jmp     loc_180005EE0
0x180005fa3  lea     rax, [rbp+980h+var_50]; jumptable 0000000180005D27 case 18
0x180005faa  inc     r13
0x180005fad  cmp     [rax+r13*2], bx
0x180005fb2  jnz     short loc_180005FAA
0x180005fb4  xor     eax, eax
0x180005fb6  test    r13, r13
0x180005fb9  setnz   al
0x180005fbc  jmp     loc_180005EC7
0x180005fc1  mov     r8, rsi; jumptable 0000000180005D27 case 19
0x180005fc4  lea     rcx, [rsp+0A80h+var_A30]
0x180005fc9  mov     rdx, rdi
0x180005fcc  call    CollectUserInfoForQuery
0x180005fd1  jmp     loc_180005EE0
0x180005fd6  mov     ecx, 57h ; 'W'; dwErrCode
0x180005fdb  call    cs:__imp_SetLastError
0x180005fe1  mov     rcx, [rsp+0A80h+bufptr]; jumptable 0000000180005D27 default case
0x180005fe6  mov     r15, [rsp+0A80h+var_30]
0x180005fee  mov     r14, [rsp+0A80h+var_28]
0x180005ff6  mov     r13, [rsp+0A80h+var_20]
0x180005ffe  mov     r12, [rsp+0A80h+var_18]
0x180006006  mov     rdi, [rsp+0A70h]
0x18000600e  mov     rsi, [rsp+0A80h+arg_10]
0x180006016  test    rcx, rcx
0x180006019  jz      short loc_180006021
0x18000601b  call    cs:__imp_NetApiBufferFree
0x180006021  mov     eax, ebx
0x180006023  mov     rcx, [rbp+980h+var_40]
0x18000602a  xor     rcx, rsp; StackCookie
0x18000602d  call    __security_check_cookie
0x180006032  add     rsp, 0A78h
0x180006039  pop     rbx
0x18000603a  pop     rbp
0x18000603b  retn
```
