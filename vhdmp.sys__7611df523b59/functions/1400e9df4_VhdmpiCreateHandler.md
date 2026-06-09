# VhdmpiCreateHandler

- ea: `0x1400e9df4`
- end: `0x1400ea569`
- name: `VhdmpiCreateHandler`
- size: `1909`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140019ff0`

## callees

- `0x140014c7c`
- `0x14001dcc4`
- `0x140023560`
- `0x1400272b4`
- `0x1400358bc`
- `0x140035e94`
- `0x14005d7c0`
- `0x14009d9a4`
- `0x14009e984`
- `0x1400c7664`
- `0x1400ca5d4`
- `0x1400caf6c`
- `0x1400cc4f8`
- `0x1400cf084`
- `0x1400e2160`
- `0x1400e6f78`
- `0x1400e9df4`
- `0x1400ed5a0`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400e9fe6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400e9fe6`
- `ntoskrnl!SeAccessCheck` at `0x1400ea032`
- `ntoskrnl!SeAccessCheck` at `0x1400ea032`
- `ntoskrnl!SeFreePrivileges` at `0x1400ea04a`
- `ntoskrnl!SeFreePrivileges` at `0x1400ea04a`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea4ec`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea4ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea405`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea4d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea405`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea4d4`
- `ntoskrnl!EtwActivityIdControl` at `0x1400e9ec6`
- `ntoskrnl!EtwActivityIdControl` at `0x1400e9ec6`
- `ntoskrnl!ExAllocatePool2` at `0x1400ea151`
- `ntoskrnl!ExAllocatePool2` at `0x1400ea151`

## string_xrefs

- `0x1400e9e99`: `VhdmpiCreateHandler: enter with file object %p`
- `0x1400ea23b`: `VhdmpiCreateHandler: unable to open backing store (0x%08x)`
- `0x1400ea3b4`: `VhdmpiCreateHandler: VHD open attempt failed (0x%08x)`
- `0x1400e9eae`: `VhdmpiCreateHandler`
- `0x1400e9f62`: `VhdmpiCreateHandler`
- `0x1400ea11f`: `VhdmpiCreateHandler`
- `0x1400ea19b`: `VhdmpiCreateHandler`
- `0x1400ea22b`: `VhdmpiCreateHandler`
- `0x1400ea368`: `VhdmpiCreateHandler`
- `0x1400ea3a4`: `VhdmpiCreateHandler`
- `0x1400ea53a`: `VhdmpiCreateHandler`
- `0x1400e9f4b`: `VhdmpiCreateHandler: invalid EA device or vendor id`
- `0x1400ea351`: `VhdmpiCreateHandler: Access not granted.`
- `0x1400ea105`: `VhdmpiCreateHandler: File object in IRP indicates empty token, but is not for a DVD device.`

## pseudocode

```c
__int64 __fastcall VhdmpiCreateHandler(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  struct _VHD_HANDLE_CONTEXT *v2; // rdi
  int *v3; // rsi
  struct _VIRTUAL_DISK_EA_BUFFER *v4; // r14
  PFILE_OBJECT FileObject; // r8
  char v7; // r8
  __int64 v8; // rcx
  int DriveType; // eax
  char **v10; // r15
  bool v11; // zf
  KPROCESSOR_MODE AccessMode; // r12
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v14; // r12
  PFILE_OBJECT v15; // r12
  _WORD *v16; // xmm0_8
  struct _VHD_HANDLE_CONTEXT *Pool2; // rax
  int v18; // edx
  __int64 v19; // rax
  __int64 v20; // r15
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r10d
  int v26; // r11d
  __int64 v27; // rax
  const __int64 *v28; // rdi
  int *v29; // r14
  int v30; // eax
  int v31; // ecx
  int v32; // edx
  int v33; // r8d
  int v34; // r9d
  int v35; // r10d
  const __int64 *v36; // rdi
  int *v37; // r14
  unsigned int v38; // edi
  int v39; // r9d
  char Privileges; // [rsp+28h] [rbp-D8h]
  char Privilegesa; // [rsp+28h] [rbp-D8h]
  char AccessStatus[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v44; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int8 v45[3]; // [rsp+85h] [rbp-7Bh] BYREF
  int v46; // [rsp+88h] [rbp-78h]
  PVOID P; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+98h] [rbp-68h] BYREF
  DWORD GrantedAccess; // [rsp+A8h] [rbp-58h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp-50h]
  PPRIVILEGE_SET v51; // [rsp+B8h] [rbp-48h] BYREF
  PIO_SECURITY_CONTEXT SecurityContext; // [rsp+C0h] [rbp-40h]
  struct _VIRTUAL_DISK_EA_BUFFER *v53[2]; // [rsp+C8h] [rbp-38h] BYREF
  struct _IO_STACK_LOCATION *v54; // [rsp+D8h] [rbp-28h]
  PFILE_OBJECT v55; // [rsp+E0h] [rbp-20h]
  GUID ActivityId; // [rsp+E8h] [rbp-18h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v2 = 0;
  GrantedAccess = 0;
  FileName = 0;
  v51 = 0;
  v3 = 0;
  *(_DWORD *)AccessStatus = -1073741823;
  v4 = 0;
  FileObject = CurrentStackLocation->FileObject;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  v45[0] = 0;
  v44 = 0;
  v46 = 0;
  v54 = CurrentStackLocation;
  v55 = FileObject;
  P = 0;
  *(_OWORD *)v53 = 0;
  ActivityId = 0;
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents((int)"VhdmpiCreateHandler", 3545, 5, 16, "VhdmpiCreateHandler: enter with file object %p", v7);
  EtwActivityIdControl(3u, &ActivityId);
  if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(v8, VirtualDiskHandleCreateBegin, &ActivityId);
  *(_DWORD *)AccessStatus = VhdmpiValidateCreateRequest(a1, (struct _VHDMP_CREATE_INFORMATION *)v53, &v44);
  if ( *(int *)AccessStatus < 0 || v44 )
  {
LABEL_69:
    if ( *(int *)AccessStatus >= 0 )
    {
LABEL_73:
      if ( v2 )
      {
        if ( *((_QWORD *)v2 + 7) )
          VhdmpiDetachHandleFromVirtualDisk(v2);
        if ( *((_QWORD *)v2 + 38) )
          VhdmpiReleaseVhdSetFileRef(v2);
        VhdmpiCleanupSecurityContext((char *)v2 + 16);
        ExFreePoolWithTag(v2, 0x63444856u);
      }
      if ( *(int *)AccessStatus < 0 && (Microsoft_Windows_VHDMPEnableBits & 2) != 0 )
      {
        if ( v4 )
        {
          v30 = *((_DWORD *)v4 + 13);
          v31 = *((_DWORD *)v4 + 10);
          v32 = *((_DWORD *)v4 + 11);
          v33 = *((_DWORD *)v4 + 12);
          v34 = *((_DWORD *)v4 + 14);
          v35 = *((_DWORD *)v4 + 15);
        }
        else
        {
          LOBYTE(v30) = 0;
          v31 = 0;
          LOBYTE(v32) = 0;
          LOBYTE(v33) = 0;
          LOBYTE(v34) = 0;
          LOBYTE(v35) = 0;
        }
        v36 = &VhdmpZeroGuid;
        v37 = &dword_1400613A4;
        if ( v53[1] )
          v36 = (const __int64 *)v53[1];
        if ( v3 )
          v37 = v3;
        McTemplateK0qzjqqqqqttppp_EtwWriteTransfer(
          v31,
          (unsigned int)VirtualDiskHandleCreateError,
          (unsigned int)&ActivityId,
          *(_DWORD *)AccessStatus,
          (__int64)v37,
          (__int64)v36,
          v46,
          v30,
          v31,
          v32,
          v33,
          v34,
          v35,
          0,
          0);
      }
      goto LABEL_89;
    }
LABEL_70:
    a1->IoStatus.Information = 0;
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents(
        (int)"VhdmpiCreateHandler",
        3806,
        2,
        16,
        "VhdmpiCreateHandler: VHD open attempt failed (0x%08x)",
        AccessStatus[0]);
    goto LABEL_73;
  }
  v4 = v53[0];
  DriveType = VhdmpiGetDriveType((char *)v53[0] + 16, 0);
  v46 = DriveType;
  switch ( DriveType )
  {
    case 0:
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
        TraceEvents(
          (int)"VhdmpiCreateHandler",
          3567,
          2,
          16,
          "VhdmpiCreateHandler: invalid EA device or vendor id",
          Privileges);
      *(_DWORD *)AccessStatus = -1073741811;
      goto LABEL_70;
    case 1:
      v10 = &Vhd1Parser;
      goto LABEL_22;
    case 2:
      goto LABEL_20;
  }
  if ( DriveType != 3 )
  {
    if ( DriveType != 4 )
    {
      v10 = 0;
LABEL_22:
      SecurityDescriptor = VhdmpiVhdSecurityDescriptor;
      goto LABEL_23;
    }
LABEL_20:
    v10 = &Vhd2Parser;
    goto LABEL_22;
  }
  *(_DWORD *)AccessStatus = VhdmpiValidateIsoFlags(v4);
  if ( *(int *)AccessStatus < 0 )
    goto LABEL_69;
  v10 = &IsoParser;
  SecurityDescriptor = VhdmpiIsoSecurityDescriptor;
LABEL_23:
  v11 = (CurrentStackLocation->Flags & 1) == 0;
  AccessMode = 1;
  if ( v11 )
    AccessMode = a1->RequestorMode;
  GenericMapping = IoGetFileObjectGenericMapping();
  v14 = SeAccessCheck(
          SecurityDescriptor,
          &SecurityContext->AccessState->SubjectSecurityContext,
          0,
          SecurityContext->DesiredAccess,
          0,
          &v51,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          (PNTSTATUS)AccessStatus);
  if ( v51 )
    SeFreePrivileges(v51);
  if ( !v14 || *(int *)AccessStatus < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents((int)"VhdmpiCreateHandler", 3636, 2, 16, "VhdmpiCreateHandler: Access not granted.", Privilegesa);
    goto LABEL_69;
  }
  *(_DWORD *)AccessStatus = VhdmpiCheckForSharedVhd(a1, v45);
  if ( *(int *)AccessStatus < 0 )
    goto LABEL_69;
  if ( (v54->Flags & 1) != 0 || a1->RequestorMode == 1 )
    LOBYTE(v3) = 1;
  v15 = v55;
  FileName = v55->FileName;
  v16 = (_WORD *)_mm_srli_si128((__m128i)FileName, 8).m128i_u64[0];
  if ( *v16 == 92 )
  {
    FileName.Buffer = v16 + 1;
    FileName.Length -= 2;
    FileName.MaximumLength -= 2;
  }
  VhdmpiDuplicateUnicodeStringToString(&FileName, &P);
  if ( VhdmpiIsEmptyPathToken(&FileName) )
  {
    if ( *((_DWORD *)v4 + 4) != 1 )
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
        TraceEvents(
          (int)"VhdmpiCreateHandler",
          3683,
          2,
          16,
          "VhdmpiCreateHandler: File object in IRP indicates empty token, but is not for a DVD device.",
          Privilegesa);
      *(_DWORD *)AccessStatus = -1073741811;
LABEL_41:
      v3 = (int *)P;
      goto LABEL_70;
    }
    FileName.Length = 0;
  }
  Pool2 = (struct _VHD_HANDLE_CONTEXT *)ExAllocatePool2(72, 448, 1665419350);
  v2 = Pool2;
  if ( !Pool2 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 1) )
      TraceEvents((int)"VhdmpiCreateHandler", 3710, 2, v18, "Failed to allocate handle context", Privilegesa);
    *(_DWORD *)AccessStatus = -1073741670;
    goto LABEL_41;
  }
  *(_DWORD *)AccessStatus = VhdmpiInitializeHandleContext(
                              Pool2,
                              &FileName,
                              v4,
                              v45[0],
                              (char)v3,
                              v53[1],
                              &SecurityContext->AccessState->SubjectSecurityContext);
  if ( *(int *)AccessStatus < 0 )
    goto LABEL_54;
  if ( v46 == 4 )
  {
    *(_DWORD *)AccessStatus = VhdmpiCreateOrShareVhdSet(v2, &FileName);
    if ( *(int *)AccessStatus < 0 )
    {
LABEL_54:
      v3 = (int *)P;
      goto LABEL_69;
    }
  }
  else
  {
    *(_DWORD *)AccessStatus = VhdmpiCreateOrShareVirtualDisk((struct _BACKING_STORE_PARSER *)v10, v2, &FileName);
    if ( *(int *)AccessStatus < 0 )
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
        TraceEvents(
          (int)"VhdmpiCreateHandler",
          3743,
          2,
          16,
          "VhdmpiCreateHandler: unable to open backing store (0x%08x)",
          AccessStatus[0]);
      goto LABEL_54;
    }
  }
  v3 = (int *)P;
  v15->FsContext2 = v2;
  if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
  {
    v19 = *((_QWORD *)v2 + 7);
    if ( v19 )
      v20 = *(_QWORD *)(v19 + 2816);
    else
      LOBYTE(v20) = 0;
    v21 = *((_DWORD *)v4 + 14);
    v22 = *((_DWORD *)v4 + 12);
    v23 = *((_DWORD *)v4 + 11);
    v24 = *((_DWORD *)v4 + 15);
    v25 = *((_DWORD *)v4 + 10);
    v26 = *((_DWORD *)v4 + 13);
    v27 = *((_QWORD *)v2 + 49);
    v28 = &VhdmpZeroGuid;
    if ( v53[1] )
      v28 = (const __int64 *)v53[1];
    v29 = &dword_1400613A4;
    if ( v3 )
      v29 = v3;
    McTemplateK0qzjqqqqqttppp_EtwWriteTransfer(
      v24,
      (unsigned int)VirtualDiskHandleCreateSuccess,
      (unsigned int)&ActivityId,
      0,
      (__int64)v29,
      (__int64)v28,
      v46,
      v26,
      v25,
      v23,
      v22,
      v21,
      v24,
      v27,
      v20);
  }
  *(_DWORD *)AccessStatus = 0;
LABEL_89:
  if ( v3 )
    ExFreePoolWithTag(v3, 0x7A444856u);
  a1->IoStatus.Status = *(_DWORD *)AccessStatus;
  IofCompleteRequest(a1, 0);
  v38 = *(_DWORD *)AccessStatus;
  if ( *(int *)AccessStatus < 0
    && (unsigned int)dword_140087708 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
  {
    TraceEvents((int)"VhdmpiCreateHandler", 3851, 2, v39, "Return with status 0x%08X", v38);
  }
  return v38;
}

```

## disassembly

```asm
0x1400e9df4  push    rbp
0x1400e9df6  push    rbx
0x1400e9df7  push    rsi
0x1400e9df8  push    rdi
0x1400e9df9  push    r12
0x1400e9dfb  push    r13
0x1400e9dfd  push    r14
0x1400e9dff  push    r15
0x1400e9e01  lea     rbp, [rsp-8]
0x1400e9e06  sub     rsp, 108h
0x1400e9e0d  mov     rax, cs:__security_cookie
0x1400e9e14  xor     rax, rsp
0x1400e9e17  mov     [rbp+40h+var_48], rax
0x1400e9e1b  mov     r12, [rcx+0B8h]
0x1400e9e22  xor     edi, edi
0x1400e9e24  xorps   xmm0, xmm0
0x1400e9e27  mov     [rbp+40h+var_98], 0
0x1400e9e2e  movups  xmmword ptr [rbp+40h+var_A8.Length], xmm0
0x1400e9e32  mov     [rbp+40h+var_88], rdi
0x1400e9e36  xor     esi, esi
0x1400e9e38  mov     dword ptr [rbp+40h+var_C0], 0C0000001h
0x1400e9e3f  lea     r15d, [rdi+10h]
0x1400e9e43  mov     rax, [r12+8]
0x1400e9e48  xor     r14d, r14d
0x1400e9e4b  mov     r8, [r12+30h]
0x1400e9e50  mov     r13, rcx
0x1400e9e53  mov     [rbp+40h+var_80], rax
0x1400e9e57  mov     eax, cs:dword_140087708
0x1400e9e5d  mov     [rbp+40h+var_BB], dil
0x1400e9e61  mov     [rbp+40h+var_BC], dil
0x1400e9e65  mov     [rbp+40h+var_B8], edi
0x1400e9e68  mov     [rbp+40h+var_68], r12
0x1400e9e6c  mov     [rbp+40h+var_60], r8
0x1400e9e70  mov     [rbp+40h+P], rsi
0x1400e9e74  movups  xmmword ptr [rbp+40h+var_78], xmm0
0x1400e9e78  movups  xmmword ptr [rbp+40h+ActivityId.Data1], xmm0
0x1400e9e7c  cmp     eax, 5
0x1400e9e7f  jbe     short loc_1400E9EBD
0x1400e9e81  mov     edx, r15d
0x1400e9e84  lea     rcx, dword_140087708
0x1400e9e8b  call    _tlgKeywordOn
0x1400e9e90  test    al, al
0x1400e9e92  jz      short loc_1400E9EBD
0x1400e9e94  mov     [rsp+140h+Privileges], r8; char
0x1400e9e99  lea     rax, aVhdmpicreateha_9; "VhdmpiCreateHandler: enter with file ob"...
0x1400e9ea0  lea     r8d, [rdi+5]; int
0x1400e9ea4  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400e9ea9  mov     edx, 0DD9h; int
0x1400e9eae  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400e9eb5  mov     r9d, r15d; int
0x1400e9eb8  call    TraceEvents
0x1400e9ebd  lea     rdx, [rbp+40h+ActivityId]; ActivityId
0x1400e9ec1  mov     ecx, 3; ControlCode
0x1400e9ec6  call    cs:__imp_EtwActivityIdControl
0x1400e9ecd  nop     dword ptr [rax+rax+00h]
0x1400e9ed2  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400e9ed9  jz      short loc_1400E9EEE
0x1400e9edb  xor     r9d, r9d
0x1400e9ede  lea     r8, [rbp+40h+ActivityId]
0x1400e9ee2  lea     rdx, VirtualDiskHandleCreateBegin
0x1400e9ee9  call    McTemplateK0p_EtwWriteTransfer
0x1400e9eee  lea     r8, [rbp+40h+var_BC]; unsigned __int8 *
0x1400e9ef2  mov     rcx, r13; struct _IRP *
0x1400e9ef5  lea     rdx, [rbp+40h+var_78]; struct _VHDMP_CREATE_INFORMATION *
0x1400e9ef9  call    ?VhdmpiValidateCreateRequest@@YAJPEAU_IRP@@PEAU_VHDMP_CREATE_INFORMATION@@PEAE@Z; VhdmpiValidateCreateRequest(_IRP *,_VHDMP_CREATE_INFORMATION *,uchar *)
0x1400e9efe  mov     dword ptr [rbp+40h+var_C0], eax
0x1400e9f01  mov     ebx, 2
0x1400e9f06  test    eax, eax
0x1400e9f08  js      loc_1400EA374
0x1400e9f0e  cmp     [rbp+40h+var_BC], sil
0x1400e9f12  jnz     loc_1400EA374
0x1400e9f18  mov     r14, [rbp+40h+var_78]
0x1400e9f1c  xor     edx, edx
0x1400e9f1e  lea     rcx, [r14+10h]
0x1400e9f22  call    VhdmpiGetDriveType
0x1400e9f27  mov     [rbp+40h+var_B8], eax
0x1400e9f2a  test    eax, eax
0x1400e9f2c  jnz     short loc_1400E9F7A
0x1400e9f2e  mov     eax, cs:dword_140087708
0x1400e9f34  cmp     eax, ebx
0x1400e9f36  jbe     short loc_1400E9F6E
0x1400e9f38  mov     rdx, r15
0x1400e9f3b  lea     rcx, dword_140087708
0x1400e9f42  call    _tlgKeywordOn
0x1400e9f47  test    al, al
0x1400e9f49  jz      short loc_1400E9F6E
0x1400e9f4b  lea     rax, aVhdmpicreateha; "VhdmpiCreateHandler: invalid EA device "...
0x1400e9f52  mov     edx, 0DEFh; int
0x1400e9f57  mov     r9d, r15d; int
0x1400e9f5a  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400e9f5f  mov     r8d, ebx; int
0x1400e9f62  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400e9f69  call    TraceEvents
0x1400e9f6e  mov     dword ptr [rbp+40h+var_C0], 0C000000Dh
0x1400e9f75  jmp     loc_1400EA37A
0x1400e9f7a  mov     ecx, eax
0x1400e9f7c  sub     ecx, 1
0x1400e9f7f  jz      short loc_1400E9FC5
0x1400e9f81  sub     ecx, 1
0x1400e9f84  jz      short loc_1400E9FBC
0x1400e9f86  sub     ecx, 1
0x1400e9f89  jz      short loc_1400E9F95
0x1400e9f8b  cmp     ecx, 1
0x1400e9f8e  jz      short loc_1400E9FBC
0x1400e9f90  xor     r15d, r15d
0x1400e9f93  jmp     short loc_1400E9FCC
0x1400e9f95  mov     rcx, r14; struct _VIRTUAL_DISK_EA_BUFFER *
0x1400e9f98  call    ?VhdmpiValidateIsoFlags@@YAJPEAU_VIRTUAL_DISK_EA_BUFFER@@@Z; VhdmpiValidateIsoFlags(_VIRTUAL_DISK_EA_BUFFER *)
0x1400e9f9d  mov     dword ptr [rbp+40h+var_C0], eax
0x1400e9fa0  test    eax, eax
0x1400e9fa2  js      loc_1400EA374
0x1400e9fa8  mov     rcx, cs:?VhdmpiIsoSecurityDescriptor@@3PEAXEA; void * VhdmpiIsoSecurityDescriptor
0x1400e9faf  lea     r15, IsoParser
0x1400e9fb6  mov     [rbp+40h+SecurityDescriptor], rcx
0x1400e9fba  jmp     short loc_1400E9FD7
0x1400e9fbc  lea     r15, Vhd2Parser
0x1400e9fc3  jmp     short loc_1400E9FCC
0x1400e9fc5  lea     r15, Vhd1Parser
0x1400e9fcc  mov     rax, cs:?VhdmpiVhdSecurityDescriptor@@3PEAXEA; void * VhdmpiVhdSecurityDescriptor
0x1400e9fd3  mov     [rbp+40h+SecurityDescriptor], rax
0x1400e9fd7  test    byte ptr [r12+2], 1
0x1400e9fdd  mov     r12b, 1
0x1400e9fe0  jnz     short loc_1400E9FE6
0x1400e9fe2  mov     r12b, [r13+40h]
0x1400e9fe6  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400e9fed  nop     dword ptr [rax+rax+00h]
0x1400e9ff2  mov     rcx, [rbp+40h+var_80]
0x1400e9ff6  lea     r8, [rbp+40h+var_C0]
0x1400e9ffa  mov     [rsp+140h+AccessStatus], r8; AccessStatus
0x1400e9fff  lea     r8, [rbp+40h+var_98]
0x1400ea003  mov     [rsp+140h+GrantedAccess], r8; GrantedAccess
0x1400ea008  xor     r8d, r8d; SubjectContextLocked
0x1400ea00b  mov     [rsp+140h+AccessMode], r12b; AccessMode
0x1400ea010  mov     rdx, [rcx+8]
0x1400ea014  mov     r9d, [rcx+10h]; DesiredAccess
0x1400ea018  add     rdx, 20h ; ' '; SubjectSecurityContext
0x1400ea01c  mov     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x1400ea020  mov     [rsp+140h+GenericMapping], rax; GenericMapping
0x1400ea025  lea     rax, [rbp+40h+var_88]
0x1400ea029  mov     [rsp+140h+Privileges], rax; char
0x1400ea02e  mov     [rsp+140h+PreviouslyGrantedAccess], esi; PreviouslyGrantedAccess
0x1400ea032  call    cs:__imp_SeAccessCheck
0x1400ea039  nop     dword ptr [rax+rax+00h]
0x1400ea03e  mov     rcx, [rbp+40h+var_88]; Privileges
0x1400ea042  mov     r12b, al
0x1400ea045  test    rcx, rcx
0x1400ea048  jz      short loc_1400EA056
0x1400ea04a  call    cs:__imp_SeFreePrivileges
0x1400ea051  nop     dword ptr [rax+rax+00h]
0x1400ea056  test    r12b, r12b
0x1400ea059  jz      loc_1400EA32E
0x1400ea05f  cmp     dword ptr [rbp+40h+var_C0], esi
0x1400ea062  jl      loc_1400EA32E
0x1400ea068  lea     rdx, [rbp+40h+var_BB]; unsigned __int8 *
0x1400ea06c  mov     rcx, r13; struct _IRP *
0x1400ea06f  call    ?VhdmpiCheckForSharedVhd@@YAJPEAU_IRP@@PEAE@Z; VhdmpiCheckForSharedVhd(_IRP *,uchar *)
0x1400ea074  mov     dword ptr [rbp+40h+var_C0], eax
0x1400ea077  test    eax, eax
0x1400ea079  js      loc_1400EA374
0x1400ea07f  mov     rax, [rbp+40h+var_68]
0x1400ea083  test    byte ptr [rax+2], 1
0x1400ea087  jnz     short loc_1400EA090
0x1400ea089  cmp     byte ptr [r13+40h], 1
0x1400ea08e  jnz     short loc_1400EA093
0x1400ea090  mov     sil, 1
0x1400ea093  mov     r12, [rbp+40h+var_60]
0x1400ea097  movups  xmm0, xmmword ptr [r12+58h]
0x1400ea09d  movups  xmmword ptr [rbp+40h+var_A8.Length], xmm0
0x1400ea0a1  psrldq  xmm0, 8
0x1400ea0a6  movq    rax, xmm0
0x1400ea0ab  cmp     word ptr [rax], 5Ch ; '\'
0x1400ea0af  jnz     short loc_1400EA0C5
0x1400ea0b1  add     rax, rbx
0x1400ea0b4  mov     [rbp+40h+var_A8.Buffer], rax
0x1400ea0b8  mov     eax, 0FFFEh
0x1400ea0bd  add     [rbp+40h+var_A8.Length], ax
0x1400ea0c1  add     [rbp+40h+var_A8.MaximumLength], ax
0x1400ea0c5  lea     rdx, [rbp+40h+P]
0x1400ea0c9  lea     rcx, [rbp+40h+var_A8]
0x1400ea0cd  call    VhdmpiDuplicateUnicodeStringToString
0x1400ea0d2  lea     rcx, [rbp+40h+var_A8]; struct _UNICODE_STRING *
0x1400ea0d6  call    ?VhdmpiIsEmptyPathToken@@YAEPEAU_UNICODE_STRING@@@Z; VhdmpiIsEmptyPathToken(_UNICODE_STRING *)
0x1400ea0db  test    al, al
0x1400ea0dd  jz      short loc_1400EA141
0x1400ea0df  cmp     dword ptr [r14+10h], 1
0x1400ea0e4  jz      short loc_1400EA13B
0x1400ea0e6  mov     eax, cs:dword_140087708
0x1400ea0ec  cmp     eax, ebx
0x1400ea0ee  jbe     short loc_1400EA12B
0x1400ea0f0  mov     edx, 10h
0x1400ea0f5  lea     rcx, dword_140087708
0x1400ea0fc  call    _tlgKeywordOn
0x1400ea101  test    al, al
0x1400ea103  jz      short loc_1400EA12B
0x1400ea105  lea     rax, aVhdmpicreateha_10; "VhdmpiCreateHandler: File object in IRP"...
0x1400ea10c  mov     edx, 0E63h; int
0x1400ea111  mov     r9d, 10h; int
0x1400ea117  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400ea11c  mov     r8d, ebx; int
0x1400ea11f  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400ea126  call    TraceEvents
0x1400ea12b  mov     dword ptr [rbp+40h+var_C0], 0C000000Dh
0x1400ea132  mov     rsi, [rbp+40h+P]
0x1400ea136  jmp     loc_1400EA37A
0x1400ea13b  xor     eax, eax
0x1400ea13d  mov     [rbp+40h+var_A8.Length], ax
0x1400ea141  mov     edx, 1C0h
0x1400ea146  mov     ecx, 48h ; 'H'
0x1400ea14b  mov     r8d, 63444856h
0x1400ea151  call    cs:__imp_ExAllocatePool2
0x1400ea158  nop     dword ptr [rax+rax+00h]
0x1400ea15d  mov     rdi, rax
0x1400ea160  test    rax, rax
0x1400ea163  jnz     short loc_1400EA1B0
0x1400ea165  mov     ecx, cs:dword_140087708
0x1400ea16b  cmp     ecx, ebx
0x1400ea16d  jbe     short loc_1400EA1A7
0x1400ea16f  lea     edx, [rax+1]
0x1400ea172  lea     rcx, dword_140087708
0x1400ea179  call    _tlgKeywordOn
0x1400ea17e  test    al, al
0x1400ea180  jz      short loc_1400EA1A7
0x1400ea182  mov     ecx, 0E7Eh
0x1400ea187  lea     rax, aFailedToAlloca_0; "Failed to allocate handle context"
0x1400ea18e  mov     r9d, edx; int
0x1400ea191  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400ea196  mov     edx, ecx; int
0x1400ea198  mov     r8d, ebx; int
0x1400ea19b  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400ea1a2  call    TraceEvents
0x1400ea1a7  mov     dword ptr [rbp+40h+var_C0], 0C000009Ah
0x1400ea1ae  jmp     short loc_1400EA132
0x1400ea1b0  mov     rax, [rbp+40h+var_80]
0x1400ea1b4  lea     rdx, [rbp+40h+var_A8]; struct _UNICODE_STRING *
0x1400ea1b8  mov     r9b, [rbp+40h+var_BB]; unsigned __int8
0x1400ea1bc  mov     r8, r14; struct _VIRTUAL_DISK_EA_BUFFER *
0x1400ea1bf  mov     rcx, rdi; struct _VHD_HANDLE_CONTEXT *
0x1400ea1c2  mov     rax, [rax+8]
0x1400ea1c6  add     rax, 20h ; ' '
0x1400ea1ca  mov     [rsp+140h+GenericMapping], rax; struct _SECURITY_SUBJECT_CONTEXT *
0x1400ea1cf  mov     rax, [rbp+40h+var_78+8]
0x1400ea1d3  mov     [rsp+140h+Privileges], rax; void *
0x1400ea1d8  mov     byte ptr [rsp+140h+PreviouslyGrantedAccess], sil; char
0x1400ea1dd  call    ?VhdmpiInitializeHandleContext@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_UNICODE_STRING@@PEAU_VIRTUAL_DISK_EA_BUFFER@@EEPEAXPEAU_SECURITY_SUBJECT_CONTEXT@@@Z; VhdmpiInitializeHandleContext(_VHD_HANDLE_CONTEXT *,_UNICODE_STRING *,_VIRTUAL_DISK_EA_BUFFER *,uchar,uchar,void *,_SECURITY_SUBJECT_CONTEXT *)
0x1400ea1e2  mov     dword ptr [rbp+40h+var_C0], eax
0x1400ea1e5  test    eax, eax
0x1400ea1e7  js      short loc_1400EA252
0x1400ea1e9  cmp     [rbp+40h+var_B8], 4
0x1400ea1ed  jz      short loc_1400EA25B
0x1400ea1ef  lea     r8, [rbp+40h+var_A8]; struct _UNICODE_STRING *
0x1400ea1f3  mov     rdx, rdi; struct _VHD_HANDLE_CONTEXT *
0x1400ea1f6  mov     rcx, r15; struct _BACKING_STORE_PARSER *
0x1400ea1f9  call    VhdmpiCreateOrShareVirtualDisk
0x1400ea1fe  mov     dword ptr [rbp+40h+var_C0], eax
0x1400ea201  test    eax, eax
0x1400ea203  jns     short loc_1400EA26E
0x1400ea205  mov     eax, cs:dword_140087708
0x1400ea20b  cmp     eax, ebx
0x1400ea20d  jbe     short loc_1400EA252
0x1400ea20f  mov     r15d, 10h
0x1400ea215  lea     rcx, dword_140087708
0x1400ea21c  mov     edx, r15d
0x1400ea21f  call    _tlgKeywordOn
0x1400ea224  test    al, al
0x1400ea226  jz      short loc_1400EA252
0x1400ea228  mov     eax, dword ptr [rbp+40h+var_C0]
0x1400ea22b  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400ea232  mov     dword ptr [rsp+140h+Privileges], eax; char
0x1400ea236  mov     edx, 0E9Fh; int
0x1400ea23b  lea     rax, aVhdmpicreateha_5; "VhdmpiCreateHandler: unable to open bac"...
0x1400ea242  mov     r9d, r15d; int
0x1400ea245  mov     r8d, ebx; int
0x1400ea248  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400ea24d  call    TraceEvents
0x1400ea252  mov     rsi, [rbp+40h+P]
0x1400ea256  jmp     loc_1400EA374
0x1400ea25b  lea     rdx, [rbp+40h+var_A8]; struct _UNICODE_STRING *
0x1400ea25f  mov     rcx, rdi; struct _VHD_HANDLE_CONTEXT *
0x1400ea262  call    VhdmpiCreateOrShareVhdSet
0x1400ea267  mov     dword ptr [rbp+40h+var_C0], eax
0x1400ea26a  test    eax, eax
0x1400ea26c  js      short loc_1400EA252
0x1400ea26e  mov     rsi, [rbp+40h+P]
0x1400ea272  mov     [r12+20h], rdi
0x1400ea277  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400ea27e  jz      loc_1400EA322
0x1400ea284  mov     rax, [rdi+38h]
0x1400ea288  test    rax, rax
0x1400ea28b  jz      short loc_1400EA296
0x1400ea28d  mov     r15, [rax+0B00h]
0x1400ea294  jmp     short loc_1400EA299
0x1400ea296  xor     r15d, r15d
0x1400ea299  mov     edx, [r14+38h]
0x1400ea29d  mov     r8d, [r14+30h]
0x1400ea2a1  mov     r9d, [r14+2Ch]
0x1400ea2a5  mov     ecx, [r14+3Ch]
0x1400ea2a9  mov     r10d, [r14+28h]
0x1400ea2ad  mov     r11d, [r14+34h]
0x1400ea2b1  mov     rax, [rdi+188h]
0x1400ea2b8  lea     rdi, VhdmpZeroGuid
  ... truncated ...
```
