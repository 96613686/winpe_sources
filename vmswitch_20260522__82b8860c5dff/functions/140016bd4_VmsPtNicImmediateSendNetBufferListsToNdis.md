# VmsPtNicImmediateSendNetBufferListsToNdis

- ea: `0x140016bd4`
- end: `0x140017365`
- name: `VmsPtNicImmediateSendNetBufferListsToNdis`
- size: `1937`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140016bb0`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140014330`
- `0x140016ac0`
- `0x140016bd4`
- `0x140017a7c`
- `0x140017b4c`
- `0x140017ca8`
- `0x140027a64`
- `0x140062a88`
- `0x14008497c`
- `0x14008b6a8`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140016dae`
- `ntoskrnl!KeBugCheckEx` at `0x140016f7b`
- `ntoskrnl!KeBugCheckEx` at `0x14001709a`
- `ntoskrnl!KeBugCheckEx` at `0x14001711f`
- `ntoskrnl!KeBugCheckEx` at `0x140016dae`
- `ntoskrnl!KeBugCheckEx` at `0x140016f7b`
- `ntoskrnl!KeBugCheckEx` at `0x14001709a`
- `ntoskrnl!KeBugCheckEx` at `0x14001711f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016cf8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016d4c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016d8f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016e03`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016f32`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016f58`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001703f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001707b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400170d6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400170fc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016cf8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016d4c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016d8f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016e03`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016f32`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140016f58`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001703f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001707b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400170d6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400170fc`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016c13`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016c13`
- `NDIS!NdisSendNetBufferLists` at `0x140017023`
- `NDIS!NdisSendNetBufferLists` at `0x1400170bf`
- `NDIS!NdisSendNetBufferLists` at `0x140017023`
- `NDIS!NdisSendNetBufferLists` at `0x1400170bf`
- `NDIS!NdisAcquireRWLockRead` at `0x140016fa4`
- `NDIS!NdisAcquireRWLockRead` at `0x140016fa4`
- `NDIS!NdisReleaseRWLock` at `0x140016fd6`
- `NDIS!NdisReleaseRWLock` at `0x140016fd6`
- `HAL!KeQueryPerformanceCounter` at `0x140017152`
- `HAL!KeQueryPerformanceCounter` at `0x140017152`

## string_xrefs

- `0x14001727b`: `ProtocolNic->Type == VmsNicProtocol`

## pseudocode

```c
void __fastcall VmsPtNicImmediateSendNetBufferListsToNdis(
        _QWORD *a1,
        unsigned __int16 a2,
        struct _NET_BUFFER_LIST *a3,
        ULONG a4)
{
  __int64 v4; // rsi
  struct _NET_BUFFER_LIST *v6; // rbp
  char v8; // r12
  __int64 v9; // rdi
  char v10; // r14
  __int64 v11; // r15
  unsigned int v12; // edi
  _SLIST_HEADER *Alignment; // rax
  __int64 v14; // rsi
  __int64 v15; // r14
  __int64 v16; // r12
  __int64 NicHeaderAtIndex; // r13
  ULONG v18; // eax
  int v19; // edx
  ULONG_PTR v20; // r14
  __int64 v21; // r12
  ULONG v22; // eax
  __int64 v23; // r14
  __int64 v24; // rsi
  int v25; // eax
  __int64 v26; // rax
  _QWORD *v27; // rax
  __int64 v28; // rax
  __int64 v29; // r14
  NDIS_HANDLE *v30; // r14
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v32; // rbx
  ULONG v33; // eax
  char v34; // di
  int FirstAvailableNicIndex; // eax
  __int64 v36; // r8
  ULONG v37; // eax
  int v38; // edx
  ULONG_PTR v39; // rbx
  __int64 v40; // rsi
  ULONG_PTR v41; // rdi
  ULONG v42; // eax
  ULONG v43; // eax
  ULONG_PTR v44; // rbx
  ULONG v45; // eax
  LARGE_INTEGER *v46; // rbx
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v48; // rcx
  __int64 v49; // rdx
  LARGE_INTEGER *v50; // rcx
  unsigned __int8 v51; // r8
  LARGE_INTEGER v52; // rdx
  LARGE_INTEGER v53; // rcx
  char *v54; // rcx
  char *v55; // rcx
  char *v56; // rcx
  unsigned __int16 v57[2]; // [rsp+30h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+34h] [rbp-44h] BYREF
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]
  char v60; // [rsp+80h] [rbp+8h]

  v4 = a2;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = a3;
  if ( (a4 & 1) != 0 || (v8 = 0, KeGetCurrentIrql() == 2) )
    v8 = 1;
  v60 = v8;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( v6 )
    {
      v27 = v6->NetBufferListInfo[18];
      if ( v27 )
      {
        v28 = v27[2];
        if ( v28 )
        {
          *(_DWORD *)(v28 + 184) = 11572;
          *(_QWORD *)(v28 + 176) = "VmsPtNicImmediateSendNetBufferListsToNdis";
          *(_QWORD *)(v28 + 168) = retaddr;
        }
      }
    }
  }
  v9 = *a1;
  if ( *(_DWORD *)(*a1 + 68LL) != 1 || *((_DWORD *)a1 + 24) != 1 || *((int *)a1 + 25) > 1 || *((_BYTE *)a1 + 104) == 1 )
    goto LABEL_32;
  v10 = 0;
  if ( ((g_VmsSkuInfo & 1) == 0 || (g_VmsSkuInfo & 2) != 0) && v9 )
  {
    if ( *(_DWORD *)(v9 + 1872) != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        0,
        19,
        292,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        "ProtocolNic->Type == VmsNicProtocol");
      if ( *(_DWORD *)(v9 + 1872) != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v23 = *(_QWORD *)(v9 + 1888);
    if ( v23 )
      v10 = *(_BYTE *)(v23 + 8912);
    else
      v10 = *(_BYTE *)(v9 + 1896);
  }
  if ( (_WORD)v4 )
  {
    v11 = a1[v4 + 236];
  }
  else
  {
    v26 = *a1;
    LOWORD(v4) = 0;
    v57[0] = 0;
    if ( v10 )
    {
      v11 = 0;
      v34 = 0;
      NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v26 + 56), &LockState, 0);
      FirstAvailableNicIndex = VmsPtPvtFindFirstAvailableNicIndex(*a1, v57);
      v4 = v57[0];
      if ( !FirstAvailableNicIndex && v57[0] <= 0x3Fu )
      {
        v34 = 1;
        VmsNblUpdateDestinationForSet(v6, *a1, v36, v57[0]);
        v11 = a1[v4 + 236];
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*a1 + 56LL), &LockState);
      if ( !v34 )
      {
        v25 = -536862704;
        goto LABEL_33;
      }
    }
    else
    {
      v11 = v26 + 1232;
    }
  }
  if ( !v11 )
  {
    v25 = -536862703;
    goto LABEL_33;
  }
  v12 = 0;
  Alignment = (_SLIST_HEADER *)v6;
  if ( v6 )
  {
    do
    {
      Alignment = (_SLIST_HEADER *)Alignment->Alignment;
      ++v12;
    }
    while ( Alignment );
  }
  if ( v10 )
  {
    v29 = a1[(unsigned __int16)v4 + 236];
    if ( v29 )
    {
      v30 = *(NDIS_HANDLE **)(v29 + 632);
      if ( v30 )
      {
        if ( *(_DWORD *)(v11 + 16) == 2 )
        {
          LOBYTE(a3) = 1;
          if ( (unsigned __int8)VmsPtPvtAcquireOutgoingRefCount(v30, v12, a3) )
          {
            if ( v8 )
            {
              CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
              v32 = CurrentProcessorNumber;
              if ( CurrentProcessorNumber == -1
                || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
                || (v56 = (char *)VmsPlanCpuTable + 5440 * v32) == 0 )
              {
                v33 = KeGetCurrentProcessorNumberEx(0);
                KeBugCheckEx(0x121u, v32, v33, 0, 0);
              }
              NetDispatchProfilerLeave(v56 + 1152);
            }
            NdisSendNetBufferLists(*v30, v6, 0, a4);
            if ( v8 )
            {
              v43 = KeGetCurrentProcessorNumberEx(0);
              v44 = v43;
              if ( v43 == -1
                || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v43)
                || (v55 = (char *)VmsPlanCpuTable + 5440 * v44) == 0 )
              {
                v45 = KeGetCurrentProcessorNumberEx(0);
                KeBugCheckEx(0x121u, v44, v45, 0, 0);
              }
              NetDispatchProfilerEnter(v55 + 1152, 1);
            }
            return;
          }
        }
      }
    }
    v25 = -536862702;
LABEL_33:
    VmsPktReportDroppedPacketEx(*a1, (_DWORD)v6, 2, 0, -1073676271, v25);
    VmsPtNicFinalComplete(a1, v6, 0);
    return;
  }
  v14 = a1[424];
  v15 = *(_QWORD *)(v14 + 8);
  v16 = *(_QWORD *)(v15 + 3312);
  if ( *(_BYTE *)(v16 + 104) == 1 )
  {
LABEL_32:
    v25 = -536862705;
    goto LABEL_33;
  }
  NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(*(_QWORD *)(v14 + 8), *(unsigned __int16 *)(v14 + 16));
  if ( NicHeaderAtIndex )
    _InterlockedAdd64(
      (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                + *(_QWORD *)(NicHeaderAtIndex + 24)
                                + 24),
      (int)v12);
  if ( *(_BYTE *)(v16 + 104) == 1 )
  {
    v24 = VmsPtGetNicHeaderAtIndex(v15, *(unsigned __int16 *)(v14 + 16));
    if ( v24 )
      _InterlockedAdd64(
        (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                  + *(_QWORD *)(v24 + 24)
                                  + 24),
        -v12);
    goto LABEL_32;
  }
  if ( v60 )
  {
    v18 = KeGetCurrentProcessorNumberEx(0);
    v20 = v18;
    if ( v18 == -1 )
      goto LABEL_25;
    v21 = v18 >> 6;
    if ( (unsigned int)v21 >= 0x40 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v19,
        19,
        10,
        (__int64)WPP_1993566a47c33aa75355351056e61473_Traceguids,
        "(*SetIndex < VMS_CPU_SET_ARRAY_COUNT)");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( !_bittest64(&VmsKnownProcessors[v21], v20 & 0x3F) || (v54 = (char *)VmsPlanCpuTable + 5440 * v20) == 0 )
    {
LABEL_25:
      v22 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v20, v22, 0, 0);
    }
    NetDispatchProfilerLeave(v54 + 1152);
  }
  NdisSendNetBufferLists((NDIS_HANDLE)a1[14], v6, *(_DWORD *)(v11 + 12), a4);
  if ( v60 )
  {
    v37 = KeGetCurrentProcessorNumberEx(0);
    v39 = v37;
    if ( v37 == -1 )
      goto LABEL_59;
    v40 = v37 >> 6;
    if ( (unsigned int)v40 >= 0x40 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v38,
        19,
        10,
        (__int64)WPP_1993566a47c33aa75355351056e61473_Traceguids,
        "(*SetIndex < VMS_CPU_SET_ARRAY_COUNT)");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( !_bittest64(&VmsKnownProcessors[v40], v39 & 0x3F) )
    {
LABEL_59:
      v41 = v39;
      goto LABEL_60;
    }
    v41 = v39;
    v46 = (LARGE_INTEGER *)((char *)VmsPlanCpuTable + 5440 * v39);
    if ( !v46 )
    {
LABEL_60:
      v42 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v41, v42, 0, 0);
    }
    if ( v46[146].QuadPart )
    {
      LOBYTE(v46[161].LowPart) = 1;
    }
    else
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v48 = v46[144];
      v46[146] = PerformanceCounter;
      v49 = *(_QWORD *)(v48.QuadPart + 13104);
      BYTE2(v46[150].u.LowPart) = 0;
      LOBYTE(v46[150].LowPart) = v49 != 0;
      v50 = v46 + 145;
      if ( !v49 || (v51 = 1, v50->QuadPart != v49) )
        v51 = 0;
      BYTE1(v46[150].LowPart) = v51;
      v50->QuadPart = v49;
      if ( v49 && !v51 )
      {
        v52.QuadPart = HIWORD(v46[150].QuadPart);
        v53 = v46[155];
        HIWORD(v46[150].QuadPart) = 1;
        v46[148] = PerformanceCounter;
        if ( v53.QuadPart <= (unsigned __int64)v52.QuadPart )
          v53 = v52;
        v46[147] = PerformanceCounter;
        ++v46[153].QuadPart;
        v46[155] = v53;
        v46[149].QuadPart = 0;
        BYTE4(v46[150].QuadPart) = -1;
      }
      HIWORD(v46[150].QuadPart) += v51;
    }
  }
}

```

## disassembly

```asm
0x140016bd4  mov     [rsp+arg_8], rbx
0x140016bd9  mov     [rsp+SendFlags], r9d
0x140016bde  push    rbp
0x140016bdf  push    rsi
0x140016be0  push    rdi
0x140016be1  push    r12
0x140016be3  push    r13
0x140016be5  push    r14
0x140016be7  push    r15
0x140016be9  sub     rsp, 40h
0x140016bed  xor     eax, eax
0x140016bef  movzx   esi, dx
0x140016bf2  xor     edx, edx
0x140016bf4  mov     word ptr [rsp+78h+LockState.OldIrql], ax
0x140016bf9  mov     r13d, r9d
0x140016bfc  mov     [rsp+78h+LockState.Flags], al
0x140016c00  mov     rbp, r8
0x140016c03  mov     rbx, rcx
0x140016c06  lea     r15d, [rax+1]
0x140016c0a  test    r15b, r9b
0x140016c0d  jnz     loc_140016E8D
0x140016c13  call    cs:__imp_KeGetCurrentIrql
0x140016c1a  nop     dword ptr [rax+rax+00h]
0x140016c1f  xor     edx, edx
0x140016c21  mov     r12b, dl
0x140016c24  cmp     al, 2
0x140016c26  jz      loc_140016E8D
0x140016c2c  mov     eax, cs:VmsDiagnosticFlags
0x140016c32  mov     rcx, [rsp+78h]
0x140016c37  mov     [rsp+78h+arg_0], r12b
0x140016c3f  test    r15b, al
0x140016c42  jnz     loc_140016E95
0x140016c48  mov     rdi, [rbx]
0x140016c4b  cmp     [rdi+44h], r15d
0x140016c4f  jnz     loc_140016E24
0x140016c55  cmp     [rbx+60h], r15d
0x140016c59  jnz     loc_140016E24
0x140016c5f  cmp     [rbx+64h], r15d
0x140016c63  jg      loc_140016E24
0x140016c69  cmp     [rbx+68h], r15b
0x140016c6d  jz      loc_140016E24
0x140016c73  mov     eax, cs:g_VmsSkuInfo
0x140016c79  mov     r14b, dl
0x140016c7c  test    r15b, al
0x140016c7f  jz      loc_140016DBB
0x140016c85  test    al, 2
0x140016c87  jnz     loc_140016DBB
0x140016c8d  test    si, si
0x140016c90  jz      loc_140016E6E
0x140016c96  mov     r15, [rbx+rsi*8+760h]
0x140016c9e  test    r15, r15
0x140016ca1  jz      loc_1400172F2
0x140016ca7  mov     edi, edx
0x140016ca9  mov     rax, rbp
0x140016cac  test    rbp, rbp
0x140016caf  jz      short loc_140016CBB
0x140016cb1  mov     rax, [rax]
0x140016cb4  inc     edi
0x140016cb6  test    rax, rax
0x140016cb9  jnz     short loc_140016CB1
0x140016cbb  test    r14b, r14b
0x140016cbe  jnz     loc_140016EE1
0x140016cc4  mov     rsi, [rbx+0D40h]
0x140016ccb  mov     r14, [rsi+8]
0x140016ccf  mov     r12, [r14+0CF0h]
0x140016cd6  cmp     byte ptr [r12+68h], 1
0x140016cdc  jz      loc_140016E24
0x140016ce2  movzx   edx, word ptr [rsi+10h]
0x140016ce6  mov     rcx, r14
0x140016ce9  call    VmsPtGetNicHeaderAtIndex
0x140016cee  mov     r13, rax
0x140016cf1  test    rax, rax
0x140016cf4  jz      short loc_140016D17
0x140016cf6  xor     ecx, ecx; ProcNumber
0x140016cf8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140016cff  nop     dword ptr [rax+rax+00h]
0x140016d04  mov     edx, eax
0x140016d06  mov     rax, [r13+18h]
0x140016d0a  shl     rdx, 6
0x140016d0e  movsxd  r8, edi
0x140016d11  lock add [rdx+rax+18h], r8
0x140016d17  mov     r13d, 1
0x140016d1d  cmp     [r12+68h], r13b
0x140016d22  jz      loc_140016DED
0x140016d28  or      esi, 0FFFFFFFFh
0x140016d2b  lea     rdi, VmsKnownProcessors
0x140016d32  xor     r12d, r12d
0x140016d35  lea     r14, aSetindexVmsCpu; "(*SetIndex < VMS_CPU_SET_ARRAY_COUNT)"
0x140016d3c  cmp     [rsp+78h+arg_0], r12b
0x140016d44  jz      loc_140017010
0x140016d4a  xor     ecx, ecx; ProcNumber
0x140016d4c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140016d53  nop     dword ptr [rax+rax+00h]
0x140016d58  mov     r14d, eax
0x140016d5b  cmp     eax, esi
0x140016d5d  jz      short loc_140016D8D
0x140016d5f  mov     r12d, r14d
0x140016d62  mov     r13d, r14d
0x140016d65  shr     r12d, 6
0x140016d69  and     r13d, 3Fh
0x140016d6d  cmp     r12d, 40h ; '@'
0x140016d71  jnb     loc_1400172FC
0x140016d77  mov     ecx, r13d
0x140016d7a  bt      [rdi+r12*8], rcx
0x140016d7f  setb    al
0x140016d82  xor     r12d, r12d
0x140016d85  test    al, al
0x140016d87  jnz     loc_140017218
0x140016d8d  xor     ecx, ecx; ProcNumber
0x140016d8f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140016d96  nop     dword ptr [rax+rax+00h]
0x140016d9b  xor     r9d, r9d; BugCheckParameter3
0x140016d9e  mov     [rsp+78h+BugCheckParameter4], r12; BugCheckParameter4
0x140016da3  mov     r8d, eax; BugCheckParameter2
0x140016da6  mov     rdx, r14; BugCheckParameter1
0x140016da9  mov     ecx, 121h; BugCheckCode
0x140016dae  call    cs:__imp_KeBugCheckEx
0x140016dbb  test    rdi, rdi
0x140016dbe  jz      loc_140016C8D
0x140016dc4  cmp     dword ptr [rdi+750h], 2
0x140016dcb  jnz     loc_140017274
0x140016dd1  mov     r14, [rdi+760h]
0x140016dd8  test    r14, r14
0x140016ddb  jz      loc_1400172B9
0x140016de1  mov     r14b, [r14+22D0h]
0x140016de8  jmp     loc_140016C8D
0x140016ded  movzx   edx, word ptr [rsi+10h]
0x140016df1  mov     rcx, r14
0x140016df4  call    VmsPtGetNicHeaderAtIndex
0x140016df9  mov     rsi, rax
0x140016dfc  test    rax, rax
0x140016dff  jz      short loc_140016E24
0x140016e01  xor     ecx, ecx; ProcNumber
0x140016e03  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140016e0a  nop     dword ptr [rax+rax+00h]
0x140016e0f  mov     ecx, eax
0x140016e11  neg     edi
0x140016e13  mov     rax, [rsi+18h]
0x140016e17  shl     rcx, 6
0x140016e1b  movsxd  rdx, edi
0x140016e1e  lock add [rcx+rax+18h], rdx
0x140016e24  mov     eax, 0E000200Fh
0x140016e29  mov     rcx, [rbx]
0x140016e2c  xor     r9d, r9d
0x140016e2f  mov     dword ptr [rsp+78h+var_50], eax
0x140016e33  mov     rdx, rbp
0x140016e36  mov     dword ptr [rsp+78h+BugCheckParameter4], 0C0010011h
0x140016e3e  lea     r8d, [r9+2]
0x140016e42  call    VmsPktReportDroppedPacketEx
0x140016e47  xor     r8d, r8d
0x140016e4a  mov     rdx, rbp
0x140016e4d  mov     rcx, rbx
0x140016e50  call    VmsPtNicFinalComplete
0x140016e55  mov     rbx, [rsp+78h+arg_8]
0x140016e5d  add     rsp, 40h
0x140016e61  pop     r15
0x140016e63  pop     r14
0x140016e65  pop     r13
0x140016e67  pop     r12
0x140016e69  pop     rdi
0x140016e6a  pop     rsi
0x140016e6b  pop     rbp
0x140016e6c  retn
0x140016e6e  mov     rax, [rbx]
0x140016e71  mov     esi, edx
0x140016e73  mov     [rsp+78h+var_48], dx
0x140016e78  test    r14b, r14b
0x140016e7b  jnz     loc_140016F92
0x140016e81  lea     r15, [rax+4D0h]
0x140016e88  jmp     loc_140016C9E
0x140016e8d  mov     r12b, r15b
0x140016e90  jmp     loc_140016C2C
0x140016e95  test    rbp, rbp
0x140016e98  jz      loc_140016C48
0x140016e9e  mov     rax, [rbp+120h]
0x140016ea5  test    rax, rax
0x140016ea8  jz      loc_140016C48
0x140016eae  mov     rax, [rax+10h]
0x140016eb2  test    rax, rax
0x140016eb5  jz      loc_140016C48
0x140016ebb  lea     rdx, aVmsptnicimmedi; "VmsPtNicImmediateSendNetBufferListsToNd"...
0x140016ec2  mov     dword ptr [rax+0B8h], 2D34h
0x140016ecc  mov     [rax+0B0h], rdx
0x140016ed3  xor     edx, edx
0x140016ed5  mov     [rax+0A8h], rcx
0x140016edc  jmp     loc_140016C48
0x140016ee1  movzx   eax, si
0x140016ee4  mov     r14, [rbx+rax*8+760h]
0x140016eec  test    r14, r14
0x140016eef  jz      loc_140016F88
0x140016ef5  mov     r14, [r14+278h]
0x140016efc  test    r14, r14
0x140016eff  jz      loc_140016F88
0x140016f05  cmp     dword ptr [r15+10h], 2
0x140016f0a  jnz     short loc_140016F88
0x140016f0c  mov     r8b, 1
0x140016f0f  mov     edx, edi
0x140016f11  mov     rcx, r14
0x140016f14  call    VmsPtPvtAcquireOutgoingRefCount
0x140016f19  test    al, al
0x140016f1b  jz      short loc_140016F88
0x140016f1d  or      esi, 0FFFFFFFFh
0x140016f20  lea     rdi, VmsKnownProcessors
0x140016f27  test    r12b, r12b
0x140016f2a  jz      loc_1400170B3
0x140016f30  xor     ecx, ecx; ProcNumber
0x140016f32  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140016f39  nop     dword ptr [rax+rax+00h]
0x140016f3e  mov     ebx, eax
0x140016f40  cmp     eax, esi
0x140016f42  jz      short loc_140016F56
0x140016f44  mov     edx, ebx
0x140016f46  mov     rcx, rdi
0x140016f49  call    VmsCpuSetContainsProcessor
0x140016f4e  test    al, al
0x140016f50  jnz     loc_14001725B
0x140016f56  xor     ecx, ecx; ProcNumber
0x140016f58  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140016f5f  nop     dword ptr [rax+rax+00h]
0x140016f64  xor     r9d, r9d; BugCheckParameter3
0x140016f67  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x140016f70  mov     r8d, eax; BugCheckParameter2
0x140016f73  mov     rdx, rbx; BugCheckParameter1
0x140016f76  mov     ecx, 121h; BugCheckCode
0x140016f7b  call    cs:__imp_KeBugCheckEx
0x140016f88  mov     eax, 0E0002012h
0x140016f8d  jmp     loc_140016E29
0x140016f92  mov     rcx, [rax+38h]; Lock
0x140016f96  mov     r15, rdx
0x140016f99  mov     dil, dl
0x140016f9c  xor     r8d, r8d; Flags
0x140016f9f  lea     rdx, [rsp+78h+LockState]; LockState
0x140016fa4  call    cs:__imp_NdisAcquireRWLockRead
0x140016fab  nop     dword ptr [rax+rax+00h]
0x140016fb0  mov     rcx, [rbx]
0x140016fb3  lea     rdx, [rsp+78h+var_48]
0x140016fb8  call    VmsPtPvtFindFirstAvailableNicIndex
0x140016fbd  movzx   esi, [rsp+78h+var_48]
0x140016fc2  test    eax, eax
0x140016fc4  jz      loc_1400172C5
0x140016fca  mov     rcx, [rbx]
0x140016fcd  lea     rdx, [rsp+78h+LockState]; LockState
0x140016fd2  mov     rcx, [rcx+38h]; Lock
0x140016fd6  call    cs:__imp_NdisReleaseRWLock
0x140016fdd  nop     dword ptr [rax+rax+00h]
0x140016fe2  xor     edx, edx
0x140016fe4  test    dil, dil
0x140016fe7  jnz     loc_140016C9E
0x140016fed  mov     eax, 0E0002010h
0x140016ff2  jmp     loc_140016E29
0x140016ff7  add     rcx, 480h
0x140016ffe  call    NetDispatchProfilerLeave
0x140017003  mov     r13d, 1
0x140017009  lea     r14, aSetindexVmsCpu; "(*SetIndex < VMS_CPU_SET_ARRAY_COUNT)"
0x140017010  mov     r9d, [rsp+78h+SendFlags]; SendFlags
0x140017018  mov     rdx, rbp; NetBufferLists
0x14001701b  mov     r8d, [r15+0Ch]; PortNumber
0x14001701f  mov     rcx, [rbx+70h]; NdisBindingHandle
0x140017023  call    cs:__imp_NdisSendNetBufferLists
0x14001702a  nop     dword ptr [rax+rax+00h]
0x14001702f  cmp     [rsp+78h+arg_0], r12b
0x140017037  jz      loc_140016E55
0x14001703d  xor     ecx, ecx; ProcNumber
0x14001703f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140017046  nop     dword ptr [rax+rax+00h]
0x14001704b  mov     ebx, eax
0x14001704d  cmp     eax, esi
0x14001704f  jz      short loc_140017076
0x140017051  mov     esi, ebx
0x140017053  mov     ebp, ebx
0x140017055  shr     esi, 6
0x140017058  and     ebp, 3Fh
0x14001705b  cmp     esi, 40h ; '@'
0x14001705e  jnb     loc_140017334
0x140017064  mov     ecx, ebp
0x140017066  bt      [rdi+rsi*8], rcx
0x14001706b  setb    al
0x14001706e  test    al, al
0x140017070  jnz     loc_14001712C
0x140017076  mov     rdi, rbx
0x140017079  xor     ecx, ecx; ProcNumber
0x14001707b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140017082  nop     dword ptr [rax+rax+00h]
0x140017087  xor     r9d, r9d; BugCheckParameter3
0x14001708a  mov     [rsp+78h+BugCheckParameter4], r12; BugCheckParameter4
0x14001708f  mov     r8d, eax; BugCheckParameter2
0x140017092  mov     rdx, rdi; BugCheckParameter1
0x140017095  mov     ecx, 121h; BugCheckCode
0x14001709a  call    cs:__imp_KeBugCheckEx
0x1400170a7  add     rcx, 480h
0x1400170ae  call    NetDispatchProfilerLeave
0x1400170b3  mov     rcx, [r14]; NdisBindingHandle
0x1400170b6  mov     r9d, r13d; SendFlags
0x1400170b9  xor     r8d, r8d; PortNumber
0x1400170bc  mov     rdx, rbp; NetBufferLists
0x1400170bf  call    cs:__imp_NdisSendNetBufferLists
0x1400170c6  nop     dword ptr [rax+rax+00h]
0x1400170cb  test    r12b, r12b
0x1400170ce  jz      loc_140016E55
0x1400170d4  xor     ecx, ecx; ProcNumber
  ... truncated ...
```
