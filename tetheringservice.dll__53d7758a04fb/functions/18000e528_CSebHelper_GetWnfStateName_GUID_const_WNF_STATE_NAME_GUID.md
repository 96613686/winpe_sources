# CSebHelper::_GetWnfStateName(_GUID const &,_WNF_STATE_NAME *,_GUID *)

- ea: `0x18000e528`
- end: `0x18000e9ff`
- name: `?_GetWnfStateName@CSebHelper@@CAJAEBU_GUID@@PEAU_WNF_STATE_NAME@@PEAU2@@Z`
- size: `1239`
- prototype: `__int64 __fastcall(GUID *rguid, struct _WNF_STATE_NAME *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d9dc`

## callees

- `0x180002590`
- `0x180002ffa`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000e528`
- `0x18000ea08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e7f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e8be`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e7f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e8be`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e96a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e96a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e5a9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e77f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e5a9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e77f`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000e6f9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000e7b8`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000e6f9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000e7b8`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000e866`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000e92a`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000e866`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000e92a`
- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x18000e655`
- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x18000e655`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x18000e5fa`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x18000e5fa`

## pseudocode

```c
__int64 __fastcall CSebHelper::_GetWnfStateName(GUID *rguid, struct _WNF_STATE_NAME *a2, struct _GUID *a3)
{
  unsigned int v6; // ebx
  int NetworkAccountIdBoundToInterfaceId; // eax
  int ObjectProperties; // eax
  GUID *v9; // rcx
  GUID v10; // xmm0
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  struct _WNF_STATE_NAME *v14; // rax
  TetheringServiceTelemetry *v15; // rcx
  __int64 v16; // rdx
  TetheringServiceTelemetry *v17; // rcx
  __int64 v18; // rdx
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  DEVPROPKEY v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+6Ch] [rbp-94h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+78h] [rbp-88h] BYREF
  int v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+8Ch] [rbp-74h]
  __int64 v30; // [rsp+90h] [rbp-70h]
  GUID rguida; // [rsp+98h] [rbp-68h] BYREF
  OLECHAR v32[40]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[40]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR v34[40]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v35[528]; // [rsp+1A0h] [rbp+A0h] BYREF

  v6 = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids);
  }
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2(rguid, sz, 40) )
    goto LABEL_67;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids, sz);
  }
  memset_0(v32, 0, sizeof(v32));
  NetworkAccountIdBoundToInterfaceId = GetNetworkAccountIdBoundToInterfaceId(sz, 40, v32);
  v6 = NetworkAccountIdBoundToInterfaceId;
  if ( NetworkAccountIdBoundToInterfaceId < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_68;
    v18 = 38;
    goto LABEL_66;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids, v32);
  }
  memset_0(v35, 0, 0x208u);
  NetworkAccountIdBoundToInterfaceId = GetNetworkAccountBindingDeviceInterfacePath(v32, 260, v35);
  v6 = NetworkAccountIdBoundToInterfaceId;
  if ( NetworkAccountIdBoundToInterfaceId < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_68;
    v18 = 37;
LABEL_66:
    WPP_SF_d(
      *((_QWORD *)v17 + 2),
      v18,
      &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids,
      (unsigned int)NetworkAccountIdBoundToInterfaceId);
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids, v35);
  }
  v24 = DEVPKEY_Device_ContainerId;
  v21 = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  ObjectProperties = DevGetObjectProperties(1, v35, 0, 1, &v24, &v21, &v23);
  v6 = ObjectProperties;
  if ( ObjectProperties >= 0 )
  {
    rguida = 0;
    if ( v21 != 1 || *(_DWORD *)(v23 + 32) != 13 )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids);
      }
      v6 = -2147024809;
      goto LABEL_53;
    }
    v9 = *(GUID **)(v23 + 40);
    if ( v9 )
    {
      v10 = *v9;
      v20 = 0;
      rguida = v10;
      v22 = 0;
      v28 = 108;
      v29 = 0;
      v27 = DEVPKEY_DeviceContainer_DCA_WnfStateName;
      v30 = 0;
      if ( StringFromGUID2(&rguida, v34, 40) )
      {
        v11 = DevGetObjectProperties(2, v34, 0, 1, &v27, &v20, &v22);
        v6 = v11;
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids,
              (unsigned int)v11);
          }
          v6 = 0;
          *a2 = (struct _WNF_STATE_NAME)WNF_SEB_MBAE_NOTIFICATION_RECEIVED;
          goto LABEL_53;
        }
        v13 = v22;
        if ( v20 != 1 || *(_DWORD *)(v22 + 32) != 4099 )
        {
          if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids);
            v13 = v22;
          }
          v6 = -2147024809;
          goto LABEL_36;
        }
        if ( a2 )
        {
          v14 = *(struct _WNF_STATE_NAME **)(v22 + 40);
          if ( v14 )
          {
            *a2 = *v14;
LABEL_36:
            DevFreeObjectProperties(v20, v13);
LABEL_53:
            DevFreeObjectProperties(v21, v23);
LABEL_57:
            v17 = WPP_GLOBAL_Control;
            goto LABEL_58;
          }
          *a2 = 0;
        }
        *(_DWORD *)_o__errno(v12, v13) = 22;
        invalid_parameter_noinfo();
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids);
        }
        v13 = v22;
        v6 = -2147467259;
        goto LABEL_36;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_48:
        v6 = -2147467259;
        goto LABEL_53;
      }
      v16 = 33;
    }
    else
    {
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 22;
      invalid_parameter_noinfo();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_48;
      }
      v16 = 34;
    }
    WPP_SF_(*((_QWORD *)v15 + 2), v16, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids);
    goto LABEL_48;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids,
      (unsigned int)ObjectProperties);
    goto LABEL_57;
  }
LABEL_58:
  if ( (v6 & 0x80000000) == 0 )
  {
    v6 = CLSIDFromString(v32, a3);
LABEL_67:
    v17 = WPP_GLOBAL_Control;
  }
LABEL_68:
  if ( v17 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v17 + 2), 39, &WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x18000e528  push    rbp
0x18000e52a  push    rbx
0x18000e52b  push    rsi
0x18000e52c  push    rdi
0x18000e52d  push    r12
0x18000e52f  push    r14
0x18000e531  push    r15
0x18000e533  lea     rbp, [rsp-2C0h]
0x18000e53b  sub     rsp, 3C0h
0x18000e542  mov     rax, cs:__security_cookie
0x18000e549  xor     rax, rsp
0x18000e54c  mov     [rbp+2F0h+var_40], rax
0x18000e553  mov     r14, r8
0x18000e556  mov     rsi, rdx
0x18000e559  mov     rdi, rcx
0x18000e55c  xor     ebx, ebx
0x18000e55e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e565  lea     r15, WPP_GLOBAL_Control
0x18000e56c  lea     r12, WPP_77a2c26801653a0753b5e21a86582ed6_Traceguids
0x18000e573  cmp     rcx, r15
0x18000e576  jz      short loc_18000E58D
0x18000e578  test    byte ptr [rcx+1Ch], 8
0x18000e57c  jz      short loc_18000E58D
0x18000e57e  mov     rcx, [rcx+10h]
0x18000e582  lea     edx, [rbx+1Ah]
0x18000e585  mov     r8, r12
0x18000e588  call    WPP_SF_
0x18000e58d  xor     edx, edx; Val
0x18000e58f  lea     rcx, [rbp+2F0h+sz]; void *
0x18000e593  lea     r8d, [rdx+50h]; Size
0x18000e597  call    memset_0
0x18000e59c  mov     r8d, 28h ; '('; cchMax
0x18000e5a2  lea     rdx, [rbp+2F0h+sz]; lpsz
0x18000e5a6  mov     rcx, rdi; rguid
0x18000e5a9  call    cs:__imp_StringFromGUID2
0x18000e5af  test    eax, eax
0x18000e5b1  jz      loc_18000E9B9
0x18000e5b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5be  cmp     rcx, r15
0x18000e5c1  jz      short loc_18000E5DE
0x18000e5c3  test    byte ptr [rcx+1Ch], 8
0x18000e5c7  jz      short loc_18000E5DE
0x18000e5c9  mov     rcx, [rcx+10h]
0x18000e5cd  lea     r9, [rbp+2F0h+sz]
0x18000e5d1  mov     edx, 1Bh
0x18000e5d6  mov     r8, r12
0x18000e5d9  call    WPP_SF_S
0x18000e5de  xor     edx, edx; Val
0x18000e5e0  lea     rcx, [rbp+2F0h+var_340]; void *
0x18000e5e4  lea     r8d, [rdx+50h]; Size
0x18000e5e8  call    memset_0
0x18000e5ed  lea     r8, [rbp+2F0h+var_340]
0x18000e5f1  mov     edx, 28h ; '('
0x18000e5f6  lea     rcx, [rbp+2F0h+sz]
0x18000e5fa  call    cs:__imp_GetNetworkAccountIdBoundToInterfaceId
0x18000e600  mov     ebx, eax
0x18000e602  test    eax, eax
0x18000e604  js      loc_18000E990
0x18000e60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e611  cmp     rcx, r15
0x18000e614  jz      short loc_18000E631
0x18000e616  test    byte ptr [rcx+1Ch], 8
0x18000e61a  jz      short loc_18000E631
0x18000e61c  mov     rcx, [rcx+10h]
0x18000e620  lea     r9, [rbp+2F0h+var_340]
0x18000e624  mov     edx, 1Ch
0x18000e629  mov     r8, r12
0x18000e62c  call    WPP_SF_S
0x18000e631  xor     edx, edx; Val
0x18000e633  lea     rcx, [rbp+2F0h+var_250]; void *
0x18000e63a  mov     r8d, 208h; Size
0x18000e640  call    memset_0
0x18000e645  lea     r8, [rbp+2F0h+var_250]
0x18000e64c  mov     edx, 104h
0x18000e651  lea     rcx, [rbp+2F0h+var_340]
0x18000e655  call    cs:__imp_GetNetworkAccountBindingDeviceInterfacePath
0x18000e65b  mov     ebx, eax
0x18000e65d  test    eax, eax
0x18000e65f  js      loc_18000E974
0x18000e665  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e66c  cmp     rcx, r15
0x18000e66f  jz      short loc_18000E68F
0x18000e671  test    byte ptr [rcx+1Ch], 8
0x18000e675  jz      short loc_18000E68F
0x18000e677  mov     rcx, [rcx+10h]
0x18000e67b  lea     r9, [rbp+2F0h+var_250]
0x18000e682  mov     edx, 1Dh
0x18000e687  mov     r8, r12
0x18000e68a  call    WPP_SF_S
0x18000e68f  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x18000e695  lea     rdx, [rbp+2F0h+var_250]
0x18000e69c  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x18000e6a3  mov     [rsp+3F0h+var_388], eax
0x18000e6a7  mov     edi, 1
0x18000e6ac  lea     rax, [rsp+3F0h+var_3A0]
0x18000e6b1  mov     [rsp+3F0h+var_3AC], 0
0x18000e6b9  mov     [rsp+3F0h+var_3C0], rax
0x18000e6be  mov     r9d, edi
0x18000e6c1  lea     rax, [rsp+3F0h+var_3AC]
0x18000e6c6  mov     [rsp+3F0h+var_3A0], 0
0x18000e6cf  mov     [rsp+3F0h+var_3C8], rax
0x18000e6d4  xor     r8d, r8d
0x18000e6d7  lea     rax, [rsp+3F0h+var_398]
0x18000e6dc  mov     [rsp+3F0h+var_384], 0
0x18000e6e4  mov     ecx, edi
0x18000e6e6  mov     [rsp+3F0h+var_3D0], rax
0x18000e6eb  movups  [rsp+3F0h+var_398], xmm0
0x18000e6f0  mov     [rsp+3F0h+var_380], 0
0x18000e6f9  call    cs:__imp_DevGetObjectProperties
0x18000e6ff  mov     ebx, eax
0x18000e701  test    eax, eax
0x18000e703  js      loc_18000E932
0x18000e709  xorps   xmm0, xmm0
0x18000e70c  movups  xmmword ptr [rbp+2F0h+rguid.Data1], xmm0
0x18000e710  cmp     [rsp+3F0h+var_3AC], edi
0x18000e714  jnz     loc_18000E8F9
0x18000e71a  mov     rax, [rsp+3F0h+var_3A0]
0x18000e71f  cmp     dword ptr [rax+20h], 0Dh
0x18000e723  jnz     loc_18000E8F9
0x18000e729  mov     rcx, [rax+28h]
0x18000e72d  test    rcx, rcx
0x18000e730  jz      loc_18000E8BE
0x18000e736  movups  xmm0, xmmword ptr [rcx]
0x18000e739  mov     eax, cs:dword_180036F78
0x18000e73f  lea     r8d, [rdi+27h]; cchMax
0x18000e743  lea     rdx, [rbp+2F0h+var_2A0]; lpsz
0x18000e747  mov     [rsp+3F0h+var_3B0], 0
0x18000e74f  movdqu  xmmword ptr [rbp+2F0h+rguid.Data1], xmm0
0x18000e754  lea     rcx, [rbp+2F0h+rguid]; rguid
0x18000e758  mov     [rsp+3F0h+var_3A8], 0
0x18000e761  movups  xmm0, cs:DEVPKEY_DeviceContainer_DCA_WnfStateName
0x18000e768  mov     [rbp+2F0h+var_368], eax
0x18000e76b  mov     [rbp+2F0h+var_364], 0
0x18000e772  movups  [rsp+3F0h+var_378], xmm0
0x18000e777  mov     [rbp+2F0h+var_360], 0
0x18000e77f  call    cs:__imp_StringFromGUID2
0x18000e785  test    eax, eax
0x18000e787  jz      loc_18000E8A5
0x18000e78d  lea     rax, [rsp+3F0h+var_3A8]
0x18000e792  mov     r9d, edi
0x18000e795  mov     [rsp+3F0h+var_3C0], rax
0x18000e79a  lea     rdx, [rbp+2F0h+var_2A0]
0x18000e79e  lea     rax, [rsp+3F0h+var_3B0]
0x18000e7a3  xor     r8d, r8d
0x18000e7a6  mov     [rsp+3F0h+var_3C8], rax
0x18000e7ab  lea     ecx, [rdi+1]
0x18000e7ae  lea     rax, [rsp+3F0h+var_378]
0x18000e7b3  mov     [rsp+3F0h+var_3D0], rax
0x18000e7b8  call    cs:__imp_DevGetObjectProperties
0x18000e7be  mov     ebx, eax
0x18000e7c0  test    eax, eax
0x18000e7c2  js      loc_18000E871
0x18000e7c8  mov     rdx, [rsp+3F0h+var_3A8]
0x18000e7cd  cmp     [rsp+3F0h+var_3B0], edi
0x18000e7d1  jnz     short loc_18000E835
0x18000e7d3  cmp     dword ptr [rdx+20h], 1003h
0x18000e7da  jnz     short loc_18000E835
0x18000e7dc  test    rsi, rsi
0x18000e7df  jz      short loc_18000E7F5
0x18000e7e1  mov     rax, [rdx+28h]
0x18000e7e5  test    rax, rax
0x18000e7e8  jz      short loc_18000E7F2
0x18000e7ea  mov     rax, [rax]
0x18000e7ed  mov     [rsi], rax
0x18000e7f0  jmp     short loc_18000E862
0x18000e7f2  mov     [rsi], rax
0x18000e7f5  call    cs:__imp__o__errno
0x18000e7fb  mov     dword ptr [rax], 16h
0x18000e801  call    _invalid_parameter_noinfo
0x18000e806  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e80d  cmp     rcx, r15
0x18000e810  jz      short loc_18000E829
0x18000e812  test    [rcx+1Ch], dil
0x18000e816  jz      short loc_18000E829
0x18000e818  mov     rcx, [rcx+10h]
0x18000e81c  mov     edx, 1Eh
0x18000e821  mov     r8, r12
0x18000e824  call    WPP_SF_
0x18000e829  mov     rdx, [rsp+3F0h+var_3A8]
0x18000e82e  mov     ebx, 80004005h
0x18000e833  jmp     short loc_18000E862
0x18000e835  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e83c  cmp     rcx, r15
0x18000e83f  jz      short loc_18000E85D
0x18000e841  test    [rcx+1Ch], dil
0x18000e845  jz      short loc_18000E85D
0x18000e847  mov     rcx, [rcx+10h]
0x18000e84b  mov     edx, 1Fh
0x18000e850  mov     r8, r12
0x18000e853  call    WPP_SF_
0x18000e858  mov     rdx, [rsp+3F0h+var_3A8]
0x18000e85d  mov     ebx, 80070057h
0x18000e862  mov     ecx, [rsp+3F0h+var_3B0]
0x18000e866  call    cs:__imp_DevFreeObjectProperties
0x18000e86c  jmp     loc_18000E921
0x18000e871  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e878  cmp     rcx, r15
0x18000e87b  jz      short loc_18000E897
0x18000e87d  test    [rcx+1Ch], dil
0x18000e881  jz      short loc_18000E897
0x18000e883  mov     rcx, [rcx+10h]
0x18000e887  mov     edx, 20h ; ' '
0x18000e88c  mov     r9d, eax
0x18000e88f  mov     r8, r12
0x18000e892  call    WPP_SF_d
0x18000e897  mov     rax, cs:WNF_SEB_MBAE_NOTIFICATION_RECEIVED
0x18000e89e  xor     ebx, ebx
0x18000e8a0  mov     [rsi], rax
0x18000e8a3  jmp     short loc_18000E921
0x18000e8a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8ac  cmp     rcx, r15
0x18000e8af  jz      short loc_18000E8F2
0x18000e8b1  test    [rcx+1Ch], dil
0x18000e8b5  jz      short loc_18000E8F2
0x18000e8b7  mov     edx, 21h ; '!'
0x18000e8bc  jmp     short loc_18000E8E6
0x18000e8be  call    cs:__imp__o__errno
0x18000e8c4  mov     dword ptr [rax], 16h
0x18000e8ca  call    _invalid_parameter_noinfo
0x18000e8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8d6  cmp     rcx, r15
0x18000e8d9  jz      short loc_18000E8F2
0x18000e8db  test    [rcx+1Ch], dil
0x18000e8df  jz      short loc_18000E8F2
0x18000e8e1  mov     edx, 22h ; '"'
0x18000e8e6  mov     rcx, [rcx+10h]
0x18000e8ea  mov     r8, r12
0x18000e8ed  call    WPP_SF_
0x18000e8f2  mov     ebx, 80004005h
0x18000e8f7  jmp     short loc_18000E921
0x18000e8f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e900  cmp     rcx, r15
0x18000e903  jz      short loc_18000E91C
0x18000e905  test    [rcx+1Ch], dil
0x18000e909  jz      short loc_18000E91C
0x18000e90b  mov     rcx, [rcx+10h]
0x18000e90f  mov     edx, 23h ; '#'
0x18000e914  mov     r8, r12
0x18000e917  call    WPP_SF_
0x18000e91c  mov     ebx, 80070057h
0x18000e921  mov     rdx, [rsp+3F0h+var_3A0]
0x18000e926  mov     ecx, [rsp+3F0h+var_3AC]
0x18000e92a  call    cs:__imp_DevFreeObjectProperties
0x18000e930  jmp     short loc_18000E958
0x18000e932  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e939  cmp     rcx, r15
0x18000e93c  jz      short loc_18000E95F
0x18000e93e  test    [rcx+1Ch], dil
0x18000e942  jz      short loc_18000E95F
0x18000e944  mov     rcx, [rcx+10h]
0x18000e948  mov     edx, 24h ; '$'
0x18000e94d  mov     r9d, eax
0x18000e950  mov     r8, r12
0x18000e953  call    WPP_SF_d
0x18000e958  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e95f  test    ebx, ebx
0x18000e961  js      short loc_18000E9C0
0x18000e963  mov     rdx, r14; pclsid
0x18000e966  lea     rcx, [rbp+2F0h+var_340]; lpsz
0x18000e96a  call    cs:__imp_CLSIDFromString
0x18000e970  mov     ebx, eax
0x18000e972  jmp     short loc_18000E9B9
0x18000e974  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e97b  cmp     rcx, r15
0x18000e97e  jz      short loc_18000E9DC
0x18000e980  mov     edi, 1
0x18000e985  test    [rcx+1Ch], dil
0x18000e989  jz      short loc_18000E9C0
0x18000e98b  lea     edx, [rdi+24h]
0x18000e98e  jmp     short loc_18000E9AA
0x18000e990  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e997  cmp     rcx, r15
0x18000e99a  jz      short loc_18000E9DC
0x18000e99c  mov     edi, 1
0x18000e9a1  test    [rcx+1Ch], dil
0x18000e9a5  jz      short loc_18000E9C0
0x18000e9a7  lea     edx, [rdi+25h]
0x18000e9aa  mov     rcx, [rcx+10h]
0x18000e9ae  mov     r9d, eax
0x18000e9b1  mov     r8, r12
0x18000e9b4  call    WPP_SF_d
0x18000e9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9c0  cmp     rcx, r15
0x18000e9c3  jz      short loc_18000E9DC
0x18000e9c5  test    byte ptr [rcx+1Ch], 8
0x18000e9c9  jz      short loc_18000E9DC
0x18000e9cb  mov     rcx, [rcx+10h]
0x18000e9cf  mov     edx, 27h ; '''
0x18000e9d4  mov     r8, r12
0x18000e9d7  call    WPP_SF_
0x18000e9dc  mov     eax, ebx
0x18000e9de  mov     rcx, [rbp+2F0h+var_40]
0x18000e9e5  xor     rcx, rsp; StackCookie
0x18000e9e8  call    __security_check_cookie
0x18000e9ed  add     rsp, 3C0h
0x18000e9f4  pop     r15
0x18000e9f6  pop     r14
0x18000e9f8  pop     r12
0x18000e9fa  pop     rdi
0x18000e9fb  pop     rsi
  ... truncated ...
```
