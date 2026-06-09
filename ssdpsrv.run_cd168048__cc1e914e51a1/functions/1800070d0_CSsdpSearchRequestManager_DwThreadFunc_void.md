# CSsdpSearchRequestManager::DwThreadFunc(void)

- ea: `0x1800070d0`
- end: `0x180007b44`
- name: `?DwThreadFunc@CSsdpSearchRequestManager@@QEAAKXZ`
- size: `2676`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x180026e30`

## callees

- `0x180005260`
- `0x180006040`
- `0x18000683c`
- `0x1800070d0`
- `0x180007b50`
- `0x180007cf0`
- `0x180008190`
- `0x180008304`
- `0x180009110`
- `0x1800091e4`
- `0x180009ef0`
- `0x18000a844`
- `0x18000ae9c`
- `0x180019850`
- `0x1800271fc`
- `0x1800287d0`
- `0x18002911c`
- `0x180029df0`
- `0x18002fe28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007589`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007663`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800077f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007589`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007663`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800077f5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800073ee`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000776f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800073ee`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000776f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800071d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000726d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007320`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007448`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800071d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000726d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007320`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007448`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800071c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007212`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000742a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800071c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007212`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000742a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800072b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000771d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800072b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000771d`
- `WS2_32!WSAAddressToStringA` at `0x1800073cf`
- `WS2_32!WSAAddressToStringA` at `0x1800073cf`
- `WS2_32!__imp_WSAGetLastError` at `0x180007833`
- `WS2_32!__imp_WSAGetLastError` at `0x18000786d`
- `WS2_32!__imp_WSAGetLastError` at `0x180007833`
- `WS2_32!__imp_WSAGetLastError` at `0x18000786d`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequestManager::DwThreadFunc(char *lpCriticalSection)
{
  int v1; // r12d
  unsigned int v3; // r13d
  CSsdpSearchSocketManager *v4; // r15
  int ReadableSocketCount; // eax
  int v6; // esi
  int v7; // r14d
  int v8; // eax
  int v10; // eax
  char *v11; // r13
  unsigned int v12; // r15d
  char **v13; // rbx
  size_t v14; // rbx
  _BYTE *v15; // rax
  _BYTE *v16; // rcx
  LPCRITICAL_SECTION v17; // rbx
  LPCSTR v18; // rbx
  int updated; // eax
  int v20; // r15d
  int v21; // r12d
  unsigned int v22; // r15d
  __int64 v23; // rdx
  CHAR *v24; // r8
  _BYTE *v25; // rax
  unsigned int v26; // r15d
  unsigned int v27; // r15d
  unsigned int v28; // r15d
  char *v29; // rdx
  __int64 *v30; // rbx
  char *v31; // rax
  char *v32; // r10
  unsigned int v33; // eax
  int Error; // eax
  bool v35; // zf
  int v36; // eax
  unsigned int Win32Error; // eax
  const char *v38; // rcx
  unsigned int v39; // [rsp+48h] [rbp-C0h]
  unsigned int v40; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD dwAddressStringLength[2]; // [rsp+50h] [rbp-B8h] BYREF
  char *Block[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _NETWORK_LOCATION_INFO *v43[12]; // [rsp+78h] [rbp-90h] BYREF
  _OWORD v44[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v45; // [rsp+F8h] [rbp-10h]
  void *v46[2]; // [rsp+108h] [rbp+0h]
  __int128 v47; // [rsp+118h] [rbp+10h]
  char **v48; // [rsp+128h] [rbp+20h]
  struct sockaddr_storage saAddress; // [rsp+138h] [rbp+30h] BYREF
  CHAR szAddressString[256]; // [rsp+1B8h] [rbp+B0h] BYREF

  v1 = 0;
  v3 = 0;
  if ( *((_DWORD *)lpCriticalSection + 168) )
    return 0;
  v4 = (CSsdpSearchSocketManager *)(lpCriticalSection + 64);
  do
  {
    dwAddressStringLength[0] = 0;
    v40 = 0;
    memset(&saAddress, 0, sizeof(saAddress));
    v48 = 0;
    memset(v44, 0, sizeof(v44));
    v45 = 0;
    *(_OWORD *)v46 = 0;
    v47 = 0;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
    ReadableSocketCount = CSsdpSearchSocketManager::GetReadableSocketCount(v4);
    if ( ReadableSocketCount == -1 )
    {
      if ( !*((_DWORD *)lpCriticalSection + 37) )
      {
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
            0xFFFFFFFFLL);
        WaitForSingleObject(*((HANDLE *)lpCriticalSection + 85), 0x1388u);
      }
    }
    else if ( ReadableSocketCount )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
      EnterCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 72));
      v6 = *((_DWORD *)lpCriticalSection + 30);
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 72));
      v7 = 0;
      if ( v6 > 0 )
      {
        while ( 1 )
        {
          if ( *((_DWORD *)lpCriticalSection + 168) )
            goto LABEL_20;
          memset(Block, 0, sizeof(Block));
          EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
          v8 = CSsdpSearchSocketManager::HrReadData(
                 v4,
                 v7,
                 &saAddress,
                 Block,
                 dwAddressStringLength,
                 &v40,
                 (struct _GUID *)&Block[1]);
          v39 = v8;
          v3 = v8;
          if ( v8 < 0 )
          {
            if ( v8 != -2147024875
              && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
                (unsigned int)v8);
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
            goto LABEL_14;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
          v10 = InitializeSsdpRequest((struct _SSDP_REQUEST *)v44);
          v11 = Block[0];
          if ( !v10 )
          {
            v39 = -2147024882;
LABEL_124:
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
            goto LABEL_56;
          }
          v12 = v40;
          if ( !(unsigned int)ParseSsdpResponse(Block[0], dwAddressStringLength[0], v40, (struct _SSDP_REQUEST *)v44)
            || (v13 = v48, !v48[3]) )
          {
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
              FreeSsdpRequest((struct _SSDP_REQUEST *)v44);
              goto LABEL_57;
            }
LABEL_54:
            v21 = v39;
            goto LABEL_55;
          }
          if ( saAddress.ss_family != 23 )
            break;
          if ( v12 - 2 > 3 )
            v12 = 2;
          if ( !*v48 )
          {
            v26 = v12 - 2;
            if ( v26 )
            {
              v27 = v26 - 1;
              if ( v27 )
              {
                v28 = v27 - 1;
                if ( v28 )
                {
                  if ( v28 == 1 )
                  {
                    v29 = SzaDupSza("[FF05::C]:1900");
                    *v48 = v29;
LABEL_131:
                    if ( v29 )
                      goto LABEL_29;
                  }
                  goto LABEL_132;
                }
                v38 = "[FF04::C]:1900";
              }
              else
              {
                v38 = "[FF03::C]:1900";
              }
            }
            else
            {
              v38 = "[FF02::C]:1900";
            }
            v29 = SzaDupSza(v38);
            *v48 = v29;
            goto LABEL_131;
          }
LABEL_29:
          v45 = *(_OWORD *)&Block[1];
          if ( v46[0] )
            goto LABEL_35;
          dwAddressStringLength[1] = 256;
          if ( WSAAddressToStringA((LPSOCKADDR)&saAddress, 0x80u, 0, szAddressString, &dwAddressStringLength[1]) != -1 )
          {
            v14 = dwAddressStringLength[1] + 1;
            v15 = malloc(v14);
            v46[0] = v15;
            v16 = v15;
            if ( v15 )
            {
              if ( v14 )
              {
                if ( v14 > 0x7FFFFFFF )
                {
                  *v15 = 0;
                }
                else
                {
                  v23 = 2147483646;
                  v24 = szAddressString;
                  do
                  {
                    if ( !v23 )
                      break;
                    if ( !*v24 )
                      break;
                    *v16++ = *v24++;
                    --v23;
                    --v14;
                  }
                  while ( v14 );
                  v25 = v16 - 1;
                  if ( v14 )
                    v25 = v16;
                  *v25 = 0;
                  if ( v14 )
                    goto LABEL_32;
                }
              }
              free(v46[0]);
              v46[0] = 0;
            }
LABEL_32:
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
              WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v46[0]);
            goto LABEL_35;
          }
          Error = WSAGetLastError();
          v35 = Error == 0;
          if ( Error > 0 )
            v35 = 0;
          if ( !v35 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          {
            v36 = WSAGetLastError();
            if ( v36 > 0 )
              v36 = (unsigned __int16)v36 | 0x80070000;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
              (unsigned int)v36);
          }
LABEL_35:
          EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
          v17 = (LPCRITICAL_SECTION)(lpCriticalSection + 40);
          if ( *((_QWORD *)lpCriticalSection + 5) )
          {
            do
            {
              if ( !v17 || !v17->DebugInfo )
                break;
              v33 = CSsdpSearchRequest::HrResponseReceived(
                      (CSsdpSearchRequest *)&v17->DebugInfo->CriticalSection,
                      (const struct _SSDP_REQUEST *)v44);
              v17 = (LPCRITICAL_SECTION)v17->DebugInfo;
              v39 = v33;
              if ( !v33 )
                v1 = 1;
            }
            while ( v17 && v17->DebugInfo );
            v11 = Block[0];
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
          if ( v1 )
          {
            v18 = WPP_GLOBAL_Control;
          }
          else
          {
            if ( !*((_QWORD *)lpCriticalSection + 92) )
              goto LABEL_54;
            EnterCriticalSection(&stru_180044610);
            v22 = 0;
            if ( qword_180044638 )
            {
              v30 = &qword_180044638;
              while ( v30 && *v30 )
              {
                if ( (unsigned int)CSsdpNotifyRequest::FIsMatchingSearchResponse(
                                     (CSsdpNotifyRequest *)(*v30 + 8),
                                     (const struct _SSDP_REQUEST *)v44) )
                {
                  v22 = 1;
                  break;
                }
                v30 = (__int64 *)*v30;
                if ( !v30 || !*v30 )
                  break;
              }
            }
            LeaveCriticalSection(&stru_180044610);
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v22);
              v18 = WPP_GLOBAL_Control;
            }
            if ( !v22 )
              goto LABEL_54;
          }
          if ( v18 != (LPCSTR)&WPP_GLOBAL_Control && (v18[28] & 8) != 0 )
          {
            WPP_SF_(*((_QWORD *)v18 + 2), 52, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
            v18 = WPP_GLOBAL_Control;
          }
          memset_0(v43, 0, 0x58u);
          if ( !v48[3] || v48[2] )
          {
            v20 = -2147024809;
            goto LABEL_142;
          }
          if ( !(unsigned int)CopySsdpRequest(v43, (const struct _SSDP_REQUEST *)v44) )
          {
            v18 = WPP_GLOBAL_Control;
            v20 = -2147024882;
LABEL_142:
            v21 = v20;
            v39 = v20;
            goto LABEL_48;
          }
          if ( (unsigned int)ConvertToAliveNotify((struct _SSDP_REQUEST *)v43) )
            updated = CSsdpCacheEntryManager::HrUpdateCacheList(
                        &CSsdpCacheEntryManager::s_instance,
                        (struct _SSDP_REQUEST *)v43,
                        1);
          else
            updated = -2147024882;
          v39 = updated;
          v20 = updated;
          FreeSsdpRequest((struct _SSDP_REQUEST *)v43);
          v21 = v20;
          if ( v20 >= 0 )
            goto LABEL_55;
          v18 = WPP_GLOBAL_Control;
LABEL_48:
          if ( v18 != (LPCSTR)&WPP_GLOBAL_Control && (v18[28] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)v18 + 2), 53, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, (unsigned int)v20);
LABEL_55:
          FreeSsdpRequest((struct _SSDP_REQUEST *)v44);
          if ( v21 < 0 )
            goto LABEL_124;
LABEL_56:
          v1 = 0;
LABEL_57:
          free(v11);
          v3 = v39;
          v4 = (CSsdpSearchSocketManager *)(lpCriticalSection + 64);
LABEL_14:
          if ( ++v7 >= v6 )
            goto LABEL_20;
        }
        if ( saAddress.ss_family == 2 )
        {
          if ( *v48 )
            goto LABEL_29;
          v31 = (char *)malloc(0x15u);
          v32 = v31;
          if ( v31 )
          {
            if ( (int)StringCbCopyA(v31, 0x15u, "239.255.255.250:1900") < 0 )
            {
              free(v32);
              *v48 = 0;
              goto LABEL_132;
            }
            v13 = v48;
          }
          *v13 = v32;
          if ( v32 )
            goto LABEL_29;
        }
LABEL_132:
        if ( v39 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v39);
        goto LABEL_29;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
      if ( WaitForSingleObject(*((HANDLE *)lpCriticalSection + 85), 0xFFFFFFFF) == -1
        && (unsigned int)HrFromLastWin32Error()
        && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        Win32Error = HrFromLastWin32Error();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, Win32Error);
      }
    }
LABEL_20:
    ;
  }
  while ( !*((_DWORD *)lpCriticalSection + 168) );
  if ( v3 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800070d0  mov     r11, rsp
0x1800070d3  push    rbp
0x1800070d4  push    rdi
0x1800070d5  push    r12
0x1800070d7  push    r13
0x1800070d9  lea     rbp, [r11-1E8h]
0x1800070e0  sub     rsp, 2C8h
0x1800070e7  mov     rax, cs:__security_cookie
0x1800070ee  xor     rax, rsp
0x1800070f1  mov     [rbp+1E0h+var_30], rax
0x1800070f8  mov     eax, [rcx+2A0h]
0x1800070fe  xor     r12d, r12d
0x180007101  mov     rdi, rcx
0x180007104  mov     r13d, r12d
0x180007107  test    eax, eax
0x180007109  jnz     loc_18000782B
0x18000710f  mov     [r11+10h], rbx
0x180007113  lea     rbx, WPP_GLOBAL_Control
0x18000711a  mov     [r11+18h], rsi
0x18000711e  mov     [r11+20h], r14
0x180007122  mov     [r11-28h], r15
0x180007126  lea     r15, [rcx+40h]
0x18000712a  nop     word ptr [rax+rax+00h]
0x180007130  xorps   xmm0, xmm0
0x180007133  mov     [rsp+2E0h+dwAddressStringLength], r12d
0x180007138  xor     eax, eax
0x18000713a  mov     [rsp+2E0h+var_29C], r12d
0x18000713f  movups  xmmword ptr [rbp+1E0h+saAddress.sa_family], xmm0
0x180007143  mov     [rbp+1E0h+var_1C0], rax
0x180007147  movups  [rbp+1E0h+var_1A0], xmm0
0x18000714b  movups  [rbp+1E0h+var_190], xmm0
0x18000714f  movups  [rbp+1E0h+var_180], xmm0
0x180007153  movups  [rbp+1E0h+var_170], xmm0
0x180007157  movups  [rbp+1E0h+var_160], xmm0
0x18000715e  movups  [rbp+1E0h+var_150], xmm0
0x180007165  movups  [rbp+1E0h+var_140], xmm0
0x18000716c  movups  [rbp+1E0h+var_210], xmm0
0x180007170  movups  [rbp+1E0h+var_200], xmm0
0x180007174  movups  [rbp+1E0h+var_1F0], xmm0
0x180007178  movups  xmmword ptr [rbp+1E0h+var_1E0], xmm0
0x18000717c  movups  [rbp+1E0h+var_1D0], xmm0
0x180007180  mov     rcx, cs:WPP_GLOBAL_Control
0x180007187  cmp     rcx, rbx
0x18000718a  jnz     loc_180007531
0x180007190  mov     rcx, r15; this
0x180007193  call    ?GetReadableSocketCount@CSsdpSearchSocketManager@@QEAAJXZ; CSsdpSearchSocketManager::GetReadableSocketCount(void)
0x180007198  cmp     eax, 0FFFFFFFFh
0x18000719b  jz      loc_1800076D6
0x1800071a1  test    eax, eax
0x1800071a3  jz      loc_18000728E
0x1800071a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071b0  cmp     rcx, rbx
0x1800071b3  jz      short loc_1800071BF
0x1800071b5  test    byte ptr [rcx+1Ch], 8
0x1800071b9  jnz     loc_18000790F
0x1800071bf  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800071c3  call    cs:__imp_EnterCriticalSection
0x1800071ca  nop     dword ptr [rax+rax+00h]
0x1800071cf  mov     esi, [rdi+78h]
0x1800071d2  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800071d6  call    cs:__imp_LeaveCriticalSection
0x1800071dd  nop     dword ptr [rax+rax+00h]
0x1800071e2  lea     rbx, WPP_GLOBAL_Control
0x1800071e9  mov     r14d, r12d
0x1800071ec  test    esi, esi
0x1800071ee  jle     loc_1800072C5
0x1800071f4  mov     eax, [rdi+2A0h]
0x1800071fa  test    eax, eax
0x1800071fc  jnz     loc_180007285
0x180007202  xorps   xmm0, xmm0
0x180007205  mov     qword ptr [rsp+2E0h+Block], r12
0x18000720a  mov     rcx, rdi; lpCriticalSection
0x18000720d  movups  xmmword ptr [rsp+2E0h+Block+8], xmm0
0x180007212  call    cs:__imp_EnterCriticalSection
0x180007219  nop     dword ptr [rax+rax+00h]
0x18000721e  lea     rax, [rsp+2E0h+Block+8]
0x180007223  mov     edx, r14d; int
0x180007226  mov     [rsp+30h], rax; struct _GUID *
0x18000722b  lea     r9, [rsp+2E0h+Block]; char **
0x180007230  lea     rax, [rsp+2E0h+var_29C]
0x180007235  mov     rcx, r15; this
0x180007238  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x18000723d  lea     r8, [rbp+1E0h+saAddress]; struct sockaddr_storage *
0x180007241  lea     rax, [rsp+2E0h+dwAddressStringLength]
0x180007246  mov     [rsp+2E0h+lpdwAddressStringLength], rax; unsigned int *
0x18000724b  call    ?HrReadData@CSsdpSearchSocketManager@@QEAAJJPEAUsockaddr_storage@@PEAPEADPEAK2PEAU_GUID@@@Z; CSsdpSearchSocketManager::HrReadData(long,sockaddr_storage *,char * *,ulong *,ulong *,_GUID *)
0x180007250  mov     [rsp+2E0h+var_2A0], eax
0x180007254  mov     r13d, eax
0x180007257  test    eax, eax
0x180007259  jns     loc_18000731D
0x18000725f  cmp     eax, 80070015h
0x180007264  jnz     loc_180007929
0x18000726a  mov     rcx, rdi; lpCriticalSection
0x18000726d  call    cs:__imp_LeaveCriticalSection
0x180007274  nop     dword ptr [rax+rax+00h]
0x180007279  inc     r14d
0x18000727c  cmp     r14d, esi
0x18000727f  jl      loc_1800071F4
0x180007285  lea     rbx, WPP_GLOBAL_Control
0x18000728c  jmp     short loc_1800072C5
0x18000728e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007295  cmp     rcx, rbx
0x180007298  jz      short loc_1800072A4
0x18000729a  test    byte ptr [rcx+1Ch], 8
0x18000729e  jnz     loc_1800078A5
0x1800072a4  mov     rcx, [rdi+2A8h]; hHandle
0x1800072ab  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800072b0  call    cs:__imp_WaitForSingleObject
0x1800072b7  nop     dword ptr [rax+rax+00h]
0x1800072bc  cmp     eax, 0FFFFFFFFh
0x1800072bf  jz      loc_1800078BF
0x1800072c5  mov     eax, [rdi+2A0h]
0x1800072cb  test    eax, eax
0x1800072cd  jz      loc_180007130
0x1800072d3  mov     r15, [rsp+2C0h]
0x1800072db  mov     r14, [rsp+2E0h+arg_18]
0x1800072e3  mov     rsi, [rsp+2E0h+arg_10]
0x1800072eb  test    r13d, r13d
0x1800072ee  jnz     loc_180007B0D
0x1800072f4  mov     rbx, [rsp+2E0h+arg_8]
0x1800072fc  mov     eax, r13d
0x1800072ff  mov     rcx, [rbp+1E0h+var_30]
0x180007306  xor     rcx, rsp; StackCookie
0x180007309  call    __security_check_cookie
0x18000730e  add     rsp, 2C8h
0x180007315  pop     r13
0x180007317  pop     r12
0x180007319  pop     rdi
0x18000731a  pop     rbp
0x18000731b  retn
0x18000731d  mov     rcx, rdi; lpCriticalSection
0x180007320  call    cs:__imp_LeaveCriticalSection
0x180007327  nop     dword ptr [rax+rax+00h]
0x18000732c  lea     rcx, [rbp+1E0h+var_210]; struct _SSDP_REQUEST *
0x180007330  call    ?InitializeSsdpRequest@@YAHPEAU_SSDP_REQUEST@@@Z; InitializeSsdpRequest(_SSDP_REQUEST *)
0x180007335  mov     r13, qword ptr [rsp+2E0h+Block]
0x18000733a  test    eax, eax
0x18000733c  jz      loc_180007960
0x180007342  mov     r15d, [rsp+2E0h+var_29C]
0x180007347  lea     r9, [rbp+1E0h+var_210]; struct _SSDP_REQUEST *
0x18000734b  mov     edx, [rsp+2E0h+dwAddressStringLength]; unsigned int
0x18000734f  mov     r8d, r15d; unsigned int
0x180007352  mov     rcx, r13; String
0x180007355  call    ?ParseSsdpResponse@@YAHPEADKKPEAU_SSDP_REQUEST@@@Z; ParseSsdpResponse(char *,ulong,ulong,_SSDP_REQUEST *)
0x18000735a  test    eax, eax
0x18000735c  jz      loc_180007555
0x180007362  mov     rbx, [rbp+1E0h+var_1C0]
0x180007366  cmp     qword ptr [rbx+18h], 0
0x18000736b  jz      loc_180007555
0x180007371  movzx   eax, [rbp+1E0h+saAddress.sa_family]
0x180007375  cmp     ax, 17h
0x180007379  jz      loc_18000767C
0x18000737f  cmp     ax, 2
0x180007383  jnz     loc_1800079DF
0x180007389  cmp     qword ptr [rbx], 0
0x18000738d  jz      loc_18000776A
0x180007393  lea     rbx, WPP_GLOBAL_Control
0x18000739a  cmp     [rbp+1E0h+var_1E0], 0
0x18000739f  movups  xmm0, xmmword ptr [rsp+2E0h+Block+8]
0x1800073a4  movaps  [rbp+1E0h+var_1F0], xmm0
0x1800073a8  jnz     short loc_180007427
0x1800073aa  lea     rax, [rsp+2E0h+dwAddressStringLength+4]
0x1800073af  mov     [rsp+2E0h+dwAddressStringLength+4], 100h
0x1800073b7  lea     r9, [rbp+1E0h+szAddressString]; lpszAddressString
0x1800073be  mov     [rsp+2E0h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x1800073c3  xor     r8d, r8d; lpProtocolInfo
0x1800073c6  lea     rcx, [rbp+1E0h+saAddress]; lpsaAddress
0x1800073ca  mov     edx, 80h; dwAddressLength
0x1800073cf  call    cs:__imp_WSAAddressToStringA
0x1800073d6  nop     dword ptr [rax+rax+00h]
0x1800073db  cmp     eax, 0FFFFFFFFh
0x1800073de  jz      loc_180007833
0x1800073e4  mov     eax, [rsp+2E0h+dwAddressStringLength+4]
0x1800073e8  inc     eax
0x1800073ea  mov     ecx, eax; Size
0x1800073ec  mov     ebx, eax
0x1800073ee  call    cs:__imp_malloc
0x1800073f5  nop     dword ptr [rax+rax+00h]
0x1800073fa  mov     [rbp+1E0h+var_1E0], rax
0x1800073fe  mov     rcx, rax
0x180007401  test    rax, rax
0x180007404  jnz     loc_18000760F
0x18000740a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007411  lea     rax, WPP_GLOBAL_Control
0x180007418  cmp     rcx, rax
0x18000741b  jz      short loc_180007427
0x18000741d  test    byte ptr [rcx+1Ch], 8
0x180007421  jnz     loc_180007A40
0x180007427  mov     rcx, rdi; lpCriticalSection
0x18000742a  call    cs:__imp_EnterCriticalSection
0x180007431  nop     dword ptr [rax+rax+00h]
0x180007436  cmp     qword ptr [rdi+28h], 0
0x18000743b  lea     rbx, [rdi+28h]
0x18000743f  jnz     loc_1800077B0
0x180007445  mov     rcx, rdi; lpCriticalSection
0x180007448  call    cs:__imp_LeaveCriticalSection
0x18000744f  nop     dword ptr [rax+rax+00h]
0x180007454  test    r12d, r12d
0x180007457  jz      loc_1800075AA
0x18000745d  mov     rbx, cs:WPP_GLOBAL_Control
0x180007464  lea     rax, WPP_GLOBAL_Control
0x18000746b  cmp     rbx, rax
0x18000746e  jz      short loc_18000747A
0x180007470  test    byte ptr [rbx+1Ch], 8
0x180007474  jnz     loc_180007A93
0x18000747a  xor     edx, edx; Val
0x18000747c  lea     rcx, [rsp+2E0h+var_270]; void *
0x180007481  mov     r8d, 58h ; 'X'; Size
0x180007487  call    memset_0
0x18000748c  mov     rax, [rbp+1E0h+var_1C0]
0x180007490  cmp     qword ptr [rax+18h], 0
0x180007495  jz      loc_180007ACD
0x18000749b  cmp     qword ptr [rax+10h], 0
0x1800074a0  jnz     loc_180007ACD
0x1800074a6  lea     rdx, [rbp+1E0h+var_210]; struct _SSDP_REQUEST *
0x1800074aa  lea     rcx, [rsp+2E0h+var_270]; struct _SSDP_REQUEST *
0x1800074af  call    ?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z; CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)
0x1800074b4  test    eax, eax
0x1800074b6  jz      loc_180007AB4
0x1800074bc  lea     rcx, [rsp+2E0h+var_270]; struct _SSDP_REQUEST *
0x1800074c1  call    ?ConvertToAliveNotify@@YAHPEAU_SSDP_REQUEST@@@Z; ConvertToAliveNotify(_SSDP_REQUEST *)
0x1800074c6  test    eax, eax
0x1800074c8  jz      loc_180007AC3
0x1800074ce  mov     r8d, 1; int
0x1800074d4  lea     rdx, [rsp+2E0h+var_270]; struct _SSDP_REQUEST *
0x1800074d9  lea     rcx, ?s_instance@CSsdpCacheEntryManager@@0V1@A; lpCriticalSection
0x1800074e0  call    ?HrUpdateCacheList@CSsdpCacheEntryManager@@QEAAJPEAU_SSDP_REQUEST@@H@Z; CSsdpCacheEntryManager::HrUpdateCacheList(_SSDP_REQUEST *,int)
0x1800074e5  lea     rcx, [rsp+2E0h+var_270]; struct _SSDP_REQUEST *
0x1800074ea  mov     [rsp+2E0h+var_2A0], eax
0x1800074ee  mov     r15d, eax
0x1800074f1  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x1800074f6  mov     r12d, r15d
0x1800074f9  test    r15d, r15d
0x1800074fc  jns     short loc_180007571
0x1800074fe  mov     rbx, cs:WPP_GLOBAL_Control
0x180007505  lea     rax, WPP_GLOBAL_Control
0x18000750c  cmp     rbx, rax
0x18000750f  jz      short loc_180007571
0x180007511  test    byte ptr [rbx+1Ch], 1
0x180007515  jz      short loc_180007571
0x180007517  mov     rcx, [rbx+10h]
0x18000751b  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x180007522  mov     edx, 35h ; '5'
0x180007527  mov     r9d, r15d
0x18000752a  call    WPP_SF_d
0x18000752f  jmp     short loc_180007571
0x180007531  test    byte ptr [rcx+1Ch], 8
0x180007535  jz      loc_180007190
0x18000753b  mov     rcx, [rcx+10h]
0x18000753f  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x180007546  mov     edx, 2Ah ; '*'
0x18000754b  call    WPP_SF_
0x180007550  jmp     loc_180007190
0x180007555  mov     rcx, cs:WPP_GLOBAL_Control
0x18000755c  lea     rax, WPP_GLOBAL_Control
0x180007563  cmp     rcx, rax
0x180007566  jnz     loc_180007AE0
0x18000756c  mov     r12d, [rsp+2E0h+var_2A0]
0x180007571  lea     rcx, [rbp+1E0h+var_210]; struct _SSDP_REQUEST *
0x180007575  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x18000757a  test    r12d, r12d
0x18000757d  js      loc_180007968
0x180007583  xor     r12d, r12d
0x180007586  mov     rcx, r13; Block
0x180007589  call    cs:__imp_free
0x180007590  nop     dword ptr [rax+rax+00h]
0x180007595  mov     r13d, [rsp+2E0h+var_2A0]
0x18000759a  lea     r15, [rdi+40h]
0x18000759e  lea     rbx, WPP_GLOBAL_Control
0x1800075a5  jmp     loc_180007279
0x1800075aa  cmp     qword ptr [rdi+2E0h], 0
0x1800075b2  jz      short loc_18000756C
0x1800075b4  lea     rcx, stru_180044610; lpCriticalSection
0x1800075bb  call    cs:__imp_EnterCriticalSection
0x1800075c2  nop     dword ptr [rax+rax+00h]
0x1800075c7  xor     r15d, r15d
0x1800075ca  cmp     cs:qword_180044638, r15
0x1800075d1  jnz     loc_18000772E
0x1800075d7  lea     rcx, stru_180044610; lpCriticalSection
0x1800075de  call    cs:__imp_LeaveCriticalSection
0x1800075e5  nop     dword ptr [rax+rax+00h]
0x1800075ea  mov     rbx, cs:WPP_GLOBAL_Control
0x1800075f1  lea     rax, WPP_GLOBAL_Control
0x1800075f8  cmp     rbx, rax
0x1800075fb  jnz     loc_180007A5E
0x180007601  test    r15d, r15d
0x180007604  jnz     loc_18000746B
0x18000760a  jmp     loc_18000756C
0x18000760f  test    rbx, rbx
0x180007612  jz      short loc_18000765F
0x180007614  cmp     rbx, 7FFFFFFFh
0x18000761b  ja      loc_180007A38
0x180007621  mov     edx, 7FFFFFFEh
0x180007626  lea     r8, [rbp+1E0h+szAddressString]
0x18000762d  test    rdx, rdx
0x180007630  jz      short loc_18000764B
0x180007632  movzx   eax, byte ptr [r8]
0x180007636  test    al, al
0x180007638  jz      short loc_18000764B
0x18000763a  mov     [rcx], al
  ... truncated ...
```
