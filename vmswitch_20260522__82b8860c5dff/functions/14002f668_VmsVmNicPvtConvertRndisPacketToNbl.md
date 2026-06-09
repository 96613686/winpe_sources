# VmsVmNicPvtConvertRndisPacketToNbl

- ea: `0x14002f668`
- end: `0x14002fcb5`
- name: `VmsVmNicPvtConvertRndisPacketToNbl`
- size: `1613`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002f1f0`

## callees

- `0x140013010`
- `0x1400132b0`
- `0x1400147e0`
- `0x14001736c`
- `0x140027a64`
- `0x14002f668`
- `0x1400313cc`
- `0x140032b1c`
- `0x14004f234`
- `0x14006a868`
- `0x1400812d8`
- `0x14008497c`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x14002f8d7`
- `ntoskrnl!MmSizeOfMdl` at `0x14002f8d7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002fc08`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002fc08`
- `ntoskrnl!IoFreeMdl` at `0x14002f969`
- `ntoskrnl!IoFreeMdl` at `0x14002f969`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002f9c1`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002f9c1`
- `ntoskrnl!IoAllocateMdl` at `0x14002f996`
- `ntoskrnl!IoAllocateMdl` at `0x14002f996`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f817`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f817`
- `NDIS!NdisAllocateNetBufferList` at `0x14002f6c6`
- `NDIS!NdisAllocateNetBufferList` at `0x14002f6c6`
- `NDIS!NdisReleaseRWLock` at `0x14002fc6a`
- `NDIS!NdisReleaseRWLock` at `0x14002fc6a`
- `NDIS!NdisGetDataBuffer` at `0x14002f7c2`
- `NDIS!NdisGetDataBuffer` at `0x14002f7c2`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14002f7a3`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14002f7a3`

## pseudocode

```c
__int64 __fastcall VmsVmNicPvtConvertRndisPacketToNbl(__int64 a1, __int64 **a2, PNET_BUFFER_LIST *a3)
{
  bool v4; // cf
  int fixed; // ebx
  __int64 v6; // r13
  unsigned int v7; // ebp
  ULONG v8; // ebx
  PNET_BUFFER_LIST NetBufferList; // rax
  PNET_BUFFER_LIST v10; // rsi
  __int64 v11; // rcx
  struct _NET_BUFFER *v12; // rdi
  int v13; // ecx
  unsigned int v14; // r12d
  unsigned int v15; // ecx
  __int16 v16; // ax
  unsigned int v17; // eax
  int v18; // ecx
  char *DataBuffer; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  _MDL *CurrentMdl; // rcx
  char *v23; // r9
  struct _MDL *v24; // r15
  unsigned int v25; // ebp
  char *MappedSystemVa; // rcx
  char *v27; // rax
  ULONG v28; // edi
  ULONG v29; // eax
  ULONG v30; // edi
  char *v31; // rbx
  void *v32; // r8
  struct _MDL *Mdl; // rbx
  __int64 v34; // rcx
  struct _MDL *v35; // rcx
  struct _NET_BUFFER *v36; // rax
  void *v37; // rax
  void *v38; // rax
  void *v39; // rax
  void *v40; // rax
  void *v41; // rax
  void *v42; // rax
  void *v43; // rax
  void *v44; // rax
  __int64 *v45; // rax
  void *v46; // rax
  __int16 v47; // r14
  int v48; // eax
  __int64 v49; // rdi
  __int64 v50; // rcx
  __int64 v51; // rax
  ULONG CurrentProcessorNumber; // eax
  __int64 v53; // r8
  __int64 v54; // rcx
  __int64 v55; // rbp
  __int64 v56; // rax
  unsigned int ByteCount; // [rsp+30h] [rbp-78h]
  char *v59; // [rsp+38h] [rbp-70h]
  char *VirtualAddress; // [rsp+40h] [rbp-68h]
  unsigned __int64 VirtualAddressa; // [rsp+40h] [rbp-68h]
  struct _MDL **p_Next; // [rsp+48h] [rbp-60h]
  struct _NET_BUFFER *v63; // [rsp+50h] [rbp-58h]
  struct _LOCK_STATE_EX LockState; // [rsp+B8h] [rbp+10h] BYREF
  PNET_BUFFER_LIST *v66; // [rsp+C0h] [rbp+18h]
  ULONG v67; // [rsp+C8h] [rbp+20h]

  v66 = a3;
  v4 = *((_DWORD *)a2 + 5) < 0xEu;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( v4 )
    return (unsigned int)-1073741811;
  v6 = *(_QWORD *)(a1 + 680);
  v7 = VmsSafeHeaderSize;
  v8 = VmsMaxSafeHeaderSize;
  NetBufferList = NdisAllocateNetBufferList(*(NDIS_HANDLE *)(a1 + 232), 0x158u, 0);
  v10 = NetBufferList;
  if ( !NetBufferList )
    return (unsigned int)-1073741670;
  VmsNblHelperInitializeNblContext(NetBufferList, 152, 1);
  v12 = *(struct _NET_BUFFER **)(v11 + 8);
  v63 = v12;
  VmsNblHelperInitializeOriginalNbl(v11, 4);
  VmsNblHelperSetSourceInContext(v10, v6);
  v59 = (char *)v10->NetBufferListInfo[18];
  v13 = 0;
  *((_QWORD *)v59 + 4) = a2;
  v14 = *((_DWORD *)a2 + 5);
  if ( v7 >= v14 )
    v7 = *((_DWORD *)a2 + 5);
  if ( v8 >= v14 )
    v8 = *((_DWORD *)a2 + 5);
  v67 = v8;
  if ( v7 == v14 )
    v13 = 1024;
  v15 = HIDWORD(v10->NetBufferListInfo[19]) & 0xFFFFFBFF | v13;
  v16 = 4095;
  if ( v7 < 0xFFF )
    v16 = v7;
  v17 = (v15 & 0xFF8007FF ^ ((v16 & 0xFFF) << 11)) & 0xFEFFFFFF;
  HIDWORD(v10->NetBufferListInfo[19]) = v17;
  if ( *(_BYTE *)(v6 + 1877) || (v18 = 0x800000, *((_BYTE *)a2 + 24)) )
    v18 = 0;
  HIDWORD(v10->NetBufferListInfo[19]) = v18 | v17 & 0xFF7FFFFF;
  NdisRetreatNetBufferDataStart(v12, v8, 0, 0);
  DataBuffer = (char *)NdisGetDataBuffer(v12, v8, 0, 1u, 0);
  CurrentMdl = v12->CurrentMdl;
  v23 = DataBuffer;
  v24 = (struct _MDL *)*a2;
  v25 = *((_DWORD *)a2 + 4);
  p_Next = &CurrentMdl->Next;
  VirtualAddress = DataBuffer;
  if ( v8 )
  {
    while ( 1 )
    {
      if ( (v24->MdlFlags & 5) != 0 )
      {
        MappedSystemVa = (char *)v24->MappedSystemVa;
      }
      else
      {
        v27 = (char *)MmMapLockedPagesSpecifyCache(v24, 0, MmCached, 0, 0, 0x40000000u);
        v23 = VirtualAddress;
        MappedSystemVa = v27;
      }
      if ( !MappedSystemVa )
        goto LABEL_34;
      v28 = v8;
      ByteCount = v24->ByteCount;
      if ( ByteCount - v25 < v8 )
        v28 = ByteCount - v25;
      memmove(v23, &MappedSystemVa[v25], v28);
      v29 = v28 + v25;
      v23 = &VirtualAddress[v28];
      v14 -= v28;
      v8 = v67 - v28;
      VirtualAddress = v23;
      v67 -= v28;
      if ( v28 + v25 == ByteCount )
        v24 = v24->Next;
      v25 = 0;
      if ( v29 != ByteCount )
        v25 = v29;
      if ( !v8 )
      {
        CurrentMdl = (_MDL *)p_Next;
        break;
      }
    }
  }
  if ( v14 )
  {
    if ( !v25 )
    {
      v36 = v63;
LABEL_47:
      CurrentMdl->Next = v24;
      v36->DataLength += v14;
      *((_QWORD *)v59 + 6) = *a2[1];
      *a2[1] = 0;
      goto LABEL_48;
    }
    v30 = v14;
    v31 = (char *)v24->StartVa + v24->ByteOffset + v25;
    v67 = v24->ByteCount;
    VirtualAddressa = (unsigned __int64)v31;
    if ( v67 - v25 < v14 )
      v30 = v67 - v25;
    if ( MmSizeOfMdl(v31, v30) > 0x58 )
    {
      Mdl = IoAllocateMdl(v31, v30, 0, 0, 0);
      if ( !Mdl )
      {
LABEL_34:
        fixed = -1073741670;
LABEL_35:
        v34 = *((_QWORD *)v59 + 6);
        if ( v34 )
          *a2[1] = v34;
        v35 = (struct _MDL *)*((_QWORD *)v59 + 5);
        if ( v35 )
          IoFreeMdl(v35);
        VmsNblHelperFreeNetBufferList(v10);
        return (unsigned int)fixed;
      }
      v32 = (void *)VirtualAddressa;
      *((_QWORD *)v59 + 5) = Mdl;
    }
    else
    {
      v32 = v31;
      Mdl = (struct _MDL *)(v59 + 56);
      *((_QWORD *)v59 + 7) = 0;
      *((_WORD *)v59 + 33) = 0;
      *((_WORD *)v59 + 32) = 8 * ((((VirtualAddressa & 0xFFF) + 4095 + v30) >> 12) + 6);
      *((_QWORD *)v59 + 11) = VirtualAddressa & 0xFFFFFFFFFFFFF000uLL;
      *((_DWORD *)v59 + 25) = VirtualAddressa & 0xFFF;
      *((_DWORD *)v59 + 24) = v30;
    }
    IoBuildPartialMdl(v24, Mdl, v32, v30);
    v14 -= v30;
    if ( v30 + v25 == v67 )
      v24 = v24->Next;
    CurrentMdl = Mdl;
    *p_Next = Mdl;
    v36 = v63;
    v63->DataLength += v30;
    if ( v14 )
      goto LABEL_47;
  }
LABEL_48:
  v37 = (void *)*((unsigned int *)a2 + 11);
  if ( (_DWORD)v37 )
  {
    v10->NetBufferListInfo[2] = v37;
  }
  else
  {
    v38 = (void *)*((unsigned int *)a2 + 10);
    if ( (_DWORD)v38 )
      v10->NetBufferListInfo[0] = v38;
  }
  v39 = (void *)*((unsigned int *)a2 + 12);
  if ( (_DWORD)v39 )
    v10->NetBufferListInfo[1] = v39;
  v40 = (void *)*((unsigned int *)a2 + 13);
  if ( (_DWORD)v40 )
    v10->NetBufferListInfo[11] = v40;
  v41 = (void *)*((unsigned int *)a2 + 14);
  if ( (_DWORD)v41 )
    v10->NetBufferListInfo[12] = v41;
  v42 = (void *)*((unsigned int *)a2 + 15);
  if ( (_DWORD)v42 )
    v10->NetBufferListInfo[4] = v42;
  if ( a2[9] )
    v10->NetBufferListInfo[20] = (void *)*((unsigned int *)a2 + 18);
  v43 = (void *)*((unsigned int *)a2 + 21);
  if ( (_DWORD)v43 )
    v10->NetBufferListInfo[9] = v43;
  v44 = (void *)*((unsigned int *)a2 + 20);
  if ( (_DWORD)v44 )
    v10->NetBufferListInfo[8] = v44;
  v45 = a2[11];
  if ( v45 )
    v10->NetBufferListInfo[17] = v45;
  v46 = (void *)*((unsigned int *)a2 + 24);
  if ( (_DWORD)v46 )
    v10->NetBufferListInfo[6] = v46;
  fixed = VmsVmNicPvtFixTcpHeaderOffsets(v10, v20, v21, v23);
  if ( fixed < 0 )
    goto LABEL_35;
  VmsVmNicSanitizeNblOffloadInfo(v6, v10);
  if ( VmsVmNicDropOversizedSends && (unsigned int)VmsNblHelperGetMaxSegmentSize(v10) > *(_DWORD *)(v6 + 3356) )
  {
    fixed = -1073741585;
    goto LABEL_35;
  }
  v47 = -1;
  WORD1(v10->NetBufferListInfo[14]) = *(_WORD *)(a1 + 760);
  v48 = (int)v10->NetBufferListInfo[8];
  if ( v48 )
    v47 = v48 & 0xF;
  if ( ((*(_DWORD *)(v6 + 1872) - 1) & 0xFFFFFFFD) != 0 )
    __fastfail(0xC0000024);
  v49 = 0;
  if ( !*(_QWORD *)(v6 + 6320) || (v49 = v6 + 5696, v6 == -5696) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      -3,
      19,
      216,
      (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
      (__int64)"queueGroup != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( (*(_BYTE *)(v49 + 640) & 1) != 0 )
  {
    if ( (*(_DWORD *)(v49 + 40) & 0x10) != 0 )
    {
      VmsOmObjectLockShared(v6, &LockState, 0);
      v50 = *(_QWORD *)(v49 + 624);
      v51 = 0;
      if ( v50 )
      {
        if ( v47 == -1 )
          v51 = v49 + 400;
        else
          v51 = v50 + 224LL * v47;
      }
      _InterlockedIncrement64((volatile signed __int64 *)(v51 + 72));
      CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
      v54 = *(_QWORD *)(v49 + 624);
      v55 = 0;
      if ( v54 )
      {
        if ( v47 == -1 )
          v55 = v49 + 400;
        else
          v55 = v54 + 224LL * v47;
      }
      LOBYTE(v53) = 1;
      if ( (unsigned int)VmsVmNicPvtChannelGetOpenChannelProcIndex(a1, *(unsigned __int16 *)(v55 + 42), v53) != CurrentProcessorNumber )
        _InterlockedIncrement64((volatile signed __int64 *)(v55 + 104));
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 56), &LockState);
    }
  }
  else
  {
    v56 = 0;
    if ( *(_QWORD *)(v49 + 624) )
      v56 = v49 + 176;
    _InterlockedIncrement64((volatile signed __int64 *)(v56 + 72));
  }
  *v66 = v10;
  return (unsigned int)fixed;
}

```

## disassembly

```asm
0x14002f668  mov     r11, rsp
0x14002f66b  mov     [r11+18h], r8
0x14002f66f  mov     [r11+8], rcx
0x14002f673  push    rbx
0x14002f674  push    rbp
0x14002f675  push    rsi
0x14002f676  push    rdi
0x14002f677  push    r12
0x14002f679  push    r13
0x14002f67b  push    r14
0x14002f67d  push    r15
0x14002f67f  sub     rsp, 68h
0x14002f683  mov     rax, rcx
0x14002f686  mov     r14, rdx
0x14002f689  xor     ecx, ecx
0x14002f68b  cmp     dword ptr [rdx+14h], 0Eh
0x14002f68f  mov     [r11+10h], cx
0x14002f694  mov     [r11+12h], cl
0x14002f698  jnb     short loc_14002F6A4
0x14002f69a  mov     ebx, 0C000000Dh
0x14002f69f  jmp     loc_14002FCA1
0x14002f6a4  mov     rcx, [rax+0E8h]; PoolHandle
0x14002f6ab  xor     r8d, r8d; ContextBackFill
0x14002f6ae  mov     r13, [rax+2A8h]
0x14002f6b5  mov     edx, 158h; ContextSize
0x14002f6ba  mov     ebp, cs:VmsSafeHeaderSize
0x14002f6c0  mov     ebx, cs:VmsMaxSafeHeaderSize
0x14002f6c6  call    cs:__imp_NdisAllocateNetBufferList
0x14002f6cd  nop     dword ptr [rax+rax+00h]
0x14002f6d2  xor     r15d, r15d
0x14002f6d5  mov     rsi, rax
0x14002f6d8  test    rax, rax
0x14002f6db  jz      loc_14002FC9C
0x14002f6e1  mov     edx, 98h
0x14002f6e6  lea     r8d, [r15+1]
0x14002f6ea  mov     rcx, rax
0x14002f6ed  call    VmsNblHelperInitializeNblContext
0x14002f6f2  mov     rdi, [rcx+8]
0x14002f6f6  lea     edx, [r15+4]
0x14002f6fa  mov     [rsp+0A8h+var_58], rdi
0x14002f6ff  call    VmsNblHelperInitializeOriginalNbl
0x14002f704  mov     rcx, rsi
0x14002f707  mov     rdx, r13
0x14002f70a  call    VmsNblHelperSetSourceInContext
0x14002f70f  mov     rax, [rsi+120h]
0x14002f716  mov     edx, 0FFFh
0x14002f71b  mov     [rsp+0A8h+var_70], rax
0x14002f720  mov     ecx, r15d
0x14002f723  mov     [rax+20h], r14
0x14002f727  mov     eax, 400h
0x14002f72c  mov     r12d, [r14+14h]
0x14002f730  cmp     ebp, r12d
0x14002f733  cmovnb  ebp, r12d
0x14002f737  cmp     ebx, r12d
0x14002f73a  cmovnb  ebx, r12d
0x14002f73e  cmp     ebp, r12d
0x14002f741  mov     [rsp+0A8h+arg_18], ebx
0x14002f748  cmovz   ecx, eax
0x14002f74b  mov     eax, [rsi+12Ch]
0x14002f751  btr     eax, 0Ah
0x14002f755  or      ecx, eax
0x14002f757  mov     eax, edx
0x14002f759  cmp     ebp, edx
0x14002f75b  cmovb   eax, ebp
0x14002f75e  and     ecx, 0FF8007FFh
0x14002f764  and     eax, edx
0x14002f766  shl     eax, 0Bh
0x14002f769  xor     eax, ecx
0x14002f76b  btr     eax, 18h
0x14002f76f  mov     [rsi+12Ch], eax
0x14002f775  cmp     [r13+755h], r15b
0x14002f77c  jnz     short loc_14002F789
0x14002f77e  mov     ecx, 800000h
0x14002f783  cmp     [r14+18h], r15b
0x14002f787  jz      short loc_14002F78C
0x14002f789  mov     ecx, r15d
0x14002f78c  btr     eax, 17h
0x14002f790  xor     r9d, r9d; AllocateMdlHandler
0x14002f793  or      eax, ecx
0x14002f795  xor     r8d, r8d; DataBackFill
0x14002f798  mov     rcx, rdi; NetBuffer
0x14002f79b  mov     [rsi+12Ch], eax
0x14002f7a1  mov     edx, ebx; DataOffsetDelta
0x14002f7a3  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14002f7aa  nop     dword ptr [rax+rax+00h]
0x14002f7af  mov     r9d, 1; AlignMultiple
0x14002f7b5  mov     [rsp+0A8h+AlignOffset], r15d; AlignOffset
0x14002f7ba  xor     r8d, r8d; Storage
0x14002f7bd  mov     edx, ebx; BytesNeeded
0x14002f7bf  mov     rcx, rdi; NetBuffer
0x14002f7c2  call    cs:__imp_NdisGetDataBuffer
0x14002f7c9  nop     dword ptr [rax+rax+00h]
0x14002f7ce  mov     rcx, [rdi+8]
0x14002f7d2  mov     r9, rax
0x14002f7d5  mov     r15, [r14]
0x14002f7d8  mov     ebp, [r14+10h]
0x14002f7dc  mov     [rsp+0A8h+var_60], rcx
0x14002f7e1  mov     [rsp+0A8h+VirtualAddress], rax
0x14002f7e6  test    ebx, ebx
0x14002f7e8  jz      loc_14002F899
0x14002f7ee  test    byte ptr [r15+0Ah], 5
0x14002f7f3  jz      short loc_14002F7FB
0x14002f7f5  mov     rcx, [r15+18h]
0x14002f7f9  jmp     short loc_14002F82B
0x14002f7fb  xor     r9d, r9d; RequestedAddress
0x14002f7fe  mov     [rsp+0A8h+Priority], 40000000h; Priority
0x14002f806  xor     edx, edx; AccessMode
0x14002f808  mov     [rsp+0A8h+AlignOffset], 0; BugCheckOnFailure
0x14002f810  mov     rcx, r15; MemoryDescriptorList
0x14002f813  lea     r8d, [r9+1]; CacheType
0x14002f817  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002f81e  nop     dword ptr [rax+rax+00h]
0x14002f823  mov     r9, [rsp+0A8h+VirtualAddress]
0x14002f828  mov     rcx, rax
0x14002f82b  test    rcx, rcx
0x14002f82e  jz      loc_14002F946
0x14002f834  mov     eax, [r15+28h]
0x14002f838  mov     edi, ebx
0x14002f83a  mov     [rsp+0A8h+var_78], eax
0x14002f83e  sub     eax, ebp
0x14002f840  cmp     eax, ebx
0x14002f842  mov     edx, ebp
0x14002f844  cmovb   edi, eax
0x14002f847  add     rdx, rcx; Src
0x14002f84a  mov     r8d, edi; Size
0x14002f84d  mov     rcx, r9; void *
0x14002f850  mov     ebx, edi
0x14002f852  call    memmove
0x14002f857  mov     r9, [rsp+0A8h+VirtualAddress]
0x14002f85c  lea     eax, [rdi+rbp]
0x14002f85f  mov     ecx, [rsp+0A8h+var_78]
0x14002f863  add     r9, rbx
0x14002f866  mov     ebx, [rsp+0A8h+arg_18]
0x14002f86d  sub     r12d, edi
0x14002f870  sub     ebx, edi
0x14002f872  mov     [rsp+0A8h+VirtualAddress], r9
0x14002f877  mov     [rsp+0A8h+arg_18], ebx
0x14002f87e  cmp     eax, ecx
0x14002f880  jnz     short loc_14002F885
0x14002f882  mov     r15, [r15]
0x14002f885  xor     ebp, ebp
0x14002f887  cmp     eax, ecx
0x14002f889  cmovnz  ebp, eax
0x14002f88c  test    ebx, ebx
0x14002f88e  jnz     loc_14002F7EE
0x14002f894  mov     rcx, [rsp+0A8h+var_60]
0x14002f899  test    r12d, r12d
0x14002f89c  jz      loc_14002FA20
0x14002f8a2  test    ebp, ebp
0x14002f8a4  jz      loc_14002F9F9
0x14002f8aa  mov     ebx, [r15+2Ch]
0x14002f8ae  mov     edi, r12d
0x14002f8b1  add     rbx, [r15+20h]
0x14002f8b5  mov     eax, ebp
0x14002f8b7  add     rbx, rax
0x14002f8ba  mov     eax, [r15+28h]
0x14002f8be  mov     [rsp+0A8h+arg_18], eax
0x14002f8c5  mov     rcx, rbx; Base
0x14002f8c8  sub     eax, ebp
0x14002f8ca  mov     [rsp+0A8h+VirtualAddress], rbx
0x14002f8cf  cmp     eax, r12d
0x14002f8d2  cmovb   edi, eax
0x14002f8d5  mov     edx, edi; Length
0x14002f8d7  call    cs:__imp_MmSizeOfMdl
0x14002f8de  nop     dword ptr [rax+rax+00h]
0x14002f8e3  cmp     rax, 58h ; 'X'
0x14002f8e7  ja      loc_14002F982
0x14002f8ed  mov     r8, [rsp+0A8h+VirtualAddress]
0x14002f8f2  mov     r9d, 0FFFh
0x14002f8f8  mov     rbx, [rsp+0A8h+var_70]
0x14002f8fd  mov     edx, r8d
0x14002f900  add     rbx, 38h ; '8'
0x14002f904  mov     ecx, edi
0x14002f906  mov     eax, edx
0x14002f908  and     rax, r9
0x14002f90b  add     rax, r9
0x14002f90e  add     rcx, rax
0x14002f911  mov     qword ptr [rbx], 0
0x14002f918  xor     eax, eax
0x14002f91a  shr     rcx, 0Ch
0x14002f91e  mov     [rbx+0Ah], ax
0x14002f922  add     cx, 6
0x14002f926  shl     cx, 3
0x14002f92a  mov     rax, r8
0x14002f92d  and     rax, 0FFFFFFFFFFFFF000h
0x14002f933  mov     [rbx+8], cx
0x14002f937  and     edx, r9d
0x14002f93a  mov     [rbx+20h], rax
0x14002f93e  mov     [rbx+2Ch], edx
0x14002f941  mov     [rbx+28h], edi
0x14002f944  jmp     short loc_14002F9B8
0x14002f946  mov     ebx, 0C000009Ah
0x14002f94b  mov     rdx, [rsp+0A8h+var_70]
0x14002f950  mov     rcx, [rdx+30h]
0x14002f954  test    rcx, rcx
0x14002f957  jz      short loc_14002F960
0x14002f959  mov     rax, [r14+8]
0x14002f95d  mov     [rax], rcx
0x14002f960  mov     rcx, [rdx+28h]; Mdl
0x14002f964  test    rcx, rcx
0x14002f967  jz      short loc_14002F975
0x14002f969  call    cs:__imp_IoFreeMdl
0x14002f970  nop     dword ptr [rax+rax+00h]
0x14002f975  mov     rcx, rsi; NetBufferList
0x14002f978  call    VmsNblHelperFreeNetBufferList
0x14002f97d  jmp     loc_14002FCA1
0x14002f982  xor     r9d, r9d; ChargeQuota
0x14002f985  mov     qword ptr [rsp+0A8h+AlignOffset], 0; Irp
0x14002f98e  xor     r8d, r8d; SecondaryBuffer
0x14002f991  mov     edx, edi; Length
0x14002f993  mov     rcx, rbx; VirtualAddress
0x14002f996  call    cs:__imp_IoAllocateMdl
0x14002f99d  nop     dword ptr [rax+rax+00h]
0x14002f9a2  mov     rbx, rax
0x14002f9a5  test    rax, rax
0x14002f9a8  jz      short loc_14002F946
0x14002f9aa  mov     rax, [rsp+0A8h+var_70]
0x14002f9af  mov     r8, [rsp+0A8h+VirtualAddress]; VirtualAddress
0x14002f9b4  mov     [rax+28h], rbx
0x14002f9b8  mov     r9d, edi; Length
0x14002f9bb  mov     rdx, rbx; TargetMdl
0x14002f9be  mov     rcx, r15; SourceMdl
0x14002f9c1  call    cs:__imp_IoBuildPartialMdl
0x14002f9c8  nop     dword ptr [rax+rax+00h]
0x14002f9cd  lea     eax, [rdi+rbp]
0x14002f9d0  sub     r12d, edi
0x14002f9d3  cmp     eax, [rsp+0A8h+arg_18]
0x14002f9da  jnz     short loc_14002F9DF
0x14002f9dc  mov     r15, [r15]
0x14002f9df  mov     rax, [rsp+0A8h+var_60]
0x14002f9e4  mov     rcx, rbx
0x14002f9e7  mov     [rax], rbx
0x14002f9ea  mov     rax, [rsp+0A8h+var_58]
0x14002f9ef  add     [rax+18h], edi
0x14002f9f2  test    r12d, r12d
0x14002f9f5  jz      short loc_14002FA20
0x14002f9f7  jmp     short loc_14002F9FE
0x14002f9f9  mov     rax, [rsp+0A8h+var_58]
0x14002f9fe  mov     [rcx], r15
0x14002fa01  add     [rax+18h], r12d
0x14002fa05  mov     rax, [r14+8]
0x14002fa09  mov     rcx, [rax]
0x14002fa0c  mov     rax, [rsp+0A8h+var_70]
0x14002fa11  mov     [rax+30h], rcx
0x14002fa15  mov     rax, [r14+8]
0x14002fa19  mov     qword ptr [rax], 0
0x14002fa20  mov     eax, [r14+2Ch]
0x14002fa24  test    eax, eax
0x14002fa26  jz      short loc_14002FA31
0x14002fa28  mov     [rsi+0A0h], rax
0x14002fa2f  jmp     short loc_14002FA40
0x14002fa31  mov     eax, [r14+28h]
0x14002fa35  test    eax, eax
0x14002fa37  jz      short loc_14002FA40
0x14002fa39  mov     [rsi+90h], rax
0x14002fa40  mov     eax, [r14+30h]
0x14002fa44  test    eax, eax
0x14002fa46  jz      short loc_14002FA4F
0x14002fa48  mov     [rsi+98h], rax
0x14002fa4f  mov     eax, [r14+34h]
0x14002fa53  test    eax, eax
0x14002fa55  jz      short loc_14002FA5E
0x14002fa57  mov     [rsi+0E8h], rax
0x14002fa5e  mov     eax, [r14+38h]
0x14002fa62  test    eax, eax
0x14002fa64  jz      short loc_14002FA6D
0x14002fa66  mov     [rsi+0F0h], rax
0x14002fa6d  mov     eax, [r14+3Ch]
0x14002fa71  test    eax, eax
0x14002fa73  jz      short loc_14002FA7C
0x14002fa75  mov     [rsi+0B0h], rax
0x14002fa7c  cmp     qword ptr [r14+48h], 0
0x14002fa81  jz      short loc_14002FA8E
0x14002fa83  mov     eax, [r14+48h]
0x14002fa87  mov     [rsi+130h], rax
0x14002fa8e  mov     eax, [r14+54h]
0x14002fa92  test    eax, eax
0x14002fa94  jz      short loc_14002FA9D
0x14002fa96  mov     [rsi+0D8h], rax
0x14002fa9d  mov     eax, [r14+50h]
0x14002faa1  test    eax, eax
0x14002faa3  jz      short loc_14002FAAC
0x14002faa5  mov     [rsi+0D0h], rax
0x14002faac  mov     rax, [r14+58h]
0x14002fab0  test    rax, rax
0x14002fab3  jz      short loc_14002FABC
0x14002fab5  mov     [rsi+118h], rax
0x14002fabc  mov     eax, [r14+60h]
0x14002fac0  test    eax, eax
0x14002fac2  jz      short loc_14002FACB
0x14002fac4  mov     [rsi+0C0h], rax
0x14002facb  mov     rcx, rsi
0x14002face  call    VmsVmNicPvtFixTcpHeaderOffsets
0x14002fad3  mov     ebx, eax
0x14002fad5  test    eax, eax
0x14002fad7  js      loc_14002F94B
0x14002fadd  mov     rdx, rsi
0x14002fae0  mov     rcx, r13
0x14002fae3  call    VmsVmNicSanitizeNblOffloadInfo
0x14002fae8  cmp     cs:VmsVmNicDropOversizedSends, 0
  ... truncated ...
```
