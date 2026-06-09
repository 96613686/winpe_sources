# VmsNdkOpenNDKAdapterHandler

- ea: `0x1401423d4`
- end: `0x140142a87`
- name: `VmsNdkOpenNDKAdapterHandler`
- size: `1715`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400f8410`

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
- `0x14013b53c`
- `0x1401423d4`
- `0x140143ed8`
- `0x1401443b8`
- `0x14015c020`
- `0x140186f24`
- `0x14018ddd8`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14014254b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14014254b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140142994`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140142994`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401429aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401429aa`
- `ntoskrnl!ExAllocatePool2` at `0x1401424f5`
- `ntoskrnl!ExAllocatePool2` at `0x1401424f5`
- `NDIS!NdisOpenNDKAdapter` at `0x1401428b1`
- `NDIS!NdisOpenNDKAdapter` at `0x1401428b1`
- `NDIS!NdisReleaseRWLock` at `0x140142732`
- `NDIS!NdisReleaseRWLock` at `0x140142759`
- `NDIS!NdisReleaseRWLock` at `0x14014293e`
- `NDIS!NdisReleaseRWLock` at `0x140142732`
- `NDIS!NdisReleaseRWLock` at `0x140142759`
- `NDIS!NdisReleaseRWLock` at `0x14014293e`

## string_xrefs

- `0x140142691`: `Nic->NicSwitchVPort.ProtocolNic == parentSwitch->ProtocolNic`

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
0x1401423d4  mov     [rsp-8+arg_18], rbx
0x1401423d9  push    rbp
0x1401423da  push    rsi
0x1401423db  push    rdi
0x1401423dc  push    r12
0x1401423de  push    r13
0x1401423e0  push    r14
0x1401423e2  push    r15
0x1401423e4  lea     rbp, [rsp-27h]
0x1401423e9  sub     rsp, 90h
0x1401423f0  mov     rax, cs:__security_cookie
0x1401423f7  xor     rax, rsp
0x1401423fa  mov     [rbp+57h+var_40], rax
0x1401423fe  xor     esi, esi
0x140142400  mov     [rbp+57h+var_58], rdx
0x140142404  xor     eax, eax
0x140142406  mov     [r8], rsi
0x140142409  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14014240d  mov     rdi, rdx
0x140142410  mov     [rbp+57h+LockState.Flags], al
0x140142413  mov     r13, r8
0x140142416  mov     word ptr [rbp+57h+var_64.OldIrql], ax
0x14014241a  mov     rbx, rcx
0x14014241d  mov     [rbp+57h+var_64.Flags], al
0x140142420  mov     r12d, esi
0x140142423  mov     [rbp+57h+var_60], rsi
0x140142427  mov     r14d, esi
0x14014242a  mov     [rbp+57h+var_6F], sil
0x14014242e  mov     r15b, sil
0x140142431  mov     [rbp+57h+var_6C], si
0x140142435  lea     rdx, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x14014243c  mov     [rbp+57h+var_50], rax
0x140142440  mov     [rbp+57h+var_48], eax
0x140142443  test    rcx, rcx
0x140142446  jnz     short loc_140142476
0x140142448  mov     eax, 0C000000Dh
0x14014244d  lea     esi, [rcx+1]
0x140142450  mov     edi, eax
0x140142452  mov     dword ptr [rsp+0C0h+var_98], eax
0x140142456  lea     r9d, [rcx+34h]
0x14014245a  mov     qword ptr [rsp+0C0h+var_A0], rdx
0x14014245f  lea     r8d, [rcx+14h]
0x140142463  mov     rcx, cs:VmsIfrLog
0x14014246a  mov     dl, 2
0x14014246c  call    WPP_RECORDER_SF_d
0x140142471  jmp     loc_14014294E
0x140142476  cmp     [rcx+105Ch], esi
0x14014247c  jnz     short loc_1401424AE
0x14014247e  mov     eax, 0C000000Dh
0x140142483  mov     esi, 4
0x140142488  mov     edi, eax
0x14014248a  mov     rcx, cs:VmsIfrLog
0x140142491  lea     r9d, [rsi+31h]
0x140142495  mov     dword ptr [rsp+0C0h+var_98], eax
0x140142499  lea     r8d, [rsi+10h]
0x14014249d  mov     qword ptr [rsp+0C0h+var_A0], rdx
0x1401424a2  mov     dl, 2
0x1401424a4  call    WPP_RECORDER_SF_d
0x1401424a9  jmp     loc_14014294E
0x1401424ae  mov     ecx, [rcx+129Ch]
0x1401424b4  cmp     ecx, 3
0x1401424b7  jz      short loc_1401424E7
0x1401424b9  mov     eax, 0C000000Dh
0x1401424be  mov     esi, 7
0x1401424c3  mov     edi, eax
0x1401424c5  mov     dword ptr [rsp+0C0h+var_90], eax
0x1401424c9  lea     r9d, [rsi+2Fh]
0x1401424cd  mov     dword ptr [rsp+0C0h+var_98], ecx
0x1401424d1  mov     rcx, cs:VmsIfrLog
0x1401424d8  mov     qword ptr [rsp+0C0h+var_A0], rdx
0x1401424dd  call    WPP_RECORDER_SF_Ld
0x1401424e2  jmp     loc_14014294E
0x1401424e7  mov     edx, 18h
0x1401424ec  mov     r8d, 4D737356h
0x1401424f2  lea     ecx, [rdx+28h]
0x1401424f5  call    cs:__imp_ExAllocatePool2
0x1401424fc  nop     dword ptr [rax+rax+00h]
0x140142501  mov     r12, rax
0x140142504  test    rax, rax
0x140142507  jnz     short loc_140142544
0x140142509  lea     esi, [rax+0Ch]
0x14014250c  mov     edi, 0C000009Ah
0x140142511  mov     rcx, cs:VmsIfrNicLog
0x140142518  lea     r13, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x14014251f  mov     dword ptr [rsp+0C0h+var_90], edi
0x140142523  lea     r9d, [rax+37h]
0x140142527  mov     dword ptr [rsp+0C0h+var_98], 18h
0x14014252f  lea     r8d, [rax+14h]
0x140142533  mov     dl, 2
0x140142535  mov     qword ptr [rsp+0C0h+var_A0], r13
0x14014253a  call    WPP_RECORDER_SF_ld
0x14014253f  jmp     loc_140142955
0x140142544  lea     rcx, [rbx+1308h]; RunRef
0x14014254b  call    cs:__imp_ExAcquireRundownProtection
0x140142552  nop     dword ptr [rax+rax+00h]
0x140142557  mov     esi, [rbx+750h]
0x14014255d  mov     r15b, al
0x140142560  mov     [rbp+57h+var_70], al
0x140142563  test    al, al
0x140142565  jnz     short loc_14014258E
0x140142567  mov     edi, 0C000000Dh
0x14014256c  movzx   ecx, byte ptr [rbx+0FE8h]
0x140142573  mov     dword ptr [rsp+0C0h+var_90], ecx
0x140142577  mov     dword ptr [rsp+0C0h+var_98], esi
0x14014257b  call    WPP_RECORDER_SF_Ldd
0x140142580  dec     esi
0x140142582  neg     esi
0x140142584  sbb     esi, esi
0x140142586  add     esi, 3
0x140142589  jmp     loc_14014294E
0x14014258e  mov     r14d, 13h
0x140142594  cmp     esi, 1
0x140142597  jnz     short loc_1401425B7
0x140142599  xor     esi, esi
0x14014259b  cmp     [rbx+0FE8h], sil
0x1401425a2  jz      short loc_1401425B9
0x1401425a4  cmp     [rbx+105Ch], esi
0x1401425aa  jz      short loc_1401425B9
0x1401425ac  cmp     dword ptr [rbx+129Ch], 3
0x1401425b3  jz      short loc_14014260E
0x1401425b5  jmp     short loc_1401425B9
0x1401425b7  xor     esi, esi
0x1401425b9  mov     rcx, cs:VmsIfrLog
0x1401425c0  lea     rax, aNicTypeVmsnicm_2; "(Nic->Type == VmsNicMiniport) && Nic->N"...
0x1401425c7  mov     [rsp+0C0h+var_98], rax
0x1401425cc  mov     r9d, 39h ; '9'
0x1401425d2  lea     rax, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x1401425d9  mov     r8d, r14d
0x1401425dc  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1401425e1  call    WPP_RECORDER_SF_s
0x1401425e6  cmp     dword ptr [rbx+750h], 1
0x1401425ed  jnz     short loc_140142609
0x1401425ef  cmp     [rbx+0FE8h], sil
0x1401425f6  jz      short loc_140142609
0x1401425f8  cmp     [rbx+105Ch], esi
0x1401425fe  jz      short loc_140142609
0x140142600  cmp     dword ptr [rbx+129Ch], 3
0x140142607  jz      short loc_14014260E
0x140142609  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(Nic->Type == VmsNicMiniport) && Nic->NicSwitchVPort.VPortAllocated && (Nic->NicSwitchVPort.VPortInfo.VPortId != 0) && (Nic->NicNDKInfo.NdkState == VmsNdkCapabilitiesEnabled)")
0x14014260e  movzx   eax, word ptr [rdi]
0x140142611  mov     r15, [rbx+760h]
0x140142618  mov     word ptr [rbp+57h+var_50], ax
0x14014261c  movzx   eax, word ptr [rdi+2]
0x140142620  mov     word ptr [rbp+57h+var_50+2], ax
0x140142624  mov     eax, [rbx+105Ch]
0x14014262a  mov     [rbp+57h+var_48], eax
0x14014262d  test    r15, r15
0x140142630  jnz     short loc_140142664
0x140142632  mov     rcx, cs:VmsIfrLog
0x140142639  lea     rax, aParentswitchNu_0; "parentSwitch != NULL"
0x140142640  mov     [rsp+0C0h+var_98], rax
0x140142645  lea     rdi, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x14014264c  lea     r9d, [r15+3Ah]
0x140142650  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x140142655  mov     r8d, r14d
0x140142658  call    WPP_RECORDER_SF_s
0x14014265d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "parentSwitch != ((void *)0)")
0x140142662  jmp     short loc_14014266B
0x140142664  lea     rdi, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x14014266b  xor     r8d, r8d
0x14014266e  lea     rdx, [rbp+57h+LockState]
0x140142672  mov     rcx, r15
0x140142675  call    VmsOmObjectLockShared
0x14014267a  mov     rax, [r15+10A8h]
0x140142681  cmp     [rbx+1048h], rax
0x140142688  jz      short loc_1401426C5
0x14014268a  mov     rcx, cs:VmsIfrLog
0x140142691  lea     rax, aNicNicswitchvp_0; "Nic->NicSwitchVPort.ProtocolNic == pare"...
0x140142698  mov     [rsp+0C0h+var_98], rax
0x14014269d  mov     r9d, 3Bh ; ';'
0x1401426a3  mov     r8d, r14d
0x1401426a6  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x1401426ab  call    WPP_RECORDER_SF_s
0x1401426b0  mov     rax, [r15+10A8h]
0x1401426b7  cmp     [rbx+1048h], rax
0x1401426be  jz      short loc_1401426C5
0x1401426c0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->NicSwitchVPort.ProtocolNic == parentSwitch->ProtocolNic")
0x1401426c5  mov     r14, [rbx+1048h]
0x1401426cc  test    r14, r14
0x1401426cf  jnz     short loc_140142743
0x1401426d1  mov     rcx, cs:VmsIfrLog
0x1401426d8  lea     rax, aPtnicNull; "ptNic!= NULL"
0x1401426df  mov     [rsp+0C0h+var_98], rax
0x1401426e4  lea     r9d, [r14+3Ch]
0x1401426e8  lea     r8d, [r14+13h]
0x1401426ec  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x1401426f1  call    WPP_RECORDER_SF_s
0x1401426f6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ptNic!= ((void *)0)")
0x1401426fb  mov     edi, 0C0000001h
0x140142700  lea     esi, [r14+8]
0x140142704  mov     rcx, cs:VmsIfrLog
0x14014270b  lea     r13, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x140142712  lea     r9d, [r14+3Dh]
0x140142716  mov     dword ptr [rsp+0C0h+var_98], edi
0x14014271a  lea     r8d, [r14+14h]
0x14014271e  mov     qword ptr [rsp+0C0h+var_A0], r13
0x140142723  mov     dl, 2
0x140142725  call    WPP_RECORDER_SF_d
0x14014272a  mov     rcx, [r15+38h]; Lock
0x14014272e  lea     rdx, [rbp+57h+LockState]; LockState
0x140142732  call    cs:__imp_NdisReleaseRWLock
0x140142739  nop     dword ptr [rax+rax+00h]
0x14014273e  jmp     loc_1401427CC
0x140142743  mov     dl, 1
0x140142745  mov     rcx, r14
0x140142748  call    VmsOmpObjectReference
0x14014274d  mov     rcx, [r15+38h]; Lock
0x140142751  lea     rdx, [rbp+57h+LockState]; LockState
0x140142755  mov     [rbp+57h+var_6F], 1
0x140142759  call    cs:__imp_NdisReleaseRWLock
0x140142760  nop     dword ptr [rax+rax+00h]
0x140142765  mov     r15, [r14+0CF0h]
0x14014276c  test    r15, r15
0x14014276f  jnz     short loc_1401427D5
0x140142771  mov     rcx, cs:VmsIfrLog
0x140142778  lea     rax, aPtnicextNull_0; "ptNicExt != NULL"
0x14014277f  mov     [rsp+0C0h+var_98], rax
0x140142784  lea     r9d, [r15+3Eh]
0x140142788  lea     r8d, [r15+13h]
0x14014278c  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x140142791  call    WPP_RECORDER_SF_s
0x140142796  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ptNicExt != ((void *)0)")
0x14014279b  mov     eax, 0C000000Dh
0x1401427a0  lea     esi, [r15+9]
0x1401427a4  mov     edi, eax
0x1401427a6  mov     rcx, cs:VmsIfrLog
0x1401427ad  lea     r13, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x1401427b4  mov     dword ptr [rsp+0C0h+var_98], eax
0x1401427b8  lea     r9d, [r15+3Fh]
0x1401427bc  lea     r8d, [r15+14h]
0x1401427c0  mov     qword ptr [rsp+0C0h+var_A0], r13
0x1401427c5  mov     dl, 2
0x1401427c7  call    WPP_RECORDER_SF_d
0x1401427cc  mov     r15b, [rbp+57h+var_70]
0x1401427d0  jmp     loc_140142955
0x1401427d5  cmp     [r15+70h], rsi
0x1401427d9  jnz     short loc_14014280F
0x1401427db  mov     eax, 0C000000Dh
0x1401427e0  mov     esi, 0Ah
0x1401427e5  mov     edi, eax
0x1401427e7  mov     rcx, cs:VmsIfrLog
0x1401427ee  lea     r13, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x1401427f5  mov     dword ptr [rsp+0C0h+var_98], eax
0x1401427f9  lea     r9d, [rsi+36h]
0x1401427fd  lea     r8d, [rsi+0Ah]
0x140142801  mov     qword ptr [rsp+0C0h+var_A0], r13
0x140142806  mov     dl, 2
0x140142808  call    WPP_RECORDER_SF_d
0x14014280d  jmp     short loc_1401427CC
0x14014280f  xor     edx, edx
0x140142811  mov     rcx, r14
0x140142814  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x140142819  test    al, al
0x14014281b  jz      short loc_14014286D
0x14014281d  lea     r8, [rbp+57h+var_6C]
0x140142821  mov     edx, 2
0x140142826  mov     rcx, rbx
0x140142829  call    VmsTmGetMappedNicIndexByObjNic
0x14014282e  mov     edi, eax
0x140142830  test    eax, eax
0x140142832  jz      short loc_14014283E
0x140142834  mov     esi, 0Eh
0x140142839  jmp     loc_14014294A
0x14014283e  movzx   edx, [rbp+57h+var_6C]
0x140142842  lea     r9, [rbp+57h+var_60]
0x140142846  mov     r8d, 38h ; '8'
0x14014284c  mov     rcx, r14
0x14014284f  call    VmsPtNicMuxReferenceMemberAdapterByIndex
0x140142854  mov     edi, eax
0x140142856  test    eax, eax
0x140142858  jz      short loc_140142864
0x14014285a  mov     esi, 0Fh
0x14014285f  jmp     loc_14014294A
0x140142864  mov     rax, [rbp+57h+var_60]
0x140142868  mov     r15, [rax]
0x14014286b  jmp     short loc_140142871
0x14014286d  mov     r15, [r15+70h]
0x140142871  test    r15, r15
0x140142874  jnz     short loc_1401428A7
0x140142876  mov     rcx, cs:VmsIfrLog
0x14014287d  lea     rax, aPtnichandleNul; "ptNicHandle != NULL"
0x140142884  mov     [rsp+0C0h+var_98], rax
0x140142889  lea     r9d, [r15+41h]
0x14014288d  lea     rax, WPP_88abc93045f037d81f612a0177f0d10e_Traceguids
0x140142894  lea     r8d, [r15+13h]
0x140142898  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14014289d  call    WPP_RECORDER_SF_s
0x1401428a2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ptNicHandle != ((void *)0)")
0x1401428a7  mov     r8, r13
0x1401428aa  lea     rdx, [rbp+57h+var_50]
0x1401428ae  mov     rcx, r15
0x1401428b1  call    cs:__imp_NdisOpenNDKAdapter
0x1401428b8  nop     dword ptr [rax+rax+00h]
0x1401428bd  mov     edi, eax
0x1401428bf  test    eax, eax
0x1401428c1  jz      short loc_1401428F7
0x1401428c3  mov     esi, 0Bh
0x1401428c8  mov     qword ptr [r13+0], 0
0x1401428d0  movzx   ecx, word ptr [rbp+57h+var_50+2]
0x1401428d4  movzx   edx, word ptr [rbp+57h+var_50]
  ... truncated ...
```
