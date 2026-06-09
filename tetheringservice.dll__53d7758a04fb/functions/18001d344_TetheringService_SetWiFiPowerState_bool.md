# TetheringService::SetWiFiPowerState(bool)

- ea: `0x18001d344`
- end: `0x18001daff`
- name: `?SetWiFiPowerState@TetheringService@@AEAAJ_N@Z`
- size: `1979`
- prototype: `__int64 __fastcall(TetheringService *this, unsigned __int8, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001e4a4`
- `0x18001f740`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18000bfb4`
- `0x18001d344`
- `0x180029c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d853`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d95a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d853`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d95a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d67d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d7c7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d67d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9ae`
- `wlanapi!WlanQueryInterface` at `0x18001d73e`
- `wlanapi!WlanQueryInterface` at `0x18001d73e`
- `wlanapi!WlanPrivateQueryInterface` at `0x18001d61d`
- `wlanapi!WlanPrivateQueryInterface` at `0x18001d61d`
- `wlanapi!WlanPrivateSetInterface` at `0x18001d5a7`
- `wlanapi!WlanPrivateSetInterface` at `0x18001d6a4`
- `wlanapi!WlanPrivateSetInterface` at `0x18001d7ee`
- `wlanapi!WlanPrivateSetInterface` at `0x18001d5a7`
- `wlanapi!WlanPrivateSetInterface` at `0x18001d6a4`
- `wlanapi!WlanPrivateSetInterface` at `0x18001d7ee`
- `wlanapi!WlanRegisterNotification` at `0x18001d47f`
- `wlanapi!WlanRegisterNotification` at `0x18001da63`
- `wlanapi!WlanRegisterNotification` at `0x18001d47f`
- `wlanapi!WlanRegisterNotification` at `0x18001da63`
- `wlanapi!WlanFreeMemory` at `0x18001d56d`
- `wlanapi!WlanFreeMemory` at `0x18001da36`
- `wlanapi!WlanFreeMemory` at `0x18001da98`
- `wlanapi!WlanFreeMemory` at `0x18001dab1`
- `wlanapi!WlanFreeMemory` at `0x18001d56d`
- `wlanapi!WlanFreeMemory` at `0x18001da36`
- `wlanapi!WlanFreeMemory` at `0x18001da98`
- `wlanapi!WlanFreeMemory` at `0x18001dab1`
- `wlanapi!WlanCloseHandle` at `0x18001da6e`
- `wlanapi!WlanCloseHandle` at `0x18001da6e`
- `wlanapi!WlanEnumInterfaces` at `0x18001d4c7`
- `wlanapi!WlanEnumInterfaces` at `0x18001d4c7`
- `wlanapi!WlanOpenHandle` at `0x18001d408`
- `wlanapi!WlanOpenHandle` at `0x18001d408`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TetheringService::SetWiFiPowerState(
        TetheringService *this,
        unsigned __int8 a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // r12d
  char v6; // si
  PVOID v7; // r13
  bool v8; // r14
  HANDLE *v9; // rdi
  signed int v10; // eax
  unsigned int v11; // ebx
  TetheringServiceTelemetry *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // eax
  signed int v15; // eax
  PWLAN_INTERFACE_INFO_LIST v16; // rcx
  int v17; // eax
  int v18; // eax
  HANDLE v19; // rcx
  int v20; // eax
  void *v21; // rcx
  signed int v22; // eax
  int v23; // eax
  DWORD v24; // eax
  signed int LastError; // eax
  DWORD v26; // eax
  signed int v27; // eax
  DWORD pdwDataSize; // [rsp+40h] [rbp-28h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+48h] [rbp-20h] BYREF
  PVOID pMemory; // [rsp+50h] [rbp-18h] BYREF
  PVOID ppData; // [rsp+58h] [rbp-10h] BYREF
  int v33; // [rsp+B0h] [rbp+48h]
  int v34; // [rsp+B8h] [rbp+50h]
  DWORD pdwNegotiatedVersion; // [rsp+C0h] [rbp+58h] BYREF
  int v36; // [rsp+C8h] [rbp+60h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    LOBYTE(a4) = a2;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, a4);
  }
  v6 = 0;
  v33 = v4 + 1;
  v7 = 0;
  v36 = 0;
  pdwNegotiatedVersion = 0;
  v34 = v4 ^ 1;
  ppInterfaceList = 0;
  pMemory = 0;
  v8 = IsMobile();
  *((_BYTE *)this + 1891) = 0;
  if ( *((_BYTE *)this + 1536) )
  {
    v9 = (HANDLE *)((char *)this + 1528);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
    v9 = (HANDLE *)((char *)this + 1528);
    v10 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, (PHANDLE)this + 191);
    v11 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 127;
LABEL_14:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v11);
LABEL_114:
        v12 = WPP_GLOBAL_Control;
        goto LABEL_115;
      }
      goto LABEL_115;
    }
    v14 = WlanRegisterNotification(
            *v9,
            0x18u,
            1,
            (WLAN_NOTIFICATION_CALLBACK)TetheringService::s_WlanNotificationCallback,
            0,
            0,
            0);
    v11 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v11 = (unsigned __int16)v14 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 128;
        goto LABEL_14;
      }
LABEL_115:
      if ( (v11 & 0x80000000) == 0 && (_BYTE)v4 )
        goto LABEL_122;
      goto LABEL_117;
    }
    v15 = WlanEnumInterfaces(*v9, 0, &ppInterfaceList);
    v11 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v11 = (unsigned __int16)v15 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 129;
        goto LABEL_14;
      }
      goto LABEL_115;
    }
    if ( !ppInterfaceList->dwNumberOfItems )
    {
      v11 = -2147024894;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          130,
          &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
          2147942402LL);
      }
      goto LABEL_117;
    }
    v16 = ppInterfaceList;
    g_WlanInterfaceGuid = ppInterfaceList->InterfaceInfo[0].InterfaceGuid;
    *((_BYTE *)this + 1536) = 1;
    WlanFreeMemory(v16);
    ppInterfaceList = 0;
  }
  if ( v8 )
  {
    if ( v34 )
    {
      v17 = WlanPrivateSetInterface(*v9, &g_WlanInterfaceGuid, 8);
      v11 = v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          v11 = (unsigned __int16)v17 | 0x80070000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 131;
          goto LABEL_14;
        }
        goto LABEL_115;
      }
    }
  }
  if ( *((_BYTE *)this + 1889) && !(_BYTE)v4 || (_BYTE)v4 )
  {
    v18 = WlanPrivateQueryInterface(*v9, &g_WlanInterfaceGuid, 7, &v36, &pMemory);
    v11 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v11 = (unsigned __int16)v18 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 132;
        goto LABEL_14;
      }
      goto LABEL_115;
    }
    if ( *(_DWORD *)pMemory != v33 )
    {
      v19 = g_hWlanPowerSet;
      *((_BYTE *)this + 1891) = 1;
      ResetEvent(v19);
      v20 = WlanPrivateSetInterface(*((_QWORD *)this + 191), &g_WlanInterfaceGuid, 7);
      v11 = v20;
      if ( v20 )
      {
        if ( v20 > 0 )
          v11 = (unsigned __int16)v20 | 0x80070000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 133;
          goto LABEL_14;
        }
        goto LABEL_115;
      }
      *((_BYTE *)this + 1889) = v33 == 2;
    }
  }
  if ( v8 && !v34 )
  {
    v21 = (void *)*((_QWORD *)this + 191);
    pdwDataSize = 0;
    ppData = 0;
    v22 = WlanQueryInterface(v21, &g_WlanInterfaceGuid, wlan_intf_opcode_interface_state, 0, &pdwDataSize, &ppData, 0);
    v11 = v22;
    if ( v22 )
    {
      if ( v22 > 0 )
        v11 = (unsigned __int16)v22 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 134;
        goto LABEL_14;
      }
      goto LABEL_115;
    }
    v7 = ppData;
    if ( *(_DWORD *)ppData != 4 )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
          *(unsigned int *)ppData);
      }
      v6 = 1;
      ResetEvent(g_hWlanDisconnected);
    }
    v23 = WlanPrivateSetInterface(*((_QWORD *)this + 191), &g_WlanInterfaceGuid, 8);
    v11 = v23;
    if ( v23 )
    {
      if ( v23 > 0 )
        v11 = (unsigned __int16)v23 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 136;
        goto LABEL_14;
      }
      goto LABEL_115;
    }
  }
  v11 = 0;
  if ( *((_BYTE *)this + 1891) )
  {
    v24 = WaitForSingleObject(g_hWlanPowerSet, 0x2710u);
    if ( v24 )
    {
      if ( v24 == 258 )
      {
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
        }
        v11 = -2147023436;
        goto LABEL_85;
      }
      if ( v24 != -1 )
      {
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v24);
        }
        v11 = -2147418113;
LABEL_85:
        *((_BYTE *)this + 1891) = 0;
        goto LABEL_117;
      }
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v11);
      }
    }
    *((_BYTE *)this + 1891) = 0;
    if ( (v11 & 0x80000000) != 0 )
      goto LABEL_117;
  }
  if ( !v6 )
    goto LABEL_114;
  v26 = WaitForSingleObject(g_hWlanDisconnected, 0x2710u);
  switch ( v26 )
  {
    case 0u:
      goto LABEL_114;
    case 0x102u:
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
      v11 = -2147023436;
      break;
    case 0xFFFFFFFF:
      v27 = GetLastError();
      v11 = v27;
      if ( v27 > 0 )
        v11 = (unsigned __int16)v27 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 141;
        goto LABEL_14;
      }
      goto LABEL_115;
    default:
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v26);
      }
      v11 = -2147418113;
      break;
  }
LABEL_117:
  if ( ppInterfaceList )
  {
    WlanFreeMemory(ppInterfaceList);
    ppInterfaceList = 0;
  }
  if ( *v9 )
  {
    WlanRegisterNotification(
      *v9,
      0,
      0,
      (WLAN_NOTIFICATION_CALLBACK)TetheringService::s_WlanNotificationCallback,
      0,
      0,
      0);
    WlanCloseHandle(*v9, 0);
    *v9 = 0;
  }
  g_WlanInterfaceGuid = 0;
  *((_BYTE *)this + 1536) = 0;
  v12 = WPP_GLOBAL_Control;
LABEL_122:
  if ( v7 )
  {
    WlanFreeMemory(v7);
    v12 = WPP_GLOBAL_Control;
  }
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    v12 = WPP_GLOBAL_Control;
    pMemory = 0;
  }
  if ( v12 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v12 + 2), 143, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18001d344  push    rbp
0x18001d346  push    rbx
0x18001d347  push    rsi
0x18001d348  push    rdi
0x18001d349  push    r12
0x18001d34b  push    r13
0x18001d34d  push    r14
0x18001d34f  push    r15
0x18001d351  mov     rbp, rsp
0x18001d354  sub     rsp, 68h
0x18001d358  movzx   r12d, dl
0x18001d35c  mov     r15, rcx
0x18001d35f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d366  lea     rbx, WPP_GLOBAL_Control
0x18001d36d  cmp     rcx, rbx
0x18001d370  jz      short loc_18001D390
0x18001d372  test    byte ptr [rcx+1Ch], 8
0x18001d376  jz      short loc_18001D390
0x18001d378  mov     rcx, [rcx+10h]
0x18001d37c  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001d383  mov     edx, 7Dh ; '}'
0x18001d388  mov     r9b, r12b
0x18001d38b  call    WPP_SF_c
0x18001d390  xor     esi, esi
0x18001d392  lea     eax, [r12+1]
0x18001d397  mov     [rbp+arg_0], eax
0x18001d39a  mov     r13d, esi
0x18001d39d  mov     eax, r12d
0x18001d3a0  mov     [rbp+arg_18], esi
0x18001d3a3  xor     eax, 1
0x18001d3a6  mov     [rbp+pdwNegotiatedVersion], esi
0x18001d3a9  mov     [rbp+arg_8], eax
0x18001d3ac  mov     [rbp+ppInterfaceList], rsi
0x18001d3b0  mov     [rbp+pMemory], rsi
0x18001d3b4  call    ?IsMobile@@YA_NXZ; IsMobile(void)
0x18001d3b9  mov     r14b, al
0x18001d3bc  mov     [r15+763h], sil
0x18001d3c3  cmp     [r15+600h], sil
0x18001d3ca  jnz     loc_18001D579
0x18001d3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3d7  cmp     rcx, rbx
0x18001d3da  jz      short loc_18001D3F5
0x18001d3dc  test    byte ptr [rcx+1Ch], 4
0x18001d3e0  jz      short loc_18001D3F5
0x18001d3e2  mov     rcx, [rcx+10h]
0x18001d3e6  lea     edx, [rsi+7Eh]
0x18001d3e9  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001d3f0  call    WPP_SF_
0x18001d3f5  xor     edx, edx; pReserved
0x18001d3f7  lea     rdi, [r15+5F8h]
0x18001d3fe  mov     r9, rdi; phClientHandle
0x18001d401  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18001d405  lea     ecx, [rdx+2]; dwClientVersion
0x18001d408  call    cs:__imp_WlanOpenHandle
0x18001d40e  mov     ebx, eax
0x18001d410  test    eax, eax
0x18001d412  jz      short loc_18001D45D
0x18001d414  jle     short loc_18001D41F
0x18001d416  movzx   ebx, ax
0x18001d419  or      ebx, 80070000h
0x18001d41f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d426  lea     rdx, WPP_GLOBAL_Control
0x18001d42d  cmp     rcx, rdx
0x18001d430  jz      loc_18001DA24
0x18001d436  test    byte ptr [rcx+1Ch], 1
0x18001d43a  jz      loc_18001DA24
0x18001d440  mov     edx, 7Fh
0x18001d445  mov     rcx, [rcx+10h]
0x18001d449  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001d450  mov     r9d, ebx
0x18001d453  call    WPP_SF_d
0x18001d458  jmp     loc_18001DA1D
0x18001d45d  mov     rcx, [rdi]; hClientHandle
0x18001d460  lea     r9, ?s_WlanNotificationCallback@TetheringService@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x18001d467  mov     edx, 18h; dwNotifSource
0x18001d46c  mov     [rsp+68h+pdwPrevNotifSource], rsi; pdwPrevNotifSource
0x18001d471  mov     [rsp+68h+pReserved], rsi; pReserved
0x18001d476  mov     [rsp+68h+pCallbackContext], rsi; pCallbackContext
0x18001d47b  lea     r8d, [rdx-17h]; bIgnoreDuplicate
0x18001d47f  call    cs:__imp_WlanRegisterNotification
0x18001d485  mov     ebx, eax
0x18001d487  test    eax, eax
0x18001d489  jz      short loc_18001D4BE
0x18001d48b  jle     short loc_18001D496
0x18001d48d  movzx   ebx, ax
0x18001d490  or      ebx, 80070000h
0x18001d496  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d49d  lea     rdx, WPP_GLOBAL_Control
0x18001d4a4  cmp     rcx, rdx
0x18001d4a7  jz      loc_18001DA24
0x18001d4ad  test    byte ptr [rcx+1Ch], 1
0x18001d4b1  jz      loc_18001DA24
0x18001d4b7  mov     edx, 80h
0x18001d4bc  jmp     short loc_18001D445
0x18001d4be  mov     rcx, [rdi]; hClientHandle
0x18001d4c1  lea     r8, [rbp+ppInterfaceList]; ppInterfaceList
0x18001d4c5  xor     edx, edx; pReserved
0x18001d4c7  call    cs:__imp_WlanEnumInterfaces
0x18001d4cd  mov     ebx, eax
0x18001d4cf  test    eax, eax
0x18001d4d1  jz      short loc_18001D509
0x18001d4d3  jle     short loc_18001D4DE
0x18001d4d5  movzx   ebx, ax
0x18001d4d8  or      ebx, 80070000h
0x18001d4de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4e5  lea     rdx, WPP_GLOBAL_Control
0x18001d4ec  cmp     rcx, rdx
0x18001d4ef  jz      loc_18001DA24
0x18001d4f5  test    byte ptr [rcx+1Ch], 1
0x18001d4f9  jz      loc_18001DA24
0x18001d4ff  mov     edx, 81h
0x18001d504  jmp     loc_18001D445
0x18001d509  mov     rax, [rbp+ppInterfaceList]
0x18001d50d  cmp     dword ptr [rax], 1
0x18001d510  jnb     short loc_18001D555
0x18001d512  mov     ebx, 80070002h
0x18001d517  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d51e  lea     rdx, WPP_GLOBAL_Control
0x18001d525  cmp     rcx, rdx
0x18001d528  jz      loc_18001DA2D
0x18001d52e  test    byte ptr [rcx+1Ch], 1
0x18001d532  jz      loc_18001DA2D
0x18001d538  mov     rcx, [rcx+10h]
0x18001d53c  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001d543  mov     edx, 82h
0x18001d548  mov     r9d, ebx
0x18001d54b  call    WPP_SF_d
0x18001d550  jmp     loc_18001DA2D
0x18001d555  mov     rcx, [rbp+ppInterfaceList]; pMemory
0x18001d559  movups  xmm0, xmmword ptr [rcx+8]
0x18001d55d  movdqu  xmmword ptr cs:?g_WlanInterfaceGuid@@3U_GUID@@A.Data1, xmm0; _GUID g_WlanInterfaceGuid ...
0x18001d565  mov     byte ptr [r15+600h], 1
0x18001d56d  call    cs:__imp_WlanFreeMemory
0x18001d573  mov     [rbp+ppInterfaceList], rsi
0x18001d577  jmp     short loc_18001D580
0x18001d579  lea     rdi, [r15+5F8h]
0x18001d580  test    r14b, r14b
0x18001d583  jz      short loc_18001D5E9
0x18001d585  cmp     [rbp+arg_8], esi
0x18001d588  jz      short loc_18001D5E9
0x18001d58a  mov     rcx, [rdi]
0x18001d58d  lea     rax, [rbp+arg_8]
0x18001d591  mov     r9d, 4
0x18001d597  mov     [rsp+68h+pCallbackContext], rax
0x18001d59c  lea     rdx, ?g_WlanInterfaceGuid@@3U_GUID@@A; _GUID g_WlanInterfaceGuid
0x18001d5a3  lea     r8d, [r9+4]
0x18001d5a7  call    cs:__imp_WlanPrivateSetInterface
0x18001d5ad  mov     ebx, eax
0x18001d5af  test    eax, eax
0x18001d5b1  jz      short loc_18001D5E9
0x18001d5b3  jle     short loc_18001D5BE
0x18001d5b5  movzx   ebx, ax
0x18001d5b8  or      ebx, 80070000h
0x18001d5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5c5  lea     rdx, WPP_GLOBAL_Control
0x18001d5cc  cmp     rcx, rdx
0x18001d5cf  jz      loc_18001DA24
0x18001d5d5  test    byte ptr [rcx+1Ch], 1
0x18001d5d9  jz      loc_18001DA24
0x18001d5df  mov     edx, 83h
0x18001d5e4  jmp     loc_18001D445
0x18001d5e9  cmp     [r15+761h], sil
0x18001d5f0  jz      short loc_18001D5F7
0x18001d5f2  test    r12b, r12b
0x18001d5f5  jz      short loc_18001D600
0x18001d5f7  test    r12b, r12b
0x18001d5fa  jz      loc_18001D6F4
0x18001d600  mov     rcx, [rdi]
0x18001d603  lea     rax, [rbp+pMemory]
0x18001d607  lea     r9, [rbp+arg_18]
0x18001d60b  mov     [rsp+68h+pCallbackContext], rax
0x18001d610  mov     r8d, 7
0x18001d616  lea     rdx, ?g_WlanInterfaceGuid@@3U_GUID@@A; _GUID g_WlanInterfaceGuid
0x18001d61d  call    cs:__imp_WlanPrivateQueryInterface
0x18001d623  mov     ebx, eax
0x18001d625  test    eax, eax
0x18001d627  jz      short loc_18001D65F
0x18001d629  jle     short loc_18001D634
0x18001d62b  movzx   ebx, ax
0x18001d62e  or      ebx, 80070000h
0x18001d634  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d63b  lea     rdx, WPP_GLOBAL_Control
0x18001d642  cmp     rcx, rdx
0x18001d645  jz      loc_18001DA24
0x18001d64b  test    byte ptr [rcx+1Ch], 1
0x18001d64f  jz      loc_18001DA24
0x18001d655  mov     edx, 84h
0x18001d65a  jmp     loc_18001D445
0x18001d65f  mov     rax, [rbp+pMemory]
0x18001d663  mov     ecx, [rbp+arg_0]
0x18001d666  cmp     [rax], ecx
0x18001d668  jz      loc_18001D6F4
0x18001d66e  mov     rcx, cs:?g_hWlanPowerSet@@3PEAXEA; hEvent
0x18001d675  mov     byte ptr [r15+763h], 1
0x18001d67d  call    cs:__imp_ResetEvent
0x18001d683  mov     rcx, [r15+5F8h]
0x18001d68a  lea     rax, [rbp+arg_0]
0x18001d68e  mov     r9d, 4
0x18001d694  mov     [rsp+68h+pCallbackContext], rax
0x18001d699  lea     rdx, ?g_WlanInterfaceGuid@@3U_GUID@@A; _GUID g_WlanInterfaceGuid
0x18001d6a0  lea     r8d, [r9+3]
0x18001d6a4  call    cs:__imp_WlanPrivateSetInterface
0x18001d6aa  mov     ebx, eax
0x18001d6ac  test    eax, eax
0x18001d6ae  jz      short loc_18001D6E6
0x18001d6b0  jle     short loc_18001D6BB
0x18001d6b2  movzx   ebx, ax
0x18001d6b5  or      ebx, 80070000h
0x18001d6bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6c2  lea     rdx, WPP_GLOBAL_Control
0x18001d6c9  cmp     rcx, rdx
0x18001d6cc  jz      loc_18001DA24
0x18001d6d2  test    byte ptr [rcx+1Ch], 1
0x18001d6d6  jz      loc_18001DA24
0x18001d6dc  mov     edx, 85h
0x18001d6e1  jmp     loc_18001D445
0x18001d6e6  cmp     [rbp+arg_0], 2
0x18001d6ea  setz    al
0x18001d6ed  mov     [r15+761h], al
0x18001d6f4  test    r14b, r14b
0x18001d6f7  jz      loc_18001D834
0x18001d6fd  xor     r14d, r14d
0x18001d700  cmp     [rbp+arg_8], r14d
0x18001d704  jnz     loc_18001D837
0x18001d70a  mov     rcx, [r15+5F8h]; hClientHandle
0x18001d711  lea     rax, [rbp+ppData]
0x18001d715  mov     [rsp+68h+pdwPrevNotifSource], r14; pWlanOpcodeValueType
0x18001d71a  lea     r8d, [r14+6]; OpCode
0x18001d71e  mov     [rsp+68h+pReserved], rax; ppData
0x18001d723  lea     rdx, ?g_WlanInterfaceGuid@@3U_GUID@@A; pInterfaceGuid
0x18001d72a  lea     rax, [rbp+pdwDataSize]
0x18001d72e  mov     [rbp+pdwDataSize], r14d
0x18001d732  xor     r9d, r9d; pReserved
0x18001d735  mov     [rsp+68h+pCallbackContext], rax; pdwDataSize
0x18001d73a  mov     [rbp+ppData], r14
0x18001d73e  call    cs:__imp_WlanQueryInterface
0x18001d744  mov     ebx, eax
0x18001d746  test    eax, eax
0x18001d748  jz      short loc_18001D780
0x18001d74a  jle     short loc_18001D755
0x18001d74c  movzx   ebx, ax
0x18001d74f  or      ebx, 80070000h
0x18001d755  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d75c  lea     rdx, WPP_GLOBAL_Control
0x18001d763  cmp     rcx, rdx
0x18001d766  jz      loc_18001DA24
0x18001d76c  test    byte ptr [rcx+1Ch], 1
0x18001d770  jz      loc_18001DA24
0x18001d776  mov     edx, 86h
0x18001d77b  jmp     loc_18001D445
0x18001d780  mov     r13, [rbp+ppData]
0x18001d784  cmp     dword ptr [r13+0], 4
0x18001d789  jz      short loc_18001D7CD
0x18001d78b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d792  lea     rax, WPP_GLOBAL_Control
0x18001d799  cmp     rcx, rax
0x18001d79c  jz      short loc_18001D7BD
0x18001d79e  test    byte ptr [rcx+1Ch], 4
0x18001d7a2  jz      short loc_18001D7BD
0x18001d7a4  mov     r9d, [r13+0]
0x18001d7a8  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001d7af  mov     rcx, [rcx+10h]
0x18001d7b3  mov     edx, 87h
0x18001d7b8  call    WPP_SF_d
0x18001d7bd  mov     rcx, cs:?g_hWlanDisconnected@@3PEAXEA; hEvent
0x18001d7c4  mov     sil, 1
0x18001d7c7  call    cs:__imp_ResetEvent
0x18001d7cd  mov     rcx, [r15+5F8h]
0x18001d7d4  lea     rax, [rbp+arg_8]
0x18001d7d8  mov     r9d, 4
0x18001d7de  mov     [rsp+68h+pCallbackContext], rax
0x18001d7e3  lea     rdx, ?g_WlanInterfaceGuid@@3U_GUID@@A; _GUID g_WlanInterfaceGuid
0x18001d7ea  lea     r8d, [r9+4]
0x18001d7ee  call    cs:__imp_WlanPrivateSetInterface
0x18001d7f4  mov     ebx, eax
0x18001d7f6  test    eax, eax
0x18001d7f8  jz      short loc_18001D837
0x18001d7fa  xor     esi, esi
0x18001d7fc  test    eax, eax
0x18001d7fe  jle     short loc_18001D809
0x18001d800  movzx   ebx, ax
0x18001d803  or      ebx, 80070000h
0x18001d809  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d810  lea     rax, WPP_GLOBAL_Control
0x18001d817  cmp     rcx, rax
0x18001d81a  jz      loc_18001DA24
0x18001d820  test    byte ptr [rcx+1Ch], 1
0x18001d824  jz      loc_18001DA24
0x18001d82a  mov     edx, 88h
0x18001d82f  jmp     loc_18001D445
0x18001d834  xor     r14d, r14d
0x18001d837  mov     ebx, r14d
0x18001d83a  cmp     [r15+763h], r14b
0x18001d841  jz      loc_18001D945
0x18001d847  mov     rcx, cs:?g_hWlanPowerSet@@3PEAXEA; hHandle
0x18001d84e  mov     edx, 2710h; dwMilliseconds
0x18001d853  call    cs:__imp_WaitForSingleObject
0x18001d859  test    eax, eax
0x18001d85b  jz      loc_18001D8FB
0x18001d861  cmp     eax, 102h
  ... truncated ...
```
