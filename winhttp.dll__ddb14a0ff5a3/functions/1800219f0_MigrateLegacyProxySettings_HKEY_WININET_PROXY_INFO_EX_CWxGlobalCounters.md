# MigrateLegacyProxySettings(HKEY__ *,WININET_PROXY_INFO_EX *,CWxGlobalCounters *)

- ea: `0x1800219f0`
- end: `0x180022990`
- name: `?MigrateLegacyProxySettings@@YAJPEAUHKEY__@@PEAUWININET_PROXY_INFO_EX@@PEAVCWxGlobalCounters@@@Z`
- size: `4000`
- prototype: `__int64 __fastcall(HKEY hKey, struct WININET_PROXY_INFO_EX *, struct CWxGlobalCounters *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fd20`

## callees

- `0x180007cb0`
- `0x1800081a0`
- `0x18001b480`
- `0x18001fd20`
- `0x1800219f0`
- `0x180022998`
- `0x180022c20`
- `0x18004b7a8`
- `0x180058f80`
- `0x180076b44`
- `0x18009acbc`
- `0x1800a1d10`
- `0x1800a2624`
- `0x1800a2660`
- `0x1800cf008`
- `0x1800cf124`
- `0x1800db6b0`
- `0x1800db758`
- `0x1800dc68c`
- `0x1800dc7d8`
- `0x1800dce80`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021e19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021e19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021e93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022914`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021de8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021e51`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800221d2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002223f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021de8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021e51`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800221d2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002223f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002203d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002204f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002212a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022138`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022146`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022179`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002233d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800223db`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002250a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002251f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022534`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002296f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002297a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022985`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002203d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002204f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002212a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022138`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022146`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022179`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002233d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800223db`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002250a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002251f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022534`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002296f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002297a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022985`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021cbe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021cbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021c23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021c67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021c23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021c67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800220ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022108`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800220ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022108`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800226df`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800226df`

## pseudocode

```c
__int64 __fastcall MigrateLegacyProxySettings(
        HKEY hKey,
        struct WININET_PROXY_INFO_EX *a2,
        struct CWxGlobalCounters *a3)
{
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  void *v9; // rdi
  void *v10; // rsi
  void *v11; // r15
  LSTATUS v12; // eax
  signed int v13; // r12d
  LSTATUS v14; // eax
  int v15; // eax
  int WinInetProxySettings; // eax
  const CHAR *v17; // r13
  int v18; // eax
  int v19; // ebx
  size_t v20; // r12
  WCHAR *v21; // rax
  WCHAR *v22; // r14
  WCHAR *v23; // rbx
  unsigned int v24; // ebx
  int v25; // r14d
  const CHAR *v26; // rcx
  int v28; // eax
  __int64 v29; // rcx
  WCHAR *v30; // r14
  WCHAR *Heap; // rax
  __int64 v32; // rdx
  signed int v33; // eax
  struct WININET_PROXY_INFO_EX *v34; // r13
  int v35; // r8d
  int v36; // ebx
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  __int64 v40; // rax
  int PersistedStateLocation; // eax
  int v42; // edx
  int v43; // ecx
  int v44; // r8d
  int v45; // r14d
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  signed int LastError; // eax
  WCHAR *phkResult; // [rsp+20h] [rbp-E0h]
  int cchWideChar; // [rsp+50h] [rbp-B0h]
  WCHAR *v53; // [rsp+58h] [rbp-A8h]
  WCHAR *v54; // [rsp+60h] [rbp-A0h] BYREF
  void *v55; // [rsp+68h] [rbp-98h]
  void *v56; // [rsp+70h] [rbp-90h]
  void *v57; // [rsp+78h] [rbp-88h]
  size_t v58; // [rsp+80h] [rbp-80h]
  _OWORD v59[7]; // [rsp+90h] [rbp-70h] BYREF
  struct WININET_PROXY_INFO_EX *v60; // [rsp+100h] [rbp+0h]
  struct CWxGlobalCounters *v61; // [rsp+108h] [rbp+8h]
  _OWORD v62[7]; // [rsp+110h] [rbp+10h] BYREF
  int v63; // [rsp+180h] [rbp+80h]
  HKEY hKeya; // [rsp+188h] [rbp+88h] BYREF
  HKEY v65; // [rsp+190h] [rbp+90h] BYREF
  __int128 v66; // [rsp+1A0h] [rbp+A0h] BYREF
  LPCCH lpMultiByteStr[2]; // [rsp+1B0h] [rbp+B0h]
  HGLOBAL hMem[2]; // [rsp+1C0h] [rbp+C0h]
  HGLOBAL v69[2]; // [rsp+1D0h] [rbp+D0h]
  HGLOBAL v70[2]; // [rsp+1E0h] [rbp+E0h]
  HGLOBAL v71[2]; // [rsp+1F0h] [rbp+F0h]
  HGLOBAL v72[2]; // [rsp+200h] [rbp+100h]
  __int128 v73; // [rsp+210h] [rbp+110h] BYREF
  wchar_t *String1[2]; // [rsp+220h] [rbp+120h]
  LPCWCH lpWideCharStr[2]; // [rsp+230h] [rbp+130h]
  __int128 v76; // [rsp+240h] [rbp+140h]
  __int128 v77; // [rsp+250h] [rbp+150h]
  __int128 v78; // [rsp+260h] [rbp+160h]
  __int128 v79; // [rsp+270h] [rbp+170h]
  DWORD cbData; // [rsp+280h] [rbp+180h] BYREF
  BYTE Data[4]; // [rsp+284h] [rbp+184h] BYREF
  int v82; // [rsp+288h] [rbp+188h] BYREF
  __int128 v83; // [rsp+290h] [rbp+190h] BYREF
  wchar_t *String2[2]; // [rsp+2A0h] [rbp+1A0h]
  wchar_t *v85[2]; // [rsp+2B0h] [rbp+1B0h]
  __int128 v86; // [rsp+2C0h] [rbp+1C0h]
  __int128 v87; // [rsp+2D0h] [rbp+1D0h]
  __int128 v88; // [rsp+2E0h] [rbp+1E0h]
  __int128 v89; // [rsp+2F0h] [rbp+1F0h]
  WCHAR SubKey[61]; // [rsp+300h] [rbp+200h] BYREF
  char v91[406]; // [rsp+37Ah] [rbp+27Ah] BYREF

  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internetttings\\");
  v61 = a3;
  v60 = a2;
  hKeya = 0;
  v65 = 0;
  memset_0(v91, 0, 0x18Eu);
  *(_DWORD *)Data = 0;
  cbData = 0;
  v66 = 0;
  v82 = 0;
  v9 = 0;
  *(_OWORD *)lpMultiByteStr = 0;
  v55 = 0;
  v10 = 0;
  *(_OWORD *)hMem = 0;
  v56 = 0;
  v11 = 0;
  *(_OWORD *)v69 = 0;
  v57 = 0;
  *(_OWORD *)v70 = 0;
  *(_OWORD *)v71 = 0;
  *(_OWORD *)v72 = 0;
  v73 = 0;
  *(_OWORD *)String1 = 0;
  *(_OWORD *)lpWideCharStr = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v83 = 0;
  *(_OWORD *)String2 = 0;
  *(_OWORD *)v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  memset(v62, 0, sizeof(v62));
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qqq(
      1029,
      41,
      (unsigned int)WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids,
      (_DWORD)hKey,
      (__int64)a2,
      (__int64)a3);
  if ( !hKey )
  {
    v13 = -2147024809;
    goto LABEL_50;
  }
  if ( !a2 )
  {
    v13 = -2147024809;
    goto LABEL_50;
  }
  LODWORD(v66) = 112;
  LODWORD(v73) = 112;
  LODWORD(v83) = 112;
  LODWORD(v62[0]) = 112;
  if ( hKey != HKEY_LOCAL_MACHINE )
    goto LABEL_11;
  v13 = 0;
  v63 = 0;
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_SSSqd(
      v7,
      v6,
      v8,
      (unsigned int)L"InternetSettings",
      (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
      0,
      (__int64)SubKey);
  phkResult = SubKey;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"InternetSettings",
                             0,
                             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
                             0);
  v45 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
      WPP_SF_SSSd(
        v43,
        v42,
        v44,
        (unsigned int)L"InternetSettings",
        (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
        0,
        PersistedStateLocation);
    v13 = HRESULT_FROM_NTSTATUS(v45);
  }
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v13, phkResult);
  if ( v13 >= 0 )
  {
LABEL_11:
    v12 = RegOpenKeyExW(hKey, SubKey, 0, 0x2001Fu, &hKeya);
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v13 >= 0 )
    {
      v14 = RegOpenKeyExW(hKeya, L"Connections", 0, 0x2001Fu, &v65);
      v13 = v14;
      if ( v14 > 0 )
        v13 = (unsigned __int16)v14 | 0x80070000;
      if ( v13 >= 0 )
      {
        cbData = 4;
        RegQueryValueExW(hKeya, L"MigrateProxy", 0, 0, Data, &cbData);
        if ( !*(_DWORD *)Data )
        {
          if ( (xmmword_180107A60 & 0x20) == 0 )
            goto LABEL_50;
          v32 = 42;
          goto LABEL_100;
        }
        v13 = ReadLegacyProxyInfo(hKeya, &v82, (struct tagProxySettings *)&v73);
        if ( v13 >= 0 )
        {
          v15 = 6;
          if ( v82 )
            v15 = 14;
          v63 = v15;
          lpMultiByteStr[0] = "SavedLegacySettings";
          WinInetProxySettings = ReadWinInetProxySettings(
                                   v65,
                                   0,
                                   0,
                                   0,
                                   0,
                                   0,
                                   0,
                                   0,
                                   (struct WININET_PROXY_INFO_EX *)&v66);
          v13 = WinInetProxySettings;
          if ( WinInetProxySettings > 0 )
            v13 = (unsigned __int16)WinInetProxySettings | 0x80070000;
          if ( v13 >= 0 )
          {
            memset((char *)v59 + 8, 0, 104);
            if ( (xmmword_180107A60 & 0x20) != 0 )
              WPP_SF_qq(
                1029,
                39,
                (unsigned int)WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids,
                (unsigned int)&v66,
                (__int64)&v83);
            v13 = 0;
            v17 = lpMultiByteStr[0];
            LODWORD(v59[0]) = 112;
            DWORD1(v59[0]) = DWORD1(v66);
            if ( !lpMultiByteStr[0] )
            {
LABEL_32:
              if ( !lpMultiByteStr[1] || (v13 = WxNewStringAtoWCch<WxHeapAllocator>(lpMultiByteStr[1], -1), v13 >= 0) )
              {
                if ( !hMem[0] || (v13 = WxNewStringAtoWCch<WxHeapAllocator>((LPCCH)hMem[0], -1), v13 >= 0) )
                {
                  if ( !hMem[1] || (v13 = WxNewStringAtoWCch<WxHeapAllocator>((LPCCH)hMem[1], -1), v13 >= 0) )
                  {
                    v83 = v59[0];
                    *(_OWORD *)String2 = v59[1];
                    *(_OWORD *)v85 = v59[2];
                    v86 = v59[3];
                    v87 = v59[4];
                    v88 = v59[5];
                    v89 = v59[6];
                    memset(v59, 0, sizeof(v59));
                  }
                }
              }
LABEL_36:
              FreeProxySettingsWithAllocator<WxHeapAllocator>(v59);
              if ( (xmmword_180107A60 & 0x20) != 0 )
                WPP_SF_d(1029, 40, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, (unsigned int)v13, phkResult);
              if ( v13 < 0 )
                goto LABEL_50;
              v24 = 0;
              v25 = v63;
              if ( (xmmword_180107A60 & 0x20) != 0 )
                WPP_SF_qqD(
                  1029,
                  37,
                  (unsigned int)WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids,
                  (unsigned int)&v73,
                  (__int64)&v83);
              LODWORD(v26) = v25 & DWORD1(v83);
              if ( (v25 & DWORD1(v73)) != (v25 & DWORD1(v83)) )
                goto LABEL_46;
              if ( (BYTE4(v83) & 4) == 0 )
                goto LABEL_43;
              LODWORD(v26) = lpWideCharStr[1];
              if ( lpWideCharStr[1] )
              {
                if ( !v85[1] || wcsicmp(lpWideCharStr[1], v85[1]) )
                  goto LABEL_46;
              }
              else if ( v85[1] )
              {
LABEL_46:
                if ( (xmmword_180107A60 & 0x20) != 0 )
                  WPP_SF_d(1029, 38, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, v24, phkResult);
                if ( v24 )
                {
                  if ( (xmmword_180107A60 & 0x20) == 0 )
                    goto LABEL_50;
                  v32 = 43;
LABEL_100:
                  WPP_SF_(1029, v32, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
                  goto LABEL_50;
                }
                if ( (xmmword_180107A60 & 0x20) != 0 )
                  WPP_SF_(1029, 44, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
                v34 = v60;
                DWORD2(v73) = *((_DWORD *)v60 + 2);
                DWORD1(v73) |= *((_DWORD *)v60 + 1) & ~v25;
                if ( lpWideCharStr[1]
                  || (v26 = (const CHAR *)*((_QWORD *)v60 + 5)) == 0
                  || (v13 = WxNewStringAtoWCch<WxGlobalAllocator>(v26), v13 >= 0) )
                {
                  v35 = (int)v61;
                  if ( !v61 )
                    goto LABEL_119;
                  v46 = WriteWinInetProxySettings((struct tagProxySettings *)&v73, (unsigned __int16 *)1, v61);
                  v13 = v46;
                  if ( v46 > 0 )
                    v13 = (unsigned __int16)v46 | 0x80070000;
                  if ( v13 >= 0 )
                  {
LABEL_119:
                    if ( (xmmword_180107A60 & 0x20) != 0 )
                      WPP_SF_Dsss(
                        (_DWORD)v26,
                        45,
                        v35,
                        *((_DWORD *)v34 + 1),
                        *((_QWORD *)v34 + 3),
                        *((_QWORD *)v34 + 4),
                        *((_QWORD *)v34 + 5));
                    if ( !String1[1]
                      || (v47 = WxNewStringWtoACchCp<WxGlobalAllocator>(String1[1]), v9 = v55, v13 = v47, v47 >= 0) )
                    {
                      if ( !lpWideCharStr[0]
                        || (v48 = WxNewStringWtoACchCp<WxGlobalAllocator>(lpWideCharStr[0]),
                            v10 = v56,
                            v13 = v48,
                            v48 >= 0) )
                      {
                        if ( !lpWideCharStr[1]
                          || (v49 = WxNewStringWtoACchCp<WxGlobalAllocator>(lpWideCharStr[1]),
                              v11 = v57,
                              v13 = v49,
                              v49 >= 0) )
                        {
                          v36 = *((_DWORD *)v34 + 1) & ~v25;
                          v37 = (void *)*((_QWORD *)v34 + 3);
                          *((_DWORD *)v34 + 2) = DWORD2(v73);
                          *((_DWORD *)v34 + 1) = v25 & DWORD1(v73) | v36;
                          if ( v37 )
                            GlobalFree(v37);
                          v38 = (void *)*((_QWORD *)v34 + 4);
                          *((_QWORD *)v34 + 3) = v9;
                          v9 = 0;
                          if ( v38 )
                            GlobalFree(v38);
                          v39 = (void *)*((_QWORD *)v34 + 5);
                          *((_QWORD *)v34 + 4) = v10;
                          v10 = 0;
                          if ( v39 )
                            GlobalFree(v39);
                          v40 = (__int64)v11;
                          v11 = 0;
                          *((_QWORD *)v34 + 5) = v40;
                          if ( (xmmword_180107A60 & 0x20) != 0 )
                            WPP_SF_Dsss(
                              (_DWORD)v39,
                              46,
                              v35,
                              *((_DWORD *)v34 + 1),
                              *((_QWORD *)v34 + 3),
                              *((_QWORD *)v34 + 4),
                              v40);
                        }
                      }
                    }
                  }
                }
                goto LABEL_50;
              }
LABEL_43:
              LODWORD(v26) = String1[1];
              if ( !String1[1] && !String2[1] || (v24 = 0, String1[1]) && String2[1] && !wcsicmp(String1[1], String2[1]) )
              {
                if ( (LODWORD(v26) = lpWideCharStr[0], !lpWideCharStr[0]) && !v85[0]
                  || (v24 = 0, lpWideCharStr[0]) && v85[0] && !wcsicmp(lpWideCharStr[0], v85[0]) )
                {
                  v24 = 1;
                }
              }
              goto LABEL_46;
            }
            *(_QWORD *)&v59[1] = 0;
            v18 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr[0], -1, 0, 0);
            v19 = v18;
            if ( v18 )
            {
              v20 = (unsigned int)(2 * v18);
              HIDWORD(v54) = 0;
              if ( g_fWxHeapExtensionInitialized )
                v21 = (WCHAR *)((__int64 (__fastcall *)(size_t))qword_180107D38)(v20);
              else
                v21 = (WCHAR *)HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v20);
              v22 = v21;
              if ( !v21 )
              {
                v13 = -2147024882;
                HIDWORD(v54) = 76;
LABEL_81:
                v28 = MultiByteToWideChar(0, 0, v17, -1, 0, 0);
                cchWideChar = v28;
                if ( v28 )
                {
                  v30 = 0;
                  v58 = (unsigned int)(2 * v28);
                  v54 = 0;
                  Heap = (WCHAR *)WxAllocateHeapEx(v29, (unsigned int)v58);
                  v53 = Heap;
                  if ( Heap )
                  {
                    memset_0(Heap, 0, v58);
                    v30 = v53;
                    v54 = v53;
                    if ( MultiByteToWideChar(0, 0, v17, -1, v53, cchWideChar) )
                    {
                      v23 = v53;
                      v13 = 0;
                      goto LABEL_30;
                    }
                    LastError = GetLastError();
                    v13 = LastError;
                    if ( LastError > 0 )
                      v13 = (unsigned __int16)LastError | 0x80070000;
                    if ( v13 >= 0 )
                      v13 = -2147418113;
                  }
                  else
                  {
                    HIDWORD(v58) = 76;
                  }
                  if ( v30 )
                    WxFreeHeapEx(&v54);
                }
                else
                {
                  v33 = GetLastError();
                  v13 = v33;
                  if ( v33 > 0 )
                    v13 = (unsigned __int16)v33 | 0x80070000;
                  if ( v13 >= 0 )
                    v13 = -2147418113;
                }
LABEL_31:
                if ( v13 < 0 )
                  goto LABEL_36;
                goto LABEL_32;
              }
              memset_0(v21, 0, v20);
              if ( MultiByteToWideChar(0xFDE9u, 0, v17, -1, v22, v19) )
              {
                v23 = v22;
                v13 = 0;
LABEL_30:
                *(_QWORD *)&v59[1] = v23;
                goto LABEL_31;
              }
              GetLastError();
              if ( g_fWxHeapExtensionInitialized )
                g_WxHeapExtensionInterfaces(v22);
              else
                HeapFree(g_hWxProcessHeap, 0, v22);
            }
            else
            {
              GetLastError();
            }
            v13 = -2147024882;
            goto LABEL_81;
          }
        }
      }
    }
  }
LABEL_50:
  lpMultiByteStr[0] = 0;
  FreeProxySettingsWithAllocator<WxHeapAllocator>(&v73);
  FreeProxySettingsWithAllocator<WxHeapAllocator>(&v83);
  FreeProxySettingsWithAllocator<WxHeapAllocator>(v62);
  if ( lpMultiByteStr[0] )
    GlobalFree((HGLOBAL)lpMultiByteStr[0]);
  if ( lpMultiByteStr[1] )
    GlobalFree((HGLOBAL)lpMultiByteStr[1]);
  if ( hMem[0] )
    GlobalFree(hMem[0]);
  if ( hMem[1] )
    GlobalFree(hMem[1]);
  if ( v69[0] )
    GlobalFree(v69[0]);
  if ( v70[0] )
    GlobalFree(v70[0]);
  if ( v71[1] )
    GlobalFree(v71[1]);
  if ( v72[1] )
    GlobalFree(v72[1]);
  v66 = 0;
  DWORD1(v66) = 1;
  *(_OWORD *)lpMultiByteStr = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v69 = 0;
  *(_OWORD *)v70 = 0;
  *(_OWORD *)v71 = 0;
  *(_OWORD *)v72 = 0;
  if ( v65 )
  {
    RegCloseKey(v65);
    v65 = 0;
  }
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 47, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, (unsigned int)v13, phkResult);
  if ( v11 )
    GlobalFree(v11);
  if ( v10 )
    GlobalFree(v10);
  if ( v9 )
    GlobalFree(v9);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800219f0  mov     [rsp-8+arg_18], rbx
0x1800219f5  push    rbp
0x1800219f6  push    rsi
0x1800219f7  push    rdi
0x1800219f8  push    r12
0x1800219fa  push    r13
0x1800219fc  push    r14
0x1800219fe  push    r15
0x180021a00  lea     rbp, [rsp-420h]
0x180021a08  sub     rsp, 520h
0x180021a0f  mov     rax, cs:__security_cookie
0x180021a16  xor     rax, rsp
0x180021a19  mov     [rbp+450h+var_40], rax
0x180021a20  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\Windows\\CurrentVersion\\I"...
0x180021a27  xor     r13d, r13d
0x180021a2a  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180021a31  mov     r12, r8
0x180021a34  movaps  [rbp+450h+var_240], xmm1
0x180021a3b  mov     r14, rdx
0x180021a3e  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "ws\\CurrentVersion\\Internet Settings\\"
0x180021a45  mov     rbx, rcx
0x180021a48  movaps  xmmword ptr [rbp+450h+SubKey], xmm0
0x180021a4f  lea     rcx, [rbp+450h+var_1D6]; void *
0x180021a56  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\Windows\\CurrentVersion\\Internet S"...
0x180021a5d  movaps  [rbp+450h+var_220], xmm1
0x180021a64  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+50h; "n\\Internet Settings\\"
0x180021a6b  movaps  [rbp+450h+var_230], xmm0
0x180021a72  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "ntVersion\\Internet Settings\\"
0x180021a79  movaps  [rbp+450h+var_200], xmm1
0x180021a80  movups  xmm1, xmmword ptr cs:aSoftwareMicros+6Ah; "ttings\\"
0x180021a87  mov     [rbp+450h+var_448], r8
0x180021a8b  mov     r8d, 18Eh; Size
0x180021a91  movaps  [rbp+450h+var_210], xmm0
0x180021a98  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+60h; "et Settings\\"
0x180021a9f  mov     [rbp+450h+var_450], rdx
0x180021aa3  xor     edx, edx; Val
0x180021aa5  movaps  [rbp+450h+var_1F0], xmm0
0x180021aac  movups  [rbp+450h+var_1F0+0Ah], xmm1
0x180021ab3  mov     [rsp+550h+var_4FC], r13d
0x180021ab8  mov     [rbp+450h+hKey], r13
0x180021abf  mov     [rbp+450h+var_3C0], r13
0x180021ac6  call    memset_0
0x180021acb  xorps   xmm0, xmm0
0x180021ace  mov     dword ptr [rbp+450h+Data], r13d
0x180021ad5  xorps   xmm1, xmm1
0x180021ad8  mov     [rbp+450h+cbData], r13d
0x180021adf  movups  [rbp+450h+var_3B0], xmm0
0x180021ae6  mov     [rbp+450h+var_2C8], r13d
0x180021aed  mov     edi, r13d
0x180021af0  movups  xmmword ptr [rbp+450h+lpMultiByteStr], xmm0
0x180021af7  mov     [rsp+550h+var_4E8], r13
0x180021afc  mov     esi, r13d
0x180021aff  movups  xmmword ptr [rbp+450h+hMem], xmm0
0x180021b06  mov     [rsp+550h+var_4E0], r13
0x180021b0b  mov     r15d, r13d
0x180021b0e  movups  xmmword ptr [rbp+450h+var_380], xmm0
0x180021b15  mov     [rsp+550h+var_4D8], r13
0x180021b1a  movups  xmmword ptr [rbp+450h+var_370], xmm0
0x180021b21  movups  xmmword ptr [rbp+450h+var_360], xmm0
0x180021b28  movups  xmmword ptr [rbp+450h+var_350], xmm0
0x180021b2f  movups  [rbp+450h+var_340], xmm1
0x180021b36  movups  xmmword ptr [rbp+450h+String1], xmm1
0x180021b3d  movups  xmmword ptr [rbp+450h+lpWideCharStr], xmm1
0x180021b44  movups  [rbp+450h+var_310], xmm1
0x180021b4b  movups  [rbp+450h+var_300], xmm1
0x180021b52  movups  [rbp+450h+var_2F0], xmm1
0x180021b59  movups  [rbp+450h+var_2E0], xmm1
0x180021b60  movups  [rbp+450h+var_2C0], xmm0
0x180021b67  movups  xmmword ptr [rbp+450h+String2], xmm0
0x180021b6e  movups  xmmword ptr [rbp+450h+var_2A0], xmm0
0x180021b75  movups  [rbp+450h+var_290], xmm0
0x180021b7c  movups  [rbp+450h+var_280], xmm0
0x180021b83  movups  [rbp+450h+var_270], xmm0
0x180021b8a  movups  [rbp+450h+var_260], xmm0
0x180021b91  movups  [rbp+450h+var_440], xmm1
0x180021b95  movups  [rbp+450h+var_430], xmm1
0x180021b99  movups  [rbp+450h+var_420], xmm1
0x180021b9d  movups  [rbp+450h+var_410], xmm1
0x180021ba1  movups  [rbp+450h+var_400], xmm1
0x180021ba5  movups  [rbp+450h+var_3F0], xmm1
0x180021ba9  movups  [rbp+450h+var_3E0], xmm1
0x180021bad  test    byte ptr cs:xmmword_180107A60, 20h
0x180021bb4  jnz     loc_1800225F3
0x180021bba  test    rbx, rbx
0x180021bbd  jz      loc_180022265
0x180021bc3  test    r14, r14
0x180021bc6  jz      loc_180022767
0x180021bcc  mov     dword ptr [rbp+450h+var_3B0], 70h ; 'p'
0x180021bd6  mov     r14d, 0Eh
0x180021bdc  mov     dword ptr [rbp+450h+var_340], 70h ; 'p'
0x180021be6  mov     dword ptr [rbp+450h+var_2C0], 70h ; 'p'
0x180021bf0  mov     dword ptr [rbp+450h+var_440], 70h ; 'p'
0x180021bf7  cmp     rbx, 0FFFFFFFF80000002h
0x180021bfe  jz      loc_180022692
0x180021c04  lea     rax, [rbp+450h+hKey]
0x180021c0b  mov     r9d, 2001Fh; samDesired
0x180021c11  xor     r8d, r8d; ulOptions
0x180021c14  mov     [rsp+550h+phkResult], rax; phkResult
0x180021c19  lea     rdx, [rbp+450h+SubKey]; lpSubKey
0x180021c20  mov     rcx, rbx; hKey
0x180021c23  call    cs:__imp_RegOpenKeyExW
0x180021c29  mov     r12d, eax
0x180021c2c  test    eax, eax
0x180021c2e  jle     short loc_180021C3B
0x180021c30  movzx   r12d, ax
0x180021c34  or      r12d, 80070000h
0x180021c3b  test    r12d, r12d
0x180021c3e  js      loc_180022308
0x180021c44  mov     rcx, [rbp+450h+hKey]; hKey
0x180021c4b  lea     rax, [rbp+450h+var_3C0]
0x180021c52  mov     r9d, 2001Fh; samDesired
0x180021c58  mov     [rsp+550h+phkResult], rax; phkResult
0x180021c5d  xor     r8d, r8d; ulOptions
0x180021c60  lea     rdx, aConnections; "Connections"
0x180021c67  call    cs:__imp_RegOpenKeyExW
0x180021c6d  mov     r12d, eax
0x180021c70  test    eax, eax
0x180021c72  jle     short loc_180021C7F
0x180021c74  movzx   r12d, ax
0x180021c78  or      r12d, 80070000h
0x180021c7f  test    r12d, r12d
0x180021c82  js      loc_180022719
0x180021c88  mov     rcx, [rbp+450h+hKey]; hKey
0x180021c8f  lea     rax, [rbp+450h+cbData]
0x180021c96  mov     [rsp+550h+lpcbData], rax; lpcbData
0x180021c9b  lea     rdx, aMigrateproxy; "MigrateProxy"
0x180021ca2  lea     rax, [rbp+450h+Data]
0x180021ca9  mov     [rbp+450h+cbData], 4
0x180021cb3  xor     r9d, r9d; lpType
0x180021cb6  mov     [rsp+550h+phkResult], rax; lpData
0x180021cbb  xor     r8d, r8d; lpReserved
0x180021cbe  call    cs:__imp_RegQueryValueExW
0x180021cc4  cmp     dword ptr [rbp+450h+Data], esi
0x180021cca  jz      loc_180022315
0x180021cd0  mov     rcx, [rbp+450h+hKey]; hKey
0x180021cd7  lea     r8, [rbp+450h+var_340]; struct tagProxySettings *
0x180021cde  lea     rdx, [rbp+450h+var_2C8]; int *
0x180021ce5  call    ?ReadLegacyProxyInfo@@YAJPEAUHKEY__@@PEAHPEAUtagProxySettings@@@Z; ReadLegacyProxyInfo(HKEY__ *,int *,tagProxySettings *)
0x180021cea  mov     r12d, eax
0x180021ced  test    eax, eax
0x180021cef  js      loc_180022258
0x180021cf5  cmp     [rbp+450h+var_2C8], esi
0x180021cfb  mov     eax, 6
0x180021d00  mov     rcx, [rbp+450h+var_3C0]; HKEY
0x180021d07  cmovnz  eax, r14d
0x180021d0b  xor     r9d, r9d; int
0x180021d0e  mov     [rbp+450h+var_3D0], eax
0x180021d14  xor     r8d, r8d; int *
0x180021d17  lea     rax, aSavedlegacyset; "SavedLegacySettings"
0x180021d1e  xor     edx, edx; struct _FILETIME *
0x180021d20  mov     [rbp+450h+lpMultiByteStr], rax
0x180021d27  lea     rax, [rbp+450h+var_3B0]
0x180021d2e  mov     [rsp+550h+var_510], rax; struct WININET_PROXY_INFO_EX *
0x180021d33  mov     [rsp+550h+var_518], r13; int *
0x180021d38  mov     [rsp+550h+var_520], r13; unsigned int *
0x180021d3d  mov     [rsp+550h+lpcbData], r13; struct CWxGlobalCounters *
0x180021d42  mov     dword ptr [rsp+550h+phkResult], r13d; int
0x180021d47  call    ?ReadWinInetProxySettings@@YAKPEAUHKEY__@@PEAU_FILETIME@@PEAHHHPEAVCWxGlobalCounters@@PEAK2PEAUWININET_PROXY_INFO_EX@@@Z; ReadWinInetProxySettings(HKEY__ *,_FILETIME *,int *,int,int,CWxGlobalCounters *,ulong *,int *,WININET_PROXY_INFO_EX *)
0x180021d4c  mov     r12d, eax
0x180021d4f  test    eax, eax
0x180021d51  jle     short loc_180021D5E
0x180021d53  movzx   r12d, ax
0x180021d57  or      r12d, 80070000h
0x180021d5e  test    r12d, r12d
0x180021d61  js      loc_180022726
0x180021d67  xorps   xmm0, xmm0
0x180021d6a  mov     [rsp+550h+var_4FC], r13d
0x180021d6f  xor     eax, eax
0x180021d71  movups  [rbp+450h+var_4C0+8], xmm0
0x180021d75  mov     [rbp+450h+var_458], rax
0x180021d79  movups  [rbp+450h+var_4A8], xmm0
0x180021d7d  movups  [rbp+450h+var_498], xmm0
0x180021d81  movups  [rbp+450h+var_488], xmm0
0x180021d85  movups  [rbp+450h+var_478], xmm0
0x180021d89  movups  [rbp+450h+var_468], xmm0
0x180021d8d  test    byte ptr cs:xmmword_180107A60, 20h
0x180021d94  jnz     loc_18002262F
0x180021d9a  mov     eax, dword ptr [rbp+450h+var_3B0+4]
0x180021da0  mov     r12d, r13d
0x180021da3  mov     r13, [rbp+450h+lpMultiByteStr]
0x180021daa  mov     dword ptr [rbp+450h+var_4C0], 70h ; 'p'
0x180021db1  mov     dword ptr [rbp+450h+var_4C0+4], eax
0x180021db4  test    r13, r13
0x180021db7  jz      loc_180021EAF
0x180021dbd  xor     r14d, r14d
0x180021dc0  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180021dc6  mov     [rsp+550h+var_4FC], r14d
0x180021dcb  mov     r8, r13; lpMultiByteStr
0x180021dce  mov     dword ptr [rsp+550h+lpcbData], r14d; cchWideChar
0x180021dd3  xor     edx, edx; dwFlags
0x180021dd5  mov     ecx, 0FDE9h; CodePage
0x180021dda  mov     [rsp+550h+var_4FC], r14d
0x180021ddf  mov     [rsp+550h+phkResult], r14; lpWideCharStr
0x180021de4  mov     [rbp-60h], r14
0x180021de8  call    cs:__imp_MultiByteToWideChar
0x180021dee  mov     ebx, eax
0x180021df0  test    eax, eax
0x180021df2  jz      loc_180022184
0x180021df8  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, esi; int g_fWxHeapExtensionInitialized
0x180021dfe  lea     r12d, [rax+rax]
0x180021e02  mov     [rsp+550h+var_4EC], r14d
0x180021e07  jnz     loc_180022884
0x180021e0d  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180021e14  mov     r8d, r12d; dwBytes
0x180021e17  xor     edx, edx; dwFlags
0x180021e19  call    cs:__imp_HeapAlloc
0x180021e1f  mov     r14, rax
0x180021e22  test    rax, rax
0x180021e25  jz      loc_180022935
0x180021e2b  mov     r8, r12; Size
0x180021e2e  xor     edx, edx; Val
0x180021e30  mov     rcx, rax; void *
0x180021e33  call    memset_0
0x180021e38  mov     dword ptr [rsp+550h+lpcbData], ebx; cchWideChar
0x180021e3c  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180021e42  mov     r8, r13; lpMultiByteStr
0x180021e45  mov     [rsp+550h+phkResult], r14; lpWideCharStr
0x180021e4a  xor     edx, edx; dwFlags
0x180021e4c  mov     ecx, 0FDE9h; CodePage
0x180021e51  call    cs:__imp_MultiByteToWideChar
0x180021e57  test    eax, eax
0x180021e59  jz      loc_1800228F1
0x180021e5f  mov     rbx, r14
0x180021e62  xor     r12d, r12d
0x180021e65  jmp     short loc_180021EA2
0x180021e67  test    r12d, r12d
0x180021e6a  mov     [rsp+550h+var_4FC], 0D1h
0x180021e72  mov     eax, 8000FFFFh
0x180021e77  cmovns  r12d, eax
0x180021e7b  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, ebx; int g_fWxHeapExtensionInitialized
0x180021e81  jnz     loc_18002261B
0x180021e87  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180021e8e  mov     r8, r14; lpMem
0x180021e91  xor     edx, edx; dwFlags
0x180021e93  call    cs:__imp_HeapFree
0x180021e99  test    r12d, r12d
0x180021e9c  js      loc_18002229E
0x180021ea2  mov     [rbp-60h], rbx
0x180021ea6  test    r12d, r12d
0x180021ea9  js      loc_18002265D
0x180021eaf  mov     rcx, [rbp+450h+lpMultiByteStr+8]; lpMultiByteStr
0x180021eb6  test    rcx, rcx
0x180021eb9  jnz     loc_1800223B5
0x180021ebf  mov     rcx, [rbp+450h+hMem]; lpMultiByteStr
0x180021ec6  test    rcx, rcx
0x180021ec9  jnz     loc_180022278
0x180021ecf  mov     rcx, [rbp+450h+hMem+8]; lpMultiByteStr
0x180021ed6  test    rcx, rcx
0x180021ed9  jnz     loc_180022404
0x180021edf  movaps  xmm0, [rbp+450h+var_4C0]
0x180021ee3  movaps  xmm1, xmmword ptr [rbp-60h]
0x180021ee7  movaps  [rbp+450h+var_2C0], xmm0
0x180021eee  movaps  xmm0, [rbp+450h+var_4A8+8]
0x180021ef2  movaps  xmmword ptr [rbp+450h+String2], xmm1
0x180021ef9  movaps  xmm1, [rbp+450h+var_498+8]
0x180021efd  movaps  xmmword ptr [rbp+450h+var_2A0], xmm0
0x180021f04  movaps  xmm0, [rbp+450h+var_488+8]
0x180021f08  movaps  [rbp+450h+var_290], xmm1
0x180021f0f  movaps  xmm1, [rbp+450h+var_478+8]
0x180021f13  movaps  [rbp+450h+var_280], xmm0
0x180021f1a  movaps  xmm0, [rbp+450h+var_468+8]
0x180021f1e  movaps  [rbp+450h+var_270], xmm1
0x180021f25  xorps   xmm1, xmm1
0x180021f28  movaps  [rbp+450h+var_260], xmm0
0x180021f2f  movups  [rbp+450h+var_4C0], xmm1
0x180021f33  movups  xmmword ptr [rbp-60h], xmm1
0x180021f37  movups  [rbp+450h+var_4A8+8], xmm1
0x180021f3b  movups  [rbp+450h+var_498+8], xmm1
0x180021f3f  movups  [rbp+450h+var_488+8], xmm1
0x180021f43  movups  [rbp+450h+var_478+8], xmm1
0x180021f47  movups  [rbp+450h+var_468+8], xmm1
0x180021f4b  lea     rcx, [rbp+450h+var_4C0]
0x180021f4f  call    ??$FreeProxySettingsWithAllocator@VWxHeapAllocator@@@@YAXPEAUtagProxySettings@@@Z; FreeProxySettingsWithAllocator<WxHeapAllocator>(tagProxySettings *)
0x180021f54  test    byte ptr cs:xmmword_180107A60, 20h
0x180021f5b  jnz     loc_1800223E6
0x180021f61  xor     r13d, r13d
0x180021f64  test    r12d, r12d
0x180021f67  js      loc_18002277A
0x180021f6d  mov     [rsp+550h+var_4F4], r13d
0x180021f72  mov     ebx, r13d
0x180021f75  test    byte ptr cs:xmmword_180107A60, 20h
0x180021f7c  mov     r14d, [rbp+450h+var_3D0]
0x180021f83  jnz     loc_1800225C0
0x180021f89  mov     edx, dword ptr [rbp+450h+var_2C0+4]
0x180021f8f  mov     ecx, edx
0x180021f91  mov     eax, dword ptr [rbp+450h+var_340+4]
0x180021f97  and     ecx, r14d
0x180021f9a  and     eax, r14d
0x180021f9d  cmp     eax, ecx
0x180021f9f  jnz     short loc_180021FD7
0x180021fa1  test    dl, 4
0x180021fa4  jnz     loc_18002257B
0x180021faa  mov     rcx, [rbp+450h+String1+8]; String1
0x180021fb1  mov     rdx, [rbp+450h+String2+8]; String2
0x180021fb8  mov     [rsp+550h+var_4F4], r13d
0x180021fbd  test    rcx, rcx
0x180021fc0  jnz     short loc_180021FCB
0x180021fc2  test    rdx, rdx
0x180021fc5  jz      loc_1800222BF
0x180021fcb  mov     ebx, r13d
  ... truncated ...
```
