# Smb2CreateBuildResponse

- ea: `0x14000f4d0`
- end: `0x140010147`
- name: `Smb2CreateBuildResponse`
- size: `3191`
- prototype: ``
- caller_count: `3`
- callee_count: `26`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006ad90`
- `0x140079710`
- `0x140079c30`

## callees

- `0x14000e5f0`
- `0x14000f420`
- `0x14000f4d0`
- `0x1400101f0`
- `0x140010324`
- `0x140017170`
- `0x14001ef80`
- `0x14001efac`
- `0x14002019c`
- `0x140020f78`
- `0x1400222ec`
- `0x1400224b8`
- `0x140022958`
- `0x14002d904`
- `0x140032a78`
- `0x140038490`
- `0x14006ea80`
- `0x140077600`
- `0x140080770`
- `0x140084f30`
- `0x140085670`
- `0x140085810`
- `0x140085d40`
- `0x140085f90`
- `0x140086000`
- `0x1400886a4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bc0c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bc0c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003bc6d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003bc6d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f5ce`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f64b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f9aa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ba11`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f5ce`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f64b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f9aa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ba11`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f610`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f626`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f677`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000fa02`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b9f3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ba36`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f610`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f626`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f677`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000fa02`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b9f3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ba36`
- `ntoskrnl!RtlCompareMemory` at `0x14003bce8`
- `ntoskrnl!RtlCompareMemory` at `0x14003bce8`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14003bcc3`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14003bcc3`
- `ntoskrnl!NtQueryInformationFile` at `0x14000fbc2`
- `ntoskrnl!NtQueryInformationFile` at `0x14000fbc2`
- `ntoskrnl!PsImpersonateClient` at `0x14000fd21`
- `ntoskrnl!PsImpersonateClient` at `0x14000fd21`
- `ntoskrnl!FsRtlGetNextExtraCreateParameter` at `0x14003bc98`
- `ntoskrnl!FsRtlGetNextExtraCreateParameter` at `0x14003bc98`
- `srvnet!SrvLibFilePowerManagementPreventIdle` at `0x14000fb52`
- `srvnet!SrvLibFilePowerManagementPreventIdle` at `0x14000fb52`
- `ksecdd!ImpersonateSecurityContext` at `0x14000f58a`
- `ksecdd!ImpersonateSecurityContext` at `0x14000f58a`

## pseudocode

```c
__int64 __fastcall Smb2CreateBuildResponse(_QWORD *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rax
  __int64 v4; // r13
  __int64 v5; // rcx
  __int64 v6; // r14
  __int64 v7; // rdx
  __int64 v8; // rdx
  NTSTATUS v9; // eax
  NTSTATUS NetworkOpenInfo; // esi
  __int64 v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // rdi
  signed __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rdx
  int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rdx
  int v22; // edi
  int v23; // r8d
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // eax
  bool v27; // zf
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // rax
  void *v31; // r12
  __int64 v32; // r13
  __int64 v33; // rdi
  PVOID v34; // rcx
  __int128 v35; // xmm0
  __int64 v36; // rax
  char v37; // al
  __int64 v38; // rcx
  __int64 v39; // rcx
  _BYTE *v41; // rsi
  char v42; // al
  PVOID v43; // rdx
  __int64 v44; // rdi
  __int64 v45; // r8
  __int64 SessionSelfSecurityDescriptor; // rax
  void *v47; // r12
  int v48; // r13d
  __int64 v49; // r9
  KIRQL v50; // r8
  __int64 v51; // rdx
  __int64 v52; // rax
  int FileInformationClass; // [rsp+20h] [rbp-A9h]
  char v54; // [rsp+40h] [rbp-89h]
  ULONG NextEcpContextSize; // [rsp+44h] [rbp-85h] BYREF
  char v56; // [rsp+48h] [rbp-81h]
  PVOID NextEcpContext; // [rsp+50h] [rbp-79h] BYREF
  __int64 v58; // [rsp+58h] [rbp-71h] BYREF
  __int64 v59; // [rsp+60h] [rbp-69h] BYREF
  struct _KLOCK_QUEUE_HANDLE v60; // [rsp+68h] [rbp-61h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp-49h] BYREF
  __int128 v62; // [rsp+98h] [rbp-31h] BYREF
  __int128 v63; // [rsp+A8h] [rbp-21h]
  __int128 v64; // [rsp+B8h] [rbp-11h]
  int v65; // [rsp+C8h] [rbp-1h]
  _OWORD FileInformation[2]; // [rsp+D0h] [rbp+7h] BYREF

  v1 = a1[70];
  v65 = 0;
  v3 = a1[12];
  v62 = 0;
  v63 = 0;
  v64 = 0;
  memset(&v60, 0, sizeof(v60));
  v4 = *(_QWORD *)(v3 + 496);
  v5 = *(_QWORD *)(a1[39] + 24LL);
  *(_DWORD *)(v5 + 124) = 0;
  v62 = 0;
  v65 = 0;
  v6 = v5 + 64;
  v59 = v5;
  v63 = 0;
  v58 = v5 + 64;
  v64 = 0;
  v7 = *(_QWORD *)(v1 + 56);
  if ( !v7 || (v8 = *(_QWORD *)(v7 + 120)) == 0 )
    v8 = *(_QWORD *)(v1 + 48);
  if ( *(_BYTE *)(v8 + 24) )
  {
    v9 = PsImpersonateClient(
           KeGetCurrentThread(),
           *(PACCESS_TOKEN *)(v8 + 48),
           *(_BYTE *)(v8 + 60),
           *(_BYTE *)(v8 + 61),
           *(SECURITY_IMPERSONATION_LEVEL *)(v8 + 64));
  }
  else
  {
    if ( !*(_QWORD *)(v8 + 32) && !*(_QWORD *)(v8 + 40) )
    {
      NetworkOpenInfo = -1073741790;
      goto LABEL_85;
    }
    v9 = ImpersonateSecurityContext((PCtxtHandle)(v8 + 32));
  }
  NetworkOpenInfo = v9;
  if ( v9 >= 0 )
  {
    if ( !*(_QWORD *)(v1 + 80) )
    {
      v11 = *(_QWORD *)(v1 + 72);
      memset(&LockHandle, 0, sizeof(LockHandle));
      v12 = 0;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v11 + 112), &LockHandle);
      if ( (unsigned int)(*(_DWORD *)(v11 + 12) - 219) > 1
        || (v13 = *(_QWORD *)(v11 + 120)) == 0
        || *(_BYTE *)(v13 + 104)
        || (v14 = _InterlockedIncrement64((volatile signed __int64 *)v13)) != 0 && (v12 = v13, v14 != -1) )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        *(_QWORD *)(v1 + 80) = v12;
        if ( !v12 )
        {
          NetworkOpenInfo = -1073741528;
          goto LABEL_84;
        }
      }
      else
      {
        __int2c();
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        *(_QWORD *)(v1 + 80) = v13;
      }
    }
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v1 + 72) + 112LL), &v60);
    v15 = *(_QWORD *)(v1 + 72);
    if ( *(_DWORD *)(v15 + 12) != 220 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          69,
          WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
          *(_QWORD *)(v1 + 72));
      }
      NetworkOpenInfo = -1073741528;
      KeReleaseInStackQueuedSpinLock(&v60);
      goto LABEL_84;
    }
    *(_OWORD *)(v6 + 64) = *(_OWORD *)(v15 + 80);
    KeReleaseInStackQueuedSpinLock(&v60);
    *(_DWORD *)(v6 + 4) = *(_DWORD *)(*(_QWORD *)(v1 + 72) + 456LL);
    *(_QWORD *)(v6 + 80) = 0;
    *(_WORD *)v6 = 89;
    *(_BYTE *)(v6 + 3) = *(_BYTE *)(v1 + 308) != 0;
    *(_DWORD *)(a1[39] + 36LL) = 152;
    if ( *(_BYTE *)(v1 + 304) )
    {
      NextEcpContext = 0;
      if ( *(_QWORD *)(v1 + 312) == *(_QWORD *)(v6 + 32) )
      {
        LODWORD(NextEcpContext) = -1073741709;
      }
      else
      {
        v17 = *(_QWORD *)(v1 + 56);
        if ( !v17 || (v18 = *(_QWORD *)(v17 + 120)) == 0 )
          v18 = *(_QWORD *)(v1 + 48);
        LODWORD(NextEcpContext) = Smb2QueryMaximalAccess(*(_QWORD *)(v1 + 72), v18, (__int64)&NextEcpContext + 4);
      }
      NextEcpContextSize = 1665235021;
      NetworkOpenInfo = Smb2AddCreateContextToResponse(4, &NextEcpContextSize, 8, &NextEcpContext, a1, &v59, &v58);
      if ( NetworkOpenInfo < 0 )
        goto LABEL_84;
      v6 = v58;
    }
    v19 = *(_DWORD *)(v1 + 332);
    if ( (v19 & 0x41) != 0 )
    {
      v20 = *(_QWORD *)(v1 + 72);
      v54 = 1;
      v21 = *(_DWORD *)(v20 + 224)
          ^ ((unsigned __int8)*(_DWORD *)(v20 + 224)
           ^ (unsigned __int8)((_BYTE)v19 << 6))
          & 0x40u;
      *(_DWORD *)(v20 + 224) = v21;
    }
    else
    {
      NetworkOpenInfo = Smb2QueryNetworkOpenInfo(a1, *(_QWORD *)(v1 + 80), v6 + 8);
      if ( NetworkOpenInfo < 0 )
        goto LABEL_84;
      v21 = *(_QWORD *)(v1 + 72);
      v54 = 0;
      *(_DWORD *)(v21 + 224) = *(_DWORD *)(v21 + 224) & 0xFFFFFFBF | (4 * (*(_DWORD *)(v6 + 56) & 0x10));
    }
    v22 = -1073741823;
    v56 = 0;
    if ( *(_BYTE *)(v1 + 360) || *(_BYTE *)(v1 + 378) )
    {
      v16 = *(_QWORD *)(v1 + 72);
      if ( *(_QWORD *)(v16 + 168) )
      {
        *(_BYTE *)(v6 + 2) = -1;
        LOBYTE(FileInformationClass) = *(_BYTE *)(v1 + 424);
        Smb2AddLeaseContextForReconnect(
          (_DWORD)a1,
          (unsigned int)&v62,
          (unsigned int)&v59,
          (unsigned int)&v58,
          FileInformationClass,
          *(_WORD *)(v1 + 426),
          *(_DWORD *)(v1 + 428));
        v6 = v58;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            70,
            WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
            v16,
            *(unsigned __int8 *)(v16 + 284));
        }
        *(_BYTE *)(v6 + 2) = *(_BYTE *)(*(_QWORD *)(v1 + 72) + 284LL);
      }
      if ( *(_BYTE *)(v1 + 380) )
      {
        *(_BYTE *)(*(_QWORD *)(v1 + 72) + 242LL) = 1;
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 72) + 136LL) + 504LL));
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v1 + 40) + 336LL));
      }
    }
    else
    {
      if ( !*(_BYTE *)(v1 + 306) )
        goto LABEL_187;
      if ( *(_BYTE *)(v1 + 307) )
      {
        *(_BYTE *)(v1 + 302) = -1;
        *(_BYTE *)(v6 + 2) = -1;
        LOBYTE(FileInformationClass) = *(_BYTE *)(v1 + 424);
        Smb2AddLeaseContextForReconnect(
          (_DWORD)a1,
          (unsigned int)&v62,
          (unsigned int)&v59,
          (unsigned int)&v58,
          FileInformationClass,
          *(_WORD *)(v1 + 426),
          *(_DWORD *)(v1 + 428));
        v6 = v58;
      }
      else if ( Smb2DirLeasingEnabled && *(_WORD *)(*(_QWORD *)(v1 + 32) + 288LL) >= 0x300u
             || (*(_DWORD *)(*(_QWORD *)(v1 + 72) + 224LL) & 0x40) == 0 )
      {
        v23 = *(_DWORD *)(v1 + 264);
        v24 = *(_QWORD *)(v1 + 72);
        v25 = *(_QWORD *)(v1 + 104);
        *(_BYTE *)(v1 + 302) = 0;
        v26 = Smb2LeaseAcquireOrUpgrade(v25, v24, v23, 0, v1 + 296, (__int64)&v62);
        v21 = 0x80000000LL;
        if ( (int)(v26 + 0x80000000) < 0 || v26 == -1073741823 )
        {
          v27 = *(_BYTE *)(v1 + 301) == 0;
          v56 = 1;
          v54 = 1;
          if ( !v27 )
          {
            DWORD1(v63) |= 4u;
            v64 = *(_OWORD *)(v1 + 280);
          }
          v28 = *(_QWORD *)(v1 + 104);
          v29 = 52;
          NextEcpContextSize = 1934389586;
          if ( !*(_BYTE *)(v28 + 135) )
            v29 = 32;
          Smb2AddCreateContextToResponse(4, &NextEcpContextSize, v29, &v62, a1, &v59, &v58);
          v30 = *(_QWORD *)(v1 + 72);
          v6 = v58;
          *(_BYTE *)(v1 + 302) = -1;
          *(_BYTE *)(v30 + 284) = -1;
          *(_BYTE *)(v6 + 2) = -1;
          if ( (*(_DWORD *)(*(_QWORD *)(v1 + 72) + 192LL) & 0x1000) != 0 )
            Smb2FilePreventLeaseDelay();
        }
        else if ( v26 == -1073741808 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              71,
              WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
              *(_QWORD *)(v1 + 104));
          }
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v1 + 72) + 112LL), &v60);
          if ( *(_QWORD *)(*(_QWORD *)(v1 + 72) + 168LL) )
            Smb2LeaseCloseFile();
          KeReleaseInStackQueuedSpinLock(&v60);
          Smb2LeaseDisconnect(*(_QWORD *)(v1 + 104), *(_QWORD *)(*(_QWORD *)(v4 + 24) + 136LL));
          Smb2ReleaseLeaseReferenceForWorkItem(v1);
          Smb2LeaseStateMapToOplock(*(unsigned int *)(v1 + 264), v1 + 302);
          *(_BYTE *)(v1 + 306) = 0;
        }
      }
      if ( !*(_BYTE *)(v1 + 306) )
      {
LABEL_187:
        v41 = (_BYTE *)(v1 + 302);
        v21 = *(unsigned __int8 *)(v1 + 302);
        if ( (_BYTE)v21 )
        {
          if ( !*(_BYTE *)(v1 + 307) )
          {
            if ( (*(_DWORD *)(*(_QWORD *)(v1 + 72) + 224LL) & 0x40) != 0 && (_BYTE)v21 != 16 )
              *v41 = 0;
            while ( (int)Smb2RequestOplock(*(PVOID *)(v1 + 72)) < 0 )
            {
              if ( *v41 == 1 )
              {
                *v41 = 0;
                goto LABEL_46;
              }
              *v41 = 1;
            }
            v54 = 1;
          }
        }
      }
LABEL_46:
      *(_BYTE *)(v6 + 2) = *(_BYTE *)(v1 + 302);
    }
    if ( *(_BYTE *)(v1 + 381) )
    {
      Smb2RkfNotifyComplete(a1[8], *(_QWORD *)(*(_QWORD *)(v1 + 80) + 96LL));
      *(_BYTE *)(v1 + 381) = 0;
    }
    NetworkOpenInfo = 0;
    if ( *(_BYTE *)(v1 + 352) )
    {
      v42 = *(_BYTE *)(v6 + 2);
      if ( v42 == 9 || v42 == -1 && (v63 & 2) != 0 )
      {
        if ( *(_BYTE *)(v1 + 307) )
          goto LABEL_160;
        LOBYTE(v21) = 1;
        SessionSelfSecurityDescriptor = Smb2GetSessionSelfSecurityDescriptor(*(_QWORD *)(v1 + 32), v21);
        v47 = (void *)SessionSelfSecurityDescriptor;
        if ( SessionSelfSecurityDescriptor )
        {
          v48 = Smb2MarkFileForDurableOperation(*(_QWORD *)(v1 + 72), 0, SessionSelfSecurityDescriptor);
          if ( v48 >= 0 )
          {
            _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 72) + 136LL) + 456LL));
            _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v1 + 40) + 288LL));
          }
          Smb2DereferenceSecurityDescriptor(v47);
          if ( v48 >= 0 )
          {
LABEL_160:
            v49 = *(_QWORD *)(v1 + 72);
            NextEcpContextSize = 1366181956;
            NetworkOpenInfo = Smb2AddCreateContextToResponse(4, &NextEcpContextSize, 8, v49 + 376, a1, &v59, &v58);
            if ( NetworkOpenInfo < 0 )
              goto LABEL_84;
            v6 = v58;
          }
        }
      }
    }
    if ( *(_BYTE *)(v1 + 377) )
    {
      if ( *(_BYTE *)(v1 + 307) )
        goto LABEL_60;
      LOBYTE(v21) = 1;
      v31 = (void *)Smb2GetSessionSelfSecurityDescriptor(*(_QWORD *)(v1 + 32), v21);
      if ( v31 )
      {
        v32 = *(_QWORD *)(v1 + 72);
        if ( (*(_DWORD *)(v32 + 224) & 0x40) == 0 || *(_BYTE *)(v1 + 380) )
        {
          v33 = *(unsigned int *)(v1 + 356);
          NextEcpContext = 0;
          memset(&LockHandle, 0, sizeof(LockHandle));
          Smb2ReferenceSecurityDescriptor(v31);
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v32 + 112), &LockHandle);
          v34 = NextEcpContext;
          v35 = *(_OWORD *)(v32 + 80);
          if ( *(_QWORD *)(v32 + 408) )
            v34 = *(PVOID *)(v32 + 408);
          *(_BYTE *)(v32 + 237) = 1;
          NextEcpContext = v34;
          *(_OWORD *)(v32 + 360) = v35;
          *(_QWORD *)(v32 + 408) = v31;
          *(_QWORD *)(v32 + 376) = 10000 * v33;
          *(_BYTE *)(v32 + 238) = 1;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( NextEcpContext )
            Smb2DereferenceSecurityDescriptor(NextEcpContext);
          v22 = 0;
          _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 72) + 136LL) + 456LL));
          _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v1 + 40) + 288LL));
        }
        else
        {
          v22 = -1073741637;
        }
        Smb2DereferenceSecurityDescriptor(v31);
        if ( v22 >= 0 )
        {
LABEL_60:
          v27 = *(_BYTE *)(v1 + 380) == 0;
          LODWORD(NextEcpContext) = *(_DWORD *)(v1 + 356);
          if ( !v27 )
          {
            *(_BYTE *)(*(_QWORD *)(v1 + 72) + 242LL) = 1;
            _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v1 + 72) + 136LL) + 504LL));
            _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v1 + 40) + 336LL));
          }
          v36 = *(_QWORD *)(v1 + 72);
          HIDWORD(NextEcpContext) = 0;
          if ( *(_BYTE *)(v36 + 242) )
          {
            HIDWORD(NextEcpContext) = 2;
            NextEcpContextSize = 1362249796;
            NetworkOpenInfo = Smb2AddCreateContextToResponse(4, &NextEcpContextSize, 8, &NextEcpContext, a1, &v59, &v58);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                72,
                WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
                *(_QWORD *)(v1 + 72));
            }
            if ( v56 )
            {
              v50 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(v1 + 104) + 96LL));
              *(_BYTE *)(*(_QWORD *)(v1 + 104) + 133LL) = 1;
              v51 = *(_QWORD *)(*(_QWORD *)(v1 + 72) + 376LL);
              if ( !v51 || v51 >= 1800000000 )
                LODWORD(v51) = 1800000000;
              v52 = *(_QWORD *)(v1 + 104);
              if ( *(_DWORD *)(v52 + 248) < (unsigned int)v51 )
                *(_DWORD *)(v52 + 248) = v51;
              ++*(_DWORD *)(*(_QWORD *)(v1 + 104) + 252LL);
              KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v1 + 104) + 96LL), v50);
            }
          }
          else
          {
            v37 = *(_BYTE *)(v6 + 2);
            if ( v37 != 9 && (v37 != -1 || (v63 & 2) == 0) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
              }
LABEL_68:
              if ( NetworkOpenInfo < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
                }
                goto LABEL_84;
              }
              goto LABEL_69;
            }
            NextEcpContextSize = 1362249796;
            NetworkOpenInfo = Smb2AddCreateContextToResponse(4, &NextEcpContextSize, 8, &NextEcpContext, a1, &v59, &v58);
          }
          v6 = v58;
          goto LABEL_68;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          75,
          WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
          (unsigned int)v22);
      }
    }
LABEL_69:
    if ( !v54 || (NetworkOpenInfo = Smb2QueryNetworkOpenInfo(a1, *(_QWORD *)(v1 + 80), v6 + 8), NetworkOpenInfo >= 0) )
    {
      *(_DWORD *)(*(_QWORD *)(v1 + 72) + 224LL) = *(_DWORD *)(*(_QWORD *)(v1 + 72) + 224LL) & 0xFFFFFEFF
                                                | (*(_DWORD *)(v6 + 56) >> 4) & 0x100;
      if ( !*(_BYTE *)(*(_QWORD *)(v1 + 32) + 276LL) && *(_DWORD *)(*(_QWORD *)(v1 + 56) + 76LL) != 1 )
      {
        v38 = *(_QWORD *)(v1 + 72);
        if ( (*(_DWORD *)(v38 + 224) & 0x40) == 0 )
          SrvLibFilePowerManagementPreventIdle(v38 + 256);
      }
      if ( *(_BYTE *)(v1 + 328) && *(_QWORD *)(v1 + 320) )
      {
        v43 = 0;
        v44 = *(_QWORD *)(a1[12] + 496LL);
        NextEcpContext = 0;
        LockHandle.LockQueue = 0;
        NextEcpContextSize = 0;
        while ( FsRtlGetNextExtraCreateParameter(
                  *(PECP_LIST *)(v1 + 320),
                  v43,
                  (LPGUID)&LockHandle,
                  &NextEcpContext,
                  &NextEcpContextSize) >= 0 )
        {
          if ( Smb2IsKnownPassthroughEcp(&LockHandle, 0) && FsRtlIsEcpAcknowledged(NextEcpContext) )
          {
            if ( RtlCompareMemory(&LockHandle, &Smb2RkfGuidEcpIn, 0x10u) != 16
              || *(_BYTE *)(*(_QWORD *)(v44 + 56) + 509LL) )
            {
              NetworkOpenInfo = Smb2AddCreateContextToResponse(
                                  16,
                                  &LockHandle,
                                  NextEcpContextSize,
                                  NextEcpContext,
                                  a1,
                                  &v59,
                                  &v58);
              if ( NetworkOpenInfo < 0 )
                goto LABEL_84;
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
            }
          }
          v43 = NextEcpContext;
        }
      }
      if ( *(_BYTE *)(v1 + 360) || *(_BYTE *)(v1 + 378) || !*(_BYTE *)(v1 + 305) )
        goto LABEL_188;
      v39 = *(_QWORD *)(v1 + 80);
      LockHandle.LockQueue = 0;
      memset(FileInformation, 0, sizeof(FileInformation));
      NetworkOpenInfo = NtQueryInformationFile(
                          *(HANDLE *)(v39 + 88),
                          (PIO_STATUS_BLOCK)&LockHandle,
                          FileInformation,
                          8u,
                          FileInternalInformation);
      if ( NetworkOpenInfo < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            67,
            WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
            *(_QWORD *)(*(_QWORD *)(v1 + 80) + 88LL));
        }
        goto LABEL_84;
      }
      if ( *(_QWORD *)&FileInformation[0] == -1
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          68,
          WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v1 + 80) + 88LL));
      }
      NetworkOpenInfo = Smb2GetVolumeID(v1, (char *)FileInformation + 8);
      if ( NetworkOpenInfo >= 0 )
      {
        NextEcpContextSize = 1684620881;
        NetworkOpenInfo = Smb2AddCreateContextToResponse(4, &NextEcpContextSize, 32, FileInformation, a1, &v59, &v58);
        if ( NetworkOpenInfo >= 0 )
        {
LABEL_188:
          if ( (*(_DWORD *)(*(_QWORD *)(v1 + 56) + 84LL) & 0x1000000) != 0 )
          {
            v45 = *(_QWORD *)(v1 + 32);
            if ( *(_BYTE *)(v45 + 285) )
              Smb2MarkFileForResilientOperation(*(_QWORD *)(v1 + 72), 300000, v45, v16);
          }
        }
      }
    }
LABEL_84:
    Smb2Revert();
  }
LABEL_85:
  Smb2ReleaseLeaseReferenceForWorkItem(v1);
  return (unsigned int)NetworkOpenInfo;
}

```

## disassembly

```asm
0x14000f4d0  mov     [rsp-8+arg_10], rbx
0x14000f4d5  mov     [rsp-8+arg_18], rsi
0x14000f4da  push    rbp
0x14000f4db  push    r12
0x14000f4dd  push    r13
0x14000f4df  push    r14
0x14000f4e1  push    r15
0x14000f4e3  lea     rbp, [rsp-37h]
0x14000f4e8  sub     rsp, 100h
0x14000f4ef  mov     rax, cs:__security_cookie
0x14000f4f6  xor     rax, rsp
0x14000f4f9  mov     [rbp+57h+var_30], rax
0x14000f4fd  mov     rbx, [rcx+230h]
0x14000f504  xorps   xmm0, xmm0
0x14000f507  xor     eax, eax
0x14000f509  xor     r12d, r12d
0x14000f50c  mov     [rbp+57h+var_58], eax
0x14000f50f  mov     r15, rcx
0x14000f512  mov     qword ptr [rbp+57h+var_B8.OldIrql], rax
0x14000f516  mov     rax, [rcx+60h]
0x14000f51a  movups  [rbp+57h+var_88], xmm0
0x14000f51e  movups  [rbp+57h+var_78], xmm0
0x14000f522  movups  [rbp+57h+var_68], xmm0
0x14000f526  movups  xmmword ptr [rbp+57h+var_B8.LockQueue.Next], xmm0
0x14000f52a  mov     r13, [rax+1F0h]
0x14000f531  mov     rax, [rcx+138h]
0x14000f538  mov     rcx, [rax+18h]
0x14000f53c  xor     eax, eax
0x14000f53e  mov     [rcx+7Ch], r12d
0x14000f542  movups  [rbp+57h+var_88], xmm0
0x14000f546  mov     [rbp+57h+var_58], eax
0x14000f549  lea     r14, [rcx+40h]
0x14000f54d  mov     [rbp+57h+var_C0], rcx
0x14000f551  movups  [rbp+57h+var_78], xmm0
0x14000f555  mov     [rbp+57h+var_C8], r14
0x14000f559  movups  [rbp+57h+var_68], xmm0
0x14000f55d  mov     rdx, [rbx+38h]
0x14000f561  test    rdx, rdx
0x14000f564  jz      short loc_14000F56F
0x14000f566  mov     rdx, [rdx+78h]
0x14000f56a  test    rdx, rdx
0x14000f56d  jnz     short loc_14000F573
0x14000f56f  mov     rdx, [rbx+30h]
0x14000f573  cmp     [rdx+18h], al
0x14000f576  jnz     loc_14000FD03
0x14000f57c  cmp     [rdx+20h], rax
0x14000f580  lea     rcx, [rdx+20h]; phContext
0x14000f584  jz      loc_14000FEC7
0x14000f58a  call    cs:__imp_ImpersonateSecurityContext
0x14000f591  nop     dword ptr [rax+rax+00h]
0x14000f596  mov     esi, eax
0x14000f598  test    eax, eax
0x14000f59a  js      loc_14000FC51
0x14000f5a0  mov     [rsp+120h+arg_8], rdi
0x14000f5a8  cmp     [rbx+50h], r12
0x14000f5ac  jnz     loc_14000F63F
0x14000f5b2  mov     rdi, [rbx+48h]
0x14000f5b6  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14000f5ba  xorps   xmm0, xmm0
0x14000f5bd  xor     eax, eax
0x14000f5bf  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000f5c3  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000f5c7  mov     rsi, r12
0x14000f5ca  lea     rcx, [rdi+70h]; SpinLock
0x14000f5ce  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f5d5  nop     dword ptr [rax+rax+00h]
0x14000f5da  mov     eax, [rdi+0Ch]
0x14000f5dd  sub     eax, 0DBh
0x14000f5e2  cmp     eax, 1
0x14000f5e5  ja      short loc_14000F622
0x14000f5e7  mov     rdi, [rdi+78h]
0x14000f5eb  test    rdi, rdi
0x14000f5ee  jz      short loc_14000F622
0x14000f5f0  cmp     [rdi+68h], sil
0x14000f5f4  jnz     short loc_14000F622
0x14000f5f6  mov     eax, 1
0x14000f5fb  lock xadd [rdi], rax
0x14000f600  add     rax, 1
0x14000f604  jnz     loc_14000FEDB
0x14000f60a  int     2Ch; Windows NT - assertion failure
0x14000f60c  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000f610  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f617  nop     dword ptr [rax+rax+00h]
0x14000f61c  mov     [rbx+50h], rdi
0x14000f620  jmp     short loc_14000F63F
0x14000f622  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000f626  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f62d  nop     dword ptr [rax+rax+00h]
0x14000f632  mov     [rbx+50h], rsi
0x14000f636  test    rsi, rsi
0x14000f639  jz      loc_14000FE68
0x14000f63f  mov     rcx, [rbx+48h]
0x14000f643  lea     rdx, [rbp+57h+var_B8]; LockHandle
0x14000f647  add     rcx, 70h ; 'p'; SpinLock
0x14000f64b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f652  nop     dword ptr [rax+rax+00h]
0x14000f657  mov     r8, [rbx+48h]
0x14000f65b  cmp     dword ptr [r8+0Ch], 0DCh
0x14000f663  jnz     loc_14000FEED
0x14000f669  movups  xmm0, xmmword ptr [r8+50h]
0x14000f66e  lea     rcx, [rbp+57h+var_B8]; LockHandle
0x14000f672  movups  xmmword ptr [r14+40h], xmm0
0x14000f677  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f67e  nop     dword ptr [rax+rax+00h]
0x14000f683  mov     rax, [rbx+48h]
0x14000f687  mov     ecx, [rax+1C8h]
0x14000f68d  mov     [r14+4], ecx
0x14000f691  mov     [r14+50h], r12
0x14000f695  mov     word ptr [r14], 59h ; 'Y'
0x14000f69b  cmp     [rbx+134h], r12b
0x14000f6a2  setnz   al
0x14000f6a5  mov     [r14+3], al
0x14000f6a9  mov     rax, [r15+138h]
0x14000f6b0  mov     dword ptr [rax+24h], 98h
0x14000f6b7  cmp     [rbx+130h], r12b
0x14000f6be  jz      loc_14000F745
0x14000f6c4  mov     [rbp+57h+NextEcpContext], r12
0x14000f6c8  mov     rax, [r14+20h]
0x14000f6cc  cmp     [rbx+138h], rax
0x14000f6d3  jz      loc_14000FEBB
0x14000f6d9  mov     rdx, [rbx+38h]
0x14000f6dd  test    rdx, rdx
0x14000f6e0  jz      short loc_14000F6EB
0x14000f6e2  mov     rdx, [rdx+78h]
0x14000f6e6  test    rdx, rdx
0x14000f6e9  jnz     short loc_14000F6EF
0x14000f6eb  mov     rdx, [rbx+30h]
0x14000f6ef  mov     rcx, [rbx+48h]
0x14000f6f3  lea     r8, [rbp+57h+NextEcpContext+4]
0x14000f6f7  call    Smb2QueryMaximalAccess
0x14000f6fc  mov     dword ptr [rbp+57h+NextEcpContext], eax
0x14000f6ff  lea     rax, [rbp+57h+var_C8]
0x14000f703  mov     [rsp+120h+NextEcpContextSize], 6341784Dh
0x14000f70b  mov     [rsp+120h+var_F0], rax
0x14000f710  lea     r9, [rbp+57h+NextEcpContext]
0x14000f714  lea     rax, [rbp+57h+var_C0]
0x14000f718  mov     r8d, 8
0x14000f71e  mov     [rsp+120h+var_F8], rax
0x14000f723  lea     rdx, [rsp+120h+NextEcpContextSize]
0x14000f728  mov     ecx, 4
0x14000f72d  mov     qword ptr [rsp+120h+FileInformationClass], r15
0x14000f732  call    Smb2AddCreateContextToResponse
0x14000f737  mov     esi, eax
0x14000f739  test    eax, eax
0x14000f73b  js      loc_14000FC44
0x14000f741  mov     r14, [rbp+57h+var_C8]
0x14000f745  mov     edx, [rbx+14Ch]
0x14000f74b  test    dl, 41h
0x14000f74e  jz      loc_14000FC85
0x14000f754  mov     rcx, [rbx+48h]
0x14000f758  shl     edx, 6
0x14000f75b  mov     [rsp+120h+var_E0], 1
0x14000f760  mov     eax, [rcx+0E0h]
0x14000f766  xor     edx, eax
0x14000f768  and     edx, 40h
0x14000f76b  xor     edx, eax
0x14000f76d  mov     [rcx+0E0h], edx
0x14000f773  mov     edi, 0C0000001h
0x14000f778  mov     [rsp+120h+var_D8], r12b
0x14000f77d  cmp     [rbx+168h], r12b
0x14000f784  jnz     loc_14000FDBE
0x14000f78a  cmp     [rbx+17Ah], r12b
0x14000f791  jnz     loc_14000FDBE
0x14000f797  cmp     byte ptr [rbx+132h], 0
0x14000f79e  lea     r12, WPP_GLOBAL_Control
0x14000f7a5  jz      loc_14000FD7B
0x14000f7ab  cmp     byte ptr [rbx+133h], 0
0x14000f7b2  jnz     loc_14000FF59
0x14000f7b8  cmp     cs:Smb2DirLeasingEnabled, 0
0x14000f7bf  jz      loc_14000FF37
0x14000f7c5  mov     rax, [rbx+20h]
0x14000f7c9  mov     ecx, 300h
0x14000f7ce  cmp     [rax+120h], cx
0x14000f7d5  jb      loc_14000FF37
0x14000f7db  mov     r8d, [rbx+108h]
0x14000f7e2  lea     rcx, [rbp+57h+var_88]
0x14000f7e6  mov     rdx, [rbx+48h]
0x14000f7ea  lea     rax, [rbx+128h]
0x14000f7f1  mov     [rsp+120h+var_F8], rcx
0x14000f7f6  xor     r9d, r9d
0x14000f7f9  mov     rcx, [rbx+68h]
0x14000f7fd  mov     byte ptr [rbx+12Eh], 0
0x14000f804  mov     qword ptr [rsp+120h+FileInformationClass], rax
0x14000f809  call    Smb2LeaseAcquireOrUpgrade
0x14000f80e  mov     edx, 80000000h
0x14000f813  lea     ecx, [rax+rdx]
0x14000f816  test    edx, ecx
0x14000f818  jnz     short loc_14000F86D
0x14000f81a  cmp     eax, edi
0x14000f81c  jz      short loc_14000F86D
0x14000f81e  cmp     eax, 0C0000010h
0x14000f823  jnz     loc_14000F90A
0x14000f829  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f830  cmp     rcx, r12
0x14000f833  jz      loc_14003BA05
0x14000f839  mov     eax, [rcx+2Ch]
0x14000f83c  test    al, 1
0x14000f83e  jz      loc_14003BA05
0x14000f844  cmp     byte ptr [rcx+29h], 2
0x14000f848  jb      loc_14003BA05
0x14000f84e  mov     r9, [rbx+68h]
0x14000f852  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14000f859  mov     rcx, [rcx+18h]
0x14000f85d  mov     edx, 47h ; 'G'
0x14000f862  call    WPP_SF_q
0x14000f867  nop
0x14000f868  jmp     loc_14003BA05
0x14000f86d  cmp     byte ptr [rbx+12Dh], 0
0x14000f874  mov     [rsp+120h+var_D8], 1
0x14000f879  mov     [rsp+120h+var_E0], 1
0x14000f87e  jz      short loc_14000F88F
0x14000f880  or      dword ptr [rbp+57h+var_78+4], 4
0x14000f884  movups  xmm0, xmmword ptr [rbx+118h]
0x14000f88b  movups  [rbp+57h+var_68], xmm0
0x14000f88f  mov     rax, [rbx+68h]
0x14000f893  lea     r9, [rbp+57h+var_88]
0x14000f897  mov     r8d, 34h ; '4'
0x14000f89d  mov     [rsp+120h+NextEcpContextSize], 734C7152h
0x14000f8a5  lea     rdx, [rsp+120h+NextEcpContextSize]
0x14000f8aa  mov     ecx, 4
0x14000f8af  cmp     byte ptr [rax+87h], 0
0x14000f8b6  mov     eax, 20h ; ' '
0x14000f8bb  cmovz   r8d, eax
0x14000f8bf  lea     rax, [rbp+57h+var_C8]
0x14000f8c3  mov     [rsp+120h+var_F0], rax
0x14000f8c8  lea     rax, [rbp+57h+var_C0]
0x14000f8cc  mov     [rsp+120h+var_F8], rax
0x14000f8d1  mov     qword ptr [rsp+120h+FileInformationClass], r15
0x14000f8d6  call    Smb2AddCreateContextToResponse
0x14000f8db  mov     rax, [rbx+48h]
0x14000f8df  mov     r14, [rbp+57h+var_C8]
0x14000f8e3  mov     byte ptr [rbx+12Eh], 0FFh
0x14000f8ea  mov     byte ptr [rax+11Ch], 0FFh
0x14000f8f1  mov     byte ptr [r14+2], 0FFh
0x14000f8f6  mov     rcx, [rbx+48h]
0x14000f8fa  test    dword ptr [rcx+0C0h], 1000h
0x14000f904  jnz     loc_14000FF4F
0x14000f90a  cmp     byte ptr [rbx+132h], 0
0x14000f911  jz      loc_14000FD7B
0x14000f917  movzx   eax, byte ptr [rbx+12Eh]
0x14000f91e  mov     [r14+2], al
0x14000f922  cmp     byte ptr [rbx+17Dh], 0
0x14000f929  jnz     loc_14000FFF1
0x14000f92f  xor     esi, esi
0x14000f931  cmp     [rbx+160h], sil
0x14000f938  jnz     loc_14001000E
0x14000f93e  cmp     byte ptr [rbx+179h], 0
0x14000f945  jz      loc_14000FAE2
0x14000f94b  cmp     byte ptr [rbx+133h], 0
0x14000f952  jnz     loc_14000FA53
0x14000f958  mov     rcx, [rbx+20h]
0x14000f95c  mov     dl, 1
0x14000f95e  call    Smb2GetSessionSelfSecurityDescriptor
0x14000f963  mov     r12, rax
0x14000f966  test    rax, rax
0x14000f969  jz      loc_14000FD32
0x14000f96f  mov     r13, [rbx+48h]
0x14000f973  mov     ecx, [r13+0E0h]
0x14000f97a  test    cl, 40h
0x14000f97d  jnz     loc_14000FE51
0x14000f983  mov     edi, [rbx+164h]
0x14000f989  xor     eax, eax
0x14000f98b  xorps   xmm0, xmm0
0x14000f98e  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000f992  mov     rcx, r12
0x14000f995  mov     [rbp+57h+NextEcpContext], rax
0x14000f999  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000f99d  call    Smb2ReferenceSecurityDescriptor
0x14000f9a2  lea     rcx, [r13+70h]; SpinLock
0x14000f9a6  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14000f9aa  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f9b1  nop     dword ptr [rax+rax+00h]
0x14000f9b6  mov     rax, [r13+198h]
0x14000f9bd  mov     rcx, [rbp+57h+NextEcpContext]
0x14000f9c1  test    rax, rax
0x14000f9c4  movups  xmm0, xmmword ptr [r13+50h]
0x14000f9c9  cmovnz  rcx, rax
0x14000f9cd  mov     byte ptr [r13+0EDh], 1
0x14000f9d5  mov     [rbp+57h+NextEcpContext], rcx
0x14000f9d9  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000f9dd  imul    rdx, rdi, 2710h
0x14000f9e4  movups  xmmword ptr [r13+168h], xmm0
0x14000f9ec  mov     [r13+198h], r12
0x14000f9f3  mov     [r13+178h], rdx
0x14000f9fa  mov     byte ptr [r13+0EEh], 1
0x14000fa02  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000fa09  nop     dword ptr [rax+rax+00h]
0x14000fa0e  mov     rcx, [rbp+57h+NextEcpContext]; P
0x14000fa12  test    rcx, rcx
0x14000fa15  jnz     loc_140010032
0x14000fa1b  mov     rax, [rbx+48h]
0x14000fa1f  xor     edi, edi
0x14000fa21  mov     rcx, [rax+88h]
0x14000fa28  lock inc qword ptr [rcx+1C8h]
0x14000fa30  mov     rax, [rbx+28h]
0x14000fa34  lock inc qword ptr [rax+120h]
0x14000fa3c  mov     rcx, r12; P
0x14000fa3f  call    Smb2DereferenceSecurityDescriptor
0x14000fa44  test    edi, edi
0x14000fa46  js      loc_14000FD32
  ... truncated ...
```
