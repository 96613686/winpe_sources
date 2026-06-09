# Smb2ExecuteSetInfoReal

- ea: `0x1400792e0`
- end: `0x14007975a`
- name: `Smb2ExecuteSetInfoReal`
- size: `1146`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140085f40`

## callees

- `0x140005070`
- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x14000e340`
- `0x1400101f0`
- `0x1400152a0`
- `0x1400154b0`
- `0x1400172d0`
- `0x140019e6c`
- `0x1400222ec`
- `0x140022958`
- `0x140028e58`
- `0x140079130`
- `0x1400792e0`
- `0x14007a690`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140079741`
- `ntoskrnl!ZwClose` at `0x140079741`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097b2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097b2d`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140097b0f`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140097b0f`
- `ntoskrnl!IoCreateFileEx` at `0x140097af8`
- `ntoskrnl!IoCreateFileEx` at `0x140097af8`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400793ff`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140079620`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097908`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400979ea`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097b44`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400793ff`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140079620`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097908`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400979ea`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097b44`
- `ntoskrnl!NtSetInformationFile` at `0x14007939d`
- `ntoskrnl!NtSetInformationFile` at `0x14007939d`
- `ntoskrnl!NtSetEaFile` at `0x1400794b3`
- `ntoskrnl!NtSetEaFile` at `0x1400794b3`
- `ntoskrnl!NtSetVolumeInformationFile` at `0x1400979b0`
- `ntoskrnl!NtSetVolumeInformationFile` at `0x1400979b0`
- `ntoskrnl!NtSetSecurityObject` at `0x1400795e6`
- `ntoskrnl!NtSetSecurityObject` at `0x1400795e6`
- `ntoskrnl!NtSetQuotaInformationFile` at `0x1400978ce`
- `ntoskrnl!NtSetQuotaInformationFile` at `0x1400978ce`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteSetInfoReal(_QWORD *a1)
{
  __int64 v1; // rsi
  int v3; // ecx
  int v4; // r14d
  __int64 v5; // rdx
  NTSTATUS v6; // edi
  char v7; // r12
  struct _IO_STATUS_BLOCK *v8; // rdx
  ULONG v9; // r9d
  void *v10; // r8
  void *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  int v14; // edi
  __int64 v15; // rsi
  __int64 v17; // r13
  NTSTATUS StopOnSymlinkEcp; // edi
  int v19; // ecx
  int v20; // ecx
  __int64 v21; // rdx
  int v22; // r14d
  NTSTATUS v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r14
  __int64 v26; // rax
  _BYTE *v27; // rsi
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  NTSTATUS v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rdx
  NTSTATUS v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rdx
  FILE_INFORMATION_CLASS FileInformationClass; // [rsp+28h] [rbp-A9h]
  FILE_INFORMATION_CLASS FileInformationClassa; // [rsp+28h] [rbp-A9h]
  FILE_INFORMATION_CLASS FileInformationClassb; // [rsp+28h] [rbp-A9h]
  FILE_INFORMATION_CLASS FileInformationClassc; // [rsp+28h] [rbp-A9h]
  __int128 v41; // [rsp+88h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-39h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v44; // [rsp+C8h] [rbp-9h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-1h] BYREF
  HANDLE Handle; // [rsp+138h] [rbp+67h] BYREF

  v1 = a1[70];
  v3 = *(unsigned __int8 *)(v1 + 192);
  if ( v3 == 1 )
  {
    v4 = *(_DWORD *)(v1 + 212);
    v6 = Smb2ImpersonateWorkItem(v1);
    if ( v6 >= 0 )
    {
      Handle = 0;
      LOBYTE(v5) = 2;
      v7 = 0;
      SRV2_PERF_ENTER_EX(a1 + 73, v5, 851, "Smb2ExecuteSetInfoReal", 1);
      if ( (unsigned int)(v4 - 10) <= 1 )
      {
        v17 = *(_QWORD *)(v1 + 200);
        IoStatusBlock = 0;
        memset(&ObjectAttributes, 0, 44);
        v41 = 0;
        if ( *(_QWORD *)(v17 + 8) )
        {
          v44 = 1;
          memset(&DriverContext, 0, sizeof(DriverContext));
          DriverContext.Size = 40;
          StopOnSymlinkEcp = Smb2CreateStopOnSymlinkEcp(&DriverContext.ExtraCreateParameter);
          if ( StopOnSymlinkEcp < 0 )
          {
LABEL_69:
            PsAssignImpersonationToken(KeGetCurrentThread(), 0);
            LOBYTE(FileInformationClass) = 1;
            LOBYTE(v36) = 2;
            SRV2_PERF_ENTER_EX(a1 + 73, v36, 922, "Smb2ExecuteSetInfoReal", FileInformationClass);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_qZd(
                WPP_GLOBAL_Control->AttachedDevice,
                33,
                (unsigned int)WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
                (_DWORD)a1,
                (__int64)&v41,
                StopOnSymlinkEcp);
            }
            Smb2SetError(
              a1,
              (unsigned int)StopOnSymlinkEcp,
              "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
              927);
            return Srv2CompleteWorkItem(a1, 0);
          }
          WORD1(v41) = *(_WORD *)(v17 + 16);
          LOWORD(v41) = WORD1(v41);
          ObjectAttributes.Length = 48;
          *((_QWORD *)&v41 + 1) = v17 + 20;
          ObjectAttributes.RootDirectory = *(HANDLE *)(v17 + 8);
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&v41;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          StopOnSymlinkEcp = IoCreateFileEx(
                               &Handle,
                               0x80u,
                               &ObjectAttributes,
                               &IoStatusBlock,
                               0,
                               0,
                               3u,
                               1u,
                               0,
                               0,
                               0,
                               CreateFileTypeNone,
                               0,
                               0xCu,
                               &DriverContext);
          if ( DriverContext.ExtraCreateParameter )
            FsRtlFreeExtraCreateParameterList(DriverContext.ExtraCreateParameter);
          if ( StopOnSymlinkEcp == -2147483603 )
          {
            ExFreePoolWithTag((PVOID)IoStatusBlock.Information, 0);
            goto LABEL_69;
          }
          if ( StopOnSymlinkEcp < 0 )
            goto LABEL_69;
          v7 = 1;
        }
      }
      v8 = (struct _IO_STATUS_BLOCK *)(a1[15] + 48LL);
      v9 = *(_DWORD *)(v1 + 208);
      v10 = *(void **)(v1 + 200);
      v11 = *(void **)(*(_QWORD *)(v1 + 80) + 88LL);
      if ( v4 == 15 )
      {
        v6 = NtSetEaFile(v11, v8, v10, v9);
        if ( v6 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids, a1, v6);
        }
      }
      else
      {
        v6 = NtSetInformationFile(v11, v8, v10, v9, *(FILE_INFORMATION_CLASS *)(v1 + 212));
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids, a1, v6);
          }
        }
        else
        {
          v13 = *(_DWORD *)(v1 + 212);
          if ( (v13 == 13 || v13 == 10) && *(_QWORD *)(*(_QWORD *)(v1 + 72) + 168LL) )
            Smb2FilePreventLeaseDelay();
        }
      }
      LOBYTE(FileInformationClass) = 1;
      LOBYTE(v12) = 2;
      SRV2_PERF_ENTER_EX(a1 + 73, v12, 978, "Smb2ExecuteSetInfoReal", FileInformationClass);
      if ( v7 )
      {
        ZwClose(Handle);
        Handle = 0;
      }
      PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    }
    *(_DWORD *)(a1[15] + 48LL) = v6;
    v14 = *(_DWORD *)(a1[15] + 48LL);
    if ( v14 < 0 )
    {
      Smb2SetError(a1, (unsigned int)v14, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c", 788);
    }
    else
    {
      v15 = a1[70];
      Srv2SetResponseBufferToReceiveBuffer(a1);
      *(_WORD *)(*(_QWORD *)(a1[38] + 24LL) + 64LL) = 2;
      *(_DWORD *)(a1[39] + 36LL) = 66;
      if ( *(_DWORD *)(v15 + 212) == 10 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v15 + 72) + 168LL) )
        {
          v25 = *(_QWORD *)(v15 + 200);
          v26 = Smb2ReferenceLeaseFromFile();
          v27 = (_BYTE *)v26;
          if ( v26 )
          {
            if ( (int)Smb2UpdateLeaseFileName(v26, v25 + 20, *(unsigned int *)(v25 + 16)) >= 0 )
              v27[129] = 0;
            Smb2DereferenceLease(v27);
          }
        }
      }
      Smb2SetSuccess(a1, (unsigned int)v14);
    }
    return Srv2CompleteWorkItem(a1, 0);
  }
  v19 = v3 - 2;
  if ( !v19 )
  {
    v22 = Smb2ImpersonateWorkItem(v1);
    if ( v22 < 0 )
      goto LABEL_30;
    LOBYTE(v33) = 2;
    SRV2_PERF_ENTER_EX(a1 + 73, v33, 1002, "Smb2ExecuteSetInfoReal", 1);
    v34 = NtSetVolumeInformationFile(
            *(HANDLE *)(*(_QWORD *)(v1 + 80) + 88LL),
            (PIO_STATUS_BLOCK)(a1[15] + 48LL),
            *(PVOID *)(v1 + 200),
            *(_DWORD *)(v1 + 208),
            *(FS_INFORMATION_CLASS *)(v1 + 212));
    LOBYTE(FileInformationClassc) = 1;
    LOBYTE(v35) = 2;
    v22 = v34;
    SRV2_PERF_ENTER_EX(a1 + 73, v35, 1010, "Smb2ExecuteSetInfoReal", FileInformationClassc);
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    if ( v22 >= 0 )
      goto LABEL_30;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_30;
    }
    v29 = 36;
    goto LABEL_64;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    v22 = Smb2ImpersonateWorkItem(v1);
    if ( v22 < 0 )
      goto LABEL_30;
    LOBYTE(v21) = 2;
    SRV2_PERF_ENTER_EX(a1 + 73, v21, 1035, "Smb2ExecuteSetInfoReal", 1);
    v23 = NtSetSecurityObject(
            *(HANDLE *)(*(_QWORD *)(v1 + 80) + 88LL),
            *(_DWORD *)(v1 + 212),
            *(PSECURITY_DESCRIPTOR *)(v1 + 200));
    LOBYTE(FileInformationClassa) = 1;
    LOBYTE(v24) = 2;
    v22 = v23;
    SRV2_PERF_ENTER_EX(a1 + 73, v24, 1041, "Smb2ExecuteSetInfoReal", FileInformationClassa);
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    if ( v22 >= 0 )
      goto LABEL_30;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_30;
    }
    v29 = 37;
LABEL_64:
    WPP_SF_qD(v28->AttachedDevice, v29, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids, a1, v22);
LABEL_30:
    *(_DWORD *)(a1[15] + 48LL) = v22;
    return Smb2ContinueSetInfo(a1);
  }
  if ( v20 == 1 )
  {
    v22 = Smb2ImpersonateWorkItem(v1);
    if ( v22 < 0 )
      goto LABEL_30;
    LOBYTE(v30) = 2;
    SRV2_PERF_ENTER_EX(a1 + 73, v30, 1066, "Smb2ExecuteSetInfoReal", 1);
    v31 = NtSetQuotaInformationFile(
            *(HANDLE *)(*(_QWORD *)(v1 + 80) + 88LL),
            (PIO_STATUS_BLOCK)(a1[15] + 48LL),
            *(PVOID *)(v1 + 200),
            *(_DWORD *)(v1 + 208));
    LOBYTE(FileInformationClassb) = 1;
    LOBYTE(v32) = 2;
    v22 = v31;
    SRV2_PERF_ENTER_EX(a1 + 73, v32, 1075, "Smb2ExecuteSetInfoReal", FileInformationClassb);
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    if ( v22 >= 0 )
      goto LABEL_30;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_30;
    }
    v29 = 38;
    goto LABEL_64;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids, a1);
  }
  Smb2SetError(a1, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c", 1101);
  return Srv2CompleteWorkItem(a1, 0);
}

```

## disassembly

```asm
0x1400792e0  mov     rax, rsp
0x1400792e3  push    rbp
0x1400792e4  push    rbx
0x1400792e5  push    rsi
0x1400792e6  push    rdi
0x1400792e7  push    r14
0x1400792e9  lea     rbp, [rax-5Fh]
0x1400792ed  sub     rsp, 100h
0x1400792f4  mov     rsi, [rcx+230h]
0x1400792fb  mov     rbx, rcx
0x1400792fe  movzx   ecx, byte ptr [rsi+0C0h]
0x140079305  cmp     ecx, 1
0x140079308  jnz     loc_14007958C
0x14007930e  mov     r14d, [rsi+0D4h]
0x140079315  mov     rcx, rsi
0x140079318  mov     [rax+10h], r12
0x14007931c  mov     [rax+18h], r13
0x140079320  mov     [rax+20h], r15
0x140079324  call    Smb2ImpersonateWorkItem
0x140079329  mov     edi, eax
0x14007932b  test    eax, eax
0x14007932d  js      loc_14007940B
0x140079333  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x14007933a  mov     [rbp+57h+Handle], 0
0x140079342  mov     r8d, 353h
0x140079348  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x14007934d  mov     dl, 2
0x14007934f  lea     rcx, [rbx+248h]
0x140079356  xor     r12b, r12b
0x140079359  call    SRV2_PERF_ENTER_EX
0x14007935e  lea     eax, [r14-0Ah]
0x140079362  cmp     eax, 1
0x140079365  jbe     loc_140079531
0x14007936b  mov     rdx, [rbx+78h]
0x14007936f  mov     rcx, [rsi+50h]
0x140079373  add     rdx, 30h ; '0'; IoStatusBlock
0x140079377  mov     r9d, [rsi+0D0h]; EaBufferSize
0x14007937e  mov     r8, [rsi+0C8h]; EaBuffer
0x140079385  mov     rcx, [rcx+58h]; FileHandle
0x140079389  cmp     r14d, 0Fh
0x14007938d  jz      loc_1400794B3
0x140079393  mov     eax, [rsi+0D4h]
0x140079399  mov     [rsp+120h+FileInformationClass], eax; FileInformationClass
0x14007939d  call    cs:__imp_NtSetInformationFile
0x1400793a4  nop     dword ptr [rax+rax+00h]
0x1400793a9  mov     edi, eax
0x1400793ab  test    eax, eax
0x1400793ad  js      loc_1400796EE
0x1400793b3  mov     eax, [rsi+0D4h]
0x1400793b9  cmp     eax, 0Dh
0x1400793bc  jz      loc_140079497
0x1400793c2  cmp     eax, 0Ah
0x1400793c5  jz      loc_140079497
0x1400793cb  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x1400793d2  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x1400793d7  mov     r8d, 3D2h
0x1400793dd  lea     rcx, [rbx+248h]
0x1400793e4  mov     dl, 2
0x1400793e6  call    SRV2_PERF_ENTER_EX
0x1400793eb  test    r12b, r12b
0x1400793ee  jnz     loc_14007973D
0x1400793f4  mov     rcx, gs:188h; Thread
0x1400793fd  xor     edx, edx; Token
0x1400793ff  call    cs:__imp_PsAssignImpersonationToken
0x140079406  nop     dword ptr [rax+rax+00h]
0x14007940b  mov     rax, [rbx+78h]
0x14007940f  mov     rcx, rbx
0x140079412  mov     [rax+30h], edi
0x140079415  mov     rax, [rbx+78h]
0x140079419  mov     edi, [rax+30h]
0x14007941c  test    edi, edi
0x14007941e  js      loc_140079518
0x140079424  mov     rsi, [rbx+230h]
0x14007942b  call    Srv2SetResponseBufferToReceiveBuffer
0x140079430  mov     rax, [rbx+130h]
0x140079437  mov     rcx, [rax+18h]
0x14007943b  mov     word ptr [rcx+40h], 2
0x140079441  mov     rax, [rbx+138h]
0x140079448  mov     dword ptr [rax+24h], 42h ; 'B'
0x14007944f  cmp     dword ptr [rsi+0D4h], 0Ah
0x140079456  jz      loc_140079654
0x14007945c  mov     edx, edi
0x14007945e  mov     rcx, rbx
0x140079461  call    Smb2SetSuccess
0x140079466  xor     edx, edx
0x140079468  mov     rcx, rbx
0x14007946b  call    Srv2CompleteWorkItem
0x140079470  mov     r13, [rsp+120h+arg_10]
0x140079478  mov     r12, [rsp+120h+arg_8]
0x140079480  mov     r15, [rsp+120h+arg_18]
0x140079488  add     rsp, 100h
0x14007948f  pop     r14
0x140079491  pop     rdi
0x140079492  pop     rsi
0x140079493  pop     rbx
0x140079494  pop     rbp
0x140079495  retn
0x140079497  mov     rcx, [rsi+48h]
0x14007949b  cmp     qword ptr [rcx+0A8h], 0
0x1400794a3  jz      loc_1400793CB
0x1400794a9  call    Smb2FilePreventLeaseDelay
0x1400794ae  jmp     loc_1400793CB
0x1400794b3  call    cs:__imp_NtSetEaFile
0x1400794ba  nop     dword ptr [rax+rax+00h]
0x1400794bf  mov     edi, eax
0x1400794c1  test    eax, eax
0x1400794c3  jns     loc_1400793CB
0x1400794c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400794d0  lea     rax, WPP_GLOBAL_Control
0x1400794d7  cmp     rcx, rax
0x1400794da  jz      loc_1400793CB
0x1400794e0  test    dword ptr [rcx+2Ch], 10000000h
0x1400794e7  jz      loc_1400793CB
0x1400794ed  cmp     byte ptr [rcx+29h], 1
0x1400794f1  jb      loc_1400793CB
0x1400794f7  mov     rcx, [rcx+18h]
0x1400794fb  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x140079502  mov     edx, 23h ; '#'
0x140079507  mov     [rsp+120h+FileInformationClass], edi
0x14007950b  mov     r9, rbx
0x14007950e  call    WPP_SF_qD
0x140079513  jmp     loc_1400793CB
0x140079518  mov     r9d, 314h
0x14007951e  lea     r8, aOnecoreBaseFsR_17; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140079525  mov     edx, edi
0x140079527  call    _Smb2SetError
0x14007952c  jmp     loc_140079466
0x140079531  mov     r13, [rsi+0C8h]
0x140079538  xorps   xmm0, xmm0
0x14007953b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14007953f  xor     eax, eax
0x140079541  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140079545  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140079549  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14007954d  movups  [rbp+57h+var_A0], xmm0
0x140079551  cmp     [r13+8], rax
0x140079555  jz      loc_14007936B
0x14007955b  mov     eax, 28h ; '('
0x140079560  mov     [rbp+57h+var_60], 1
0x140079568  movups  xmmword ptr [rbp+57h+DriverContext.Size], xmm0
0x14007956c  lea     rcx, [rbp+57h+DriverContext.ExtraCreateParameter]
0x140079570  mov     [rbp+57h+DriverContext.Size], ax
0x140079574  movups  xmmword ptr [rbp+57h+DriverContext.DeviceObjectHint], xmm0
0x140079578  call    Smb2CreateStopOnSymlinkEcp
0x14007957d  mov     edi, eax
0x14007957f  test    eax, eax
0x140079581  jns     loc_140097A50
0x140079587  jmp     loc_140097B39
0x14007958c  sub     ecx, 2
0x14007958f  jz      loc_140097955
0x140079595  sub     ecx, 1
0x140079598  jnz     loc_140097814
0x14007959e  mov     rcx, rsi
0x1400795a1  call    Smb2ImpersonateWorkItem
0x1400795a6  mov     r14d, eax
0x1400795a9  test    eax, eax
0x1400795ab  js      loc_140079635
0x1400795b1  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x1400795b8  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x1400795bd  mov     r8d, 40Bh
0x1400795c3  lea     rcx, [rbx+248h]
0x1400795ca  mov     dl, 2
0x1400795cc  call    SRV2_PERF_ENTER_EX
0x1400795d1  mov     rcx, [rsi+50h]
0x1400795d5  mov     r8, [rsi+0C8h]; SecurityDescriptor
0x1400795dc  mov     edx, [rsi+0D4h]; SecurityInformation
0x1400795e2  mov     rcx, [rcx+58h]; Handle
0x1400795e6  call    cs:__imp_NtSetSecurityObject
0x1400795ed  nop     dword ptr [rax+rax+00h]
0x1400795f2  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x1400795f9  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x1400795fe  mov     r8d, 411h
0x140079604  lea     rcx, [rbx+248h]
0x14007960b  mov     dl, 2
0x14007960d  mov     r14d, eax
0x140079610  call    SRV2_PERF_ENTER_EX
0x140079615  mov     rcx, gs:188h; Thread
0x14007961e  xor     edx, edx; Token
0x140079620  call    cs:__imp_PsAssignImpersonationToken
0x140079627  nop     dword ptr [rax+rax+00h]
0x14007962c  test    r14d, r14d
0x14007962f  js      loc_1400796B6
0x140079635  mov     rax, [rbx+78h]
0x140079639  mov     rcx, rbx
0x14007963c  mov     [rax+30h], r14d
0x140079640  call    Smb2ContinueSetInfo
0x140079645  add     rsp, 100h
0x14007964c  pop     r14
0x14007964e  pop     rdi
0x14007964f  pop     rsi
0x140079650  pop     rbx
0x140079651  pop     rbp
0x140079652  retn
0x140079654  mov     rcx, [rsi+48h]
0x140079658  cmp     qword ptr [rcx+0A8h], 0
0x140079660  jz      loc_14007945C
0x140079666  mov     r14, [rsi+0C8h]
0x14007966d  call    Smb2ReferenceLeaseFromFile
0x140079672  mov     rsi, rax
0x140079675  test    rax, rax
0x140079678  jz      loc_14007945C
0x14007967e  mov     r8d, [r14+10h]
0x140079682  lea     rdx, [r14+14h]
0x140079686  mov     rcx, rax
0x140079689  call    Smb2UpdateLeaseFileName
0x14007968e  test    eax, eax
0x140079690  js      short loc_140079699
0x140079692  mov     byte ptr [rsi+81h], 0
0x140079699  mov     rcx, rsi
0x14007969c  call    Smb2DereferenceLease
0x1400796a1  jmp     loc_14007945C
0x1400796a6  test    edi, edi
0x1400796a8  js      loc_140097B39
0x1400796ae  mov     r12b, 1
0x1400796b1  jmp     loc_14007936B
0x1400796b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400796bd  lea     rax, WPP_GLOBAL_Control
0x1400796c4  cmp     rcx, rax
0x1400796c7  jz      loc_140079635
0x1400796cd  test    dword ptr [rcx+2Ch], 10000000h
0x1400796d4  jz      loc_140079635
0x1400796da  cmp     byte ptr [rcx+29h], 1
0x1400796de  jb      loc_140079635
0x1400796e4  mov     edx, 25h ; '%'
0x1400796e9  jmp     loc_140097A32
0x1400796ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400796f5  lea     rax, WPP_GLOBAL_Control
0x1400796fc  cmp     rcx, rax
0x1400796ff  jz      loc_1400793CB
0x140079705  test    dword ptr [rcx+2Ch], 10000000h
0x14007970c  jz      loc_1400793CB
0x140079712  cmp     byte ptr [rcx+29h], 1
0x140079716  jb      loc_1400793CB
0x14007971c  mov     rcx, [rcx+18h]
0x140079720  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x140079727  mov     edx, 22h ; '"'
0x14007972c  mov     [rsp+120h+FileInformationClass], edi
0x140079730  mov     r9, rbx
0x140079733  call    WPP_SF_qD
0x140079738  jmp     loc_1400793CB
0x14007973d  mov     rcx, [rbp+57h+Handle]; Handle
0x140079741  call    cs:__imp_ZwClose
0x140079748  nop     dword ptr [rax+rax+00h]
0x14007974d  mov     [rbp+57h+Handle], 0
0x140079755  jmp     loc_1400793F4
0x140097814  cmp     ecx, 1
0x140097817  jz      short loc_14009787D
0x140097819  mov     rcx, cs:WPP_GLOBAL_Control
0x140097820  lea     rax, WPP_GLOBAL_Control
0x140097827  cmp     rcx, rax
0x14009782a  jz      short loc_140097853
0x14009782c  test    dword ptr [rcx+2Ch], 10000000h
0x140097833  jz      short loc_140097853
0x140097835  cmp     byte ptr [rcx+29h], 1
0x140097839  jb      short loc_140097853
0x14009783b  mov     rcx, [rcx+18h]
0x14009783f  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x140097846  mov     edx, 27h ; '''
0x14009784b  mov     r9, rbx
0x14009784e  call    WPP_SF_q
0x140097853  mov     r9d, 44Dh
0x140097859  lea     r8, aOnecoreBaseFsR_17; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140097860  mov     edx, 0C000000Dh
0x140097865  mov     rcx, rbx
0x140097868  call    _Smb2SetError
0x14009786d  xor     edx, edx
0x14009786f  mov     rcx, rbx
0x140097872  call    Srv2CompleteWorkItem
0x140097877  nop
0x140097878  jmp     loc_140079488
0x14009787d  mov     rcx, rsi
0x140097880  call    Smb2ImpersonateWorkItem
0x140097885  mov     r14d, eax
0x140097888  test    eax, eax
0x14009788a  js      loc_140079635
0x140097890  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x140097897  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x14009789c  mov     r8d, 42Ah
0x1400978a2  lea     rcx, [rbx+248h]
0x1400978a9  mov     dl, 2
0x1400978ab  call    SRV2_PERF_ENTER_EX
0x1400978b0  mov     rcx, [rsi+50h]
0x1400978b4  mov     rdx, [rbx+78h]
0x1400978b8  mov     r9d, [rsi+0D0h]; Length
0x1400978bf  add     rdx, 30h ; '0'; IoStatusBlock
0x1400978c3  mov     r8, [rsi+0C8h]; Buffer
0x1400978ca  mov     rcx, [rcx+58h]; FileHandle
0x1400978ce  call    cs:__imp_NtSetQuotaInformationFile
0x1400978d5  nop     dword ptr [rax+rax+00h]
0x1400978da  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x1400978e1  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x1400978e6  mov     r8d, 433h
0x1400978ec  lea     rcx, [rbx+248h]
0x1400978f3  mov     dl, 2
0x1400978f5  mov     r14d, eax
0x1400978f8  call    SRV2_PERF_ENTER_EX
0x1400978fd  mov     rcx, gs:188h; Thread
0x140097906  xor     edx, edx; Token
0x140097908  call    cs:__imp_PsAssignImpersonationToken
0x14009790f  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
