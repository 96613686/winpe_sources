# SocketOpen(unsigned __int64 *,sockaddr *,ulong,ulong,int)

- ea: `0x180013480`
- end: `0x180013d11`
- name: `?SocketOpen@@YAHPEA_KPEAUsockaddr@@KKH@Z`
- size: `2193`
- prototype: `int(unsigned __int64 *, struct sockaddr *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000eff4`
- `0x180013efc`

## callees

- `0x180011ec0`
- `0x180013480`
- `0x1800271fc`
- `0x1800287d0`
- `0x180029df0`
- `0x180031018`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013571`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001352b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180013561`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001352b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180013561`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800134f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800134f1`
- `WS2_32!WSAIoctl` at `0x180013a7f`
- `WS2_32!WSAIoctl` at `0x180013a7f`
- `WS2_32!__imp_bind` at `0x180013679`
- `WS2_32!__imp_bind` at `0x180013679`
- `WS2_32!__imp_closesocket` at `0x180013826`
- `WS2_32!__imp_closesocket` at `0x180013826`
- `WS2_32!__imp_inet_addr` at `0x180013996`
- `WS2_32!__imp_inet_addr` at `0x180013996`
- `WS2_32!__imp_setsockopt` at `0x18001363c`
- `WS2_32!__imp_setsockopt` at `0x1800136df`
- `WS2_32!__imp_setsockopt` at `0x180013717`
- `WS2_32!__imp_setsockopt` at `0x180013760`
- `WS2_32!__imp_setsockopt` at `0x18001389a`
- `WS2_32!__imp_setsockopt` at `0x1800138fa`
- `WS2_32!__imp_setsockopt` at `0x18001363c`
- `WS2_32!__imp_setsockopt` at `0x1800136df`
- `WS2_32!__imp_setsockopt` at `0x180013717`
- `WS2_32!__imp_setsockopt` at `0x180013760`
- `WS2_32!__imp_setsockopt` at `0x18001389a`
- `WS2_32!__imp_setsockopt` at `0x1800138fa`
- `WS2_32!__imp_socket` at `0x1800135e1`
- `WS2_32!__imp_socket` at `0x1800135e1`
- `WS2_32!__imp_WSAGetLastError` at `0x180013928`
- `WS2_32!__imp_WSAGetLastError` at `0x180013972`
- `WS2_32!__imp_WSAGetLastError` at `0x180013a05`
- `WS2_32!__imp_WSAGetLastError` at `0x180013aae`
- `WS2_32!__imp_WSAGetLastError` at `0x180013b05`
- `WS2_32!__imp_WSAGetLastError` at `0x180013b3c`
- `WS2_32!__imp_WSAGetLastError` at `0x180013ba7`
- `WS2_32!__imp_WSAGetLastError` at `0x180013c19`
- `WS2_32!__imp_WSAGetLastError` at `0x180013c74`
- `WS2_32!__imp_WSAGetLastError` at `0x180013928`
- `WS2_32!__imp_WSAGetLastError` at `0x180013972`
- `WS2_32!__imp_WSAGetLastError` at `0x180013a05`
- `WS2_32!__imp_WSAGetLastError` at `0x180013aae`
- `WS2_32!__imp_WSAGetLastError` at `0x180013b05`
- `WS2_32!__imp_WSAGetLastError` at `0x180013b3c`
- `WS2_32!__imp_WSAGetLastError` at `0x180013ba7`
- `WS2_32!__imp_WSAGetLastError` at `0x180013c19`
- `WS2_32!__imp_WSAGetLastError` at `0x180013c74`

## string_xrefs

- `0x1800134e3`: `SYSTEM\CurrentControlSet\Services\SSDPSRV\Parameters`

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
  DWORD cbData; // [rsp+50h] [rbp-41h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-3Dh] BYREF
  BYTE v33[4]; // [rsp+58h] [rbp-39h] BYREF
  char optval[8]; // [rsp+60h] [rbp-31h] BYREF
  char v35[4]; // [rsp+68h] [rbp-29h] BYREF
  DWORD cbBytesReturned[2]; // [rsp+70h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-19h] BYREF
  char v38[16]; // [rsp+80h] [rbp-11h] BYREF
  int v39; // [rsp+90h] [rbp-1h]

  v5 = a4;
  *(_DWORD *)optval = a3;
  *(_DWORD *)Data = 4;
  *(_DWORD *)v33 = 1;
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
    RegQueryValueExA(hKey, "ReceiveScope", 0, 0, v33, &cbData);
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
  v10 = *(unsigned int *)v33;
  if ( *(_DWORD *)v33 > 3u )
  {
    v10 = 1;
    *(_DWORD *)v33 = 1;
  }
  dword_18004431C = v10;
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
    v39 = 0;
    sa_family = a2->sa_family;
    *(_OWORD *)v38 = 0;
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
      v22 = v38;
      v23 = 41;
      v24 = *(_OWORD *)&(&in6SSDPAddresses)[2 * v5];
      v39 = *(_DWORD *)optval;
      *(_OWORD *)v38 = v24;
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
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids, v28, v27);
LABEL_44:
    closesocket(v12);
    result = 0;
    *a1 = -1;
    return result;
  }
  sa_family = a2->sa_family;
  *(_DWORD *)v35 = 1;
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
  if ( setsockopt(v12, v17, 19, v35, 4) == -1 )
  {
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_44;
    v27 = WSAGetLastError();
    v28 = *(unsigned int *)v35;
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
0x180013480  push    rbp
0x180013482  push    rbx
0x180013483  push    rdi
0x180013484  push    r13
0x180013486  push    r14
0x180013488  push    r15
0x18001348a  lea     rbp, [rsp-27h]
0x18001348f  sub     rsp, 0B8h
0x180013496  mov     rax, cs:__security_cookie
0x18001349d  xor     rax, rsp
0x1800134a0  mov     [rbp+4Fh+var_48], rax
0x1800134a4  mov     r14d, r9d
0x1800134a7  mov     rdi, rdx
0x1800134aa  mov     dword ptr [rbp+4Fh+optval], r8d
0x1800134ae  mov     r13, rcx
0x1800134b1  mov     dword ptr [rbp+4Fh+Data], 4
0x1800134b8  mov     dword ptr [rbp+4Fh+var_88], 1
0x1800134bf  mov     [rbp+4Fh+hKey], 0
0x1800134c7  cmp     r9d, 6
0x1800134cb  jnb     loc_1800137E5
0x1800134d1  lea     rax, [rbp+4Fh+hKey]
0x1800134d5  mov     r9d, 20019h; samDesired
0x1800134db  xor     r8d, r8d; ulOptions
0x1800134de  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800134e3  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\SS"...
0x1800134ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800134f1  call    cs:__imp_RegOpenKeyExA
0x1800134f8  nop     dword ptr [rax+rax+00h]
0x1800134fd  test    eax, eax
0x1800134ff  jnz     short loc_18001357D
0x180013501  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180013505  lea     rax, [rbp+4Fh+cbData]
0x180013509  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x18001350e  lea     rdx, aTtl; "TTL"
0x180013515  lea     rax, [rbp+4Fh+Data]
0x180013519  mov     [rbp+4Fh+cbData], 4
0x180013520  xor     r9d, r9d; lpType
0x180013523  mov     [rsp+0E0h+phkResult], rax; lpData
0x180013528  xor     r8d, r8d; lpReserved
0x18001352b  call    cs:__imp_RegQueryValueExA
0x180013532  nop     dword ptr [rax+rax+00h]
0x180013537  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18001353b  lea     rax, [rbp+4Fh+cbData]
0x18001353f  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180013544  lea     rdx, aReceivescope; "ReceiveScope"
0x18001354b  lea     rax, [rbp+4Fh+var_88]
0x18001354f  mov     [rbp+4Fh+cbData], 4
0x180013556  xor     r9d, r9d; lpType
0x180013559  mov     [rsp+0E0h+phkResult], rax; lpData
0x18001355e  xor     r8d, r8d; lpReserved
0x180013561  call    cs:__imp_RegQueryValueExA
0x180013568  nop     dword ptr [rax+rax+00h]
0x18001356d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180013571  call    cs:__imp_RegCloseKey
0x180013578  nop     dword ptr [rax+rax+00h]
0x18001357d  mov     r9d, dword ptr [rbp+4Fh+Data]
0x180013581  cmp     r9d, 1
0x180013585  jbe     loc_180013B56
0x18001358b  cmp     r9d, 0FFh
0x180013592  jnb     loc_180013B5E
0x180013598  mov     rcx, cs:WPP_GLOBAL_Control
0x18001359f  lea     r15, WPP_GLOBAL_Control
0x1800135a6  cmp     rcx, r15
0x1800135a9  jz      short loc_1800135B8
0x1800135ab  test    dword ptr [rcx+1Ch], 2000h
0x1800135b2  jnz     loc_180013B6D
0x1800135b8  mov     r9d, dword ptr [rbp+4Fh+var_88]
0x1800135bc  cmp     r9d, 3
0x1800135c0  ja      loc_180013B8E
0x1800135c6  mov     cs:dword_18004431C, r9d
0x1800135cd  cmp     rcx, r15
0x1800135d0  jnz     loc_1800139BC
0x1800135d6  movzx   ecx, word ptr [rdi]; af
0x1800135d9  xor     r8d, r8d; protocol
0x1800135dc  mov     edx, 2; type
0x1800135e1  call    cs:__imp_socket
0x1800135e8  nop     dword ptr [rax+rax+00h]
0x1800135ed  mov     rbx, rax
0x1800135f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800135f4  jz      loc_1800137D5
0x1800135fa  mov     [rsp+0E0h+var_30], rsi
0x180013602  lea     r9, [rbp+4Fh+cbData]; optval
0x180013606  mov     esi, [rbp+4Fh+arg_20]
0x180013609  mov     edx, 0FFFFh; level
0x18001360e  mov     [rsp+0E0h+var_38], r12
0x180013616  mov     r12d, 14h
0x18001361c  mov     [rbp+4Fh+cbData], 1
0x180013623  mov     rcx, rax; s
0x180013626  mov     dword ptr [rsp+0E0h+phkResult], 4; optlen
0x18001362e  test    esi, esi
0x180013630  jz      loc_1800138F4
0x180013636  mov     r8d, 4; optname
0x18001363c  call    cs:__imp_setsockopt
0x180013643  nop     dword ptr [rax+rax+00h]
0x180013648  test    eax, eax
0x18001364a  jnz     loc_180013AEB
0x180013650  mov     rcx, cs:WPP_GLOBAL_Control
0x180013657  cmp     rcx, r15
0x18001365a  jnz     loc_1800137E9
0x180013660  cmp     word ptr [rdi], 17h
0x180013664  mov     r8d, 1Ch
0x18001366a  mov     eax, 10h
0x18001366f  mov     rdx, rdi; name
0x180013672  cmovnz  r8d, eax; namelen
0x180013676  mov     rcx, rbx; s
0x180013679  call    cs:__imp_bind
0x180013680  nop     dword ptr [rax+rax+00h]
0x180013685  cmp     eax, 0FFFFFFFFh
0x180013688  jz      loc_180013958
0x18001368e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013695  cmp     rcx, r15
0x180013698  jz      short loc_1800136A7
0x18001369a  test    dword ptr [rcx+1Ch], 2000h
0x1800136a1  jnz     loc_180013BD7
0x1800136a7  mov     r15d, 29h ; ')'
0x1800136ad  test    esi, esi
0x1800136af  jnz     loc_180013841
0x1800136b5  lea     rsi, WPP_GLOBAL_Control
0x1800136bc  movzx   eax, word ptr [rdi]
0x1800136bf  cmp     eax, 2
0x1800136c2  jnz     loc_180013811
0x1800136c8  xor     edx, edx; level
0x1800136ca  lea     r9, [rbp+4Fh+optval]; optval
0x1800136ce  mov     dword ptr [rsp+0E0h+phkResult], 4; optlen
0x1800136d6  mov     r8d, 9; optname
0x1800136dc  mov     rcx, rbx; s
0x1800136df  call    cs:__imp_setsockopt
0x1800136e6  nop     dword ptr [rax+rax+00h]
0x1800136eb  cmp     eax, 0FFFFFFFFh
0x1800136ee  jz      loc_1800139EB
0x1800136f4  movzx   eax, word ptr [rdi]
0x1800136f7  cmp     eax, 2
0x1800136fa  jnz     loc_180013A22
0x180013700  xor     edx, edx; level
0x180013702  lea     r9, [rbp+4Fh+Data]; optval
0x180013706  mov     dword ptr [rsp+0E0h+phkResult], 4; optlen
0x18001370e  mov     r8d, 0Ah; optname
0x180013714  mov     rcx, rbx; s
0x180013717  call    cs:__imp_setsockopt
0x18001371e  nop     dword ptr [rax+rax+00h]
0x180013723  cmp     eax, 0FFFFFFFFh
0x180013726  jz      loc_180013C5A
0x18001372c  movzx   eax, word ptr [rdi]
0x18001372f  mov     dword ptr [rbp+4Fh+var_78], 1
0x180013736  cmp     eax, 2
0x180013739  jz      loc_180013AE3
0x18001373f  cmp     eax, 17h
0x180013742  jnz     loc_180013CA8
0x180013748  lea     r9, [rbp+4Fh+var_78]; optval
0x18001374c  mov     dword ptr [rsp+0E0h+phkResult], 4; optlen
0x180013754  mov     r8d, 13h; optname
0x18001375a  mov     edx, r15d; level
0x18001375d  mov     rcx, rbx; s
0x180013760  call    cs:__imp_setsockopt
0x180013767  nop     dword ptr [rax+rax+00h]
0x18001376c  cmp     eax, 0FFFFFFFFh
0x18001376f  jz      loc_180013B22
0x180013775  mov     rcx, rdi; struct sockaddr *
0x180013778  call    ?AddressIsLoopback@@YAHPEBUsockaddr@@@Z; AddressIsLoopback(sockaddr const *)
0x18001377d  test    eax, eax
0x18001377f  jz      loc_180013A33
0x180013785  mov     rcx, cs:WPP_GLOBAL_Control
0x18001378c  cmp     rcx, rsi
0x18001378f  jz      short loc_18001379E
0x180013791  test    dword ptr [rcx+1Ch], 2000h
0x180013798  jnz     loc_180013C8E
0x18001379e  mov     [r13+0], rbx
0x1800137a2  mov     eax, 1
0x1800137a7  mov     rsi, [rsp+0E0h+var_30]
0x1800137af  mov     r12, [rsp+0E0h+var_38]
0x1800137b7  mov     rcx, [rbp+4Fh+var_48]
0x1800137bb  xor     rcx, rsp; StackCookie
0x1800137be  call    __security_check_cookie
0x1800137c3  add     rsp, 0B8h
0x1800137ca  pop     r15
0x1800137cc  pop     r14
0x1800137ce  pop     r13
0x1800137d0  pop     rdi
0x1800137d1  pop     rbx
0x1800137d2  pop     rbp
0x1800137d3  retn
0x1800137d5  mov     rax, cs:WPP_GLOBAL_Control
0x1800137dc  cmp     rax, r15
0x1800137df  jnz     loc_180013B9D
0x1800137e5  xor     eax, eax
0x1800137e7  jmp     short loc_1800137B7
0x1800137e9  test    dword ptr [rcx+1Ch], 2000h
0x1800137f0  jz      loc_180013660
0x1800137f6  mov     rcx, [rcx+10h]
0x1800137fa  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x180013801  mov     r9d, ebx
0x180013804  mov     edx, r12d
0x180013807  call    WPP_SF_d
0x18001380c  jmp     loc_180013660
0x180013811  cmp     eax, 17h
0x180013814  jz      loc_1800139E3
0x18001381a  cmp     rcx, rsi
0x18001381d  jnz     loc_180013CEA
0x180013823  mov     rcx, rbx; s
0x180013826  call    cs:__imp_closesocket
0x18001382d  nop     dword ptr [rax+rax+00h]
0x180013832  xor     eax, eax
0x180013834  mov     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x18001383c  jmp     loc_1800137A7
0x180013841  xor     eax, eax
0x180013843  mov     qword ptr [rbp+4Fh+cbBytesReturned], 0
0x18001384b  mov     [rbp+4Fh+var_50], eax
0x18001384e  xorps   xmm0, xmm0
0x180013851  movzx   eax, word ptr [rdi]
0x180013854  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x180013858  cmp     eax, 2
0x18001385b  jz      loc_18001398F
0x180013861  cmp     eax, 17h
0x180013864  jnz     loc_180013C36
0x18001386a  mov     rax, r14
0x18001386d  lea     rcx, ?in6SSDPAddresses@@3PAUin6_addr@@A; in6_addr near * in6SSDPAddresses
0x180013874  add     rax, rax
0x180013877  lea     r9, [rbp+4Fh+var_60]; optval
0x18001387b  mov     edx, r15d; level
0x18001387e  movups  xmm0, xmmword ptr [rcx+rax*8]
0x180013882  mov     eax, dword ptr [rbp+4Fh+optval]
0x180013885  mov     [rbp+4Fh+var_50], eax
0x180013888  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x18001388c  mov     r8d, 0Ch; optname
0x180013892  mov     dword ptr [rsp+0E0h+phkResult], r12d; optlen
0x180013897  mov     rcx, rbx; s
0x18001389a  call    cs:__imp_setsockopt
0x1800138a1  nop     dword ptr [rax+rax+00h]
0x1800138a6  cmp     eax, 0FFFFFFFFh
0x1800138a9  jz      loc_180013BF8
0x1800138af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138b6  lea     rsi, WPP_GLOBAL_Control
0x1800138bd  cmp     rcx, rsi
0x1800138c0  jz      loc_1800136BC
0x1800138c6  test    dword ptr [rcx+1Ch], 2000h
0x1800138cd  jz      loc_1800136BC
0x1800138d3  mov     rcx, [rcx+10h]
0x1800138d7  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x1800138de  mov     edx, 19h
0x1800138e3  call    WPP_SF_
0x1800138e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138ef  jmp     loc_1800136BC
0x1800138f4  mov     r8d, 0FFFFFFFBh; optname
0x1800138fa  call    cs:__imp_setsockopt
0x180013901  nop     dword ptr [rax+rax+00h]
0x180013906  test    eax, eax
0x180013908  jz      loc_180013650
0x18001390e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013915  cmp     rcx, r15
0x180013918  jz      loc_180013660
0x18001391e  test    byte ptr [rcx+1Ch], 1
0x180013922  jz      loc_180013657
0x180013928  call    cs:__imp_WSAGetLastError
0x18001392f  nop     dword ptr [rax+rax+00h]
0x180013934  mov     rcx, cs:WPP_GLOBAL_Control
0x18001393b  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x180013942  mov     edx, 13h
0x180013947  mov     r9d, eax
0x18001394a  mov     rcx, [rcx+10h]
0x18001394e  call    WPP_SF_d
0x180013953  jmp     loc_180013650
0x180013958  mov     rax, cs:WPP_GLOBAL_Control
0x18001395f  cmp     rax, r15
0x180013962  jz      loc_180013823
0x180013968  test    byte ptr [rax+1Ch], 1
0x18001396c  jz      loc_180013823
0x180013972  call    cs:__imp_WSAGetLastError
0x180013979  nop     dword ptr [rax+rax+00h]
0x18001397e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013985  mov     edx, 15h
0x18001398a  jmp     loc_180013CF9
0x18001398f  lea     rcx, String; "239.255.255.250"
0x180013996  call    cs:__imp_inet_addr
0x18001399d  nop     dword ptr [rax+rax+00h]
0x1800139a2  mov     [rbp+4Fh+cbBytesReturned], eax
0x1800139a5  xor     edx, edx
0x1800139a7  mov     eax, dword ptr [rbp+4Fh+optval]
0x1800139aa  lea     r9, [rbp+4Fh+cbBytesReturned]
0x1800139ae  mov     [rbp+4Fh+cbBytesReturned+4], eax
0x1800139b1  mov     r12d, 8
0x1800139b7  jmp     loc_18001388C
0x1800139bc  test    dword ptr [rcx+1Ch], 2000h
0x1800139c3  jz      loc_1800135D6
0x1800139c9  mov     rcx, [rcx+10h]
0x1800139cd  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x1800139d4  mov     edx, 10h
0x1800139d9  call    WPP_SF_d
0x1800139de  jmp     loc_1800135D6
0x1800139e3  mov     edx, r15d
0x1800139e6  jmp     loc_1800136CA
0x1800139eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800139f2  cmp     rax, rsi
0x1800139f5  jz      loc_180013823
0x1800139fb  test    byte ptr [rax+1Ch], 1
0x1800139ff  jz      loc_180013823
0x180013a05  call    cs:__imp_WSAGetLastError
0x180013a0c  nop     dword ptr [rax+rax+00h]
0x180013a11  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a18  mov     edx, 1Bh
0x180013a1d  jmp     loc_180013CF9
  ... truncated ...
```
