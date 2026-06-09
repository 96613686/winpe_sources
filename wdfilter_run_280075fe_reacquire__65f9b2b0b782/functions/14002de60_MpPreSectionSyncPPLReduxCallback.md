# MpPreSectionSyncPPLReduxCallback

- ea: `0x14002de60`
- end: `0x14002e37e`
- name: `MpPreSectionSyncPPLReduxCallback`
- size: `1310`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x14002da90`

## callees

- `0x1400018a4`
- `0x140002450`
- `0x140004a08`
- `0x1400118d0`
- `0x14002d2b4`
- `0x14002de60`
- `0x140030060`
- `0x140040388`
- `0x14008b3b8`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14002df8a`
- `ntoskrnl!PsGetProcessId` at `0x14002df8a`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002df5c`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002df78`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002df78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002e020`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002e33a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002e020`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002e33a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e014`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e32e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e014`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e32e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002dfbb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002dfbb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002dfa9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002dfa9`
- `ntoskrnl!IoThreadToProcess` at `0x14002df19`
- `ntoskrnl!IoThreadToProcess` at `0x14002e08d`
- `ntoskrnl!IoThreadToProcess` at `0x14002df19`
- `ntoskrnl!IoThreadToProcess` at `0x14002e08d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e156`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e1a9`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e156`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e1a9`
- `FLTMGR!FltReleaseContext` at `0x14002e0df`
- `FLTMGR!FltReleaseContext` at `0x14002e0df`
- `FLTMGR!FltGetFileNameInformation` at `0x14002e2aa`
- `FLTMGR!FltGetFileNameInformation` at `0x14002e2aa`
- `FLTMGR!FltGetStreamContext` at `0x14002e0bc`
- `FLTMGR!FltGetStreamContext` at `0x14002e0bc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e312`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e312`

## string_xrefs

- `0x14002e1d1`: `[Mini-filter] [PPL-Redux] Detected. Process [%wZ][Pid:%u] trying to map file[%wZ] PageProtection[0x%x] with reparse tag[0x%x]. MpReduxMitigationFlags[0x%x]`

## pseudocode

```c
__int64 __fastcall MpPreSectionSyncPPLReduxCallback(PFLT_CALLBACK_DATA CallbackData, _QWORD *a2)
{
  bool v2; // r15
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  unsigned int v6; // r14d
  ULONG PageProtection; // r13d
  LONG HighPart; // eax
  struct _KPROCESS *v9; // rbx
  struct _KPROCESS *RequestorProcess; // rax
  struct _KPROCESS *v12; // rbx
  LONGLONG TimeQuadPart; // r12
  unsigned __int64 ProcessId; // rsi
  char *v15; // rbx
  _QWORD *v16; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v18; // rbx
  NTSTATUS StreamContext; // esi
  struct _KPROCESS *v20; // rbx
  struct _FILE_OBJECT *v21; // rdx
  struct _FLT_INSTANCE *v22; // rcx
  int v23; // r12d
  char CurrentProcessId; // al
  unsigned int v25; // eax
  NTSTATUS v26; // eax
  __int64 v27; // [rsp+20h] [rbp-88h]
  __int64 v28; // [rsp+28h] [rbp-80h]
  __int64 v29; // [rsp+30h] [rbp-78h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-58h] BYREF
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-50h] BYREF

  v2 = 0;
  Context = 0;
  if ( !CallbackData )
    return 3221225485LL;
  if ( !a2 )
    return 3221225485LL;
  Iopb = CallbackData->Iopb;
  if ( Iopb->MajorFunction != 0xFF )
    return 3221225485LL;
  if ( !CallbackData->RequestorMode || a2[5] )
    return 0;
  v6 = *(_DWORD *)(MpData + 4120);
  if ( (v6 & 0xFFFFFFE0) != 0 )
    return 3221225485LL;
  if ( (v6 & 1) == 0 )
    return 0;
  PageProtection = Iopb->Parameters.AcquireForSectionSynchronization.PageProtection;
  if ( (*(_DWORD *)(MpData + 864) & 0x2000) != 0 )
  {
    HighPart = Iopb->Parameters.Read.ByteOffset.HighPart;
    v2 = (HighPart & 0x1000000) != 0;
    if ( (HighPart & 0x1000000) != 0 )
      goto LABEL_12;
  }
  else if ( (PageProtection & 0xF0) != 0 )
  {
    v2 = 1;
    goto LABEL_12;
  }
  v9 = *(struct _KPROCESS **)(MpData + 232);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v9 )
    return 0;
  v20 = *(struct _KPROCESS **)(MpData + 256);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v20 )
    return 0;
LABEL_12:
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(CallbackData);
  v12 = RequestorProcess;
  if ( !RequestorProcess || PsInitialSystemProcess == RequestorProcess )
    return 0;
  TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
  ProcessId = (unsigned __int64)PsGetProcessId(v12);
  if ( ProcessId )
  {
    v15 = (char *)MpProcessTable;
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)(v15 + 8), 1u);
    v16 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
    for ( i = (_QWORD *)*v16; i != v16; i = (_QWORD *)*i )
    {
      v18 = (volatile signed __int32 *)(i - 1);
      if ( ProcessId == i[2] && TimeQuadPart == *((_QWORD *)v18 + 4) )
      {
        _InterlockedIncrement(v18 + 12);
        ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
        KeLeaveCriticalRegion();
        _mm_lfence();
        StreamContext = 0;
        if ( (v18[72] & 1) == 0 || (v18[46] & 7) != 1 )
          goto LABEL_22;
        v21 = (struct _FILE_OBJECT *)a2[4];
        v22 = (struct _FLT_INSTANCE *)a2[3];
        LODWORD(FileNameInformation) = -1;
        StreamContext = FltGetStreamContext(v22, v21, &Context);
        if ( StreamContext >= 0 )
        {
          LODWORD(FileNameInformation) = *((_DWORD *)Context + 159);
          v23 = (int)FileNameInformation;
          FltReleaseContext(Context);
          Context = 0;
          if ( ((unsigned int)FileNameInformation & 0xFFF0000) != 0 || (unsigned int)FileNameInformation <= 2 )
          {
LABEL_29:
            if ( !(_DWORD)FileNameInformation )
              goto LABEL_32;
          }
          else if ( ((unsigned int)FileNameInformation & 0xC0000000) != 0x40000000 )
          {
            if ( ((unsigned int)FileNameInformation & 0x30000000) == 0x30000000 )
              goto LABEL_29;
LABEL_32:
            if ( (v23 & 0xFFFF0FFF) == 0x9000001A )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
                WPP_SF_ZDZDDD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  11,
                  (unsigned int)WPP_3ac2d441938b3ccb0af7fdd108b4c5f3_Traceguids,
                  *((_QWORD *)v18 + 16),
                  CurrentProcessId,
                  (__int64)&CallbackData->Iopb->TargetFileObject->FileName,
                  PageProtection,
                  v23,
                  v6);
              }
              v25 = (unsigned int)PsGetCurrentProcessId();
              LODWORD(v29) = v6;
              LODWORD(v28) = v23;
              LODWORD(v27) = PageProtection;
              MpLogPrintfW(
                L"[Mini-filter] [PPL-Redux] Detected. Process [%wZ][Pid:%u] trying to map file[%wZ] PageProtection[0x%x] w"
                 "ith reparse tag[0x%x]. MpReduxMitigationFlags[0x%x]",
                *((_QWORD *)v18 + 16),
                v25,
                &CallbackData->Iopb->TargetFileObject->FileName,
                v27,
                v28,
                v29);
              StreamContext = 0;
              if ( v2 )
              {
                if ( (v6 & 4) == 0 )
                {
LABEL_47:
                  if ( (v6 & 2) == 0 )
                    goto LABEL_22;
LABEL_50:
                  FileNameInformation = 0;
                  v26 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
                  if ( v26 < 0
                    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                  {
                    _mm_lfence();
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      12,
                      WPP_3ac2d441938b3ccb0af7fdd108b4c5f3_Traceguids,
                      (unsigned int)v26);
                  }
                  MpTracePPLRedux(v18, FileNameInformation, v6, v2);
                  if ( FileNameInformation )
                    FltReleaseFileNameInformation(FileNameInformation);
                  goto LABEL_22;
                }
LABEL_46:
                CallbackData->IoStatus.Information = 0;
                StreamContext = 1835009;
                CallbackData->IoStatus.Status = -1073741790;
                if ( v2 )
                  goto LABEL_47;
              }
              else if ( (v6 & 8) != 0 )
              {
                goto LABEL_46;
              }
              if ( (v6 & 0x10) != 0 )
                goto LABEL_50;
            }
LABEL_22:
            MpReleaseProcessContext(v18);
            return (unsigned int)StreamContext;
          }
        }
        StreamContext = MpGetFileReparseTag(a2[3], a2[4], &FileNameInformation);
        if ( StreamContext >= 0 )
        {
          v23 = (int)FileNameInformation;
          goto LABEL_32;
        }
        goto LABEL_22;
      }
    }
    ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
    KeLeaveCriticalRegion();
  }
  _mm_lfence();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_3ac2d441938b3ccb0af7fdd108b4c5f3_Traceguids, 3221226021LL);
  return 3221226021LL;
}

```

## disassembly

```asm
0x14002de60  push    rbx
0x14002de62  push    rbp
0x14002de63  push    rdi
0x14002de64  push    r13
0x14002de66  push    r14
0x14002de68  push    r15
0x14002de6a  sub     rsp, 78h
0x14002de6e  mov     rax, cs:__security_cookie
0x14002de75  xor     rax, rsp
0x14002de78  mov     [rsp+0A8h+var_48], rax
0x14002de7d  xor     r15b, r15b
0x14002de80  mov     [rsp+0A8h+Context], 0
0x14002de89  mov     rbp, rdx
0x14002de8c  mov     rdi, rcx
0x14002de8f  test    rcx, rcx
0x14002de92  jz      loc_14002E374
0x14002de98  test    rdx, rdx
0x14002de9b  jz      loc_14002E374
0x14002dea1  mov     rcx, [rcx+10h]
0x14002dea5  cmp     byte ptr [rcx+4], 0FFh
0x14002dea9  jnz     loc_14002E374
0x14002deaf  cmp     [rdi+50h], r15b
0x14002deb3  jz      short loc_14002DF2E
0x14002deb5  cmp     qword ptr [rdx+28h], 0
0x14002deba  jnz     short loc_14002DF2E
0x14002debc  mov     rax, cs:MpData
0x14002dec3  mov     r14d, [rax+1018h]
0x14002deca  test    r14d, 0FFFFFFE0h
0x14002ded1  jnz     loc_14002E374
0x14002ded7  test    r14b, 1
0x14002dedb  jz      short loc_14002DF2E
0x14002dedd  test    dword ptr [rax+360h], 2000h
0x14002dee7  mov     r13d, [rcx+1Ch]
0x14002deeb  jz      loc_14002E064
0x14002def1  mov     eax, [rcx+2Ch]
0x14002def4  bt      eax, 18h
0x14002def8  setb    r15b
0x14002defc  bt      eax, 18h
0x14002df00  jb      short loc_14002DF4C
0x14002df02  mov     rcx, gs:188h; Thread
0x14002df0b  mov     rax, cs:MpData
0x14002df12  mov     rbx, [rax+0E8h]
0x14002df19  call    cs:__imp_IoThreadToProcess
0x14002df20  nop     dword ptr [rax+rax+00h]
0x14002df25  cmp     rax, rbx
0x14002df28  jnz     loc_14002E076
0x14002df2e  xor     eax, eax
0x14002df30  mov     rcx, [rsp+0A8h+var_48]
0x14002df35  xor     rcx, rsp; StackCookie
0x14002df38  call    __security_check_cookie
0x14002df3d  add     rsp, 78h
0x14002df41  pop     r15
0x14002df43  pop     r14
0x14002df45  pop     r13
0x14002df47  pop     rdi
0x14002df48  pop     rbp
0x14002df49  pop     rbx
0x14002df4a  retn
0x14002df4c  mov     rcx, rdi
0x14002df4f  call    MpGetRequestorProcess
0x14002df54  mov     rbx, rax
0x14002df57  test    rax, rax
0x14002df5a  jz      short loc_14002DF2E
0x14002df5c  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002df63  cmp     [rcx], rax
0x14002df66  jz      short loc_14002DF2E
0x14002df68  mov     [rsp+0A8h+arg_10], rsi
0x14002df70  mov     rcx, rax; Process
0x14002df73  mov     [rsp+0A8h+var_38], r12
0x14002df78  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002df7f  nop     dword ptr [rax+rax+00h]
0x14002df84  mov     rcx, rbx; Process
0x14002df87  mov     r12, rax
0x14002df8a  call    cs:__imp_PsGetProcessId
0x14002df91  nop     dword ptr [rax+rax+00h]
0x14002df96  mov     rsi, rax
0x14002df99  test    rax, rax
0x14002df9c  jz      loc_14002E22D
0x14002dfa2  mov     rbx, cs:MpProcessTable
0x14002dfa9  call    cs:__imp_KeEnterCriticalRegion
0x14002dfb0  nop     dword ptr [rax+rax+00h]
0x14002dfb5  mov     dl, 1; Wait
0x14002dfb7  lea     rcx, [rbx+8]; Resource
0x14002dfbb  call    cs:__imp_ExAcquireResourceSharedLite
0x14002dfc2  nop     dword ptr [rax+rax+00h]
0x14002dfc7  mov     rax, cs:MpProcessTable
0x14002dfce  mov     r8, rsi
0x14002dfd1  shr     r8, 2
0x14002dfd5  and     r8d, 7Fh
0x14002dfd9  shl     r8, 4
0x14002dfdd  add     r8, [rax+180h]
0x14002dfe4  mov     rax, [r8]
0x14002dfe7  cmp     rax, r8
0x14002dfea  jz      loc_14002E323
0x14002dff0  cmp     rsi, [rax+10h]
0x14002dff4  lea     rbx, [rax-8]
0x14002dff8  jz      short loc_14002DFFF
0x14002dffa  mov     rax, [rax]
0x14002dffd  jmp     short loc_14002DFE7
0x14002dfff  cmp     r12, [rbx+20h]
0x14002e003  jnz     short loc_14002DFFA
0x14002e005  lock inc dword ptr [rbx+30h]
0x14002e009  mov     rcx, cs:MpProcessTable
0x14002e010  add     rcx, 8; Resource
0x14002e014  call    cs:__imp_ExReleaseResourceLite
0x14002e01b  nop     dword ptr [rax+rax+00h]
0x14002e020  call    cs:__imp_KeLeaveCriticalRegion
0x14002e027  nop     dword ptr [rax+rax+00h]
0x14002e02c  lfence
0x14002e02f  mov     eax, [rbx+120h]
0x14002e035  xor     esi, esi
0x14002e037  test    al, 1
0x14002e039  jz      short loc_14002E048
0x14002e03b  movzx   eax, byte ptr [rbx+0B8h]
0x14002e042  and     al, 7
0x14002e044  cmp     al, 1
0x14002e046  jz      short loc_14002E0A7
0x14002e048  mov     rcx, rbx
0x14002e04b  call    MpReleaseProcessContext
0x14002e050  mov     r12, [rsp+0A8h+var_38]
0x14002e055  mov     eax, esi
0x14002e057  mov     rsi, [rsp+0A8h+arg_10]
0x14002e05f  jmp     loc_14002DF30
0x14002e064  test    r13b, 0F0h
0x14002e068  jz      loc_14002DF02
0x14002e06e  mov     r15b, 1
0x14002e071  jmp     loc_14002DF4C
0x14002e076  mov     rcx, gs:188h; Thread
0x14002e07f  mov     rax, cs:MpData
0x14002e086  mov     rbx, [rax+100h]
0x14002e08d  call    cs:__imp_IoThreadToProcess
0x14002e094  nop     dword ptr [rax+rax+00h]
0x14002e099  cmp     rax, rbx
0x14002e09c  jz      loc_14002DF2E
0x14002e0a2  jmp     loc_14002DF4C
0x14002e0a7  mov     rdx, [rbp+20h]; FileObject
0x14002e0ab  lea     r8, [rsp+0A8h+Context]; Context
0x14002e0b0  mov     rcx, [rbp+18h]; Instance
0x14002e0b4  mov     dword ptr [rsp+0A8h+FileNameInformation], 0FFFFFFFFh
0x14002e0bc  call    cs:__imp_FltGetStreamContext
0x14002e0c3  nop     dword ptr [rax+rax+00h]
0x14002e0c8  mov     esi, eax
0x14002e0ca  test    eax, eax
0x14002e0cc  js      short loc_14002E108
0x14002e0ce  mov     rcx, [rsp+0A8h+Context]; Context
0x14002e0d3  mov     r12d, [rcx+27Ch]
0x14002e0da  mov     dword ptr [rsp+0A8h+FileNameInformation], r12d
0x14002e0df  call    cs:__imp_FltReleaseContext
0x14002e0e6  nop     dword ptr [rax+rax+00h]
0x14002e0eb  mov     [rsp+0A8h+Context], 0
0x14002e0f4  mov     ecx, r12d
0x14002e0f7  test    r12d, 0FFF0000h
0x14002e0fe  jz      loc_14002E1F8
0x14002e104  test    ecx, ecx
0x14002e106  jz      short loc_14002E129
0x14002e108  mov     rdx, [rbp+20h]
0x14002e10c  lea     r8, [rsp+0A8h+FileNameInformation]
0x14002e111  mov     rcx, [rbp+18h]
0x14002e115  call    MpGetFileReparseTag
0x14002e11a  mov     esi, eax
0x14002e11c  test    eax, eax
0x14002e11e  js      loc_14002E048
0x14002e124  mov     r12d, dword ptr [rsp+0A8h+FileNameInformation]
0x14002e129  mov     eax, r12d
0x14002e12c  and     eax, 0FFFF0FFFh
0x14002e131  cmp     eax, 9000001Ah
0x14002e136  jnz     loc_14002E048
0x14002e13c  mov     rax, cs:WPP_GLOBAL_Control
0x14002e143  lea     rbp, WPP_GLOBAL_Control
0x14002e14a  cmp     rax, rbp
0x14002e14d  jz      short loc_14002E1A9
0x14002e14f  mov     eax, [rax+2Ch]
0x14002e152  test    al, 2
0x14002e154  jz      short loc_14002E1A9
0x14002e156  call    cs:__imp_PsGetCurrentProcessId
0x14002e15d  nop     dword ptr [rax+rax+00h]
0x14002e162  mov     rcx, [rdi+10h]
0x14002e166  mov     edx, 0Bh
0x14002e16b  mov     r9, [rbx+80h]
0x14002e172  mov     [rsp+0A8h+var_68], r14d
0x14002e177  mov     [rsp+0A8h+var_70], r12d
0x14002e17c  mov     r8, [rcx+8]
0x14002e180  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e187  add     r8, 58h ; 'X'
0x14002e18b  mov     dword ptr [rsp+0A8h+var_78], r13d
0x14002e190  mov     [rsp+0A8h+var_80], r8
0x14002e195  lea     r8, WPP_3ac2d441938b3ccb0af7fdd108b4c5f3_Traceguids
0x14002e19c  mov     dword ptr [rsp+0A8h+var_88], eax
0x14002e1a0  mov     rcx, [rcx+18h]
0x14002e1a4  call    WPP_SF_ZDZDDD
0x14002e1a9  call    cs:__imp_PsGetCurrentProcessId
0x14002e1b0  nop     dword ptr [rax+rax+00h]
0x14002e1b5  mov     rcx, [rdi+10h]
0x14002e1b9  mov     r8d, eax
0x14002e1bc  mov     rdx, [rbx+80h]
0x14002e1c3  mov     dword ptr [rsp+0A8h+var_78], r14d
0x14002e1c8  mov     dword ptr [rsp+0A8h+var_80], r12d
0x14002e1cd  mov     r9, [rcx+8]
0x14002e1d1  lea     rcx, aMiniFilterPplR; "[Mini-filter] [PPL-Redux] Detected. Pro"...
0x14002e1d8  add     r9, 58h ; 'X'
0x14002e1dc  mov     dword ptr [rsp+0A8h+var_88], r13d
0x14002e1e1  call    MpLogPrintfW
0x14002e1e6  xor     esi, esi
0x14002e1e8  test    r15b, r15b
0x14002e1eb  jz      short loc_14002E260
0x14002e1ed  test    r14b, 4
0x14002e1f1  jnz     short loc_14002E266
0x14002e1f3  jmp     loc_14002E27B
0x14002e1f8  cmp     r12d, 2
0x14002e1fc  jbe     loc_14002E104
0x14002e202  mov     eax, r12d
0x14002e205  and     eax, 0C0000000h
0x14002e20a  cmp     eax, 40000000h
0x14002e20f  jz      loc_14002E108
0x14002e215  mov     eax, r12d
0x14002e218  and     eax, 30000000h
0x14002e21d  cmp     eax, 30000000h
0x14002e222  jnz     loc_14002E129
0x14002e228  jmp     loc_14002E104
0x14002e22d  mov     ebx, 0C0000225h
0x14002e232  lfence
0x14002e235  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e23c  lea     rbp, WPP_GLOBAL_Control
0x14002e243  cmp     rcx, rbp
0x14002e246  jnz     loc_14002E34B
0x14002e24c  mov     rsi, [rsp+0A8h+arg_10]
0x14002e254  mov     eax, ebx
0x14002e256  mov     r12, [rsp+0A8h+var_38]
0x14002e25b  jmp     loc_14002DF30
0x14002e260  test    r14b, 8
0x14002e264  jz      short loc_14002E28A
0x14002e266  mov     [rdi+20h], rsi
0x14002e26a  mov     esi, 1C0001h
0x14002e26f  mov     dword ptr [rdi+18h], 0C0000022h
0x14002e276  test    r15b, r15b
0x14002e279  jz      short loc_14002E28A
0x14002e27b  test    r14b, 2
0x14002e27f  jnz     short loc_14002E294
0x14002e281  test    r15b, r15b
0x14002e284  jnz     loc_14002E048
0x14002e28a  test    r14b, 10h
0x14002e28e  jz      loc_14002E048
0x14002e294  lea     r8, [rsp+0A8h+FileNameInformation]; FileNameInformation
0x14002e299  mov     [rsp+0A8h+FileNameInformation], 0
0x14002e2a2  mov     edx, 101h; NameOptions
0x14002e2a7  mov     rcx, rdi; CallbackData
0x14002e2aa  call    cs:__imp_FltGetFileNameInformation
0x14002e2b1  nop     dword ptr [rax+rax+00h]
0x14002e2b6  test    eax, eax
0x14002e2b8  jns     short loc_14002E2F0
0x14002e2ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e2c1  cmp     rcx, rbp
0x14002e2c4  jz      short loc_14002E2F0
0x14002e2c6  mov     ecx, [rcx+2Ch]
0x14002e2c9  test    cl, 2
0x14002e2cc  jz      short loc_14002E2F0
0x14002e2ce  lfence
0x14002e2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e2d8  lea     r8, WPP_3ac2d441938b3ccb0af7fdd108b4c5f3_Traceguids
0x14002e2df  mov     edx, 0Ch
0x14002e2e4  mov     r9d, eax
0x14002e2e7  mov     rcx, [rcx+18h]
0x14002e2eb  call    WPP_SF_d
0x14002e2f0  mov     rdx, [rsp+0A8h+FileNameInformation]
0x14002e2f5  movzx   r9d, r15b
0x14002e2f9  mov     r8d, r14d
0x14002e2fc  mov     rcx, rbx
0x14002e2ff  call    MpTracePPLRedux
0x14002e304  mov     rcx, [rsp+0A8h+FileNameInformation]; FileNameInformation
0x14002e309  test    rcx, rcx
0x14002e30c  jz      loc_14002E048
0x14002e312  call    cs:__imp_FltReleaseFileNameInformation
0x14002e319  nop     dword ptr [rax+rax+00h]
0x14002e31e  jmp     loc_14002E048
0x14002e323  mov     rcx, cs:MpProcessTable
0x14002e32a  add     rcx, 8; Resource
0x14002e32e  call    cs:__imp_ExReleaseResourceLite
0x14002e335  nop     dword ptr [rax+rax+00h]
0x14002e33a  call    cs:__imp_KeLeaveCriticalRegion
0x14002e341  nop     dword ptr [rax+rax+00h]
0x14002e346  jmp     loc_14002E22D
0x14002e34b  mov     edx, [rcx+2Ch]
0x14002e34e  test    dl, 1
0x14002e351  jz      loc_14002E24C
0x14002e357  mov     rcx, [rcx+18h]
0x14002e35b  lea     r8, WPP_3ac2d441938b3ccb0af7fdd108b4c5f3_Traceguids
0x14002e362  mov     edx, 0Ah
0x14002e367  mov     r9d, ebx
0x14002e36a  call    WPP_SF_d
0x14002e36f  jmp     loc_14002E24C
0x14002e374  mov     eax, 0C000000Dh
0x14002e379  jmp     loc_14002DF30
```
