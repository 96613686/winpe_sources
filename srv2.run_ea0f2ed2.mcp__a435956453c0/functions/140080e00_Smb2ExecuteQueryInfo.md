# Smb2ExecuteQueryInfo

- ea: `0x140080e00`
- end: `0x1400813fc`
- name: `Smb2ExecuteQueryInfo`
- size: `1532`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400748b0`

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
- `0x140080e00`
- `0x140081404`
- `0x140085440`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140080f73`
- `ntoskrnl!IoBuildPartialMdl` at `0x140080fd0`
- `ntoskrnl!IoBuildPartialMdl` at `0x14008116a`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400811cb`
- `ntoskrnl!IoBuildPartialMdl` at `0x140080f73`
- `ntoskrnl!IoBuildPartialMdl` at `0x140080fd0`
- `ntoskrnl!IoBuildPartialMdl` at `0x14008116a`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400811cb`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008134a`
- `ntoskrnl!MmUnmapLockedPages` at `0x140081362`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400813d3`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400813eb`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008134a`
- `ntoskrnl!MmUnmapLockedPages` at `0x140081362`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400813d3`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400813eb`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009894c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14009894c`
- `ntoskrnl!NtQuerySecurityObject` at `0x1400989f6`
- `ntoskrnl!NtQuerySecurityObject` at `0x1400989f6`
- `ntoskrnl!NtQueryInformationFile` at `0x140080ea3`
- `ntoskrnl!NtQueryInformationFile` at `0x140080ea3`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140080ee9`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400810d8`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009896d`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140080ee9`
- `ntoskrnl!PsAssignImpersonationToken` at `0x1400810d8`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14009896d`
- `ntoskrnl!NtQueryEaFile` at `0x140098ab3`
- `ntoskrnl!NtQueryEaFile` at `0x140098ab3`
- `ntoskrnl!NtQueryVolumeInformationFile` at `0x14008109f`
- `ntoskrnl!NtQueryVolumeInformationFile` at `0x14008109f`
- `ntoskrnl!NtQueryQuotaInformationFile` at `0x140098911`
- `ntoskrnl!NtQueryQuotaInformationFile` at `0x140098911`

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
      WPP_SF_qDD(v39->AttachedDevice, 33, &WPP_03d80664418738de4d4c12d6c892b627_Traceguids, a1, Status, v40);
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
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, &WPP_03d80664418738de4d4c12d6c892b627_Traceguids, a1);
  }
  Smb2SetError(a1, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c", 1218);
  return 0;
}

```

## disassembly

```asm
0x140080e00  push    rbx
0x140080e02  push    rbp
0x140080e03  push    rsi
0x140080e04  push    rdi
0x140080e05  push    r12
0x140080e07  push    r13
0x140080e09  push    r14
0x140080e0b  push    r15
0x140080e0d  sub     rsp, 58h
0x140080e11  mov     rsi, [rcx+230h]
0x140080e18  mov     rbx, rcx
0x140080e1b  movzx   ecx, byte ptr [rsi+0C0h]
0x140080e22  cmp     ecx, 1
0x140080e25  jnz     loc_140081038
0x140080e2b  mov     rcx, rsi
0x140080e2e  call    Smb2ImpersonateWorkItem
0x140080e33  mov     edi, eax
0x140080e35  mov     ebp, 80000000h
0x140080e3a  test    eax, eax
0x140080e3c  js      loc_1400812A2
0x140080e42  lea     r9, aSmb2executeque_0; "Smb2ExecuteQueryInfo"
0x140080e49  mov     byte ptr [rsp+98h+FileInformationClass], 1
0x140080e4e  mov     r8d, 410h
0x140080e54  lea     rcx, [rbx+248h]
0x140080e5b  mov     dl, 2
0x140080e5d  call    SRV2_PERF_ENTER_EX
0x140080e62  mov     eax, [rsi+0C8h]
0x140080e68  cmp     eax, 0Fh
0x140080e6b  jz      loc_14008138E
0x140080e71  lea     r14, [rbx+78h]
0x140080e75  cmp     eax, 30h ; '0'
0x140080e78  jz      loc_1400812CF
0x140080e7e  mov     r8, [rsi+0A0h]
0x140080e85  mov     rcx, [rsi+50h]
0x140080e89  mov     rdx, [r14]
0x140080e8c  mov     r9d, [rsi+0C4h]; Length
0x140080e93  add     rdx, 30h ; '0'; IoStatusBlock
0x140080e97  mov     r8, [r8+18h]; FileInformation
0x140080e9b  mov     rcx, [rcx+58h]; FileHandle
0x140080e9f  mov     [rsp+98h+FileInformationClass], eax; FileInformationClass
0x140080ea3  call    cs:__imp_NtQueryInformationFile
0x140080eaa  nop     dword ptr [rax+rax+00h]
0x140080eaf  cmp     dword ptr [rsi+0C8h], 12h
0x140080eb6  mov     edi, eax
0x140080eb8  jz      loc_140081373
0x140080ebe  lea     r9, aSmb2executeque_0; "Smb2ExecuteQueryInfo"
0x140080ec5  mov     byte ptr [rsp+98h+FileInformationClass], 1
0x140080eca  xor     edx, edx
0x140080ecc  lea     rcx, [rbx+248h]
0x140080ed3  mov     r8d, 452h
0x140080ed9  call    SRV2_PERF_ENTER_EX
0x140080ede  mov     rcx, gs:188h; Thread
0x140080ee7  xor     edx, edx; Token
0x140080ee9  call    cs:__imp_PsAssignImpersonationToken
0x140080ef0  nop     dword ptr [rax+rax+00h]
0x140080ef5  mov     rax, [r14]
0x140080ef8  mov     [rax+30h], edi
0x140080efb  mov     rax, [r14]
0x140080efe  mov     r15, [rbx+230h]
0x140080f05  mov     edi, [rax+30h]
0x140080f08  lea     eax, [rdi+rbp]
0x140080f0b  test    ebp, eax
0x140080f0d  jz      loc_1400811E3
0x140080f13  cmp     byte ptr [r15+0C0h], 2
0x140080f1b  jz      loc_140081237
0x140080f21  mov     rcx, rbx
0x140080f24  call    Srv2SetResponseBufferToReceiveBuffer
0x140080f29  mov     rax, [rbx+138h]
0x140080f30  mov     ebp, 48h ; 'H'
0x140080f35  mov     rsi, [rax+18h]
0x140080f39  mov     rax, [r14]
0x140080f3c  mov     ecx, [rax+38h]
0x140080f3f  mov     [rsi+44h], ecx
0x140080f42  mov     dword ptr [rsi+40h], 480009h
0x140080f49  mov     rax, [rbx+138h]
0x140080f50  mov     r14, [rax+50h]
0x140080f54  mov     r12, [rax+18h]
0x140080f58  mov     r13, [rax+38h]
0x140080f5c  test    byte ptr [r14+0Ah], 20h
0x140080f61  jnz     loc_1400813CC
0x140080f67  mov     r9d, ebp; Length
0x140080f6a  mov     r8, r12; VirtualAddress
0x140080f6d  mov     rdx, r14; TargetMdl
0x140080f70  mov     rcx, r13; SourceMdl
0x140080f73  call    cs:__imp_IoBuildPartialMdl
0x140080f7a  nop     dword ptr [rax+rax+00h]
0x140080f7f  mov     rax, [rbx+138h]
0x140080f86  mov     rdx, [rax+50h]
0x140080f8a  mov     rax, [rax+38h]
0x140080f8e  movzx   ecx, word ptr [rax+0Ah]
0x140080f92  mov     eax, 1000h
0x140080f97  and     cx, ax
0x140080f9a  or      [rdx+0Ah], cx
0x140080f9e  mov     r13d, [rsi+44h]
0x140080fa2  test    r13d, r13d
0x140080fa5  jz      short loc_140080FF5
0x140080fa7  mov     rax, [r15+0A0h]
0x140080fae  mov     rbp, [rax+50h]
0x140080fb2  mov     r14, [rax+18h]
0x140080fb6  mov     r12, [rax+38h]
0x140080fba  test    byte ptr [rbp+0Ah], 20h
0x140080fbe  jnz     loc_1400813E4
0x140080fc4  mov     r9d, r13d; Length
0x140080fc7  mov     r8, r14; VirtualAddress
0x140080fca  mov     rdx, rbp; TargetMdl
0x140080fcd  mov     rcx, r12; SourceMdl
0x140080fd0  call    cs:__imp_IoBuildPartialMdl
0x140080fd7  nop     dword ptr [rax+rax+00h]
0x140080fdc  mov     rdx, [r15+0A0h]
0x140080fe3  mov     rax, [rbx+138h]
0x140080fea  mov     rcx, [rax+50h]
0x140080fee  mov     rax, [rdx+50h]
0x140080ff2  mov     [rcx], rax
0x140080ff5  movzx   ecx, word ptr [rsi+42h]
0x140080ff9  mov     edx, edi
0x140080ffb  add     ecx, [rsi+44h]
0x140080ffe  mov     rax, [rbx+138h]
0x140081005  mov     [rax+24h], ecx
0x140081008  mov     rcx, rbx
0x14008100b  or      dword ptr [rbx+1E4h], 4
0x140081012  call    Smb2SetSuccess
0x140081017  xor     edx, edx
0x140081019  mov     rcx, rbx
0x14008101c  call    Srv2CompleteWorkItem
0x140081021  mov     eax, 103h
0x140081026  add     rsp, 58h
0x14008102a  pop     r15
0x14008102c  pop     r14
0x14008102e  pop     r13
0x140081030  pop     r12
0x140081032  pop     rdi
0x140081033  pop     rsi
0x140081034  pop     rbp
0x140081035  pop     rbx
0x140081036  retn
0x140081038  sub     ecx, 2
0x14008103b  jnz     loc_140098810
0x140081041  mov     rcx, rsi
0x140081044  call    Smb2ImpersonateWorkItem
0x140081049  mov     ebp, eax
0x14008104b  test    eax, eax
0x14008104d  js      loc_1400810E4
0x140081053  lea     r9, aSmb2executeque_0; "Smb2ExecuteQueryInfo"
0x14008105a  mov     byte ptr [rsp+98h+FileInformationClass], 1
0x14008105f  mov     r8d, 463h
0x140081065  lea     rcx, [rbx+248h]
0x14008106c  mov     dl, 2
0x14008106e  call    SRV2_PERF_ENTER_EX
0x140081073  mov     r8, [rsi+0A0h]
0x14008107a  mov     rcx, [rsi+50h]
0x14008107e  mov     rdx, [rbx+78h]
0x140081082  mov     eax, [rsi+0C8h]
0x140081088  add     rdx, 30h ; '0'; IoStatusBlock
0x14008108c  mov     r8, [r8+18h]; FsInformation
0x140081090  mov     rcx, [rcx+58h]; FileHandle
0x140081094  mov     r9d, [rsi+0C4h]; Length
0x14008109b  mov     [rsp+98h+FileInformationClass], eax; FsInformationClass
0x14008109f  call    cs:__imp_NtQueryVolumeInformationFile
0x1400810a6  nop     dword ptr [rax+rax+00h]
0x1400810ab  lea     r9, aSmb2executeque_0; "Smb2ExecuteQueryInfo"
0x1400810b2  mov     byte ptr [rsp+98h+FileInformationClass], 1
0x1400810b7  xor     edx, edx
0x1400810b9  lea     rcx, [rbx+248h]
0x1400810c0  mov     r8d, 470h
0x1400810c6  mov     ebp, eax
0x1400810c8  call    SRV2_PERF_ENTER_EX
0x1400810cd  mov     rcx, gs:188h; Thread
0x1400810d6  xor     edx, edx; Token
0x1400810d8  call    cs:__imp_PsAssignImpersonationToken
0x1400810df  nop     dword ptr [rax+rax+00h]
0x1400810e4  mov     rax, [rbx+78h]
0x1400810e8  mov     [rax+30h], ebp
0x1400810eb  mov     ebp, 80000000h
0x1400810f0  mov     rax, [rbx+78h]
0x1400810f4  mov     r14, [rbx+230h]
0x1400810fb  mov     edi, [rax+30h]
0x1400810fe  lea     eax, [rdi+rbp]
0x140081101  test    ebp, eax
0x140081103  jz      loc_14008125B
0x140081109  cmp     byte ptr [r14+0C0h], 2
0x140081111  jz      loc_1400812AB
0x140081117  mov     rcx, rbx
0x14008111a  call    Srv2SetResponseBufferToReceiveBuffer
0x14008111f  mov     rax, [rbx+138h]
0x140081126  mov     ebp, 48h ; 'H'
0x14008112b  mov     rsi, [rax+18h]
0x14008112f  mov     rax, [rbx+78h]
0x140081133  mov     ecx, [rax+38h]
0x140081136  mov     [rsi+44h], ecx
0x140081139  mov     dword ptr [rsi+40h], 480009h
0x140081140  mov     rax, [rbx+138h]
0x140081147  mov     r15, [rax+50h]
0x14008114b  mov     r12, [rax+18h]
0x14008114f  mov     r13, [rax+38h]
0x140081153  test    byte ptr [r15+0Ah], 20h
0x140081158  jnz     loc_140081343
0x14008115e  mov     r9d, ebp; Length
0x140081161  mov     r8, r12; VirtualAddress
0x140081164  mov     rdx, r15; TargetMdl
0x140081167  mov     rcx, r13; SourceMdl
0x14008116a  call    cs:__imp_IoBuildPartialMdl
0x140081171  nop     dword ptr [rax+rax+00h]
0x140081176  mov     rax, [rbx+138h]
0x14008117d  mov     rdx, [rax+50h]
0x140081181  mov     rax, [rax+38h]
0x140081185  movzx   ecx, word ptr [rax+0Ah]
0x140081189  mov     eax, 1000h
0x14008118e  and     cx, ax
0x140081191  or      [rdx+0Ah], cx
0x140081195  mov     r13d, [rsi+44h]
0x140081199  test    r13d, r13d
0x14008119c  jz      loc_140080FF5
0x1400811a2  mov     rax, [r14+0A0h]
0x1400811a9  mov     rbp, [rax+50h]
0x1400811ad  mov     r15, [rax+18h]
0x1400811b1  mov     r12, [rax+38h]
0x1400811b5  test    byte ptr [rbp+0Ah], 20h
0x1400811b9  jnz     loc_14008135B
0x1400811bf  mov     r9d, r13d; Length
0x1400811c2  mov     r8, r15; VirtualAddress
0x1400811c5  mov     rdx, rbp; TargetMdl
0x1400811c8  mov     rcx, r12; SourceMdl
0x1400811cb  call    cs:__imp_IoBuildPartialMdl
0x1400811d2  nop     dword ptr [rax+rax+00h]
0x1400811d7  mov     rdx, [r14+0A0h]
0x1400811de  jmp     loc_140080FE3
0x1400811e3  cmp     edi, 80000005h
0x1400811e9  jz      loc_140080F13
0x1400811ef  cmp     edi, 0C0000023h
0x1400811f5  jz      loc_1400812DE
0x1400811fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140081202  lea     rax, WPP_GLOBAL_Control
0x140081209  cmp     rcx, rax
0x14008120c  jz      short loc_14008121B
0x14008120e  test    dword ptr [rcx+2Ch], 8000000h
0x140081215  jnz     loc_1400813B5
0x14008121b  mov     r9d, 3CBh
0x140081221  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140081228  mov     edx, edi
0x14008122a  mov     rcx, rbx
0x14008122d  call    _Smb2SetError
0x140081232  jmp     loc_140081017
0x140081237  cmp     dword ptr [r15+0C8h], 5
0x14008123f  jnz     loc_140080F21
0x140081245  mov     rax, [r15+0A0h]
0x14008124c  mov     rcx, [rax+18h]
0x140081250  and     dword ptr [rcx], 1CDF91FEh
0x140081256  jmp     loc_140080F21
0x14008125b  cmp     edi, 80000005h
0x140081261  jz      loc_140081109
0x140081267  cmp     edi, 0C0000023h
0x14008126d  jz      loc_140081310
0x140081273  mov     rcx, cs:WPP_GLOBAL_Control
0x14008127a  lea     rax, WPP_GLOBAL_Control
0x140081281  cmp     rcx, rax
0x140081284  jz      short loc_14008121B
0x140081286  test    dword ptr [rcx+2Ch], 8000000h
0x14008128d  jz      short loc_14008121B
0x14008128f  cmp     byte ptr [rcx+29h], 1
0x140081293  jb      short loc_14008121B
0x140081295  movzx   eax, byte ptr [r14+0C0h]
0x14008129d  jmp     loc_140098AC5
0x1400812a2  lea     r14, [rbx+78h]
0x1400812a6  jmp     loc_140080EF5
0x1400812ab  cmp     dword ptr [r14+0C8h], 5
0x1400812b3  jnz     loc_140081117
0x1400812b9  mov     rax, [r14+0A0h]
0x1400812c0  mov     rcx, [rax+18h]
0x1400812c4  and     dword ptr [rcx], 1CDF91FEh
0x1400812ca  jmp     loc_140081117
0x1400812cf  mov     rcx, rbx
0x1400812d2  call    Smb2QueryFileNormalizedName
0x1400812d7  mov     edi, eax
0x1400812d9  jmp     loc_140080EBE
0x1400812de  mov     r9b, 1
0x1400812e1  xor     edx, edx
0x1400812e3  mov     r8d, 4
0x1400812e9  mov     rcx, rbx
0x1400812ec  call    Smb2AllocateExtendedErrorBuffer
0x1400812f1  mov     rdx, rax
0x1400812f4  test    rax, rax
0x1400812f7  jnz     short loc_140081303
0x1400812f9  mov     edi, 0C000009Ah
0x1400812fe  jmp     loc_1400811FB
0x140081303  mov     rax, [r14]
0x140081306  mov     ecx, [rax+38h]
0x140081309  mov     [rdx], ecx
0x14008130b  jmp     loc_1400811FB
0x140081310  mov     r9b, 1
0x140081313  xor     edx, edx
0x140081315  mov     r8d, 4
0x14008131b  mov     rcx, rbx
0x14008131e  call    Smb2AllocateExtendedErrorBuffer
0x140081323  mov     rdx, rax
0x140081326  test    rax, rax
0x140081329  jnz     short loc_140081335
0x14008132b  mov     edi, 0C000009Ah
0x140081330  jmp     loc_140081273
0x140081335  mov     rax, [rbx+78h]
0x140081339  mov     ecx, [rax+38h]
  ... truncated ...
```
