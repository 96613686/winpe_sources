# VmsDIoNicPvtWrite

- ea: `0x1400ea6a0`
- end: `0x1400ead01`
- name: `VmsDIoNicPvtWrite`
- size: `1633`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000accc`
- `0x1400132b0`
- `0x1400147e0`
- `0x14001736c`
- `0x140027a64`
- `0x14002ca0c`
- `0x14002e0f0`
- `0x14002fe4c`
- `0x1400313cc`
- `0x14003c378`
- `0x14003e9e4`
- `0x140046f1c`
- `0x140051528`
- `0x14005fc3c`
- `0x14006b120`
- `0x14008497c`
- `0x1400ea6a0`
- `0x140114a0c`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400eaa69`
- `ntoskrnl!IoFreeMdl` at `0x1400eaa69`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ea88b`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ea88b`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea835`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea835`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ea8bf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ea8bf`
- `NDIS!NdisReleaseRWLock` at `0x1400eabee`
- `NDIS!NdisReleaseRWLock` at `0x1400eabee`
- `NDIS!NdisGetDataBuffer` at `0x1400ea9f6`
- `NDIS!NdisGetDataBuffer` at `0x1400ea9f6`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400eaa44`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400eaa44`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400ea998`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400ea998`

## string_xrefs

- `0x1400ea7b0`: `dataLength == irpSp->Parameters.Write.Length`

## pseudocode

```c
__int64 __fastcall VmsDIoNicPvtWrite(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // r15
  __int64 v4; // r13
  bool v5; // zf
  __int64 v7; // r12
  int v8; // ecx
  __int64 v9; // rbx
  int v10; // edx
  unsigned int v11; // edi
  __int64 v12; // rdi
  unsigned int v13; // ebx
  struct _MDL *v14; // r14
  char *v15; // rax
  ULONG v16; // ebx
  char *v17; // rdi
  struct _MDL *Mdl; // rax
  int v19; // edx
  int v20; // edx
  PVOID *p_MappedSystemVa; // rdi
  PVOID v22; // rax
  __int64 NetBufferAndNetBufferList; // rax
  __int64 v24; // rsi
  NDIS_STATUS v25; // eax
  int v26; // edx
  struct _NET_BUFFER *v27; // rcx
  PVOID DataBuffer; // rax
  int v29; // edx
  unsigned int v30; // ecx
  int v31; // eax
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 v35; // r8
  __int64 v36; // rax
  int Irp; // [rsp+20h] [rbp-58h]
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+8h] BYREF
  void *Src; // [rsp+90h] [rbp+18h]
  __int64 v41; // [rsp+98h] [rbp+20h]

  v3 = (unsigned int)VmsSafeHeaderSize;
  v4 = a2;
  v5 = *(_DWORD *)(a1 + 1872) == 4;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( !v5 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrNicLog,
      a2,
      19,
      18,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      "((objNic)->Type) == VmsNicDirectIo");
    if ( *(_DWORD *)(a1 + 1872) != 4 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v7 = *(_QWORD *)(a1 + 3312);
  if ( !v7 )
  {
    WPP_RECORDER_SF_s(VmsIfrNicLog, a2, 19, 19, (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids, "dioNicExt");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v8 = *(_DWORD *)(a1 + 68);
  if ( v8 != 1 || *(_DWORD *)(a1 + 1880) != 1 )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_ld(
      VmsIfrNicLog,
      a2,
      20,
      20,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      v8,
      *(_DWORD *)(a1 + 1880));
    v11 = -1073741436;
    goto LABEL_56;
  }
  v9 = *(_QWORD *)(v4 + 8);
  if ( !v9 )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_I(VmsIfrNicLog, a2, 20, 21, (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids, 0);
LABEL_10:
    v11 = -1073741811;
LABEL_56:
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_qqd(
      VmsIfrNicLog,
      v10,
      20,
      30,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      a1,
      v4,
      v11);
    return v11;
  }
  v12 = *(_QWORD *)(v4 + 184);
  v13 = *(_DWORD *)(v9 + 40);
  v41 = v12;
  if ( v13 != *(_DWORD *)(v12 + 8) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrNicLog,
      a2,
      19,
      22,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      "dataLength == irpSp->Parameters.Write.Length");
    if ( v13 != *(_DWORD *)(v12 + 8) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( v13 - 60 > 0x5AE )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_ddd(
      VmsIfrNicLog,
      a2,
      20,
      23,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      v13,
      v13 < 0x3C,
      v13 > 0x5EA);
    goto LABEL_10;
  }
  v14 = 0;
  v15 = (char *)(*(unsigned int *)(*(_QWORD *)(v4 + 8) + 44LL) + *(_QWORD *)(*(_QWORD *)(v4 + 8) + 32LL));
  Src = v15;
  if ( v13 <= (unsigned int)v3 )
    v3 = v13;
  v16 = v13 - v3;
  if ( v16 )
  {
    v17 = &v15[v3];
    Mdl = IoAllocateMdl(&v15[v3], v16, 0, 0, 0);
    v14 = Mdl;
    if ( !Mdl )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_id(
        VmsIfrNicLog,
        v19,
        20,
        24,
        (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
        (char)v17,
        v16);
      v11 = -1073741670;
      goto LABEL_56;
    }
    IoBuildPartialMdl(*(PMDL *)(v4 + 8), Mdl, v17, v16);
    p_MappedSystemVa = &v14->MappedSystemVa;
    if ( (v14->MdlFlags & 5) != 0 )
      v22 = *p_MappedSystemVa;
    else
      v22 = MmMapLockedPagesSpecifyCache(v14, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v22 )
    {
      v11 = -1073741670;
      goto LABEL_39;
    }
    if ( (v14->MdlFlags & 1) == 0 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrNicLog,
        v20,
        19,
        25,
        (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
        "(partialMdl->MdlFlags & MDL_MAPPED_TO_SYSTEM_VA) != 0");
      if ( (v14->MdlFlags & 1) == 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( !*p_MappedSystemVa )
    {
      WPP_RECORDER_SF_s(
        VmsIfrNicLog,
        v20,
        19,
        26,
        (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
        "partialMdl->MappedSystemVa != NULL");
      if ( !*p_MappedSystemVa )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
  }
  NetBufferAndNetBufferList = VmsNblHelperAllocateNetBufferAndNetBufferList(
                                *(_QWORD *)(v7 + 56),
                                40,
                                a3,
                                (int)v14,
                                Irp,
                                v16,
                                1);
  v24 = NetBufferAndNetBufferList;
  if ( !NetBufferAndNetBufferList )
  {
    v11 = -1073741670;
    goto LABEL_38;
  }
  v25 = NdisRetreatNetBufferDataStart(*(PNET_BUFFER *)(NetBufferAndNetBufferList + 8), v3, 0, 0);
  v27 = *(struct _NET_BUFFER **)(v24 + 8);
  v11 = v25;
  if ( v25 < 0 )
  {
    LOBYTE(v26) = 2;
    WPP_RECORDER_SF_qDd(
      VmsIfrNicLog,
      v26,
      20,
      27,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      (char)v27,
      v3,
      v25);
LABEL_37:
    VmsNblHelperFreeNetBufferList((PNET_BUFFER_LIST)v24);
LABEL_38:
    if ( !v14 )
      goto LABEL_56;
LABEL_39:
    IoFreeMdl(v14);
    goto LABEL_56;
  }
  DataBuffer = NdisGetDataBuffer(v27, v3, 0, 1u, 0);
  if ( !DataBuffer )
  {
    LOBYTE(v29) = 2;
    WPP_RECORDER_SF_id(
      VmsIfrNicLog,
      v29,
      20,
      28,
      (__int64)&WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids,
      *(_QWORD *)(v24 + 8),
      v3);
    NdisAdvanceNetBufferDataStart(*(PNET_BUFFER *)(v24 + 8), v3, 1u, 0);
    v11 = -1073741670;
    goto LABEL_37;
  }
  memmove(DataBuffer, Src, (unsigned int)v3);
  if ( v16 )
  {
    v30 = *(_DWORD *)(v24 + 300) & 0xFE7FFBFF | (*(_BYTE *)(a1 + 1877) == 0 ? 0x800000 : 0);
    v31 = v30 ^ (v30 ^ ((_DWORD)v3 << 11)) & 0x7FF800;
    *(_DWORD *)(v24 + 300) = v31;
    if ( (v3 & 0xFFFFF000) != 0 )
      *(_DWORD *)(v24 + 300) = v31 | 0x7FF800;
  }
  else
  {
    *(_DWORD *)(v24 + 300) = *(_DWORD *)(v24 + 300) & 0xFE7FFFFF | (*(_BYTE *)(a1 + 1877) == 0 ? 0x800000 : 0) | 0x400;
  }
  VmsNblHelperInitializeOriginalNbl(v24, 3);
  VmsNblHelperSetSourceInContext(v24, a1);
  v11 = 259;
  *(_QWORD *)(*(_QWORD *)(v24 + 288) + 32LL) = v4;
  *(_BYTE *)(*(_QWORD *)(v4 + 184) + 3LL) |= 1u;
  *(_QWORD *)(v4 + 56) = *(unsigned int *)(v41 + 8);
  if ( VmsEtwTraceDatapath )
  {
    if ( (v33 = *(_QWORD *)(a1 + 1984)) != 0 && *(_BYTE *)(v33 + 10864) || !VmsEtwTraceFiltersExist )
    {
      VmsOmObjectLockShared(a1, &LockState, 0);
      v34 = *(_QWORD *)(a1 + 1888);
      VmsTrcTransferNblActivityId(v24, a1, v35);
      VmsEtwTraceNblReceiveDeliver(
        &VM_NBL_RECEIVE,
        a1 + 616,
        (v34 + 72) & -(__int64)(v34 != 0),
        (v34 + 616) & -(__int64)(v34 != 0),
        v24);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
    }
  }
  if ( byte_1401FB3C0 )
  {
    v36 = *(_QWORD *)(v7 + 680);
    if ( v36 )
    {
      if ( (*(_DWORD *)(v36 + 56) & 1) != 0 )
        PktMonClientNblLogNdis(v7 + 656, v24, v32, 2);
    }
  }
  VmsExtPtRouteNetBufferListsWithBwCap(a1, v24, 1, 0);
  return v11;
}

```

## disassembly

```asm
0x1400ea6a0  mov     r11, rsp
0x1400ea6a3  mov     [r11+10h], rbx
0x1400ea6a7  push    rbp
0x1400ea6a8  push    rsi
0x1400ea6a9  push    rdi
0x1400ea6aa  push    r12
0x1400ea6ac  push    r13
0x1400ea6ae  push    r14
0x1400ea6b0  push    r15
0x1400ea6b2  sub     rsp, 40h
0x1400ea6b6  mov     r15d, cs:VmsSafeHeaderSize
0x1400ea6bd  lea     rdi, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea6c4  xor     eax, eax
0x1400ea6c6  mov     r13, rdx
0x1400ea6c9  cmp     dword ptr [rcx+750h], 4
0x1400ea6d0  mov     rbp, rcx
0x1400ea6d3  mov     [r11+8], ax
0x1400ea6d8  mov     [r11+0Ah], al
0x1400ea6dc  jz      short loc_1400EA70F
0x1400ea6de  mov     rcx, cs:VmsIfrNicLog
0x1400ea6e5  lea     r9d, [rax+12h]
0x1400ea6e9  lea     rax, aObjnicTypeVmsn_2; "((objNic)->Type) == VmsNicDirectIo"
0x1400ea6f0  mov     [r11-50h], rax
0x1400ea6f4  lea     r8d, [r9+1]
0x1400ea6f8  mov     [r11-58h], rdi
0x1400ea6fc  call    WPP_RECORDER_SF_s
0x1400ea701  cmp     dword ptr [rbp+750h], 4
0x1400ea708  jz      short loc_1400EA70F
0x1400ea70a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((objNic)->Type) == VmsNicDirectIo")
0x1400ea70f  mov     r12, [rbp+0CF0h]
0x1400ea716  xor     esi, esi
0x1400ea718  test    r12, r12
0x1400ea71b  jnz     short loc_1400EA747
0x1400ea71d  mov     rcx, cs:VmsIfrNicLog
0x1400ea724  lea     r9d, [r12+13h]
0x1400ea729  lea     rax, aDionicext; "dioNicExt"
0x1400ea730  mov     r8d, r9d
0x1400ea733  mov     qword ptr [rsp+78h+Priority], rax
0x1400ea738  mov     [rsp+78h+Irp], rdi
0x1400ea73d  call    WPP_RECORDER_SF_s
0x1400ea742  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "dioNicExt")
0x1400ea747  mov     ecx, [rbp+44h]
0x1400ea74a  cmp     ecx, 1
0x1400ea74d  jnz     loc_1400EAC85
0x1400ea753  cmp     [rbp+758h], ecx
0x1400ea759  jnz     loc_1400EAC85
0x1400ea75f  mov     rbx, [r13+8]
0x1400ea763  test    rbx, rbx
0x1400ea766  jnz     short loc_1400EA792
0x1400ea768  lea     r9d, [rcx+14h]
0x1400ea76c  mov     qword ptr [rsp+78h+Priority], rsi
0x1400ea771  lea     r8d, [rcx+13h]
0x1400ea775  mov     [rsp+78h+Irp], rdi
0x1400ea77a  mov     rcx, cs:VmsIfrNicLog
0x1400ea781  mov     dl, 2
0x1400ea783  call    WPP_RECORDER_SF_I
0x1400ea788  mov     edi, 0C000000Dh
0x1400ea78d  jmp     loc_1400EACB4
0x1400ea792  mov     rdi, [r13+0B8h]
0x1400ea799  mov     ebx, [rbx+28h]
0x1400ea79c  mov     [rsp+78h+arg_18], rdi
0x1400ea7a4  cmp     ebx, [rdi+8]
0x1400ea7a7  jz      short loc_1400EA7E3
0x1400ea7a9  mov     rcx, cs:VmsIfrNicLog
0x1400ea7b0  lea     rax, aDatalengthIrps; "dataLength == irpSp->Parameters.Write.L"...
0x1400ea7b7  mov     r9d, 16h
0x1400ea7bd  mov     qword ptr [rsp+78h+Priority], rax
0x1400ea7c2  lea     r14, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea7c9  mov     [rsp+78h+Irp], r14
0x1400ea7ce  lea     r8d, [r9-3]
0x1400ea7d2  call    WPP_RECORDER_SF_s
0x1400ea7d7  cmp     ebx, [rdi+8]
0x1400ea7da  jz      short loc_1400EA7EA
0x1400ea7dc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "dataLength == irpSp->Parameters.Write.Length")
0x1400ea7e1  jmp     short loc_1400EA7EA
0x1400ea7e3  lea     r14, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea7ea  lea     eax, [rbx-3Ch]
0x1400ea7ed  cmp     eax, 5AEh
0x1400ea7f2  ja      loc_1400EAC44
0x1400ea7f8  mov     rax, [r13+8]
0x1400ea7fc  mov     r14, rsi
0x1400ea7ff  mov     ecx, [rax+2Ch]
0x1400ea802  mov     rax, [rax+20h]
0x1400ea806  add     rax, rcx
0x1400ea809  cmp     ebx, r15d
0x1400ea80c  mov     [rsp+78h+Src], rax
0x1400ea814  cmovbe  r15d, ebx
0x1400ea818  sub     ebx, r15d
0x1400ea81b  jz      loc_1400EA958
0x1400ea821  lea     rdi, [rax+r15]
0x1400ea825  mov     [rsp+78h+Irp], rsi; Irp
0x1400ea82a  mov     rcx, rdi; VirtualAddress
0x1400ea82d  xor     r9d, r9d; ChargeQuota
0x1400ea830  xor     r8d, r8d; SecondaryBuffer
0x1400ea833  mov     edx, ebx; Length
0x1400ea835  call    cs:__imp_IoAllocateMdl
0x1400ea83c  nop     dword ptr [rax+rax+00h]
0x1400ea841  mov     r14, rax
0x1400ea844  test    rax, rax
0x1400ea847  jnz     short loc_1400EA87E
0x1400ea849  mov     rcx, cs:VmsIfrNicLog
0x1400ea850  lea     r9d, [rax+18h]
0x1400ea854  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea85b  mov     dword ptr [rsp+78h+var_48], ebx
0x1400ea85f  mov     qword ptr [rsp+78h+Priority], rdi
0x1400ea864  lea     r8d, [r14+14h]
0x1400ea868  mov     dl, 2
0x1400ea86a  mov     [rsp+78h+Irp], rax
0x1400ea86f  call    WPP_RECORDER_SF_id
0x1400ea874  mov     edi, 0C000009Ah
0x1400ea879  jmp     loc_1400EACB4
0x1400ea87e  mov     rcx, [r13+8]; SourceMdl
0x1400ea882  mov     r9d, ebx; Length
0x1400ea885  mov     r8, rdi; VirtualAddress
0x1400ea888  mov     rdx, r14; TargetMdl
0x1400ea88b  call    cs:__imp_IoBuildPartialMdl
0x1400ea892  nop     dword ptr [rax+rax+00h]
0x1400ea897  test    byte ptr [r14+0Ah], 5
0x1400ea89c  lea     rdi, [r14+18h]
0x1400ea8a0  jz      short loc_1400EA8A7
0x1400ea8a2  mov     rax, [rdi]
0x1400ea8a5  jmp     short loc_1400EA8CB
0x1400ea8a7  xor     r9d, r9d; RequestedAddress
0x1400ea8aa  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400ea8b2  xor     edx, edx; AccessMode
0x1400ea8b4  mov     dword ptr [rsp+78h+Irp], esi; BugCheckOnFailure
0x1400ea8b8  mov     rcx, r14; MemoryDescriptorList
0x1400ea8bb  lea     r8d, [r9+1]; CacheType
0x1400ea8bf  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400ea8c6  nop     dword ptr [rax+rax+00h]
0x1400ea8cb  test    rax, rax
0x1400ea8ce  jnz     short loc_1400EA8DA
0x1400ea8d0  mov     edi, 0C000009Ah
0x1400ea8d5  jmp     loc_1400EAA66
0x1400ea8da  test    byte ptr [r14+0Ah], 1
0x1400ea8df  jnz     short loc_1400EA91B
0x1400ea8e1  mov     rcx, cs:VmsIfrNicLog
0x1400ea8e8  lea     rax, aPartialmdlMdlf; "(partialMdl->MdlFlags & MDL_MAPPED_TO_S"...
0x1400ea8ef  mov     qword ptr [rsp+78h+Priority], rax
0x1400ea8f4  mov     r9d, 19h
0x1400ea8fa  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea901  mov     [rsp+78h+Irp], rax
0x1400ea906  lea     r8d, [r9-6]
0x1400ea90a  call    WPP_RECORDER_SF_s
0x1400ea90f  test    byte ptr [r14+0Ah], 1
0x1400ea914  jnz     short loc_1400EA91B
0x1400ea916  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(partialMdl->MdlFlags & 0x0001) != 0")
0x1400ea91b  cmp     [rdi], rsi
0x1400ea91e  jnz     short loc_1400EA958
0x1400ea920  mov     rcx, cs:VmsIfrNicLog
0x1400ea927  lea     rax, aPartialmdlMapp; "partialMdl->MappedSystemVa != NULL"
0x1400ea92e  mov     qword ptr [rsp+78h+Priority], rax
0x1400ea933  mov     r9d, 1Ah
0x1400ea939  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea940  mov     [rsp+78h+Irp], rax; int
0x1400ea945  lea     r8d, [r9-7]
0x1400ea949  call    WPP_RECORDER_SF_s
0x1400ea94e  cmp     [rdi], rsi
0x1400ea951  jnz     short loc_1400EA958
0x1400ea953  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "partialMdl->MappedSystemVa != ((void *)0)")
0x1400ea958  mov     rcx, [r12+38h]; int
0x1400ea95d  mov     edx, 28h ; '('; int
0x1400ea962  mov     eax, ebx
0x1400ea964  mov     r9, r14; int
0x1400ea967  mov     dword ptr [rsp+78h+var_48], 1; int
0x1400ea96f  mov     qword ptr [rsp+78h+Priority], rax; SIZE_T
0x1400ea974  call    VmsNblHelperAllocateNetBufferAndNetBufferList
0x1400ea979  mov     rsi, rax
0x1400ea97c  test    rax, rax
0x1400ea97f  jnz     short loc_1400EA98B
0x1400ea981  mov     edi, 0C000009Ah
0x1400ea986  jmp     loc_1400EAA5D
0x1400ea98b  mov     rcx, [rax+8]; NetBuffer
0x1400ea98f  xor     r9d, r9d; AllocateMdlHandler
0x1400ea992  xor     r8d, r8d; DataBackFill
0x1400ea995  mov     edx, r15d; DataOffsetDelta
0x1400ea998  call    cs:__imp_NdisRetreatNetBufferDataStart
0x1400ea99f  nop     dword ptr [rax+rax+00h]
0x1400ea9a4  mov     rcx, [rsi+8]; NetBuffer
0x1400ea9a8  mov     edi, eax
0x1400ea9aa  test    eax, eax
0x1400ea9ac  jns     short loc_1400EA9E2
0x1400ea9ae  mov     dword ptr [rsp+78h+var_40], eax
0x1400ea9b2  mov     r9d, 1Bh
0x1400ea9b8  mov     dword ptr [rsp+78h+var_48], r15d
0x1400ea9bd  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea9c4  mov     qword ptr [rsp+78h+Priority], rcx
0x1400ea9c9  mov     dl, 2
0x1400ea9cb  mov     rcx, cs:VmsIfrNicLog
0x1400ea9d2  lea     r8d, [r9-7]
0x1400ea9d6  mov     [rsp+78h+Irp], rax
0x1400ea9db  call    WPP_RECORDER_SF_qDd
0x1400ea9e0  jmp     short loc_1400EAA55
0x1400ea9e2  mov     r9d, 1; AlignMultiple
0x1400ea9e8  mov     dword ptr [rsp+78h+Irp], 0; AlignOffset
0x1400ea9f0  xor     r8d, r8d; Storage
0x1400ea9f3  mov     edx, r15d; BytesNeeded
0x1400ea9f6  call    cs:__imp_NdisGetDataBuffer
0x1400ea9fd  nop     dword ptr [rax+rax+00h]
0x1400eaa02  test    rax, rax
0x1400eaa05  jnz     short loc_1400EAA7A
0x1400eaa07  mov     rcx, cs:VmsIfrNicLog
0x1400eaa0e  lea     r9d, [rax+1Ch]
0x1400eaa12  mov     rax, [rsi+8]
0x1400eaa16  lea     r8d, [r9-8]
0x1400eaa1a  mov     dword ptr [rsp+78h+var_48], r15d
0x1400eaa1f  mov     dl, 2
0x1400eaa21  mov     qword ptr [rsp+78h+Priority], rax
0x1400eaa26  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400eaa2d  mov     [rsp+78h+Irp], rax
0x1400eaa32  call    WPP_RECORDER_SF_id
0x1400eaa37  mov     rcx, [rsi+8]; NetBuffer
0x1400eaa3b  xor     r9d, r9d; FreeMdlHandler
0x1400eaa3e  mov     r8b, 1; FreeMdl
0x1400eaa41  mov     edx, r15d; DataOffsetDelta
0x1400eaa44  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400eaa4b  nop     dword ptr [rax+rax+00h]
0x1400eaa50  mov     edi, 0C000009Ah
0x1400eaa55  mov     rcx, rsi; NetBufferList
0x1400eaa58  call    VmsNblHelperFreeNetBufferList
0x1400eaa5d  test    r14, r14
0x1400eaa60  jz      loc_1400EACB4
0x1400eaa66  mov     rcx, r14; Mdl
0x1400eaa69  call    cs:__imp_IoFreeMdl
0x1400eaa70  nop     dword ptr [rax+rax+00h]
0x1400eaa75  jmp     loc_1400EACB4
0x1400eaa7a  mov     rdx, [rsp+78h+Src]; Src
0x1400eaa82  mov     rcx, rax; void *
0x1400eaa85  mov     r8d, r15d; Size
0x1400eaa88  call    memmove
0x1400eaa8d  mov     al, [rbp+755h]
0x1400eaa93  neg     al
0x1400eaa95  mov     eax, [rsi+12Ch]
0x1400eaa9b  sbb     ecx, ecx
0x1400eaa9d  btr     eax, 17h
0x1400eaaa1  not     ecx
0x1400eaaa3  and     ecx, 800000h
0x1400eaaa9  or      ecx, eax
0x1400eaaab  btr     ecx, 18h
0x1400eaaaf  test    ebx, ebx
0x1400eaab1  jnz     short loc_1400EAABF
0x1400eaab3  bts     ecx, 0Ah
0x1400eaab7  mov     [rsi+12Ch], ecx
0x1400eaabd  jmp     short loc_1400EAAEB
0x1400eaabf  btr     ecx, 0Ah
0x1400eaac3  mov     eax, r15d
0x1400eaac6  shl     eax, 0Bh
0x1400eaac9  mov     edx, 7FF800h
0x1400eaace  xor     eax, ecx
0x1400eaad0  and     eax, edx
0x1400eaad2  xor     eax, ecx
0x1400eaad4  mov     [rsi+12Ch], eax
0x1400eaada  test    r15d, 0FFFFF000h
0x1400eaae1  jbe     short loc_1400EAAEB
0x1400eaae3  or      eax, edx
0x1400eaae5  mov     [rsi+12Ch], eax
0x1400eaaeb  mov     edx, 3
0x1400eaaf0  mov     rcx, rsi
0x1400eaaf3  call    VmsNblHelperInitializeOriginalNbl
0x1400eaaf8  mov     rcx, rsi
0x1400eaafb  mov     rdx, rbp
0x1400eaafe  call    VmsNblHelperSetSourceInContext
0x1400eab03  mov     rdx, [rsi+120h]
0x1400eab0a  mov     edi, 103h
0x1400eab0f  mov     [rdx+20h], r13
0x1400eab13  mov     rax, [r13+0B8h]
0x1400eab1a  or      byte ptr [rax+3], 1
0x1400eab1e  mov     rax, [rsp+78h+arg_18]
0x1400eab26  mov     eax, [rax+8]
0x1400eab29  mov     [r13+38h], rax
0x1400eab2d  mov     al, cs:VmsEtwTraceDatapath
0x1400eab33  test    al, al
0x1400eab35  jz      loc_1400EABFA
0x1400eab3b  mov     rax, [rbp+7C0h]
0x1400eab42  test    rax, rax
0x1400eab45  jz      short loc_1400EAB50
0x1400eab47  cmp     byte ptr [rax+2A70h], 0
0x1400eab4e  jnz     short loc_1400EAB5E
0x1400eab50  mov     al, cs:VmsEtwTraceFiltersExist
0x1400eab56  test    al, al
0x1400eab58  jnz     loc_1400EABFA
0x1400eab5e  xor     r8d, r8d
0x1400eab61  lea     rdx, [rsp+78h+LockState]
0x1400eab69  mov     rcx, rbp
0x1400eab6c  call    VmsOmObjectLockShared
0x1400eab71  mov     rbx, [rbp+760h]
0x1400eab78  mov     rdx, rbp
0x1400eab7b  mov     rcx, rsi
0x1400eab7e  call    VmsTrcTransferNblActivityId
0x1400eab83  mov     rdx, [rsi+0F8h]
0x1400eab8a  lea     rcx, [rbx+268h]
0x1400eab91  mov     [rsp+78h+var_40], rsi; __int64
0x1400eab96  lea     r9, [rbp+48h]
0x1400eab9a  mov     rax, rbx
0x1400eab9d  mov     r10, 7FFFFFFFFFFFFFFFh
0x1400eaba7  neg     rax
0x1400eabaa  lea     rax, [rbx+48h]
0x1400eabae  sbb     r8, r8
0x1400eabb1  and     r8, rcx
0x1400eabb4  mov     [rsp+78h+var_48], r8; __int64
  ... truncated ...
```
