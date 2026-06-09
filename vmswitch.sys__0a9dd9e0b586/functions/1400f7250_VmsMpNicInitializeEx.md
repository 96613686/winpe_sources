# VmsMpNicInitializeEx

- ea: `0x1400f7250`
- end: `0x1400f817e`
- name: `VmsMpNicInitializeEx`
- size: `3886`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400f5bc0`

## callees

- `0x140027a64`
- `0x14002d258`
- `0x14002e45c`
- `0x14003c378`
- `0x14003e804`
- `0x14003e9e4`
- `0x140046f1c`
- `0x140052460`
- `0x14005deb8`
- `0x14006b990`
- `0x14006e0b0`
- `0x14008497c`
- `0x14008d88c`
- `0x1400f4db4`
- `0x1400f7250`
- `0x1400f8bb8`
- `0x1400f9330`
- `0x1400fa830`
- `0x140142a90`
- `0x1401bbcb0`
- `0x1401bbe80`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400f7eea`
- `ntoskrnl!KeReleaseMutex` at `0x1400f7ff4`
- `ntoskrnl!KeReleaseMutex` at `0x1400f8005`
- `ntoskrnl!KeReleaseMutex` at `0x1400f807d`
- `ntoskrnl!KeReleaseMutex` at `0x1400f7eea`
- `ntoskrnl!KeReleaseMutex` at `0x1400f7ff4`
- `ntoskrnl!KeReleaseMutex` at `0x1400f8005`
- `ntoskrnl!KeReleaseMutex` at `0x1400f807d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f7446`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f7fa5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f802d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f7446`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f7fa5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f802d`
- `NDIS!NdisReadNetworkAddress` at `0x1400f75ec`
- `NDIS!NdisReadNetworkAddress` at `0x1400f75ec`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x1400f738e`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x1400f738e`
- `NDIS!NdisCloseConfiguration` at `0x1400f7afb`
- `NDIS!NdisCloseConfiguration` at `0x1400f7afb`
- `NDIS!NdisReadConfiguration` at `0x1400f7676`
- `NDIS!NdisReadConfiguration` at `0x1400f76ba`
- `NDIS!NdisReadConfiguration` at `0x1400f76fe`
- `NDIS!NdisReadConfiguration` at `0x1400f7742`
- `NDIS!NdisReadConfiguration` at `0x1400f7786`
- `NDIS!NdisReadConfiguration` at `0x1400f77ca`
- `NDIS!NdisReadConfiguration` at `0x1400f780e`
- `NDIS!NdisReadConfiguration` at `0x1400f7852`
- `NDIS!NdisReadConfiguration` at `0x1400f78a7`
- `NDIS!NdisReadConfiguration` at `0x1400f7905`
- `NDIS!NdisReadConfiguration` at `0x1400f79d4`
- `NDIS!NdisReadConfiguration` at `0x1400f7a44`
- `NDIS!NdisReadConfiguration` at `0x1400f7a88`
- `NDIS!NdisReadConfiguration` at `0x1400f7acc`
- `NDIS!NdisReadConfiguration` at `0x1400f7676`
- `NDIS!NdisReadConfiguration` at `0x1400f76ba`
- `NDIS!NdisReadConfiguration` at `0x1400f76fe`
- `NDIS!NdisReadConfiguration` at `0x1400f7742`
- `NDIS!NdisReadConfiguration` at `0x1400f7786`
- `NDIS!NdisReadConfiguration` at `0x1400f77ca`
- `NDIS!NdisReadConfiguration` at `0x1400f780e`
- `NDIS!NdisReadConfiguration` at `0x1400f7852`
- `NDIS!NdisReadConfiguration` at `0x1400f78a7`
- `NDIS!NdisReadConfiguration` at `0x1400f7905`
- `NDIS!NdisReadConfiguration` at `0x1400f79d4`
- `NDIS!NdisReadConfiguration` at `0x1400f7a44`
- `NDIS!NdisReadConfiguration` at `0x1400f7a88`
- `NDIS!NdisReadConfiguration` at `0x1400f7acc`
- `NDIS!NdisOpenConfigurationEx` at `0x1400f75c0`
- `NDIS!NdisOpenConfigurationEx` at `0x1400f75c0`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x1400f737c`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x1400f737c`

## pseudocode

```c
__int64 __fastcall VmsMpNicInitializeEx(void *a1, __int64 a2, __int64 a3)
{
  char v4; // r14
  __int64 v6; // rbx
  int v7; // edx
  int v8; // r8d
  __int64 v9; // rdi
  char v10; // si
  unsigned int v11; // eax
  int v12; // edx
  int v13; // edx
  int v14; // r8d
  int v15; // edx
  int v16; // r8d
  int v17; // eax
  int v18; // edx
  int v19; // ecx
  __int128 v20; // xmm0
  bool v21; // r14
  __int128 v22; // xmm1
  __int16 v23; // ax
  __int128 v24; // xmm0
  __int16 v25; // ax
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  _WORD *v29; // rcx
  ULONG IntegerData; // ecx
  char v31; // r14
  bool v32; // zf
  int v33; // edx
  int v34; // r8d
  char v35; // si
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // edx
  unsigned __int8 v40; // al
  unsigned __int8 v41; // al
  int v42; // eax
  int v43; // edx
  int v44; // eax
  int v45; // edx
  int v46; // edx
  _DWORD *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rdi
  int v52; // edx
  int Status; // [rsp+50h] [rbp-B0h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+58h] [rbp-A8h] BYREF
  PVOID ConfigurationHandle; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int NetworkAddressLength; // [rsp+6Ch] [rbp-94h] BYREF
  PVOID NetworkAddress; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h]
  __int128 v60; // [rsp+80h] [rbp-80h] BYREF
  __m256i v61; // [rsp+90h] [rbp-70h] BYREF
  __int128 v62; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+D0h] [rbp-30h]
  struct _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v66; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v67; // [rsp+100h] [rbp+0h]
  __int128 v68; // [rsp+110h] [rbp+10h]
  _BYTE *v69; // [rsp+120h] [rbp+20h]
  _QWORD v70[28]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v71; // [rsp+210h] [rbp+110h] BYREF
  int v72; // [rsp+220h] [rbp+120h]
  _BYTE v73[112]; // [rsp+230h] [rbp+130h] BYREF

  v59 = a2;
  Status = -1073741823;
  ConfigurationHandle = 0;
  v4 = a2;
  NetworkAddress = 0;
  NetworkAddressLength = 0;
  memset(&v61, 0, 28);
  ParameterValue = 0;
  v72 = 0;
  v6 = 0;
  memset(&ConfigObject, 0, sizeof(ConfigObject));
  v71 = 0;
  memset(v70, 0, sizeof(v70));
  v62 = 0;
  LODWORD(v64) = 0;
  v63 = 0;
  v69 = 0;
  v60 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  memset(v73, 0, 0x68u);
  if ( !(unsigned __int8)VmsUtilVerifyNdisObjectHeader(a3) )
  {
    v9 = 0;
    Status = 65539;
    v10 = 1;
    goto LABEL_77;
  }
  v9 = *(_QWORD *)(a3 + 16);
  if ( !v9 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v7,
      19,
      52,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (__int64)"objNic");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v11 = ConvertInterfaceLuidToGuid((const NET_LUID *)(a3 + 40), (GUID *)(v9 + 1816));
  if ( v11 )
  {
    Status = NdisConvertNtStatusToNdisStatus(v11);
    v10 = 7;
    WPP_RECORDER_SF_Id(
      VmsIfrNicLog,
      v13,
      v14,
      53,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      *(_QWORD *)(a3 + 40),
      Status);
    goto LABEL_77;
  }
  v6 = *(_QWORD *)(v9 + 3312);
  if ( !v6 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v12,
      19,
      54,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (__int64)"mpExt");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_I(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      7,
      55,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      v9);
  KeWaitForSingleObject((PVOID)(v6 + 40), Executive, 0, 0, 0);
  if ( *(_DWORD *)(v6 + 32) )
  {
    v10 = 2;
    Status = -1073741823;
    WPP_RECORDER_SF_Ld(
      VmsIfrNicLog,
      v15,
      v16,
      56,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      *(_DWORD *)(v6 + 32),
      1);
  }
  else
  {
    *(_QWORD *)(v6 + 24) = a1;
    *(_DWORD *)(v6 + 936) = *(_DWORD *)(a3 + 32);
    v61.m256i_i64[0] = 2097566;
    v61.m256i_i64[1] = v9;
    *(_OWORD *)&v61.m256i_u64[2] = 0x20u;
    v17 = ((__int64 (__fastcall *)(void *, __m256i *))qword_1401F9528)(a1, &v61);
    Status = v17;
    if ( v17 )
    {
      v10 = 3;
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_qqd(
        VmsIfrNicLog,
        v18,
        20,
        57,
        (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
        (char)a1,
        (char)&v61,
        v17);
    }
    else
    {
      v19 = *(_DWORD *)(v9 + 2104);
      v20 = *(_OWORD *)(v9 + 3364);
      *(_DWORD *)(v9 + 3336) = v19;
      v21 = 0;
      v22 = *(_OWORD *)(v9 + 3380);
      *(_WORD *)(v9 + 3340) = *(_WORD *)(v9 + 2108);
      *(_DWORD *)(v9 + 1838) = v19;
      v23 = *(_WORD *)(v9 + 2108);
      *(_OWORD *)(v9 + 3460) = v20;
      *(_WORD *)(v9 + 1842) = v23;
      v24 = *(_OWORD *)(v9 + 3396);
      v25 = *(_WORD *)(v9 + 2108);
      *(_OWORD *)(v9 + 3476) = v22;
      *(_DWORD *)(v9 + 3342) = v19;
      v26 = *(_OWORD *)(v9 + 3412);
      *(_WORD *)(v9 + 3346) = v25;
      *(_OWORD *)(v9 + 3492) = v24;
      v27 = *(_OWORD *)(v9 + 3428);
      *(_OWORD *)(v9 + 3508) = v26;
      v28 = *(_OWORD *)(v9 + 3444);
      *(_OWORD *)(v9 + 3524) = v27;
      *(_OWORD *)(v9 + 3540) = v28;
      ConfigObject.Header = (NDIS_OBJECT_HEADER)1573289;
      ConfigObject.NdisHandle = a1;
      ConfigObject.Flags = 0;
      Status = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
      if ( !Status )
      {
        NdisReadNetworkAddress(&Status, &NetworkAddress, &NetworkAddressLength, ConfigurationHandle);
        if ( !Status && NetworkAddressLength == 6 )
        {
          v29 = NetworkAddress;
          if ( (*(_BYTE *)NetworkAddress & 1) == 0 && (*(_DWORD *)NetworkAddress || *((_WORD *)NetworkAddress + 2)) )
          {
            *(_DWORD *)(v9 + 3336) = *(_DWORD *)NetworkAddress;
            *(_WORD *)(v9 + 3340) = v29[2];
            *(_DWORD *)(v9 + 1838) = *(_DWORD *)v29;
            *(_WORD *)(v9 + 1842) = v29[2];
            *(_DWORD *)(v9 + 3342) = *(_DWORD *)NetworkAddress;
            *(_WORD *)(v9 + 3346) = *((_WORD *)NetworkAddress + 2);
          }
        }
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp4IpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4IpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp4TcpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4TcpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp6TcpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6TcpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp4UdpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4UdpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp6UdpChecksum,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6UdpChecksum, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp4TcpLsoV2,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4TcpLsoV2, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonIp6TcpLsoV2,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6TcpLsoV2, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonJumboPacket,
          NdisParameterInteger);
        if ( Status
          || (IntegerData = ParameterValue->ParameterData.IntegerData, IntegerData < 0x5EA)
          || IntegerData > VmsVmMaximumMTU )
        {
          IntegerData = 1514;
        }
        *(_DWORD *)(v9 + 3356) = IntegerData - *(_DWORD *)(v9 + 4064);
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &VmsMiniCommonIp4Rsc, NdisParameterInteger);
        v31 = *(_BYTE *)(v9 + 3952);
        if ( !Status )
        {
          v32 = ParameterValue->ParameterData.IntegerData == 0;
          *(_BYTE *)(v9 + 3954) = 0;
          *(_BYTE *)(v9 + 3952) = !v32;
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4Rsc, 0);
        }
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &VmsMiniCommonIp6Rsc, NdisParameterInteger);
        v35 = *(_BYTE *)(v9 + 3953);
        if ( !Status )
        {
          v32 = ParameterValue->ParameterData.IntegerData == 0;
          *(_BYTE *)(v9 + 3955) = 0;
          *(_BYTE *)(v9 + 3953) = !v32;
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6Rsc, 0);
        }
        if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 2) != 0 )
          McTemplateK0zzqqqqq_EtwWriteTransfer(
            *(unsigned __int8 *)(v9 + 3954),
            v33,
            v34,
            *(_QWORD *)(v9 + 80),
            *(_QWORD *)(v9 + 624),
            v31,
            v35,
            *(_BYTE *)(v9 + 3954),
            *(_BYTE *)(v9 + 3955),
            4);
        if ( *(_BYTE *)(v9 + 3952) != *(_BYTE *)(v9 + 3953) )
          VmsEtwTraceNicName((unsigned int)VM_NIC_RSC_SUBOPTIMAL_CONFIG_WARNING, v33, v34, v9 + 72, v9 + 616);
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonRssEnabled,
          NdisParameterInteger);
        if ( Status )
        {
          v21 = 0;
        }
        else
        {
          v32 = ParameterValue->ParameterData.IntegerData == 1;
          v72 = 128;
          v21 = v32;
          *(_QWORD *)&v71 = 0x30100120288LL;
          *((_QWORD *)&v71 + 1) = 0x1000000001LL;
        }
        NdisReadConfiguration(
          &Status,
          &ParameterValue,
          ConfigurationHandle,
          &VmsMiniCommonNetworkDirect,
          NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonNetworkDirect, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &VmsMiniCommonIp4Uso, NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp4Uso, ParameterValue->ParameterData.IntegerData);
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &VmsMiniCommonIp6Uso, NdisParameterInteger);
        if ( !Status )
          VmsMpCommonSetOffload(v9, &VmsMiniCommonIp6Uso, ParameterValue->ParameterData.IntegerData);
        NdisCloseConfiguration(ConfigurationHandle);
      }
      memset(v70, 0, sizeof(v70));
      LODWORD(v70[0]) = 14680479;
      v70[1] = 0;
      LODWORD(v70[2]) = *(_DWORD *)(v9 + 3356) - 14;
      v70[3] = 10000000000LL;
      v70[4] = 10000000000LL;
      v70[5] = 10000000000LL;
      v70[6] = 10000000000LL;
      v70[7] = (unsigned int)VmsOmNicGetMediaConnectState(v9);
      v36 = *(_DWORD *)(v9 + 3356) - 14;
      v70[9] = 0;
      LODWORD(v70[8]) = v36;
      v10 = 8;
      v70[10] = 0x2F00000008LL;
      v37 = 8;
      LODWORD(v70[11]) = 64;
      WORD2(v70[11]) = 6;
      if ( *(_BYTE *)(v9 + 3556) == 1 )
        v37 = 584;
      LODWORD(v70[10]) = v37;
      *(_DWORD *)((char *)&v70[15] + 6) = *(_DWORD *)(v9 + 3336);
      WORD1(v70[16]) = *(_WORD *)(v9 + 3340);
      *(_DWORD *)((char *)&v70[11] + 6) = *(_DWORD *)(v9 + 2104);
      WORD1(v70[12]) = *(_WORD *)(v9 + 2108);
      WORD2(v70[22]) = 6;
      v70[20] = (unsigned __int64)&v71 & -(__int64)v21;
      v70[21] = 2;
      v70[25] = VmsMpCommonNdis63VspOids;
      LODWORD(v70[22]) = 1;
      BYTE6(v70[22]) = 0;
      v70[23] = 1652032;
      v70[24] = 0x2000000000LL;
      LODWORD(v70[26]) = 248;
      v38 = ((__int64 (__fastcall *)(void *, _QWORD *))qword_1401F9528)(a1, v70);
      Status = v38;
      if ( v38 )
      {
        v10 = 4;
        LOBYTE(v39) = 2;
        WPP_RECORDER_SF_qqd(
          VmsIfrNicLog,
          v39,
          20,
          58,
          (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
          (char)a1,
          (char)v70,
          v38);
      }
      else
      {
        *(_QWORD *)(v6 + 944) = 0;
        *(_QWORD *)(v6 + 952) = 0;
        *(_QWORD *)(v6 + 928) = 10000000000LL;
        v62 = 0;
        v64 = 0;
        v63 = 0;
        LODWORD(v62) = 2621856;
        *(_DWORD *)(v6 + 708) = *(_DWORD *)(v9 + 3460);
        v40 = *(_BYTE *)(v6 + 709);
        *(_OWORD *)(v6 + 712) = *(_OWORD *)(v9 + 3464);
        *(_OWORD *)(v6 + 728) = *(_OWORD *)(v9 + 3480);
        *(_OWORD *)(v6 + 788) = *(_OWORD *)(v9 + 3496);
        *(_OWORD *)(v6 + 800) = *(_OWORD *)(v9 + 3508);
        if ( v40 >= 2u )
        {
          *(_OWORD *)(v6 + 820) = *(_OWORD *)(v9 + 3992);
          *(_OWORD *)(v6 + 836) = *(_OWORD *)(v9 + 4008);
        }
        if ( v40 >= 3u )
          *(_WORD *)(v6 + 852) = *(_WORD *)(v9 + 3954);
        *((_QWORD *)&v62 + 1) = v6 + 708;
        *(_DWORD *)(v6 + 488) = *(_DWORD *)(v9 + 3364);
        v41 = *(_BYTE *)(v6 + 489);
        *(_OWORD *)(v6 + 492) = *(_OWORD *)(v9 + 3368);
        *(_OWORD *)(v6 + 508) = *(_OWORD *)(v9 + 3384);
        *(_OWORD *)(v6 + 568) = *(_OWORD *)(v9 + 3400);
        *(_OWORD *)(v6 + 580) = *(_OWORD *)(v9 + 3412);
        if ( v41 >= 2u )
        {
          *(_OWORD *)(v6 + 600) = *(_OWORD *)(v9 + 3960);
          *(_OWORD *)(v6 + 616) = *(_OWORD *)(v9 + 3976);
        }
        if ( v41 >= 3u )
          *(_WORD *)(v6 + 632) = *(_WORD *)(v9 + 3952);
        *(_QWORD *)&v63 = v6 + 488;
        v42 = ((__int64 (__fastcall *)(void *, __int128 *))qword_1401F9528)(a1, &v62);
        Status = v42;
        if ( v42 )
        {
          v10 = 5;
          LOBYTE(v43) = 2;
          WPP_RECORDER_SF_qqd(
            VmsIfrNicLog,
            v43,
            20,
            59,
            (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
            (char)a1,
            (char)&v62,
            v42);
        }
        else
        {
          v66 = 0;
          LODWORD(v66) = 3670400;
          v67 = 0;
          v68 = 0;
          memset(v73, 0, 0x68u);
          v69 = v73;
          *(_QWORD *)&v60 = 1049011;
          *((_QWORD *)&v60 + 1) = &v66;
          v44 = ((__int64 (__fastcall *)(_QWORD, __int128 *))qword_1401F9528)(*(_QWORD *)(v6 + 24), &v60);
          Status = v44;
          if ( !v44 )
          {
            *(_DWORD *)(v9 + 4880) |= 2u;
            *(_DWORD *)(v9 + 4848) = 14;
            *(_DWORD *)(v9 + 4764) = 1;
            *(_BYTE *)(v9 + 4852) = 0;
            *(_DWORD *)(v9 + 4856) = 0;
            *(_BYTE *)(v9 + 4864) = 0;
            v10 = 0;
            *(_DWORD *)(v6 + 32) = 1;
            *(_BYTE *)(v6 + 941) = 1;
            KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
            if ( *(_DWORD *)(v9 + 1880) == 1 )
            {
              v47 = *(_DWORD **)(v9 + 1888);
              if ( (unsigned int)(v47[1068] - 2) <= 1 && v47[1284] && v47[1285] )
                VmsMpNicPvtUpdateNdisStack(v9, 0);
            }
            KeReleaseMutex(&VmsOmIoctlMutex, 0);
            KeReleaseMutex((PRKMUTEX)(v6 + 40), 0);
            VmsMpNicPvtPinMacAddress(v9);
            KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
            if ( *(_DWORD *)(v9 + 1880) == 1 )
            {
              v48 = *(_QWORD *)(v9 + 1888);
              if ( v48 )
              {
                v49 = *(_QWORD *)(v48 + 4264);
                if ( v49 )
                {
                  if ( *(_DWORD *)(v49 + 4764) == 3 && *(_BYTE *)(v9 + 4760) )
                    VmsNdkRequestRdma(v9);
                }
              }
            }
            KeReleaseMutex(&VmsOmIoctlMutex, 0);
            if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
              WPP_RECORDER_SF_id(
                WPP_GLOBAL_Control->DeviceExtension,
                0,
                7,
                62,
                (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
                v6,
                Status);
            goto LABEL_76;
          }
          LOBYTE(v45) = 2;
          WPP_RECORDER_SF_qqd(
            VmsIfrNicLog,
            v45,
            20,
            60,
            (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
            *(_QWORD *)(v6 + 24),
            (char)&v60,
            v44);
        }
      }
    }
  }
  KeReleaseMutex((PRKMUTEX)(v6 + 40), 0);
LABEL_76:
  v4 = v59;
LABEL_77:
  if ( Status )
  {
    if ( v6 )
    {
      *(_QWORD *)(v6 + 24) = 0;
      *(_DWORD *)(v6 + 32) = 2;
    }
    if ( v9 )
    {
      v50 = v9 + 72;
      v51 = v9 + 616;
    }
    else
    {
      v50 = 0;
      v51 = 0;
    }
    VmsEtwTraceSwitchFailure(&VM_FAILED_TO_INITIALIZE_MINIPORT_NIC, v10, v50, v51);
    LOBYTE(v52) = 2;
    WPP_RECORDER_SF_qqqd(
      VmsIfrNicLog,
      v52,
      20,
      64,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (char)a1,
      v4,
      a3,
      Status);
  }
  else
  {
    VmsEtwTraceNicName((unsigned int)VM_MINIPORT_SUCCESSFULLY_INITIALIZED, v7, v8, v9 + 72, v9 + 616);
    WPP_RECORDER_SF_qZ(VmsIfrNicLog, v46, 1, 63, (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids, v9, v9 + 616);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400f7250  mov     [rsp-8+arg_18], rbx
0x1400f7255  push    rbp
0x1400f7256  push    rsi
0x1400f7257  push    rdi
0x1400f7258  push    r12
0x1400f725a  push    r13
0x1400f725c  push    r14
0x1400f725e  push    r15
0x1400f7260  lea     rbp, [rsp-1B0h]
0x1400f7268  sub     rsp, 2B0h
0x1400f726f  mov     rax, cs:__security_cookie
0x1400f7276  xor     rax, rsp
0x1400f7279  mov     [rbp+1E0h+var_40], rax
0x1400f7280  xorps   xmm0, xmm0
0x1400f7283  mov     [rsp+2E0h+var_268], rdx
0x1400f7288  xor     esi, esi
0x1400f728a  mov     [rsp+2E0h+Status], 0C0000001h
0x1400f7292  xor     eax, eax
0x1400f7294  mov     [rsp+2E0h+ConfigurationHandle], rsi
0x1400f7299  mov     r13, r8
0x1400f729c  mov     qword ptr [rbp+1E0h+ConfigObject.Flags], rax
0x1400f72a0  mov     r14, rdx
0x1400f72a3  mov     [rsp+2E0h+NetworkAddress], rsi
0x1400f72a8  mov     r15, rcx
0x1400f72ab  mov     [rsp+2E0h+NetworkAddressLength], esi
0x1400f72af  movups  [rbp+1E0h+var_250], xmm0
0x1400f72b3  xor     edx, edx; Val
0x1400f72b5  mov     [rsp+2E0h+ParameterValue], rsi
0x1400f72ba  mov     r8d, 0E0h; Size
0x1400f72c0  mov     [rbp+1E0h+var_C0], eax
0x1400f72c6  lea     rcx, [rbp+1E0h+var_1B0]; void *
0x1400f72ca  mov     ebx, esi
0x1400f72cc  movups  [rbp+1E0h+var_250+0Ch], xmm0
0x1400f72d0  movups  xmmword ptr [rbp+1E0h+ConfigObject.Header.Type], xmm0
0x1400f72d4  movups  [rbp+1E0h+var_D0], xmm0
0x1400f72db  call    memset
0x1400f72e0  xorps   xmm0, xmm0
0x1400f72e3  lea     r8d, [rsi+68h]; Size
0x1400f72e7  xorps   xmm1, xmm1
0x1400f72ea  lea     rcx, [rbp+1E0h+var_B0]; void *
0x1400f72f1  xor     eax, eax
0x1400f72f3  xor     edx, edx; Val
0x1400f72f5  movups  [rbp+1E0h+var_230], xmm0
0x1400f72f9  mov     dword ptr [rbp+1E0h+var_210], eax
0x1400f72fc  movups  [rbp+1E0h+var_220], xmm0
0x1400f7300  mov     [rbp+1E0h+var_1C0], rax
0x1400f7304  movups  [rbp+1E0h+var_260], xmm0
0x1400f7308  movups  [rbp+1E0h+var_1F0], xmm1
0x1400f730c  movups  [rbp+1E0h+var_1E0], xmm1
0x1400f7310  movups  [rbp+1E0h+var_1D0], xmm1
0x1400f7314  call    memset
0x1400f7319  mov     rcx, r13
0x1400f731c  call    VmsUtilVerifyNdisObjectHeader
0x1400f7321  lea     r12, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x1400f7328  test    al, al
0x1400f732a  jnz     short loc_1400F733E
0x1400f732c  mov     edi, esi
0x1400f732e  mov     [rsp+2E0h+Status], 10003h
0x1400f7336  lea     esi, [rdi+1]
0x1400f7339  jmp     loc_1400F7F02
0x1400f733e  mov     rdi, [r13+10h]
0x1400f7342  test    rdi, rdi
0x1400f7345  jnz     short loc_1400F7371
0x1400f7347  mov     rcx, cs:VmsIfrLog
0x1400f734e  lea     rax, aObjnic; "objNic"
0x1400f7355  mov     [rsp+2E0h+var_2B8], rax
0x1400f735a  lea     r9d, [rdi+34h]
0x1400f735e  lea     r8d, [rdi+13h]
0x1400f7362  mov     [rsp+2E0h+Timeout], r12
0x1400f7367  call    WPP_RECORDER_SF_s
0x1400f736c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objNic")
0x1400f7371  lea     rdx, [rdi+718h]; InterfaceGuid
0x1400f7378  lea     rcx, [r13+28h]; InterfaceLuid
0x1400f737c  call    cs:__imp_ConvertInterfaceLuidToGuid
0x1400f7383  nop     dword ptr [rax+rax+00h]
0x1400f7388  test    eax, eax
0x1400f738a  jz      short loc_1400F73CA
0x1400f738c  mov     ecx, eax
0x1400f738e  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x1400f7395  nop     dword ptr [rax+rax+00h]
0x1400f739a  mov     [rsp+2E0h+Status], eax
0x1400f739e  mov     esi, 7
0x1400f73a3  mov     rcx, cs:VmsIfrNicLog
0x1400f73aa  lea     r9d, [rsi+2Eh]
0x1400f73ae  mov     dword ptr [rsp+2E0h+var_2B0], eax
0x1400f73b2  mov     rax, [r13+28h]
0x1400f73b6  mov     [rsp+2E0h+var_2B8], rax
0x1400f73bb  mov     [rsp+2E0h+Timeout], r12
0x1400f73c0  call    WPP_RECORDER_SF_Id
0x1400f73c5  jmp     loc_1400F7F02
0x1400f73ca  mov     rbx, [rdi+0CF0h]
0x1400f73d1  test    rbx, rbx
0x1400f73d4  jnz     short loc_1400F7400
0x1400f73d6  mov     rcx, cs:VmsIfrLog
0x1400f73dd  lea     rax, aMpext; "mpExt"
0x1400f73e4  mov     [rsp+2E0h+var_2B8], rax
0x1400f73e9  lea     r9d, [rbx+36h]
0x1400f73ed  lea     r8d, [rbx+13h]
0x1400f73f1  mov     [rsp+2E0h+Timeout], r12
0x1400f73f6  call    WPP_RECORDER_SF_s
0x1400f73fb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "mpExt")
0x1400f7400  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f7407  cmp     byte ptr [rcx+29h], 4
0x1400f740b  ja      short loc_1400F7413
0x1400f740d  cmp     [rcx+48h], si
0x1400f7411  jz      short loc_1400F7432
0x1400f7413  mov     rcx, [rcx+40h]
0x1400f7417  mov     r9d, 37h ; '7'
0x1400f741d  mov     [rsp+2E0h+var_2B8], rdi
0x1400f7422  xor     edx, edx
0x1400f7424  mov     [rsp+2E0h+Timeout], r12
0x1400f7429  lea     r8d, [r9-30h]
0x1400f742d  call    WPP_RECORDER_SF_I
0x1400f7432  lea     r12, [rbx+28h]
0x1400f7436  mov     [rsp+2E0h+Timeout], rsi; Timeout
0x1400f743b  mov     rcx, r12; Object
0x1400f743e  xor     r9d, r9d; Alertable
0x1400f7441  xor     r8d, r8d; WaitMode
0x1400f7444  xor     edx, edx; WaitReason
0x1400f7446  call    cs:__imp_KeWaitForSingleObject
0x1400f744d  nop     dword ptr [rax+rax+00h]
0x1400f7452  cmp     [rbx+20h], esi
0x1400f7455  jz      short loc_1400F7491
0x1400f7457  mov     ecx, 0C0000001h
0x1400f745c  mov     esi, 2
0x1400f7461  mov     [rsp+2E0h+Status], ecx
0x1400f7465  mov     eax, [rbx+20h]
0x1400f7468  lea     r9d, [rsi+36h]
0x1400f746c  mov     dword ptr [rsp+2E0h+var_2B0], ecx
0x1400f7470  mov     rcx, cs:VmsIfrNicLog
0x1400f7477  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x1400f747b  lea     rax, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x1400f7482  mov     [rsp+2E0h+Timeout], rax
0x1400f7487  call    WPP_RECORDER_SF_Ld
0x1400f748c  jmp     loc_1400F7EE5
0x1400f7491  mov     [rbx+18h], r15
0x1400f7495  lea     rdx, [rbp+1E0h+var_250]
0x1400f7499  mov     eax, [r13+20h]
0x1400f749d  mov     rcx, r15
0x1400f74a0  mov     [rbx+3A8h], eax
0x1400f74a6  mov     rax, cs:qword_1401F9528
0x1400f74ad  mov     qword ptr [rbp+1E0h+var_250], 20019Eh
0x1400f74b5  mov     [rbp+1E0h+var_238], rsi
0x1400f74b9  mov     qword ptr [rbp+1E0h+var_250+8], rdi
0x1400f74bd  mov     [rbp+1E0h+var_240], 20h ; ' '
0x1400f74c5  call    _guard_dispatch_icall
0x1400f74ca  mov     [rsp+2E0h+Status], eax
0x1400f74ce  test    eax, eax
0x1400f74d0  jz      short loc_1400F7510
0x1400f74d2  mov     esi, 3
0x1400f74d7  mov     rcx, cs:VmsIfrNicLog
0x1400f74de  lea     r9d, [rsi+36h]
0x1400f74e2  mov     dword ptr [rsp+2E0h+var_2A8], eax
0x1400f74e6  lea     r8d, [rsi+11h]
0x1400f74ea  lea     rax, [rbp+1E0h+var_250]
0x1400f74ee  mov     dl, 2
0x1400f74f0  mov     [rsp+2E0h+var_2B0], rax
0x1400f74f5  lea     rax, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x1400f74fc  mov     [rsp+2E0h+var_2B8], r15
0x1400f7501  mov     [rsp+2E0h+Timeout], rax
0x1400f7506  call    WPP_RECORDER_SF_qqd
0x1400f750b  jmp     loc_1400F7EE5
0x1400f7510  mov     ecx, [rdi+838h]
0x1400f7516  lea     rdx, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f751b  movups  xmm0, xmmword ptr [rdi+0D24h]
0x1400f7522  mov     [rdi+0D08h], ecx
0x1400f7528  mov     r14b, sil
0x1400f752b  movzx   eax, word ptr [rdi+83Ch]
0x1400f7532  movups  xmm1, xmmword ptr [rdi+0D34h]
0x1400f7539  mov     [rdi+0D0Ch], ax
0x1400f7540  mov     [rdi+72Eh], ecx
0x1400f7546  movzx   eax, word ptr [rdi+83Ch]
0x1400f754d  movups  xmmword ptr [rdi+0D84h], xmm0
0x1400f7554  mov     [rdi+732h], ax
0x1400f755b  movups  xmm0, xmmword ptr [rdi+0D44h]
0x1400f7562  movzx   eax, word ptr [rdi+83Ch]
0x1400f7569  movups  xmmword ptr [rdi+0D94h], xmm1
0x1400f7570  mov     [rdi+0D0Eh], ecx
0x1400f7576  lea     rcx, [rbp+1E0h+ConfigObject]; ConfigObject
0x1400f757a  movups  xmm1, xmmword ptr [rdi+0D54h]
0x1400f7581  mov     [rdi+0D12h], ax
0x1400f7588  movups  xmmword ptr [rdi+0DA4h], xmm0
0x1400f758f  movups  xmm0, xmmword ptr [rdi+0D64h]
0x1400f7596  movups  xmmword ptr [rdi+0DB4h], xmm1
0x1400f759d  movups  xmm1, xmmword ptr [rdi+0D74h]
0x1400f75a4  movups  xmmword ptr [rdi+0DC4h], xmm0
0x1400f75ab  movups  xmmword ptr [rdi+0DD4h], xmm1
0x1400f75b2  mov     dword ptr [rbp+1E0h+ConfigObject.Header.Type], 1801A9h
0x1400f75b9  mov     [rbp+1E0h+ConfigObject.NdisHandle], r15
0x1400f75bd  mov     [rbp+1E0h+ConfigObject.Flags], esi
0x1400f75c0  call    cs:__imp_NdisOpenConfigurationEx
0x1400f75c7  nop     dword ptr [rax+rax+00h]
0x1400f75cc  mov     [rsp+2E0h+Status], eax
0x1400f75d0  test    eax, eax
0x1400f75d2  jnz     loc_1400F7B07
0x1400f75d8  mov     r9, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f75dd  lea     r8, [rsp+2E0h+NetworkAddressLength]; NetworkAddressLength
0x1400f75e2  lea     rdx, [rsp+2E0h+NetworkAddress]; NetworkAddress
0x1400f75e7  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f75ec  call    cs:__imp_NdisReadNetworkAddress
0x1400f75f3  nop     dword ptr [rax+rax+00h]
0x1400f75f8  cmp     [rsp+2E0h+Status], esi
0x1400f75fc  jnz     short loc_1400F765C
0x1400f75fe  cmp     [rsp+2E0h+NetworkAddressLength], 6
0x1400f7603  jnz     short loc_1400F765C
0x1400f7605  mov     rcx, [rsp+2E0h+NetworkAddress]
0x1400f760a  test    byte ptr [rcx], 1
0x1400f760d  jnz     short loc_1400F765C
0x1400f760f  cmp     [rcx], esi
0x1400f7611  jnz     short loc_1400F7619
0x1400f7613  cmp     [rcx+4], si
0x1400f7617  jz      short loc_1400F765C
0x1400f7619  mov     eax, [rcx]
0x1400f761b  mov     [rdi+0D08h], eax
0x1400f7621  movzx   eax, word ptr [rcx+4]
0x1400f7625  mov     [rdi+0D0Ch], ax
0x1400f762c  mov     eax, [rcx]
0x1400f762e  mov     [rdi+72Eh], eax
0x1400f7634  movzx   eax, word ptr [rcx+4]
0x1400f7638  mov     [rdi+732h], ax
0x1400f763f  mov     rax, [rsp+2E0h+NetworkAddress]
0x1400f7644  mov     ecx, [rax]
0x1400f7646  mov     [rdi+0D0Eh], ecx
0x1400f764c  mov     rax, [rsp+2E0h+NetworkAddress]
0x1400f7651  movzx   ecx, word ptr [rax+4]
0x1400f7655  mov     [rdi+0D12h], cx
0x1400f765c  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f7661  lea     r9, VmsMiniCommonIp4IpChecksum; Keyword
0x1400f7668  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f766d  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f7671  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f7676  call    cs:__imp_NdisReadConfiguration
0x1400f767d  nop     dword ptr [rax+rax+00h]
0x1400f7682  cmp     [rsp+2E0h+Status], esi
0x1400f7686  jnz     short loc_1400F76A0
0x1400f7688  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f768d  lea     rdx, VmsMiniCommonIp4IpChecksum
0x1400f7694  mov     rcx, rdi
0x1400f7697  mov     r8d, [r8+8]
0x1400f769b  call    VmsMpCommonSetOffload
0x1400f76a0  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f76a5  lea     r9, VmsMiniCommonIp4TcpChecksum; Keyword
0x1400f76ac  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f76b1  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f76b5  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f76ba  call    cs:__imp_NdisReadConfiguration
0x1400f76c1  nop     dword ptr [rax+rax+00h]
0x1400f76c6  cmp     [rsp+2E0h+Status], esi
0x1400f76ca  jnz     short loc_1400F76E4
0x1400f76cc  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f76d1  lea     rdx, VmsMiniCommonIp4TcpChecksum
0x1400f76d8  mov     rcx, rdi
0x1400f76db  mov     r8d, [r8+8]
0x1400f76df  call    VmsMpCommonSetOffload
0x1400f76e4  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f76e9  lea     r9, VmsMiniCommonIp6TcpChecksum; Keyword
0x1400f76f0  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f76f5  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f76f9  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f76fe  call    cs:__imp_NdisReadConfiguration
0x1400f7705  nop     dword ptr [rax+rax+00h]
0x1400f770a  cmp     [rsp+2E0h+Status], esi
0x1400f770e  jnz     short loc_1400F7728
0x1400f7710  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f7715  lea     rdx, VmsMiniCommonIp6TcpChecksum
0x1400f771c  mov     rcx, rdi
0x1400f771f  mov     r8d, [r8+8]
0x1400f7723  call    VmsMpCommonSetOffload
0x1400f7728  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f772d  lea     r9, VmsMiniCommonIp4UdpChecksum; Keyword
0x1400f7734  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f7739  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f773d  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f7742  call    cs:__imp_NdisReadConfiguration
0x1400f7749  nop     dword ptr [rax+rax+00h]
0x1400f774e  cmp     [rsp+2E0h+Status], esi
0x1400f7752  jnz     short loc_1400F776C
0x1400f7754  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f7759  lea     rdx, VmsMiniCommonIp4UdpChecksum
0x1400f7760  mov     rcx, rdi
0x1400f7763  mov     r8d, [r8+8]
0x1400f7767  call    VmsMpCommonSetOffload
0x1400f776c  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f7771  lea     r9, VmsMiniCommonIp6UdpChecksum; Keyword
0x1400f7778  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f777d  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
0x1400f7781  lea     rcx, [rsp+2E0h+Status]; Status
0x1400f7786  call    cs:__imp_NdisReadConfiguration
0x1400f778d  nop     dword ptr [rax+rax+00h]
0x1400f7792  cmp     [rsp+2E0h+Status], esi
0x1400f7796  jnz     short loc_1400F77B0
0x1400f7798  mov     r8, [rsp+2E0h+ParameterValue]
0x1400f779d  lea     rdx, VmsMiniCommonIp6UdpChecksum
0x1400f77a4  mov     rcx, rdi
0x1400f77a7  mov     r8d, [r8+8]
0x1400f77ab  call    VmsMpCommonSetOffload
0x1400f77b0  mov     r8, [rsp+2E0h+ConfigurationHandle]; ConfigurationHandle
0x1400f77b5  lea     r9, VmsMiniCommonIp4TcpLsoV2; Keyword
0x1400f77bc  lea     rdx, [rsp+2E0h+ParameterValue]; ParameterValue
0x1400f77c1  mov     dword ptr [rsp+2E0h+Timeout], esi; ParameterType
  ... truncated ...
```
