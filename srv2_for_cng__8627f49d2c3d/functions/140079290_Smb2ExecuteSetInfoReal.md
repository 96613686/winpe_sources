# Smb2ExecuteSetInfoReal

- ea: `0x140079290`
- end: `0x14007970a`
- name: `Smb2ExecuteSetInfoReal`
- size: `1146`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140085ef0`

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
- `0x1400790e0`
- `0x140079290`
- `0x14007a640`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400796f1`
- `ntoskrnl!ZwClose` at `0x1400796f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097add`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097add`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140097abf`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140097abf`
- `ntoskrnl!IoCreateFileEx` at `0x140097aa8`
- `ntoskrnl!IoCreateFileEx` at `0x140097aa8`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400793af`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400795d0`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400978b8`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009799a`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097af4`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400793af`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400795d0`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400978b8`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009799a`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140097af4`
- `ntoskrnl!NtSetInformationFile` at `0x14007934d`
- `ntoskrnl!NtSetInformationFile` at `0x14007934d`
- `ntoskrnl!NtSetEaFile` at `0x140079463`
- `ntoskrnl!NtSetEaFile` at `0x140079463`
- `ntoskrnl!NtSetVolumeInformationFile` at `0x140097960`
- `ntoskrnl!NtSetVolumeInformationFile` at `0x140097960`
- `ntoskrnl!NtSetSecurityObject` at `0x140079596`
- `ntoskrnl!NtSetSecurityObject` at `0x140079596`
- `ntoskrnl!NtSetQuotaInformationFile` at `0x14009787e`
- `ntoskrnl!NtSetQuotaInformationFile` at `0x14009787e`

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
0x140079290  mov     rax, rsp
0x140079293  push    rbp
0x140079294  push    rbx
0x140079295  push    rsi
0x140079296  push    rdi
0x140079297  push    r14
0x140079299  lea     rbp, [rax-5Fh]
0x14007929d  sub     rsp, 100h
0x1400792a4  mov     rsi, [rcx+230h]
0x1400792ab  mov     rbx, rcx
0x1400792ae  movzx   ecx, byte ptr [rsi+0C0h]
0x1400792b5  cmp     ecx, 1
0x1400792b8  jnz     loc_14007953C
0x1400792be  mov     r14d, [rsi+0D4h]
0x1400792c5  mov     rcx, rsi
0x1400792c8  mov     [rax+10h], r12
0x1400792cc  mov     [rax+18h], r13
0x1400792d0  mov     [rax+20h], r15
0x1400792d4  call    Smb2ImpersonateWorkItem
0x1400792d9  mov     edi, eax
0x1400792db  test    eax, eax
0x1400792dd  js      loc_1400793BB
0x1400792e3  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x1400792ea  mov     [rbp+57h+Handle], 0
0x1400792f2  mov     r8d, 353h
0x1400792f8  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x1400792fd  mov     dl, 2
0x1400792ff  lea     rcx, [rbx+248h]
0x140079306  xor     r12b, r12b
0x140079309  call    SRV2_PERF_ENTER_EX
0x14007930e  lea     eax, [r14-0Ah]
0x140079312  cmp     eax, 1
0x140079315  jbe     loc_1400794E1
0x14007931b  mov     rdx, [rbx+78h]
0x14007931f  mov     rcx, [rsi+50h]
0x140079323  add     rdx, 30h ; '0'; IoStatusBlock
0x140079327  mov     r9d, [rsi+0D0h]; EaBufferSize
0x14007932e  mov     r8, [rsi+0C8h]; EaBuffer
0x140079335  mov     rcx, [rcx+58h]; FileHandle
0x140079339  cmp     r14d, 0Fh
0x14007933d  jz      loc_140079463
0x140079343  mov     eax, [rsi+0D4h]
0x140079349  mov     [rsp+120h+FileInformationClass], eax; FileInformationClass
0x14007934d  call    cs:__imp_NtSetInformationFile
0x140079354  nop     dword ptr [rax+rax+00h]
0x140079359  mov     edi, eax
0x14007935b  test    eax, eax
0x14007935d  js      loc_14007969E
0x140079363  mov     eax, [rsi+0D4h]
0x140079369  cmp     eax, 0Dh
0x14007936c  jz      loc_140079447
0x140079372  cmp     eax, 0Ah
0x140079375  jz      loc_140079447
0x14007937b  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x140079382  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x140079387  mov     r8d, 3D2h
0x14007938d  lea     rcx, [rbx+248h]
0x140079394  mov     dl, 2
0x140079396  call    SRV2_PERF_ENTER_EX
0x14007939b  test    r12b, r12b
0x14007939e  jnz     loc_1400796ED
0x1400793a4  mov     rcx, gs:188h; Thread
0x1400793ad  xor     edx, edx; Token
0x1400793af  call    cs:__imp_PsAssignImpersonationToken
0x1400793b6  nop     dword ptr [rax+rax+00h]
0x1400793bb  mov     rax, [rbx+78h]
0x1400793bf  mov     rcx, rbx
0x1400793c2  mov     [rax+30h], edi
0x1400793c5  mov     rax, [rbx+78h]
0x1400793c9  mov     edi, [rax+30h]
0x1400793cc  test    edi, edi
0x1400793ce  js      loc_1400794C8
0x1400793d4  mov     rsi, [rbx+230h]
0x1400793db  call    Srv2SetResponseBufferToReceiveBuffer
0x1400793e0  mov     rax, [rbx+130h]
0x1400793e7  mov     rcx, [rax+18h]
0x1400793eb  mov     word ptr [rcx+40h], 2
0x1400793f1  mov     rax, [rbx+138h]
0x1400793f8  mov     dword ptr [rax+24h], 42h ; 'B'
0x1400793ff  cmp     dword ptr [rsi+0D4h], 0Ah
0x140079406  jz      loc_140079604
0x14007940c  mov     edx, edi
0x14007940e  mov     rcx, rbx
0x140079411  call    Smb2SetSuccess
0x140079416  xor     edx, edx
0x140079418  mov     rcx, rbx
0x14007941b  call    Srv2CompleteWorkItem
0x140079420  mov     r13, [rsp+120h+arg_10]
0x140079428  mov     r12, [rsp+120h+arg_8]
0x140079430  mov     r15, [rsp+120h+arg_18]
0x140079438  add     rsp, 100h
0x14007943f  pop     r14
0x140079441  pop     rdi
0x140079442  pop     rsi
0x140079443  pop     rbx
0x140079444  pop     rbp
0x140079445  retn
0x140079447  mov     rcx, [rsi+48h]
0x14007944b  cmp     qword ptr [rcx+0A8h], 0
0x140079453  jz      loc_14007937B
0x140079459  call    Smb2FilePreventLeaseDelay
0x14007945e  jmp     loc_14007937B
0x140079463  call    cs:__imp_NtSetEaFile
0x14007946a  nop     dword ptr [rax+rax+00h]
0x14007946f  mov     edi, eax
0x140079471  test    eax, eax
0x140079473  jns     loc_14007937B
0x140079479  mov     rcx, cs:WPP_GLOBAL_Control
0x140079480  lea     rax, WPP_GLOBAL_Control
0x140079487  cmp     rcx, rax
0x14007948a  jz      loc_14007937B
0x140079490  test    dword ptr [rcx+2Ch], 10000000h
0x140079497  jz      loc_14007937B
0x14007949d  cmp     byte ptr [rcx+29h], 1
0x1400794a1  jb      loc_14007937B
0x1400794a7  mov     rcx, [rcx+18h]
0x1400794ab  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x1400794b2  mov     edx, 23h ; '#'
0x1400794b7  mov     [rsp+120h+FileInformationClass], edi
0x1400794bb  mov     r9, rbx
0x1400794be  call    WPP_SF_qD
0x1400794c3  jmp     loc_14007937B
0x1400794c8  mov     r9d, 314h
0x1400794ce  lea     r8, aOnecoreBaseFsR_17; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400794d5  mov     edx, edi
0x1400794d7  call    _Smb2SetError
0x1400794dc  jmp     loc_140079416
0x1400794e1  mov     r13, [rsi+0C8h]
0x1400794e8  xorps   xmm0, xmm0
0x1400794eb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400794ef  xor     eax, eax
0x1400794f1  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400794f5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400794f9  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400794fd  movups  [rbp+57h+var_A0], xmm0
0x140079501  cmp     [r13+8], rax
0x140079505  jz      loc_14007931B
0x14007950b  mov     eax, 28h ; '('
0x140079510  mov     [rbp+57h+var_60], 1
0x140079518  movups  xmmword ptr [rbp+57h+DriverContext.Size], xmm0
0x14007951c  lea     rcx, [rbp+57h+DriverContext.ExtraCreateParameter]
0x140079520  mov     [rbp+57h+DriverContext.Size], ax
0x140079524  movups  xmmword ptr [rbp+57h+DriverContext.DeviceObjectHint], xmm0
0x140079528  call    Smb2CreateStopOnSymlinkEcp
0x14007952d  mov     edi, eax
0x14007952f  test    eax, eax
0x140079531  jns     loc_140097A00
0x140079537  jmp     loc_140097AE9
0x14007953c  sub     ecx, 2
0x14007953f  jz      loc_140097905
0x140079545  sub     ecx, 1
0x140079548  jnz     loc_1400977C4
0x14007954e  mov     rcx, rsi
0x140079551  call    Smb2ImpersonateWorkItem
0x140079556  mov     r14d, eax
0x140079559  test    eax, eax
0x14007955b  js      loc_1400795E5
0x140079561  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x140079568  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x14007956d  mov     r8d, 40Bh
0x140079573  lea     rcx, [rbx+248h]
0x14007957a  mov     dl, 2
0x14007957c  call    SRV2_PERF_ENTER_EX
0x140079581  mov     rcx, [rsi+50h]
0x140079585  mov     r8, [rsi+0C8h]; SecurityDescriptor
0x14007958c  mov     edx, [rsi+0D4h]; SecurityInformation
0x140079592  mov     rcx, [rcx+58h]; Handle
0x140079596  call    cs:__imp_NtSetSecurityObject
0x14007959d  nop     dword ptr [rax+rax+00h]
0x1400795a2  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x1400795a9  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x1400795ae  mov     r8d, 411h
0x1400795b4  lea     rcx, [rbx+248h]
0x1400795bb  mov     dl, 2
0x1400795bd  mov     r14d, eax
0x1400795c0  call    SRV2_PERF_ENTER_EX
0x1400795c5  mov     rcx, gs:188h; Thread
0x1400795ce  xor     edx, edx; Token
0x1400795d0  call    cs:__imp_PsAssignImpersonationToken
0x1400795d7  nop     dword ptr [rax+rax+00h]
0x1400795dc  test    r14d, r14d
0x1400795df  js      loc_140079666
0x1400795e5  mov     rax, [rbx+78h]
0x1400795e9  mov     rcx, rbx
0x1400795ec  mov     [rax+30h], r14d
0x1400795f0  call    Smb2ContinueSetInfo
0x1400795f5  add     rsp, 100h
0x1400795fc  pop     r14
0x1400795fe  pop     rdi
0x1400795ff  pop     rsi
0x140079600  pop     rbx
0x140079601  pop     rbp
0x140079602  retn
0x140079604  mov     rcx, [rsi+48h]
0x140079608  cmp     qword ptr [rcx+0A8h], 0
0x140079610  jz      loc_14007940C
0x140079616  mov     r14, [rsi+0C8h]
0x14007961d  call    Smb2ReferenceLeaseFromFile
0x140079622  mov     rsi, rax
0x140079625  test    rax, rax
0x140079628  jz      loc_14007940C
0x14007962e  mov     r8d, [r14+10h]
0x140079632  lea     rdx, [r14+14h]
0x140079636  mov     rcx, rax
0x140079639  call    Smb2UpdateLeaseFileName
0x14007963e  test    eax, eax
0x140079640  js      short loc_140079649
0x140079642  mov     byte ptr [rsi+81h], 0
0x140079649  mov     rcx, rsi
0x14007964c  call    Smb2DereferenceLease
0x140079651  jmp     loc_14007940C
0x140079656  test    edi, edi
0x140079658  js      loc_140097AE9
0x14007965e  mov     r12b, 1
0x140079661  jmp     loc_14007931B
0x140079666  mov     rcx, cs:WPP_GLOBAL_Control
0x14007966d  lea     rax, WPP_GLOBAL_Control
0x140079674  cmp     rcx, rax
0x140079677  jz      loc_1400795E5
0x14007967d  test    dword ptr [rcx+2Ch], 10000000h
0x140079684  jz      loc_1400795E5
0x14007968a  cmp     byte ptr [rcx+29h], 1
0x14007968e  jb      loc_1400795E5
0x140079694  mov     edx, 25h ; '%'
0x140079699  jmp     loc_1400979E2
0x14007969e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400796a5  lea     rax, WPP_GLOBAL_Control
0x1400796ac  cmp     rcx, rax
0x1400796af  jz      loc_14007937B
0x1400796b5  test    dword ptr [rcx+2Ch], 10000000h
0x1400796bc  jz      loc_14007937B
0x1400796c2  cmp     byte ptr [rcx+29h], 1
0x1400796c6  jb      loc_14007937B
0x1400796cc  mov     rcx, [rcx+18h]
0x1400796d0  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x1400796d7  mov     edx, 22h ; '"'
0x1400796dc  mov     [rsp+120h+FileInformationClass], edi
0x1400796e0  mov     r9, rbx
0x1400796e3  call    WPP_SF_qD
0x1400796e8  jmp     loc_14007937B
0x1400796ed  mov     rcx, [rbp+57h+Handle]; Handle
0x1400796f1  call    cs:__imp_ZwClose
0x1400796f8  nop     dword ptr [rax+rax+00h]
0x1400796fd  mov     [rbp+57h+Handle], 0
0x140079705  jmp     loc_1400793A4
0x1400977c4  cmp     ecx, 1
0x1400977c7  jz      short loc_14009782D
0x1400977c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400977d0  lea     rax, WPP_GLOBAL_Control
0x1400977d7  cmp     rcx, rax
0x1400977da  jz      short loc_140097803
0x1400977dc  test    dword ptr [rcx+2Ch], 10000000h
0x1400977e3  jz      short loc_140097803
0x1400977e5  cmp     byte ptr [rcx+29h], 1
0x1400977e9  jb      short loc_140097803
0x1400977eb  mov     rcx, [rcx+18h]
0x1400977ef  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x1400977f6  mov     edx, 27h ; '''
0x1400977fb  mov     r9, rbx
0x1400977fe  call    WPP_SF_q
0x140097803  mov     r9d, 44Dh
0x140097809  lea     r8, aOnecoreBaseFsR_17; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140097810  mov     edx, 0C000000Dh
0x140097815  mov     rcx, rbx
0x140097818  call    _Smb2SetError
0x14009781d  xor     edx, edx
0x14009781f  mov     rcx, rbx
0x140097822  call    Srv2CompleteWorkItem
0x140097827  nop
0x140097828  jmp     loc_140079438
0x14009782d  mov     rcx, rsi
0x140097830  call    Smb2ImpersonateWorkItem
0x140097835  mov     r14d, eax
0x140097838  test    eax, eax
0x14009783a  js      loc_1400795E5
0x140097840  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x140097847  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x14009784c  mov     r8d, 42Ah
0x140097852  lea     rcx, [rbx+248h]
0x140097859  mov     dl, 2
0x14009785b  call    SRV2_PERF_ENTER_EX
0x140097860  mov     rcx, [rsi+50h]
0x140097864  mov     rdx, [rbx+78h]
0x140097868  mov     r9d, [rsi+0D0h]; Length
0x14009786f  add     rdx, 30h ; '0'; IoStatusBlock
0x140097873  mov     r8, [rsi+0C8h]; Buffer
0x14009787a  mov     rcx, [rcx+58h]; FileHandle
0x14009787e  call    cs:__imp_NtSetQuotaInformationFile
0x140097885  nop     dword ptr [rax+rax+00h]
0x14009788a  lea     r9, aSmb2executeset; "Smb2ExecuteSetInfoReal"
0x140097891  mov     byte ptr [rsp+120h+FileInformationClass], 1
0x140097896  mov     r8d, 433h
0x14009789c  lea     rcx, [rbx+248h]
0x1400978a3  mov     dl, 2
0x1400978a5  mov     r14d, eax
0x1400978a8  call    SRV2_PERF_ENTER_EX
0x1400978ad  mov     rcx, gs:188h; Thread
0x1400978b6  xor     edx, edx; Token
0x1400978b8  call    cs:__imp_PsAssignImpersonationToken
0x1400978bf  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
