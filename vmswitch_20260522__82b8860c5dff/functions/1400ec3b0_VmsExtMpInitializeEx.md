# VmsExtMpInitializeEx

- ea: `0x1400ec3b0`
- end: `0x1400ec7cb`
- name: `VmsExtMpInitializeEx`
- size: `1051`
- prototype: `__int64 __fastcall(NDIS_HANDLE NdisMiniportHandle)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14001484c`
- `0x140027a64`
- `0x14003e9e4`
- `0x140052460`
- `0x1400538c4`
- `0x14006b084`
- `0x14006b990`
- `0x14008497c`
- `0x14008d88c`
- `0x1400eafdc`
- `0x1400ec3b0`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ec6d1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ec6d1`
- `NDIS!NdisInitializeEvent` at `0x1400ec763`
- `NDIS!NdisInitializeEvent` at `0x1400ec763`
- `NDIS!NdisMSetMiniportAttributes` at `0x1400ec526`
- `NDIS!NdisMSetMiniportAttributes` at `0x1400ec654`
- `NDIS!NdisMSetMiniportAttributes` at `0x1400ec526`
- `NDIS!NdisMSetMiniportAttributes` at `0x1400ec654`
- `NDIS!NdisReleaseRWLock` at `0x1400ec793`
- `NDIS!NdisReleaseRWLock` at `0x1400ec793`

## string_xrefs

- `0x1400ec71a`: `memcmp(&objSwitch->ExtensionStack.MiniportDeviceId, &deviceId, sizeof(GUID)) == 0`

## pseudocode

```c
__int64 __fastcall VmsExtMpInitializeEx(NDIS_HANDLE NdisMiniportHandle, char a2, __int64 a3)
{
  __int64 v6; // rbx
  int v7; // edx
  unsigned int DeviceId; // edi
  __int64 SwitchByExtMiniportAdapterInfo; // rax
  NDIS_STATUS v11; // eax
  int v12; // edx
  NDIS_STATUS v13; // eax
  int v14; // edx
  int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rax
  struct _NDIS_RW_LOCK_EX *v18; // rcx
  int v19; // edx
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING SourceString; // [rsp+58h] [rbp-A8h] BYREF
  __m256i MiniportAttributes; // [rsp+68h] [rbp-98h] BYREF
  union _NDIS_MINIPORT_ADAPTER_ATTRIBUTES MiniportAttributes_40; // [rsp+90h] [rbp-70h] BYREF
  GUID v24; // [rsp+170h] [rbp+70h] BYREF
  char v25; // [rsp+180h] [rbp+80h] BYREF

  memset(&MiniportAttributes, 0, 28);
  memset(&MiniportAttributes_40, 0, sizeof(MiniportAttributes_40));
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = 0;
  v24 = 0;
  SourceString = 0;
  if ( !(unsigned __int8)VmsUtilVerifyNdisObjectHeader(a3) )
  {
    DeviceId = 65539;
LABEL_3:
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_qqqd(
      VmsIfrLog,
      v7,
      20,
      33,
      (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
      (char)NdisMiniportHandle,
      a2,
      a3,
      DeviceId);
    goto LABEL_4;
  }
  *(_DWORD *)&SourceString.Length = 0x1000000;
  SourceString.Buffer = (wchar_t *)&v25;
  DeviceId = GetDeviceId(NdisMiniportHandle, &v24, &SourceString);
  if ( DeviceId )
    goto LABEL_12;
  SwitchByExtMiniportAdapterInfo = VmsOmpFindSwitchByExtMiniportAdapterInfo(0, &v24, 0);
  v6 = SwitchByExtMiniportAdapterInfo;
  if ( !SwitchByExtMiniportAdapterInfo )
  {
    DeviceId = -1073676271;
    goto LABEL_13;
  }
  MiniportAttributes.m256i_i64[0] = 2097566;
  *(_OWORD *)&MiniportAttributes.m256i_u64[2] = 0x20u;
  MiniportAttributes.m256i_i64[1] = SwitchByExtMiniportAdapterInfo;
  v11 = NdisMSetMiniportAttributes(NdisMiniportHandle, (PNDIS_MINIPORT_ADAPTER_ATTRIBUTES)&MiniportAttributes);
  DeviceId = v11;
  if ( v11 )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_qqd(
      VmsIfrLog,
      v12,
      20,
      29,
      (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
      (char)NdisMiniportHandle,
      (char)&MiniportAttributes,
      v11);
    goto LABEL_12;
  }
  memset(&MiniportAttributes_40, 0, sizeof(MiniportAttributes_40));
  MiniportAttributes_40.Header = (NDIS_OBJECT_HEADER)14680479;
  MiniportAttributes_40.GeneralAttributes.MaxXmitLinkSpeed = 10000000000LL;
  MiniportAttributes_40.GeneralAttributes.XmitLinkSpeed = 10000000000LL;
  MiniportAttributes_40.GeneralAttributes.MaxRcvLinkSpeed = 10000000000LL;
  MiniportAttributes_40.GeneralAttributes.RcvLinkSpeed = 10000000000LL;
  MiniportAttributes_40.AddDeviceRegistrationAttributes.Flags = 1500;
  MiniportAttributes_40.GeneralAttributes.IfType = 6;
  *((_QWORD *)&MiniportAttributes_40.HardwareAssistAttributes + 7) = 1;
  MiniportAttributes_40.GeneralAttributes.LookaheadSize = 1500;
  MiniportAttributes_40.GeneralAttributes.ConnectionType = NET_IF_CONNECTION_DEDICATED;
  MiniportAttributes_40.GeneralAttributes.SupportedOidList = (PNDIS_OID)VmsMpCommonNdis63VspOids;
  MiniportAttributes_40.AddDeviceRegistrationAttributes.MiniportAddDeviceContext = 0;
  MiniportAttributes_40.GeneralAttributes.PowerManagementCapabilities = 0;
  *((_QWORD *)&MiniportAttributes_40.HardwareAssistAttributes + 10) = 0x2F00000008LL;
  MiniportAttributes_40.GeneralAttributes.MaxMulticastListSize = 64;
  MiniportAttributes_40.GeneralAttributes.MacAddressLength = 0;
  MiniportAttributes_40.GeneralAttributes.RecvScaleCapabilities = 0;
  *((_QWORD *)&MiniportAttributes_40.HardwareAssistAttributes + 21) = 2;
  MiniportAttributes_40.GeneralAttributes.IfConnectorPresent = 0;
  *(_OWORD *)((char *)&MiniportAttributes_40.HardwareAssistAttributes + 184) = 0x193540u;
  MiniportAttributes_40.GeneralAttributes.SupportedOidListLength = 248;
  v13 = NdisMSetMiniportAttributes(NdisMiniportHandle, &MiniportAttributes_40);
  DeviceId = v13;
  if ( v13 )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_qqd(
      VmsIfrLog,
      v14,
      20,
      30,
      (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
      (char)NdisMiniportHandle,
      (char)&MiniportAttributes_40,
      v13);
LABEL_12:
    if ( DeviceId != -1073676271 )
      goto LABEL_3;
LABEL_13:
    LOBYTE(v7) = 3;
    WPP_RECORDER_SF_qqqd(
      VmsIfrLog,
      v7,
      20,
      32,
      (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
      (char)NdisMiniportHandle,
      a2,
      a3,
      17);
LABEL_4:
    if ( v6 )
    {
      *(_DWORD *)(v6 + 4276) = 5;
      VmsOmpObjectDereference(v6, 0);
    }
    return DeviceId;
  }
  VmsOmObjectLockExclusive(v6, &LockState, 0);
  *(_WORD *)(v6 + 4602) = 512;
  *(_QWORD *)(v6 + 4608) = v6 + 4616;
  *(_WORD *)(v6 + 4600) = 0;
  RtlCopyUnicodeString((PUNICODE_STRING)(v6 + 4600), &SourceString);
  *(_QWORD *)(v6 + 4296) = NdisMiniportHandle;
  *(_QWORD *)(v6 + 5128) = *(_QWORD *)(a3 + 40);
  v16 = *(_QWORD *)(v6 + 4312) - *(_QWORD *)&v24.Data1;
  if ( !v16 )
    v16 = *(_QWORD *)(v6 + 4320) - *(_QWORD *)v24.Data4;
  if ( v16 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v15,
      19,
      31,
      (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
      "memcmp(&objSwitch->ExtensionStack.MiniportDeviceId, &deviceId, sizeof(GUID)) == 0");
    v17 = *(_QWORD *)(v6 + 4312) - *(_QWORD *)&v24.Data1;
    if ( !v17 )
      v17 = *(_QWORD *)(v6 + 4320) - *(_QWORD *)v24.Data4;
    if ( v17 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  NdisInitializeEvent((PNDIS_EVENT)(v6 + 5144));
  *(_QWORD *)(v6 + 5208) = v6 + 5200;
  *(_QWORD *)(v6 + 5200) = v6 + 5200;
  v18 = *(struct _NDIS_RW_LOCK_EX **)(v6 + 56);
  *(_DWORD *)(v6 + 4276) = 1;
  NdisReleaseRWLock(v18, &LockState);
  WPP_RECORDER_SF_qZ(
    *(_QWORD *)(v6 + 9096),
    v19,
    1,
    34,
    (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
    v6,
    (__int64)&SourceString);
  return DeviceId;
}

```

## disassembly

```asm
0x1400ec3b0  mov     [rsp-8+arg_18], rbx
0x1400ec3b5  push    rbp
0x1400ec3b6  push    rsi
0x1400ec3b7  push    rdi
0x1400ec3b8  push    r12
0x1400ec3ba  push    r13
0x1400ec3bc  push    r14
0x1400ec3be  push    r15
0x1400ec3c0  lea     rbp, [rsp-190h]
0x1400ec3c8  sub     rsp, 290h
0x1400ec3cf  mov     rax, cs:__security_cookie
0x1400ec3d6  xor     rax, rsp
0x1400ec3d9  mov     [rbp+1C0h+var_40], rax
0x1400ec3e0  xorps   xmm0, xmm0
0x1400ec3e3  mov     r15, r8
0x1400ec3e6  mov     r12, rdx
0x1400ec3e9  mov     r14, rcx
0x1400ec3ec  movups  xmmword ptr [rsp+2C0h+MiniportAttributes], xmm0
0x1400ec3f1  xor     eax, eax
0x1400ec3f3  lea     rcx, [rbp+1C0h+MiniportAttributes+28h]; void *
0x1400ec3f7  xor     edx, edx; Val
0x1400ec3f9  mov     r8d, 0E0h; Size
0x1400ec3ff  movups  xmmword ptr [rsp+2C0h+MiniportAttributes+0Ch], xmm0
0x1400ec404  call    memset
0x1400ec409  xor     eax, eax
0x1400ec40b  xorps   xmm0, xmm0
0x1400ec40e  xorps   xmm1, xmm1
0x1400ec411  mov     word ptr [rsp+2C0h+LockState.OldIrql], ax
0x1400ec416  xor     r13d, r13d
0x1400ec419  mov     [rsp+2C0h+LockState.Flags], al
0x1400ec41d  mov     rcx, r15
0x1400ec420  mov     ebx, r13d
0x1400ec423  movups  [rbp+1C0h+var_150], xmm0
0x1400ec427  movups  xmmword ptr [rsp+2C0h+SourceString.Length], xmm1
0x1400ec42c  call    VmsUtilVerifyNdisObjectHeader
0x1400ec431  lea     rsi, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ec438  test    al, al
0x1400ec43a  jnz     short loc_1400EC4B7
0x1400ec43c  mov     edi, 10003h
0x1400ec441  mov     rcx, cs:VmsIfrLog
0x1400ec448  mov     r9d, 21h ; '!'
0x1400ec44e  mov     [rsp+2C0h+var_280], edi
0x1400ec452  mov     dl, 2
0x1400ec454  mov     [rsp+2C0h+var_288], r15
0x1400ec459  mov     [rsp+2C0h+var_290], r12
0x1400ec45e  lea     r8d, [r9-0Dh]
0x1400ec462  mov     [rsp+2C0h+var_298], r14
0x1400ec467  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec46c  call    WPP_RECORDER_SF_qqqd
0x1400ec471  test    rbx, rbx
0x1400ec474  jz      short loc_1400EC48A
0x1400ec476  xor     edx, edx
0x1400ec478  mov     dword ptr [rbx+10B4h], 5
0x1400ec482  mov     rcx, rbx
0x1400ec485  call    VmsOmpObjectDereference
0x1400ec48a  mov     eax, edi
0x1400ec48c  mov     rcx, [rbp+1C0h+var_40]
0x1400ec493  xor     rcx, rsp; StackCookie
0x1400ec496  call    __security_check_cookie
0x1400ec49b  mov     rbx, [rsp+2C0h+arg_18]
0x1400ec4a3  add     rsp, 290h
0x1400ec4aa  pop     r15
0x1400ec4ac  pop     r14
0x1400ec4ae  pop     r13
0x1400ec4b0  pop     r12
0x1400ec4b2  pop     rdi
0x1400ec4b3  pop     rsi
0x1400ec4b4  pop     rbp
0x1400ec4b5  retn
0x1400ec4b7  lea     rax, [rbp+1C0h+var_140]
0x1400ec4be  mov     dword ptr [rsp+2C0h+SourceString.Length], 1000000h
0x1400ec4c6  lea     r8, [rsp+2C0h+SourceString]
0x1400ec4cb  mov     [rsp+2C0h+SourceString.Buffer], rax
0x1400ec4d0  lea     rdx, [rbp+1C0h+var_150]
0x1400ec4d4  mov     rcx, r14
0x1400ec4d7  call    GetDeviceId
0x1400ec4dc  mov     edi, eax
0x1400ec4de  test    eax, eax
0x1400ec4e0  jnz     loc_1400EC568
0x1400ec4e6  xor     r8d, r8d
0x1400ec4e9  lea     rdx, [rbp+1C0h+var_150]
0x1400ec4ed  xor     ecx, ecx
0x1400ec4ef  call    VmsOmpFindSwitchByExtMiniportAdapterInfo
0x1400ec4f4  mov     rbx, rax
0x1400ec4f7  test    rax, rax
0x1400ec4fa  jnz     short loc_1400EC503
0x1400ec4fc  mov     edi, 0C0010011h
0x1400ec501  jmp     short loc_1400EC574
0x1400ec503  lea     rdx, [rsp+2C0h+MiniportAttributes]; MiniportAttributes
0x1400ec508  mov     qword ptr [rsp+2C0h+MiniportAttributes], 20019Eh
0x1400ec511  mov     rcx, r14; NdisMiniportHandle
0x1400ec514  mov     qword ptr [rbp+1C0h+MiniportAttributes+18h], r13
0x1400ec518  mov     qword ptr [rsp+2C0h+MiniportAttributes+10h], 20h ; ' '
0x1400ec521  mov     qword ptr [rsp+2C0h+MiniportAttributes+8], rbx
0x1400ec526  call    cs:__imp_NdisMSetMiniportAttributes
0x1400ec52d  nop     dword ptr [rax+rax+00h]
0x1400ec532  mov     edi, eax
0x1400ec534  test    eax, eax
0x1400ec536  jz      short loc_1400EC5AD
0x1400ec538  mov     rcx, cs:VmsIfrLog
0x1400ec53f  mov     r9d, 1Dh
0x1400ec545  mov     dword ptr [rsp+2C0h+var_288], eax
0x1400ec549  mov     dl, 2
0x1400ec54b  lea     rax, [rsp+2C0h+MiniportAttributes]
0x1400ec550  mov     [rsp+2C0h+var_290], rax
0x1400ec555  lea     r8d, [r9-9]
0x1400ec559  mov     [rsp+2C0h+var_298], r14
0x1400ec55e  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec563  call    WPP_RECORDER_SF_qqd
0x1400ec568  cmp     edi, 0C0010011h
0x1400ec56e  jnz     loc_1400EC441
0x1400ec574  mov     rcx, cs:VmsIfrLog
0x1400ec57b  mov     r9d, 20h ; ' '
0x1400ec581  mov     [rsp+2C0h+var_280], 0C0010011h
0x1400ec589  mov     dl, 3
0x1400ec58b  mov     [rsp+2C0h+var_288], r15
0x1400ec590  mov     [rsp+2C0h+var_290], r12
0x1400ec595  lea     r8d, [r9-0Ch]
0x1400ec599  mov     [rsp+2C0h+var_298], r14
0x1400ec59e  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec5a3  call    WPP_RECORDER_SF_qqqd
0x1400ec5a8  jmp     loc_1400EC471
0x1400ec5ad  xor     edx, edx; Val
0x1400ec5af  lea     rcx, [rbp+1C0h+MiniportAttributes+28h]; void *
0x1400ec5b3  mov     r8d, 0E0h; Size
0x1400ec5b9  call    memset
0x1400ec5be  mov     rax, 2540BE400h
0x1400ec5c8  mov     dword ptr [rbp+1C0h+MiniportAttributes+28h], 0E0019Fh
0x1400ec5cf  mov     edx, 1
0x1400ec5d4  mov     qword ptr [rbp+1C0h+MiniportAttributes+40h], rax
0x1400ec5d8  mov     qword ptr [rbp+1C0h+MiniportAttributes+48h], rax
0x1400ec5dc  mov     ecx, 5DCh
0x1400ec5e1  mov     qword ptr [rbp+1C0h+MiniportAttributes+50h], rax
0x1400ec5e5  mov     qword ptr [rbp+1C0h+MiniportAttributes+58h], rax
0x1400ec5e9  lea     eax, [rdx+5]
0x1400ec5ec  mov     dword ptr [rbp+1C0h+MiniportAttributes+38h], ecx
0x1400ec5ef  mov     word ptr [rbp+1C0h+MiniportAttributes+0DCh], ax
0x1400ec5f3  lea     rax, VmsMpCommonNdis63VspOids
0x1400ec5fa  mov     qword ptr [rbp+1C0h+MiniportAttributes+60h], rdx
0x1400ec5fe  mov     dword ptr [rbp+1C0h+MiniportAttributes+68h], ecx
0x1400ec601  mov     rcx, r14; NdisMiniportHandle
0x1400ec604  mov     dword ptr [rbp+1C0h+MiniportAttributes+0D8h], edx
0x1400ec607  lea     rdx, [rbp+1C0h+MiniportAttributes+28h]; MiniportAttributes
0x1400ec60b  mov     [rbp+1C0h+var_168], rax
0x1400ec60f  mov     qword ptr [rbp+1C0h+MiniportAttributes+30h], r13
0x1400ec613  mov     qword ptr [rbp+1C0h+MiniportAttributes+70h], r13
0x1400ec617  mov     dword ptr [rbp+1C0h+MiniportAttributes+78h], 8
0x1400ec61e  mov     dword ptr [rbp+1C0h+MiniportAttributes+7Ch], 2Fh ; '/'
0x1400ec625  mov     dword ptr [rbp+1C0h+MiniportAttributes+80h], 40h ; '@'
0x1400ec62c  mov     word ptr [rbp+1C0h+MiniportAttributes+84h], r13w
0x1400ec631  mov     qword ptr [rbp+1C0h+MiniportAttributes+0C8h], r13
0x1400ec635  mov     qword ptr [rbp+1C0h+MiniportAttributes+0D0h], 2
0x1400ec63d  mov     byte ptr [rbp+1C0h+MiniportAttributes+0DEh], r13b
0x1400ec641  mov     [rbp+1C0h+var_178], 193540h
0x1400ec649  mov     [rbp+1C0h+var_170], r13
0x1400ec64d  mov     [rbp+1C0h+var_160], 0F8h
0x1400ec654  call    cs:__imp_NdisMSetMiniportAttributes
0x1400ec65b  nop     dword ptr [rax+rax+00h]
0x1400ec660  mov     edi, eax
0x1400ec662  test    eax, eax
0x1400ec664  jz      short loc_1400EC69A
0x1400ec666  mov     rcx, cs:VmsIfrLog
0x1400ec66d  mov     r9d, 1Eh
0x1400ec673  mov     dword ptr [rsp+2C0h+var_288], eax
0x1400ec677  mov     dl, 2
0x1400ec679  lea     rax, [rbp+1C0h+MiniportAttributes+28h]
0x1400ec67d  mov     [rsp+2C0h+var_290], rax
0x1400ec682  lea     r8d, [r9-0Ah]
0x1400ec686  mov     [rsp+2C0h+var_298], r14
0x1400ec68b  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec690  call    WPP_RECORDER_SF_qqd
0x1400ec695  jmp     loc_1400EC568
0x1400ec69a  xor     r8d, r8d
0x1400ec69d  lea     rdx, [rsp+2C0h+LockState]
0x1400ec6a2  mov     rcx, rbx
0x1400ec6a5  call    VmsOmObjectLockExclusive
0x1400ec6aa  lea     rax, [rbx+1208h]
0x1400ec6b1  mov     word ptr [rbx+11FAh], 200h
0x1400ec6ba  lea     rcx, [rbx+11F8h]; DestinationString
0x1400ec6c1  mov     [rbx+1200h], rax
0x1400ec6c8  lea     rdx, [rsp+2C0h+SourceString]; SourceString
0x1400ec6cd  mov     [rcx], r13w
0x1400ec6d1  call    cs:__imp_RtlCopyUnicodeString
0x1400ec6d8  nop     dword ptr [rax+rax+00h]
0x1400ec6dd  mov     [rbx+10C8h], r14
0x1400ec6e4  mov     rax, [r15+28h]
0x1400ec6e8  mov     [rbx+1408h], rax
0x1400ec6ef  mov     rax, [rbx+10D8h]
0x1400ec6f6  sub     rax, qword ptr [rbp+1C0h+var_150]
0x1400ec6fa  jnz     short loc_1400EC707
0x1400ec6fc  mov     rax, [rbx+10E0h]
0x1400ec703  sub     rax, qword ptr [rbp+1C0h+var_150+8]
0x1400ec707  lea     rsi, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ec70e  test    rax, rax
0x1400ec711  jz      short loc_1400EC75C
0x1400ec713  mov     rcx, cs:VmsIfrLog
0x1400ec71a  lea     rax, aMemcmpObjswitc; "memcmp(&objSwitch->ExtensionStack.Minip"...
0x1400ec721  mov     r9d, 1Fh
0x1400ec727  mov     [rsp+2C0h+var_298], rax
0x1400ec72c  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec731  lea     r8d, [r9-0Ch]
0x1400ec735  call    WPP_RECORDER_SF_s
0x1400ec73a  mov     rax, [rbx+10D8h]
0x1400ec741  sub     rax, qword ptr [rbp+1C0h+var_150]
0x1400ec745  jnz     short loc_1400EC752
0x1400ec747  mov     rax, [rbx+10E0h]
0x1400ec74e  sub     rax, qword ptr [rbp+1C0h+var_150+8]
0x1400ec752  test    rax, rax
0x1400ec755  jz      short loc_1400EC75C
0x1400ec757  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "memcmp(&objSwitch->ExtensionStack.MiniportDeviceId, &deviceId, sizeof(GUID)) == 0")
0x1400ec75c  lea     rcx, [rbx+1418h]; Event
0x1400ec763  call    cs:__imp_NdisInitializeEvent
0x1400ec76a  nop     dword ptr [rax+rax+00h]
0x1400ec76f  lea     rax, [rbx+1450h]
0x1400ec776  mov     r14d, 1
0x1400ec77c  mov     [rax+8], rax
0x1400ec780  lea     rdx, [rsp+2C0h+LockState]; LockState
0x1400ec785  mov     [rax], rax
0x1400ec788  mov     rcx, [rbx+38h]; Lock
0x1400ec78c  mov     [rbx+10B4h], r14d
0x1400ec793  call    cs:__imp_NdisReleaseRWLock
0x1400ec79a  nop     dword ptr [rax+rax+00h]
0x1400ec79f  mov     rcx, [rbx+2388h]
0x1400ec7a6  lea     rax, [rsp+2C0h+SourceString]
0x1400ec7ab  mov     [rsp+2C0h+var_290], rax
0x1400ec7b0  lea     r9d, [r14+21h]
0x1400ec7b4  mov     [rsp+2C0h+var_298], rbx
0x1400ec7b9  mov     r8d, r14d
0x1400ec7bc  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec7c1  call    WPP_RECORDER_SF_qZ
0x1400ec7c6  jmp     loc_1400EC48A
```
