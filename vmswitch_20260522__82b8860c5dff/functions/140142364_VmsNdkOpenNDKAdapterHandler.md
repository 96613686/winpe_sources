# VmsNdkOpenNDKAdapterHandler

- ea: `0x140142364`
- end: `0x140142a17`
- name: `VmsNdkOpenNDKAdapterHandler`
- size: `1715`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400f83a0`

## callees

- `0x14001484c`
- `0x140014988`
- `0x140027a64`
- `0x14002e0f0`
- `0x1400313cc`
- `0x14003a450`
- `0x14003e804`
- `0x14004f5d8`
- `0x14006b084`
- `0x14008497c`
- `0x140089a04`
- `0x1400953e8`
- `0x14013b4cc`
- `0x140142364`
- `0x140143e68`
- `0x140144348`
- `0x14015bfb0`
- `0x140186eb4`
- `0x14018dd68`
- `0x1401bbc40`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x1401424db`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1401424db`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140142924`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140142924`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014293a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014293a`
- `ntoskrnl!ExAllocatePool2` at `0x140142485`
- `ntoskrnl!ExAllocatePool2` at `0x140142485`
- `NDIS!NdisOpenNDKAdapter` at `0x140142841`
- `NDIS!NdisOpenNDKAdapter` at `0x140142841`
- `NDIS!NdisReleaseRWLock` at `0x1401426c2`
- `NDIS!NdisReleaseRWLock` at `0x1401426e9`
- `NDIS!NdisReleaseRWLock` at `0x1401428ce`
- `NDIS!NdisReleaseRWLock` at `0x1401426c2`
- `NDIS!NdisReleaseRWLock` at `0x1401426e9`
- `NDIS!NdisReleaseRWLock` at `0x1401428ce`

## string_xrefs

- `0x140142621`: `Nic->NicSwitchVPort.ProtocolNic == parentSwitch->ProtocolNic`

## pseudocode

```c
__int64 __fastcall VmsNdkOpenNDKAdapterHandler(unsigned __int64 a1, _DWORD *a2, _QWORD *a3)
{
  _QWORD *Pool2; // r12
  __int64 v7; // r14
  BOOLEAN v8; // r15
  __int64 *v9; // rdx
  unsigned int v10; // esi
  unsigned int MappedNicIndexByObjNic; // edi
  int v12; // ecx
  int v13; // edx
  BOOLEAN v14; // al
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  int v18; // esi
  __int64 v19; // r15
  __int64 v20; // rdx
  int v21; // edx
  int v22; // edx
  __int64 v23; // r15
  int v24; // edx
  int v25; // edx
  __int64 v26; // r15
  unsigned int v27; // eax
  int v28; // r8d
  int v29; // r9d
  _QWORD *v30; // rdx
  __int64 v31; // rdx
  int v32; // edx
  int v33; // r8d
  int v35; // [rsp+20h] [rbp-49h]
  BOOLEAN v36; // [rsp+50h] [rbp-19h]
  char v37; // [rsp+51h] [rbp-18h]
  unsigned __int16 v38; // [rsp+54h] [rbp-15h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp-11h] BYREF
  struct _LOCK_STATE_EX v40; // [rsp+5Ch] [rbp-Dh] BYREF
  __int64 *v41; // [rsp+60h] [rbp-9h] BYREF
  _DWORD *v42; // [rsp+68h] [rbp-1h]
  __int64 v43; // [rsp+70h] [rbp+7h] BYREF
  int v44; // [rsp+78h] [rbp+Fh]

  v42 = a2;
  *a3 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_WORD *)&v40.OldIrql = 0;
  v40.Flags = 0;
  Pool2 = 0;
  v41 = 0;
  v7 = 0;
  v37 = 0;
  v8 = 0;
  v38 = 0;
  v9 = WPP_88abc93045f037d81f612a0177f0d10e_Traceguids;
  v43 = 0;
  v44 = 0;
  if ( !a1 )
  {
    v10 = 1;
    MappedNicIndexByObjNic = -1073741811;
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, (_DWORD)v9, 20, 52, (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids, 13);
    goto LABEL_49;
  }
  if ( !*(_DWORD *)(a1 + 4188) )
  {
    v10 = 4;
    MappedNicIndexByObjNic = -1073741811;
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, (_DWORD)v9, 20, 53, (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids, 13);
    goto LABEL_49;
  }
  v12 = *(_DWORD *)(a1 + 4764);
  if ( v12 != 3 )
  {
    v10 = 7;
    MappedNicIndexByObjNic = -1073741811;
    WPP_RECORDER_SF_Ld(
      VmsIfrLog,
      (unsigned int)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids,
      (_DWORD)a3,
      54,
      (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids,
      v12,
      13);
    goto LABEL_49;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(64, 24, 1299411798);
  if ( !Pool2 )
  {
    v10 = 12;
    MappedNicIndexByObjNic = -1073741670;
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_ld(VmsIfrNicLog, v13, 20, 55, (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids, 24, 154);
    goto LABEL_49;
  }
  v14 = ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 4872));
  v18 = *(_DWORD *)(a1 + 1872);
  v8 = v14;
  v36 = v14;
  if ( !v14 )
  {
    MappedNicIndexByObjNic = -1073741811;
    WPP_RECORDER_SF_Ldd(*(unsigned __int8 *)(a1 + 4072), v15, v16, v17);
    v10 = 3 - (v18 != 1);
    goto LABEL_49;
  }
  if ( v18 == 1 )
  {
    v10 = 0;
    if ( *(_BYTE *)(a1 + 4072) && *(_DWORD *)(a1 + 4188) && *(_DWORD *)(a1 + 4764) == 3 )
      goto LABEL_22;
  }
  else
  {
    v10 = 0;
  }
  WPP_RECORDER_SF_s(
    VmsIfrLog,
    v15,
    19,
    57,
    (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids,
    "(Nic->Type == VmsNicMiniport) && Nic->NicSwitchVPort.VPortAllocated && (Nic->NicSwitchVPort.VPortInfo.VPortId != NDI"
    "S_DEFAULT_VPORT_ID) && (Nic->NicNDKInfo.NdkState == VmsNdkCapabilitiesEnabled)");
  if ( *(_DWORD *)(a1 + 1872) != 1 || !*(_BYTE *)(a1 + 4072) || !*(_DWORD *)(a1 + 4188) || *(_DWORD *)(a1 + 4764) != 3 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
LABEL_22:
  v19 = *(_QWORD *)(a1 + 1888);
  LODWORD(v43) = *a2;
  v44 = *(_DWORD *)(a1 + 4188);
  if ( !v19 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v15,
      19,
      58,
      (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids,
      "parentSwitch != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  VmsOmObjectLockShared(v19, &LockState, 0);
  if ( *(_QWORD *)(a1 + 4168) != *(_QWORD *)(v19 + 4264) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v20,
      19,
      59,
      (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids,
      "Nic->NicSwitchVPort.ProtocolNic == parentSwitch->ProtocolNic");
    if ( *(_QWORD *)(a1 + 4168) != *(_QWORD *)(v19 + 4264) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v7 = *(_QWORD *)(a1 + 4168);
  if ( !v7 )
  {
    WPP_RECORDER_SF_s(VmsIfrLog, v20, 19, 60, (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids, "ptNic!= NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    MappedNicIndexByObjNic = -1073741823;
    v10 = 8;
    LOBYTE(v21) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v21, 20, 61, (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids, 1);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v19 + 56), &LockState);
LABEL_31:
    v8 = v36;
    goto LABEL_49;
  }
  LOBYTE(v20) = 1;
  VmsOmpObjectReference(*(_QWORD *)(a1 + 4168), v20);
  v37 = 1;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v19 + 56), &LockState);
  v23 = *(_QWORD *)(v7 + 3312);
  if ( !v23 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v22,
      19,
      62,
      (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids,
      "ptNicExt != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v10 = 9;
    MappedNicIndexByObjNic = -1073741811;
    LOBYTE(v24) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v24, 20, 63, (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids, 13);
    goto LABEL_31;
  }
  if ( !*(_QWORD *)(v23 + 112) )
  {
    v10 = 10;
    MappedNicIndexByObjNic = -1073741811;
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v22, 20, 64, (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids, 13);
    goto LABEL_31;
  }
  if ( !(unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(v7, 0) )
  {
    v26 = *(_QWORD *)(v23 + 112);
    goto LABEL_41;
  }
  MappedNicIndexByObjNic = VmsTmGetMappedNicIndexByObjNic(a1, 2, &v38);
  if ( !MappedNicIndexByObjNic )
  {
    MappedNicIndexByObjNic = VmsPtNicMuxReferenceMemberAdapterByIndex(v7, v38, 56, &v41);
    if ( MappedNicIndexByObjNic )
    {
      v10 = 15;
      goto LABEL_48;
    }
    v26 = *v41;
LABEL_41:
    if ( !v26 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v25,
        19,
        65,
        (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids,
        "ptNicHandle != NULL");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v27 = NdisOpenNDKAdapter(v26, &v43, a3);
    MappedNicIndexByObjNic = v27;
    if ( v27 )
    {
      v10 = 11;
      *a3 = 0;
      WPP_RECORDER_SF_qddLd(WORD1(v43), (unsigned __int16)v43, v28, v29, v35, v26, v43, SBYTE2(v43), v44, v27);
    }
    else
    {
      Pool2[2] = *a3;
      VmsOmObjectLockExclusive(a1, &v40, 0);
      v30 = *(_QWORD **)(a1 + 4832);
      if ( *v30 != a1 + 4824 )
        __fastfail(3u);
      Pool2[1] = v30;
      *Pool2 = a1 + 4824;
      *v30 = Pool2;
      *(_QWORD *)(a1 + 4832) = Pool2;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &v40);
    }
    goto LABEL_48;
  }
  v10 = 14;
LABEL_48:
  v8 = v36;
LABEL_49:
  if ( v41 )
    VmsOmNicDecrementControlCount(v7, v38, 56);
  VmsTraceLoggingNDKAdapterOpen(a1, &v43, MappedNicIndexByObjNic, v10);
  if ( MappedNicIndexByObjNic )
  {
    if ( v8 )
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 4872));
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    VmsEtwTraceNicNdkRequestNdkFailure(
      &HOST_VNIC_OPEN_NDK_ADAPTER_FAILED,
      v10,
      (a1 + 72) & ((unsigned __int128)-(__int128)a1 >> 64),
      (a1 + 616) & -(__int64)(a1 != 0),
      (v7 + 72) & -(__int64)(v7 != 0),
      (v7 + 616) & -(__int64)(v7 != 0));
    WPP_RECORDER_SF_qqLd(
      VmsIfrNicLog,
      v32,
      v33,
      67,
      (__int64)WPP_88abc93045f037d81f612a0177f0d10e_Traceguids,
      a1,
      (char)v42,
      v10,
      MappedNicIndexByObjNic);
  }
  if ( v37 )
  {
    LOBYTE(v31) = 1;
    VmsOmpObjectDereference(v7, v31);
  }
  return MappedNicIndexByObjNic;
}

```

## disassembly

```asm
0x140142364  mov     [rsp-8+arg_18], rbx
0x140142369  push    rbp
0x14014236a  push    rsi
0x14014236b  push    rdi
0x14014236c  push    r12
0x14014236e  push    r13
0x140142370  push    r14
0x140142372  push    r15
0x140142374  lea     rbp, [rsp-27h]
0x140142379  sub     rsp, 90h
0x140142380  mov     rax, cs:__security_cookie
0x140142387  xor     rax, rsp
0x14014238a  mov     [rbp+57h+var_40], rax
0x14014238e  xor     esi, esi
0x140142390  mov     [rbp+57h+var_58], rdx
0x140142394  xor     eax, eax
0x140142396  mov     [r8], rsi
0x140142399  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14014239d  mov     rdi, rdx
0x1401423a0  mov     [rbp+57h+LockState.Flags], al
0x1401423a3  mov     r13, r8
0x1401423a6  mov     word ptr [rbp+57h+var_64.OldIrql], ax
0x1401423aa  mov     rbx, rcx
0x1401423ad  mov     [rbp+57h+var_64.Flags], al
0x1401423b0  mov     r12d, esi
0x1401423b3  mov     [rbp+57h+var_60], rsi
0x1401423b7  mov     r14d, esi
0x1401423ba  mov     [rbp+57h+var_6F], sil
0x1401423be  mov     r15b, sil
0x1401423c1  mov     [rbp+57h+var_6C], si
0x1401423c5  lea     rdx, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x1401423cc  mov     [rbp+57h+var_50], rax
0x1401423d0  mov     [rbp+57h+var_48], eax
0x1401423d3  test    rcx, rcx
0x1401423d6  jnz     short loc_140142406
0x1401423d8  mov     eax, 0C000000Dh
0x1401423dd  lea     esi, [rcx+1]
0x1401423e0  mov     edi, eax
0x1401423e2  mov     dword ptr [rsp+0C0h+var_98], eax
0x1401423e6  lea     r9d, [rcx+34h]
0x1401423ea  mov     qword ptr [rsp+0C0h+var_A0], rdx
0x1401423ef  lea     r8d, [rcx+14h]
0x1401423f3  mov     rcx, cs:VmsIfrLog
0x1401423fa  mov     dl, 2
0x1401423fc  call    WPP_RECORDER_SF_d
0x140142401  jmp     loc_1401428DE
0x140142406  cmp     [rcx+105Ch], esi
0x14014240c  jnz     short loc_14014243E
0x14014240e  mov     eax, 0C000000Dh
0x140142413  mov     esi, 4
0x140142418  mov     edi, eax
0x14014241a  mov     rcx, cs:VmsIfrLog
0x140142421  lea     r9d, [rsi+31h]
0x140142425  mov     dword ptr [rsp+0C0h+var_98], eax
0x140142429  lea     r8d, [rsi+10h]
0x14014242d  mov     qword ptr [rsp+0C0h+var_A0], rdx
0x140142432  mov     dl, 2
0x140142434  call    WPP_RECORDER_SF_d
0x140142439  jmp     loc_1401428DE
0x14014243e  mov     ecx, [rcx+129Ch]
0x140142444  cmp     ecx, 3
0x140142447  jz      short loc_140142477
0x140142449  mov     eax, 0C000000Dh
0x14014244e  mov     esi, 7
0x140142453  mov     edi, eax
0x140142455  mov     dword ptr [rsp+0C0h+var_90], eax
0x140142459  lea     r9d, [rsi+2Fh]
0x14014245d  mov     dword ptr [rsp+0C0h+var_98], ecx
0x140142461  mov     rcx, cs:VmsIfrLog
0x140142468  mov     qword ptr [rsp+0C0h+var_A0], rdx
0x14014246d  call    WPP_RECORDER_SF_Ld
0x140142472  jmp     loc_1401428DE
0x140142477  mov     edx, 18h
0x14014247c  mov     r8d, 4D737356h
0x140142482  lea     ecx, [rdx+28h]
0x140142485  call    cs:__imp_ExAllocatePool2
0x14014248c  nop     dword ptr [rax+rax+00h]
0x140142491  mov     r12, rax
0x140142494  test    rax, rax
0x140142497  jnz     short loc_1401424D4
0x140142499  lea     esi, [rax+0Ch]
0x14014249c  mov     edi, 0C000009Ah
0x1401424a1  mov     rcx, cs:VmsIfrNicLog
0x1401424a8  lea     r13, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x1401424af  mov     dword ptr [rsp+0C0h+var_90], edi
0x1401424b3  lea     r9d, [rax+37h]
0x1401424b7  mov     dword ptr [rsp+0C0h+var_98], 18h
0x1401424bf  lea     r8d, [rax+14h]
0x1401424c3  mov     dl, 2
0x1401424c5  mov     qword ptr [rsp+0C0h+var_A0], r13
0x1401424ca  call    WPP_RECORDER_SF_ld
0x1401424cf  jmp     loc_1401428E5
0x1401424d4  lea     rcx, [rbx+1308h]; RunRef
0x1401424db  call    cs:__imp_ExAcquireRundownProtection
0x1401424e2  nop     dword ptr [rax+rax+00h]
0x1401424e7  mov     esi, [rbx+750h]
0x1401424ed  mov     r15b, al
0x1401424f0  mov     [rbp+57h+var_70], al
0x1401424f3  test    al, al
0x1401424f5  jnz     short loc_14014251E
0x1401424f7  mov     edi, 0C000000Dh
0x1401424fc  movzx   ecx, byte ptr [rbx+0FE8h]
0x140142503  mov     dword ptr [rsp+0C0h+var_90], ecx
0x140142507  mov     dword ptr [rsp+0C0h+var_98], esi
0x14014250b  call    WPP_RECORDER_SF_Ldd
0x140142510  dec     esi
0x140142512  neg     esi
0x140142514  sbb     esi, esi
0x140142516  add     esi, 3
0x140142519  jmp     loc_1401428DE
0x14014251e  mov     r14d, 13h
0x140142524  cmp     esi, 1
0x140142527  jnz     short loc_140142547
0x140142529  xor     esi, esi
0x14014252b  cmp     [rbx+0FE8h], sil
0x140142532  jz      short loc_140142549
0x140142534  cmp     [rbx+105Ch], esi
0x14014253a  jz      short loc_140142549
0x14014253c  cmp     dword ptr [rbx+129Ch], 3
0x140142543  jz      short loc_14014259E
0x140142545  jmp     short loc_140142549
0x140142547  xor     esi, esi
0x140142549  mov     rcx, cs:VmsIfrLog
0x140142550  lea     rax, aNicTypeVmsnicm_2; "(Nic->Type == VmsNicMiniport) && Nic->N"...
0x140142557  mov     [rsp+0C0h+var_98], rax
0x14014255c  mov     r9d, 39h ; '9'
0x140142562  lea     rax, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x140142569  mov     r8d, r14d
0x14014256c  mov     qword ptr [rsp+0C0h+var_A0], rax
0x140142571  call    WPP_RECORDER_SF_s
0x140142576  cmp     dword ptr [rbx+750h], 1
0x14014257d  jnz     short loc_140142599
0x14014257f  cmp     [rbx+0FE8h], sil
0x140142586  jz      short loc_140142599
0x140142588  cmp     [rbx+105Ch], esi
0x14014258e  jz      short loc_140142599
0x140142590  cmp     dword ptr [rbx+129Ch], 3
0x140142597  jz      short loc_14014259E
0x140142599  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(Nic->Type == VmsNicMiniport) && Nic->NicSwitchVPort.VPortAllocated && (Nic->NicSwitchVPort.VPortInfo.VPortId != 0) && (Nic->NicNDKInfo.NdkState == VmsNdkCapabilitiesEnabled)")
0x14014259e  movzx   eax, word ptr [rdi]
0x1401425a1  mov     r15, [rbx+760h]
0x1401425a8  mov     word ptr [rbp+57h+var_50], ax
0x1401425ac  movzx   eax, word ptr [rdi+2]
0x1401425b0  mov     word ptr [rbp+57h+var_50+2], ax
0x1401425b4  mov     eax, [rbx+105Ch]
0x1401425ba  mov     [rbp+57h+var_48], eax
0x1401425bd  test    r15, r15
0x1401425c0  jnz     short loc_1401425F4
0x1401425c2  mov     rcx, cs:VmsIfrLog
0x1401425c9  lea     rax, aParentswitchNu_0; "parentSwitch != NULL"
0x1401425d0  mov     [rsp+0C0h+var_98], rax
0x1401425d5  lea     rdi, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x1401425dc  lea     r9d, [r15+3Ah]
0x1401425e0  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x1401425e5  mov     r8d, r14d
0x1401425e8  call    WPP_RECORDER_SF_s
0x1401425ed  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "parentSwitch != ((void *)0)")
0x1401425f2  jmp     short loc_1401425FB
0x1401425f4  lea     rdi, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x1401425fb  xor     r8d, r8d
0x1401425fe  lea     rdx, [rbp+57h+LockState]
0x140142602  mov     rcx, r15
0x140142605  call    VmsOmObjectLockShared
0x14014260a  mov     rax, [r15+10A8h]
0x140142611  cmp     [rbx+1048h], rax
0x140142618  jz      short loc_140142655
0x14014261a  mov     rcx, cs:VmsIfrLog
0x140142621  lea     rax, aNicNicswitchvp_0; "Nic->NicSwitchVPort.ProtocolNic == pare"...
0x140142628  mov     [rsp+0C0h+var_98], rax
0x14014262d  mov     r9d, 3Bh ; ';'
0x140142633  mov     r8d, r14d
0x140142636  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x14014263b  call    WPP_RECORDER_SF_s
0x140142640  mov     rax, [r15+10A8h]
0x140142647  cmp     [rbx+1048h], rax
0x14014264e  jz      short loc_140142655
0x140142650  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->NicSwitchVPort.ProtocolNic == parentSwitch->ProtocolNic")
0x140142655  mov     r14, [rbx+1048h]
0x14014265c  test    r14, r14
0x14014265f  jnz     short loc_1401426D3
0x140142661  mov     rcx, cs:VmsIfrLog
0x140142668  lea     rax, aPtnicNull; "ptNic!= NULL"
0x14014266f  mov     [rsp+0C0h+var_98], rax
0x140142674  lea     r9d, [r14+3Ch]
0x140142678  lea     r8d, [r14+13h]
0x14014267c  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x140142681  call    WPP_RECORDER_SF_s
0x140142686  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ptNic!= ((void *)0)")
0x14014268b  mov     edi, 0C0000001h
0x140142690  lea     esi, [r14+8]
0x140142694  mov     rcx, cs:VmsIfrLog
0x14014269b  lea     r13, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x1401426a2  lea     r9d, [r14+3Dh]
0x1401426a6  mov     dword ptr [rsp+0C0h+var_98], edi
0x1401426aa  lea     r8d, [r14+14h]
0x1401426ae  mov     qword ptr [rsp+0C0h+var_A0], r13
0x1401426b3  mov     dl, 2
0x1401426b5  call    WPP_RECORDER_SF_d
0x1401426ba  mov     rcx, [r15+38h]; Lock
0x1401426be  lea     rdx, [rbp+57h+LockState]; LockState
0x1401426c2  call    cs:__imp_NdisReleaseRWLock
0x1401426c9  nop     dword ptr [rax+rax+00h]
0x1401426ce  jmp     loc_14014275C
0x1401426d3  mov     dl, 1
0x1401426d5  mov     rcx, r14
0x1401426d8  call    VmsOmpObjectReference
0x1401426dd  mov     rcx, [r15+38h]; Lock
0x1401426e1  lea     rdx, [rbp+57h+LockState]; LockState
0x1401426e5  mov     [rbp+57h+var_6F], 1
0x1401426e9  call    cs:__imp_NdisReleaseRWLock
0x1401426f0  nop     dword ptr [rax+rax+00h]
0x1401426f5  mov     r15, [r14+0CF0h]
0x1401426fc  test    r15, r15
0x1401426ff  jnz     short loc_140142765
0x140142701  mov     rcx, cs:VmsIfrLog
0x140142708  lea     rax, aPtnicextNull_0; "ptNicExt != NULL"
0x14014270f  mov     [rsp+0C0h+var_98], rax
0x140142714  lea     r9d, [r15+3Eh]
0x140142718  lea     r8d, [r15+13h]
0x14014271c  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x140142721  call    WPP_RECORDER_SF_s
0x140142726  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ptNicExt != ((void *)0)")
0x14014272b  mov     eax, 0C000000Dh
0x140142730  lea     esi, [r15+9]
0x140142734  mov     edi, eax
0x140142736  mov     rcx, cs:VmsIfrLog
0x14014273d  lea     r13, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x140142744  mov     dword ptr [rsp+0C0h+var_98], eax
0x140142748  lea     r9d, [r15+3Fh]
0x14014274c  lea     r8d, [r15+14h]
0x140142750  mov     qword ptr [rsp+0C0h+var_A0], r13
0x140142755  mov     dl, 2
0x140142757  call    WPP_RECORDER_SF_d
0x14014275c  mov     r15b, [rbp+57h+var_70]
0x140142760  jmp     loc_1401428E5
0x140142765  cmp     [r15+70h], rsi
0x140142769  jnz     short loc_14014279F
0x14014276b  mov     eax, 0C000000Dh
0x140142770  mov     esi, 0Ah
0x140142775  mov     edi, eax
0x140142777  mov     rcx, cs:VmsIfrLog
0x14014277e  lea     r13, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x140142785  mov     dword ptr [rsp+0C0h+var_98], eax
0x140142789  lea     r9d, [rsi+36h]
0x14014278d  lea     r8d, [rsi+0Ah]
0x140142791  mov     qword ptr [rsp+0C0h+var_A0], r13
0x140142796  mov     dl, 2
0x140142798  call    WPP_RECORDER_SF_d
0x14014279d  jmp     short loc_14014275C
0x14014279f  xor     edx, edx
0x1401427a1  mov     rcx, r14
0x1401427a4  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1401427a9  test    al, al
0x1401427ab  jz      short loc_1401427FD
0x1401427ad  lea     r8, [rbp+57h+var_6C]
0x1401427b1  mov     edx, 2
0x1401427b6  mov     rcx, rbx
0x1401427b9  call    VmsTmGetMappedNicIndexByObjNic
0x1401427be  mov     edi, eax
0x1401427c0  test    eax, eax
0x1401427c2  jz      short loc_1401427CE
0x1401427c4  mov     esi, 0Eh
0x1401427c9  jmp     loc_1401428DA
0x1401427ce  movzx   edx, [rbp+57h+var_6C]
0x1401427d2  lea     r9, [rbp+57h+var_60]
0x1401427d6  mov     r8d, 38h ; '8'
0x1401427dc  mov     rcx, r14
0x1401427df  call    VmsPtNicMuxReferenceMemberAdapterByIndex
0x1401427e4  mov     edi, eax
0x1401427e6  test    eax, eax
0x1401427e8  jz      short loc_1401427F4
0x1401427ea  mov     esi, 0Fh
0x1401427ef  jmp     loc_1401428DA
0x1401427f4  mov     rax, [rbp+57h+var_60]
0x1401427f8  mov     r15, [rax]
0x1401427fb  jmp     short loc_140142801
0x1401427fd  mov     r15, [r15+70h]
0x140142801  test    r15, r15
0x140142804  jnz     short loc_140142837
0x140142806  mov     rcx, cs:VmsIfrLog
0x14014280d  lea     rax, aPtnichandleNul; "ptNicHandle != NULL"
0x140142814  mov     [rsp+0C0h+var_98], rax
0x140142819  lea     r9d, [r15+41h]
0x14014281d  lea     rax, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x140142824  lea     r8d, [r15+13h]
0x140142828  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14014282d  call    WPP_RECORDER_SF_s
0x140142832  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ptNicHandle != ((void *)0)")
0x140142837  mov     r8, r13
0x14014283a  lea     rdx, [rbp+57h+var_50]
0x14014283e  mov     rcx, r15
0x140142841  call    cs:__imp_NdisOpenNDKAdapter
0x140142848  nop     dword ptr [rax+rax+00h]
0x14014284d  mov     edi, eax
0x14014284f  test    eax, eax
0x140142851  jz      short loc_140142887
0x140142853  mov     esi, 0Bh
0x140142858  mov     qword ptr [r13+0], 0
0x140142860  movzx   ecx, word ptr [rbp+57h+var_50+2]
0x140142864  movzx   edx, word ptr [rbp+57h+var_50]
  ... truncated ...
```
