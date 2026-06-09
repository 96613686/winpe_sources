# MpDlpPreAcquireSectionSync

- ea: `0x14003f700`
- end: `0x14003fe62`
- name: `MpDlpPreAcquireSectionSync`
- size: `1890`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14002da90`

## callees

- `0x140002450`
- `0x1400024ac`
- `0x1400051bc`
- `0x1400118d0`
- `0x14002fe00`
- `0x140030060`
- `0x14003f700`
- `0x1400408b0`
- `0x1400444b0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14003f77b`
- `ntoskrnl!PsGetProcessId` at `0x14003f77b`
- `ntoskrnl!PsInitialSystemProcess` at `0x14003f8ea`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003f769`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003f769`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f819`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fdf4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f819`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fdf4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003f80d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fde8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003f80d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fde8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003f7af`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003f7af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f79d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003f79d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003f828`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003f828`
- `ntoskrnl!IoThreadToProcess` at `0x14003f8a0`
- `ntoskrnl!IoThreadToProcess` at `0x14003f8cc`
- `ntoskrnl!IoThreadToProcess` at `0x14003f8a0`
- `ntoskrnl!IoThreadToProcess` at `0x14003f8cc`
- `FLTMGR!FltReleaseContext` at `0x14003fa87`
- `FLTMGR!FltReleaseContext` at `0x14003fa87`
- `FLTMGR!FltReleasePushLock` at `0x14003fa4d`
- `FLTMGR!FltReleasePushLock` at `0x14003fa64`
- `FLTMGR!FltReleasePushLock` at `0x14003fb99`
- `FLTMGR!FltReleasePushLock` at `0x14003fc18`
- `FLTMGR!FltReleasePushLock` at `0x14003fa4d`
- `FLTMGR!FltReleasePushLock` at `0x14003fa64`
- `FLTMGR!FltReleasePushLock` at `0x14003fb99`
- `FLTMGR!FltReleasePushLock` at `0x14003fc18`
- `FLTMGR!FltGetFileNameInformation` at `0x14003fae5`
- `FLTMGR!FltGetFileNameInformation` at `0x14003fcc3`
- `FLTMGR!FltGetFileNameInformation` at `0x14003fae5`
- `FLTMGR!FltGetFileNameInformation` at `0x14003fcc3`
- `FLTMGR!FltGetStreamHandleContext` at `0x14003f91d`
- `FLTMGR!FltGetStreamHandleContext` at `0x14003f91d`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14003f9aa`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14003fa0f`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14003fb51`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14003fbd4`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14003f9aa`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14003fa0f`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14003fb51`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14003fbd4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003fc30`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003fc30`

## pseudocode

```c
__int64 __fastcall MpDlpPreAcquireSectionSync(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
{
  unsigned int v3; // esi
  struct _KPROCESS *RequestorProcess; // rax
  struct _KPROCESS *v8; // rbx
  LONGLONG TimeQuadPart; // r12
  __int64 v10; // r13
  unsigned __int64 ProcessId; // rbp
  char *v12; // rbx
  _QWORD *v13; // r8
  _QWORD *i; // rax
  __int64 v15; // rsi
  PFLT_CALLBACK_DATA v16; // rbp
  struct _KPROCESS *CurrentProcess; // r12
  struct _KPROCESS *v18; // rbx
  struct _KPROCESS *v19; // rbx
  bool v20; // zf
  _QWORD *v21; // rax
  _QWORD *v22; // rdx
  __int64 v23; // rbp
  _QWORD *v24; // r14
  _QWORD *v25; // rbx
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v29; // rbp
  FLT_FILE_NAME_OPTIONS v30; // edx
  NTSTATUS v31; // ecx
  UNICODE_STRING *p_Name; // rdx
  _QWORD *v33; // rbx
  char *v34; // rax
  PVOID *v35; // rcx
  UNICODE_STRING *v36; // r14
  __int64 v37; // r15
  _QWORD *v38; // rbx
  _QWORD *v39; // rax
  _QWORD *v40; // rcx
  _QWORD *v41; // rcx
  _QWORD *v42; // rax
  _QWORD *v43; // rdx
  _QWORD *v44; // rax
  size_t Size; // [rsp+38h] [rbp-80h]
  unsigned int v46; // [rsp+50h] [rbp-68h]
  _QWORD *v47; // [rsp+58h] [rbp-60h] BYREF
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-58h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-50h] BYREF

  v3 = 0;
  Context = 0;
  v46 = 0;
  if ( (*(_DWORD *)(MpData + 864) & 0x2000) != 0
    && (CallbackData->Iopb->Parameters.Read.ByteOffset.HighPart & 0x1000000) != 0 )
  {
    return v3;
  }
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(CallbackData);
  v8 = RequestorProcess;
  if ( RequestorProcess )
  {
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
    v10 = 0;
    ProcessId = (unsigned __int64)PsGetProcessId(v8);
    if ( !ProcessId )
    {
LABEL_90:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_a67f6715d69b338c18208b3d25efa3ca_Traceguids,
            KeGetCurrentThread(),
            -1073741275);
        }
LABEL_38:
        if ( v10 )
          MpReleaseProcessContext(v10);
      }
      if ( Context )
        FltReleaseContext(Context);
      return v3;
    }
    v12 = (char *)MpProcessTable;
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)(v12 + 8), 1u);
    v13 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
    for ( i = (_QWORD *)*v13; ; i = (_QWORD *)*i )
    {
      if ( i == v13 )
      {
        ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
        KeLeaveCriticalRegion();
        v3 = 0;
        goto LABEL_90;
      }
      v15 = (__int64)(i - 1);
      if ( ProcessId == i[2] && TimeQuadPart == *(_QWORD *)(v15 + 32) )
        break;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 48));
    ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
    KeLeaveCriticalRegion();
    v16 = CallbackData;
    v10 = v15;
    CurrentProcess = IoGetCurrentProcess();
    if ( !MpDlpData )
      goto LABEL_37;
    if ( (unsigned __int64)(&CallbackData[-1].RequestorMode + 7) <= 1 )
      v16 = 0;
    if ( !*((_BYTE *)MpDlpData + 32)
      || (*(_DWORD *)(MpData + 864) & 0x400) == 0
      || !*(_QWORD *)(MpData + 320) && !*(_QWORD *)(MpData + 336) )
    {
LABEL_37:
      v3 = v46;
      goto LABEL_38;
    }
    v18 = *(struct _KPROCESS **)(MpData + 232);
    if ( IoThreadToProcess(KeGetCurrentThread()) == v18
      || (v19 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v19) )
    {
      if ( CallbackData != (PFLT_CALLBACK_DATA)1 )
      {
        v10 = v15;
        v20 = CallbackData == (PFLT_CALLBACK_DATA)2;
        goto LABEL_20;
      }
    }
    else
    {
      if ( v16 )
      {
        CurrentProcess = (struct _KPROCESS *)MpGetRequestorProcess(v16);
        v10 = v15;
        if ( !CurrentProcess )
          goto LABEL_37;
      }
      if ( PsInitialSystemProcess == CurrentProcess && !(unsigned __int8)MpIsPotentialRemoteOpen(v16) )
      {
        v10 = v15;
        if ( CallbackData != (PFLT_CALLBACK_DATA)2 )
          goto LABEL_37;
      }
      v10 = v15;
      v20 = !MpDlpIsProcessExcluded((__int64)v16, (_QWORD *)v15);
LABEL_20:
      if ( !v20 )
        goto LABEL_37;
    }
    if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
    {
      v10 = v15;
      if ( (*((_DWORD *)Context + 10) & 0x40) == 0 )
        goto LABEL_37;
      _InterlockedOr((volatile signed __int32 *)Context + 10, 0x20u);
      LODWORD(Size) = 0;
      v46 = MpDlpCheckFileAccess(
              CallbackData,
              a2,
              v15,
              *(_DWORD *)(*(_QWORD *)(a3 + 8) + 84LL),
              a3,
              Context,
              0,
              Size,
              0,
              0);
      if ( v46 == 2 )
      {
        v3 = 2;
        CallbackData->IoStatus.Status = dword_140026538;
        CallbackData->IoStatus.Information = 0;
        goto LABEL_38;
      }
      if ( (*(_DWORD *)(a3 + 48) & 0x40000) != 0 )
      {
        FltAcquirePushLockExclusive((PULONG_PTR)MpDlpData + 1);
        v21 = (_QWORD *)*((_QWORD *)MpDlpData + 2);
        do
        {
          if ( v21 == (_QWORD *)((char *)MpDlpData + 16) )
            goto LABEL_36;
          v22 = v21;
          v21 = (_QWORD *)*v21;
        }
        while ( v22[3] != a3 );
        *((_DWORD *)v22 + 4) &= ~1u;
        v22[6] = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 40LL);
        if ( !*(_BYTE *)(v15 + 224) )
        {
          v23 = *(_QWORD *)(a2 + 32);
          v24 = v22 + 4;
          if ( v22 != (_QWORD *)-32LL && (*(_DWORD *)(a3 + 48) & 0x10000) != 0 )
          {
            FltAcquirePushLockExclusive((PULONG_PTR)(v15 + 200));
            v25 = (_QWORD *)(v15 + 208);
            v26 = *(_QWORD **)(v15 + 208);
            while ( v26 != v25 )
            {
              v27 = v26;
              v26 = (_QWORD *)*v26;
              if ( v27[3] == a3 )
              {
                *((_DWORD *)v27 + 4) &= ~1u;
                v27[6] = *(_QWORD *)(v23 + 40);
                goto LABEL_35;
              }
            }
            v47 = 0;
            if ( (int)MpCreateDlpSectionFileNameEntry(a3, v24, &v47) >= 0 )
            {
              v41 = v47;
              if ( v47 )
              {
                v47[6] = *(_QWORD *)(v23 + 40);
                v42 = *(_QWORD **)(v15 + 216);
                if ( (_QWORD *)*v42 == v25 )
                {
                  *v41 = v25;
                  v41[1] = v42;
                  *v42 = v41;
                  *(_QWORD *)(v15 + 216) = v41;
                  goto LABEL_35;
                }
LABEL_72:
                __fastfail(3u);
              }
            }
LABEL_35:
            FltReleasePushLock((PULONG_PTR)(v15 + 200));
          }
        }
LABEL_36:
        FltReleasePushLock((PULONG_PTR)MpDlpData + 1);
        goto LABEL_37;
      }
      v29 = 0;
      v47 = 0;
      v30 = 513;
      FileNameInformation = 0;
      if ( !byte_1400269F8 && (*(_DWORD *)(*(_QWORD *)(a3 + 8) + 84LL) & 0x11) == 0 )
        v30 = 257;
      v31 = FltGetFileNameInformation(CallbackData, v30, &FileNameInformation);
      if ( v31 < 0 )
      {
        _mm_lfence();
        v31 = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
      }
      if ( FileNameInformation )
        v29 = FileNameInformation;
      p_Name = &v29->Name;
      if ( v31 < 0 )
        p_Name = (UNICODE_STRING *)(a3 + 240);
      if ( (int)MpCreateDlpSectionFileNameEntry(a3, p_Name, &v47) >= 0 )
      {
        v33 = v47;
        if ( v47 )
        {
          v47[6] = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 40LL);
          FltAcquirePushLockExclusive((PULONG_PTR)MpDlpData + 1);
          v34 = (char *)MpDlpData + 16;
          v35 = (PVOID *)*((_QWORD *)MpDlpData + 3);
          if ( *v35 != (char *)MpDlpData + 16 )
            goto LABEL_72;
          _mm_lfence();
          *v33 = v34;
          v33[1] = v35;
          *v35 = v33;
          *((_QWORD *)v34 + 1) = v33;
          _InterlockedOr((volatile signed __int32 *)(a3 + 48), 0x40000u);
          FltReleasePushLock((PULONG_PTR)MpDlpData + 1);
          if ( !*(_BYTE *)(v15 + 224) )
          {
            v36 = &v29->Name;
            if ( !v29 )
              v36 = (UNICODE_STRING *)(a3 + 240);
            v37 = *(_QWORD *)(a2 + 32);
            if ( v36 )
            {
              if ( (*(_DWORD *)(a3 + 48) & 0x10000) != 0 )
              {
                FltAcquirePushLockExclusive((PULONG_PTR)(v15 + 200));
                v38 = (_QWORD *)(v15 + 208);
                v39 = *(_QWORD **)(v15 + 208);
                while ( v39 != v38 )
                {
                  v40 = v39;
                  v39 = (_QWORD *)*v39;
                  if ( v40[3] == a3 )
                  {
                    *((_DWORD *)v40 + 4) &= ~1u;
                    v40[6] = *(_QWORD *)(v37 + 40);
                    goto LABEL_62;
                  }
                }
                _mm_lfence();
                v47 = 0;
                if ( (int)MpCreateDlpSectionFileNameEntry(a3, v36, &v47) >= 0 )
                {
                  v43 = v47;
                  if ( v47 )
                  {
                    v47[6] = *(_QWORD *)(v37 + 40);
                    v44 = *(_QWORD **)(v15 + 216);
                    if ( (_QWORD *)*v44 != v38 )
                      goto LABEL_72;
                    *v43 = v38;
                    v43[1] = v44;
                    *v44 = v43;
                    *(_QWORD *)(v15 + 216) = v43;
                  }
                }
LABEL_62:
                FltReleasePushLock((PULONG_PTR)(v15 + 200));
              }
            }
          }
        }
      }
      if ( v29 )
        FltReleaseFileNameInformation(v29);
      goto LABEL_37;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003f700  mov     [rsp+arg_18], rbx
0x14003f705  push    rbp
0x14003f706  push    rsi
0x14003f707  push    rdi
0x14003f708  push    r12
0x14003f70a  push    r13
0x14003f70c  push    r14
0x14003f70e  push    r15
0x14003f710  sub     rsp, 80h
0x14003f717  mov     rax, cs:__security_cookie
0x14003f71e  xor     rax, rsp
0x14003f721  mov     [rsp+0B8h+var_48], rax
0x14003f726  mov     rax, cs:MpData
0x14003f72d  xor     esi, esi
0x14003f72f  mov     [rsp+0B8h+Context], 0
0x14003f738  mov     rdi, r8
0x14003f73b  mov     r15, rdx
0x14003f73e  mov     [rsp+0B8h+var_68], esi
0x14003f742  mov     r14, rcx
0x14003f745  test    dword ptr [rax+360h], 2000h
0x14003f74f  jnz     loc_14003FC9D
0x14003f755  call    MpGetRequestorProcess
0x14003f75a  mov     rbx, rax
0x14003f75d  test    rax, rax
0x14003f760  jz      loc_14003FE5B
0x14003f766  mov     rcx, rax; Process
0x14003f769  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14003f770  nop     dword ptr [rax+rax+00h]
0x14003f775  mov     rcx, rbx; Process
0x14003f778  mov     r12, rax
0x14003f77b  call    cs:__imp_PsGetProcessId
0x14003f782  nop     dword ptr [rax+rax+00h]
0x14003f787  xor     r13d, r13d
0x14003f78a  mov     rbp, rax
0x14003f78d  test    rax, rax
0x14003f790  jz      loc_14003FE03
0x14003f796  mov     rbx, cs:MpProcessTable
0x14003f79d  call    cs:__imp_KeEnterCriticalRegion
0x14003f7a4  nop     dword ptr [rax+rax+00h]
0x14003f7a9  mov     dl, 1; Wait
0x14003f7ab  lea     rcx, [rbx+8]; Resource
0x14003f7af  call    cs:__imp_ExAcquireResourceSharedLite
0x14003f7b6  nop     dword ptr [rax+rax+00h]
0x14003f7bb  mov     rax, cs:MpProcessTable
0x14003f7c2  mov     r8, rbp
0x14003f7c5  shr     r8, 2
0x14003f7c9  and     r8d, 7Fh
0x14003f7cd  shl     r8, 4
0x14003f7d1  add     r8, [rax+180h]
0x14003f7d8  mov     rax, [r8]
0x14003f7db  nop     dword ptr [rax+rax+00h]
0x14003f7e0  cmp     rax, r8
0x14003f7e3  jz      loc_14003FDDD
0x14003f7e9  cmp     rbp, [rax+10h]
0x14003f7ed  lea     rsi, [rax-8]
0x14003f7f1  jz      short loc_14003F7F8
0x14003f7f3  mov     rax, [rax]
0x14003f7f6  jmp     short loc_14003F7E0
0x14003f7f8  cmp     r12, [rsi+20h]
0x14003f7fc  jnz     short loc_14003F7F3
0x14003f7fe  lock inc dword ptr [rsi+30h]
0x14003f802  mov     rcx, cs:MpProcessTable
0x14003f809  add     rcx, 8; Resource
0x14003f80d  call    cs:__imp_ExReleaseResourceLite
0x14003f814  nop     dword ptr [rax+rax+00h]
0x14003f819  call    cs:__imp_KeLeaveCriticalRegion
0x14003f820  nop     dword ptr [rax+rax+00h]
0x14003f825  mov     rbp, r14
0x14003f828  call    cs:__imp_IoGetCurrentProcess
0x14003f82f  nop     dword ptr [rax+rax+00h]
0x14003f834  mov     rcx, cs:MpDlpData
0x14003f83b  mov     r13, rsi
0x14003f83e  mov     r12, rax
0x14003f841  test    rcx, rcx
0x14003f844  jz      loc_14003FA70
0x14003f84a  lea     rax, [r14-1]
0x14003f84e  cmp     rax, 1
0x14003f852  jbe     loc_14003FD18
0x14003f858  movzx   eax, byte ptr [rcx+20h]
0x14003f85c  test    al, al
0x14003f85e  jz      loc_14003FA70
0x14003f864  mov     rcx, cs:MpData
0x14003f86b  test    dword ptr [rcx+360h], 400h
0x14003f875  jz      loc_14003FA70
0x14003f87b  cmp     qword ptr [rcx+140h], 0
0x14003f883  jz      loc_14003FD05
0x14003f889  mov     rcx, gs:188h; Thread
0x14003f892  mov     rax, cs:MpData
0x14003f899  mov     rbx, [rax+0E8h]
0x14003f8a0  call    cs:__imp_IoThreadToProcess
0x14003f8a7  nop     dword ptr [rax+rax+00h]
0x14003f8ac  cmp     rax, rbx
0x14003f8af  jz      loc_14003FC4D
0x14003f8b5  mov     rcx, gs:188h; Thread
0x14003f8be  mov     rax, cs:MpData
0x14003f8c5  mov     rbx, [rax+100h]
0x14003f8cc  call    cs:__imp_IoThreadToProcess
0x14003f8d3  nop     dword ptr [rax+rax+00h]
0x14003f8d8  cmp     rax, rbx
0x14003f8db  jz      loc_14003FC4D
0x14003f8e1  test    rbp, rbp
0x14003f8e4  jnz     loc_14003FC7A
0x14003f8ea  mov     rax, cs:__imp_PsInitialSystemProcess
0x14003f8f1  cmp     [rax], r12
0x14003f8f4  jz      loc_14003FCD6
0x14003f8fa  mov     rdx, rsi
0x14003f8fd  mov     rcx, rbp
0x14003f900  mov     r13, rsi
0x14003f903  call    MpDlpIsProcessExcluded
0x14003f908  test    al, al
0x14003f90a  jnz     loc_14003FA70
0x14003f910  mov     rdx, [r15+20h]; FileObject
0x14003f914  lea     r8, [rsp+0B8h+Context]; Context
0x14003f919  mov     rcx, [r15+18h]; Instance
0x14003f91d  call    cs:__imp_FltGetStreamHandleContext
0x14003f924  nop     dword ptr [rax+rax+00h]
0x14003f929  test    eax, eax
0x14003f92b  js      loc_14003FE5B
0x14003f931  mov     rcx, [rsp+0B8h+Context]
0x14003f936  mov     r13, rsi
0x14003f939  mov     eax, [rcx+28h]
0x14003f93c  test    al, 40h
0x14003f93e  jz      loc_14003FA70
0x14003f944  lock or dword ptr [rcx+28h], 20h
0x14003f949  mov     r9, [rdi+8]
0x14003f94d  xor     r12d, r12d
0x14003f950  mov     rax, [rsp+0B8h+Context]
0x14003f955  mov     r8, rsi
0x14003f958  mov     [rsp+0B8h+var_70], r12; __int64
0x14003f95d  mov     rdx, r15
0x14003f960  mov     [rsp+0B8h+var_78], r12; __int64
0x14003f965  mov     rcx, r14; CallbackData
0x14003f968  mov     r9d, [r9+54h]
0x14003f96c  mov     dword ptr [rsp+0B8h+Size], r12d; Size
0x14003f971  mov     [rsp+0B8h+var_88], r12; __int64
0x14003f976  mov     [rsp+0B8h+var_90], rax; __int64
0x14003f97b  mov     [rsp+0B8h+var_98], rdi; __int64
0x14003f980  call    MpDlpCheckFileAccess
0x14003f985  mov     [rsp+0B8h+var_68], eax
0x14003f989  cmp     eax, 2
0x14003f98c  jz      loc_14003FDC8
0x14003f992  test    dword ptr [rdi+30h], 40000h
0x14003f999  jz      loc_14003FABE
0x14003f99f  mov     rcx, cs:MpDlpData
0x14003f9a6  add     rcx, 8; PushLock
0x14003f9aa  call    cs:__imp_FltAcquirePushLockExclusive
0x14003f9b1  nop     dword ptr [rax+rax+00h]
0x14003f9b6  mov     rcx, cs:MpDlpData
0x14003f9bd  add     rcx, 10h
0x14003f9c1  mov     rax, [rcx]
0x14003f9c4  cmp     rax, rcx
0x14003f9c7  jz      loc_14003FA59
0x14003f9cd  mov     rdx, rax
0x14003f9d0  mov     rax, [rax]
0x14003f9d3  cmp     [rdx+18h], rdi
0x14003f9d7  jnz     short loc_14003F9C4
0x14003f9d9  and     dword ptr [rdx+10h], 0FFFFFFFEh
0x14003f9dd  mov     rax, [r15+20h]
0x14003f9e1  mov     rcx, [rax+28h]
0x14003f9e5  mov     [rdx+30h], rcx
0x14003f9e9  cmp     [rsi+0E0h], r12b
0x14003f9f0  jnz     short loc_14003FA59
0x14003f9f2  mov     rbp, [r15+20h]
0x14003f9f6  lea     r14, [rdx+20h]
0x14003f9fa  test    r14, r14
0x14003f9fd  jz      short loc_14003FA59
0x14003f9ff  test    dword ptr [rdi+30h], 10000h
0x14003fa06  jz      short loc_14003FA59
0x14003fa08  lea     rcx, [rsi+0C8h]; PushLock
0x14003fa0f  call    cs:__imp_FltAcquirePushLockExclusive
0x14003fa16  nop     dword ptr [rax+rax+00h]
0x14003fa1b  lea     rbx, [rsi+0D0h]
0x14003fa22  mov     rax, [rbx]
0x14003fa25  cmp     rax, rbx
0x14003fa28  jz      loc_14003FD1F
0x14003fa2e  mov     rcx, rax
0x14003fa31  mov     rax, [rax]
0x14003fa34  cmp     [rcx+18h], rdi
0x14003fa38  jnz     short loc_14003FA25
0x14003fa3a  and     dword ptr [rcx+10h], 0FFFFFFFEh
0x14003fa3e  mov     rax, [rbp+28h]
0x14003fa42  mov     [rcx+30h], rax
0x14003fa46  lea     rcx, [rsi+0C8h]; PushLock
0x14003fa4d  call    cs:__imp_FltReleasePushLock
0x14003fa54  nop     dword ptr [rax+rax+00h]
0x14003fa59  mov     rcx, cs:MpDlpData
0x14003fa60  add     rcx, 8; PushLock
0x14003fa64  call    cs:__imp_FltReleasePushLock
0x14003fa6b  nop     dword ptr [rax+rax+00h]
0x14003fa70  mov     esi, [rsp+0B8h+var_68]
0x14003fa74  test    r13, r13
0x14003fa77  jnz     loc_14003FCF8
0x14003fa7d  mov     rcx, [rsp+0B8h+Context]; Context
0x14003fa82  test    rcx, rcx
0x14003fa85  jz      short loc_14003FA93
0x14003fa87  call    cs:__imp_FltReleaseContext
0x14003fa8e  nop     dword ptr [rax+rax+00h]
0x14003fa93  mov     eax, esi
0x14003fa95  mov     rcx, [rsp+0B8h+var_48]
0x14003fa9a  xor     rcx, rsp; StackCookie
0x14003fa9d  call    __security_check_cookie
0x14003faa2  mov     rbx, [rsp+0B8h+arg_18]
0x14003faaa  add     rsp, 80h
0x14003fab1  pop     r15
0x14003fab3  pop     r14
0x14003fab5  pop     r13
0x14003fab7  pop     r12
0x14003fab9  pop     rdi
0x14003faba  pop     rsi
0x14003fabb  pop     rbp
0x14003fabc  retn
0x14003fabe  mov     rbp, r12
0x14003fac1  mov     [rsp+0B8h+var_60], r12
0x14003fac6  cmp     cs:byte_1400269F8, bpl
0x14003facd  mov     edx, 201h; NameOptions
0x14003fad2  mov     [rsp+0B8h+FileNameInformation], r12
0x14003fad7  jz      loc_14003FC63
0x14003fadd  lea     r8, [rsp+0B8h+FileNameInformation]; FileNameInformation
0x14003fae2  mov     rcx, r14; CallbackData
0x14003fae5  call    cs:__imp_FltGetFileNameInformation
0x14003faec  nop     dword ptr [rax+rax+00h]
0x14003faf1  mov     ecx, eax
0x14003faf3  test    eax, eax
0x14003faf5  js      loc_14003FCB3
0x14003fafb  mov     rax, [rsp+0B8h+FileNameInformation]
0x14003fb00  test    rax, rax
0x14003fb03  jz      short loc_14003FB08
0x14003fb05  mov     rbp, rax
0x14003fb08  lea     rdx, [rbp+8]
0x14003fb0c  test    ecx, ecx
0x14003fb0e  jns     short loc_14003FB17
0x14003fb10  lea     rdx, [rdi+0F0h]
0x14003fb17  lea     r8, [rsp+0B8h+var_60]
0x14003fb1c  mov     rcx, rdi
0x14003fb1f  call    MpCreateDlpSectionFileNameEntry
0x14003fb24  test    eax, eax
0x14003fb26  js      loc_14003FC24
0x14003fb2c  mov     rbx, [rsp+0B8h+var_60]
0x14003fb31  test    rbx, rbx
0x14003fb34  jz      loc_14003FC24
0x14003fb3a  mov     rax, [r15+20h]
0x14003fb3e  mov     rcx, [rax+28h]
0x14003fb42  mov     [rbx+30h], rcx
0x14003fb46  mov     rcx, cs:MpDlpData
0x14003fb4d  add     rcx, 8; PushLock
0x14003fb51  call    cs:__imp_FltAcquirePushLockExclusive
0x14003fb58  nop     dword ptr [rax+rax+00h]
0x14003fb5d  mov     rax, cs:MpDlpData
0x14003fb64  add     rax, 10h
0x14003fb68  mov     rcx, [rax+8]
0x14003fb6c  cmp     [rcx], rax
0x14003fb6f  jnz     loc_14003FC96
0x14003fb75  lfence
0x14003fb78  mov     [rbx], rax
0x14003fb7b  mov     [rbx+8], rcx
0x14003fb7f  mov     [rcx], rbx
0x14003fb82  mov     [rax+8], rbx
0x14003fb86  lock or dword ptr [rdi+30h], 40000h
0x14003fb8e  mov     rcx, cs:MpDlpData
0x14003fb95  add     rcx, 8; PushLock
0x14003fb99  call    cs:__imp_FltReleasePushLock
0x14003fba0  nop     dword ptr [rax+rax+00h]
0x14003fba5  cmp     [rsi+0E0h], r12b
0x14003fbac  jnz     short loc_14003FC24
0x14003fbae  lea     r14, [rbp+8]
0x14003fbb2  test    rbp, rbp
0x14003fbb5  jz      loc_14003FC41
0x14003fbbb  mov     r15, [r15+20h]
0x14003fbbf  test    r14, r14
0x14003fbc2  jz      short loc_14003FC24
0x14003fbc4  test    dword ptr [rdi+30h], 10000h
0x14003fbcb  jz      short loc_14003FC24
0x14003fbcd  lea     rcx, [rsi+0C8h]; PushLock
0x14003fbd4  call    cs:__imp_FltAcquirePushLockExclusive
0x14003fbdb  nop     dword ptr [rax+rax+00h]
0x14003fbe0  lea     rbx, [rsi+0D0h]
0x14003fbe7  mov     rax, [rbx]
0x14003fbea  nop     word ptr [rax+rax+00h]
0x14003fbf0  cmp     rax, rbx
0x14003fbf3  jz      loc_14003FD72
0x14003fbf9  mov     rcx, rax
0x14003fbfc  mov     rax, [rax]
0x14003fbff  cmp     [rcx+18h], rdi
0x14003fc03  jnz     short loc_14003FBF0
0x14003fc05  and     dword ptr [rcx+10h], 0FFFFFFFEh
0x14003fc09  mov     rax, [r15+28h]
0x14003fc0d  mov     [rcx+30h], rax
0x14003fc11  lea     rcx, [rsi+0C8h]; PushLock
0x14003fc18  call    cs:__imp_FltReleasePushLock
0x14003fc1f  nop     dword ptr [rax+rax+00h]
0x14003fc24  test    rbp, rbp
0x14003fc27  jz      loc_14003FA70
0x14003fc2d  mov     rcx, rbp; FileNameInformation
0x14003fc30  call    cs:__imp_FltReleaseFileNameInformation
0x14003fc37  nop     dword ptr [rax+rax+00h]
0x14003fc3c  jmp     loc_14003FA70
0x14003fc41  lea     r14, [rdi+0F0h]
0x14003fc48  jmp     loc_14003FBBB
0x14003fc4d  cmp     r14, 1
0x14003fc51  jz      loc_14003F910
  ... truncated ...
```
