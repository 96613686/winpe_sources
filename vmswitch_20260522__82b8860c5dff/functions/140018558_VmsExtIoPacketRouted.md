# VmsExtIoPacketRouted

- ea: `0x140018558`
- end: `0x140018edf`
- name: `VmsExtIoPacketRouted`
- size: `2439`
- prototype: ``
- caller_count: `11`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140017e30`
- `0x140018130`
- `0x140018190`
- `0x1400181f0`
- `0x140018330`
- `0x140018fb4`
- `0x14001a49c`
- `0x14001acc8`
- `0x14001e8f0`
- `0x140030590`
- `0x140087dc0`

## callees

- `0x140017e30`
- `0x140018558`
- `0x140018ef0`
- `0x140018fb4`
- `0x140027a64`
- `0x1400329f0`
- `0x1400749f4`
- `0x14008497c`
- `0x14008f0e4`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140018942`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001898d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140018a2f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140018aa3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140018942`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001898d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140018a2f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140018aa3`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x140018a64`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x140018a64`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400189c2`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400189c2`
- `NDIS!NdisFReturnNetBufferLists` at `0x140018ad5`
- `NDIS!NdisFReturnNetBufferLists` at `0x140018ad5`
- `NDIS!NdisReturnNetBufferLists` at `0x140018975`
- `NDIS!NdisReturnNetBufferLists` at `0x140018975`
- `NDIS!NdisReleaseRWLock` at `0x140018e58`
- `NDIS!NdisReleaseRWLock` at `0x140018e58`
- `NDIS!NdisAcquireRWLockWrite` at `0x140018e15`
- `NDIS!NdisAcquireRWLockWrite` at `0x140018e15`

## string_xrefs

- `0x1400188d4`: `VmsNblHelperAppendNblsMoveLast`

## pseudocode

```c
__int64 __fastcall VmsExtIoPacketRouted(__int64 *a1, char a2)
{
  int v3; // r15d
  int v4; // edx
  __int64 v5; // rsi
  const char *v6; // rdx
  __int64 **v7; // r8
  PNET_BUFFER_LIST *v8; // r12
  int v9; // r13d
  __int64 *v10; // r15
  __int64 v11; // rdi
  __int64 v12; // r14
  __int64 *v13; // rax
  struct _NET_BUFFER_LIST *v14; // rbx
  int v15; // r13d
  struct _NET_BUFFER_LIST *Alignment; // r14
  void *v17; // rdi
  unsigned int *v18; // rdi
  unsigned int v19; // eax
  void *v20; // rcx
  unsigned int v21; // eax
  void *v22; // rax
  int v23; // edi
  const char *v24; // r9
  struct _NET_BUFFER_LIST *v25; // rbx
  char v26; // r13
  struct _NET_BUFFER_LIST *v27; // rbx
  struct _NET_BUFFER_LIST *v28; // rbx
  struct _NET_BUFFER_LIST *v29; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // rax
  unsigned int v38; // eax
  void *v39; // rax
  PNET_BUFFER_LIST *v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  int v56; // [rsp+30h] [rbp-79h]
  __int64 v57; // [rsp+38h] [rbp-71h] BYREF
  __int64 **v58; // [rsp+48h] [rbp-61h] BYREF
  PNET_BUFFER_LIST v59; // [rsp+50h] [rbp-59h] BYREF
  struct _NET_BUFFER_LIST *v60; // [rsp+58h] [rbp-51h] BYREF
  PNET_BUFFER_LIST *p_NetBufferLists; // [rsp+60h] [rbp-49h]
  PNET_BUFFER_LIST *p_Next; // [rsp+68h] [rbp-41h]
  __int64 *v63; // [rsp+70h] [rbp-39h]
  PNET_BUFFER_LIST *p_NetBufferList; // [rsp+78h] [rbp-31h]
  PNET_BUFFER_LIST *v65; // [rsp+80h] [rbp-29h]
  __int64 *v66; // [rsp+88h] [rbp-21h]
  PNET_BUFFER_LIST NetBufferLists; // [rsp+90h] [rbp-19h] BYREF
  PNET_BUFFER_LIST v68; // [rsp+98h] [rbp-11h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-9h] BYREF
  PNET_BUFFER_LIST NetBufferList; // [rsp+A8h] [rbp-1h] BYREF
  PNET_BUFFER_LIST v71; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v72; // [rsp+B8h] [rbp+Fh] BYREF
  void *retaddr; // [rsp+108h] [rbp+5Fh]
  struct _LOCK_STATE_EX LockState; // [rsp+110h] [rbp+67h] BYREF
  char v75; // [rsp+118h] [rbp+6Fh]
  int v76; // [rsp+120h] [rbp+77h]
  int v77; // [rsp+128h] [rbp+7Fh]

  v75 = a2;
  *(_WORD *)&LockState.OldIrql = 0;
  v3 = 0;
  LockState.Flags = 0;
  v60 = 0;
  v76 = 0;
  v77 = 0;
  LODWORD(v57) = 0;
  if ( !(unsigned __int8)((__int64 (*)(void))VmsNblHelperVerifyRoutedRefCount)() )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v4,
      19,
      108,
      (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
      (__int64)"VmsNblHelperVerifyRoutedRefCount(NetBufferLists)");
    if ( !(unsigned __int8)VmsNblHelperVerifyRoutedRefCount(a1) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a1 )
    {
      v31 = a1[36];
      if ( v31 )
      {
        v32 = *(_QWORD *)(v31 + 16);
        if ( v32 )
        {
          *(_QWORD *)(v32 + 176) = "VmsExtIoPacketRouted";
          *(_DWORD *)(v32 + 184) = 4825;
          *(_QWORD *)(v32 + 168) = retaddr;
        }
      }
    }
  }
  v5 = 0;
  v59 = 0;
  NetBufferLists = 0;
  p_NetBufferLists = &NetBufferLists;
  p_Next = &v68;
  p_NetBufferList = &NetBufferList;
  v65 = &v71;
  v66 = &v72;
  v6 = (const char *)&v69;
  v63 = &v69;
  v7 = (__int64 **)&v60;
  v68 = 0;
  v8 = &v59;
  NetBufferList = 0;
  v71 = 0;
  v72 = 0;
  v69 = 0;
  v58 = (__int64 **)&v60;
  if ( a1 )
  {
    v9 = 0;
    do
    {
      ++v9;
      v10 = (__int64 *)*a1;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( v10 )
        {
          v33 = v10[36];
          if ( v33 )
          {
            v34 = *(_QWORD *)(v33 + 16);
            if ( v34 )
            {
              *(_QWORD *)(v34 + 176) = "VmsExtIoPacketRouted";
              *(_DWORD *)(v34 + 184) = 4864;
              *(_QWORD *)(v34 + 168) = retaddr;
            }
          }
        }
      }
      *a1 = 0;
      v6 = (const char *)a1[36];
      v57 = 0;
      if ( v6 && (v11 = *((_QWORD *)v6 + 2)) != 0 && (v12 = *(_QWORD *)(v11 + 32)) != 0 )
      {
        NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(v12 + 480) + 56LL), &LockState, 0);
        VmsScQosCompleteNbls(v12, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 480) + 1240LL) + 8680LL), a1, &v57);
        *(_QWORD *)(v11 + 32) = 0;
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(v12 + 480) + 56LL), &LockState);
        VmsNblHelperAppendNblsMoveLast(&v58, v57);
        v7 = v58;
      }
      else
      {
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v6 )
          {
            v35 = *((_QWORD *)v6 + 2);
            if ( v35 )
            {
              *(_DWORD *)(v35 + 184) = 2646;
              *(_QWORD *)(v35 + 176) = "VmsNblHelperAppendNblsMoveLast";
              *(_QWORD *)(v35 + 168) = retaddr;
            }
          }
        }
        *v7 = a1;
        do
        {
          v13 = (__int64 *)*a1;
          v7 = (__int64 **)a1;
          v58 = (__int64 **)a1;
          a1 = v13;
        }
        while ( v13 );
      }
      a1 = v10;
    }
    while ( v10 );
    LODWORD(v57) = v9;
    v8 = &v59;
    v3 = 0;
  }
  v14 = v60;
  if ( v60 )
  {
    v15 = 0;
    while ( 1 )
    {
      Alignment = (struct _NET_BUFFER_LIST *)v14->Link.Alignment;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( Alignment )
        {
          v36 = Alignment->NetBufferListInfo[18];
          if ( v36 )
          {
            v37 = v36[2];
            if ( v37 )
            {
              *(_QWORD *)(v37 + 176) = "VmsExtIoPacketRouted";
              *(_DWORD *)(v37 + 184) = 4910;
              *(_QWORD *)(v37 + 168) = retaddr;
            }
          }
        }
      }
      v14->Link.Alignment = 0;
      v17 = v14->NetBufferListInfo[18];
      if ( !v17 )
        break;
      v18 = (unsigned int *)*((_QWORD *)v17 + 2);
      if ( !v18 )
        break;
      if ( !v5 )
      {
        if ( !*((_QWORD *)v18 + 3) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            (_DWORD)v6,
            19,
            109,
            (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
            (__int64)"curNblContext->SourceNic != NULL");
          if ( !*((_QWORD *)v18 + 3) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        v5 = *(_QWORD *)(*((_QWORD *)v18 + 3) + 1888LL);
      }
      v19 = *v18;
      if ( (*v18 & 0x10) != 0 )
      {
        v21 = v19 & 0xFFFFFFEF;
        *v18 = v21;
        if ( (v21 & 0x400) != 0 )
          v22 = (void *)*((_QWORD *)v18 + 1);
        else
          v22 = *(void **)(v5 + 4296);
        v14->SourceHandle = v22;
        *p_NetBufferLists = v14;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v14->Link.Alignment )
          {
            v41 = *(_QWORD *)(v14->Link.Alignment + 288);
            if ( v41 )
            {
              v42 = *(_QWORD *)(v41 + 16);
              if ( v42 )
              {
                v6 = "VmsExtIoPacketRouted";
                *(_DWORD *)(v42 + 184) = 4949;
                *(_QWORD *)(v42 + 176) = "VmsExtIoPacketRouted";
                *(_QWORD *)(v42 + 168) = retaddr;
              }
            }
          }
        }
        p_NetBufferLists = &v14->Next;
        ++v3;
        goto LABEL_34;
      }
      if ( (v19 & 0x20) != 0 )
      {
        *v18 = v19 & 0xFFFFFFDF;
        *p_Next = v14;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v14->Link.Alignment )
          {
            v49 = *(_QWORD *)(v14->Link.Alignment + 288);
            if ( v49 )
            {
              v50 = *(_QWORD *)(v49 + 16);
              if ( v50 )
              {
                v6 = "VmsExtIoPacketRouted";
                *(_DWORD *)(v50 + 184) = 4962;
                *(_QWORD *)(v50 + 176) = "VmsExtIoPacketRouted";
                *(_QWORD *)(v50 + 168) = retaddr;
              }
            }
          }
        }
        v23 = v76 + 1;
        p_Next = &v14->Next;
        ++v76;
        goto LABEL_35;
      }
      if ( (v19 & 0x10000) != 0 )
      {
        *v18 = v19 & 0xFFFEFFFF;
        *v63 = (__int64)v14;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v14->Link.Alignment )
          {
            v52 = *(_QWORD *)(v14->Link.Alignment + 288);
            if ( v52 )
            {
              v53 = *(_QWORD *)(v52 + 16);
              if ( v53 )
              {
                v6 = "VmsExtIoPacketRouted";
                *(_DWORD *)(v53 + 184) = 4974;
                *(_QWORD *)(v53 + 176) = "VmsExtIoPacketRouted";
                *(_QWORD *)(v53 + 168) = retaddr;
              }
            }
          }
        }
        v63 = (__int64 *)v14;
        goto LABEL_34;
      }
      if ( (v19 & 0x80u) != 0 )
      {
        v38 = v19 & 0xFFFFFF7F;
        *v18 = v38;
        if ( (v38 & 0x800) != 0 )
          v39 = (void *)*((_QWORD *)v18 + 1);
        else
          v39 = *(void **)(v5 + 4288);
        v14->SourceHandle = v39;
        WORD1(v14->NetBufferListInfo[14]) = *((_WORD *)v18 + 8);
        v40 = p_NetBufferList;
        v14->Status = 0;
        *v40 = v14;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v14->Link.Alignment )
          {
            v43 = *(_QWORD *)(v14->Link.Alignment + 288);
            if ( v43 )
            {
              v44 = *(_QWORD *)(v43 + 16);
              if ( v44 )
              {
                v6 = "VmsExtIoPacketRouted";
                *(_DWORD *)(v44 + 184) = 5005;
                *(_QWORD *)(v44 + 176) = "VmsExtIoPacketRouted";
                *(_QWORD *)(v44 + 168) = retaddr;
              }
            }
          }
        }
        ++v77;
        p_NetBufferList = &v14->Next;
        goto LABEL_34;
      }
      v20 = retaddr;
      if ( (v19 & 0x100) != 0 )
      {
        *v18 = v19 & 0xFFFFFEFF;
        *v65 = v14;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v14->Link.Alignment )
          {
            v47 = *(_QWORD *)(v14->Link.Alignment + 288);
            if ( v47 )
            {
              v48 = *(_QWORD *)(v47 + 16);
              if ( v48 )
              {
                v6 = "VmsExtIoPacketRouted";
                *(_DWORD *)(v48 + 184) = 5018;
                *(_QWORD *)(v48 + 176) = "VmsExtIoPacketRouted";
                *(_QWORD *)(v48 + 168) = retaddr;
              }
            }
          }
        }
        v65 = &v14->Next;
        ++v15;
        goto LABEL_34;
      }
      if ( (v19 & 0x20000) != 0 )
      {
        *v18 = v19 & 0xFFFDFFFF;
        *v66 = (__int64)v14;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v14->Link.Alignment )
          {
            v54 = *(_QWORD *)(v14->Link.Alignment + 288);
            if ( v54 )
            {
              v55 = *(_QWORD *)(v54 + 16);
              if ( v55 )
              {
                v6 = "VmsExtIoPacketRouted";
                *(_DWORD *)(v55 + 184) = 5030;
                *(_QWORD *)(v55 + 176) = "VmsExtIoPacketRouted";
                *(_QWORD *)(v55 + 168) = retaddr;
              }
            }
          }
        }
        v66 = (__int64 *)v14;
        goto LABEL_34;
      }
      v14->SourceHandle = (void *)*((_QWORD *)v18 + 1);
      *v8 = v14;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( v14->Link.Alignment )
        {
          v45 = *(_QWORD *)(v14->Link.Alignment + 288);
          if ( v45 )
          {
            v46 = *(_QWORD *)(v45 + 16);
            if ( v46 )
            {
              v6 = "VmsExtIoPacketRouted";
              *(_DWORD *)(v46 + 184) = 5042;
              *(_QWORD *)(v46 + 176) = "VmsExtIoPacketRouted";
LABEL_94:
              *(_QWORD *)(v46 + 168) = v20;
            }
          }
        }
      }
LABEL_29:
      v8 = &v14->Next;
LABEL_34:
      v23 = v76;
LABEL_35:
      v24 = "VmsExtIoPacketRouted";
      v14 = Alignment;
      if ( !Alignment )
      {
        v25 = NetBufferLists;
        v56 = v15;
        v26 = v75;
        if ( NetBufferLists )
        {
          if ( v75 )
            _InterlockedAdd64(
              (volatile signed __int64 *)(*(_QWORD *)(v5 + 6472)
                                        + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                        + 56),
              -v3);
          NdisReturnNetBufferLists(*(NDIS_HANDLE *)(v5 + 4288), v25, 4u);
        }
        v27 = v68;
        if ( v68 )
        {
          if ( v26 )
            _InterlockedAdd64(
              (volatile signed __int64 *)(*(_QWORD *)(v5 + 6472)
                                        + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                        + 40),
              -v23);
          NdisFReturnNetBufferLists(*(NDIS_HANDLE *)(v5 + 4304), v27, 4u);
        }
        if ( v69 )
          VmsTmSendCompleteInternalNbls(*(_QWORD *)(v5 + 9000), v69, 0, v24);
        v28 = NetBufferList;
        if ( NetBufferList )
        {
          if ( v26 )
            _InterlockedAdd64(
              (volatile signed __int64 *)(*(_QWORD *)(v5 + 6472)
                                        + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                        + 24),
              -v77);
          NdisMSendNetBufferListsComplete(*(NDIS_HANDLE *)(v5 + 4296), v28, 4u);
        }
        v29 = v71;
        if ( v71 )
        {
          if ( v26 )
            _InterlockedAdd64(
              (volatile signed __int64 *)(*(_QWORD *)(v5 + 6472)
                                        + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                        + 8),
              -v56);
          NdisFSendNetBufferListsComplete(*(NDIS_HANDLE *)(v5 + 4304), v29, 4u);
        }
        if ( v72 )
          VmsExtPtSendNetBufferListsCompleteFinal(v5, v72, 4, v24);
        if ( v59 )
          VmsNblHelperCompleteNbls(v59);
        return (unsigned int)v57;
      }
    }
    v20 = retaddr;
    *v8 = v14;
    if ( (VmsDiagnosticFlags & 1) == 0 )
      goto LABEL_29;
    if ( !v14->Link.Alignment )
      goto LABEL_29;
    v51 = *(_QWORD *)(v14->Link.Alignment + 288);
    if ( !v51 )
      goto LABEL_29;
    v46 = *(_QWORD *)(v51 + 16);
    if ( !v46 )
      goto LABEL_29;
    *(_QWORD *)(v46 + 176) = "VmsExtIoPacketRouted";
    *(_DWORD *)(v46 + 184) = 5051;
    goto LABEL_94;
  }
  return (unsigned int)v57;
}

```

## disassembly

```asm
0x140018558  mov     [rsp-8+arg_8], dl
0x14001855c  push    rbp
0x14001855d  push    rbx
0x14001855e  push    rsi
0x14001855f  push    rdi
0x140018560  push    r12
0x140018562  push    r13
0x140018564  push    r14
0x140018566  push    r15
0x140018568  lea     rbp, [rsp-1Fh]
0x14001856d  sub     rsp, 0C8h
0x140018574  xor     eax, eax
0x140018576  mov     rbx, rcx
0x140018579  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14001857d  xor     r15d, r15d
0x140018580  mov     [rbp+57h+LockState.Flags], al
0x140018583  mov     [rbp+57h+var_A8], rax
0x140018587  mov     [rbp+57h+arg_10], eax
0x14001858a  mov     [rbp+57h+arg_18], eax
0x14001858d  mov     dword ptr [rbp+57h+var_C8], eax
0x140018590  call    VmsNblHelperVerifyRoutedRefCount
0x140018595  lea     rcx, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x14001859c  test    al, al
0x14001859e  jz      loc_140018E7A
0x1400185a4  mov     eax, cs:VmsDiagnosticFlags
0x1400185aa  lea     r9, aVmsextiopacket; "VmsExtIoPacketRouted"
0x1400185b1  mov     rcx, [rbp+5Fh]
0x1400185b5  test    al, 1
0x1400185b7  jnz     loc_140018838
0x1400185bd  xor     esi, esi
0x1400185bf  mov     [rbp+57h+var_B0], r15
0x1400185c3  mov     [rbp+57h+NetBufferLists], r15
0x1400185c7  lea     rdx, [rbp+57h+NetBufferLists]
0x1400185cb  mov     [rbp+57h+var_A0], rdx
0x1400185cf  lea     rdx, [rbp+57h+var_68]
0x1400185d3  mov     [rbp+57h+var_98], rdx
0x1400185d7  lea     rdx, [rbp+57h+NetBufferList]
0x1400185db  mov     [rbp+57h+var_88], rdx
0x1400185df  lea     rdx, [rbp+57h+var_50]
0x1400185e3  mov     [rbp+57h+var_80], rdx
0x1400185e7  lea     rdx, [rbp+57h+var_48]
0x1400185eb  mov     [rbp+57h+var_78], rdx
0x1400185ef  lea     rdx, [rbp+57h+var_60]
0x1400185f3  mov     [rbp+57h+var_90], rdx
0x1400185f7  lea     r8, [rbp+57h+var_A8]
0x1400185fb  mov     [rbp+57h+var_68], r15
0x1400185ff  lea     r12, [rbp+57h+var_B0]
0x140018603  mov     [rbp+57h+NetBufferList], r15
0x140018607  mov     [rbp+57h+var_50], r15
0x14001860b  mov     [rbp+57h+var_48], rsi
0x14001860f  mov     [rbp+57h+var_60], rsi
0x140018613  mov     [rbp+57h+var_B8], r8
0x140018617  test    rbx, rbx
0x14001861a  jz      loc_1400186AC
0x140018620  mov     r13d, esi
0x140018623  lea     r12, aVmsextiopacket; "VmsExtIoPacketRouted"
0x14001862a  mov     eax, cs:VmsDiagnosticFlags
0x140018630  inc     r13d
0x140018633  mov     r15, [rbx]
0x140018636  mov     rcx, [rbp+5Fh]
0x14001863a  test    al, 1
0x14001863c  jnz     loc_14001887B
0x140018642  mov     [rbx], rsi
0x140018645  mov     rdx, [rbx+120h]
0x14001864c  mov     [rbp+57h+var_C8], rsi
0x140018650  test    rdx, rdx
0x140018653  jz      short loc_14001866B
0x140018655  mov     rdi, [rdx+10h]
0x140018659  test    rdi, rdi
0x14001865c  jz      short loc_14001866B
0x14001865e  mov     r14, [rdi+20h]
0x140018662  test    r14, r14
0x140018665  jnz     loc_140018E03
0x14001866b  mov     eax, cs:VmsDiagnosticFlags
0x140018671  mov     r9, [rbp+5Fh]
0x140018675  test    al, 1
0x140018677  jnz     loc_1400188BE
0x14001867d  mov     [r8], rbx
0x140018680  mov     rax, [rbx]
0x140018683  mov     r8, rbx
0x140018686  mov     [rbp+57h+var_B8], rbx
0x14001868a  mov     rbx, rax
0x14001868d  test    rax, rax
0x140018690  jnz     short loc_140018680
0x140018692  mov     rbx, r15
0x140018695  test    r15, r15
0x140018698  jnz     short loc_14001862A
0x14001869a  mov     dword ptr [rbp+57h+var_C8], r13d
0x14001869e  lea     r12, [rbp+57h+var_B0]
0x1400186a2  mov     r15d, esi
0x1400186a5  lea     r9, aVmsextiopacket; "VmsExtIoPacketRouted"
0x1400186ac  mov     rbx, [rbp+57h+var_A8]
0x1400186b0  test    rbx, rbx
0x1400186b3  jz      loc_140018820
0x1400186b9  mov     r13d, esi
0x1400186bc  mov     eax, cs:VmsDiagnosticFlags
0x1400186c2  mov     r14, [rbx]
0x1400186c5  mov     rcx, [rbp+5Fh]
0x1400186c9  test    al, 1
0x1400186cb  jnz     loc_1400188F8
0x1400186d1  mov     qword ptr [rbx], 0
0x1400186d8  mov     rdi, [rbx+120h]
0x1400186df  test    rdi, rdi
0x1400186e2  jz      loc_140018CE2
0x1400186e8  mov     rdi, [rdi+10h]
0x1400186ec  test    rdi, rdi
0x1400186ef  jz      loc_140018CE2
0x1400186f5  test    rsi, rsi
0x1400186f8  jnz     short loc_14001870F
0x1400186fa  cmp     [rdi+18h], rsi
0x1400186fe  jz      loc_140018C9F
0x140018704  mov     rax, [rdi+18h]
0x140018708  mov     rsi, [rax+760h]
0x14001870f  mov     eax, [rdi]
0x140018711  test    al, 10h
0x140018713  jnz     short loc_140018766
0x140018715  test    al, 20h
0x140018717  jnz     loc_140018AE6
0x14001871d  bt      eax, 10h
0x140018721  jb      loc_140018D37
0x140018727  test    al, al
0x140018729  js      loc_1400189D3
0x14001872f  mov     rcx, [rbp+5Fh]
0x140018733  bt      eax, 8
0x140018737  jb      loc_140018A75
0x14001873d  bt      eax, 11h
0x140018741  jb      loc_140018D5B
0x140018747  mov     rax, [rdi+8]
0x14001874b  mov     [rbx+78h], rax
0x14001874f  mov     [r12], rbx
0x140018753  mov     eax, cs:VmsDiagnosticFlags
0x140018759  test    al, 1
0x14001875b  jnz     loc_140018BAF
0x140018761  mov     r12, rbx
0x140018764  jmp     short loc_1400187A0
0x140018766  and     eax, 0FFFFFFEFh
0x140018769  mov     [rdi], eax
0x14001876b  bt      eax, 0Ah
0x14001876f  jb      loc_140018C96
0x140018775  mov     rax, [rsi+10C8h]
0x14001877c  mov     rcx, [rbp+5Fh]
0x140018780  mov     [rbx+78h], rax
0x140018784  mov     rax, [rbp+57h+var_A0]
0x140018788  mov     [rax], rbx
0x14001878b  mov     eax, cs:VmsDiagnosticFlags
0x140018791  test    al, 1
0x140018793  jnz     loc_140018B15
0x140018799  mov     [rbp+57h+var_A0], rbx
0x14001879d  inc     r15d
0x1400187a0  mov     edi, [rbp+57h+arg_10]
0x1400187a3  lea     r9, aVmsextiopacket; "VmsExtIoPacketRouted"
0x1400187aa  mov     rbx, r14
0x1400187ad  test    r14, r14
0x1400187b0  jnz     loc_1400186BC
0x1400187b6  mov     rbx, [rbp+57h+NetBufferLists]
0x1400187ba  mov     r14d, 4
0x1400187c0  mov     [rbp+57h+var_D0], r13d
0x1400187c4  mov     r13b, [rbp+57h+arg_8]
0x1400187c8  test    rbx, rbx
0x1400187cb  jnz     loc_14001893B
0x1400187d1  mov     rbx, [rbp+57h+var_68]
0x1400187d5  test    rbx, rbx
0x1400187d8  jnz     loc_140018A9C
0x1400187de  mov     rdx, [rbp+57h+var_60]
0x1400187e2  test    rdx, rdx
0x1400187e5  jnz     loc_140018EBB
0x1400187eb  mov     rbx, [rbp+57h+NetBufferList]
0x1400187ef  test    rbx, rbx
0x1400187f2  jnz     loc_140018986
0x1400187f8  mov     rbx, [rbp+57h+var_50]
0x1400187fc  test    rbx, rbx
0x1400187ff  jnz     loc_140018A28
0x140018805  mov     rdx, [rbp+57h+var_48]
0x140018809  test    rdx, rdx
0x14001880c  jnz     loc_140018ECF
0x140018812  mov     rcx, [rbp+57h+var_B0]; NetBufferList
0x140018816  test    rcx, rcx
0x140018819  jz      short loc_140018820
0x14001881b  call    VmsNblHelperCompleteNbls
0x140018820  mov     eax, dword ptr [rbp+57h+var_C8]
0x140018823  add     rsp, 0C8h
0x14001882a  pop     r15
0x14001882c  pop     r14
0x14001882e  pop     r13
0x140018830  pop     r12
0x140018832  pop     rdi
0x140018833  pop     rsi
0x140018834  pop     rbx
0x140018835  pop     rbp
0x140018836  retn
0x140018838  test    rbx, rbx
0x14001883b  jz      loc_1400185BD
0x140018841  mov     rax, [rbx+120h]
0x140018848  test    rax, rax
0x14001884b  jz      loc_1400185BD
0x140018851  mov     rax, [rax+10h]
0x140018855  test    rax, rax
0x140018858  jz      loc_1400185BD
0x14001885e  mov     [rax+0B0h], r9
0x140018865  mov     dword ptr [rax+0B8h], 12D9h
0x14001886f  mov     [rax+0A8h], rcx
0x140018876  jmp     loc_1400185BD
0x14001887b  test    r15, r15
0x14001887e  jz      loc_140018642
0x140018884  mov     rax, [r15+120h]
0x14001888b  test    rax, rax
0x14001888e  jz      loc_140018642
0x140018894  mov     rax, [rax+10h]
0x140018898  test    rax, rax
0x14001889b  jz      loc_140018642
0x1400188a1  mov     [rax+0B0h], r12
0x1400188a8  mov     dword ptr [rax+0B8h], 1300h
0x1400188b2  mov     [rax+0A8h], rcx
0x1400188b9  jmp     loc_140018642
0x1400188be  test    rdx, rdx
0x1400188c1  jz      loc_14001867D
0x1400188c7  mov     rax, [rdx+10h]
0x1400188cb  test    rax, rax
0x1400188ce  jz      loc_14001867D
0x1400188d4  lea     rcx, aVmsnblhelperap; "VmsNblHelperAppendNblsMoveLast"
0x1400188db  mov     dword ptr [rax+0B8h], 0A56h
0x1400188e5  mov     [rax+0B0h], rcx
0x1400188ec  mov     [rax+0A8h], r9
0x1400188f3  jmp     loc_14001867D
0x1400188f8  test    r14, r14
0x1400188fb  jz      loc_1400186D1
0x140018901  mov     rax, [r14+120h]
0x140018908  test    rax, rax
0x14001890b  jz      loc_1400186D1
0x140018911  mov     rax, [rax+10h]
0x140018915  test    rax, rax
0x140018918  jz      loc_1400186D1
0x14001891e  mov     [rax+0B0h], r9
0x140018925  mov     dword ptr [rax+0B8h], 132Eh
0x14001892f  mov     [rax+0A8h], rcx
0x140018936  jmp     loc_1400186D1
0x14001893b  test    r13b, r13b
0x14001893e  jz      short loc_140018968
0x140018940  xor     ecx, ecx; ProcNumber
0x140018942  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140018949  nop     dword ptr [rax+rax+00h]
0x14001894e  mov     r8d, eax
0x140018951  mov     rax, [rsi+1948h]
0x140018958  shl     r8, 6
0x14001895c  neg     r15d
0x14001895f  movsxd  rcx, r15d
0x140018962  lock add [rax+r8+38h], rcx
0x140018968  mov     rcx, [rsi+10C0h]; NdisBindingHandle
0x14001896f  mov     r8d, r14d; ReturnFlags
0x140018972  mov     rdx, rbx; NetBufferLists
0x140018975  call    cs:__imp_NdisReturnNetBufferLists
0x14001897c  nop     dword ptr [rax+rax+00h]
0x140018981  jmp     loc_1400187D1
0x140018986  test    r13b, r13b
0x140018989  jz      short loc_1400189B5
0x14001898b  xor     ecx, ecx; ProcNumber
0x14001898d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140018994  nop     dword ptr [rax+rax+00h]
0x140018999  mov     r8d, eax
0x14001899c  mov     eax, [rbp+57h+arg_18]
0x14001899f  shl     r8, 6
0x1400189a3  neg     eax
0x1400189a5  movsxd  rcx, eax
0x1400189a8  mov     rax, [rsi+1948h]
0x1400189af  lock add [rax+r8+18h], rcx
0x1400189b5  mov     rcx, [rsi+10C8h]; MiniportAdapterHandle
0x1400189bc  mov     r8d, r14d; SendCompleteFlags
0x1400189bf  mov     rdx, rbx; NetBufferList
0x1400189c2  call    cs:__imp_NdisMSendNetBufferListsComplete
0x1400189c9  nop     dword ptr [rax+rax+00h]
0x1400189ce  jmp     loc_1400187F8
0x1400189d3  btr     eax, 7
0x1400189d7  mov     [rdi], eax
0x1400189d9  bt      eax, 0Bh
0x1400189dd  jb      loc_140018D7B
0x1400189e3  mov     rax, [rsi+10C0h]
0x1400189ea  mov     rcx, [rbp+5Fh]
0x1400189ee  mov     [rbx+78h], rax
0x1400189f2  movzx   eax, word ptr [rdi+10h]
0x1400189f6  mov     [rbx+102h], ax
0x1400189fd  mov     rax, [rbp+57h+var_88]
0x140018a01  mov     dword ptr [rbx+8Ch], 0
0x140018a0b  mov     [rax], rbx
0x140018a0e  mov     eax, cs:VmsDiagnosticFlags
0x140018a14  test    al, 1
0x140018a16  jnz     loc_140018B62
0x140018a1c  inc     [rbp+57h+arg_18]
0x140018a1f  mov     [rbp+57h+var_88], rbx
0x140018a23  jmp     loc_1400187A0
0x140018a28  test    r13b, r13b
0x140018a2b  jz      short loc_140018A57
0x140018a2d  xor     ecx, ecx; ProcNumber
0x140018a2f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140018a36  nop     dword ptr [rax+rax+00h]
0x140018a3b  mov     r9d, eax
0x140018a3e  mov     eax, [rbp+57h+var_D0]
0x140018a41  shl     r9, 6
0x140018a45  neg     eax
0x140018a47  movsxd  rcx, eax
0x140018a4a  mov     rax, [rsi+1948h]
  ... truncated ...
```
