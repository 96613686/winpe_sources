# Smb2ExecuteQueryInfo

- ea: `0x140080db0`
- end: `0x1400813ac`
- name: `Smb2ExecuteQueryInfo`
- size: `1532`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140074860`

## callees

- `0x140005070`
- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x1400152a0`
- `0x140015354`
- `0x1400154b0`
- `0x1400222ec`
- `0x1400229ac`
- `0x140080db0`
- `0x1400813b4`
- `0x1400853f0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140080f23`
- `ntoskrnl!IoBuildPartialMdl` at `0x140080f80`
- `ntoskrnl!IoBuildPartialMdl` at `0x14008111a`
- `ntoskrnl!IoBuildPartialMdl` at `0x14008117b`
- `ntoskrnl!IoBuildPartialMdl` at `0x140080f23`
- `ntoskrnl!IoBuildPartialMdl` at `0x140080f80`
- `ntoskrnl!IoBuildPartialMdl` at `0x14008111a`
- `ntoskrnl!IoBuildPartialMdl` at `0x14008117b`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400812fa`
- `ntoskrnl!MmUnmapLockedPages` at `0x140081312`
- `ntoskrnl!MmUnmapLockedPages` at `0x140081383`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008139b`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400812fa`
- `ntoskrnl!MmUnmapLockedPages` at `0x140081312`
- `ntoskrnl!MmUnmapLockedPages` at `0x140081383`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008139b`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400988fc`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400988fc`
- `ntoskrnl!NtQuerySecurityObject` at `0x1400989a6`
- `ntoskrnl!NtQuerySecurityObject` at `0x1400989a6`
- `ntoskrnl!NtQueryInformationFile` at `0x140080e53`
- `ntoskrnl!NtQueryInformationFile` at `0x140080e53`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140080e99`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140081088`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009891d`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140080e99`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140081088`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009891d`
- `ntoskrnl!NtQueryEaFile` at `0x140098a63`
- `ntoskrnl!NtQueryEaFile` at `0x140098a63`
- `ntoskrnl!NtQueryVolumeInformationFile` at `0x14008104f`
- `ntoskrnl!NtQueryVolumeInformationFile` at `0x14008104f`
- `ntoskrnl!NtQueryQuotaInformationFile` at `0x1400988c1`
- `ntoskrnl!NtQueryQuotaInformationFile` at `0x1400988c1`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteQueryInfo(__int64 a1)
{
  __int64 v1; // rsi
  int v3; // ecx
  __int64 v4; // rdx
  int v5; // edi
  __int64 v6; // r9
  int v7; // eax
  struct _IO_STATUS_BLOCK **v8; // r14
  NTSTATUS InformationFile; // eax
  __int64 v10; // r15
  unsigned int Status; // edi
  __int64 v12; // rsi
  __int64 v13; // rax
  __int64 v14; // r14
  void *v15; // r12
  struct _MDL *v16; // r13
  ULONG v17; // r13d
  __int64 v18; // rax
  __int64 v19; // rbp
  void *v20; // r14
  struct _MDL *v21; // r12
  __int64 v22; // rdx
  int v24; // ecx
  __int64 v25; // rdx
  int v26; // ebp
  __int64 v27; // r9
  NTSTATUS VolumeInformationFile; // eax
  __int64 v29; // r14
  __int64 v30; // rax
  __int64 v31; // r15
  void *v32; // r12
  struct _MDL *v33; // r13
  ULONG v34; // r13d
  __int64 v35; // rax
  __int64 v36; // rbp
  void *v37; // r15
  struct _MDL *v38; // r12
  PDEVICE_OBJECT v39; // rcx
  int v40; // eax
  NTSTATUS EaFile; // eax
  _DWORD *ExtendedErrorBuffer; // rdx
  _DWORD *v43; // rdx
  int v44; // ecx
  ULONG *v45; // r9
  void *v46; // rdi
  BOOLEAN RestartScan; // r8
  int v48; // ecx
  __int64 v49; // rdx
  int v50; // edi
  ULONG v51; // r9d
  void *v52; // rdi
  NTSTATUS QuotaInformationFile; // eax
  ULONG v54; // ebp
  __int64 v55; // rdx
  void *v56; // rdi
  NTSTATUS SecurityObject; // eax
  __int64 v58; // rcx
  ULONG v59; // r11d
  int v60; // ecx
  int FileInformationClass; // [rsp+20h] [rbp-78h]
  int FileInformationClassa; // [rsp+20h] [rbp-78h]
  int FileInformationClassb; // [rsp+20h] [rbp-78h]
  int FileInformationClassc; // [rsp+20h] [rbp-78h]

  v1 = *(_QWORD *)(a1 + 560);
  v3 = *(unsigned __int8 *)(v1 + 192);
  if ( v3 == 1 )
  {
    v5 = Smb2ImpersonateWorkItem(v1);
    if ( v5 < 0 )
    {
      v8 = (struct _IO_STATUS_BLOCK **)(a1 + 120);
      goto LABEL_7;
    }
    LOBYTE(v4) = 2;
    SRV2_PERF_ENTER_EX(a1 + 584, v4, 1040, "Smb2ExecuteQueryInfo", 1);
    v7 = *(_DWORD *)(v1 + 200);
    if ( v7 == 15 )
    {
      v44 = *(_DWORD *)(v1 + 204);
      v45 = (ULONG *)(v1 + 208);
      v46 = 0;
      RestartScan = v44 & 1;
      if ( (v44 & 4) == 0 )
        v45 = 0;
      v59 = *(_DWORD *)(v1 + 196);
      v60 = v44 & 2;
      if ( v59 )
        v46 = *(void **)(*(_QWORD *)(v1 + 160) + 24LL);
      v8 = (struct _IO_STATUS_BLOCK **)(a1 + 120);
      EaFile = NtQueryEaFile(
                 *(HANDLE *)(*(_QWORD *)(v1 + 80) + 88LL),
                 (PIO_STATUS_BLOCK)(*(_QWORD *)(a1 + 120) + 48LL),
                 v46,
                 v59,
                 v60 != 0,
                 *(PVOID *)(v1 + 216),
                 *(_DWORD *)(v1 + 212),
                 v45,
                 RestartScan);
    }
    else
    {
      v8 = (struct _IO_STATUS_BLOCK **)(a1 + 120);
      if ( v7 != 48 )
      {
        InformationFile = NtQueryInformationFile(
                            *(HANDLE *)(*(_QWORD *)(v1 + 80) + 88LL),
                            *v8 + 3,
                            *(PVOID *)(*(_QWORD *)(v1 + 160) + 24LL),
                            *(_DWORD *)(v1 + 196),
                            *(FILE_INFORMATION_CLASS *)(v1 + 200));
        v5 = InformationFile;
        if ( *(_DWORD *)(v1 + 200) == 18
          && (((InformationFile + 0x80000000) & 0x80000000) != 0 || InformationFile == -2147483643) )
        {
          v5 = 0;
          v58 = *(_QWORD *)(*(_QWORD *)(v1 + 160) + 24LL);
          (*v8)[3].Information = 104;
          *(_DWORD *)(v58 + 96) = 0;
          *(_WORD *)(v58 + 100) = 0;
        }
        goto LABEL_6;
      }
      EaFile = Smb2QueryFileNormalizedName(a1);
    }
    v5 = EaFile;
LABEL_6:
    LOBYTE(FileInformationClass) = 1;
    SRV2_PERF_ENTER_EX(a1 + 584, 0, 1106, "Smb2ExecuteQueryInfo", FileInformationClass);
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
LABEL_7:
    (*v8)[3].Status = v5;
    v10 = *(_QWORD *)(a1 + 560);
    Status = (*v8)[3].Status;
    if ( ((Status + 0x80000000) & 0x80000000) == 0 && Status != -2147483643 )
    {
      if ( Status == -1073741789 )
      {
        LOBYTE(v6) = 1;
        ExtendedErrorBuffer = (_DWORD *)Smb2AllocateExtendedErrorBuffer(a1, 0, 4, v6);
        if ( ExtendedErrorBuffer )
          *ExtendedErrorBuffer = (*v8)[3].Information;
        else
          Status = -1073741670;
      }
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_34;
      }
      v40 = *(unsigned __int8 *)(v10 + 192);
LABEL_85:
      WPP_SF_qDD(v39->AttachedDevice, 33, WPP_03d80664418738de4d4c12d6c892b627_Traceguids, a1, Status, v40);
LABEL_34:
      Smb2SetError(a1, Status, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c", 971);
      goto LABEL_17;
    }
    if ( *(_BYTE *)(v10 + 192) == 2 && *(_DWORD *)(v10 + 200) == 5 )
      **(_DWORD **)(*(_QWORD *)(v10 + 160) + 24LL) &= 0x1CDF91FEu;
    Srv2SetResponseBufferToReceiveBuffer(a1);
    v12 = *(_QWORD *)(*(_QWORD *)(a1 + 312) + 24LL);
    *(_DWORD *)(v12 + 68) = (*v8)[3].Information;
    *(_DWORD *)(v12 + 64) = 4718601;
    v13 = *(_QWORD *)(a1 + 312);
    v14 = *(_QWORD *)(v13 + 80);
    v15 = *(void **)(v13 + 24);
    v16 = *(struct _MDL **)(v13 + 56);
    if ( (*(_BYTE *)(v14 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v14 + 24), *(PMDL *)(v13 + 80));
    IoBuildPartialMdl(v16, (PMDL)v14, v15, 0x48u);
    *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 312) + 80LL) + 10LL) |= *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 312) + 56LL)
                                                                             + 10LL)
                                                                  & 0x1000;
    v17 = *(_DWORD *)(v12 + 68);
    if ( v17 )
    {
      v18 = *(_QWORD *)(v10 + 160);
      v19 = *(_QWORD *)(v18 + 80);
      v20 = *(void **)(v18 + 24);
      v21 = *(struct _MDL **)(v18 + 56);
      if ( (*(_BYTE *)(v19 + 10) & 0x20) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v19 + 24), *(PMDL *)(v18 + 80));
      IoBuildPartialMdl(v21, (PMDL)v19, v20, v17);
      v22 = *(_QWORD *)(v10 + 160);
LABEL_15:
      **(_QWORD **)(*(_QWORD *)(a1 + 312) + 80LL) = *(_QWORD *)(v22 + 80);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  v24 = v3 - 2;
  if ( !v24 )
  {
    v26 = Smb2ImpersonateWorkItem(v1);
    if ( v26 >= 0 )
    {
      LOBYTE(v25) = 2;
      SRV2_PERF_ENTER_EX(a1 + 584, v25, 1123, "Smb2ExecuteQueryInfo", 1);
      VolumeInformationFile = NtQueryVolumeInformationFile(
                                *(HANDLE *)(*(_QWORD *)(v1 + 80) + 88LL),
                                (PIO_STATUS_BLOCK)(*(_QWORD *)(a1 + 120) + 48LL),
                                *(PVOID *)(*(_QWORD *)(v1 + 160) + 24LL),
                                *(_DWORD *)(v1 + 196),
                                *(FS_INFORMATION_CLASS *)(v1 + 200));
      LOBYTE(FileInformationClassa) = 1;
      v26 = VolumeInformationFile;
      SRV2_PERF_ENTER_EX(a1 + 584, 0, 1136, "Smb2ExecuteQueryInfo", FileInformationClassa);
      PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    }
    *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = v26;
    v29 = *(_QWORD *)(a1 + 560);
    Status = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL);
    if ( (int)(Status + 0x80000000) >= 0 && Status != -2147483643 )
    {
      if ( Status == -1073741789 )
      {
        LOBYTE(v27) = 1;
        v43 = (_DWORD *)Smb2AllocateExtendedErrorBuffer(a1, 0, 4, v27);
        if ( v43 )
          *v43 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 56LL);
        else
          Status = -1073741670;
      }
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_34;
      }
      v40 = *(unsigned __int8 *)(v29 + 192);
      goto LABEL_85;
    }
    if ( *(_BYTE *)(v29 + 192) == 2 && *(_DWORD *)(v29 + 200) == 5 )
      **(_DWORD **)(*(_QWORD *)(v29 + 160) + 24LL) &= 0x1CDF91FEu;
    Srv2SetResponseBufferToReceiveBuffer(a1);
    v12 = *(_QWORD *)(*(_QWORD *)(a1 + 312) + 24LL);
    *(_DWORD *)(v12 + 68) = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 56LL);
    *(_DWORD *)(v12 + 64) = 4718601;
    v30 = *(_QWORD *)(a1 + 312);
    v31 = *(_QWORD *)(v30 + 80);
    v32 = *(void **)(v30 + 24);
    v33 = *(struct _MDL **)(v30 + 56);
    if ( (*(_BYTE *)(v31 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v31 + 24), *(PMDL *)(v30 + 80));
    IoBuildPartialMdl(v33, (PMDL)v31, v32, 0x48u);
    *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 312) + 80LL) + 10LL) |= *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 312) + 56LL)
                                                                             + 10LL)
                                                                  & 0x1000;
    v34 = *(_DWORD *)(v12 + 68);
    if ( v34 )
    {
      v35 = *(_QWORD *)(v29 + 160);
      v36 = *(_QWORD *)(v35 + 80);
      v37 = *(void **)(v35 + 24);
      v38 = *(struct _MDL **)(v35 + 56);
      if ( (*(_BYTE *)(v36 + 10) & 0x20) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v36 + 24), *(PMDL *)(v35 + 80));
      IoBuildPartialMdl(v38, (PMDL)v36, v37, v34);
      v22 = *(_QWORD *)(v29 + 160);
      goto LABEL_15;
    }
LABEL_16:
    *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL) = *(_DWORD *)(v12 + 68) + *(unsigned __int16 *)(v12 + 66);
    *(_DWORD *)(a1 + 484) |= 4u;
    Smb2SetSuccess(a1, Status);
LABEL_17:
    Srv2CompleteWorkItem(a1, 0);
    return 259;
  }
  v48 = v24 - 1;
  if ( !v48 )
  {
    v54 = *(_DWORD *)(v1 + 196);
    v50 = Smb2ImpersonateWorkItem(v1);
    if ( v50 < 0 )
      goto LABEL_74;
    LOBYTE(v55) = 2;
    SRV2_PERF_ENTER_EX(a1 + 584, v55, 1156, "Smb2ExecuteQueryInfo", 1);
    if ( v54 )
      v56 = *(void **)(*(_QWORD *)(v1 + 160) + 24LL);
    else
      v56 = 0;
    SecurityObject = NtQuerySecurityObject(
                       *(HANDLE *)(*(_QWORD *)(v1 + 80) + 88LL),
                       *(_DWORD *)(v1 + 200),
                       v56,
                       v54,
                       (PULONG)(*(_QWORD *)(a1 + 120) + 56LL));
    LOBYTE(FileInformationClassc) = 1;
    v50 = SecurityObject;
    SRV2_PERF_ENTER_EX(a1 + 584, 0, 1164, "Smb2ExecuteQueryInfo", FileInformationClassc);
    if ( v50 >= 0 )
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(*(_QWORD *)(v1 + 160) + 24LL));
    goto LABEL_73;
  }
  if ( v48 == 1 )
  {
    v50 = Smb2ImpersonateWorkItem(v1);
    if ( v50 < 0 )
    {
LABEL_74:
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = v50;
      Smb2ContinueQueryInfo(a1);
      return 259;
    }
    LOBYTE(v49) = 2;
    SRV2_PERF_ENTER_EX(a1 + 584, v49, 1185, "Smb2ExecuteQueryInfo", 1);
    v51 = *(_DWORD *)(v1 + 196);
    if ( v51 )
      v52 = *(void **)(*(_QWORD *)(v1 + 160) + 24LL);
    else
      v52 = 0;
    QuotaInformationFile = NtQueryQuotaInformationFile(
                             *(HANDLE *)(*(_QWORD *)(v1 + 80) + 88LL),
                             (PIO_STATUS_BLOCK)(*(_QWORD *)(a1 + 120) + 48LL),
                             v52,
                             v51,
                             *(_BYTE *)(v1 + 228),
                             *(PVOID *)(v1 + 200),
                             *(_DWORD *)(v1 + 216),
                             *(PSID *)(v1 + 208),
                             *(_BYTE *)(v1 + 229));
    LOBYTE(FileInformationClassb) = 1;
    v50 = QuotaInformationFile;
    SRV2_PERF_ENTER_EX(a1 + 584, 0, 1200, "Smb2ExecuteQueryInfo", FileInformationClassb);
LABEL_73:
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    goto LABEL_74;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_03d80664418738de4d4c12d6c892b627_Traceguids, a1);
  }
  Smb2SetError(a1, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c", 1218);
  return 0;
}

```

## disassembly

```asm
0x140080db0  push    rbx
0x140080db2  push    rbp
0x140080db3  push    rsi
0x140080db4  push    rdi
0x140080db5  push    r12
0x140080db7  push    r13
0x140080db9  push    r14
0x140080dbb  push    r15
0x140080dbd  sub     rsp, 58h
0x140080dc1  mov     rsi, [rcx+230h]
0x140080dc8  mov     rbx, rcx
0x140080dcb  movzx   ecx, byte ptr [rsi+0C0h]
0x140080dd2  cmp     ecx, 1
0x140080dd5  jnz     loc_140080FE8
0x140080ddb  mov     rcx, rsi
0x140080dde  call    Smb2ImpersonateWorkItem
0x140080de3  mov     edi, eax
0x140080de5  mov     ebp, 80000000h
0x140080dea  test    eax, eax
0x140080dec  js      loc_140081252
0x140080df2  lea     r9, aSmb2executeque_0; "Smb2ExecuteQueryInfo"
0x140080df9  mov     byte ptr [rsp+98h+FileInformationClass], 1
0x140080dfe  mov     r8d, 410h
0x140080e04  lea     rcx, [rbx+248h]
0x140080e0b  mov     dl, 2
0x140080e0d  call    SRV2_PERF_ENTER_EX
0x140080e12  mov     eax, [rsi+0C8h]
0x140080e18  cmp     eax, 0Fh
0x140080e1b  jz      loc_14008133E
0x140080e21  lea     r14, [rbx+78h]
0x140080e25  cmp     eax, 30h ; '0'
0x140080e28  jz      loc_14008127F
0x140080e2e  mov     r8, [rsi+0A0h]
0x140080e35  mov     rcx, [rsi+50h]
0x140080e39  mov     rdx, [r14]
0x140080e3c  mov     r9d, [rsi+0C4h]; Length
0x140080e43  add     rdx, 30h ; '0'; IoStatusBlock
0x140080e47  mov     r8, [r8+18h]; FileInformation
0x140080e4b  mov     rcx, [rcx+58h]; FileHandle
0x140080e4f  mov     [rsp+98h+FileInformationClass], eax; FileInformationClass
0x140080e53  call    cs:__imp_NtQueryInformationFile
0x140080e5a  nop     dword ptr [rax+rax+00h]
0x140080e5f  cmp     dword ptr [rsi+0C8h], 12h
0x140080e66  mov     edi, eax
0x140080e68  jz      loc_140081323
0x140080e6e  lea     r9, aSmb2executeque_0; "Smb2ExecuteQueryInfo"
0x140080e75  mov     byte ptr [rsp+98h+FileInformationClass], 1
0x140080e7a  xor     edx, edx
0x140080e7c  lea     rcx, [rbx+248h]
0x140080e83  mov     r8d, 452h
0x140080e89  call    SRV2_PERF_ENTER_EX
0x140080e8e  mov     rcx, gs:188h; Thread
0x140080e97  xor     edx, edx; Token
0x140080e99  call    cs:__imp_PsAssignImpersonationToken
0x140080ea0  nop     dword ptr [rax+rax+00h]
0x140080ea5  mov     rax, [r14]
0x140080ea8  mov     [rax+30h], edi
0x140080eab  mov     rax, [r14]
0x140080eae  mov     r15, [rbx+230h]
0x140080eb5  mov     edi, [rax+30h]
0x140080eb8  lea     eax, [rdi+rbp]
0x140080ebb  test    ebp, eax
0x140080ebd  jz      loc_140081193
0x140080ec3  cmp     byte ptr [r15+0C0h], 2
0x140080ecb  jz      loc_1400811E7
0x140080ed1  mov     rcx, rbx
0x140080ed4  call    Srv2SetResponseBufferToReceiveBuffer
0x140080ed9  mov     rax, [rbx+138h]
0x140080ee0  mov     ebp, 48h ; 'H'
0x140080ee5  mov     rsi, [rax+18h]
0x140080ee9  mov     rax, [r14]
0x140080eec  mov     ecx, [rax+38h]
0x140080eef  mov     [rsi+44h], ecx
0x140080ef2  mov     dword ptr [rsi+40h], 480009h
0x140080ef9  mov     rax, [rbx+138h]
0x140080f00  mov     r14, [rax+50h]
0x140080f04  mov     r12, [rax+18h]
0x140080f08  mov     r13, [rax+38h]
0x140080f0c  test    byte ptr [r14+0Ah], 20h
0x140080f11  jnz     loc_14008137C
0x140080f17  mov     r9d, ebp; Length
0x140080f1a  mov     r8, r12; VirtualAddress
0x140080f1d  mov     rdx, r14; TargetMdl
0x140080f20  mov     rcx, r13; SourceMdl
0x140080f23  call    cs:__imp_IoBuildPartialMdl
0x140080f2a  nop     dword ptr [rax+rax+00h]
0x140080f2f  mov     rax, [rbx+138h]
0x140080f36  mov     rdx, [rax+50h]
0x140080f3a  mov     rax, [rax+38h]
0x140080f3e  movzx   ecx, word ptr [rax+0Ah]
0x140080f42  mov     eax, 1000h
0x140080f47  and     cx, ax
0x140080f4a  or      [rdx+0Ah], cx
0x140080f4e  mov     r13d, [rsi+44h]
0x140080f52  test    r13d, r13d
0x140080f55  jz      short loc_140080FA5
0x140080f57  mov     rax, [r15+0A0h]
0x140080f5e  mov     rbp, [rax+50h]
0x140080f62  mov     r14, [rax+18h]
0x140080f66  mov     r12, [rax+38h]
0x140080f6a  test    byte ptr [rbp+0Ah], 20h
0x140080f6e  jnz     loc_140081394
0x140080f74  mov     r9d, r13d; Length
0x140080f77  mov     r8, r14; VirtualAddress
0x140080f7a  mov     rdx, rbp; TargetMdl
0x140080f7d  mov     rcx, r12; SourceMdl
0x140080f80  call    cs:__imp_IoBuildPartialMdl
0x140080f87  nop     dword ptr [rax+rax+00h]
0x140080f8c  mov     rdx, [r15+0A0h]
0x140080f93  mov     rax, [rbx+138h]
0x140080f9a  mov     rcx, [rax+50h]
0x140080f9e  mov     rax, [rdx+50h]
0x140080fa2  mov     [rcx], rax
0x140080fa5  movzx   ecx, word ptr [rsi+42h]
0x140080fa9  mov     edx, edi
0x140080fab  add     ecx, [rsi+44h]
0x140080fae  mov     rax, [rbx+138h]
0x140080fb5  mov     [rax+24h], ecx
0x140080fb8  mov     rcx, rbx
0x140080fbb  or      dword ptr [rbx+1E4h], 4
0x140080fc2  call    Smb2SetSuccess
0x140080fc7  xor     edx, edx
0x140080fc9  mov     rcx, rbx
0x140080fcc  call    Srv2CompleteWorkItem
0x140080fd1  mov     eax, 103h
0x140080fd6  add     rsp, 58h
0x140080fda  pop     r15
0x140080fdc  pop     r14
0x140080fde  pop     r13
0x140080fe0  pop     r12
0x140080fe2  pop     rdi
0x140080fe3  pop     rsi
0x140080fe4  pop     rbp
0x140080fe5  pop     rbx
0x140080fe6  retn
0x140080fe8  sub     ecx, 2
0x140080feb  jnz     loc_1400987C0
0x140080ff1  mov     rcx, rsi
0x140080ff4  call    Smb2ImpersonateWorkItem
0x140080ff9  mov     ebp, eax
0x140080ffb  test    eax, eax
0x140080ffd  js      loc_140081094
0x140081003  lea     r9, aSmb2executeque_0; "Smb2ExecuteQueryInfo"
0x14008100a  mov     byte ptr [rsp+98h+FileInformationClass], 1
0x14008100f  mov     r8d, 463h
0x140081015  lea     rcx, [rbx+248h]
0x14008101c  mov     dl, 2
0x14008101e  call    SRV2_PERF_ENTER_EX
0x140081023  mov     r8, [rsi+0A0h]
0x14008102a  mov     rcx, [rsi+50h]
0x14008102e  mov     rdx, [rbx+78h]
0x140081032  mov     eax, [rsi+0C8h]
0x140081038  add     rdx, 30h ; '0'; IoStatusBlock
0x14008103c  mov     r8, [r8+18h]; FsInformation
0x140081040  mov     rcx, [rcx+58h]; FileHandle
0x140081044  mov     r9d, [rsi+0C4h]; Length
0x14008104b  mov     [rsp+98h+FileInformationClass], eax; FsInformationClass
0x14008104f  call    cs:__imp_NtQueryVolumeInformationFile
0x140081056  nop     dword ptr [rax+rax+00h]
0x14008105b  lea     r9, aSmb2executeque_0; "Smb2ExecuteQueryInfo"
0x140081062  mov     byte ptr [rsp+98h+FileInformationClass], 1
0x140081067  xor     edx, edx
0x140081069  lea     rcx, [rbx+248h]
0x140081070  mov     r8d, 470h
0x140081076  mov     ebp, eax
0x140081078  call    SRV2_PERF_ENTER_EX
0x14008107d  mov     rcx, gs:188h; Thread
0x140081086  xor     edx, edx; Token
0x140081088  call    cs:__imp_PsAssignImpersonationToken
0x14008108f  nop     dword ptr [rax+rax+00h]
0x140081094  mov     rax, [rbx+78h]
0x140081098  mov     [rax+30h], ebp
0x14008109b  mov     ebp, 80000000h
0x1400810a0  mov     rax, [rbx+78h]
0x1400810a4  mov     r14, [rbx+230h]
0x1400810ab  mov     edi, [rax+30h]
0x1400810ae  lea     eax, [rdi+rbp]
0x1400810b1  test    ebp, eax
0x1400810b3  jz      loc_14008120B
0x1400810b9  cmp     byte ptr [r14+0C0h], 2
0x1400810c1  jz      loc_14008125B
0x1400810c7  mov     rcx, rbx
0x1400810ca  call    Srv2SetResponseBufferToReceiveBuffer
0x1400810cf  mov     rax, [rbx+138h]
0x1400810d6  mov     ebp, 48h ; 'H'
0x1400810db  mov     rsi, [rax+18h]
0x1400810df  mov     rax, [rbx+78h]
0x1400810e3  mov     ecx, [rax+38h]
0x1400810e6  mov     [rsi+44h], ecx
0x1400810e9  mov     dword ptr [rsi+40h], 480009h
0x1400810f0  mov     rax, [rbx+138h]
0x1400810f7  mov     r15, [rax+50h]
0x1400810fb  mov     r12, [rax+18h]
0x1400810ff  mov     r13, [rax+38h]
0x140081103  test    byte ptr [r15+0Ah], 20h
0x140081108  jnz     loc_1400812F3
0x14008110e  mov     r9d, ebp; Length
0x140081111  mov     r8, r12; VirtualAddress
0x140081114  mov     rdx, r15; TargetMdl
0x140081117  mov     rcx, r13; SourceMdl
0x14008111a  call    cs:__imp_IoBuildPartialMdl
0x140081121  nop     dword ptr [rax+rax+00h]
0x140081126  mov     rax, [rbx+138h]
0x14008112d  mov     rdx, [rax+50h]
0x140081131  mov     rax, [rax+38h]
0x140081135  movzx   ecx, word ptr [rax+0Ah]
0x140081139  mov     eax, 1000h
0x14008113e  and     cx, ax
0x140081141  or      [rdx+0Ah], cx
0x140081145  mov     r13d, [rsi+44h]
0x140081149  test    r13d, r13d
0x14008114c  jz      loc_140080FA5
0x140081152  mov     rax, [r14+0A0h]
0x140081159  mov     rbp, [rax+50h]
0x14008115d  mov     r15, [rax+18h]
0x140081161  mov     r12, [rax+38h]
0x140081165  test    byte ptr [rbp+0Ah], 20h
0x140081169  jnz     loc_14008130B
0x14008116f  mov     r9d, r13d; Length
0x140081172  mov     r8, r15; VirtualAddress
0x140081175  mov     rdx, rbp; TargetMdl
0x140081178  mov     rcx, r12; SourceMdl
0x14008117b  call    cs:__imp_IoBuildPartialMdl
0x140081182  nop     dword ptr [rax+rax+00h]
0x140081187  mov     rdx, [r14+0A0h]
0x14008118e  jmp     loc_140080F93
0x140081193  cmp     edi, 80000005h
0x140081199  jz      loc_140080EC3
0x14008119f  cmp     edi, 0C0000023h
0x1400811a5  jz      loc_14008128E
0x1400811ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400811b2  lea     rax, WPP_GLOBAL_Control
0x1400811b9  cmp     rcx, rax
0x1400811bc  jz      short loc_1400811CB
0x1400811be  test    dword ptr [rcx+2Ch], 8000000h
0x1400811c5  jnz     loc_140081365
0x1400811cb  mov     r9d, 3CBh
0x1400811d1  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400811d8  mov     edx, edi
0x1400811da  mov     rcx, rbx
0x1400811dd  call    _Smb2SetError
0x1400811e2  jmp     loc_140080FC7
0x1400811e7  cmp     dword ptr [r15+0C8h], 5
0x1400811ef  jnz     loc_140080ED1
0x1400811f5  mov     rax, [r15+0A0h]
0x1400811fc  mov     rcx, [rax+18h]
0x140081200  and     dword ptr [rcx], 1CDF91FEh
0x140081206  jmp     loc_140080ED1
0x14008120b  cmp     edi, 80000005h
0x140081211  jz      loc_1400810B9
0x140081217  cmp     edi, 0C0000023h
0x14008121d  jz      loc_1400812C0
0x140081223  mov     rcx, cs:WPP_GLOBAL_Control
0x14008122a  lea     rax, WPP_GLOBAL_Control
0x140081231  cmp     rcx, rax
0x140081234  jz      short loc_1400811CB
0x140081236  test    dword ptr [rcx+2Ch], 8000000h
0x14008123d  jz      short loc_1400811CB
0x14008123f  cmp     byte ptr [rcx+29h], 1
0x140081243  jb      short loc_1400811CB
0x140081245  movzx   eax, byte ptr [r14+0C0h]
0x14008124d  jmp     loc_140098A75
0x140081252  lea     r14, [rbx+78h]
0x140081256  jmp     loc_140080EA5
0x14008125b  cmp     dword ptr [r14+0C8h], 5
0x140081263  jnz     loc_1400810C7
0x140081269  mov     rax, [r14+0A0h]
0x140081270  mov     rcx, [rax+18h]
0x140081274  and     dword ptr [rcx], 1CDF91FEh
0x14008127a  jmp     loc_1400810C7
0x14008127f  mov     rcx, rbx
0x140081282  call    Smb2QueryFileNormalizedName
0x140081287  mov     edi, eax
0x140081289  jmp     loc_140080E6E
0x14008128e  mov     r9b, 1
0x140081291  xor     edx, edx
0x140081293  mov     r8d, 4
0x140081299  mov     rcx, rbx
0x14008129c  call    Smb2AllocateExtendedErrorBuffer
0x1400812a1  mov     rdx, rax
0x1400812a4  test    rax, rax
0x1400812a7  jnz     short loc_1400812B3
0x1400812a9  mov     edi, 0C000009Ah
0x1400812ae  jmp     loc_1400811AB
0x1400812b3  mov     rax, [r14]
0x1400812b6  mov     ecx, [rax+38h]
0x1400812b9  mov     [rdx], ecx
0x1400812bb  jmp     loc_1400811AB
0x1400812c0  mov     r9b, 1
0x1400812c3  xor     edx, edx
0x1400812c5  mov     r8d, 4
0x1400812cb  mov     rcx, rbx
0x1400812ce  call    Smb2AllocateExtendedErrorBuffer
0x1400812d3  mov     rdx, rax
0x1400812d6  test    rax, rax
0x1400812d9  jnz     short loc_1400812E5
0x1400812db  mov     edi, 0C000009Ah
0x1400812e0  jmp     loc_140081223
0x1400812e5  mov     rax, [rbx+78h]
0x1400812e9  mov     ecx, [rax+38h]
  ... truncated ...
```
