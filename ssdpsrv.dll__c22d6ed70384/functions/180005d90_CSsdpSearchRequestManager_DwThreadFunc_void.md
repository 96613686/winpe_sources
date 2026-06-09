# CSsdpSearchRequestManager::DwThreadFunc(void)

- ea: `0x180005d90`
- end: `0x180006908`
- name: `?DwThreadFunc@CSsdpSearchRequestManager@@QEAAKXZ`
- size: `2936`
- prototype: `__int64 __fastcall(char *lpCriticalSection)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x180025170`

## callees

- `0x180003a00`
- `0x180004dc0`
- `0x18000554c`
- `0x180005d90`
- `0x180006910`
- `0x180006d70`
- `0x180006eb8`
- `0x180007cf0`
- `0x180007db0`
- `0x180008930`
- `0x18000920c`
- `0x180009798`
- `0x18000d09c`
- `0x180017400`
- `0x1800255a8`
- `0x180026a30`
- `0x18002735c`
- `0x180028000`
- `0x18002dcf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800062b0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000642e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800065be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800062b0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000642e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800065be`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006191`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000653a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006191`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000653a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006007`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006007`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005e7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005fb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005e7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005fb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800062e9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800066a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800062e9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800066a9`
- `WS2_32!WSAAddressToStringA` at `0x180006178`
- `WS2_32!WSAAddressToStringA` at `0x180006178`
- `WS2_32!__imp_select` at `0x180005f2f`
- `WS2_32!__imp_select` at `0x180005f2f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800065f6`
- `WS2_32!__imp_WSAGetLastError` at `0x18000662a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800065f6`
- `WS2_32!__imp_WSAGetLastError` at `0x18000662a`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequestManager::DwThreadFunc(char *lpCriticalSection)
{
  int v1; // r15d
  LPCRITICAL_SECTION v2; // r14
  unsigned int v3; // r12d
  HANDLE *v4; // r13
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  fd_set *v6; // rdi
  int v7; // ebx
  int v8; // r8d
  __int64 v9; // rax
  __int64 v10; // r9
  __int64 v11; // r9
  int i; // r11d
  _WORD *v13; // rax
  __int64 v14; // r10
  unsigned int v15; // edx
  __int64 v16; // rcx
  int v17; // ebx
  int DebugInfo; // edi
  int v19; // esi
  int v20; // eax
  unsigned int fd_count; // edx
  unsigned int v23; // r10d
  int v24; // eax
  char *v25; // r12
  unsigned int v26; // r14d
  char **v27; // rbx
  size_t v28; // rbx
  _BYTE *v29; // rax
  _BYTE *v30; // rcx
  LPCRITICAL_SECTION v31; // rbx
  LPCSTR v32; // rbx
  int updated; // eax
  int v34; // r14d
  unsigned int Win32Error; // eax
  __int64 v36; // rdx
  CHAR *v37; // r8
  _BYTE *v38; // rax
  unsigned int v39; // r14d
  unsigned int v40; // r14d
  unsigned int v41; // r14d
  char *v42; // rdx
  unsigned int v43; // r14d
  __int64 *v44; // rbx
  char *v45; // rax
  char *v46; // r10
  int v47; // eax
  int Error; // eax
  bool v49; // zf
  int v50; // eax
  const char *v51; // rcx
  int v52; // [rsp+48h] [rbp-C0h]
  char *dwAddressStringLength; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v55[2]; // [rsp+60h] [rbp-A8h] BYREF
  struct timeval timeout[4]; // [rsp+68h] [rbp-A0h] BYREF
  struct _NETWORK_LOCATION_INFO *v57[12]; // [rsp+88h] [rbp-80h] BYREF
  _OWORD v58[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v59; // [rsp+108h] [rbp+0h]
  void *Block[2]; // [rsp+118h] [rbp+10h]
  __int128 v61; // [rsp+128h] [rbp+20h]
  char **v62; // [rsp+138h] [rbp+30h]
  struct sockaddr_storage saAddress; // [rsp+148h] [rbp+40h] BYREF
  CHAR szAddressString[256]; // [rsp+1C8h] [rbp+C0h] BYREF

  v1 = 0;
  v2 = (LPCRITICAL_SECTION)lpCriticalSection;
  v3 = 0;
  if ( *((_DWORD *)lpCriticalSection + 168) )
    return 0;
  v4 = (HANDLE *)(lpCriticalSection + 64);
  v5 = (struct _RTL_CRITICAL_SECTION *)(lpCriticalSection + 72);
  v6 = (fd_set *)(lpCriticalSection + 152);
  do
  {
    v55[1] = 0;
    v55[0] = 0;
    memset(&saAddress, 0, sizeof(saAddress));
    v62 = 0;
    memset(v58, 0, sizeof(v58));
    v59 = 0;
    *(_OWORD *)Block = 0;
    v61 = 0;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
    v49 = *((_DWORD *)v4 + 18) == 0;
    timeout[0] = (struct timeval)60LL;
    if ( !v49 )
      CSsdpSearchSocketManager::ClearOld((CSsdpSearchSocketManager *)v4);
    EnterCriticalSection(v5);
    v7 = *((_DWORD *)v4 + 14);
    v8 = 0;
    *((_DWORD *)v4 + 20) = 1;
    *((_DWORD *)v4 + 21) = 0;
    v6->fd_count = 0;
    if ( v7 > 0 )
    {
      v9 = 0;
      do
      {
        v10 = (__int64)v4[6] + 32 * v9;
        if ( *(_WORD *)(v10 + 24) == 2 )
        {
          fd_count = v6->fd_count;
          v23 = 0;
          if ( v6->fd_count )
          {
            while ( v4[v23 + 12] != *(HANDLE *)v10 )
            {
              if ( ++v23 >= fd_count )
                goto LABEL_35;
            }
          }
          else
          {
LABEL_35:
            if ( v23 == fd_count && fd_count < 0x40 )
            {
              v4[v23 + 12] = *(HANDLE *)v10;
              ++v6->fd_count;
            }
          }
        }
        ++v8;
        ++v9;
      }
      while ( v8 < v7 );
      v11 = 0;
      for ( i = 0; i < v7; ++i )
      {
        v13 = v4[6];
        v14 = 16 * v11;
        if ( v13[16 * v11 + 12] != 2 )
        {
          v15 = v6->fd_count;
          v16 = 0;
          if ( v6->fd_count )
          {
            while ( v4[v16 + 12] != *(HANDLE *)&v13[v14] )
            {
              v16 = (unsigned int)(v16 + 1);
              if ( (unsigned int)v16 >= v15 )
                goto LABEL_15;
            }
          }
          else
          {
LABEL_15:
            if ( (_DWORD)v16 == v15 && v15 < 0x40 )
            {
              v4[v16 + 12] = *(HANDLE *)&v13[v14];
              ++v6->fd_count;
            }
          }
        }
        ++v11;
      }
    }
    LeaveCriticalSection(v5);
    v17 = select(-1, v6, 0, 0, timeout);
    EnterCriticalSection(v5);
    *((_DWORD *)v4 + 20) = 0;
    LeaveCriticalSection(v5);
    if ( v17 == -1 )
    {
      if ( !HIDWORD(v2[3].LockSemaphore) )
      {
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
            0xFFFFFFFFLL);
        WaitForSingleObject(v2[17].DebugInfo, 0x1388u);
      }
    }
    else if ( v17 )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
      EnterCriticalSection(v5);
      DebugInfo = (int)v2[3].DebugInfo;
      LeaveCriticalSection(v5);
      v19 = 0;
      if ( DebugInfo > 0 )
      {
        while ( 1 )
        {
          if ( LODWORD(v2[16].SpinCount) )
            goto LABEL_30;
          dwAddressStringLength = 0;
          *(_OWORD *)&timeout[1].tv_sec = 0;
          EnterCriticalSection(v2);
          v20 = CSsdpSearchSocketManager::HrReadData(
                  (CSsdpSearchSocketManager *)v4,
                  v19,
                  &saAddress,
                  &dwAddressStringLength,
                  &v55[1],
                  v55,
                  (struct _GUID *)&timeout[1]);
          v52 = v20;
          v3 = v20;
          if ( v20 < 0 )
          {
            if ( v20 != -2147024875
              && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
                (unsigned int)v20);
            }
            LeaveCriticalSection(v2);
            goto LABEL_29;
          }
          LeaveCriticalSection(v2);
          v24 = InitializeSsdpRequest((struct _SSDP_REQUEST *)v58);
          v25 = dwAddressStringLength;
          if ( !v24 )
          {
            v52 = -2147024882;
LABEL_148:
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
            goto LABEL_67;
          }
          v26 = v55[0];
          if ( !(unsigned int)ParseSsdpResponse(dwAddressStringLength, v55[1], v55[0], (struct _SSDP_REQUEST *)v58)
            || (v27 = v62, !v62[3]) )
          {
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
              FreeSsdpRequest((struct _SSDP_REQUEST *)v58);
              v2 = (LPCRITICAL_SECTION)lpCriticalSection;
              goto LABEL_67;
            }
            v2 = (LPCRITICAL_SECTION)lpCriticalSection;
            goto LABEL_66;
          }
          if ( saAddress.ss_family != 23 )
            break;
          if ( v26 - 2 > 3 )
            v26 = 2;
          if ( !*v62 )
          {
            v39 = v26 - 2;
            if ( v39 )
            {
              v40 = v39 - 1;
              if ( v40 )
              {
                v41 = v40 - 1;
                if ( v41 )
                {
                  if ( v41 == 1 )
                  {
                    v42 = SzaDupSza("[FF05::C]:1900");
                    *v62 = v42;
LABEL_155:
                    if ( v42 )
                      goto LABEL_47;
                  }
                  goto LABEL_156;
                }
                v51 = "[FF04::C]:1900";
              }
              else
              {
                v51 = "[FF03::C]:1900";
              }
            }
            else
            {
              v51 = "[FF02::C]:1900";
            }
            v42 = SzaDupSza(v51);
            *v62 = v42;
            goto LABEL_155;
          }
LABEL_47:
          v59 = *(_OWORD *)&timeout[1].tv_sec;
          if ( !Block[0] )
          {
            LODWORD(dwAddressStringLength) = 256;
            if ( WSAAddressToStringA((LPSOCKADDR)&saAddress, 0x80u, 0, szAddressString, (LPDWORD)&dwAddressStringLength) == -1 )
            {
              Error = WSAGetLastError();
              v49 = Error == 0;
              if ( Error > 0 )
                v49 = 0;
              if ( !v49 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
              {
                v50 = WSAGetLastError();
                if ( v50 > 0 )
                  v50 = (unsigned __int16)v50 | 0x80070000;
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  49,
                  WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
                  (unsigned int)v50);
              }
              goto LABEL_53;
            }
            v28 = (unsigned int)((_DWORD)dwAddressStringLength + 1);
            v29 = malloc(v28);
            Block[0] = v29;
            v30 = v29;
            if ( !v29 )
              goto LABEL_50;
            if ( !v28 )
              goto LABEL_95;
            if ( v28 > 0x7FFFFFFF )
            {
              *v29 = 0;
              goto LABEL_95;
            }
            v36 = 2147483646;
            v37 = szAddressString;
            do
            {
              if ( !v36 )
                break;
              if ( !*v37 )
                break;
              *v30++ = *v37++;
              --v36;
              --v28;
            }
            while ( v28 );
            v38 = v30 - 1;
            if ( v28 )
              v38 = v30;
            *v38 = 0;
            if ( !v28 )
            {
LABEL_95:
              free(Block[0]);
              Block[0] = 0;
            }
LABEL_50:
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                50,
                WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
                Block[0]);
          }
LABEL_53:
          v2 = (LPCRITICAL_SECTION)lpCriticalSection;
          EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
          v31 = (LPCRITICAL_SECTION)(lpCriticalSection + 40);
          if ( *((_QWORD *)lpCriticalSection + 5) )
          {
            do
            {
              if ( !v31 || !v31->DebugInfo )
                break;
              v47 = CSsdpSearchRequest::HrResponseReceived(
                      (CSsdpSearchRequest *)&v31->DebugInfo->CriticalSection,
                      (const struct _SSDP_REQUEST *)v58);
              v31 = (LPCRITICAL_SECTION)v31->DebugInfo;
              v52 = v47;
              if ( !v47 )
                v1 = 1;
            }
            while ( v31 && v31->DebugInfo );
            v4 = (HANDLE *)(lpCriticalSection + 64);
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
          if ( v1 )
          {
            v32 = WPP_GLOBAL_Control;
            v1 = 0;
            goto LABEL_56;
          }
          if ( *((_QWORD *)lpCriticalSection + 92) )
          {
            EnterCriticalSection(&stru_180041510);
            v1 = 0;
            v43 = 0;
            if ( qword_180041538 )
            {
              v44 = &qword_180041538;
              while ( v44 && *v44 )
              {
                if ( (unsigned int)CSsdpNotifyRequest::FIsMatchingSearchResponse(
                                     (CSsdpNotifyRequest *)(*v44 + 8),
                                     (const struct _SSDP_REQUEST *)v58) )
                {
                  v43 = 1;
                  break;
                }
                v44 = (__int64 *)*v44;
                if ( !v44 || !*v44 )
                  break;
              }
            }
            LeaveCriticalSection(&stru_180041510);
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v43);
              v32 = WPP_GLOBAL_Control;
            }
            if ( !v43 )
              goto LABEL_65;
LABEL_56:
            if ( v32 != (LPCSTR)&WPP_GLOBAL_Control && (v32[28] & 8) != 0 )
            {
              WPP_SF_(*((_QWORD *)v32 + 2), 52, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
              v32 = WPP_GLOBAL_Control;
            }
            memset_0(v57, 0, 0x58u);
            if ( !v62[3] || v62[2] )
            {
              v34 = -2147024809;
            }
            else
            {
              if ( (unsigned int)CopySsdpRequest(v57, (const struct _SSDP_REQUEST *)v58) )
              {
                if ( (unsigned int)ConvertToAliveNotify((struct _SSDP_REQUEST *)v57) )
                  updated = CSsdpCacheEntryManager::HrUpdateCacheList(
                              &CSsdpCacheEntryManager::s_instance,
                              (struct _SSDP_REQUEST *)v57,
                              1);
                else
                  updated = -2147024882;
                v52 = updated;
                v34 = updated;
                FreeSsdpRequest((struct _SSDP_REQUEST *)v57);
                if ( v34 >= 0 )
                {
LABEL_65:
                  v2 = (LPCRITICAL_SECTION)lpCriticalSection;
                  goto LABEL_66;
                }
                v32 = WPP_GLOBAL_Control;
LABEL_83:
                if ( v32 != (LPCSTR)&WPP_GLOBAL_Control && (v32[28] & 1) != 0 )
                  WPP_SF_d(*((_QWORD *)v32 + 2), 53, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, (unsigned int)v34);
                goto LABEL_65;
              }
              v32 = WPP_GLOBAL_Control;
              v34 = -2147024882;
            }
            v52 = v34;
            goto LABEL_83;
          }
          v1 = 0;
LABEL_66:
          FreeSsdpRequest((struct _SSDP_REQUEST *)v58);
          if ( v52 < 0 )
            goto LABEL_148;
LABEL_67:
          free(v25);
          v3 = v52;
LABEL_29:
          if ( ++v19 >= DebugInfo )
            goto LABEL_30;
        }
        if ( saAddress.ss_family == 2 )
        {
          if ( *v62 )
            goto LABEL_47;
          v45 = (char *)malloc(0x15u);
          v46 = v45;
          if ( v45 )
          {
            if ( (int)StringCbCopyA(v45, 0x15u, "239.255.255.250:1900") < 0 )
            {
              free(v46);
              *v62 = 0;
              goto LABEL_156;
            }
            v27 = v62;
          }
          *v27 = v46;
          if ( v46 )
            goto LABEL_47;
        }
LABEL_156:
        if ( v52 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
            (unsigned int)v52);
        goto LABEL_47;
      }
LABEL_30:
      v5 = (struct _RTL_CRITICAL_SECTION *)(v4 + 1);
      v6 = (fd_set *)(v4 + 11);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
      if ( WaitForSingleObject(v2[17].DebugInfo, 0xFFFFFFFF) == -1
        && (unsigned int)HrFromLastWin32Error()
        && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        Win32Error = HrFromLastWin32Error();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, Win32Error);
      }
    }
  }
  while ( !LODWORD(v2[16].SpinCount) );
  if ( v3 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180005d90  mov     r11, rsp
0x180005d93  push    rbp
0x180005d94  push    r12
0x180005d96  push    r14
0x180005d98  push    r15
0x180005d9a  lea     rbp, [r11-1F8h]
0x180005da1  sub     rsp, 2D8h
0x180005da8  mov     rax, cs:__security_cookie
0x180005daf  xor     rax, rsp
0x180005db2  mov     [rbp+1F0h+var_30], rax
0x180005db9  mov     eax, [rcx+2A0h]
0x180005dbf  xor     r15d, r15d
0x180005dc2  mov     [rsp+2F0h+lpCriticalSection], rcx
0x180005dc7  mov     r14, rcx
0x180005dca  mov     r12d, r15d
0x180005dcd  test    eax, eax
0x180005dcf  jnz     loc_1800065EE
0x180005dd5  mov     [r11+10h], rbx
0x180005dd9  lea     rbx, WPP_GLOBAL_Control
0x180005de0  mov     [r11+18h], rsi
0x180005de4  mov     [r11+20h], rdi
0x180005de8  mov     [r11-28h], r13
0x180005dec  lea     r13, [rcx+40h]
0x180005df0  lea     rsi, [r13+8]
0x180005df4  lea     rdi, [r13+58h]
0x180005df8  nop     dword ptr [rax+rax+00000000h]
0x180005e00  xorps   xmm0, xmm0
0x180005e03  mov     [rsp+2F0h+var_298+4], r15d
0x180005e08  xor     eax, eax
0x180005e0a  mov     [rsp+2F0h+var_298], r15d
0x180005e0f  movups  xmmword ptr [rbp+1F0h+saAddress.sa_family], xmm0
0x180005e13  mov     [rbp+1F0h+var_1C0], rax
0x180005e17  movups  [rbp+1F0h+var_1A0], xmm0
0x180005e1b  movups  [rbp+1F0h+var_190], xmm0
0x180005e1f  movups  [rbp+1F0h+var_180], xmm0
0x180005e23  movups  [rbp+1F0h+var_170], xmm0
0x180005e2a  movups  [rbp+1F0h+var_160], xmm0
0x180005e31  movups  [rbp+1F0h+var_150], xmm0
0x180005e38  movups  [rbp+1F0h+var_140], xmm0
0x180005e3f  movups  [rbp+1F0h+var_210], xmm0
0x180005e43  movups  [rbp+1F0h+var_200], xmm0
0x180005e47  movups  [rbp+1F0h+var_1F0], xmm0
0x180005e4b  movups  xmmword ptr [rbp+1F0h+Block], xmm0
0x180005e4f  movups  [rbp+1F0h+var_1D0], xmm0
0x180005e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e5a  cmp     rcx, rbx
0x180005e5d  jnz     loc_180006348
0x180005e63  cmp     dword ptr [r13+48h], 0
0x180005e68  mov     qword ptr [rsp+2F0h+var_290], 3Ch ; '<'
0x180005e71  jnz     loc_18000665C
0x180005e77  mov     rcx, rsi; lpCriticalSection
0x180005e7a  call    cs:__imp_EnterCriticalSection
0x180005e80  mov     ebx, [r13+38h]
0x180005e84  mov     r8d, r15d
0x180005e87  mov     dword ptr [r13+50h], 1
0x180005e8f  mov     [r13+54h], r15d
0x180005e93  mov     [rdi], r15d
0x180005e96  test    ebx, ebx
0x180005e98  jle     short loc_180005F0E
0x180005e9a  mov     rax, r15
0x180005e9d  nop     dword ptr [rax]
0x180005ea0  mov     r9, rax
0x180005ea3  shl     r9, 5
0x180005ea7  add     r9, [r13+30h]
0x180005eab  cmp     word ptr [r9+18h], 2
0x180005eb1  jz      loc_180006074
0x180005eb7  inc     r8d
0x180005eba  inc     rax
0x180005ebd  cmp     r8d, ebx
0x180005ec0  jl      short loc_180005EA0
0x180005ec2  mov     r9, r15
0x180005ec5  mov     r11d, r15d
0x180005ec8  mov     rax, [r13+30h]
0x180005ecc  mov     r10, r9
0x180005ecf  shl     r10, 5
0x180005ed3  cmp     word ptr [r10+rax+18h], 2
0x180005eda  jz      short loc_180005F03
0x180005edc  mov     edx, [rdi]
0x180005ede  mov     ecx, r15d
0x180005ee1  test    edx, edx
0x180005ee3  jz      short loc_180005EF6
0x180005ee5  mov     r8, [r10+rax]
0x180005ee9  cmp     [r13+rcx*8+60h], r8
0x180005eee  jz      short loc_180005F03
0x180005ef0  inc     ecx
0x180005ef2  cmp     ecx, edx
0x180005ef4  jb      short loc_180005EE9
0x180005ef6  cmp     ecx, edx
0x180005ef8  jnz     short loc_180005F03
0x180005efa  cmp     edx, 40h ; '@'
0x180005efd  jb      loc_1800060BC
0x180005f03  inc     r11d
0x180005f06  inc     r9
0x180005f09  cmp     r11d, ebx
0x180005f0c  jl      short loc_180005EC8
0x180005f0e  mov     rcx, rsi; lpCriticalSection
0x180005f11  call    cs:__imp_LeaveCriticalSection
0x180005f17  lea     rax, [rsp+2F0h+var_290]
0x180005f1c  xor     r9d, r9d; exceptfds
0x180005f1f  xor     r8d, r8d; writefds
0x180005f22  mov     [rsp+2F0h+timeout], rax; timeout
0x180005f27  mov     rdx, rdi; readfds
0x180005f2a  mov     ecx, 0FFFFFFFFh; nfds
0x180005f2f  call    cs:__imp_select
0x180005f35  mov     rcx, rsi; lpCriticalSection
0x180005f38  mov     ebx, eax
0x180005f3a  call    cs:__imp_EnterCriticalSection
0x180005f40  mov     rcx, rsi; lpCriticalSection
0x180005f43  mov     [r13+50h], r15d
0x180005f47  call    cs:__imp_LeaveCriticalSection
0x180005f4d  cmp     ebx, 0FFFFFFFFh
0x180005f50  jz      loc_18000649B
0x180005f56  test    ebx, ebx
0x180005f58  jz      loc_1800062C0
0x180005f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f65  lea     rbx, WPP_GLOBAL_Control
0x180005f6c  cmp     rcx, rbx
0x180005f6f  jz      short loc_180005F7B
0x180005f71  test    byte ptr [rcx+1Ch], 8
0x180005f75  jnz     loc_1800066CE
0x180005f7b  mov     rcx, rsi; lpCriticalSection
0x180005f7e  call    cs:__imp_EnterCriticalSection
0x180005f84  mov     edi, [r14+78h]
0x180005f88  mov     rcx, rsi; lpCriticalSection
0x180005f8b  call    cs:__imp_LeaveCriticalSection
0x180005f91  mov     esi, r15d
0x180005f94  test    edi, edi
0x180005f96  jle     short loc_180006013
0x180005f98  mov     eax, [r14+2A0h]
0x180005f9f  test    eax, eax
0x180005fa1  jnz     short loc_180006013
0x180005fa3  xorps   xmm0, xmm0
0x180005fa6  mov     qword ptr [rsp+2F0h+dwAddressStringLength], r15
0x180005fab  mov     rcx, r14; lpCriticalSection
0x180005fae  movups  xmmword ptr [rsp+2F0h+var_290+8], xmm0
0x180005fb3  call    cs:__imp_EnterCriticalSection
0x180005fb9  lea     rax, [rsp+2F0h+var_290+8]
0x180005fbe  mov     edx, esi; int
0x180005fc0  mov     [rsp+30h], rax; struct _GUID *
0x180005fc5  lea     r9, [rsp+2F0h+dwAddressStringLength]; char **
0x180005fca  lea     rax, [rsp+2F0h+var_298]
0x180005fcf  mov     rcx, r13; this
0x180005fd2  mov     [rsp+2F0h+var_2C8], rax; unsigned int *
0x180005fd7  lea     r8, [rbp+1F0h+saAddress]; struct sockaddr_storage *
0x180005fdb  lea     rax, [rsp+2F0h+var_298+4]
0x180005fe0  mov     [rsp+2F0h+timeout], rax; unsigned int *
0x180005fe5  call    ?HrReadData@CSsdpSearchSocketManager@@QEAAJJPEAUsockaddr_storage@@PEAPEADPEAK2PEAU_GUID@@@Z; CSsdpSearchSocketManager::HrReadData(long,sockaddr_storage *,char * *,ulong *,ulong *,_GUID *)
0x180005fea  mov     dword ptr [rsp+2F0h+var_2B0], eax
0x180005fee  mov     r12d, eax
0x180005ff1  test    eax, eax
0x180005ff3  jns     loc_1800060CC
0x180005ff9  cmp     eax, 80070015h
0x180005ffe  jnz     loc_1800066E8
0x180006004  mov     rcx, r14; lpCriticalSection
0x180006007  call    cs:__imp_LeaveCriticalSection
0x18000600d  inc     esi
0x18000600f  cmp     esi, edi
0x180006011  jl      short loc_180005F98
0x180006013  lea     rsi, [r13+8]
0x180006017  lea     rdi, [r13+58h]
0x18000601b  mov     eax, [r14+2A0h]
0x180006022  test    eax, eax
0x180006024  jz      loc_180005E00
0x18000602a  mov     r13, [rsp+2D0h]
0x180006032  mov     rdi, [rsp+2F0h+arg_18]
0x18000603a  mov     rsi, [rsp+2F0h+arg_10]
0x180006042  test    r12d, r12d
0x180006045  jnz     loc_1800068D1
0x18000604b  mov     rbx, [rsp+2F0h+arg_8]
0x180006053  mov     eax, r12d
0x180006056  mov     rcx, [rbp+1F0h+var_30]
0x18000605d  xor     rcx, rsp; StackCookie
0x180006060  call    __security_check_cookie
0x180006065  add     rsp, 2D8h
0x18000606c  pop     r15
0x18000606e  pop     r14
0x180006070  pop     r12
0x180006072  pop     rbp
0x180006073  retn
0x180006074  mov     edx, [rdi]
0x180006076  mov     r10d, r15d
0x180006079  test    edx, edx
0x18000607b  jnz     short loc_1800060A1
0x18000607d  cmp     r10d, edx
0x180006080  jnz     loc_180005EB7
0x180006086  cmp     edx, 40h ; '@'
0x180006089  jnb     loc_180005EB7
0x18000608f  mov     rcx, [r9]
0x180006092  mov     edx, r10d
0x180006095  mov     [r13+rdx*8+60h], rcx
0x18000609a  inc     dword ptr [rdi]
0x18000609c  jmp     loc_180005EB7
0x1800060a1  mov     r11, [r9]
0x1800060a4  mov     ecx, r10d
0x1800060a7  cmp     [r13+rcx*8+60h], r11
0x1800060ac  jz      loc_180005EB7
0x1800060b2  inc     r10d
0x1800060b5  cmp     r10d, edx
0x1800060b8  jb      short loc_1800060A4
0x1800060ba  jmp     short loc_18000607D
0x1800060bc  mov     rax, [r10+rax]
0x1800060c0  mov     [r13+rcx*8+60h], rax
0x1800060c5  inc     dword ptr [rdi]
0x1800060c7  jmp     loc_180005F03
0x1800060cc  mov     rcx, r14; lpCriticalSection
0x1800060cf  call    cs:__imp_LeaveCriticalSection
0x1800060d5  lea     rcx, [rbp+1F0h+var_210]; struct _SSDP_REQUEST *
0x1800060d9  call    ?InitializeSsdpRequest@@YAHPEAU_SSDP_REQUEST@@@Z; InitializeSsdpRequest(_SSDP_REQUEST *)
0x1800060de  mov     r12, qword ptr [rsp+2F0h+dwAddressStringLength]
0x1800060e3  test    eax, eax
0x1800060e5  jz      loc_18000671F
0x1800060eb  mov     r14d, [rsp+2F0h+var_298]
0x1800060f0  lea     r9, [rbp+1F0h+var_210]; struct _SSDP_REQUEST *
0x1800060f4  mov     edx, [rsp+2F0h+var_298+4]; unsigned int
0x1800060f8  mov     r8d, r14d; unsigned int
0x1800060fb  mov     rcx, r12; String
0x1800060fe  call    ?ParseSsdpResponse@@YAHPEADKKPEAU_SSDP_REQUEST@@@Z; ParseSsdpResponse(char *,ulong,ulong,_SSDP_REQUEST *)
0x180006103  test    eax, eax
0x180006105  jz      loc_18000636C
0x18000610b  mov     rbx, [rbp+1F0h+var_1C0]
0x18000610f  cmp     qword ptr [rbx+18h], 0
0x180006114  jz      loc_180006893
0x18000611a  movzx   eax, [rbp+1F0h+saAddress.sa_family]
0x18000611e  cmp     ax, 17h
0x180006122  jz      loc_180006441
0x180006128  cmp     ax, 2
0x18000612c  jnz     loc_180006797
0x180006132  cmp     qword ptr [rbx], 0
0x180006136  jz      loc_180006535
0x18000613c  lea     r14, WPP_GLOBAL_Control
0x180006143  cmp     [rbp+1F0h+Block], 0
0x180006148  movups  xmm0, xmmword ptr [rsp+2F0h+var_290+8]
0x18000614d  movaps  [rbp+1F0h+var_1F0], xmm0
0x180006151  jnz     short loc_1800061BD
0x180006153  lea     rax, [rsp+2F0h+dwAddressStringLength]
0x180006158  mov     [rsp+2F0h+dwAddressStringLength], 100h
0x180006160  lea     r9, [rbp+1F0h+szAddressString]; lpszAddressString
0x180006167  mov     [rsp+2F0h+timeout], rax; lpdwAddressStringLength
0x18000616c  xor     r8d, r8d; lpProtocolInfo
0x18000616f  lea     rcx, [rbp+1F0h+saAddress]; lpsaAddress
0x180006173  mov     edx, 80h; dwAddressLength
0x180006178  call    cs:__imp_WSAAddressToStringA
0x18000617e  cmp     eax, 0FFFFFFFFh
0x180006181  jz      loc_1800065F6
0x180006187  mov     eax, [rsp+2F0h+dwAddressStringLength]
0x18000618b  inc     eax
0x18000618d  mov     ecx, eax; Size
0x18000618f  mov     ebx, eax
0x180006191  call    cs:__imp_malloc
0x180006197  mov     [rbp+1F0h+Block], rax
0x18000619b  mov     rcx, rax
0x18000619e  test    rax, rax
0x1800061a1  jnz     loc_1800063DA
0x1800061a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061ae  cmp     rcx, r14
0x1800061b1  jz      short loc_1800061BD
0x1800061b3  test    byte ptr [rcx+1Ch], 8
0x1800061b7  jnz     loc_1800067F6
0x1800061bd  mov     r14, [rsp+2F0h+lpCriticalSection]
0x1800061c2  mov     rcx, r14; lpCriticalSection
0x1800061c5  call    cs:__imp_EnterCriticalSection
0x1800061cb  cmp     qword ptr [r14+28h], 0
0x1800061d0  lea     rbx, [r14+28h]
0x1800061d4  jnz     loc_180006575
0x1800061da  mov     rcx, r14; lpCriticalSection
0x1800061dd  call    cs:__imp_LeaveCriticalSection
0x1800061e3  test    r15d, r15d
0x1800061e6  jz      loc_180006386
0x1800061ec  mov     rbx, cs:WPP_GLOBAL_Control
0x1800061f3  lea     rax, WPP_GLOBAL_Control
0x1800061fa  xor     r15d, r15d
0x1800061fd  cmp     rbx, rax
0x180006200  jz      short loc_18000620C
0x180006202  test    byte ptr [rbx+1Ch], 8
0x180006206  jnz     loc_180006849
0x18000620c  xor     edx, edx; Val
0x18000620e  lea     rcx, [rbp+1F0h+var_270]; void *
0x180006212  mov     r8d, 58h ; 'X'; Size
0x180006218  call    memset_0
0x18000621d  mov     rax, [rbp+1F0h+var_1C0]
0x180006221  cmp     qword ptr [rax+18h], 0
0x180006226  jz      loc_180006883
0x18000622c  cmp     qword ptr [rax+10h], 0
0x180006231  jnz     loc_180006883
0x180006237  lea     rdx, [rbp+1F0h+var_210]; struct _SSDP_REQUEST *
0x18000623b  lea     rcx, [rbp+1F0h+var_270]; struct _SSDP_REQUEST *
0x18000623f  call    ?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z; CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)
0x180006244  test    eax, eax
0x180006246  jz      loc_18000686A
0x18000624c  lea     rcx, [rbp+1F0h+var_270]; struct _SSDP_REQUEST *
0x180006250  call    ?ConvertToAliveNotify@@YAHPEAU_SSDP_REQUEST@@@Z; ConvertToAliveNotify(_SSDP_REQUEST *)
0x180006255  test    eax, eax
0x180006257  jz      loc_180006879
0x18000625d  mov     r8d, 1; int
0x180006263  lea     rdx, [rbp+1F0h+var_270]; struct _SSDP_REQUEST *
0x180006267  lea     rcx, ?s_instance@CSsdpCacheEntryManager@@0V1@A; lpCriticalSection
0x18000626e  call    ?HrUpdateCacheList@CSsdpCacheEntryManager@@QEAAJPEAU_SSDP_REQUEST@@H@Z; CSsdpCacheEntryManager::HrUpdateCacheList(_SSDP_REQUEST *,int)
0x180006273  lea     rcx, [rbp+1F0h+var_270]; struct _SSDP_REQUEST *
0x180006277  mov     dword ptr [rsp+2F0h+var_2B0], eax
0x18000627b  mov     r14d, eax
  ... truncated ...
```
