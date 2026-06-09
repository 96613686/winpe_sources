# SocketOpen(unsigned __int64 *,sockaddr *,ulong,ulong,int)

- ea: `0x180011f50`
- end: `0x180012750`
- name: `?SocketOpen@@YAHPEA_KPEAUsockaddr@@KKH@Z`
- size: `2048`
- prototype: `__int64 __fastcall(unsigned __int64 *, struct sockaddr *, int, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000c340`
- `0x18000dc54`

## callees

- `0x180010a30`
- `0x180011f50`
- `0x1800255a8`
- `0x180026a30`
- `0x180028000`
- `0x18002edf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001202f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001202f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011ff5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180012025`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011ff5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180012025`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180011fc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180011fc1`
- `WS2_32!WSAIoctl` at `0x1800124e8`
- `WS2_32!WSAIoctl` at `0x1800124e8`
- `WS2_32!__imp_bind` at `0x180012125`
- `WS2_32!__imp_bind` at `0x180012125`
- `WS2_32!__imp_closesocket` at `0x1800122b9`
- `WS2_32!__imp_closesocket` at `0x1800122b9`
- `WS2_32!__imp_inet_addr` at `0x18001240b`
- `WS2_32!__imp_inet_addr` at `0x18001240b`
- `WS2_32!__imp_setsockopt` at `0x1800120ee`
- `WS2_32!__imp_setsockopt` at `0x180012185`
- `WS2_32!__imp_setsockopt` at `0x1800121b7`
- `WS2_32!__imp_setsockopt` at `0x1800121fa`
- `WS2_32!__imp_setsockopt` at `0x180012327`
- `WS2_32!__imp_setsockopt` at `0x180012381`
- `WS2_32!__imp_setsockopt` at `0x1800120ee`
- `WS2_32!__imp_setsockopt` at `0x180012185`
- `WS2_32!__imp_setsockopt` at `0x1800121b7`
- `WS2_32!__imp_setsockopt` at `0x1800121fa`
- `WS2_32!__imp_setsockopt` at `0x180012327`
- `WS2_32!__imp_setsockopt` at `0x180012381`
- `WS2_32!__imp_socket` at `0x180012099`
- `WS2_32!__imp_socket` at `0x180012099`
- `WS2_32!__imp_WSAGetLastError` at `0x1800123a9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800123ed`
- `WS2_32!__imp_WSAGetLastError` at `0x180012474`
- `WS2_32!__imp_WSAGetLastError` at `0x180012511`
- `WS2_32!__imp_WSAGetLastError` at `0x180012562`
- `WS2_32!__imp_WSAGetLastError` at `0x180012593`
- `WS2_32!__imp_WSAGetLastError` at `0x1800125f8`
- `WS2_32!__imp_WSAGetLastError` at `0x180012664`
- `WS2_32!__imp_WSAGetLastError` at `0x1800126b9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800123a9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800123ed`
- `WS2_32!__imp_WSAGetLastError` at `0x180012474`
- `WS2_32!__imp_WSAGetLastError` at `0x180012511`
- `WS2_32!__imp_WSAGetLastError` at `0x180012562`
- `WS2_32!__imp_WSAGetLastError` at `0x180012593`
- `WS2_32!__imp_WSAGetLastError` at `0x1800125f8`
- `WS2_32!__imp_WSAGetLastError` at `0x180012664`
- `WS2_32!__imp_WSAGetLastError` at `0x1800126b9`

## string_xrefs

- `0x180011fb3`: `SYSTEM\CurrentControlSet\Services\SSDPSRV\Parameters`

## pseudocode

```c
__int64 __fastcall SocketOpen(unsigned __int64 *a1, struct sockaddr *a2, int a3, unsigned int a4, int a5)
{
  __int64 v5; // r14
  __int64 v8; // r9
  LPCSTR v9; // rcx
  __int64 v10; // r9
  SOCKET v11; // rax
  SOCKET v12; // rbx
  int v13; // r12d
  LPCSTR v14; // rcx
  int v15; // r8d
  LPCSTR v16; // rcx
  int v17; // r15d
  unsigned int sa_family; // eax
  int v19; // edx
  int v20; // edx
  __int64 result; // rax
  const char *v22; // r9
  int v23; // edx
  __int128 v24; // xmm0
  unsigned int v25; // eax
  __int64 v26; // rdx
  int v27; // eax
  __int64 v28; // r9
  __int64 v29; // rdx
  unsigned int Error; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-71h]
  DWORD cbData; // [rsp+50h] [rbp-41h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-3Dh] BYREF
  BYTE v34[4]; // [rsp+58h] [rbp-39h] BYREF
  char optval[8]; // [rsp+60h] [rbp-31h] BYREF
  char v36[4]; // [rsp+68h] [rbp-29h] BYREF
  DWORD cbBytesReturned[2]; // [rsp+70h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-19h] BYREF
  char v39[16]; // [rsp+80h] [rbp-11h] BYREF
  int v40; // [rsp+90h] [rbp-1h]

  v5 = a4;
  *(_DWORD *)optval = a3;
  *(_DWORD *)Data = 4;
  *(_DWORD *)v34 = 1;
  hKey = 0;
  if ( a4 >= 6 )
    return 0;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "SYSTEM\\CurrentControlSet\\Services\\SSDPSRV\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    RegQueryValueExA(hKey, "TTL", 0, 0, Data, &cbData);
    cbData = 4;
    RegQueryValueExA(hKey, "ReceiveScope", 0, 0, v34, &cbData);
    RegCloseKey(hKey);
  }
  v8 = *(unsigned int *)Data;
  if ( *(_DWORD *)Data <= 1u )
  {
    v8 = 1;
LABEL_82:
    *(_DWORD *)Data = v8;
    goto LABEL_6;
  }
  if ( *(_DWORD *)Data >= 0xFFu )
  {
    v8 = 255;
    goto LABEL_82;
  }
LABEL_6:
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids, v8);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = *(unsigned int *)v34;
  if ( *(_DWORD *)v34 > 3u )
  {
    v10 = 1;
    *(_DWORD *)v34 = 1;
  }
  dword_18004121C = v10;
  if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x2000) != 0 )
    WPP_SF_d(*((_QWORD *)v9 + 2), 16, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids, v10);
  v11 = socket(a2->sa_family, 2, 0);
  v12 = v11;
  if ( v11 == -1 )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      Error = WSAGetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids, Error);
    }
    return 0;
  }
  v13 = 20;
  cbData = 1;
  if ( a5 )
  {
    if ( setsockopt(v11, 0xFFFF, 4, (const char *)&cbData, 4) )
    {
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_44;
      sa_family = WSAGetLastError();
      v16 = WPP_GLOBAL_Control;
      v26 = 18;
      goto LABEL_102;
    }
    goto LABEL_15;
  }
  if ( !setsockopt(v11, 0xFFFF, -5, (const char *)&cbData, 4) )
  {
LABEL_15:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
    goto LABEL_17;
  if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    v25 = WSAGetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids, v25);
    goto LABEL_15;
  }
LABEL_16:
  if ( v14 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x2000) != 0 )
    WPP_SF_d(*((_QWORD *)v14 + 2), 20, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids, (unsigned int)v12);
LABEL_17:
  v15 = 28;
  if ( a2->sa_family != 23 )
    v15 = 16;
  if ( bind(v12, a2, v15) == -1 )
  {
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_44;
    sa_family = WSAGetLastError();
    v16 = WPP_GLOBAL_Control;
    v26 = 21;
    goto LABEL_102;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids);
    v16 = WPP_GLOBAL_Control;
  }
  v17 = 41;
  if ( a5 )
  {
    *(_QWORD *)cbBytesReturned = 0;
    v40 = 0;
    sa_family = a2->sa_family;
    *(_OWORD *)v39 = 0;
    if ( sa_family == 2 )
    {
      cbBytesReturned[0] = inet_addr("239.255.255.250");
      v23 = 0;
      v22 = (const char *)cbBytesReturned;
      cbBytesReturned[1] = *(_DWORD *)optval;
      v13 = 8;
    }
    else
    {
      if ( sa_family != 23 )
      {
        if ( v16 == (LPCSTR)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
          goto LABEL_44;
        v26 = 23;
        goto LABEL_102;
      }
      v22 = v39;
      v23 = 41;
      v24 = *(_OWORD *)&(&in6SSDPAddresses)[2 * v5];
      v40 = *(_DWORD *)optval;
      *(_OWORD *)v39 = v24;
    }
    if ( setsockopt(v12, v23, 12, v22, v13) == -1 )
    {
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_44;
      sa_family = WSAGetLastError();
      v16 = WPP_GLOBAL_Control;
      v26 = 24;
      goto LABEL_102;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
  }
  sa_family = a2->sa_family;
  if ( sa_family == 2 )
  {
    v19 = 0;
  }
  else
  {
    if ( sa_family != 23 )
    {
      if ( v16 == (LPCSTR)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
        goto LABEL_44;
      v26 = 26;
      goto LABEL_102;
    }
    v19 = 41;
  }
  if ( setsockopt(v12, v19, 9, optval, 4) == -1 )
  {
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_44;
    sa_family = WSAGetLastError();
    v16 = WPP_GLOBAL_Control;
    v26 = 27;
    goto LABEL_102;
  }
  sa_family = a2->sa_family;
  if ( sa_family == 2 )
  {
    v20 = 0;
  }
  else
  {
    if ( sa_family != 23 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_44;
      v26 = 28;
      goto LABEL_102;
    }
    v20 = 41;
  }
  if ( setsockopt(v12, v20, 10, (const char *)Data, 4) == -1 )
  {
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_44;
    v27 = WSAGetLastError();
    v28 = *(unsigned int *)Data;
    v29 = 29;
LABEL_72:
    LODWORD(phkResult) = v27;
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids, v28, phkResult);
LABEL_44:
    closesocket(v12);
    result = 0;
    *a1 = -1;
    return result;
  }
  sa_family = a2->sa_family;
  *(_DWORD *)v36 = 1;
  if ( sa_family != 2 )
  {
    if ( sa_family == 23 )
      goto LABEL_32;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_44;
    v26 = 30;
LABEL_102:
    WPP_SF_d(*((_QWORD *)v16 + 2), v26, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids, sa_family);
    goto LABEL_44;
  }
  v17 = 0;
LABEL_32:
  if ( setsockopt(v12, v17, 19, v36, 4) == -1 )
  {
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_44;
    v27 = WSAGetLastError();
    v28 = *(unsigned int *)v36;
    v29 = 31;
    goto LABEL_72;
  }
  if ( !(unsigned int)AddressIsLoopback(a2) )
  {
    cbData = 0;
    cbBytesReturned[0] = 0;
    if ( WSAIoctl(v12, 0x88000009, &cbData, 4u, 0, 0, cbBytesReturned, 0, 0) == -1 )
    {
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_44;
      v27 = WSAGetLastError();
      v28 = cbData;
      v29 = 32;
      goto LABEL_72;
    }
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids);
  *a1 = v12;
  return 1;
}

```

## disassembly

```asm
0x180011f50  push    rbp
0x180011f52  push    rbx
0x180011f53  push    rdi
0x180011f54  push    r13
0x180011f56  push    r14
0x180011f58  push    r15
0x180011f5a  lea     rbp, [rsp-27h]
0x180011f5f  sub     rsp, 0B8h
0x180011f66  mov     rax, cs:__security_cookie
0x180011f6d  xor     rax, rsp
0x180011f70  mov     [rbp+4Fh+var_48], rax
0x180011f74  mov     r14d, r9d
0x180011f77  mov     rdi, rdx
0x180011f7a  mov     dword ptr [rbp+4Fh+optval], r8d
0x180011f7e  mov     r13, rcx
0x180011f81  mov     dword ptr [rbp+4Fh+Data], 4
0x180011f88  mov     dword ptr [rbp+4Fh+var_88], 1
0x180011f8f  mov     [rbp+4Fh+hKey], 0
0x180011f97  cmp     r9d, 6
0x180011f9b  jnb     loc_180012278
0x180011fa1  lea     rax, [rbp+4Fh+hKey]
0x180011fa5  mov     r9d, 20019h; samDesired
0x180011fab  xor     r8d, r8d; ulOptions
0x180011fae  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180011fb3  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\SS"...
0x180011fba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011fc1  call    cs:__imp_RegOpenKeyExA
0x180011fc7  test    eax, eax
0x180011fc9  jnz     short loc_180012035
0x180011fcb  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180011fcf  lea     rax, [rbp+4Fh+cbData]
0x180011fd3  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180011fd8  lea     rdx, aTtl; "TTL"
0x180011fdf  lea     rax, [rbp+4Fh+Data]
0x180011fe3  mov     [rbp+4Fh+cbData], 4
0x180011fea  xor     r9d, r9d; lpType
0x180011fed  mov     [rsp+0E0h+phkResult], rax; lpData
0x180011ff2  xor     r8d, r8d; lpReserved
0x180011ff5  call    cs:__imp_RegQueryValueExA
0x180011ffb  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180011fff  lea     rax, [rbp+4Fh+cbData]
0x180012003  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180012008  lea     rdx, aReceivescope; "ReceiveScope"
0x18001200f  lea     rax, [rbp+4Fh+var_88]
0x180012013  mov     [rbp+4Fh+cbData], 4
0x18001201a  xor     r9d, r9d; lpType
0x18001201d  mov     [rsp+0E0h+phkResult], rax; lpData
0x180012022  xor     r8d, r8d; lpReserved
0x180012025  call    cs:__imp_RegQueryValueExA
0x18001202b  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18001202f  call    cs:__imp_RegCloseKey
0x180012035  mov     r9d, dword ptr [rbp+4Fh+Data]
0x180012039  cmp     r9d, 1
0x18001203d  jbe     loc_1800125A7
0x180012043  cmp     r9d, 0FFh
0x18001204a  jnb     loc_1800125AF
0x180012050  mov     rcx, cs:WPP_GLOBAL_Control
0x180012057  lea     r15, WPP_GLOBAL_Control
0x18001205e  cmp     rcx, r15
0x180012061  jz      short loc_180012070
0x180012063  test    dword ptr [rcx+1Ch], 2000h
0x18001206a  jnz     loc_1800125BE
0x180012070  mov     r9d, dword ptr [rbp+4Fh+var_88]
0x180012074  cmp     r9d, 3
0x180012078  ja      loc_1800125DF
0x18001207e  mov     cs:dword_18004121C, r9d
0x180012085  cmp     rcx, r15
0x180012088  jnz     loc_18001242B
0x18001208e  movzx   ecx, word ptr [rdi]; af
0x180012091  xor     r8d, r8d; protocol
0x180012094  mov     edx, 2; type
0x180012099  call    cs:__imp_socket
0x18001209f  mov     rbx, rax
0x1800120a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800120a6  jz      loc_180012268
0x1800120ac  mov     [rsp+0E0h+var_30], rsi
0x1800120b4  lea     r9, [rbp+4Fh+cbData]; optval
0x1800120b8  mov     esi, [rbp+4Fh+arg_20]
0x1800120bb  mov     edx, 0FFFFh; level
0x1800120c0  mov     [rsp+0E0h+var_38], r12
0x1800120c8  mov     r12d, 14h
0x1800120ce  mov     [rbp+4Fh+cbData], 1
0x1800120d5  mov     rcx, rax; s
0x1800120d8  mov     dword ptr [rsp+0E0h+phkResult], 4; optlen
0x1800120e0  test    esi, esi
0x1800120e2  jz      loc_18001237B
0x1800120e8  mov     r8d, 4; optname
0x1800120ee  call    cs:__imp_setsockopt
0x1800120f4  test    eax, eax
0x1800120f6  jnz     loc_180012548
0x1800120fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012103  cmp     rcx, r15
0x180012106  jnz     loc_18001227C
0x18001210c  cmp     word ptr [rdi], 17h
0x180012110  mov     r8d, 1Ch
0x180012116  mov     eax, 10h
0x18001211b  mov     rdx, rdi; name
0x18001211e  cmovnz  r8d, eax; namelen
0x180012122  mov     rcx, rbx; s
0x180012125  call    cs:__imp_bind
0x18001212b  cmp     eax, 0FFFFFFFFh
0x18001212e  jz      loc_1800123D3
0x180012134  mov     rcx, cs:WPP_GLOBAL_Control
0x18001213b  cmp     rcx, r15
0x18001213e  jz      short loc_18001214D
0x180012140  test    dword ptr [rcx+1Ch], 2000h
0x180012147  jnz     loc_180012622
0x18001214d  mov     r15d, 29h ; ')'
0x180012153  test    esi, esi
0x180012155  jnz     loc_1800122CE
0x18001215b  lea     rsi, WPP_GLOBAL_Control
0x180012162  movzx   eax, word ptr [rdi]
0x180012165  cmp     eax, 2
0x180012168  jnz     loc_1800122A4
0x18001216e  xor     edx, edx; level
0x180012170  lea     r9, [rbp+4Fh+optval]; optval
0x180012174  mov     dword ptr [rsp+0E0h+phkResult], 4; optlen
0x18001217c  mov     r8d, 9; optname
0x180012182  mov     rcx, rbx; s
0x180012185  call    cs:__imp_setsockopt
0x18001218b  cmp     eax, 0FFFFFFFFh
0x18001218e  jz      loc_18001245A
0x180012194  movzx   eax, word ptr [rdi]
0x180012197  cmp     eax, 2
0x18001219a  jnz     loc_18001248B
0x1800121a0  xor     edx, edx; level
0x1800121a2  lea     r9, [rbp+4Fh+Data]; optval
0x1800121a6  mov     dword ptr [rsp+0E0h+phkResult], 4; optlen
0x1800121ae  mov     r8d, 0Ah; optname
0x1800121b4  mov     rcx, rbx; s
0x1800121b7  call    cs:__imp_setsockopt
0x1800121bd  cmp     eax, 0FFFFFFFFh
0x1800121c0  jz      loc_18001269F
0x1800121c6  movzx   eax, word ptr [rdi]
0x1800121c9  mov     dword ptr [rbp+4Fh+var_78], 1
0x1800121d0  cmp     eax, 2
0x1800121d3  jz      loc_180012540
0x1800121d9  cmp     eax, 17h
0x1800121dc  jnz     loc_1800126E7
0x1800121e2  lea     r9, [rbp+4Fh+var_78]; optval
0x1800121e6  mov     dword ptr [rsp+0E0h+phkResult], 4; optlen
0x1800121ee  mov     r8d, 13h; optname
0x1800121f4  mov     edx, r15d; level
0x1800121f7  mov     rcx, rbx; s
0x1800121fa  call    cs:__imp_setsockopt
0x180012200  cmp     eax, 0FFFFFFFFh
0x180012203  jz      loc_180012579
0x180012209  mov     rcx, rdi; struct sockaddr *
0x18001220c  call    ?AddressIsLoopback@@YAHPEBUsockaddr@@@Z; AddressIsLoopback(sockaddr const *)
0x180012211  test    eax, eax
0x180012213  jz      loc_18001249C
0x180012219  mov     rcx, cs:WPP_GLOBAL_Control
0x180012220  cmp     rcx, rsi
0x180012223  jz      short loc_180012232
0x180012225  test    dword ptr [rcx+1Ch], 2000h
0x18001222c  jnz     loc_1800126CD
0x180012232  mov     [r13+0], rbx
0x180012236  mov     eax, 1
0x18001223b  mov     rsi, [rsp+0E0h+var_30]
0x180012243  mov     r12, [rsp+0E0h+var_38]
0x18001224b  mov     rcx, [rbp+4Fh+var_48]
0x18001224f  xor     rcx, rsp; StackCookie
0x180012252  call    __security_check_cookie
0x180012257  add     rsp, 0B8h
0x18001225e  pop     r15
0x180012260  pop     r14
0x180012262  pop     r13
0x180012264  pop     rdi
0x180012265  pop     rbx
0x180012266  pop     rbp
0x180012267  retn
0x180012268  mov     rax, cs:WPP_GLOBAL_Control
0x18001226f  cmp     rax, r15
0x180012272  jnz     loc_1800125EE
0x180012278  xor     eax, eax
0x18001227a  jmp     short loc_18001224B
0x18001227c  test    dword ptr [rcx+1Ch], 2000h
0x180012283  jz      loc_18001210C
0x180012289  mov     rcx, [rcx+10h]
0x18001228d  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x180012294  mov     r9d, ebx
0x180012297  mov     edx, r12d
0x18001229a  call    WPP_SF_d
0x18001229f  jmp     loc_18001210C
0x1800122a4  cmp     eax, 17h
0x1800122a7  jz      loc_180012452
0x1800122ad  cmp     rcx, rsi
0x1800122b0  jnz     loc_180012729
0x1800122b6  mov     rcx, rbx; s
0x1800122b9  call    cs:__imp_closesocket
0x1800122bf  xor     eax, eax
0x1800122c1  mov     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x1800122c9  jmp     loc_18001223B
0x1800122ce  xor     eax, eax
0x1800122d0  mov     qword ptr [rbp+4Fh+cbBytesReturned], 0
0x1800122d8  mov     [rbp+4Fh+var_50], eax
0x1800122db  xorps   xmm0, xmm0
0x1800122de  movzx   eax, word ptr [rdi]
0x1800122e1  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x1800122e5  cmp     eax, 2
0x1800122e8  jz      loc_180012404
0x1800122ee  cmp     eax, 17h
0x1800122f1  jnz     loc_18001267B
0x1800122f7  mov     rax, r14
0x1800122fa  lea     rcx, ?in6SSDPAddresses@@3PAUin6_addr@@A; in6_addr near * in6SSDPAddresses
0x180012301  add     rax, rax
0x180012304  lea     r9, [rbp+4Fh+var_60]; optval
0x180012308  mov     edx, r15d; level
0x18001230b  movups  xmm0, xmmword ptr [rcx+rax*8]
0x18001230f  mov     eax, dword ptr [rbp+4Fh+optval]
0x180012312  mov     [rbp+4Fh+var_50], eax
0x180012315  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x180012319  mov     r8d, 0Ch; optname
0x18001231f  mov     dword ptr [rsp+0E0h+phkResult], r12d; optlen
0x180012324  mov     rcx, rbx; s
0x180012327  call    cs:__imp_setsockopt
0x18001232d  cmp     eax, 0FFFFFFFFh
0x180012330  jz      loc_180012643
0x180012336  mov     rcx, cs:WPP_GLOBAL_Control
0x18001233d  lea     rsi, WPP_GLOBAL_Control
0x180012344  cmp     rcx, rsi
0x180012347  jz      loc_180012162
0x18001234d  test    dword ptr [rcx+1Ch], 2000h
0x180012354  jz      loc_180012162
0x18001235a  mov     rcx, [rcx+10h]
0x18001235e  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x180012365  mov     edx, 19h
0x18001236a  call    WPP_SF_
0x18001236f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012376  jmp     loc_180012162
0x18001237b  mov     r8d, 0FFFFFFFBh; optname
0x180012381  call    cs:__imp_setsockopt
0x180012387  test    eax, eax
0x180012389  jz      loc_1800120FC
0x18001238f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012396  cmp     rcx, r15
0x180012399  jz      loc_18001210C
0x18001239f  test    byte ptr [rcx+1Ch], 1
0x1800123a3  jz      loc_180012103
0x1800123a9  call    cs:__imp_WSAGetLastError
0x1800123af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123b6  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x1800123bd  mov     edx, 13h
0x1800123c2  mov     r9d, eax
0x1800123c5  mov     rcx, [rcx+10h]
0x1800123c9  call    WPP_SF_d
0x1800123ce  jmp     loc_1800120FC
0x1800123d3  mov     rax, cs:WPP_GLOBAL_Control
0x1800123da  cmp     rax, r15
0x1800123dd  jz      loc_1800122B6
0x1800123e3  test    byte ptr [rax+1Ch], 1
0x1800123e7  jz      loc_1800122B6
0x1800123ed  call    cs:__imp_WSAGetLastError
0x1800123f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123fa  mov     edx, 15h
0x1800123ff  jmp     loc_180012738
0x180012404  lea     rcx, String; "239.255.255.250"
0x18001240b  call    cs:__imp_inet_addr
0x180012411  mov     [rbp+4Fh+cbBytesReturned], eax
0x180012414  xor     edx, edx
0x180012416  mov     eax, dword ptr [rbp+4Fh+optval]
0x180012419  lea     r9, [rbp+4Fh+cbBytesReturned]
0x18001241d  mov     [rbp+4Fh+cbBytesReturned+4], eax
0x180012420  mov     r12d, 8
0x180012426  jmp     loc_180012319
0x18001242b  test    dword ptr [rcx+1Ch], 2000h
0x180012432  jz      loc_18001208E
0x180012438  mov     rcx, [rcx+10h]
0x18001243c  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x180012443  mov     edx, 10h
0x180012448  call    WPP_SF_d
0x18001244d  jmp     loc_18001208E
0x180012452  mov     edx, r15d
0x180012455  jmp     loc_180012170
0x18001245a  mov     rax, cs:WPP_GLOBAL_Control
0x180012461  cmp     rax, rsi
0x180012464  jz      loc_1800122B6
0x18001246a  test    byte ptr [rax+1Ch], 1
0x18001246e  jz      loc_1800122B6
0x180012474  call    cs:__imp_WSAGetLastError
0x18001247a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012481  mov     edx, 1Bh
0x180012486  jmp     loc_180012738
0x18001248b  cmp     eax, 17h
0x18001248e  jnz     loc_180012708
0x180012494  mov     edx, r15d
0x180012497  jmp     loc_1800121A2
0x18001249c  mov     [rsp+0E0h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800124a5  lea     rax, [rbp+4Fh+cbBytesReturned]
0x1800124a9  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x1800124b2  lea     r8, [rbp+4Fh+cbData]; lpvInBuffer
0x1800124b6  mov     [rsp+0E0h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800124bb  mov     r9d, 4; cbInBuffer
0x1800124c1  mov     dword ptr [rsp+0E0h+lpcbData], 0; cbOutBuffer
0x1800124c9  mov     edx, 88000009h; dwIoControlCode
0x1800124ce  mov     rcx, rbx; s
0x1800124d1  mov     [rsp+0E0h+phkResult], 0; lpvOutBuffer
0x1800124da  mov     [rbp+4Fh+cbData], 0
0x1800124e1  mov     [rbp+4Fh+cbBytesReturned], 0
0x1800124e8  call    cs:__imp_WSAIoctl
  ... truncated ...
```
