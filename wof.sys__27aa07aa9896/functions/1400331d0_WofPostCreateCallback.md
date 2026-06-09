# WofPostCreateCallback

- ea: `0x1400331d0`
- end: `0x140033922`
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
- `0x1400331d0`
- `0x140033930`
- `0x140034fa0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140033407`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033792`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033911`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033407`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033792`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033911`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140033296`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140033296`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033389`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033389`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140033259`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140033259`
- `FLTMGR!FltCancelFileOpen` at `0x140033887`
- `FLTMGR!FltCancelFileOpen` at `0x1400338e9`
- `FLTMGR!FltCancelFileOpen` at `0x140033887`
- `FLTMGR!FltCancelFileOpen` at `0x1400338e9`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140033280`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140033280`
- `FLTMGR!FltFsControlFile` at `0x14003369a`
- `FLTMGR!FltFsControlFile` at `0x14003369a`
- `FLTMGR!FltGetStreamContext` at `0x1400335e3`
- `FLTMGR!FltGetStreamContext` at `0x1400335e3`
- `FLTMGR!FltReleaseContext` at `0x140033374`
- `FLTMGR!FltReleaseContext` at `0x1400333f6`
- `FLTMGR!FltReleaseContext` at `0x1400337a5`
- `FLTMGR!FltReleaseContext` at `0x140033374`
- `FLTMGR!FltReleaseContext` at `0x1400333f6`
- `FLTMGR!FltReleaseContext` at `0x1400337a5`

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
0x1400331d0  push    rbp
0x1400331d2  push    rbx
0x1400331d3  push    rsi
0x1400331d4  push    rdi
0x1400331d5  push    r12
0x1400331d7  push    r13
0x1400331d9  push    r14
0x1400331db  push    r15
0x1400331dd  sub     rsp, 0B8h
0x1400331e4  lea     rbp, [rsp+50h]
0x1400331e9  mov     rax, cs:__security_cookie
0x1400331f0  xor     rax, rbp
0x1400331f3  mov     [rbp+0A0h+var_50], rax
0x1400331f7  mov     eax, cs:dword_140018448
0x1400331fd  mov     r14, rcx
0x140033200  xor     ecx, ecx
0x140033202  add     eax, 10h
0x140033205  xor     r15b, r15b
0x140033208  mov     [rbp+0A0h+var_80], ecx
0x14003320b  mov     ebx, ecx
0x14003320d  mov     [rbp+0A0h+Context], rcx
0x140033211  mov     esi, ecx
0x140033213  mov     [rbp+0A0h+var_70], rcx
0x140033217  mov     [rbp+0A0h+var_98], rcx
0x14003321b  mov     r12d, ecx
0x14003321e  mov     [rbp+0A0h+RunRef], rcx
0x140033222  mov     rdi, r8
0x140033225  mov     ecx, eax
0x140033227  mov     r13, rdx
0x14003322a  mov     [rbp+0A0h+var_7C], eax
0x14003322d  add     rax, 0Fh
0x140033231  mov     [rbp+0A0h+var_9F], r15b
0x140033235  cmp     rax, rcx
0x140033238  ja      short loc_140033244
0x14003323a  mov     rax, 0FFFFFFFFFFFFFF0h
0x140033244  and     rax, 0FFFFFFFFFFFFFFF0h
0x140033248  call    __chkstk_0
0x14003324d  sub     rsp, rax
0x140033250  lea     rax, [rsp+0F0h+var_A0]
0x140033255  mov     [rbp+0A0h+var_68], rax
0x140033259  call    cs:__imp_KeEnterCriticalRegion
0x140033260  nop     dword ptr [rax+rax+00h]
0x140033265  test    rdi, rdi
0x140033268  jz      short loc_1400332A2
0x14003326a  movzx   r15d, byte ptr [rdi+14h]
0x14003326f  mov     r8, rdi
0x140033272  mov     rcx, cs:WofGlobal
0x140033279  mov     rdx, r14
0x14003327c  and     r15b, 1
0x140033280  call    cs:__imp_FltRemoveOpenReparseEntry
0x140033287  nop     dword ptr [rax+rax+00h]
0x14003328c  mov     rdx, rdi; Entry
0x14003328f  lea     rcx, Lookaside; Lookaside
0x140033296  call    cs:__imp_ExFreeToPagedLookasideList
0x14003329d  nop     dword ptr [rax+rax+00h]
0x1400332a2  mov     edx, [r14+18h]
0x1400332a6  test    edx, edx
0x1400332a8  js      loc_1400333B5
0x1400332ae  mov     r9, [r13+20h]
0x1400332b2  test    dword ptr [r9+50h], 400000h
0x1400332ba  jnz     loc_14003372A
0x1400332c0  cmp     edx, 104h
0x1400332c6  jz      loc_140033380
0x1400332cc  mov     rax, [r14+10h]
0x1400332d0  lea     rdi, [r13+18h]
0x1400332d4  mov     [rbp+0A0h+var_60], rbx
0x1400332d8  mov     [rbp+0A0h+var_88], rdi
0x1400332dc  mov     rcx, [rax+18h]
0x1400332e0  mov     eax, [rcx+10h]
0x1400332e3  mov     [rbp+0A0h+var_90], eax
0x1400332e6  test    r15b, r15b
0x1400332e9  jnz     loc_1400335D9
0x1400332ef  mov     rcx, [rdi]; Instance
0x1400332f2  lea     rdx, [rbp+0A0h+Context]
0x1400332f6  call    WofGetVolumeContext
0x1400332fb  mov     rbx, [rbp+0A0h+Context]
0x1400332ff  lea     r8, [rbp+0A0h+var_70]
0x140033303  mov     rdx, rbx
0x140033306  mov     rcx, r14
0x140033309  call    WofLocateInNamedScope
0x14003330e  mov     rsi, [rbp+0A0h+var_70]
0x140033312  test    eax, eax
0x140033314  jns     loc_1400337E4
0x14003331a  xor     cl, cl
0x14003331c  cmp     eax, 0C0000034h
0x140033321  jnz     loc_1400337F5
0x140033327  test    r15b, r15b
0x14003332a  jnz     loc_140033664
0x140033330  test    cl, cl
0x140033332  jnz     loc_140033418
0x140033338  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003333f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033346  jz      short loc_14003335A
0x140033348  mov     rcx, cs:WPP_GLOBAL_Control
0x14003334f  cmp     word ptr [rcx+48h], 0
0x140033354  jnz     loc_14003380A
0x14003335a  test    rsi, rsi
0x14003335d  jnz     loc_14003390D
0x140033363  test    r12, r12
0x140033366  jnz     loc_140033404
0x14003336c  test    rbx, rbx
0x14003336f  jz      short loc_140033380
0x140033371  mov     rcx, rbx; Context
0x140033374  call    cs:__imp_FltReleaseContext
0x14003337b  nop     dword ptr [rax+rax+00h]
0x140033380  mov     rcx, [rbp+0A0h+var_98]; Context
0x140033384  test    rcx, rcx
0x140033387  jnz     short loc_1400333F6
0x140033389  call    cs:__imp_KeLeaveCriticalRegion
0x140033390  nop     dword ptr [rax+rax+00h]
0x140033395  xor     eax, eax
0x140033397  mov     rcx, [rbp+0A0h+var_50]
0x14003339b  xor     rcx, rbp; StackCookie
0x14003339e  call    __security_check_cookie
0x1400333a3  lea     rsp, [rbp+68h]
0x1400333a7  pop     r15
0x1400333a9  pop     r14
0x1400333ab  pop     r13
0x1400333ad  pop     r12
0x1400333af  pop     rdi
0x1400333b0  pop     rsi
0x1400333b1  pop     rbx
0x1400333b2  pop     rbp
0x1400333b3  retn
0x1400333b5  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400333bc  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400333c3  jz      short loc_140033380
0x1400333c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400333cc  cmp     [rcx+48h], bx
0x1400333d0  jz      short loc_140033380
0x1400333d2  mov     rax, [r14+10h]
0x1400333d6  mov     r9d, 0Ch
0x1400333dc  mov     rcx, [rcx+40h]
0x1400333e0  mov     [rsp+0F0h+OutputBufferLength], edx
0x1400333e4  mov     dl, 5
0x1400333e6  mov     rax, [rax+8]
0x1400333ea  mov     [rsp+0F0h+OutputBuffer], rax
0x1400333ef  call    WPP_RECORDER_SF_qd
0x1400333f4  jmp     short loc_140033380
0x1400333f6  call    cs:__imp_FltReleaseContext
0x1400333fd  nop     dword ptr [rax+rax+00h]
0x140033402  jmp     short loc_140033389
0x140033404  mov     rcx, r12; RunRef
0x140033407  call    cs:__imp_ExReleaseRundownProtection
0x14003340e  nop     dword ptr [rax+rax+00h]
0x140033413  jmp     loc_14003336C
0x140033418  mov     rax, [rbp+0A0h+var_98]
0x14003341c  test    rax, rax
0x14003341f  jnz     loc_1400335BA
0x140033425  lea     rdx, [rbp+0A0h+var_9F]
0x140033429  mov     rcx, r14; CallbackData
0x14003342c  call    WofIsDataAlternateStream
0x140033431  mov     r15d, eax
0x140033434  test    eax, eax
0x140033436  js      loc_14003383D
0x14003343c  movzx   r15d, [rbp+0A0h+var_9F]
0x140033441  test    r15b, r15b
0x140033444  jz      loc_1400334FC
0x14003344a  lea     rdi, WPP_RECORDER_INITIALIZED
0x140033451  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033458  jnz     loc_14003356A
0x14003345e  test    r15b, r15b
0x140033461  jz      loc_140033558
0x140033467  mov     r8d, 0FFFFFFFFh
0x14003346d  test    rsi, rsi
0x140033470  jnz     loc_1400338A4
0x140033476  xor     eax, eax
0x140033478  mov     ecx, [rbp+0A0h+var_90]
0x14003347b  mov     rdx, r13
0x14003347e  mov     r9, [rbp+0A0h+var_60]
0x140033482  mov     byte ptr [rsp+0F0h+LengthReturned], 0
0x140033487  mov     byte ptr [rsp+0F0h+OutputBufferLength], r15b
0x14003348c  mov     dword ptr [rsp+0F0h+OutputBuffer], ecx
0x140033490  mov     rcx, r14
0x140033493  mov     qword ptr [rsp+0F0h+InputBufferLength], rax
0x140033498  call    WofCreateOpenContext
0x14003349d  lea     rcx, WPP_29117806511237e02a674e96f7110bad_Traceguids
0x1400334a4  mov     r15d, eax
0x1400334a7  test    eax, eax
0x1400334a9  js      loc_1400338AD
0x1400334af  cmp     eax, 30F0001h
0x1400334b4  jz      loc_14003335A
0x1400334ba  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400334c1  jz      loc_14003335A
0x1400334c7  mov     rax, [r14+10h]
0x1400334cb  mov     r9d, 11h
0x1400334d1  mov     r8d, 5
0x1400334d7  mov     dl, 4
0x1400334d9  mov     rax, [rax+8]
0x1400334dd  mov     [rsp+0F0h+OutputBuffer], rax
0x1400334e2  mov     qword ptr [rsp+0F0h+InputBufferLength], rcx
0x1400334e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400334ee  mov     rcx, [rcx+40h]
0x1400334f2  call    WPP_RECORDER_SF_q
0x1400334f7  jmp     loc_14003335A
0x1400334fc  mov     rdx, [r14+20h]
0x140033500  cmp     rdx, 1
0x140033504  jz      loc_14003344A
0x14003350a  lea     rdi, WPP_RECORDER_INITIALIZED
0x140033511  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033518  jz      short loc_14003354B
0x14003351a  mov     rcx, [r14+10h]
0x14003351e  mov     r9d, 0Fh
0x140033524  movzx   eax, byte ptr [rcx+23h]
0x140033528  mov     dword ptr [rsp+0F0h+LengthReturned], eax
0x14003352c  mov     rax, [rcx+8]
0x140033530  mov     rcx, cs:WPP_GLOBAL_Control
0x140033537  mov     [rsp+0F0h+OutputBufferLength], edx
0x14003353b  mov     dl, 4
0x14003353d  mov     [rsp+0F0h+OutputBuffer], rax
0x140033542  mov     rcx, [rcx+40h]
0x140033546  call    WPP_RECORDER_SF_qll
0x14003354b  mov     rcx, r13
0x14003354e  call    WofDoNotTrackOpen
0x140033553  jmp     loc_14003335A
0x140033558  mov     r8, [rbp+0A0h+var_98]
0x14003355c  test    r8, r8
0x14003355f  jz      short loc_1400335AD
0x140033561  mov     r8d, [r8+0Ch]
0x140033565  jmp     loc_14003346D
0x14003356a  mov     rdx, [r14+10h]
0x14003356e  mov     r8d, [rbp+0A0h+var_90]
0x140033572  mov     [rsp+0F0h+var_A8], r8d
0x140033577  movzx   eax, word ptr [rdx+2Ah]
0x14003357b  movzx   ecx, byte ptr [rdx+23h]
0x14003357f  mov     [rsp+0F0h+var_B0], eax
0x140033583  mov     eax, [r14+20h]
0x140033587  mov     dword ptr [rsp+0F0h+LengthReturned], ecx
0x14003358b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033592  mov     [rsp+0F0h+OutputBufferLength], eax
0x140033596  mov     rax, [rdx+8]
0x14003359a  mov     [rsp+0F0h+OutputBuffer], rax
0x14003359f  mov     rcx, [rcx+40h]
0x1400335a3  call    WPP_RECORDER_SF_qllLL
0x1400335a8  jmp     loc_14003345E
0x1400335ad  mov     rax, [rbp+0A0h+var_68]
0x1400335b1  mov     r8d, [rax+0Ch]
0x1400335b5  jmp     loc_14003346D
0x1400335ba  mov     eax, [rax+8]
0x1400335bd  test    al, 1
0x1400335bf  jz      loc_140033425
0x1400335c5  mov     rax, [rbp+0A0h+var_98]
0x1400335c9  mov     r15d, [rax+8]
0x1400335cd  shr     r15d, 1
0x1400335d0  and     r15b, 1
0x1400335d4  jmp     loc_140033441
0x1400335d9  mov     rcx, [rdi]; Instance
0x1400335dc  lea     r8, [rbp+0A0h+var_98]; Context
0x1400335e0  mov     rdx, r9; FileObject
0x1400335e3  call    cs:__imp_FltGetStreamContext
0x1400335ea  nop     dword ptr [rax+rax+00h]
0x1400335ef  lea     r15, WPP_MAIN_CB.Queue+10h
0x1400335f6  test    eax, eax
0x1400335f8  js      short loc_14003365E
0x1400335fa  mov     rax, [rbp+0A0h+var_98]
0x1400335fe  mov     [rbp+0A0h+var_A0], 1
0x140033602  mov     ecx, [rax+8]
0x140033605  test    cl, 1
0x140033608  jz      loc_1400337A1
0x14003360e  cmp     qword ptr [r14+20h], 1
0x140033613  jnz     loc_1400337A1
0x140033619  mov     rcx, [rbp+0A0h+var_98]
0x14003361d  lea     r9, [rbp+0A0h+RunRef]
0x140033621  lea     r8, [rbp+0A0h+var_A0]
0x140033625  mov     rdx, r13
0x140033628  call    WofIsDataInFilesystemEx
0x14003362d  test    eax, eax
0x14003362f  js      loc_140033786
0x140033635  cmp     [rbp+0A0h+var_A0], bl
0x140033638  jnz     loc_140033786
0x14003363e  mov     rax, [rbp+0A0h+var_98]
0x140033642  mov     ecx, [rax+0Ch]
0x140033645  imul    rax, rcx, 1A8h
0x14003364c  mov     eax, [rax+r15+18h]
0x140033651  test    [rbp+0A0h+var_90], eax
0x140033654  jnz     loc_140033786
0x14003365a  mov     r12, [rbp+0A0h+RunRef]
0x14003365e  cmp     [rbp+0A0h+var_98], rbx
0x140033662  jz      short loc_14003366D
0x140033664  mov     [rbp+0A0h+var_88], rdi
0x140033668  jmp     loc_140033418
0x14003366d  mov     r15, [rbp+0A0h+var_68]
0x140033671  lea     rax, [rbp+0A0h+var_80]
0x140033675  mov     rdx, [r13+20h]; FileObject
0x140033679  xor     r9d, r9d; InputBuffer
0x14003367c  mov     rcx, [rdi]; Instance
0x14003367f  mov     r8d, 900A8h; FsControlCode
0x140033685  mov     [rsp+0F0h+LengthReturned], rax; LengthReturned
0x14003368a  mov     eax, [rbp+0A0h+var_7C]
0x14003368d  mov     [rsp+0F0h+OutputBufferLength], eax; OutputBufferLength
0x140033691  mov     [rsp+0F0h+OutputBuffer], r15; OutputBuffer
0x140033696  mov     [rsp+0F0h+InputBufferLength], ebx; InputBufferLength
0x14003369a  call    cs:__imp_FltFsControlFile
0x1400336a1  nop     dword ptr [rax+rax+00h]
0x1400336a6  test    eax, eax
0x1400336a8  js      loc_1400337C3
0x1400336ae  mov     eax, cs:FileTag
0x1400336b4  cmp     [r15], eax
0x1400336b7  jnz     loc_1400337C3
0x1400336bd  movzx   ecx, word ptr [r15+4]
  ... truncated ...
```
