# WTSCreateListenerW

- ea: `0x18000a580`
- end: `0x18000ace8`
- name: `WTSCreateListenerW`
- size: `1896`
- prototype: `BOOL __stdcall(HANDLE hServer, PVOID pReserved, DWORD Reserved, LPWSTR pListenerName, PWTSLISTENERCONFIGW pBuffer, DWORD flag)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a490`

## callees

- `0x180004150`
- `0x18000a580`
- `0x18000eedc`
- `0x18000ef34`
- `0x18000ef9c`
- `0x18000efdc`
- `0x180015582`
- `0x18001558e`
- `0x1800155c0`
- `0x180015650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aaf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000acb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aaf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000acb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aca5`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000aaac`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000aaac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aba2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac8c`
- `REGAPI!RegWinStationCreateW` at `0x18000aa26`
- `REGAPI!RegWinStationCreateW` at `0x18000aa26`
- `REGAPI!RegWdQueryW` at `0x18000a6be`
- `REGAPI!RegWdQueryW` at `0x18000a6be`
- `REGAPI!RegWinstationQuerySecurityConfig_Machine` at `0x18000a878`
- `REGAPI!RegWinstationQuerySecurityConfig_Machine` at `0x18000a878`
- `REGAPI!RegWinStationQueryW` at `0x18000a862`
- `REGAPI!RegWinStationQueryW` at `0x18000a862`
- `REGAPI!RegWinstationSetSecurityConfig` at `0x18000aa4a`
- `REGAPI!RegWinstationSetSecurityConfig` at `0x18000aa4a`
- `REGAPI!RegPdQueryW` at `0x18000a776`
- `REGAPI!RegPdQueryW` at `0x18000a776`
- `REGAPI!RegWinStationQueryExtendedSettingsW` at `0x18000aa97`
- `REGAPI!RegWinStationQueryExtendedSettingsW` at `0x18000aac6`
- `REGAPI!RegWinStationQueryExtendedSettingsW` at `0x18000aa97`
- `REGAPI!RegWinStationQueryExtendedSettingsW` at `0x18000aac6`
- `REGAPI!RegWinStationSetExtendedSettingsW` at `0x18000aadd`
- `REGAPI!RegWinStationSetExtendedSettingsW` at `0x18000aadd`

## string_xrefs

- `0x18000abbc`: `PdDLL`
- `0x18000ac1d`: `PdDLL1`

## pseudocode

```c
BOOL __stdcall WTSCreateListenerW(
        HANDLE hServer,
        PVOID pReserved,
        DWORD Reserved,
        LPWSTR pListenerName,
        PWTSLISTENERCONFIGW pBuffer,
        DWORD flag)
{
  BOOL v10; // r15d
  LSTATUS v11; // ebx
  DWORD SecurityConfig_Machine; // eax
  DWORD v13; // ecx
  __int64 v14; // rdx
  char *v15; // rax
  _OWORD *v16; // rcx
  __int64 v17; // r8
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  int v27; // edx
  int v28; // ecx
  int v29; // eax
  char fEnableListener; // r12
  int v31; // edx
  int v32; // edx
  unsigned int v33; // ecx
  int v34; // ecx
  unsigned int v35; // r10d
  __int64 v36; // r8
  HLOCAL v37; // rsi
  unsigned int i; // ebx
  LSTATUS v39; // eax
  HLOCAL v40; // rax
  DWORD v41; // ecx
  __int64 v42; // rcx
  int v43; // r8d
  int v44; // r8d
  unsigned int NumValue; // ebx
  unsigned int v46; // edi
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  DWORD LastError; // ebx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v56; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v57; // [rsp+50h] [rbp-B0h] BYREF
  int v58; // [rsp+58h] [rbp-A8h] BYREF
  int v59; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v61[288]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v62[4]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v63; // [rsp+1D0h] [rbp+D0h]
  __int128 v64; // [rsp+1E0h] [rbp+E0h]
  __int128 v65; // [rsp+1F0h] [rbp+F0h]
  __int128 v66; // [rsp+200h] [rbp+100h]
  __int128 v67; // [rsp+210h] [rbp+110h]
  __int128 v68; // [rsp+220h] [rbp+120h]
  __int64 v69; // [rsp+230h] [rbp+130h]
  _DWORD v70[2]; // [rsp+560h] [rbp+460h] BYREF
  __int128 v71; // [rsp+568h] [rbp+468h]
  __int128 v72; // [rsp+578h] [rbp+478h]
  __int128 v73; // [rsp+588h] [rbp+488h]
  __int128 v74; // [rsp+598h] [rbp+498h]
  __int128 v75; // [rsp+5A8h] [rbp+4A8h]
  __int128 v76; // [rsp+5B8h] [rbp+4B8h]
  __int128 v77; // [rsp+5C8h] [rbp+4C8h]
  __int128 v78; // [rsp+5D8h] [rbp+4D8h]
  __int128 v79; // [rsp+5E8h] [rbp+4E8h]
  __int128 v80; // [rsp+5F8h] [rbp+4F8h]
  __int64 v81; // [rsp+608h] [rbp+508h]
  int v82; // [rsp+610h] [rbp+510h]
  ULONG LanAdapter; // [rsp+614h] [rbp+514h]
  char v84; // [rsp+2228h] [rbp+2128h] BYREF
  wchar_t pszDest[62]; // [rsp+23E0h] [rbp+22E0h] BYREF
  int v86; // [rsp+245Ch] [rbp+235Ch] BYREF
  unsigned int v87; // [rsp+2460h] [rbp+2360h]
  wchar_t v88[21]; // [rsp+2464h] [rbp+2364h] BYREF
  wchar_t v89[33]; // [rsp+248Eh] [rbp+238Eh] BYREF
  wchar_t v90[257]; // [rsp+24D0h] [rbp+23D0h] BYREF
  wchar_t v91[311]; // [rsp+26D2h] [rbp+25D2h] BYREF
  ULONG ShadowSettings; // [rsp+2940h] [rbp+2840h]
  ULONG TimeoutSettingsConnection; // [rsp+2944h] [rbp+2844h]
  ULONG TimeoutSettingsDisconnection; // [rsp+2948h] [rbp+2848h]
  ULONG TimeoutSettingsIdle; // [rsp+294Ch] [rbp+284Ch]
  char MinEncryptionLevel; // [rsp+2954h] [rbp+2854h]
  _BYTE v97[864]; // [rsp+2E50h] [rbp+2D50h] BYREF
  _BYTE Src[2544]; // [rsp+31B0h] [rbp+30B0h] BYREF
  _BYTE v99[80]; // [rsp+3BA0h] [rbp+3AA0h] BYREF
  _BYTE v100[80]; // [rsp+3BF0h] [rbp+3AF0h] BYREF

  v10 = 0;
  memset_0(v97, 0, 0xD48u);
  WORD1(v63) = 0;
  memset_0(v62, 0, 0x3C2u);
  v58 = 0;
  memset_0(v61, 0, sizeof(v61));
  v56 = 0;
  hKey = 0;
  v57 = 0;
  v59 = 0;
  LODWORD(uBytes) = 0;
  if ( hServer
    || pReserved
    || Reserved
    || !pListenerName
    || !pBuffer
    || (v11 = 1, flag != 1) && flag != 16
    || pBuffer->version != 1 )
  {
    v13 = 87;
    goto LABEL_49;
  }
  memset_0(v70, 0, 0x28E8u);
  if ( flag == 1 )
  {
    SecurityConfig_Machine = RegWdQueryW(0, L"rdpwd", v97, 3400, &v58);
    if ( SecurityConfig_Machine )
      goto LABEL_11;
    v14 = 2;
    v15 = &v84;
    v16 = v97;
    v17 = 128;
    do
    {
      v18 = v16[1];
      *(_OWORD *)v15 = *v16;
      v19 = v16[2];
      *((_OWORD *)v15 + 1) = v18;
      v20 = v16[3];
      *((_OWORD *)v15 + 2) = v19;
      v21 = v16[4];
      *((_OWORD *)v15 + 3) = v20;
      v22 = v16[5];
      *((_OWORD *)v15 + 4) = v21;
      v23 = v16[6];
      *((_OWORD *)v15 + 5) = v22;
      v24 = v16[7];
      v16 += 8;
      *((_OWORD *)v15 + 6) = v23;
      *((_OWORD *)v15 + 7) = v24;
      v15 += 128;
      --v14;
    }
    while ( v14 );
    LOBYTE(v17) = 1;
    v25 = v16[1];
    *(_OWORD *)v15 = *v16;
    v26 = *(_OWORD *)((char *)v16 + 28);
    *((_OWORD *)v15 + 1) = v25;
    *(_OWORD *)(v15 + 28) = v26;
    SecurityConfig_Machine = RegPdQueryW(0, L"rdpwd", v17, L"tcp", v62, 964, &v58);
    if ( SecurityConfig_Machine )
      goto LABEL_11;
    memset_0(v61, 0, sizeof(v61));
    v71 = v62[0];
    v81 = v69;
    v72 = v62[1];
    v73 = v62[2];
    v74 = v62[3];
    v75 = v63;
    v76 = v64;
    v77 = v65;
    v78 = v66;
    v79 = v67;
    v80 = v68;
    memcpy_0(&v86, Src, 0x9E8u);
  }
  else
  {
    SecurityConfig_Machine = RegWinStationQueryW(0, pListenerName, v70, 10472, &v59);
    if ( SecurityConfig_Machine )
      goto LABEL_11;
    SecurityConfig_Machine = RegWinstationQuerySecurityConfig_Machine(pListenerName, v61);
    if ( SecurityConfig_Machine )
      goto LABEL_11;
  }
  v70[1] = pBuffer->MaxConnectionCount;
  v27 = 2 * LOBYTE(pBuffer->fDisableComPortRedirection);
  v28 = pBuffer->fDisablePNPRedirection & 1;
  v29 = pBuffer->fDisableDriveRedirection & 1;
  v70[0] &= ~1u;
  fEnableListener = pBuffer->fEnableListener;
  v31 = pBuffer->fDisablePrinterRedirection & 1 | (2 * (v29 | v27));
  v82 = 2;
  v32 = v86 & 0x1FFFEFFD
      | (2 * (pBuffer->fInheritBrokenTimeoutSettings & 1 | ((pBuffer->fPromptForPassword & 1 | (v31 << 17)) << 11)));
  v33 = v87 & 0xFFFFF614
      | pBuffer->fDisableLPTPortRedirection & 1
      | (2
       * (pBuffer->fDisableClipboardRedirection & 1
        | (4
         * (pBuffer->fDisableAudioRedirection & 1
          | (4 * (pBuffer->ColorDepth & 7 | (8 * (pBuffer->fInheritColorDepth & 1 | (8 * v28)))))))));
  LanAdapter = pBuffer->LanAdapter;
  LODWORD(v81) = pBuffer->PortNumber;
  LOBYTE(v29) = LOBYTE(pBuffer->fInheritShadowSettings) << 6;
  v87 = v33;
  v34 = v32 ^ (v32 ^ (LOBYTE(pBuffer->fDisableDefaultMainClientPrinter) << 19)) & 0x80000;
  v86 = v34 ^ ((unsigned __int8)v34 ^ (unsigned __int8)v29) & 0x40;
  ShadowSettings = pBuffer->ShadowSettings;
  TimeoutSettingsConnection = pBuffer->TimeoutSettingsConnection;
  TimeoutSettingsDisconnection = pBuffer->TimeoutSettingsDisconnection;
  TimeoutSettingsIdle = pBuffer->TimeoutSettingsIdle;
  MinEncryptionLevel = pBuffer->MinEncryptionLevel;
  StringCchCopyW(pszDest, 0x3Du, pBuffer->Comment);
  StringCchCopyW(v88, 0x15u, pBuffer->LogonUserName);
  StringCchCopyW(v89, 0x12u, pBuffer->LogonDomain);
  StringCchCopyW(v90, 0x101u, pBuffer->WorkDirectory);
  StringCchCopyW(v91, v35, pBuffer->InitialProgram);
  LOBYTE(v36) = flag == 1;
  SecurityConfig_Machine = RegWinStationCreateW(0, pListenerName, v36, v70, 10472);
  if ( SecurityConfig_Machine
    || (v61[0] = pBuffer->SecurityLayer,
        v61[1] = pBuffer->UserAuthentication,
        (SecurityConfig_Machine = RegWinstationSetSecurityConfig(pListenerName, v61)) != 0) )
  {
LABEL_11:
    v13 = SecurityConfig_Machine;
LABEL_49:
    SetLastError(v13);
    return v10;
  }
  v37 = 0;
  if ( flag == 1 )
  {
    LODWORD(uBytes) = 524;
    v37 = LocalAlloc(0, 0x20Cu);
    if ( !v37 )
      return v10;
    for ( i = 0; (int)i < 2; ++i )
    {
      v39 = RegWinStationQueryExtendedSettingsW(0, i, v37, &uBytes);
      if ( v39 == 122 )
      {
        v40 = LocalReAlloc(v37, (unsigned int)uBytes, 0);
        v37 = v40;
        if ( !v40 )
        {
          v13 = 14;
          goto LABEL_49;
        }
        v39 = RegWinStationQueryExtendedSettingsW(0, i, v40, &uBytes);
      }
      if ( v39 )
        goto LABEL_31;
      v39 = RegWinStationSetExtendedSettingsW(pListenerName, i, v37, (unsigned int)uBytes);
      if ( v39 )
        goto LABEL_31;
    }
    v11 = 1;
LABEL_36:
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
           0,
           0x20006u,
           &hKey)
      || (v11 = RegOpenKeyExW(hKey, pListenerName, 0, 0x20006u, &v56), RegCloseKey(hKey), v11) )
    {
      v41 = v11;
    }
    else
    {
      if ( flag != 1 )
      {
LABEL_42:
        if ( fEnableListener == 1 )
          SetNumValue(v42, v56, L"fEnableWinStation", 1);
        RegCloseKey(v56);
        goto LABEL_45;
      }
      v39 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Control\\Terminal Server\\Wds\\rdpwd\\Pds\\tssecsrv",
              0,
              0x20019u,
              &v57);
      if ( !v39 )
      {
        GetStringValue((_DWORD)v57, (unsigned int)L"PdDLL", v43, (unsigned int)v99, phkResult);
        GetStringValue((_DWORD)v57, (unsigned int)L"PdName", v44, (unsigned int)v100, phkResulta);
        NumValue = GetNumValue(v57, L"PdClass");
        v46 = GetNumValue(v57, L"PdFlag");
        RegCloseKey(v57);
        SetStringValue(v47, v56, L"PdDLL1", v99);
        SetStringValue(v48, v56, L"PdName1", v100);
        SetNumValue(v49, v56, L"PdClass1", NumValue);
        SetNumValue(v50, v56, L"PdFlag1", v46);
        goto LABEL_42;
      }
LABEL_31:
      v41 = v39;
    }
    SetLastError(v41);
    goto LABEL_46;
  }
  if ( fEnableListener == 1 )
    goto LABEL_36;
LABEL_45:
  v10 = 1;
LABEL_46:
  if ( v37 )
  {
    LastError = GetLastError();
    LocalFree(v37);
    v13 = LastError;
    goto LABEL_49;
  }
  return v10;
}

```

## disassembly

```asm
0x18000a580  mov     [rsp-8+arg_0], rbx
0x18000a585  mov     [rsp-8+arg_8], rsi
0x18000a58a  push    rbp
0x18000a58b  push    rdi
0x18000a58c  push    r12
0x18000a58e  push    r14
0x18000a590  push    r15
0x18000a592  lea     rbp, [rsp-3B50h]
0x18000a59a  mov     eax, 3C50h
0x18000a59f  call    _alloca_probe
0x18000a5a4  sub     rsp, rax
0x18000a5a7  mov     rax, cs:__security_cookie
0x18000a5ae  xor     rax, rsp
0x18000a5b1  mov     [rbp+3B70h+var_30], rax
0x18000a5b8  mov     rsi, [rbp+3B70h+pBuffer]
0x18000a5bf  mov     r12d, r8d
0x18000a5c2  mov     r14, rdx
0x18000a5c5  mov     rbx, rcx
0x18000a5c8  xor     edx, edx; Val
0x18000a5ca  lea     rcx, [rbp+3B70h+var_E20]; void *
0x18000a5d1  mov     r8d, 0D48h; Size
0x18000a5d7  mov     rdi, r9
0x18000a5da  xor     r15d, r15d
0x18000a5dd  call    memset_0
0x18000a5e2  xor     eax, eax
0x18000a5e4  lea     rcx, [rbp+3B70h+var_3AE0]; void *
0x18000a5eb  xor     edx, edx; Val
0x18000a5ed  mov     [rbp+3B70h+var_3A9E], ax
0x18000a5f4  mov     r8d, 3C2h; Size
0x18000a5fa  call    memset_0
0x18000a5ff  xor     edx, edx; Val
0x18000a601  mov     [rsp+3C70h+var_3C18], r15d
0x18000a606  mov     r8d, 120h; Size
0x18000a60c  lea     rcx, [rsp+3C70h+var_3C00]; void *
0x18000a611  call    memset_0
0x18000a616  mov     [rsp+3C70h+var_3C28], r15
0x18000a61b  mov     [rsp+3C70h+hKey], r15
0x18000a620  mov     [rsp+3C70h+var_3C20], r15
0x18000a625  mov     [rsp+3C70h+var_3C14], r15d
0x18000a62a  mov     dword ptr [rsp+3C70h+uBytes], r15d
0x18000a62f  test    rbx, rbx
0x18000a632  jnz     loc_18000ACAF
0x18000a638  test    r14, r14
0x18000a63b  jnz     loc_18000ACAF
0x18000a641  test    r12d, r12d
0x18000a644  jnz     loc_18000ACAF
0x18000a64a  test    rdi, rdi
0x18000a64d  jz      loc_18000ACAF
0x18000a653  test    rsi, rsi
0x18000a656  jz      loc_18000ACAF
0x18000a65c  mov     r14d, [rbp+3B70h+flag]
0x18000a663  lea     ebx, [r15+1]
0x18000a667  cmp     r14d, ebx
0x18000a66a  jz      short loc_18000A676
0x18000a66c  cmp     r14d, 10h
0x18000a670  jnz     loc_18000ACAF
0x18000a676  cmp     [rsi], ebx
0x18000a678  jnz     loc_18000ACAF
0x18000a67e  mov     r12d, 28E8h
0x18000a684  lea     rcx, [rbp+3B70h+var_3710]; void *
0x18000a68b  mov     r8d, r12d; Size
0x18000a68e  xor     edx, edx; Val
0x18000a690  call    memset_0
0x18000a695  xor     ecx, ecx
0x18000a697  cmp     r14d, ebx
0x18000a69a  jnz     loc_18000A84B
0x18000a6a0  lea     rax, [rsp+3C70h+var_3C18]
0x18000a6a5  mov     r9d, 0D48h
0x18000a6ab  lea     r8, [rbp+3B70h+var_E20]
0x18000a6b2  mov     [rsp+3C70h+phkResult], rax
0x18000a6b7  lea     rdx, aRdpwd; "rdpwd"
0x18000a6be  call    cs:__imp_RegWdQueryW
0x18000a6c4  test    eax, eax
0x18000a6c6  jz      short loc_18000A6CF
0x18000a6c8  mov     ecx, eax
0x18000a6ca  jmp     loc_18000ACB4
0x18000a6cf  mov     edx, 2
0x18000a6d4  lea     rax, [rbp+3B70h+var_1A48]
0x18000a6db  lea     rcx, [rbp+3B70h+var_E20]
0x18000a6e2  lea     r8d, [rdx+7Eh]
0x18000a6e6  movups  xmm0, xmmword ptr [rcx]
0x18000a6e9  movups  xmm1, xmmword ptr [rcx+10h]
0x18000a6ed  movups  xmmword ptr [rax], xmm0
0x18000a6f0  movups  xmm0, xmmword ptr [rcx+20h]
0x18000a6f4  movups  xmmword ptr [rax+10h], xmm1
0x18000a6f8  movups  xmm1, xmmword ptr [rcx+30h]
0x18000a6fc  movups  xmmword ptr [rax+20h], xmm0
0x18000a700  movups  xmm0, xmmword ptr [rcx+40h]
0x18000a704  movups  xmmword ptr [rax+30h], xmm1
0x18000a708  movups  xmm1, xmmword ptr [rcx+50h]
0x18000a70c  movups  xmmword ptr [rax+40h], xmm0
0x18000a710  movups  xmm0, xmmword ptr [rcx+60h]
0x18000a714  movups  xmmword ptr [rax+50h], xmm1
0x18000a718  movups  xmm1, xmmword ptr [rcx+70h]
0x18000a71c  add     rcx, r8
0x18000a71f  movups  xmmword ptr [rax+60h], xmm0
0x18000a723  movups  xmmword ptr [rax+70h], xmm1
0x18000a727  add     rax, r8
0x18000a72a  sub     rdx, rbx
0x18000a72d  jnz     short loc_18000A6E6
0x18000a72f  movups  xmm0, xmmword ptr [rcx]
0x18000a732  lea     r9, aTcp; "tcp"
0x18000a739  mov     r8b, bl
0x18000a73c  movups  xmm1, xmmword ptr [rcx+10h]
0x18000a740  lea     rdx, aRdpwd; "rdpwd"
0x18000a747  movups  xmmword ptr [rax], xmm0
0x18000a74a  movups  xmm0, xmmword ptr [rcx+1Ch]
0x18000a74e  xor     ecx, ecx
0x18000a750  movups  xmmword ptr [rax+10h], xmm1
0x18000a754  movups  xmmword ptr [rax+1Ch], xmm0
0x18000a758  lea     rax, [rsp+3C70h+var_3C18]
0x18000a75d  mov     [rsp+3C70h+var_3C40], rax
0x18000a762  lea     rax, [rbp+3B70h+var_3AE0]
0x18000a769  mov     [rsp+3C70h+var_3C48], 3C4h
0x18000a771  mov     [rsp+3C70h+phkResult], rax
0x18000a776  call    cs:__imp_RegPdQueryW
0x18000a77c  test    eax, eax
0x18000a77e  jnz     loc_18000A6C8
0x18000a784  xor     edx, edx; Val
0x18000a786  lea     rcx, [rsp+3C70h+var_3C00]; void *
0x18000a78b  mov     r8d, 120h; Size
0x18000a791  call    memset_0
0x18000a796  movaps  xmm0, [rbp+3B70h+var_3AE0]
0x18000a79d  lea     rcx, [rbp+3B70h+var_1814]; void *
0x18000a7a4  movaps  xmm1, [rbp+3B70h+var_3AD0]
0x18000a7ab  lea     rdx, [rbp+3B70h+Src]; Src
0x18000a7b2  mov     rax, [rbp+3B70h+var_3A40]
0x18000a7b9  mov     r8d, 9E8h; Size
0x18000a7bf  movups  [rbp+3B70h+var_3708], xmm0
0x18000a7c6  mov     [rbp+3B70h+var_3668], rax
0x18000a7cd  movaps  xmm0, [rbp+3B70h+var_3AC0]
0x18000a7d4  movups  [rbp+3B70h+var_36F8], xmm1
0x18000a7db  movaps  xmm1, [rbp+3B70h+var_3AB0]
0x18000a7e2  movups  [rbp+3B70h+var_36E8], xmm0
0x18000a7e9  movaps  xmm0, xmmword ptr [rbp+0D0h]
0x18000a7f0  movups  [rbp+3B70h+var_36D8], xmm1
0x18000a7f7  movaps  xmm1, [rbp+3B70h+var_3A90]
0x18000a7fe  movups  [rbp+3B70h+var_36C8], xmm0
0x18000a805  movaps  xmm0, [rbp+3B70h+var_3A80]
0x18000a80c  movups  [rbp+3B70h+var_36B8], xmm1
0x18000a813  movaps  xmm1, [rbp+3B70h+var_3A70]
0x18000a81a  movups  [rbp+3B70h+var_36A8], xmm0
0x18000a821  movaps  xmm0, [rbp+3B70h+var_3A60]
0x18000a828  movups  [rbp+3B70h+var_3698], xmm1
0x18000a82f  movaps  xmm1, [rbp+3B70h+var_3A50]
0x18000a836  movups  [rbp+3B70h+var_3688], xmm0
0x18000a83d  movups  [rbp+3B70h+var_3678], xmm1
0x18000a844  call    memcpy_0
0x18000a849  jmp     short loc_18000A886
0x18000a84b  lea     rax, [rsp+3C70h+var_3C14]
0x18000a850  mov     r9d, r12d
0x18000a853  lea     r8, [rbp+3B70h+var_3710]
0x18000a85a  mov     [rsp+3C70h+phkResult], rax
0x18000a85f  mov     rdx, rdi
0x18000a862  call    cs:__imp_RegWinStationQueryW
0x18000a868  test    eax, eax
0x18000a86a  jnz     loc_18000A6C8
0x18000a870  lea     rdx, [rsp+3C70h+var_3C00]
0x18000a875  mov     rcx, rdi
0x18000a878  call    cs:__imp_RegWinstationQuerySecurityConfig_Machine
0x18000a87e  test    eax, eax
0x18000a880  jnz     loc_18000A6C8
0x18000a886  mov     eax, [rsi+8]
0x18000a889  lea     r8, [rsi+68h]; pszSrc
0x18000a88d  mov     [rbp+3B70h+var_370C], eax
0x18000a893  movzx   edx, byte ptr [rsi+28h]
0x18000a897  movzx   ecx, byte ptr [rsi+38h]
0x18000a89b  add     edx, edx
0x18000a89d  movzx   eax, byte ptr [rsi+24h]
0x18000a8a1  and     ecx, ebx
0x18000a8a3  and     eax, ebx
0x18000a8a5  and     [rbp+3B70h+var_3710], 0FFFFFFFEh
0x18000a8ac  or      edx, eax
0x18000a8ae  mov     r12b, [rsi+4]
0x18000a8b2  movzx   eax, byte ptr [rsi+20h]
0x18000a8b6  add     edx, edx
0x18000a8b8  and     eax, ebx
0x18000a8ba  shl     ecx, 3
0x18000a8bd  or      edx, eax
0x18000a8bf  mov     [rbp+3B70h+var_3660], 2
0x18000a8c9  movzx   eax, byte ptr [rsi+0Ch]
0x18000a8cd  and     eax, ebx
0x18000a8cf  shl     edx, 11h
0x18000a8d2  or      edx, eax
0x18000a8d4  movzx   eax, byte ptr [rsi+18h]
0x18000a8d8  and     eax, ebx
0x18000a8da  shl     edx, 0Bh
0x18000a8dd  or      edx, eax
0x18000a8df  mov     eax, [rbp+3B70h+var_1814]
0x18000a8e5  and     eax, 1FFFEFFDh
0x18000a8ea  add     edx, edx
0x18000a8ec  or      edx, eax
0x18000a8ee  movzx   eax, byte ptr [rsi+10h]
0x18000a8f2  and     eax, ebx
0x18000a8f4  or      ecx, eax
0x18000a8f6  mov     eax, [rsi+14h]
0x18000a8f9  and     eax, 7
0x18000a8fc  shl     ecx, 3
0x18000a8ff  or      ecx, eax
0x18000a901  movzx   eax, byte ptr [rsi+34h]
0x18000a905  and     eax, ebx
0x18000a907  shl     ecx, 2
0x18000a90a  or      ecx, eax
0x18000a90c  movzx   eax, byte ptr [rsi+30h]
0x18000a910  and     eax, ebx
0x18000a912  shl     ecx, 2
0x18000a915  or      ecx, eax
0x18000a917  movzx   eax, byte ptr [rsi+2Ch]
0x18000a91b  and     eax, ebx
0x18000a91d  add     ecx, ecx
0x18000a91f  or      ecx, eax
0x18000a921  mov     eax, [rbp+3B70h+var_1810]
0x18000a927  and     eax, 0FFFFF614h
0x18000a92c  or      ecx, eax
0x18000a92e  mov     eax, [rsi+40h]
0x18000a931  mov     [rbp+3B70h+var_365C], eax
0x18000a937  mov     eax, [rsi+44h]
0x18000a93a  mov     dword ptr [rbp+3B70h+var_3668], eax
0x18000a940  movzx   eax, byte ptr [rsi+48h]
0x18000a944  shl     eax, 6
0x18000a947  mov     [rbp+3B70h+var_1810], ecx
0x18000a94d  movzx   ecx, byte ptr [rsi+3Ch]
0x18000a951  shl     ecx, 13h
0x18000a954  xor     ecx, edx
0x18000a956  and     ecx, 80000h
0x18000a95c  xor     ecx, edx
0x18000a95e  mov     edx, 3Dh ; '='; cchDest
0x18000a963  xor     eax, ecx
0x18000a965  and     eax, 40h
0x18000a968  xor     eax, ecx
0x18000a96a  lea     rcx, [rbp+3B70h+pszDest]; pszDest
0x18000a971  mov     [rbp+3B70h+var_1814], eax
0x18000a977  mov     eax, [rsi+4Ch]
0x18000a97a  mov     [rbp+3B70h+var_1330], eax
0x18000a980  mov     eax, [rsi+50h]
0x18000a983  mov     [rbp+3B70h+var_132C], eax
0x18000a989  mov     eax, [rsi+54h]
0x18000a98c  mov     [rbp+3B70h+var_1328], eax
0x18000a992  mov     eax, [rsi+58h]
0x18000a995  mov     [rbp+3B70h+var_1324], eax
0x18000a99b  mov     al, [rsi+60h]
0x18000a99e  mov     [rbp+3B70h+var_131C], al
0x18000a9a4  call    StringCchCopyW
0x18000a9a9  lea     r8, [rsi+0E2h]; pszSrc
0x18000a9b0  mov     edx, 15h; cchDest
0x18000a9b5  lea     rcx, [rbp+3B70h+var_180C]; pszDest
0x18000a9bc  call    StringCchCopyW
0x18000a9c1  lea     r8, [rsi+10Ch]; pszSrc
0x18000a9c8  mov     edx, 12h; cchDest
0x18000a9cd  lea     rcx, [rbp+3B70h+var_17E2]; pszDest
0x18000a9d4  call    StringCchCopyW
0x18000a9d9  mov     r10d, 101h
0x18000a9df  lea     r8, [rsi+130h]; pszSrc
0x18000a9e6  mov     edx, r10d; cchDest
0x18000a9e9  lea     rcx, [rbp+3B70h+var_17A0]; pszDest
0x18000a9f0  call    StringCchCopyW
0x18000a9f5  lea     r8, [rsi+33Ah]; pszSrc
0x18000a9fc  mov     edx, r10d; cchDest
0x18000a9ff  lea     rcx, [rbp+3B70h+var_159E]; pszDest
0x18000aa06  call    StringCchCopyW
0x18000aa0b  cmp     r14d, ebx
0x18000aa0e  mov     dword ptr [rsp+3C70h+phkResult], 28E8h
0x18000aa16  lea     r9, [rbp+3B70h+var_3710]
0x18000aa1d  mov     rdx, rdi
0x18000aa20  setz    r8b
0x18000aa24  xor     ecx, ecx
0x18000aa26  call    cs:__imp_RegWinStationCreateW
0x18000aa2c  test    eax, eax
0x18000aa2e  jnz     loc_18000A6C8
0x18000aa34  mov     al, [rsi+5Ch]
0x18000aa37  lea     rdx, [rsp+3C70h+var_3C00]
0x18000aa3c  mov     [rsp+3C70h+var_3C00], al
0x18000aa40  mov     rcx, rdi
0x18000aa43  mov     al, [rsi+64h]
0x18000aa46  mov     [rsp+3C70h+var_3BFF], al
0x18000aa4a  call    cs:__imp_RegWinstationSetSecurityConfig
0x18000aa50  test    eax, eax
0x18000aa52  jnz     loc_18000A6C8
0x18000aa58  xor     esi, esi
0x18000aa5a  cmp     r14d, ebx
0x18000aa5d  jnz     loc_18000AB02
0x18000aa63  mov     edx, 20Ch; uBytes
0x18000aa68  xor     ecx, ecx; uFlags
0x18000aa6a  mov     dword ptr [rsp+3C70h+uBytes], edx
0x18000aa6e  call    cs:__imp_LocalAlloc
0x18000aa74  mov     rsi, rax
0x18000aa77  test    rax, rax
0x18000aa7a  jz      loc_18000ACBA
0x18000aa80  xor     ebx, ebx
0x18000aa82  cmp     ebx, 2
0x18000aa85  jge     loc_18000AB0D
0x18000aa8b  lea     r9, [rsp+3C70h+uBytes]
0x18000aa90  mov     r8, rsi
0x18000aa93  mov     edx, ebx
0x18000aa95  xor     ecx, ecx
0x18000aa97  call    cs:__imp_RegWinStationQueryExtendedSettingsW
0x18000aa9d  cmp     eax, 7Ah ; 'z'
0x18000aaa0  jnz     short loc_18000AACC
0x18000aaa2  mov     edx, dword ptr [rsp+3C70h+uBytes]; uBytes
0x18000aaa6  xor     r8d, r8d; uFlags
  ... truncated ...
```
