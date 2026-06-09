# Smb2ReconnectDurableFile

- ea: `0x14001b628`
- end: `0x14001bd46`
- name: `Smb2ReconnectDurableFile`
- size: `1822`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140079760`

## callees

- `0x140012790`
- `0x140013920`
- `0x140015830`
- `0x140016df0`
- `0x14001b628`
- `0x14001beac`
- `0x14001ff28`
- `0x1400222ec`
- `0x140022690`
- `0x14002d5b0`
- `0x14002dca4`
- `0x14002dd28`
- `0x14002f01c`
- `0x140068838`
- `0x14007ca90`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001b9ef`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001b9ef`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001ba07`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001bb40`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001ba07`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001bb40`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b8ea`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b8ea`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b952`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001ba18`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bb51`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bc71`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b952`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001ba18`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bb51`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bc71`
- `srvnet!SrvAdminUpdateFileSessionID` at `0x14001bba9`
- `srvnet!SrvAdminUpdateFileSessionID` at `0x14001bba9`

## pseudocode

```c
__int64 __fastcall Smb2ReconnectDurableFile(_QWORD *a1, __int64 a2, _BYTE *a3, _BYTE *a4, _BYTE *a5)
{
  __int64 v5; // rsi
  __int64 v7; // rcx
  __int64 v10; // r13
  __int64 FileGlobal; // rax
  __int64 v12; // rdi
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  char v15; // cl
  __int64 v16; // rax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 WorkItemSecurityContext; // rax
  __int64 v20; // r8
  __int64 v22; // rcx
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r15
  volatile LONG *v26; // rbx
  __int64 v27; // r14
  __int64 v28; // rdx
  __int64 v29; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-58h] BYREF

  v5 = a1[70];
  v7 = a1[8];
  v10 = *(_QWORD *)(v5 + 32);
  memset(&LockHandle, 0, sizeof(LockHandle));
  FileGlobal = Smb2FindFileGlobal(*(_QWORD *)(v7 + 160), *(_QWORD *)(v5 + 361));
  v12 = FileGlobal;
  if ( !FileGlobal )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225524LL;
    }
    v14 = 13;
    goto LABEL_96;
  }
  v15 = *(_BYTE *)(FileGlobal + 237);
  if ( v15 && *(_QWORD *)(FileGlobal + 408) )
    goto LABEL_11;
  if ( !*(_BYTE *)(FileGlobal + 241) || !*(_QWORD *)(FileGlobal + 408) )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_102;
    }
    v24 = 14;
LABEL_101:
    WPP_SF_qq(v23->AttachedDevice, v24, &WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids, a1, *(_QWORD *)(v5 + 361));
    goto LABEL_102;
  }
  if ( v15 )
  {
LABEL_11:
    v16 = *(_QWORD *)(FileGlobal + 168);
    if ( v16 )
    {
      if ( (*(_DWORD *)(v16 + 120) & 2) != 0 )
        goto LABEL_13;
LABEL_20:
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_102;
      }
      v18 = 15;
LABEL_18:
      WPP_SF_q(v17->AttachedDevice, v18, &WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids, a1);
LABEL_102:
      Smb2DereferenceFile((PVOID)v12);
      return 3221225524LL;
    }
    if ( *(_BYTE *)(v12 + 284) != 9 )
      goto LABEL_20;
  }
LABEL_13:
  if ( *(_QWORD *)(v12 + 168) != *(_QWORD *)(v5 + 104) )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_102;
    }
    v18 = 16;
    goto LABEL_18;
  }
  if ( a4 )
    *a4 = v15;
  if ( a3 )
    *a3 = *(_BYTE *)(v12 + 241);
  if ( a5 )
    *a5 = *(_BYTE *)(v12 + 242);
  WorkItemSecurityContext = Smb2GetWorkItemSecurityContext(v5);
  if ( !Smb2VerifySecurityContext(*(_QWORD *)(v20 + 8), WorkItemSecurityContext) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        &WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids,
        a1,
        *(_QWORD *)(v5 + 361));
    }
    Smb2DereferenceFile((PVOID)v12);
    return 3221225506LL;
  }
  if ( *(_BYTE *)(v5 + 378) )
  {
    v22 = *(_QWORD *)(v5 + 336) - *(_QWORD *)(v12 + 672);
    if ( !v22 )
      v22 = *(_QWORD *)(v5 + 344) - *(_QWORD *)(v12 + 680);
    if ( v22 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_102;
      }
      v24 = 18;
      goto LABEL_101;
    }
  }
  v25 = *(_QWORD *)(*(_QWORD *)(v5 + 56) + 96LL);
  if ( ((_InterlockedExchangeAdd64(*(volatile signed __int64 **)(*(_QWORD *)(v5 + 32) + 24LL), 1u) + 2)
      & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    __int2c();
  if ( ((_InterlockedExchangeAdd64(*(volatile signed __int64 **)(v5 + 56), 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    __int2c();
  v26 = *(volatile LONG **)(v10 + 104);
  v27 = *(_QWORD *)(*(_QWORD *)(v5 + 32) + 24LL);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v12 + 112), &LockHandle);
  if ( *(_DWORD *)(v12 + 12) != 220
    || !*(_BYTE *)(v12 + 237) && !*(_BYTE *)(v12 + 241)
    || *(_DWORD *)(v12 + 88) != -1
    || *(_QWORD *)(v12 + 144)
    || *(_QWORD *)(v12 + 128) != v25 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    Smb2DereferenceFile((PVOID)v12);
    Smb2DereferenceSession(*(_QWORD *)(v5 + 32));
    Smb2DereferenceTreeConnect(*(PVOID *)(v5 + 56));
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225524LL;
    }
    v14 = 19;
LABEL_96:
    WPP_SF_qq(v13->AttachedDevice, v14, &WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids, a1, *(_QWORD *)(v5 + 361));
    return 3221225524LL;
  }
  if ( !(unsigned __int8)RfsTableInsert(v26) )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    Smb2DereferenceFile((PVOID)v12);
    Smb2DereferenceSession(*(_QWORD *)(v5 + 32));
    Smb2DereferenceTreeConnect(*(PVOID *)(v5 + 56));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        &WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids,
        a1,
        *(_QWORD *)(v5 + 361));
    }
    return 3221225626LL;
  }
  *(_QWORD *)(v12 + 144) = *(_QWORD *)(v5 + 32);
  *(_QWORD *)(v12 + 152) = v27;
  *(_QWORD *)(v12 + 160) = *(_QWORD *)(v5 + 56);
  KeAcquireSpinLockAtDpcLevel(&qword_14004B3E0);
  if ( *(_BYTE *)(v12 + 240) )
  {
    KeReleaseSpinLockFromDpcLevel(&qword_14004B3E0);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v5 + 32) + 112LL));
    Smb2DereferenceFile((PVOID)v12);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225524LL;
    }
    v14 = 21;
    goto LABEL_96;
  }
  if ( !*(_BYTE *)(v12 + 237) || *(_QWORD *)(v12 + 392) == v12 + 392 )
  {
    if ( *(_BYTE *)(v12 + 241) && *(_QWORD *)(v12 + 392) != v12 + 392 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids, a1, v12);
      }
      LOBYTE(v28) = 1;
      Smb2RemoveFileFromResilientHandleList(v12 + 392, v28);
      ++*(_DWORD *)(Srv2Statistics + 176);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 22, &WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids, a1, v12);
    }
    LOBYTE(v28) = 1;
    Smb2RemoveFileFromDurableHandleList(v12 + 392, v28);
    ++*(_DWORD *)(Srv2Statistics + 136);
  }
  KeReleaseSpinLockFromDpcLevel(&qword_14004B3E0);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( *(_BYTE *)(v12 + 242) )
  {
    v29 = *(_QWORD *)(v5 + 104);
    if ( v29 )
    {
      if ( *(_DWORD *)(v29 + 12) == 226 )
        Smb2LeaseResumePendingBreak(v29, v5 + 426, v5 + 428, v5 + 424);
    }
  }
  SrvAdminUpdateFileSessionID(
    *(_QWORD *)(v12 + 320),
    *(_QWORD *)(*(_QWORD *)(v5 + 32) + 64LL),
    *(unsigned __int8 *)a1[8]);
  if ( (byte_14004C339 & 8) != 0 )
    McTemplateK0jjjj_EtwWriteTransfer(
      *(_DWORD *)(v5 + 32) + 72,
      *(_DWORD *)(a1[12] + 496LL) + 72,
      (_DWORD)a1 + 584,
      v12 + 96,
      *(_QWORD *)(v5 + 56) + 24LL,
      *(_QWORD *)(v5 + 32) + 72LL,
      *(_QWORD *)(a1[12] + 496LL) + 72LL);
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v5 + 32) + 112LL));
  *(_QWORD *)(v5 + 72) = v12;
  *(_BYTE *)(v5 + 352) = 0;
  if ( *(_BYTE *)(v12 + 241) )
    Smb2SetConnectionKeepalive(a1[12], 2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      24,
      &WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids,
      a1,
      *(_QWORD *)(v5 + 361));
  }
  return 0;
}

```

## disassembly

```asm
0x14001b628  push    rbx
0x14001b62a  push    rbp
0x14001b62b  push    rsi
0x14001b62c  push    rdi
0x14001b62d  push    r13
0x14001b62f  push    r14
0x14001b631  push    r15
0x14001b633  sub     rsp, 60h
0x14001b637  mov     rsi, [rcx+230h]
0x14001b63e  mov     rbp, rcx
0x14001b641  mov     rcx, [rcx+40h]
0x14001b645  xorps   xmm0, xmm0
0x14001b648  xor     eax, eax
0x14001b64a  mov     rbx, r9
0x14001b64d  mov     r14, r8
0x14001b650  mov     r13, [rsi+20h]
0x14001b654  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x14001b659  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x14001b65e  mov     rdx, [rsi+169h]
0x14001b665  mov     rcx, [rcx+0A0h]
0x14001b66c  call    Smb2FindFileGlobal
0x14001b671  mov     rdi, rax
0x14001b674  test    rax, rax
0x14001b677  jnz     short loc_14001B6AF
0x14001b679  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001b680  lea     rbx, WPP_GLOBAL_Control
0x14001b687  cmp     rcx, rbx
0x14001b68a  jz      loc_14001BD31
0x14001b690  test    dword ptr [rcx+2Ch], 10000h
0x14001b697  jz      loc_14001BD31
0x14001b69d  cmp     byte ptr [rcx+29h], 1
0x14001b6a1  jb      loc_14001BD31
0x14001b6a7  lea     edx, [rax+0Dh]
0x14001b6aa  jmp     loc_14001BCC2
0x14001b6af  mov     cl, [rax+0EDh]
0x14001b6b5  test    cl, cl
0x14001b6b7  jz      short loc_14001B6C5
0x14001b6b9  mov     r8, [rax+198h]
0x14001b6c0  test    r8, r8
0x14001b6c3  jnz     short loc_14001B6E6
0x14001b6c5  cmp     byte ptr [rax+0F1h], 0
0x14001b6cc  jz      loc_14001BCE3
0x14001b6d2  mov     r8, [rax+198h]
0x14001b6d9  test    r8, r8
0x14001b6dc  jz      loc_14001BCE3
0x14001b6e2  test    cl, cl
0x14001b6e4  jz      short loc_14001B6F9
0x14001b6e6  mov     rax, [rax+0A8h]
0x14001b6ed  test    rax, rax
0x14001b6f0  jz      short loc_14001B755
0x14001b6f2  mov     eax, [rax+78h]
0x14001b6f5  test    al, 2
0x14001b6f7  jz      short loc_14001B75E
0x14001b6f9  mov     rax, [rsi+68h]
0x14001b6fd  cmp     [rdi+0A8h], rax
0x14001b704  jz      loc_14001B793
0x14001b70a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001b711  lea     rbx, WPP_GLOBAL_Control
0x14001b718  cmp     rcx, rbx
0x14001b71b  jz      loc_14001BD29
0x14001b721  test    dword ptr [rcx+2Ch], 10000h
0x14001b728  jz      loc_14001BD29
0x14001b72e  cmp     byte ptr [rcx+29h], 1
0x14001b732  jb      loc_14001BD29
0x14001b738  mov     edx, 10h
0x14001b73d  mov     rcx, [rcx+18h]
0x14001b741  lea     r8, WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids
0x14001b748  mov     r9, rbp
0x14001b74b  call    WPP_SF_q
0x14001b750  jmp     loc_14001BD29
0x14001b755  cmp     byte ptr [rdi+11Ch], 9
0x14001b75c  jz      short loc_14001B6F9
0x14001b75e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001b765  lea     rbx, WPP_GLOBAL_Control
0x14001b76c  cmp     rcx, rbx
0x14001b76f  jz      loc_14001BD29
0x14001b775  test    dword ptr [rcx+2Ch], 10000h
0x14001b77c  jz      loc_14001BD29
0x14001b782  cmp     byte ptr [rcx+29h], 1
0x14001b786  jb      loc_14001BD29
0x14001b78c  mov     edx, 0Fh
0x14001b791  jmp     short loc_14001B73D
0x14001b793  test    rbx, rbx
0x14001b796  jz      short loc_14001B79A
0x14001b798  mov     [rbx], cl
0x14001b79a  test    r14, r14
0x14001b79d  jz      short loc_14001B7A8
0x14001b79f  mov     al, [rdi+0F1h]
0x14001b7a5  mov     [r14], al
0x14001b7a8  mov     rdx, [rsp+98h+arg_20]
0x14001b7b0  test    rdx, rdx
0x14001b7b3  jz      short loc_14001B7BD
0x14001b7b5  mov     al, [rdi+0F2h]
0x14001b7bb  mov     [rdx], al
0x14001b7bd  mov     rcx, rsi
0x14001b7c0  call    Smb2GetWorkItemSecurityContext
0x14001b7c5  mov     rcx, [r8+8]
0x14001b7c9  mov     rdx, rax
0x14001b7cc  call    Smb2VerifySecurityContext
0x14001b7d1  test    al, al
0x14001b7d3  jnz     short loc_14001B82D
0x14001b7d5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001b7dc  lea     rbx, WPP_GLOBAL_Control
0x14001b7e3  cmp     rcx, rbx
0x14001b7e6  jz      short loc_14001B81B
0x14001b7e8  test    dword ptr [rcx+2Ch], 10000h
0x14001b7ef  jz      short loc_14001B81B
0x14001b7f1  cmp     byte ptr [rcx+29h], 1
0x14001b7f5  jb      short loc_14001B81B
0x14001b7f7  mov     rax, [rsi+169h]
0x14001b7fe  lea     r8, WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids
0x14001b805  mov     rcx, [rcx+18h]
0x14001b809  mov     edx, 11h
0x14001b80e  mov     r9, rbp
0x14001b811  mov     [rsp+98h+var_78], rax
0x14001b816  call    WPP_SF_qq
0x14001b81b  mov     rcx, rdi; P
0x14001b81e  call    Smb2DereferenceFile
0x14001b823  mov     eax, 0C0000022h
0x14001b828  jmp     loc_14001BD36
0x14001b82d  cmp     byte ptr [rsi+17Ah], 0
0x14001b834  jz      short loc_14001B891
0x14001b836  mov     rcx, [rsi+150h]
0x14001b83d  sub     rcx, [rdi+2A0h]
0x14001b844  jnz     short loc_14001B854
0x14001b846  mov     rcx, [rsi+158h]
0x14001b84d  sub     rcx, [rdi+2A8h]
0x14001b854  test    rcx, rcx
0x14001b857  jz      short loc_14001B891
0x14001b859  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001b860  lea     rbx, WPP_GLOBAL_Control
0x14001b867  cmp     rcx, rbx
0x14001b86a  jz      loc_14001BD29
0x14001b870  test    dword ptr [rcx+2Ch], 10000h
0x14001b877  jz      loc_14001BD29
0x14001b87d  cmp     byte ptr [rcx+29h], 1
0x14001b881  jb      loc_14001BD29
0x14001b887  mov     edx, 12h
0x14001b88c  jmp     loc_14001BD0A
0x14001b891  mov     rax, [rsi+38h]
0x14001b895  mov     r15, [rax+60h]
0x14001b899  mov     rax, [rsi+20h]
0x14001b89d  mov     rcx, [rax+18h]
0x14001b8a1  mov     eax, 1
0x14001b8a6  lock xadd [rcx], rax
0x14001b8ab  add     rax, 2
0x14001b8af  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001b8b5  jnz     short loc_14001B8B9
0x14001b8b7  int     2Ch; Windows NT - assertion failure
0x14001b8b9  mov     rax, [rsi+38h]
0x14001b8bd  mov     ecx, 1
0x14001b8c2  lock xadd [rax], rcx
0x14001b8c7  lea     rax, [rcx+2]
0x14001b8cb  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001b8d1  jnz     short loc_14001B8D5
0x14001b8d3  int     2Ch; Windows NT - assertion failure
0x14001b8d5  mov     rax, [rsi+20h]
0x14001b8d9  lea     rcx, [rdi+70h]; SpinLock
0x14001b8dd  mov     rbx, [r13+68h]
0x14001b8e1  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x14001b8e6  mov     r14, [rax+18h]
0x14001b8ea  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001b8f1  nop     dword ptr [rax+rax+00h]
0x14001b8f6  cmp     dword ptr [rdi+0Ch], 0DCh
0x14001b8fd  jnz     loc_14001BC6C
0x14001b903  cmp     byte ptr [rdi+0EDh], 0
0x14001b90a  jnz     short loc_14001B919
0x14001b90c  cmp     byte ptr [rdi+0F1h], 0
0x14001b913  jz      loc_14001BC6C
0x14001b919  lea     rdx, [rdi+58h]
0x14001b91d  cmp     dword ptr [rdx], 0FFFFFFFFh
0x14001b920  jnz     loc_14001BC6C
0x14001b926  cmp     qword ptr [rdi+90h], 0
0x14001b92e  jnz     loc_14001BC6C
0x14001b934  cmp     [rdi+80h], r15
0x14001b93b  jnz     loc_14001BC6C
0x14001b941  mov     rcx, rbx; SpinLock
0x14001b944  call    RfsTableInsert
0x14001b949  test    al, al
0x14001b94b  jnz     short loc_14001B9C8
0x14001b94d  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x14001b952  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001b959  nop     dword ptr [rax+rax+00h]
0x14001b95e  mov     rcx, rdi; P
0x14001b961  call    Smb2DereferenceFile
0x14001b966  mov     rcx, [rsi+20h]
0x14001b96a  call    Smb2DereferenceSession
0x14001b96f  mov     rcx, [rsi+38h]; P
0x14001b973  call    Smb2DereferenceTreeConnect
0x14001b978  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001b97f  lea     rbx, WPP_GLOBAL_Control
0x14001b986  cmp     rcx, rbx
0x14001b989  jz      short loc_14001B9BE
0x14001b98b  test    dword ptr [rcx+2Ch], 10000h
0x14001b992  jz      short loc_14001B9BE
0x14001b994  cmp     byte ptr [rcx+29h], 1
0x14001b998  jb      short loc_14001B9BE
0x14001b99a  mov     rax, [rsi+169h]
0x14001b9a1  lea     r8, WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids
0x14001b9a8  mov     rcx, [rcx+18h]
0x14001b9ac  mov     edx, 14h
0x14001b9b1  mov     r9, rbp
0x14001b9b4  mov     [rsp+98h+var_78], rax
0x14001b9b9  call    WPP_SF_qq
0x14001b9be  mov     eax, 0C000009Ah
0x14001b9c3  jmp     loc_14001BD36
0x14001b9c8  mov     rax, [rsi+20h]
0x14001b9cc  lea     r15, qword_14004B3E0
0x14001b9d3  mov     [rdi+90h], rax
0x14001b9da  mov     rcx, r15; SpinLock
0x14001b9dd  mov     [rdi+98h], r14
0x14001b9e4  mov     rax, [rsi+38h]
0x14001b9e8  mov     [rdi+0A0h], rax
0x14001b9ef  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001b9f6  nop     dword ptr [rax+rax+00h]
0x14001b9fb  cmp     byte ptr [rdi+0F0h], 0
0x14001ba02  jz      short loc_14001BA6C
0x14001ba04  mov     rcx, r15; SpinLock
0x14001ba07  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001ba0e  nop     dword ptr [rax+rax+00h]
0x14001ba13  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x14001ba18  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001ba1f  nop     dword ptr [rax+rax+00h]
0x14001ba24  mov     rax, [rsi+20h]
0x14001ba28  lock inc dword ptr [rax+70h]
0x14001ba2c  mov     rcx, rdi; P
0x14001ba2f  call    Smb2DereferenceFile
0x14001ba34  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ba3b  lea     rbx, WPP_GLOBAL_Control
0x14001ba42  cmp     rcx, rbx
0x14001ba45  jz      loc_14001BD31
0x14001ba4b  test    dword ptr [rcx+2Ch], 10000h
0x14001ba52  jz      loc_14001BD31
0x14001ba58  cmp     byte ptr [rcx+29h], 1
0x14001ba5c  jb      loc_14001BD31
0x14001ba62  mov     edx, 15h
0x14001ba67  jmp     loc_14001BCC2
0x14001ba6c  cmp     byte ptr [rdi+0EDh], 0
0x14001ba73  lea     rbx, WPP_GLOBAL_Control
0x14001ba7a  jz      short loc_14001BAD9
0x14001ba7c  lea     r14, [rdi+188h]
0x14001ba83  cmp     [r14], r14
0x14001ba86  jz      short loc_14001BAD9
0x14001ba88  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ba8f  cmp     rcx, rbx
0x14001ba92  jz      short loc_14001BAC0
0x14001ba94  test    dword ptr [rcx+2Ch], 10000h
0x14001ba9b  jz      short loc_14001BAC0
0x14001ba9d  cmp     byte ptr [rcx+29h], 2
0x14001baa1  jb      short loc_14001BAC0
0x14001baa3  mov     rcx, [rcx+18h]
0x14001baa7  lea     r8, WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids
0x14001baae  mov     edx, 16h
0x14001bab3  mov     [rsp+98h+var_78], rdi
0x14001bab8  mov     r9, rbp
0x14001babb  call    WPP_SF_qq
0x14001bac0  mov     dl, 1
0x14001bac2  mov     rcx, r14
0x14001bac5  call    Smb2RemoveFileFromDurableHandleList
0x14001baca  mov     rax, cs:Srv2Statistics
0x14001bad1  inc     dword ptr [rax+88h]
0x14001bad7  jmp     short loc_14001BB3D
0x14001bad9  cmp     byte ptr [rdi+0F1h], 0
0x14001bae0  jz      short loc_14001BB3D
0x14001bae2  lea     r14, [rdi+188h]
0x14001bae9  cmp     [r14], r14
0x14001baec  jz      short loc_14001BB3D
0x14001baee  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001baf5  cmp     rcx, rbx
0x14001baf8  jz      short loc_14001BB26
0x14001bafa  test    dword ptr [rcx+2Ch], 10000h
0x14001bb01  jz      short loc_14001BB26
0x14001bb03  cmp     byte ptr [rcx+29h], 2
0x14001bb07  jb      short loc_14001BB26
0x14001bb09  mov     rcx, [rcx+18h]
0x14001bb0d  lea     r8, WPP_7d594e2a7c393ff0e3c0fb2157eeeeb7_Traceguids
0x14001bb14  mov     edx, 17h
0x14001bb19  mov     [rsp+98h+var_78], rdi
0x14001bb1e  mov     r9, rbp
0x14001bb21  call    WPP_SF_qq
0x14001bb26  mov     dl, 1
0x14001bb28  mov     rcx, r14
0x14001bb2b  call    Smb2RemoveFileFromResilientHandleList
0x14001bb30  mov     rax, cs:Srv2Statistics
0x14001bb37  inc     dword ptr [rax+0B0h]
0x14001bb3d  mov     rcx, r15; SpinLock
0x14001bb40  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001bb47  nop     dword ptr [rax+rax+00h]
0x14001bb4c  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x14001bb51  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001bb58  nop     dword ptr [rax+rax+00h]
0x14001bb5d  cmp     byte ptr [rdi+0F2h], 0
0x14001bb64  jz      short loc_14001BB92
0x14001bb66  mov     rcx, [rsi+68h]
0x14001bb6a  test    rcx, rcx
0x14001bb6d  jz      short loc_14001BB92
0x14001bb6f  cmp     dword ptr [rcx+0Ch], 0E2h
0x14001bb76  jnz     short loc_14001BB92
0x14001bb78  lea     r9, [rsi+1A8h]
0x14001bb7f  lea     r8, [rsi+1ACh]
  ... truncated ...
```
