# CheckForUpgrade(void)

- ea: `0x1800073c0`
- end: `0x180007852`
- name: `?CheckForUpgrade@@YAXXZ`
- size: `1170`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800062c0`
- `0x180006ed0`
- `0x180155a60`
- `0x18016cc70`

## callees

- `0x180006b28`
- `0x1800073c0`
- `0x18003e350`
- `0x1800f3b40`
- `0x1800f3b64`
- `0x1800f40d4`
- `0x1801221e8`
- `0x18012ad4c`
- `0x1801389a8`
- `0x18014a7a0`
- `0x180153e40`
- `0x18016489c`
- `0x18016cfa0`
- `0x18016e1b4`
- `0x1801e1790`
- `0x1801e285c`
- `0x1801e3c24`
- `0x1801e3c78`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000751e`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180007554`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000751e`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180007554`
- `WINHTTP!WinHttpFreeProxySettings` at `0x180007464`
- `WINHTTP!WinHttpFreeProxySettings` at `0x1800075c3`
- `WINHTTP!WinHttpFreeProxySettings` at `0x1800075eb`
- `WINHTTP!WinHttpFreeProxySettings` at `0x1800076c6`
- `WINHTTP!WinHttpFreeProxySettings` at `0x18000781f`
- `WINHTTP!WinHttpFreeProxySettings` at `0x180007464`
- `WINHTTP!WinHttpFreeProxySettings` at `0x1800075c3`
- `WINHTTP!WinHttpFreeProxySettings` at `0x1800075eb`
- `WINHTTP!WinHttpFreeProxySettings` at `0x1800076c6`
- `WINHTTP!WinHttpFreeProxySettings` at `0x18000781f`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000758b`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000758b`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800077eb`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800077eb`

## pseudocode

```c
void CheckForUpgrade(void)
{
  __int64 v0; // r9
  struct CRefdKey *BaseProxyKey; // rax
  HKEY *v2; // rbx
  const CHAR *v3; // rdi
  unsigned int v4; // eax
  RasEnumHelp *v5; // rdi
  unsigned int v6; // edx
  int v7; // r8d
  unsigned int v8; // r14d
  RasEnumHelp *v9; // rax
  RasEnumHelp *v10; // rax
  int v11; // edx
  _WORD *v12; // rdx
  unsigned int i; // esi
  WCHAR *v14; // r10
  __int64 v15; // rcx
  int v16; // [rsp+30h] [rbp-59h] BYREF
  int v17; // [rsp+34h] [rbp-55h]
  WINHTTP_PROXY_SETTINGS pWinHttpProxySettings; // [rsp+40h] [rbp-49h] BYREF
  int pvData; // [rsp+B0h] [rbp+27h] BYREF
  int v20; // [rsp+B4h] [rbp+2Bh] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp+2Fh] BYREF
  DWORD pdwType; // [rsp+BCh] [rbp+33h] BYREF

  pvData = 1;
  v16 = 0;
  pdwType = 0;
  v20 = 0;
  pcbData = 4;
  memset(&pWinHttpProxySettings, 0, sizeof(pWinHttpProxySettings));
  if ( (xmmword_180266B60 & 0x10) != 0 )
    WPP_SF_(1028, 14, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids);
  pWinHttpProxySettings.dwStructSize = 112;
  if ( !(unsigned __int8)IsRasEnumEntriesWPresent() )
  {
    if ( (xmmword_180266B60 & 0x10) != 0 )
      WPP_SF_(1028, 15, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids);
    goto LABEL_7;
  }
  v0 = (unsigned int)_InterlockedExchange(&g_fCheckedUpgrade, 1);
  if ( (_DWORD)v0 )
  {
    if ( (xmmword_180266B60 & 0x10) != 0 )
      WPP_SF_d(1028, 16, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids, v0);
LABEL_7:
    pWinHttpProxySettings.pwszConnectionName = 0;
    WinHttpFreeProxySettings(&pWinHttpProxySettings);
    goto LABEL_8;
  }
  BaseProxyKey = FindBaseProxyKey();
  v2 = (HKEY *)BaseProxyKey;
  if ( !BaseProxyKey || GlobalIsProcessNtService )
  {
    v5 = 0;
    if ( (xmmword_180266B60 & 0x10) != 0 )
    {
      WPP_SF_q(1028, 17, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids, BaseProxyKey);
      pWinHttpProxySettings.pwszConnectionName = 0;
      WinHttpFreeProxySettings(&pWinHttpProxySettings);
      goto LABEL_28;
    }
  }
  else
  {
    v3 = g_pszCurrentUser;
    if ( (xmmword_180266B60 & 0x10) != 0 )
      WPP_SF_s(1028, 18, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids, g_pszCurrentUser);
    if ( CompareStringA(0x7Fu, 1u, v3, -1, ".Default", -1) == 2 || CompareStringA(0x7Fu, 1u, v3, -1, "SYSTEM", -1) == 2 )
      goto LABEL_35;
    if ( SHGetValueW(
           v2[1],
           L"Software\\Microsoft\\windows\\CurrentVersion\\Internet Settings",
           L"MigrateProxy",
           &pdwType,
           &pvData,
           &pcbData) )
    {
      v4 = 0;
      pvData = 0;
    }
    else
    {
      v4 = pvData;
    }
    if ( (xmmword_180266B60 & 0x10) != 0 )
    {
      WPP_SF_d(1028, 19, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids, v4);
      v4 = pvData;
    }
    if ( v4 )
    {
      ReadProxySettings(&pWinHttpProxySettings, 0);
      pWinHttpProxySettings.pwszConnectionName = 0;
      WinHttpFreeProxySettings(&pWinHttpProxySettings);
LABEL_24:
      CloseBaseProxyKey((struct CRefdKey *)v2);
      goto LABEL_8;
    }
    if ( (unsigned int)IsProcessLessThanMediumIL() )
    {
      if ( v2[1] == HKEY_LOCAL_MACHINE )
      {
        if ( (xmmword_180266B60 & 0x10) != 0 )
          WPP_SF_(1028, 20, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids);
      }
      else
      {
        v17 = 0;
        if ( (int)WxRunCom((int (*)(void *))MigrateProxySettingsViaBrokerCallback, 0, v7) < 0 )
          v17 = 732;
      }
LABEL_35:
      pWinHttpProxySettings.pwszConnectionName = 0;
      WinHttpFreeProxySettings(&pWinHttpProxySettings);
      CloseBaseProxyKey((struct CRefdKey *)v2);
      goto LABEL_8;
    }
    v8 = 0;
    v9 = (RasEnumHelp *)operator new(0x10u);
    if ( v9 )
    {
      *(_OWORD *)v9 = 0;
      v10 = RasEnumHelp::RasEnumHelp(v9);
      v5 = v10;
      if ( v10 )
        v8 = *((_DWORD *)v10 + 1);
    }
    else
    {
      v5 = 0;
    }
    if ( (unsigned int)ReadLegacyProxyInfo(&v16, (struct tagProxySettings *)&pWinHttpProxySettings, 0) )
    {
      if ( !v16 )
        pWinHttpProxySettings.dwFlags |= 8u;
      pWinHttpProxySettings.pwszConnectionName = 0;
      WriteProxySettings(&pWinHttpProxySettings, v11);
      if ( !(unsigned int)EnableAutodiscoverForDialup() )
        pWinHttpProxySettings.dwFlags &= ~8u;
      for ( i = 0; i < v8; ++i )
      {
        v14 = 0;
        if ( i < *((_DWORD *)v5 + 1) )
        {
          v15 = 1048LL * i;
          v12 = (_WORD *)(v15 + *((_QWORD *)v5 + 1) + 4LL);
          if ( *v12 )
            v14 = (WCHAR *)(v15 + *((_QWORD *)v5 + 1) + 4LL);
        }
        pWinHttpProxySettings.pwszConnectionName = v14;
        WriteProxySettings(&pWinHttpProxySettings, (int)v12);
      }
    }
    v20 = 1;
    SHSetValueW(
      v2[1],
      L"Software\\Microsoft\\windows\\CurrentVersion\\Internet Settings",
      L"MigrateProxy",
      4u,
      &v20,
      4u);
  }
  pWinHttpProxySettings.pwszConnectionName = 0;
  WinHttpFreeProxySettings(&pWinHttpProxySettings);
  if ( v5 )
    RasEnumHelp::`scalar deleting destructor'(v5, v6);
LABEL_28:
  if ( v2 )
    goto LABEL_24;
LABEL_8:
  if ( (xmmword_180266B60 & 0x10) != 0 )
    WPP_SF_(1028, 21, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids);
}

```

## disassembly

```asm
0x1800073c0  push    rbp
0x1800073c2  lea     rbp, [rsp-57h]
0x1800073c7  sub     rsp, 0E0h
0x1800073ce  mov     rax, cs:__security_cookie
0x1800073d5  xor     rax, rsp
0x1800073d8  mov     [rbp+57h+var_20], rax
0x1800073dc  xorps   xmm0, xmm0
0x1800073df  mov     [rsp+0E0h+var_10], r15
0x1800073e7  xor     r15d, r15d
0x1800073ea  mov     [rbp+57h+pvData], 1
0x1800073f1  mov     [rbp+57h+var_B0], r15d
0x1800073f5  mov     [rbp+57h+pdwType], r15d
0x1800073f9  mov     [rbp+57h+var_2C], r15d
0x1800073fd  mov     [rbp+57h+pcbData], 4
0x180007404  movups  xmmword ptr [rbp+57h+pWinHttpProxySettings.dwStructSize], xmm0
0x180007408  movups  xmmword ptr [rbp+57h+pWinHttpProxySettings.pwszConnectionName], xmm0
0x18000740c  movups  xmmword ptr [rbp+57h+pWinHttpProxySettings.pwszProxyBypass], xmm0
0x180007410  movups  xmmword ptr [rbp+57h+pWinHttpProxySettings.pwszAutoconfigSecondaryUrl], xmm0
0x180007414  movups  xmmword ptr [rbp+57h+pWinHttpProxySettings.pwszLastKnownGoodAutoConfigUrl], xmm0
0x180007418  movups  xmmword ptr [rbp+57h+pWinHttpProxySettings.ftLastKnownDetectTime.dwHighDateTime], xmm0
0x18000741c  movups  xmmword ptr [rbp+57h+pWinHttpProxySettings.cNetworkKeys], xmm0
0x180007420  test    byte ptr cs:xmmword_180266B60, 10h
0x180007427  jnz     loc_180007619
0x18000742d  mov     [rbp+57h+pWinHttpProxySettings.dwStructSize], 70h ; 'p'
0x180007434  call    IsRasEnumEntriesWPresent
0x180007439  test    al, al
0x18000743b  jz      short loc_180007494
0x18000743d  mov     r9d, 1
0x180007443  xchg    r9d, cs:?g_fCheckedUpgrade@@3HA; int g_fCheckedUpgrade
0x18000744a  test    r9d, r9d
0x18000744d  jz      short loc_1800074B5
0x18000744f  test    byte ptr cs:xmmword_180266B60, 10h
0x180007456  jnz     loc_180007634
0x18000745c  lea     rcx, [rbp+57h+pWinHttpProxySettings]; pWinHttpProxySettings
0x180007460  mov     [rbp+57h+pWinHttpProxySettings.pwszConnectionName], r15
0x180007464  call    cs:__imp_WinHttpFreeProxySettings
0x18000746a  test    byte ptr cs:xmmword_180266B60, 10h
0x180007471  mov     r15, [rsp+0E0h+var_10]
0x180007479  jnz     loc_180007837
0x18000747f  mov     rcx, [rbp+57h+var_20]
0x180007483  xor     rcx, rsp; StackCookie
0x180007486  call    __security_check_cookie
0x18000748b  add     rsp, 0E0h
0x180007492  pop     rbp
0x180007493  retn
0x180007494  test    byte ptr cs:xmmword_180266B60, 10h
0x18000749b  jz      short loc_18000745C
0x18000749d  mov     edx, 0Fh
0x1800074a2  lea     r8, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids
0x1800074a9  mov     ecx, 404h
0x1800074ae  call    WPP_SF_
0x1800074b3  jmp     short loc_18000745C
0x1800074b5  mov     [rsp+0E0h+arg_0], rbx
0x1800074bd  mov     [rsp+0E0h+arg_10], rdi
0x1800074c5  call    ?FindBaseProxyKey@@YAPEAVCRefdKey@@XZ; FindBaseProxyKey(void)
0x1800074ca  mov     rbx, rax
0x1800074cd  test    rax, rax
0x1800074d0  jz      loc_1800075D3
0x1800074d6  cmp     cs:GlobalIsProcessNtService, r15d
0x1800074dd  jnz     loc_1800075D3
0x1800074e3  mov     rdi, cs:g_pszCurrentUser
0x1800074ea  test    byte ptr cs:xmmword_180266B60, 10h
0x1800074f1  jnz     loc_18000764F
0x1800074f7  lea     rax, aDefault; ".Default"
0x1800074fe  mov     [rsp+0E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x180007506  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000750c  mov     [rsp+0E0h+lpString2], rax; lpString2
0x180007511  mov     r8, rdi; lpString1
0x180007514  mov     edx, 1; dwCmpFlags
0x180007519  mov     ecx, 7Fh; Locale
0x18000751e  call    cs:__imp_CompareStringA
0x180007524  cmp     eax, 2
0x180007527  jz      loc_1800076BE
0x18000752d  lea     rax, aSystem; "SYSTEM"
0x180007534  mov     [rsp+0E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000753c  mov     r9d, 0FFFFFFFFh; cchCount1
0x180007542  mov     [rsp+0E0h+lpString2], rax; lpString2
0x180007547  mov     r8, rdi; lpString1
0x18000754a  mov     edx, 1; dwCmpFlags
0x18000754f  mov     ecx, 7Fh; Locale
0x180007554  call    cs:__imp_CompareStringA
0x18000755a  cmp     eax, 2
0x18000755d  jz      loc_1800076BE
0x180007563  mov     rcx, [rbx+8]; hkey
0x180007567  lea     rax, [rbp+57h+pcbData]
0x18000756b  mov     qword ptr [rsp+0E0h+cchCount2], rax; pcbData
0x180007570  lea     r9, [rbp+57h+pdwType]; pdwType
0x180007574  lea     rax, [rbp+57h+pvData]
0x180007578  lea     r8, pszValue; "MigrateProxy"
0x18000757f  mov     [rsp+0E0h+lpString2], rax; pvData
0x180007584  lea     rdx, pszSubKey; "Software\\Microsoft\\windows\\CurrentVe"...
0x18000758b  call    cs:__imp_SHGetValueW
0x180007591  test    eax, eax
0x180007593  jz      short loc_180007614
0x180007595  mov     eax, r15d
0x180007598  mov     [rbp+57h+pvData], eax
0x18000759b  test    byte ptr cs:xmmword_180266B60, 10h
0x1800075a2  jnz     loc_18000766D
0x1800075a8  test    eax, eax
0x1800075aa  jz      loc_18000768E
0x1800075b0  xor     edx, edx; unsigned int *
0x1800075b2  lea     rcx, [rbp+57h+pWinHttpProxySettings]; pWinHttpProxySettings
0x1800075b6  call    ?ReadProxySettings@@YAKPEAUtagProxySettings@@PEAK@Z; ReadProxySettings(tagProxySettings *,ulong *)
0x1800075bb  lea     rcx, [rbp+57h+pWinHttpProxySettings]; pWinHttpProxySettings
0x1800075bf  mov     [rbp+57h+pWinHttpProxySettings.pwszConnectionName], r15
0x1800075c3  call    cs:__imp_WinHttpFreeProxySettings
0x1800075c9  mov     rcx, rbx; struct CRefdKey *
0x1800075cc  call    ?CloseBaseProxyKey@@YAHPEAVCRefdKey@@@Z; CloseBaseProxyKey(CRefdKey *)
0x1800075d1  jmp     short loc_1800075FF
0x1800075d3  test    byte ptr cs:xmmword_180266B60, 10h
0x1800075da  mov     rdi, r15
0x1800075dd  jnz     loc_1800077FE
0x1800075e3  lea     rcx, [rbp+57h+pWinHttpProxySettings]; pWinHttpProxySettings
0x1800075e7  mov     [rbp+57h+pWinHttpProxySettings.pwszConnectionName], r15
0x1800075eb  call    cs:__imp_WinHttpFreeProxySettings
0x1800075f1  test    rdi, rdi
0x1800075f4  jnz     loc_18000782A
0x1800075fa  test    rbx, rbx
0x1800075fd  jnz     short loc_1800075C9
0x1800075ff  mov     rbx, [rsp+0E0h+arg_0]
0x180007607  mov     rdi, [rsp+0E0h+arg_10]
0x18000760f  jmp     loc_18000746A
0x180007614  mov     eax, [rbp+57h+pvData]
0x180007617  jmp     short loc_18000759B
0x180007619  mov     edx, 0Eh
0x18000761e  lea     r8, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids
0x180007625  mov     ecx, 404h
0x18000762a  call    WPP_SF_
0x18000762f  jmp     loc_18000742D
0x180007634  mov     edx, 10h
0x180007639  lea     r8, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids
0x180007640  mov     ecx, 404h
0x180007645  call    WPP_SF_d
0x18000764a  jmp     loc_18000745C
0x18000764f  mov     edx, 12h
0x180007654  lea     r8, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids
0x18000765b  mov     ecx, 404h
0x180007660  mov     r9, rdi
0x180007663  call    WPP_SF_s
0x180007668  jmp     loc_1800074F7
0x18000766d  mov     edx, 13h
0x180007672  lea     r8, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids
0x180007679  mov     ecx, 404h
0x18000767e  mov     r9d, eax
0x180007681  call    WPP_SF_d
0x180007686  mov     eax, [rbp+57h+pvData]
0x180007689  jmp     loc_1800075A8
0x18000768e  call    IsProcessLessThanMediumIL
0x180007693  test    eax, eax
0x180007695  jz      short loc_1800076FA
0x180007697  cmp     qword ptr [rbx+8], 0FFFFFFFF80000002h
0x18000769f  jz      short loc_1800076D9
0x1800076a1  xor     edx, edx; void *
0x1800076a3  mov     [rbp+57h+var_AC], r15d
0x1800076a7  lea     rcx, ?MigrateProxySettingsViaBrokerCallback@@YAJPEAX@Z; int (*)(void *)
0x1800076ae  call    ?WxRunCom@@YAJP6AJPEAX@Z0H@Z; WxRunCom(long (*)(void *),void *,int)
0x1800076b3  test    eax, eax
0x1800076b5  jns     short loc_1800076BE
0x1800076b7  mov     [rbp+57h+var_AC], 2DCh
0x1800076be  lea     rcx, [rbp+57h+pWinHttpProxySettings]; pWinHttpProxySettings
0x1800076c2  mov     [rbp+57h+pWinHttpProxySettings.pwszConnectionName], r15
0x1800076c6  call    cs:__imp_WinHttpFreeProxySettings
0x1800076cc  mov     rcx, rbx; struct CRefdKey *
0x1800076cf  call    ?CloseBaseProxyKey@@YAHPEAVCRefdKey@@@Z; CloseBaseProxyKey(CRefdKey *)
0x1800076d4  jmp     loc_1800075FF
0x1800076d9  test    byte ptr cs:xmmword_180266B60, 10h
0x1800076e0  jz      short loc_1800076BE
0x1800076e2  mov     edx, 14h
0x1800076e7  lea     r8, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids
0x1800076ee  mov     ecx, 404h
0x1800076f3  call    WPP_SF_
0x1800076f8  jmp     short loc_1800076BE
0x1800076fa  mov     [rsp+0E0h+var_8], r14
0x180007702  mov     ecx, 10h; unsigned __int64
0x180007707  mov     r14d, r15d
0x18000770a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000770f  test    rax, rax
0x180007712  jz      short loc_180007730
0x180007714  xorps   xmm0, xmm0
0x180007717  mov     rcx, rax; this
0x18000771a  movups  xmmword ptr [rax], xmm0
0x18000771d  call    ??0RasEnumHelp@@QEAA@XZ; RasEnumHelp::RasEnumHelp(void)
0x180007722  mov     rdi, rax
0x180007725  test    rax, rax
0x180007728  jz      short loc_180007733
0x18000772a  mov     r14d, [rax+4]
0x18000772e  jmp     short loc_180007733
0x180007730  mov     rdi, r15
0x180007733  xor     r8d, r8d; int *
0x180007736  lea     rdx, [rbp+57h+pWinHttpProxySettings]; struct tagProxySettings *
0x18000773a  lea     rcx, [rbp+57h+var_B0]; int *
0x18000773e  call    ?ReadLegacyProxyInfo@@YAHPEAHPEAUtagProxySettings@@0@Z; ReadLegacyProxyInfo(int *,tagProxySettings *,int *)
0x180007743  test    eax, eax
0x180007745  jz      short loc_1800077BB
0x180007747  mov     [rsp+0E0h+arg_8], rsi
0x18000774f  cmp     [rbp+57h+var_B0], r15d
0x180007753  jnz     short loc_180007759
0x180007755  or      [rbp+57h+pWinHttpProxySettings.dwFlags], 8
0x180007759  lea     rcx, [rbp+57h+pWinHttpProxySettings]; pWinHttpProxySettings
0x18000775d  mov     [rbp+57h+pWinHttpProxySettings.pwszConnectionName], r15
0x180007761  call    ?WriteProxySettings@@YAKPEAUtagProxySettings@@H@Z; WriteProxySettings(tagProxySettings *,int)
0x180007766  call    ?EnableAutodiscoverForDialup@@YAHXZ; EnableAutodiscoverForDialup(void)
0x18000776b  test    eax, eax
0x18000776d  jnz     short loc_180007773
0x18000776f  and     [rbp+57h+pWinHttpProxySettings.dwFlags], 0FFFFFFF7h
0x180007773  mov     esi, r15d
0x180007776  test    r14d, r14d
0x180007779  jz      short loc_1800077B3
0x18000777b  mov     r10, r15
0x18000777e  cmp     esi, [rdi+4]
0x180007781  jnb     short loc_18000779F
0x180007783  mov     rdx, [rdi+8]
0x180007787  add     rdx, 4
0x18000778b  mov     eax, esi
0x18000778d  imul    rcx, rax, 418h
0x180007794  add     rdx, rcx; int
0x180007797  cmp     [rdx], r10w
0x18000779b  cmovnz  r10, rdx
0x18000779f  lea     rcx, [rbp+57h+pWinHttpProxySettings]; pWinHttpProxySettings
0x1800077a3  mov     [rbp+57h+pWinHttpProxySettings.pwszConnectionName], r10
0x1800077a7  call    ?WriteProxySettings@@YAKPEAUtagProxySettings@@H@Z; WriteProxySettings(tagProxySettings *,int)
0x1800077ac  inc     esi
0x1800077ae  cmp     esi, r14d
0x1800077b1  jb      short loc_18000777B
0x1800077b3  mov     rsi, [rsp+0E0h+arg_8]
0x1800077bb  mov     [rbp+57h+var_2C], 1
0x1800077c2  lea     rax, [rbp+57h+var_2C]
0x1800077c6  mov     rcx, [rbx+8]; hkey
0x1800077ca  lea     r8, pszValue; "MigrateProxy"
0x1800077d1  mov     [rsp+0E0h+cchCount2], 4; cbData
0x1800077d9  lea     rdx, pszSubKey; "Software\\Microsoft\\windows\\CurrentVe"...
0x1800077e0  mov     r9d, 4; dwType
0x1800077e6  mov     [rsp+0E0h+lpString2], rax; pvData
0x1800077eb  call    cs:__imp_SHSetValueW
0x1800077f1  mov     r14, [rsp+0E0h+var_8]
0x1800077f9  jmp     loc_1800075E3
0x1800077fe  mov     edx, 11h
0x180007803  lea     r8, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids
0x18000780a  mov     ecx, 404h
0x18000780f  mov     r9, rbx
0x180007812  call    WPP_SF_q
0x180007817  lea     rcx, [rbp+57h+pWinHttpProxySettings]; pWinHttpProxySettings
0x18000781b  mov     [rbp+57h+pWinHttpProxySettings.pwszConnectionName], r15
0x18000781f  call    cs:__imp_WinHttpFreeProxySettings
0x180007825  jmp     loc_1800075FA
0x18000782a  mov     rcx, rdi; this
0x18000782d  call    ??_GRasEnumHelp@@QEAAPEAXI@Z; RasEnumHelp::`scalar deleting destructor'(uint)
0x180007832  jmp     loc_1800075FA
0x180007837  mov     edx, 15h
0x18000783c  lea     r8, WPP_1a99b2eb469f39ab69dd1402eafc966c_Traceguids
0x180007843  mov     ecx, 404h
0x180007848  call    WPP_SF_
0x18000784d  jmp     loc_18000747F
```
