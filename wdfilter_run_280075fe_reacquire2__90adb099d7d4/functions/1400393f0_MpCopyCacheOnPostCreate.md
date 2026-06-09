# MpCopyCacheOnPostCreate

- ea: `0x1400393f0`
- end: `0x140039f6f`
- name: `MpCopyCacheOnPostCreate`
- size: `2943`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x14002e850`

## callees

- `0x140002450`
- `0x1400026c0`
- `0x140003650`
- `0x140003d20`
- `0x1400051bc`
- `0x140007eec`
- `0x14000e694`
- `0x14000e7d8`
- `0x140011890`
- `0x1400118d0`
- `0x140030060`
- `0x1400393f0`
- `0x140039f70`
- `0x14003a1b0`
- `0x1400444b0`
- `0x140051160`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140039b88`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140039b88`
- `ntoskrnl!PsInitialSystemProcess` at `0x1400396fc`
- `ntoskrnl!PsInitialSystemProcess` at `0x1400398e8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400395eb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140039a98`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400395eb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140039a98`
- `ntoskrnl!IoGetCurrentProcess` at `0x140039449`
- `ntoskrnl!IoGetCurrentProcess` at `0x140039449`
- `ntoskrnl!IoThreadToProcess` at `0x1400396ed`
- `ntoskrnl!IoThreadToProcess` at `0x14003989e`
- `ntoskrnl!IoThreadToProcess` at `0x1400398ca`
- `ntoskrnl!IoThreadToProcess` at `0x1400396ed`
- `ntoskrnl!IoThreadToProcess` at `0x14003989e`
- `ntoskrnl!IoThreadToProcess` at `0x1400398ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400397c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400397c1`
- `FLTMGR!FltReleaseContext` at `0x140039f4e`
- `FLTMGR!FltReleaseContext` at `0x140039f61`
- `FLTMGR!FltReleaseContext` at `0x14008c8ce`
- `FLTMGR!FltReleaseContext` at `0x14008c8e4`
- `FLTMGR!FltReleaseContext` at `0x140039f4e`
- `FLTMGR!FltReleaseContext` at `0x140039f61`
- `FLTMGR!FltReleaseContext` at `0x14008c8ce`
- `FLTMGR!FltReleaseContext` at `0x14008c8e4`
- `FLTMGR!FltAcquirePushLockShared` at `0x140039c5b`
- `FLTMGR!FltAcquirePushLockShared` at `0x140039c5b`
- `FLTMGR!FltReleasePushLock` at `0x140039834`
- `FLTMGR!FltReleasePushLock` at `0x140039aec`
- `FLTMGR!FltReleasePushLock` at `0x140039c93`
- `FLTMGR!FltReleasePushLock` at `0x140039834`
- `FLTMGR!FltReleasePushLock` at `0x140039aec`
- `FLTMGR!FltReleasePushLock` at `0x140039c93`
- `FLTMGR!FltGetFileNameInformation` at `0x14003962a`
- `FLTMGR!FltGetFileNameInformation` at `0x14003962a`
- `FLTMGR!FltGetStreamContext` at `0x140039949`
- `FLTMGR!FltGetStreamContext` at `0x140039949`
- `FLTMGR!FltQueryInformationFile` at `0x1400399e2`
- `FLTMGR!FltQueryInformationFile` at `0x140039a1d`
- `FLTMGR!FltQueryInformationFile` at `0x1400399e2`
- `FLTMGR!FltQueryInformationFile` at `0x140039a1d`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140039648`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140039acb`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140039648`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140039acb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039851`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039851`

## pseudocode

```c
void __fastcall MpCopyCacheOnPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3, void *a4)
{
  int v6; // r13d
  int MpFileStateWithSeq_0; // r12d
  PFLT_CALLBACK_DATA v8; // rdi
  struct _KPROCESS *CurrentProcess; // r14
  ULONG_PTR Information; // rax
  __int64 v11; // r8
  _QWORD *v12; // rdi
  __int64 v13; // r8
  int *v14; // rdx
  __int64 (__fastcall *v15)(_QWORD, PFLT_CALLBACK_DATA, __int64, HANDLE *); // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  bool v19; // r15
  __int64 v20; // r14
  NTSTATUS v21; // eax
  unsigned __int64 *v22; // r12
  __int64 v23; // r9
  __int64 v24; // r10
  unsigned __int64 v25; // r8
  unsigned int v26; // eax
  char v27; // r11
  unsigned int v28; // ecx
  __int64 v29; // rbx
  int v30; // eax
  struct _KPROCESS *v31; // rcx
  char v32; // di
  __int64 v33; // rbx
  PUNICODE_STRING *v34; // rdi
  void *v35; // rcx
  struct _KPROCESS *v36; // rbx
  struct _KPROCESS *v37; // rbx
  __int64 v38; // r14
  __int64 v39; // rcx
  NTSTATUS v40; // eax
  NTSTATUS v41; // eax
  bool v42; // bl
  HANDLE CurrentThreadId; // rdi
  unsigned int v44; // ebx
  __int64 v45; // r14
  UNICODE_STRING *p_Name; // r14
  int v47; // edx
  int v48; // r8d
  __int64 Length; // rsi
  __int64 PoolWithTag; // rax
  __int64 v51; // rcx
  _QWORD *v52; // r8
  int v53; // eax
  unsigned int v54; // eax
  __int64 v55; // r9
  NTSTATUS v56; // [rsp+30h] [rbp-F8h]
  __int64 v57; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v58; // [rsp+40h] [rbp-E8h]
  __int64 v59; // [rsp+48h] [rbp-E0h]
  PFLT_CONTEXT v60; // [rsp+50h] [rbp-D8h] BYREF
  int v61; // [rsp+58h] [rbp-D0h]
  int v62; // [rsp+5Ch] [rbp-CCh]
  __int64 v63; // [rsp+60h] [rbp-C8h]
  __int64 v64; // [rsp+68h] [rbp-C0h]
  __int64 v65; // [rsp+70h] [rbp-B8h]
  __int64 v66; // [rsp+78h] [rbp-B0h]
  PFLT_CONTEXT v67; // [rsp+80h] [rbp-A8h]
  void *v68; // [rsp+88h] [rbp-A0h]
  PFLT_CONTEXT Context; // [rsp+90h] [rbp-98h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+98h] [rbp-90h] BYREF
  HANDLE v71; // [rsp+A0h] [rbp-88h] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp-80h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-70h]
  __int128 v74; // [rsp+C0h] [rbp-68h] BYREF
  __int128 v75; // [rsp+D0h] [rbp-58h]
  __int64 v76; // [rsp+E0h] [rbp-48h]

  v67 = a4;
  v59 = a3;
  v68 = a4;
  Context = a4;
  v6 = 0;
  v60 = 0;
  MpFileStateWithSeq_0 = 0;
  v8 = CallbackData;
  CurrentProcess = IoGetCurrentProcess();
  if ( MpDlpData )
  {
    if ( (unsigned __int64)(&v8[-1].RequestorMode + 7) <= 1 )
      v8 = 0;
    if ( *((_BYTE *)MpDlpData + 32) )
    {
      if ( (*(_DWORD *)(MpData + 864) & 0x400) != 0 )
      {
        if ( *(_QWORD *)(MpData + 320) || *(_QWORD *)(MpData + 336) )
        {
          v36 = *(struct _KPROCESS **)(MpData + 232);
          if ( IoThreadToProcess(KeGetCurrentThread()) == v36
            || (v37 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v37) )
          {
            LOBYTE(CurrentProcess) = (unsigned __int64)(&CallbackData[-1].RequestorMode + 7) <= 1;
          }
          else if ( !v8 || (CurrentProcess = (struct _KPROCESS *)MpGetRequestorProcess(v8)) != 0 )
          {
            if ( PsInitialSystemProcess != CurrentProcess
              || (unsigned __int8)MpIsPotentialRemoteOpen(v8)
              || CallbackData == (PFLT_CALLBACK_DATA)2 )
            {
              v38 = v59;
              v39 = v59;
              v57 = v59;
              if ( !v59 )
              {
                if ( !v8 )
                  goto LABEL_68;
                if ( (int)MpDlpGetAccessCheckProcessContext(v8, &v57) < 0 )
                  goto LABEL_68;
                v39 = v57;
                if ( !v57 )
                  goto LABEL_68;
              }
              v42 = (*(_DWORD *)(v39 + 56) & 0x40000000) != 0 || *(_DWORD *)(v39 + 240) == 33;
              if ( v39 != v38 )
                MpReleaseProcessContext(v39);
              if ( v42 )
                LOBYTE(CurrentProcess) = 0;
              else
LABEL_68:
                LOBYTE(CurrentProcess) = 1;
            }
            else
            {
              LOBYTE(CurrentProcess) = 0;
            }
          }
        }
        else
        {
          LOBYTE(CurrentProcess) = 0;
        }
      }
      else
      {
        LOBYTE(CurrentProcess) = 0;
      }
    }
    else
    {
      LOBYTE(CurrentProcess) = 0;
    }
  }
  else
  {
    LOBYTE(CurrentProcess) = 0;
  }
  if ( v59 )
  {
    v30 = *(_DWORD *)(v59 + 52);
    if ( (v30 & 1) != 0 )
      goto LABEL_44;
    if ( (v30 & 0x4000) != 0 )
    {
      v31 = IoThreadToProcess(KeGetCurrentThread());
      if ( v31 != PsInitialSystemProcess )
      {
        v58 = 0;
        if ( (int)MpGetProcessContextByObject(v31) >= 0 )
        {
          v32 = 0;
          v33 = v58;
          if ( (*(_DWORD *)(v58 + 52) & 1) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                17,
                WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids,
                KeGetCurrentThread(),
                *(_DWORD *)(v58 + 24));
            }
            v32 = 1;
          }
          MpReleaseProcessContext(v33);
          if ( v32 )
          {
LABEL_44:
            if ( !(_BYTE)CurrentProcess )
              goto LABEL_142;
          }
        }
      }
    }
  }
  if ( !Context && FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) < 0
    || (*((_DWORD *)Context + 12) & 1) != 0
    || *(_DWORD *)(*((_QWORD *)Context + 1) + 100LL) )
  {
    goto LABEL_142;
  }
  Information = CallbackData->IoStatus.Information;
  if ( Information == 2 || Information == 3 )
  {
    CurrentThreadId = PsGetCurrentThreadId();
    v44 = dword_1400269EC;
    v62 = dword_1400269EC;
    v45 = v59;
    if ( *(_QWORD *)(v59 + 264) )
    {
      FltAcquirePushLockExclusive((PULONG_PTR)(v59 + 272));
      if ( *(_QWORD *)(v45 + 264) )
      {
        while ( 1 )
        {
          v54 = v44--;
          v62 = v44;
          if ( !v54 )
            break;
          v55 = *(_QWORD *)(v45 + 264) + 56LL * v44;
          if ( (*(_DWORD *)v55 & 1) != 0 && *(HANDLE *)(v55 + 8) == CurrentThreadId )
          {
            *(_DWORD *)v55 |= 2u;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_qI(WPP_GLOBAL_Control->AttachedDevice, 12);
            }
          }
        }
      }
      FltReleasePushLock((PULONG_PTR)(v45 + 272));
    }
    goto LABEL_142;
  }
  if ( *((__int64 *)Context + 22) <= 4 )
    goto LABEL_142;
  v11 = *(_QWORD *)(a2 + 40);
  if ( v11 )
  {
    if ( (int)MpTxfGetContext(a2, 0, v11, &v60) < 0 )
      goto LABEL_142;
  }
  v12 = Context;
  if ( !v60 )
  {
    v13 = *((_QWORD *)Context + 1);
    v14 = (int *)((char *)Context + 32);
    if ( Context != (PFLT_CONTEXT)-32LL && v13 )
    {
      if ( *v14 != 5 || (*(_DWORD *)(MpData + 868) & 0x8000) != 0 )
      {
        if ( *((_DWORD *)Context + 9) == *(_DWORD *)(v13 + 144) )
          MpFileStateWithSeq_0 = *v14;
        else
          MpFileStateWithSeq_0 = 0;
      }
      else
      {
        MpFileStateWithSeq_0 = 5;
      }
      goto LABEL_20;
    }
    goto LABEL_102;
  }
  if ( (*((_DWORD *)v60 + 42) & 1) == 0 )
  {
    if ( (unsigned __int16)(*(_WORD *)(a2 + 2) - 1) > 0xFFFCu )
    {
      FltAcquirePushLockShared((PULONG_PTR)Context + 24);
      v51 = v12[26];
      v52 = (_QWORD *)(v51 + 24);
      if ( !v51 )
        v52 = v12 + 4;
      MpFileStateWithSeq_0 = GetMpFileStateWithSeq_0(v52, v12[1]);
      FltReleasePushLock(v12 + 24);
      goto LABEL_20;
    }
LABEL_102:
    MpFileStateWithSeq_0 = 0;
  }
LABEL_20:
  if ( MpFileStateWithSeq_0 == 4 && !(_BYTE)CurrentProcess )
    goto LABEL_142;
  v64 = 0;
  v63 = 0;
  v15 = *(__int64 (__fastcall **)(_QWORD, PFLT_CALLBACK_DATA, __int64, HANDLE *))(MpData + 96);
  if ( v15 )
  {
    LODWORD(v71) = 0;
    v16 = v15(*(_QWORD *)(MpData + 16), CallbackData, 1, &v71);
    if ( v16 )
    {
      v17 = *(_QWORD *)(v16 + 48);
      v64 = v17;
      v18 = *(_QWORD *)(v16 + 24);
      v63 = v18;
      v56 = 0;
LABEL_24:
      v58 = v17;
      v57 = v18;
      if ( !v17 )
        goto LABEL_142;
      v19 = (*((_DWORD *)Context + 12) & 0x200000) != 0;
      v71 = PsGetCurrentThreadId();
      FileNameInformation = 0;
      v20 = v59;
      if ( !*(_QWORD *)(v59 + 264) )
        goto LABEL_142;
      v21 = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
      if ( v21 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_cdc8c5bdf4153e2541ef4ccbc66457af_Traceguids,
          KeGetCurrentThread(),
          v21);
      }
      v22 = (unsigned __int64 *)(v20 + 272);
      FltAcquirePushLockExclusive((PULONG_PTR)(v20 + 272));
      v23 = *(_QWORD *)(v20 + 264);
      if ( !v23 )
        goto LABEL_57;
      v24 = 0;
      v66 = 0;
      v25 = -1;
      v65 = -1;
      v26 = dword_1400269EC;
      v61 = dword_1400269EC;
      v27 = 0;
      while ( 1 )
      {
        v28 = v26--;
        v61 = v26;
        if ( !v28 )
          break;
        v29 = v23 + 56LL * v26;
        if ( (*(_DWORD *)v29 & 1) == 0 )
          goto LABEL_47;
        if ( *(_QWORD *)(v29 + 40) < v25 )
        {
          v25 = *(_QWORD *)(v29 + 40);
          v65 = v25;
          v24 = v23 + 56LL * v26;
          v66 = v24;
        }
      }
      v27 = 1;
      v29 = v24;
LABEL_47:
      if ( !v29 )
        goto LABEL_57;
      if ( v27 )
      {
        _InterlockedIncrement(&dword_140026A4C);
        _InterlockedIncrement(&dword_140026A48);
        if ( (*(_DWORD *)v29 & 0xFFFFFFFE) != 0 )
          _InterlockedIncrement(&dword_140026A50);
        if ( (*(_BYTE *)v29 & 0xF) == 0xF )
          _InterlockedIncrement(&dword_140026AC0);
      }
      v34 = (PUNICODE_STRING *)(v29 + 16);
      v35 = *(void **)(v29 + 16);
      if ( v35 )
      {
        ExFreePoolWithTag(v35, 0x7375704Du);
        *v34 = 0;
      }
      *(_OWORD *)v29 = 0;
      *(_OWORD *)(v29 + 16) = 0;
      *(_OWORD *)(v29 + 32) = 0;
      *(_QWORD *)(v29 + 48) = 0;
      *(_QWORD *)(v29 + 8) = v71;
      *(_QWORD *)(v29 + 24) = v58;
      *(_QWORD *)(v29 + 32) = v57;
      *(_BYTE *)(v29 + 48) = v19;
      *(_QWORD *)(v29 + 40) = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(v20 + 280));
      if ( !FileNameInformation
        || (p_Name = &FileNameInformation->Name, FileNameInformation == (PFLT_FILE_NAME_INFORMATION)-8LL)
        || v29 == -16
        || RtlUnicodeStringValidateWorker(&FileNameInformation->Name, 0x7FFFu, 0) < 0 )
      {
LABEL_56:
        *(_DWORD *)v29 = 1;
LABEL_57:
        FltReleasePushLock(v22);
        if ( FileNameInformation )
          FltReleaseFileNameInformation(FileNameInformation);
        goto LABEL_142;
      }
      Length = p_Name->Length;
      if ( !(_WORD)Length || (Length & 1) != 0 )
      {
        v53 = -1073741811;
      }
      else
      {
        PoolWithTag = MpAllocatePoolWithTag(1, Length + 18, 1937076301);
        *v34 = (PUNICODE_STRING)PoolWithTag;
        if ( PoolWithTag )
        {
          *(_QWORD *)(PoolWithTag + 8) = PoolWithTag + 16;
          (*v34)->Length = 0;
          (*v34)->MaximumLength = Length + 2;
          _mm_lfence();
          RtlCopyUnicodeString(*v34, p_Name);
LABEL_94:
          if ( v6 >= 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_qZI(WPP_GLOBAL_Control->AttachedDevice, v47, v48, v29, (__int64)*v34, *(_QWORD *)(v29 + 24), v56);
          }
          goto LABEL_56;
        }
        v53 = -1073741670;
      }
      v6 = v53;
      goto LABEL_94;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        116,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        KeGetCurrentThread());
  }
  v74 = 0;
  v75 = 0;
  v76 = 0;
  FileInformation = 0;
  v73 = 0;
  v40 = FltQueryInformationFile(
          *(PFLT_INSTANCE *)(a2 + 24),
          *(PFILE_OBJECT *)(a2 + 32),
          &FileInformation,
          0x18u,
          FileStandardInformation,
          0);
  if ( v40 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        117,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        KeGetCurrentThread(),
        v40);
    }
  }
  else
  {
    v41 = FltQueryInformationFile(
            *(PFLT_INSTANCE *)(a2 + 24),
            *(PFILE_OBJECT *)(a2 + 32),
            &v74,
            0x28u,
            FileBasicInformation,
            0);
    v56 = v41;
    if ( v41 >= 0 )
    {
      v18 = v75;
      v63 = v75;
      v17 = *((_QWORD *)&FileInformation + 1);
      v64 = *((_QWORD *)&FileInformation + 1);
      goto LABEL_24;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        118,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        KeGetCurrentThread(),
        v41);
    }
  }
LABEL_142:
  if ( Context != v67 && Context )
    FltReleaseContext(Context);
  if ( v60 )
    FltReleaseContext(v60);
}

```

## disassembly

```asm
0x1400393f0  push    rbx
0x1400393f2  push    rsi
0x1400393f3  push    rdi
0x1400393f4  push    r12
0x1400393f6  push    r13
0x1400393f8  push    r14
0x1400393fa  push    r15
0x1400393fc  sub     rsp, 0F0h
0x140039403  mov     rax, cs:__security_cookie
0x14003940a  xor     rax, rsp
0x14003940d  mov     [rsp+128h+var_40], rax
0x140039415  mov     rax, r9
0x140039418  mov     [rsp+128h+var_A8], rax
0x140039420  mov     [rsp+128h+var_E0], r8
0x140039425  mov     r15, rdx
0x140039428  mov     rsi, rcx
0x14003942b  mov     [rsp+128h+var_A0], rax
0x140039433  mov     [rsp+128h+Context], rax
0x14003943b  xor     r13d, r13d
0x14003943e  mov     [rsp+128h+var_D8], r13
0x140039443  mov     r12d, r13d
0x140039446  mov     rdi, rcx
0x140039449  call    cs:__imp_IoGetCurrentProcess
0x140039450  nop     dword ptr [rax+rax+00h]
0x140039455  mov     r14, rax
0x140039458  mov     rcx, cs:MpDlpData
0x14003945f  test    rcx, rcx
0x140039462  jz      loc_140039DD5
0x140039468  lea     rax, [rdi-1]
0x14003946c  cmp     rax, 1
0x140039470  jbe     loc_140039D50
0x140039476  movzx   eax, byte ptr [rcx+20h]
0x14003947a  test    al, al
0x14003947c  jnz     loc_140039862
0x140039482  xor     r14b, r14b
0x140039485  mov     rcx, [rsp+128h+var_E0]
0x14003948a  test    rcx, rcx
0x14003948d  jnz     loc_1400396CF
0x140039493  cmp     [rsp+128h+Context], 0
0x14003949c  jz      loc_140039939
0x1400394a2  mov     rcx, [rsp+128h+Context]
0x1400394aa  mov     eax, [rcx+30h]
0x1400394ad  test    al, 1
0x1400394af  jnz     loc_140039F0B
0x1400394b5  mov     rax, [rcx+8]
0x1400394b9  cmp     dword ptr [rax+64h], 0
0x1400394bd  jnz     loc_140039F0B
0x1400394c3  mov     rax, [rsi+20h]
0x1400394c7  cmp     rax, 2
0x1400394cb  jz      loc_140039A98
0x1400394d1  cmp     rax, 3
0x1400394d5  jz      loc_140039A98
0x1400394db  cmp     qword ptr [rcx+0B0h], 4
0x1400394e3  jle     loc_140039F0B
0x1400394e9  mov     r8, [r15+28h]
0x1400394ed  test    r8, r8
0x1400394f0  jnz     loc_140039CC6
0x1400394f6  mov     rdi, [rsp+128h+Context]
0x1400394fe  movzx   ecx, word ptr [r15+2]
0x140039503  mov     rax, [rsp+128h+var_D8]
0x140039508  test    rax, rax
0x14003950b  jnz     loc_140039C39
0x140039511  mov     r8, [rdi+8]
0x140039515  lea     rdx, [rdi+20h]
0x140039519  test    rdx, rdx
0x14003951c  jz      loc_140039C08
0x140039522  test    r8, r8
0x140039525  jz      loc_140039C08
0x14003952b  cmp     dword ptr [rdx], 5
0x14003952e  jz      loc_140039C10
0x140039534  mov     eax, [r8+90h]
0x14003953b  cmp     [rdx+4], eax
0x14003953e  jnz     loc_140039966
0x140039544  mov     r12d, [rdx]
0x140039547  cmp     r12d, 4
0x14003954b  jz      loc_140039BFA
0x140039551  mov     [rsp+128h+var_F8], 0C0000001h
0x140039559  mov     [rsp+128h+var_C0], r13
0x14003955e  mov     [rsp+128h+var_C8], r13
0x140039563  mov     [rsp+128h+var_C0], r13
0x140039568  mov     [rsp+128h+var_C8], r13
0x14003956d  mov     rcx, cs:MpData
0x140039574  mov     rax, [rcx+60h]
0x140039578  test    rax, rax
0x14003957b  jz      loc_14003998B
0x140039581  mov     dword ptr [rsp+128h+var_88], r13d
0x140039589  lea     r9, [rsp+128h+var_88]
0x140039591  mov     r8d, 1
0x140039597  mov     rdx, rsi
0x14003959a  mov     rcx, [rcx+10h]
0x14003959e  call    cs:__guard_dispatch_icall_fptr
0x1400395a4  test    rax, rax
0x1400395a7  jz      loc_140039CE6
0x1400395ad  mov     rcx, [rax+30h]
0x1400395b1  mov     [rsp+128h+var_C0], rcx
0x1400395b6  mov     rax, [rax+18h]
0x1400395ba  mov     [rsp+128h+var_C8], rax
0x1400395bf  mov     [rsp+128h+var_F8], r13d
0x1400395c4  mov     [rsp+128h+var_E8], rcx
0x1400395c9  mov     [rsp+128h+var_F0], rax
0x1400395ce  test    rcx, rcx
0x1400395d1  jz      loc_140039F0B
0x1400395d7  mov     rax, [rsp+128h+Context]
0x1400395df  mov     r15d, [rax+30h]
0x1400395e3  shr     r15d, 15h
0x1400395e7  and     r15b, 1
0x1400395eb  call    cs:__imp_PsGetCurrentThreadId
0x1400395f2  nop     dword ptr [rax+rax+00h]
0x1400395f7  mov     [rsp+128h+var_88], rax
0x1400395ff  mov     [rsp+128h+FileNameInformation], r13
0x140039607  mov     r14, [rsp+128h+var_E0]
0x14003960c  cmp     qword ptr [r14+108h], 0
0x140039614  jz      loc_140039F0B
0x14003961a  lea     r8, [rsp+128h+FileNameInformation]; FileNameInformation
0x140039622  mov     edx, 102h; NameOptions
0x140039627  mov     rcx, rsi; CallbackData
0x14003962a  call    cs:__imp_FltGetFileNameInformation
0x140039631  nop     dword ptr [rax+rax+00h]
0x140039636  test    eax, eax
0x140039638  js      loc_140039EAD
0x14003963e  lea     r12, [r14+110h]
0x140039645  mov     rcx, r12; PushLock
0x140039648  call    cs:__imp_FltAcquirePushLockExclusive
0x14003964f  nop     dword ptr [rax+rax+00h]
0x140039654  mov     r9, [r14+108h]
0x14003965b  test    r9, r9
0x14003965e  jz      loc_140039831
0x140039664  mov     r10, r13
0x140039667  mov     [rsp+128h+var_B0], r13
0x14003966c  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140039673  mov     [rsp+128h+var_B8], r8
0x140039678  mov     eax, cs:dword_1400269EC
0x14003967e  mov     [rsp+128h+var_D0], eax
0x140039682  xor     r11b, r11b
0x140039685  nop     word ptr [rax+rax+00000000h]
0x140039690  mov     ecx, eax
0x140039692  dec     eax
0x140039694  mov     [rsp+128h+var_D0], eax
0x140039698  test    ecx, ecx
0x14003969a  jz      loc_140039772
0x1400396a0  mov     ecx, eax
0x1400396a2  imul    rbx, rcx, 38h ; '8'
0x1400396a6  add     rbx, r9
0x1400396a9  mov     ecx, [rbx]
0x1400396ab  test    cl, 1
0x1400396ae  jz      loc_140039778
0x1400396b4  mov     rcx, [rbx+28h]
0x1400396b8  cmp     rcx, r8
0x1400396bb  jnb     short loc_1400396CD
0x1400396bd  mov     r8, rcx
0x1400396c0  mov     [rsp+128h+var_B8], rcx
0x1400396c5  mov     r10, rbx
0x1400396c8  mov     [rsp+128h+var_B0], rbx
0x1400396cd  jmp     short loc_140039690
0x1400396cf  mov     eax, [rcx+34h]
0x1400396d2  test    al, 1
0x1400396d4  jnz     loc_140039764
0x1400396da  bt      eax, 0Eh
0x1400396de  jnb     loc_140039493
0x1400396e4  mov     rcx, gs:188h; Thread
0x1400396ed  call    cs:__imp_IoThreadToProcess
0x1400396f4  nop     dword ptr [rax+rax+00h]
0x1400396f9  mov     rcx, rax; Process
0x1400396fc  mov     rax, cs:__imp_PsInitialSystemProcess
0x140039703  cmp     rcx, [rax]
0x140039706  jz      loc_140039493
0x14003970c  mov     [rsp+128h+var_E8], r13
0x140039711  lea     rdx, [rsp+128h+var_E8]
0x140039716  call    MpGetProcessContextByObject
0x14003971b  test    eax, eax
0x14003971d  js      loc_140039493
0x140039723  xor     dil, dil
0x140039726  mov     rbx, [rsp+128h+var_E8]
0x14003972b  mov     eax, [rbx+34h]
0x14003972e  test    al, 1
0x140039730  jz      short loc_140039753
0x140039732  lea     rcx, WPP_GLOBAL_Control
0x140039739  mov     rax, cs:WPP_GLOBAL_Control
0x140039740  cmp     rax, rcx
0x140039743  jz      short loc_140039750
0x140039745  mov     eax, [rax+2Ch]
0x140039748  test    al, 4
0x14003974a  jnz     loc_140039DE5
0x140039750  mov     dil, 1
0x140039753  mov     rcx, rbx
0x140039756  call    MpReleaseProcessContext
0x14003975b  test    dil, dil
0x14003975e  jz      loc_140039493
0x140039764  test    r14b, r14b
0x140039767  jz      loc_140039F0B
0x14003976d  jmp     loc_140039493
0x140039772  mov     r11b, 1
0x140039775  mov     rbx, r10
0x140039778  test    rbx, rbx
0x14003977b  jz      loc_140039831
0x140039781  test    r11b, r11b
0x140039784  jz      short loc_1400397B0
0x140039786  lock inc cs:dword_140026A4C
0x14003978d  lock inc cs:dword_140026A48
0x140039794  test    dword ptr [rbx], 0FFFFFFFEh
0x14003979a  jnz     loc_14003996E
0x1400397a0  mov     eax, [rbx]
0x1400397a2  and     eax, 0Fh
0x1400397a5  cmp     al, 0Fh
0x1400397a7  jnz     short loc_1400397B0
0x1400397a9  lock inc cs:dword_140026AC0
0x1400397b0  lea     rdi, [rbx+10h]
0x1400397b4  mov     rcx, [rdi]; P
0x1400397b7  test    rcx, rcx
0x1400397ba  jz      short loc_1400397D0
0x1400397bc  mov     edx, 7375704Dh; Tag
0x1400397c1  call    cs:__imp_ExFreePoolWithTag
0x1400397c8  nop     dword ptr [rax+rax+00h]
0x1400397cd  mov     [rdi], r13
0x1400397d0  xorps   xmm0, xmm0
0x1400397d3  xor     eax, eax
0x1400397d5  movups  xmmword ptr [rbx], xmm0
0x1400397d8  movups  xmmword ptr [rbx+10h], xmm0
0x1400397dc  movups  xmmword ptr [rbx+20h], xmm0
0x1400397e0  mov     [rbx+30h], rax
0x1400397e4  mov     rax, [rsp+128h+var_88]
0x1400397ec  mov     [rbx+8], rax
0x1400397f0  mov     rax, [rsp+128h+var_E8]
0x1400397f5  mov     [rbx+18h], rax
0x1400397f9  mov     rax, [rsp+128h+var_F0]
0x1400397fe  mov     [rbx+20h], rax
0x140039802  mov     [rbx+30h], r15b
0x140039806  mov     eax, 1
0x14003980b  lock xadd [r14+118h], eax
0x140039814  inc     eax
0x140039816  mov     [rbx+28h], rax
0x14003981a  mov     rax, [rsp+128h+FileNameInformation]
0x140039822  test    rax, rax
0x140039825  jnz     loc_140039AFD
0x14003982b  mov     dword ptr [rbx], 1
0x140039831  mov     rcx, r12; PushLock
0x140039834  call    cs:__imp_FltReleasePushLock
0x14003983b  nop     dword ptr [rax+rax+00h]
0x140039840  mov     rcx, [rsp+128h+FileNameInformation]; FileNameInformation
0x140039848  test    rcx, rcx
0x14003984b  jz      loc_140039F0B
0x140039851  call    cs:__imp_FltReleaseFileNameInformation
0x140039858  nop     dword ptr [rax+rax+00h]
0x14003985d  jmp     loc_140039F0B
0x140039862  mov     rcx, cs:MpData
0x140039869  test    dword ptr [rcx+360h], 400h
0x140039873  jz      loc_140039DDD
0x140039879  cmp     qword ptr [rcx+140h], 0
0x140039881  jz      loc_140039D3A
0x140039887  mov     rcx, gs:188h; Thread
0x140039890  mov     rax, cs:MpData
0x140039897  mov     rbx, [rax+0E8h]
0x14003989e  call    cs:__imp_IoThreadToProcess
0x1400398a5  nop     dword ptr [rax+rax+00h]
0x1400398aa  cmp     rax, rbx
0x1400398ad  jz      loc_14003997A
0x1400398b3  mov     rcx, gs:188h; Thread
0x1400398bc  mov     rax, cs:MpData
0x1400398c3  mov     rbx, [rax+100h]
0x1400398ca  call    cs:__imp_IoThreadToProcess
0x1400398d1  nop     dword ptr [rax+rax+00h]
0x1400398d6  cmp     rax, rbx
0x1400398d9  jz      loc_14003997A
0x1400398df  test    rdi, rdi
0x1400398e2  jnz     loc_140039BE1
0x1400398e8  mov     rax, cs:__imp_PsInitialSystemProcess
0x1400398ef  cmp     [rax], r14
0x1400398f2  jz      loc_140039CA4
0x1400398f8  mov     r14, [rsp+128h+var_E0]
0x1400398fd  mov     rcx, r14
0x140039900  mov     [rsp+128h+var_F0], rcx
0x140039905  test    r14, r14
0x140039908  jnz     loc_140039A62
0x14003990e  test    rdi, rdi
0x140039911  jz      short loc_140039931
0x140039913  test    r14, r14
0x140039916  jnz     loc_140039A62
0x14003991c  lea     rdx, [rsp+128h+var_F0]
0x140039921  mov     rcx, rdi
0x140039924  call    MpDlpGetAccessCheckProcessContext
0x140039929  test    eax, eax
0x14003992b  jns     loc_140039A54
0x140039931  mov     r14b, 1
0x140039934  jmp     loc_140039485
0x140039939  lea     r8, [rsp+128h+Context]; Context
0x140039941  mov     rdx, [r15+20h]; FileObject
0x140039945  mov     rcx, [r15+18h]; Instance
0x140039949  call    cs:__imp_FltGetStreamContext
0x140039950  nop     dword ptr [rax+rax+00h]
0x140039955  mov     [rsp+128h+var_F8], eax
0x140039959  test    eax, eax
0x14003995b  jns     loc_1400394A2
0x140039961  jmp     loc_140039F0B
0x140039966  mov     r12d, r13d
0x140039969  jmp     loc_140039547
0x14003996e  lock inc cs:dword_140026A50
0x140039975  jmp     loc_1400397A0
0x14003997a  lea     rax, [rsi-1]
0x14003997e  cmp     rax, 1
0x140039982  setbe   r14b
  ... truncated ...
```
