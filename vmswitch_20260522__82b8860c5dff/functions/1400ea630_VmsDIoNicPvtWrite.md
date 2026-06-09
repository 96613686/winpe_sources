# VmsDIoNicPvtWrite

- ea: `0x1400ea630`
- end: `0x1400eac91`
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
- `0x1400ea630`
- `0x14011499c`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400ea9f9`
- `ntoskrnl!IoFreeMdl` at `0x1400ea9f9`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ea81b`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ea81b`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea7c5`
- `ntoskrnl!IoAllocateMdl` at `0x1400ea7c5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ea84f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ea84f`
- `NDIS!NdisReleaseRWLock` at `0x1400eab7e`
- `NDIS!NdisReleaseRWLock` at `0x1400eab7e`
- `NDIS!NdisGetDataBuffer` at `0x1400ea986`
- `NDIS!NdisGetDataBuffer` at `0x1400ea986`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400ea9d4`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400ea9d4`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400ea928`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400ea928`

## string_xrefs

- `0x1400ea740`: `dataLength == irpSp->Parameters.Write.Length`

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
  __int64 v35; // rax
  int Irp; // [rsp+20h] [rbp-58h]
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+8h] BYREF
  void *Src; // [rsp+90h] [rbp+18h]
  __int64 v40; // [rsp+98h] [rbp+20h]

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
  v40 = v12;
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
  *(_QWORD *)(v4 + 56) = *(unsigned int *)(v40 + 8);
  if ( VmsEtwTraceDatapath )
  {
    if ( (v33 = *(_QWORD *)(a1 + 1984)) != 0 && *(_BYTE *)(v33 + 10864) || !VmsEtwTraceFiltersExist )
    {
      VmsOmObjectLockShared(a1, &LockState, 0);
      v34 = *(_QWORD *)(a1 + 1888);
      VmsTrcTransferNblActivityId(v24, a1);
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
    v35 = *(_QWORD *)(v7 + 680);
    if ( v35 )
    {
      if ( (*(_DWORD *)(v35 + 56) & 1) != 0 )
        PktMonClientNblLogNdis(v7 + 656, v24, v32, 2);
    }
  }
  VmsExtPtRouteNetBufferListsWithBwCap(a1, v24, 1, 0);
  return v11;
}

```

## disassembly

```asm
0x1400ea630  mov     r11, rsp
0x1400ea633  mov     [r11+10h], rbx
0x1400ea637  push    rbp
0x1400ea638  push    rsi
0x1400ea639  push    rdi
0x1400ea63a  push    r12
0x1400ea63c  push    r13
0x1400ea63e  push    r14
0x1400ea640  push    r15
0x1400ea642  sub     rsp, 40h
0x1400ea646  mov     r15d, cs:VmsSafeHeaderSize
0x1400ea64d  lea     rdi, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea654  xor     eax, eax
0x1400ea656  mov     r13, rdx
0x1400ea659  cmp     dword ptr [rcx+750h], 4
0x1400ea660  mov     rbp, rcx
0x1400ea663  mov     [r11+8], ax
0x1400ea668  mov     [r11+0Ah], al
0x1400ea66c  jz      short loc_1400EA69F
0x1400ea66e  mov     rcx, cs:VmsIfrNicLog
0x1400ea675  lea     r9d, [rax+12h]
0x1400ea679  lea     rax, aObjnicTypeVmsn_2; "((objNic)->Type) == VmsNicDirectIo"
0x1400ea680  mov     [r11-50h], rax
0x1400ea684  lea     r8d, [r9+1]
0x1400ea688  mov     [r11-58h], rdi
0x1400ea68c  call    WPP_RECORDER_SF_s
0x1400ea691  cmp     dword ptr [rbp+750h], 4
0x1400ea698  jz      short loc_1400EA69F
0x1400ea69a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((objNic)->Type) == VmsNicDirectIo")
0x1400ea69f  mov     r12, [rbp+0CF0h]
0x1400ea6a6  xor     esi, esi
0x1400ea6a8  test    r12, r12
0x1400ea6ab  jnz     short loc_1400EA6D7
0x1400ea6ad  mov     rcx, cs:VmsIfrNicLog
0x1400ea6b4  lea     r9d, [r12+13h]
0x1400ea6b9  lea     rax, aDionicext; "dioNicExt"
0x1400ea6c0  mov     r8d, r9d
0x1400ea6c3  mov     qword ptr [rsp+78h+Priority], rax
0x1400ea6c8  mov     [rsp+78h+Irp], rdi
0x1400ea6cd  call    WPP_RECORDER_SF_s
0x1400ea6d2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "dioNicExt")
0x1400ea6d7  mov     ecx, [rbp+44h]
0x1400ea6da  cmp     ecx, 1
0x1400ea6dd  jnz     loc_1400EAC15
0x1400ea6e3  cmp     [rbp+758h], ecx
0x1400ea6e9  jnz     loc_1400EAC15
0x1400ea6ef  mov     rbx, [r13+8]
0x1400ea6f3  test    rbx, rbx
0x1400ea6f6  jnz     short loc_1400EA722
0x1400ea6f8  lea     r9d, [rcx+14h]
0x1400ea6fc  mov     qword ptr [rsp+78h+Priority], rsi
0x1400ea701  lea     r8d, [rcx+13h]
0x1400ea705  mov     [rsp+78h+Irp], rdi
0x1400ea70a  mov     rcx, cs:VmsIfrNicLog
0x1400ea711  mov     dl, 2
0x1400ea713  call    WPP_RECORDER_SF_I
0x1400ea718  mov     edi, 0C000000Dh
0x1400ea71d  jmp     loc_1400EAC44
0x1400ea722  mov     rdi, [r13+0B8h]
0x1400ea729  mov     ebx, [rbx+28h]
0x1400ea72c  mov     [rsp+78h+arg_18], rdi
0x1400ea734  cmp     ebx, [rdi+8]
0x1400ea737  jz      short loc_1400EA773
0x1400ea739  mov     rcx, cs:VmsIfrNicLog
0x1400ea740  lea     rax, aDatalengthIrps; "dataLength == irpSp->Parameters.Write.L"...
0x1400ea747  mov     r9d, 16h
0x1400ea74d  mov     qword ptr [rsp+78h+Priority], rax
0x1400ea752  lea     r14, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea759  mov     [rsp+78h+Irp], r14
0x1400ea75e  lea     r8d, [r9-3]
0x1400ea762  call    WPP_RECORDER_SF_s
0x1400ea767  cmp     ebx, [rdi+8]
0x1400ea76a  jz      short loc_1400EA77A
0x1400ea76c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "dataLength == irpSp->Parameters.Write.Length")
0x1400ea771  jmp     short loc_1400EA77A
0x1400ea773  lea     r14, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea77a  lea     eax, [rbx-3Ch]
0x1400ea77d  cmp     eax, 5AEh
0x1400ea782  ja      loc_1400EABD4
0x1400ea788  mov     rax, [r13+8]
0x1400ea78c  mov     r14, rsi
0x1400ea78f  mov     ecx, [rax+2Ch]
0x1400ea792  mov     rax, [rax+20h]
0x1400ea796  add     rax, rcx
0x1400ea799  cmp     ebx, r15d
0x1400ea79c  mov     [rsp+78h+Src], rax
0x1400ea7a4  cmovbe  r15d, ebx
0x1400ea7a8  sub     ebx, r15d
0x1400ea7ab  jz      loc_1400EA8E8
0x1400ea7b1  lea     rdi, [rax+r15]
0x1400ea7b5  mov     [rsp+78h+Irp], rsi; Irp
0x1400ea7ba  mov     rcx, rdi; VirtualAddress
0x1400ea7bd  xor     r9d, r9d; ChargeQuota
0x1400ea7c0  xor     r8d, r8d; SecondaryBuffer
0x1400ea7c3  mov     edx, ebx; Length
0x1400ea7c5  call    cs:__imp_IoAllocateMdl
0x1400ea7cc  nop     dword ptr [rax+rax+00h]
0x1400ea7d1  mov     r14, rax
0x1400ea7d4  test    rax, rax
0x1400ea7d7  jnz     short loc_1400EA80E
0x1400ea7d9  mov     rcx, cs:VmsIfrNicLog
0x1400ea7e0  lea     r9d, [rax+18h]
0x1400ea7e4  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea7eb  mov     dword ptr [rsp+78h+var_48], ebx
0x1400ea7ef  mov     qword ptr [rsp+78h+Priority], rdi
0x1400ea7f4  lea     r8d, [r14+14h]
0x1400ea7f8  mov     dl, 2
0x1400ea7fa  mov     [rsp+78h+Irp], rax
0x1400ea7ff  call    WPP_RECORDER_SF_id
0x1400ea804  mov     edi, 0C000009Ah
0x1400ea809  jmp     loc_1400EAC44
0x1400ea80e  mov     rcx, [r13+8]; SourceMdl
0x1400ea812  mov     r9d, ebx; Length
0x1400ea815  mov     r8, rdi; VirtualAddress
0x1400ea818  mov     rdx, r14; TargetMdl
0x1400ea81b  call    cs:__imp_IoBuildPartialMdl
0x1400ea822  nop     dword ptr [rax+rax+00h]
0x1400ea827  test    byte ptr [r14+0Ah], 5
0x1400ea82c  lea     rdi, [r14+18h]
0x1400ea830  jz      short loc_1400EA837
0x1400ea832  mov     rax, [rdi]
0x1400ea835  jmp     short loc_1400EA85B
0x1400ea837  xor     r9d, r9d; RequestedAddress
0x1400ea83a  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400ea842  xor     edx, edx; AccessMode
0x1400ea844  mov     dword ptr [rsp+78h+Irp], esi; BugCheckOnFailure
0x1400ea848  mov     rcx, r14; MemoryDescriptorList
0x1400ea84b  lea     r8d, [r9+1]; CacheType
0x1400ea84f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400ea856  nop     dword ptr [rax+rax+00h]
0x1400ea85b  test    rax, rax
0x1400ea85e  jnz     short loc_1400EA86A
0x1400ea860  mov     edi, 0C000009Ah
0x1400ea865  jmp     loc_1400EA9F6
0x1400ea86a  test    byte ptr [r14+0Ah], 1
0x1400ea86f  jnz     short loc_1400EA8AB
0x1400ea871  mov     rcx, cs:VmsIfrNicLog
0x1400ea878  lea     rax, aPartialmdlMdlf; "(partialMdl->MdlFlags & MDL_MAPPED_TO_S"...
0x1400ea87f  mov     qword ptr [rsp+78h+Priority], rax
0x1400ea884  mov     r9d, 19h
0x1400ea88a  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea891  mov     [rsp+78h+Irp], rax
0x1400ea896  lea     r8d, [r9-6]
0x1400ea89a  call    WPP_RECORDER_SF_s
0x1400ea89f  test    byte ptr [r14+0Ah], 1
0x1400ea8a4  jnz     short loc_1400EA8AB
0x1400ea8a6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(partialMdl->MdlFlags & 0x0001) != 0")
0x1400ea8ab  cmp     [rdi], rsi
0x1400ea8ae  jnz     short loc_1400EA8E8
0x1400ea8b0  mov     rcx, cs:VmsIfrNicLog
0x1400ea8b7  lea     rax, aPartialmdlMapp; "partialMdl->MappedSystemVa != NULL"
0x1400ea8be  mov     qword ptr [rsp+78h+Priority], rax
0x1400ea8c3  mov     r9d, 1Ah
0x1400ea8c9  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea8d0  mov     [rsp+78h+Irp], rax; int
0x1400ea8d5  lea     r8d, [r9-7]
0x1400ea8d9  call    WPP_RECORDER_SF_s
0x1400ea8de  cmp     [rdi], rsi
0x1400ea8e1  jnz     short loc_1400EA8E8
0x1400ea8e3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "partialMdl->MappedSystemVa != ((void *)0)")
0x1400ea8e8  mov     rcx, [r12+38h]; int
0x1400ea8ed  mov     edx, 28h ; '('; int
0x1400ea8f2  mov     eax, ebx
0x1400ea8f4  mov     r9, r14; int
0x1400ea8f7  mov     dword ptr [rsp+78h+var_48], 1; int
0x1400ea8ff  mov     qword ptr [rsp+78h+Priority], rax; SIZE_T
0x1400ea904  call    VmsNblHelperAllocateNetBufferAndNetBufferList
0x1400ea909  mov     rsi, rax
0x1400ea90c  test    rax, rax
0x1400ea90f  jnz     short loc_1400EA91B
0x1400ea911  mov     edi, 0C000009Ah
0x1400ea916  jmp     loc_1400EA9ED
0x1400ea91b  mov     rcx, [rax+8]; NetBuffer
0x1400ea91f  xor     r9d, r9d; AllocateMdlHandler
0x1400ea922  xor     r8d, r8d; DataBackFill
0x1400ea925  mov     edx, r15d; DataOffsetDelta
0x1400ea928  call    cs:__imp_NdisRetreatNetBufferDataStart
0x1400ea92f  nop     dword ptr [rax+rax+00h]
0x1400ea934  mov     rcx, [rsi+8]; NetBuffer
0x1400ea938  mov     edi, eax
0x1400ea93a  test    eax, eax
0x1400ea93c  jns     short loc_1400EA972
0x1400ea93e  mov     dword ptr [rsp+78h+var_40], eax
0x1400ea942  mov     r9d, 1Bh
0x1400ea948  mov     dword ptr [rsp+78h+var_48], r15d
0x1400ea94d  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea954  mov     qword ptr [rsp+78h+Priority], rcx
0x1400ea959  mov     dl, 2
0x1400ea95b  mov     rcx, cs:VmsIfrNicLog
0x1400ea962  lea     r8d, [r9-7]
0x1400ea966  mov     [rsp+78h+Irp], rax
0x1400ea96b  call    WPP_RECORDER_SF_qDd
0x1400ea970  jmp     short loc_1400EA9E5
0x1400ea972  mov     r9d, 1; AlignMultiple
0x1400ea978  mov     dword ptr [rsp+78h+Irp], 0; AlignOffset
0x1400ea980  xor     r8d, r8d; Storage
0x1400ea983  mov     edx, r15d; BytesNeeded
0x1400ea986  call    cs:__imp_NdisGetDataBuffer
0x1400ea98d  nop     dword ptr [rax+rax+00h]
0x1400ea992  test    rax, rax
0x1400ea995  jnz     short loc_1400EAA0A
0x1400ea997  mov     rcx, cs:VmsIfrNicLog
0x1400ea99e  lea     r9d, [rax+1Ch]
0x1400ea9a2  mov     rax, [rsi+8]
0x1400ea9a6  lea     r8d, [r9-8]
0x1400ea9aa  mov     dword ptr [rsp+78h+var_48], r15d
0x1400ea9af  mov     dl, 2
0x1400ea9b1  mov     qword ptr [rsp+78h+Priority], rax
0x1400ea9b6  lea     rax, WPP_e044bfdd865730b064bcaf57c723b6ba_Traceguids
0x1400ea9bd  mov     [rsp+78h+Irp], rax
0x1400ea9c2  call    WPP_RECORDER_SF_id
0x1400ea9c7  mov     rcx, [rsi+8]; NetBuffer
0x1400ea9cb  xor     r9d, r9d; FreeMdlHandler
0x1400ea9ce  mov     r8b, 1; FreeMdl
0x1400ea9d1  mov     edx, r15d; DataOffsetDelta
0x1400ea9d4  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400ea9db  nop     dword ptr [rax+rax+00h]
0x1400ea9e0  mov     edi, 0C000009Ah
0x1400ea9e5  mov     rcx, rsi; NetBufferList
0x1400ea9e8  call    VmsNblHelperFreeNetBufferList
0x1400ea9ed  test    r14, r14
0x1400ea9f0  jz      loc_1400EAC44
0x1400ea9f6  mov     rcx, r14; Mdl
0x1400ea9f9  call    cs:__imp_IoFreeMdl
0x1400eaa00  nop     dword ptr [rax+rax+00h]
0x1400eaa05  jmp     loc_1400EAC44
0x1400eaa0a  mov     rdx, [rsp+78h+Src]; Src
0x1400eaa12  mov     rcx, rax; void *
0x1400eaa15  mov     r8d, r15d; Size
0x1400eaa18  call    memmove
0x1400eaa1d  mov     al, [rbp+755h]
0x1400eaa23  neg     al
0x1400eaa25  mov     eax, [rsi+12Ch]
0x1400eaa2b  sbb     ecx, ecx
0x1400eaa2d  btr     eax, 17h
0x1400eaa31  not     ecx
0x1400eaa33  and     ecx, 800000h
0x1400eaa39  or      ecx, eax
0x1400eaa3b  btr     ecx, 18h
0x1400eaa3f  test    ebx, ebx
0x1400eaa41  jnz     short loc_1400EAA4F
0x1400eaa43  bts     ecx, 0Ah
0x1400eaa47  mov     [rsi+12Ch], ecx
0x1400eaa4d  jmp     short loc_1400EAA7B
0x1400eaa4f  btr     ecx, 0Ah
0x1400eaa53  mov     eax, r15d
0x1400eaa56  shl     eax, 0Bh
0x1400eaa59  mov     edx, 7FF800h
0x1400eaa5e  xor     eax, ecx
0x1400eaa60  and     eax, edx
0x1400eaa62  xor     eax, ecx
0x1400eaa64  mov     [rsi+12Ch], eax
0x1400eaa6a  test    r15d, 0FFFFF000h
0x1400eaa71  jbe     short loc_1400EAA7B
0x1400eaa73  or      eax, edx
0x1400eaa75  mov     [rsi+12Ch], eax
0x1400eaa7b  mov     edx, 3
0x1400eaa80  mov     rcx, rsi
0x1400eaa83  call    VmsNblHelperInitializeOriginalNbl
0x1400eaa88  mov     rcx, rsi
0x1400eaa8b  mov     rdx, rbp
0x1400eaa8e  call    VmsNblHelperSetSourceInContext
0x1400eaa93  mov     rdx, [rsi+120h]
0x1400eaa9a  mov     edi, 103h
0x1400eaa9f  mov     [rdx+20h], r13
0x1400eaaa3  mov     rax, [r13+0B8h]
0x1400eaaaa  or      byte ptr [rax+3], 1
0x1400eaaae  mov     rax, [rsp+78h+arg_18]
0x1400eaab6  mov     eax, [rax+8]
0x1400eaab9  mov     [r13+38h], rax
0x1400eaabd  mov     al, cs:VmsEtwTraceDatapath
0x1400eaac3  test    al, al
0x1400eaac5  jz      loc_1400EAB8A
0x1400eaacb  mov     rax, [rbp+7C0h]
0x1400eaad2  test    rax, rax
0x1400eaad5  jz      short loc_1400EAAE0
0x1400eaad7  cmp     byte ptr [rax+2A70h], 0
0x1400eaade  jnz     short loc_1400EAAEE
0x1400eaae0  mov     al, cs:VmsEtwTraceFiltersExist
0x1400eaae6  test    al, al
0x1400eaae8  jnz     loc_1400EAB8A
0x1400eaaee  xor     r8d, r8d
0x1400eaaf1  lea     rdx, [rsp+78h+LockState]
0x1400eaaf9  mov     rcx, rbp
0x1400eaafc  call    VmsOmObjectLockShared
0x1400eab01  mov     rbx, [rbp+760h]
0x1400eab08  mov     rdx, rbp
0x1400eab0b  mov     rcx, rsi
0x1400eab0e  call    VmsTrcTransferNblActivityId
0x1400eab13  mov     rdx, [rsi+0F8h]
0x1400eab1a  lea     rcx, [rbx+268h]
0x1400eab21  mov     [rsp+78h+var_40], rsi; __int64
0x1400eab26  lea     r9, [rbp+48h]
0x1400eab2a  mov     rax, rbx
0x1400eab2d  mov     r10, 7FFFFFFFFFFFFFFFh
0x1400eab37  neg     rax
0x1400eab3a  lea     rax, [rbx+48h]
0x1400eab3e  sbb     r8, r8
0x1400eab41  and     r8, rcx
0x1400eab44  mov     [rsp+78h+var_48], r8; __int64
  ... truncated ...
```
