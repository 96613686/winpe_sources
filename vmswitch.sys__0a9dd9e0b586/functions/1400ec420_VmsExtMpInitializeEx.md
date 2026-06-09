# VmsExtMpInitializeEx

- ea: `0x1400ec420`
- end: `0x1400ec83b`
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
- `0x1400eb04c`
- `0x1400ec420`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ec741`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ec741`
- `NDIS!NdisInitializeEvent` at `0x1400ec7d3`
- `NDIS!NdisInitializeEvent` at `0x1400ec7d3`
- `NDIS!NdisMSetMiniportAttributes` at `0x1400ec596`
- `NDIS!NdisMSetMiniportAttributes` at `0x1400ec6c4`
- `NDIS!NdisMSetMiniportAttributes` at `0x1400ec596`
- `NDIS!NdisMSetMiniportAttributes` at `0x1400ec6c4`
- `NDIS!NdisReleaseRWLock` at `0x1400ec803`
- `NDIS!NdisReleaseRWLock` at `0x1400ec803`

## string_xrefs

- `0x1400ec78a`: `memcmp(&objSwitch->ExtensionStack.MiniportDeviceId, &deviceId, sizeof(GUID)) == 0`

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
0x1400ec420  mov     [rsp-8+arg_18], rbx
0x1400ec425  push    rbp
0x1400ec426  push    rsi
0x1400ec427  push    rdi
0x1400ec428  push    r12
0x1400ec42a  push    r13
0x1400ec42c  push    r14
0x1400ec42e  push    r15
0x1400ec430  lea     rbp, [rsp-190h]
0x1400ec438  sub     rsp, 290h
0x1400ec43f  mov     rax, cs:__security_cookie
0x1400ec446  xor     rax, rsp
0x1400ec449  mov     [rbp+1C0h+var_40], rax
0x1400ec450  xorps   xmm0, xmm0
0x1400ec453  mov     r15, r8
0x1400ec456  mov     r12, rdx
0x1400ec459  mov     r14, rcx
0x1400ec45c  movups  xmmword ptr [rsp+2C0h+MiniportAttributes], xmm0
0x1400ec461  xor     eax, eax
0x1400ec463  lea     rcx, [rbp+1C0h+MiniportAttributes+28h]; void *
0x1400ec467  xor     edx, edx; Val
0x1400ec469  mov     r8d, 0E0h; Size
0x1400ec46f  movups  xmmword ptr [rsp+2C0h+MiniportAttributes+0Ch], xmm0
0x1400ec474  call    memset
0x1400ec479  xor     eax, eax
0x1400ec47b  xorps   xmm0, xmm0
0x1400ec47e  xorps   xmm1, xmm1
0x1400ec481  mov     word ptr [rsp+2C0h+LockState.OldIrql], ax
0x1400ec486  xor     r13d, r13d
0x1400ec489  mov     [rsp+2C0h+LockState.Flags], al
0x1400ec48d  mov     rcx, r15
0x1400ec490  mov     ebx, r13d
0x1400ec493  movups  [rbp+1C0h+var_150], xmm0
0x1400ec497  movups  xmmword ptr [rsp+2C0h+SourceString.Length], xmm1
0x1400ec49c  call    VmsUtilVerifyNdisObjectHeader
0x1400ec4a1  lea     rsi, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ec4a8  test    al, al
0x1400ec4aa  jnz     short loc_1400EC527
0x1400ec4ac  mov     edi, 10003h
0x1400ec4b1  mov     rcx, cs:VmsIfrLog
0x1400ec4b8  mov     r9d, 21h ; '!'
0x1400ec4be  mov     [rsp+2C0h+var_280], edi
0x1400ec4c2  mov     dl, 2
0x1400ec4c4  mov     [rsp+2C0h+var_288], r15
0x1400ec4c9  mov     [rsp+2C0h+var_290], r12
0x1400ec4ce  lea     r8d, [r9-0Dh]
0x1400ec4d2  mov     [rsp+2C0h+var_298], r14
0x1400ec4d7  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec4dc  call    WPP_RECORDER_SF_qqqd
0x1400ec4e1  test    rbx, rbx
0x1400ec4e4  jz      short loc_1400EC4FA
0x1400ec4e6  xor     edx, edx
0x1400ec4e8  mov     dword ptr [rbx+10B4h], 5
0x1400ec4f2  mov     rcx, rbx
0x1400ec4f5  call    VmsOmpObjectDereference
0x1400ec4fa  mov     eax, edi
0x1400ec4fc  mov     rcx, [rbp+1C0h+var_40]
0x1400ec503  xor     rcx, rsp; StackCookie
0x1400ec506  call    __security_check_cookie
0x1400ec50b  mov     rbx, [rsp+2C0h+arg_18]
0x1400ec513  add     rsp, 290h
0x1400ec51a  pop     r15
0x1400ec51c  pop     r14
0x1400ec51e  pop     r13
0x1400ec520  pop     r12
0x1400ec522  pop     rdi
0x1400ec523  pop     rsi
0x1400ec524  pop     rbp
0x1400ec525  retn
0x1400ec527  lea     rax, [rbp+1C0h+var_140]
0x1400ec52e  mov     dword ptr [rsp+2C0h+SourceString.Length], 1000000h
0x1400ec536  lea     r8, [rsp+2C0h+SourceString]
0x1400ec53b  mov     [rsp+2C0h+SourceString.Buffer], rax
0x1400ec540  lea     rdx, [rbp+1C0h+var_150]
0x1400ec544  mov     rcx, r14
0x1400ec547  call    GetDeviceId
0x1400ec54c  mov     edi, eax
0x1400ec54e  test    eax, eax
0x1400ec550  jnz     loc_1400EC5D8
0x1400ec556  xor     r8d, r8d
0x1400ec559  lea     rdx, [rbp+1C0h+var_150]
0x1400ec55d  xor     ecx, ecx
0x1400ec55f  call    VmsOmpFindSwitchByExtMiniportAdapterInfo
0x1400ec564  mov     rbx, rax
0x1400ec567  test    rax, rax
0x1400ec56a  jnz     short loc_1400EC573
0x1400ec56c  mov     edi, 0C0010011h
0x1400ec571  jmp     short loc_1400EC5E4
0x1400ec573  lea     rdx, [rsp+2C0h+MiniportAttributes]; MiniportAttributes
0x1400ec578  mov     qword ptr [rsp+2C0h+MiniportAttributes], 20019Eh
0x1400ec581  mov     rcx, r14; NdisMiniportHandle
0x1400ec584  mov     qword ptr [rbp+1C0h+MiniportAttributes+18h], r13
0x1400ec588  mov     qword ptr [rsp+2C0h+MiniportAttributes+10h], 20h ; ' '
0x1400ec591  mov     qword ptr [rsp+2C0h+MiniportAttributes+8], rbx
0x1400ec596  call    cs:__imp_NdisMSetMiniportAttributes
0x1400ec59d  nop     dword ptr [rax+rax+00h]
0x1400ec5a2  mov     edi, eax
0x1400ec5a4  test    eax, eax
0x1400ec5a6  jz      short loc_1400EC61D
0x1400ec5a8  mov     rcx, cs:VmsIfrLog
0x1400ec5af  mov     r9d, 1Dh
0x1400ec5b5  mov     dword ptr [rsp+2C0h+var_288], eax
0x1400ec5b9  mov     dl, 2
0x1400ec5bb  lea     rax, [rsp+2C0h+MiniportAttributes]
0x1400ec5c0  mov     [rsp+2C0h+var_290], rax
0x1400ec5c5  lea     r8d, [r9-9]
0x1400ec5c9  mov     [rsp+2C0h+var_298], r14
0x1400ec5ce  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec5d3  call    WPP_RECORDER_SF_qqd
0x1400ec5d8  cmp     edi, 0C0010011h
0x1400ec5de  jnz     loc_1400EC4B1
0x1400ec5e4  mov     rcx, cs:VmsIfrLog
0x1400ec5eb  mov     r9d, 20h ; ' '
0x1400ec5f1  mov     [rsp+2C0h+var_280], 0C0010011h
0x1400ec5f9  mov     dl, 3
0x1400ec5fb  mov     [rsp+2C0h+var_288], r15
0x1400ec600  mov     [rsp+2C0h+var_290], r12
0x1400ec605  lea     r8d, [r9-0Ch]
0x1400ec609  mov     [rsp+2C0h+var_298], r14
0x1400ec60e  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec613  call    WPP_RECORDER_SF_qqqd
0x1400ec618  jmp     loc_1400EC4E1
0x1400ec61d  xor     edx, edx; Val
0x1400ec61f  lea     rcx, [rbp+1C0h+MiniportAttributes+28h]; void *
0x1400ec623  mov     r8d, 0E0h; Size
0x1400ec629  call    memset
0x1400ec62e  mov     rax, 2540BE400h
0x1400ec638  mov     dword ptr [rbp+1C0h+MiniportAttributes+28h], 0E0019Fh
0x1400ec63f  mov     edx, 1
0x1400ec644  mov     qword ptr [rbp+1C0h+MiniportAttributes+40h], rax
0x1400ec648  mov     qword ptr [rbp+1C0h+MiniportAttributes+48h], rax
0x1400ec64c  mov     ecx, 5DCh
0x1400ec651  mov     qword ptr [rbp+1C0h+MiniportAttributes+50h], rax
0x1400ec655  mov     qword ptr [rbp+1C0h+MiniportAttributes+58h], rax
0x1400ec659  lea     eax, [rdx+5]
0x1400ec65c  mov     dword ptr [rbp+1C0h+MiniportAttributes+38h], ecx
0x1400ec65f  mov     word ptr [rbp+1C0h+MiniportAttributes+0DCh], ax
0x1400ec663  lea     rax, VmsMpCommonNdis63VspOids
0x1400ec66a  mov     qword ptr [rbp+1C0h+MiniportAttributes+60h], rdx
0x1400ec66e  mov     dword ptr [rbp+1C0h+MiniportAttributes+68h], ecx
0x1400ec671  mov     rcx, r14; NdisMiniportHandle
0x1400ec674  mov     dword ptr [rbp+1C0h+MiniportAttributes+0D8h], edx
0x1400ec677  lea     rdx, [rbp+1C0h+MiniportAttributes+28h]; MiniportAttributes
0x1400ec67b  mov     [rbp+1C0h+var_168], rax
0x1400ec67f  mov     qword ptr [rbp+1C0h+MiniportAttributes+30h], r13
0x1400ec683  mov     qword ptr [rbp+1C0h+MiniportAttributes+70h], r13
0x1400ec687  mov     dword ptr [rbp+1C0h+MiniportAttributes+78h], 8
0x1400ec68e  mov     dword ptr [rbp+1C0h+MiniportAttributes+7Ch], 2Fh ; '/'
0x1400ec695  mov     dword ptr [rbp+1C0h+MiniportAttributes+80h], 40h ; '@'
0x1400ec69c  mov     word ptr [rbp+1C0h+MiniportAttributes+84h], r13w
0x1400ec6a1  mov     qword ptr [rbp+1C0h+MiniportAttributes+0C8h], r13
0x1400ec6a5  mov     qword ptr [rbp+1C0h+MiniportAttributes+0D0h], 2
0x1400ec6ad  mov     byte ptr [rbp+1C0h+MiniportAttributes+0DEh], r13b
0x1400ec6b1  mov     [rbp+1C0h+var_178], 193540h
0x1400ec6b9  mov     [rbp+1C0h+var_170], r13
0x1400ec6bd  mov     [rbp+1C0h+var_160], 0F8h
0x1400ec6c4  call    cs:__imp_NdisMSetMiniportAttributes
0x1400ec6cb  nop     dword ptr [rax+rax+00h]
0x1400ec6d0  mov     edi, eax
0x1400ec6d2  test    eax, eax
0x1400ec6d4  jz      short loc_1400EC70A
0x1400ec6d6  mov     rcx, cs:VmsIfrLog
0x1400ec6dd  mov     r9d, 1Eh
0x1400ec6e3  mov     dword ptr [rsp+2C0h+var_288], eax
0x1400ec6e7  mov     dl, 2
0x1400ec6e9  lea     rax, [rbp+1C0h+MiniportAttributes+28h]
0x1400ec6ed  mov     [rsp+2C0h+var_290], rax
0x1400ec6f2  lea     r8d, [r9-0Ah]
0x1400ec6f6  mov     [rsp+2C0h+var_298], r14
0x1400ec6fb  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec700  call    WPP_RECORDER_SF_qqd
0x1400ec705  jmp     loc_1400EC5D8
0x1400ec70a  xor     r8d, r8d
0x1400ec70d  lea     rdx, [rsp+2C0h+LockState]
0x1400ec712  mov     rcx, rbx
0x1400ec715  call    VmsOmObjectLockExclusive
0x1400ec71a  lea     rax, [rbx+1208h]
0x1400ec721  mov     word ptr [rbx+11FAh], 200h
0x1400ec72a  lea     rcx, [rbx+11F8h]; DestinationString
0x1400ec731  mov     [rbx+1200h], rax
0x1400ec738  lea     rdx, [rsp+2C0h+SourceString]; SourceString
0x1400ec73d  mov     [rcx], r13w
0x1400ec741  call    cs:__imp_RtlCopyUnicodeString
0x1400ec748  nop     dword ptr [rax+rax+00h]
0x1400ec74d  mov     [rbx+10C8h], r14
0x1400ec754  mov     rax, [r15+28h]
0x1400ec758  mov     [rbx+1408h], rax
0x1400ec75f  mov     rax, [rbx+10D8h]
0x1400ec766  sub     rax, qword ptr [rbp+1C0h+var_150]
0x1400ec76a  jnz     short loc_1400EC777
0x1400ec76c  mov     rax, [rbx+10E0h]
0x1400ec773  sub     rax, qword ptr [rbp+1C0h+var_150+8]
0x1400ec777  lea     rsi, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ec77e  test    rax, rax
0x1400ec781  jz      short loc_1400EC7CC
0x1400ec783  mov     rcx, cs:VmsIfrLog
0x1400ec78a  lea     rax, aMemcmpObjswitc; "memcmp(&objSwitch->ExtensionStack.Minip"...
0x1400ec791  mov     r9d, 1Fh
0x1400ec797  mov     [rsp+2C0h+var_298], rax
0x1400ec79c  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec7a1  lea     r8d, [r9-0Ch]
0x1400ec7a5  call    WPP_RECORDER_SF_s
0x1400ec7aa  mov     rax, [rbx+10D8h]
0x1400ec7b1  sub     rax, qword ptr [rbp+1C0h+var_150]
0x1400ec7b5  jnz     short loc_1400EC7C2
0x1400ec7b7  mov     rax, [rbx+10E0h]
0x1400ec7be  sub     rax, qword ptr [rbp+1C0h+var_150+8]
0x1400ec7c2  test    rax, rax
0x1400ec7c5  jz      short loc_1400EC7CC
0x1400ec7c7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "memcmp(&objSwitch->ExtensionStack.MiniportDeviceId, &deviceId, sizeof(GUID)) == 0")
0x1400ec7cc  lea     rcx, [rbx+1418h]; Event
0x1400ec7d3  call    cs:__imp_NdisInitializeEvent
0x1400ec7da  nop     dword ptr [rax+rax+00h]
0x1400ec7df  lea     rax, [rbx+1450h]
0x1400ec7e6  mov     r14d, 1
0x1400ec7ec  mov     [rax+8], rax
0x1400ec7f0  lea     rdx, [rsp+2C0h+LockState]; LockState
0x1400ec7f5  mov     [rax], rax
0x1400ec7f8  mov     rcx, [rbx+38h]; Lock
0x1400ec7fc  mov     [rbx+10B4h], r14d
0x1400ec803  call    cs:__imp_NdisReleaseRWLock
0x1400ec80a  nop     dword ptr [rax+rax+00h]
0x1400ec80f  mov     rcx, [rbx+2388h]
0x1400ec816  lea     rax, [rsp+2C0h+SourceString]
0x1400ec81b  mov     [rsp+2C0h+var_290], rax
0x1400ec820  lea     r9d, [r14+21h]
0x1400ec824  mov     [rsp+2C0h+var_298], rbx
0x1400ec829  mov     r8d, r14d
0x1400ec82c  mov     [rsp+2C0h+var_2A0], rsi
0x1400ec831  call    WPP_RECORDER_SF_qZ
0x1400ec836  jmp     loc_1400EC4FA
```
