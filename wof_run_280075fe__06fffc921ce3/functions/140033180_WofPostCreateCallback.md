# WofPostCreateCallback

- ea: `0x140033180`
- end: `0x1400338d2`
- name: `WofPostCreateCallback`
- size: `1874`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callees

- `0x1400014d0`
- `0x140007740`
- `0x140009910`
- `0x14000b938`
- `0x14000ba78`
- `0x14000dc88`
- `0x14000e198`
- `0x14000e27c`
- `0x140011542`
- `0x140011560`
- `0x140011640`
- `0x140022b54`
- `0x140033180`
- `0x1400338e0`
- `0x140034f50`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400333b7`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033742`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400338c1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400333b7`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033742`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400338c1`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140033246`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140033246`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033339`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033339`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140033209`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140033209`
- `FLTMGR!FltCancelFileOpen` at `0x140033837`
- `FLTMGR!FltCancelFileOpen` at `0x140033899`
- `FLTMGR!FltCancelFileOpen` at `0x140033837`
- `FLTMGR!FltCancelFileOpen` at `0x140033899`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140033230`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140033230`
- `FLTMGR!FltFsControlFile` at `0x14003364a`
- `FLTMGR!FltFsControlFile` at `0x14003364a`
- `FLTMGR!FltGetStreamContext` at `0x140033593`
- `FLTMGR!FltGetStreamContext` at `0x140033593`
- `FLTMGR!FltReleaseContext` at `0x140033324`
- `FLTMGR!FltReleaseContext` at `0x1400333a6`
- `FLTMGR!FltReleaseContext` at `0x140033755`
- `FLTMGR!FltReleaseContext` at `0x140033324`
- `FLTMGR!FltReleaseContext` at `0x1400333a6`
- `FLTMGR!FltReleaseContext` at `0x140033755`

## pseudocode

```c
__int64 __fastcall WofPostCreateCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _BYTE *a3)
{
  __int64 v4; // rax
  char v5; // r15
  PFLT_CONTEXT v6; // rbx
  struct _EX_RUNDOWN_REF *v7; // rsi
  struct _EX_RUNDOWN_REF *v8; // r12
  unsigned __int64 v10; // rcx
  unsigned __int64 v12; // rax
  void *v13; // rsp
  int v14; // r8d
  NTSTATUS Status; // edx
  struct _FILE_OBJECT *v16; // r9
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PFLT_INSTANCE *v18; // rdi
  NTSTATUS v19; // eax
  ULONG *p_SortKey; // r8
  int v21; // r9d
  char v22; // cl
  int v24; // edx
  int IsDataAlternateStream; // r15d
  char v26; // r15
  int v27; // r8d
  __int64 Count; // rax
  int OpenContext; // eax
  int v30; // edx
  NTSTATUS v31; // r15d
  ULONG_PTR Information; // rdx
  _DWORD *v33; // r15
  unsigned int v34; // ecx
  __int64 v35; // rax
  __int64 v36; // rax
  int (__fastcall *v37)(char *, _QWORD, ULONG *); // rax
  char *v38; // r15
  PFLT_IO_PARAMETER_BLOCK v39; // rdx
  PFILE_OBJECT TargetFileObject; // rax
  int InputBufferLength; // [rsp+20h] [rbp-30h]
  char LengthReturned; // [rsp+38h] [rbp-18h]
  char v43; // [rsp+50h] [rbp+0h] BYREF
  char v44; // [rsp+51h] [rbp+1h]
  PFLT_CONTEXT v45; // [rsp+58h] [rbp+8h] BYREF
  int v46; // [rsp+60h] [rbp+10h]
  PFLT_INSTANCE *v47; // [rsp+68h] [rbp+18h]
  ULONG v48; // [rsp+70h] [rbp+20h] BYREF
  _BYTE OutputBufferLength[12]; // [rsp+74h] [rbp+24h] BYREF
  __int64 v50; // [rsp+80h] [rbp+30h] BYREF
  PVOID OutputBuffer; // [rsp+88h] [rbp+38h]
  char *v52; // [rsp+90h] [rbp+40h]
  PFLT_CONTEXT Context; // [rsp+98h] [rbp+48h]

  v4 = (unsigned int)(dword_140018448 + 16);
  v5 = 0;
  v48 = 0;
  v6 = 0;
  Context = 0;
  v7 = 0;
  v50 = 0;
  v45 = 0;
  v8 = 0;
  *(_DWORD *)&OutputBufferLength[8] = 0;
  v10 = (unsigned int)v4;
  *(_QWORD *)OutputBufferLength = v4;
  v12 = v4 + 15;
  v44 = 0;
  if ( v12 <= v10 )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = alloca(v12 & 0xFFFFFFFFFFFFFFF0uLL);
  OutputBuffer = &v43;
  KeEnterCriticalRegion();
  if ( a3 )
  {
    v5 = a3[20] & 1;
    FltRemoveOpenReparseEntry(WofGlobal, CallbackData, a3);
    ExFreeToPagedLookasideList(&Lookaside, a3);
  }
  Status = CallbackData->IoStatus.Status;
  if ( Status < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(Status) = 5;
      WPP_RECORDER_SF_qd(WPP_GLOBAL_Control->DeviceExtension, Status, v14, 12);
    }
  }
  else
  {
    v16 = *(struct _FILE_OBJECT **)(a2 + 32);
    if ( (v16->Flags & 0x400000) == 0 )
    {
      if ( Status == 260 )
        goto LABEL_21;
      Iopb = CallbackData->Iopb;
      v18 = (PFLT_INSTANCE *)(a2 + 24);
      v52 = 0;
      v47 = (PFLT_INSTANCE *)(a2 + 24);
      v46 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
      if ( !v5 )
        goto LABEL_9;
      if ( FltGetStreamContext(*v18, v16, &v45) >= 0 )
      {
        v43 = 1;
        if ( (*((_DWORD *)v45 + 2) & 1) != 0 && CallbackData->IoStatus.Information == 1 )
        {
          if ( (int)WofIsDataInFilesystemEx(v45, a2, &v43, &OutputBufferLength[4]) >= 0
            && !v43
            && (*(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 106 * *((unsigned int *)v45 + 3) + 6) & v46) == 0 )
          {
            v8 = *(struct _EX_RUNDOWN_REF **)&OutputBufferLength[4];
            goto LABEL_57;
          }
          v8 = *(struct _EX_RUNDOWN_REF **)&OutputBufferLength[4];
          if ( *(_QWORD *)&OutputBufferLength[4] )
          {
            ExReleaseRundownProtection(*(PEX_RUNDOWN_REF *)&OutputBufferLength[4]);
            v8 = 0;
          }
        }
        FltReleaseContext(v45);
        v45 = 0;
LABEL_59:
        v33 = OutputBuffer;
        if ( FltFsControlFile(
               *v18,
               *(PFILE_OBJECT *)(a2 + 32),
               0x900A8u,
               0,
               0,
               OutputBuffer,
               *(ULONG *)OutputBufferLength,
               &v48) >= 0
          && *v33 == FileTag )
        {
          v34 = *((unsigned __int16 *)v33 + 2);
          if ( v34 >= 8 && v33[2] == 1 )
          {
            v35 = (unsigned int)v33[3];
            if ( (unsigned int)v35 < 4 )
            {
              v36 = 424 * v35;
              p_SortKey = &WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey;
              if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v36) )
              {
                v37 = *(int (__fastcall **)(char *, _QWORD, ULONG *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                    + v36
                                                                    + 344);
                v38 = (char *)(v33 + 4);
                LOBYTE(p_SortKey) = 1;
                v52 = v38;
                if ( v37(v38, v34 - 8, p_SortKey) >= 0 )
                {
                  if ( v38 )
                    goto LABEL_27;
                }
                else
                {
                  v52 = 0;
                }
              }
            }
          }
        }
        if ( !v45 && CallbackData->IoStatus.Information == 1 )
        {
          v47 = (PFLT_INSTANCE *)(a2 + 24);
LABEL_9:
          WofGetVolumeContext(*v18);
          v6 = Context;
          v19 = WofLocateInNamedScope(CallbackData, Context, &v50);
          v7 = (struct _EX_RUNDOWN_REF *)v50;
          if ( v19 >= 0 )
          {
            *((_DWORD *)OutputBuffer + 3) = *(_DWORD *)(v50 + 40);
            v22 = 1;
          }
          else
          {
            v22 = 0;
            if ( v19 != -1073741772 )
            {
              v7 = (struct _EX_RUNDOWN_REF *)v50;
              CallbackData->IoStatus.Status = v19;
              CallbackData->IoStatus.Information = 0;
              goto LABEL_15;
            }
          }
          if ( !v22 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              v39 = CallbackData->Iopb;
              LengthReturned = HIBYTE(v39->Parameters.SetVolumeInformation.FsInformationClass);
              TargetFileObject = v39->TargetFileObject;
              LOBYTE(v39) = 5;
              WPP_RECORDER_SF_qll(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)v39,
                (_DWORD)p_SortKey,
                14,
                InputBufferLength,
                (char)TargetFileObject,
                CallbackData->IoStatus.Information,
                LengthReturned);
            }
            goto LABEL_15;
          }
LABEL_27:
          if ( v45 && (*((_DWORD *)v45 + 2) & 1) != 0 )
          {
            v26 = (*((_DWORD *)v45 + 2) & 2) != 0;
          }
          else
          {
            IsDataAlternateStream = WofIsDataAlternateStream(CallbackData);
            if ( IsDataAlternateStream < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v24) = 2;
                WPP_RECORDER_SF_d(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v24,
                  5,
                  10,
                  (__int64)WPP_29117806511237e02a674e96f7110bad_Traceguids,
                  IsDataAlternateStream);
              }
              FltCancelFileOpen(*v47, *(PFILE_OBJECT *)(a2 + 32));
              CallbackData->IoStatus.Status = IsDataAlternateStream;
              CallbackData->IoStatus.Information = 0;
              goto LABEL_15;
            }
            v26 = v44;
          }
          if ( !v26 )
          {
            Information = CallbackData->IoStatus.Information;
            if ( Information != 1 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(Information) = 4;
                WPP_RECORDER_SF_qll(
                  WPP_GLOBAL_Control->DeviceExtension,
                  Information,
                  (_DWORD)p_SortKey,
                  15,
                  InputBufferLength,
                  (char)CallbackData->Iopb->TargetFileObject,
                  CallbackData->IoStatus.Information,
                  HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass));
              }
              WofDoNotTrackOpen(a2);
              goto LABEL_15;
            }
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_qllLL(
              WPP_GLOBAL_Control->DeviceExtension,
              CallbackData->Iopb,
              v46,
              v21,
              InputBufferLength,
              (char)CallbackData->Iopb->TargetFileObject,
              CallbackData->IoStatus.Information,
              HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
              CallbackData->Iopb->Parameters.Create.ShareAccess,
              v46);
          if ( v26 )
          {
            v27 = -1;
          }
          else if ( v45 )
          {
            v27 = *((_DWORD *)v45 + 3);
          }
          else
          {
            v27 = *((_DWORD *)OutputBuffer + 3);
          }
          if ( v7 )
            Count = v7[6].Count;
          else
            Count = 0;
          OpenContext = WofCreateOpenContext((_DWORD)CallbackData, a2, v27, (_DWORD)v52, Count, v46, v26, 0);
          v31 = OpenContext;
          if ( OpenContext < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v30) = 2;
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v30,
                5,
                10,
                (__int64)WPP_29117806511237e02a674e96f7110bad_Traceguids,
                OpenContext);
            }
            FltCancelFileOpen(*v47, *(PFILE_OBJECT *)(a2 + 32));
            CallbackData->IoStatus.Status = v31;
            CallbackData->IoStatus.Information = 0;
            goto LABEL_39;
          }
          if ( OpenContext != 51314689 )
          {
LABEL_39:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v30) = 4;
              WPP_RECORDER_SF_q(
                WPP_GLOBAL_Control->DeviceExtension,
                v30,
                5,
                17,
                (__int64)WPP_29117806511237e02a674e96f7110bad_Traceguids,
                (char)CallbackData->Iopb->TargetFileObject);
            }
          }
LABEL_15:
          if ( v7 )
            ExReleaseRundownProtection(v7 + 2);
          if ( v8 )
            ExReleaseRundownProtection(v8);
          if ( v6 )
            FltReleaseContext(v6);
          goto LABEL_21;
        }
LABEL_58:
        v47 = (PFLT_INSTANCE *)(a2 + 24);
        goto LABEL_27;
      }
LABEL_57:
      if ( v45 )
        goto LABEL_58;
      goto LABEL_59;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        5,
        13,
        (__int64)WPP_29117806511237e02a674e96f7110bad_Traceguids,
        (char)CallbackData->Iopb->TargetFileObject);
  }
LABEL_21:
  if ( v45 )
    FltReleaseContext(v45);
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x140033180  push    rbp
0x140033182  push    rbx
0x140033183  push    rsi
0x140033184  push    rdi
0x140033185  push    r12
0x140033187  push    r13
0x140033189  push    r14
0x14003318b  push    r15
0x14003318d  sub     rsp, 0B8h
0x140033194  lea     rbp, [rsp+50h]
0x140033199  mov     rax, cs:__security_cookie
0x1400331a0  xor     rax, rbp
0x1400331a3  mov     [rbp+0A0h+var_50], rax
0x1400331a7  mov     eax, cs:dword_140018448
0x1400331ad  mov     r14, rcx
0x1400331b0  xor     ecx, ecx
0x1400331b2  add     eax, 10h
0x1400331b5  xor     r15b, r15b
0x1400331b8  mov     [rbp+0A0h+var_80], ecx
0x1400331bb  mov     ebx, ecx
0x1400331bd  mov     [rbp+0A0h+Context], rcx
0x1400331c1  mov     esi, ecx
0x1400331c3  mov     [rbp+0A0h+var_70], rcx
0x1400331c7  mov     [rbp+0A0h+var_98], rcx
0x1400331cb  mov     r12d, ecx
0x1400331ce  mov     [rbp+0A0h+RunRef], rcx
0x1400331d2  mov     rdi, r8
0x1400331d5  mov     ecx, eax
0x1400331d7  mov     r13, rdx
0x1400331da  mov     [rbp+0A0h+var_7C], eax
0x1400331dd  add     rax, 0Fh
0x1400331e1  mov     [rbp+0A0h+var_9F], r15b
0x1400331e5  cmp     rax, rcx
0x1400331e8  ja      short loc_1400331F4
0x1400331ea  mov     rax, 0FFFFFFFFFFFFFF0h
0x1400331f4  and     rax, 0FFFFFFFFFFFFFFF0h
0x1400331f8  call    __chkstk_0
0x1400331fd  sub     rsp, rax
0x140033200  lea     rax, [rsp+0F0h+var_A0]
0x140033205  mov     [rbp+0A0h+var_68], rax
0x140033209  call    cs:__imp_KeEnterCriticalRegion
0x140033210  nop     dword ptr [rax+rax+00h]
0x140033215  test    rdi, rdi
0x140033218  jz      short loc_140033252
0x14003321a  movzx   r15d, byte ptr [rdi+14h]
0x14003321f  mov     r8, rdi
0x140033222  mov     rcx, cs:WofGlobal
0x140033229  mov     rdx, r14
0x14003322c  and     r15b, 1
0x140033230  call    cs:__imp_FltRemoveOpenReparseEntry
0x140033237  nop     dword ptr [rax+rax+00h]
0x14003323c  mov     rdx, rdi; Entry
0x14003323f  lea     rcx, Lookaside; Lookaside
0x140033246  call    cs:__imp_ExFreeToPagedLookasideList
0x14003324d  nop     dword ptr [rax+rax+00h]
0x140033252  mov     edx, [r14+18h]
0x140033256  test    edx, edx
0x140033258  js      loc_140033365
0x14003325e  mov     r9, [r13+20h]
0x140033262  test    dword ptr [r9+50h], 400000h
0x14003326a  jnz     loc_1400336DA
0x140033270  cmp     edx, 104h
0x140033276  jz      loc_140033330
0x14003327c  mov     rax, [r14+10h]
0x140033280  lea     rdi, [r13+18h]
0x140033284  mov     [rbp+0A0h+var_60], rbx
0x140033288  mov     [rbp+0A0h+var_88], rdi
0x14003328c  mov     rcx, [rax+18h]
0x140033290  mov     eax, [rcx+10h]
0x140033293  mov     [rbp+0A0h+var_90], eax
0x140033296  test    r15b, r15b
0x140033299  jnz     loc_140033589
0x14003329f  mov     rcx, [rdi]; Instance
0x1400332a2  lea     rdx, [rbp+0A0h+Context]
0x1400332a6  call    WofGetVolumeContext
0x1400332ab  mov     rbx, [rbp+0A0h+Context]
0x1400332af  lea     r8, [rbp+0A0h+var_70]
0x1400332b3  mov     rdx, rbx
0x1400332b6  mov     rcx, r14
0x1400332b9  call    WofLocateInNamedScope
0x1400332be  mov     rsi, [rbp+0A0h+var_70]
0x1400332c2  test    eax, eax
0x1400332c4  jns     loc_140033794
0x1400332ca  xor     cl, cl
0x1400332cc  cmp     eax, 0C0000034h
0x1400332d1  jnz     loc_1400337A5
0x1400332d7  test    r15b, r15b
0x1400332da  jnz     loc_140033614
0x1400332e0  test    cl, cl
0x1400332e2  jnz     loc_1400333C8
0x1400332e8  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400332ef  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400332f6  jz      short loc_14003330A
0x1400332f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400332ff  cmp     word ptr [rcx+48h], 0
0x140033304  jnz     loc_1400337BA
0x14003330a  test    rsi, rsi
0x14003330d  jnz     loc_1400338BD
0x140033313  test    r12, r12
0x140033316  jnz     loc_1400333B4
0x14003331c  test    rbx, rbx
0x14003331f  jz      short loc_140033330
0x140033321  mov     rcx, rbx; Context
0x140033324  call    cs:__imp_FltReleaseContext
0x14003332b  nop     dword ptr [rax+rax+00h]
0x140033330  mov     rcx, [rbp+0A0h+var_98]; Context
0x140033334  test    rcx, rcx
0x140033337  jnz     short loc_1400333A6
0x140033339  call    cs:__imp_KeLeaveCriticalRegion
0x140033340  nop     dword ptr [rax+rax+00h]
0x140033345  xor     eax, eax
0x140033347  mov     rcx, [rbp+0A0h+var_50]
0x14003334b  xor     rcx, rbp; StackCookie
0x14003334e  call    __security_check_cookie
0x140033353  lea     rsp, [rbp+68h]
0x140033357  pop     r15
0x140033359  pop     r14
0x14003335b  pop     r13
0x14003335d  pop     r12
0x14003335f  pop     rdi
0x140033360  pop     rsi
0x140033361  pop     rbx
0x140033362  pop     rbp
0x140033363  retn
0x140033365  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003336c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033373  jz      short loc_140033330
0x140033375  mov     rcx, cs:WPP_GLOBAL_Control
0x14003337c  cmp     [rcx+48h], bx
0x140033380  jz      short loc_140033330
0x140033382  mov     rax, [r14+10h]
0x140033386  mov     r9d, 0Ch
0x14003338c  mov     rcx, [rcx+40h]
0x140033390  mov     [rsp+0F0h+OutputBufferLength], edx
0x140033394  mov     dl, 5
0x140033396  mov     rax, [rax+8]
0x14003339a  mov     [rsp+0F0h+OutputBuffer], rax
0x14003339f  call    WPP_RECORDER_SF_qd
0x1400333a4  jmp     short loc_140033330
0x1400333a6  call    cs:__imp_FltReleaseContext
0x1400333ad  nop     dword ptr [rax+rax+00h]
0x1400333b2  jmp     short loc_140033339
0x1400333b4  mov     rcx, r12; RunRef
0x1400333b7  call    cs:__imp_ExReleaseRundownProtection
0x1400333be  nop     dword ptr [rax+rax+00h]
0x1400333c3  jmp     loc_14003331C
0x1400333c8  mov     rax, [rbp+0A0h+var_98]
0x1400333cc  test    rax, rax
0x1400333cf  jnz     loc_14003356A
0x1400333d5  lea     rdx, [rbp+0A0h+var_9F]
0x1400333d9  mov     rcx, r14; CallbackData
0x1400333dc  call    WofIsDataAlternateStream
0x1400333e1  mov     r15d, eax
0x1400333e4  test    eax, eax
0x1400333e6  js      loc_1400337ED
0x1400333ec  movzx   r15d, [rbp+0A0h+var_9F]
0x1400333f1  test    r15b, r15b
0x1400333f4  jz      loc_1400334AC
0x1400333fa  lea     rdi, WPP_RECORDER_INITIALIZED
0x140033401  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033408  jnz     loc_14003351A
0x14003340e  test    r15b, r15b
0x140033411  jz      loc_140033508
0x140033417  mov     r8d, 0FFFFFFFFh
0x14003341d  test    rsi, rsi
0x140033420  jnz     loc_140033854
0x140033426  xor     eax, eax
0x140033428  mov     ecx, [rbp+0A0h+var_90]
0x14003342b  mov     rdx, r13
0x14003342e  mov     r9, [rbp+0A0h+var_60]
0x140033432  mov     byte ptr [rsp+0F0h+LengthReturned], 0
0x140033437  mov     byte ptr [rsp+0F0h+OutputBufferLength], r15b
0x14003343c  mov     dword ptr [rsp+0F0h+OutputBuffer], ecx
0x140033440  mov     rcx, r14
0x140033443  mov     qword ptr [rsp+0F0h+InputBufferLength], rax
0x140033448  call    WofCreateOpenContext
0x14003344d  lea     rcx, WPP_29117806511237e02a674e96f7110bad_Traceguids
0x140033454  mov     r15d, eax
0x140033457  test    eax, eax
0x140033459  js      loc_14003385D
0x14003345f  cmp     eax, 30F0001h
0x140033464  jz      loc_14003330A
0x14003346a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033471  jz      loc_14003330A
0x140033477  mov     rax, [r14+10h]
0x14003347b  mov     r9d, 11h
0x140033481  mov     r8d, 5
0x140033487  mov     dl, 4
0x140033489  mov     rax, [rax+8]
0x14003348d  mov     [rsp+0F0h+OutputBuffer], rax
0x140033492  mov     qword ptr [rsp+0F0h+InputBufferLength], rcx
0x140033497  mov     rcx, cs:WPP_GLOBAL_Control
0x14003349e  mov     rcx, [rcx+40h]
0x1400334a2  call    WPP_RECORDER_SF_q
0x1400334a7  jmp     loc_14003330A
0x1400334ac  mov     rdx, [r14+20h]
0x1400334b0  cmp     rdx, 1
0x1400334b4  jz      loc_1400333FA
0x1400334ba  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400334c1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400334c8  jz      short loc_1400334FB
0x1400334ca  mov     rcx, [r14+10h]
0x1400334ce  mov     r9d, 0Fh
0x1400334d4  movzx   eax, byte ptr [rcx+23h]
0x1400334d8  mov     dword ptr [rsp+0F0h+LengthReturned], eax
0x1400334dc  mov     rax, [rcx+8]
0x1400334e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400334e7  mov     [rsp+0F0h+OutputBufferLength], edx
0x1400334eb  mov     dl, 4
0x1400334ed  mov     [rsp+0F0h+OutputBuffer], rax
0x1400334f2  mov     rcx, [rcx+40h]
0x1400334f6  call    WPP_RECORDER_SF_qll
0x1400334fb  mov     rcx, r13
0x1400334fe  call    WofDoNotTrackOpen
0x140033503  jmp     loc_14003330A
0x140033508  mov     r8, [rbp+0A0h+var_98]
0x14003350c  test    r8, r8
0x14003350f  jz      short loc_14003355D
0x140033511  mov     r8d, [r8+0Ch]
0x140033515  jmp     loc_14003341D
0x14003351a  mov     rdx, [r14+10h]
0x14003351e  mov     r8d, [rbp+0A0h+var_90]
0x140033522  mov     [rsp+0F0h+var_A8], r8d
0x140033527  movzx   eax, word ptr [rdx+2Ah]
0x14003352b  movzx   ecx, byte ptr [rdx+23h]
0x14003352f  mov     [rsp+0F0h+var_B0], eax
0x140033533  mov     eax, [r14+20h]
0x140033537  mov     dword ptr [rsp+0F0h+LengthReturned], ecx
0x14003353b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033542  mov     [rsp+0F0h+OutputBufferLength], eax
0x140033546  mov     rax, [rdx+8]
0x14003354a  mov     [rsp+0F0h+OutputBuffer], rax
0x14003354f  mov     rcx, [rcx+40h]
0x140033553  call    WPP_RECORDER_SF_qllLL
0x140033558  jmp     loc_14003340E
0x14003355d  mov     rax, [rbp+0A0h+var_68]
0x140033561  mov     r8d, [rax+0Ch]
0x140033565  jmp     loc_14003341D
0x14003356a  mov     eax, [rax+8]
0x14003356d  test    al, 1
0x14003356f  jz      loc_1400333D5
0x140033575  mov     rax, [rbp+0A0h+var_98]
0x140033579  mov     r15d, [rax+8]
0x14003357d  shr     r15d, 1
0x140033580  and     r15b, 1
0x140033584  jmp     loc_1400333F1
0x140033589  mov     rcx, [rdi]; Instance
0x14003358c  lea     r8, [rbp+0A0h+var_98]; Context
0x140033590  mov     rdx, r9; FileObject
0x140033593  call    cs:__imp_FltGetStreamContext
0x14003359a  nop     dword ptr [rax+rax+00h]
0x14003359f  lea     r15, WPP_MAIN_CB.Queue+10h
0x1400335a6  test    eax, eax
0x1400335a8  js      short loc_14003360E
0x1400335aa  mov     rax, [rbp+0A0h+var_98]
0x1400335ae  mov     [rbp+0A0h+var_A0], 1
0x1400335b2  mov     ecx, [rax+8]
0x1400335b5  test    cl, 1
0x1400335b8  jz      loc_140033751
0x1400335be  cmp     qword ptr [r14+20h], 1
0x1400335c3  jnz     loc_140033751
0x1400335c9  mov     rcx, [rbp+0A0h+var_98]
0x1400335cd  lea     r9, [rbp+0A0h+RunRef]
0x1400335d1  lea     r8, [rbp+0A0h+var_A0]
0x1400335d5  mov     rdx, r13
0x1400335d8  call    WofIsDataInFilesystemEx
0x1400335dd  test    eax, eax
0x1400335df  js      loc_140033736
0x1400335e5  cmp     [rbp+0A0h+var_A0], bl
0x1400335e8  jnz     loc_140033736
0x1400335ee  mov     rax, [rbp+0A0h+var_98]
0x1400335f2  mov     ecx, [rax+0Ch]
0x1400335f5  imul    rax, rcx, 1A8h
0x1400335fc  mov     eax, [rax+r15+18h]
0x140033601  test    [rbp+0A0h+var_90], eax
0x140033604  jnz     loc_140033736
0x14003360a  mov     r12, [rbp+0A0h+RunRef]
0x14003360e  cmp     [rbp+0A0h+var_98], rbx
0x140033612  jz      short loc_14003361D
0x140033614  mov     [rbp+0A0h+var_88], rdi
0x140033618  jmp     loc_1400333C8
0x14003361d  mov     r15, [rbp+0A0h+var_68]
0x140033621  lea     rax, [rbp+0A0h+var_80]
0x140033625  mov     rdx, [r13+20h]; FileObject
0x140033629  xor     r9d, r9d; InputBuffer
0x14003362c  mov     rcx, [rdi]; Instance
0x14003362f  mov     r8d, 900A8h; FsControlCode
0x140033635  mov     [rsp+0F0h+LengthReturned], rax; LengthReturned
0x14003363a  mov     eax, [rbp+0A0h+var_7C]
0x14003363d  mov     [rsp+0F0h+OutputBufferLength], eax; OutputBufferLength
0x140033641  mov     [rsp+0F0h+OutputBuffer], r15; OutputBuffer
0x140033646  mov     [rsp+0F0h+InputBufferLength], ebx; InputBufferLength
0x14003364a  call    cs:__imp_FltFsControlFile
0x140033651  nop     dword ptr [rax+rax+00h]
0x140033656  test    eax, eax
0x140033658  js      loc_140033773
0x14003365e  mov     eax, cs:FileTag
0x140033664  cmp     [r15], eax
0x140033667  jnz     loc_140033773
0x14003366d  movzx   ecx, word ptr [r15+4]
  ... truncated ...
```
