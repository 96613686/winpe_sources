# VhdmpiCreateHandler

- ea: `0x1400e9d84`
- end: `0x1400ea4f9`
- name: `VhdmpiCreateHandler`
- size: `1909`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001a410`

## callees

- `0x14001511c`
- `0x14001e0e4`
- `0x140023980`
- `0x1400277d4`
- `0x140035cac`
- `0x140036284`
- `0x14005dbb0`
- `0x14009d9a4`
- `0x14009e984`
- `0x1400c7654`
- `0x1400ca5c4`
- `0x1400caf5c`
- `0x1400cc4e8`
- `0x1400cf014`
- `0x1400e20f0`
- `0x1400e6f08`
- `0x1400e9d84`
- `0x1400ed530`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400e9f76`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400e9f76`
- `ntoskrnl!SeAccessCheck` at `0x1400e9fc2`
- `ntoskrnl!SeAccessCheck` at `0x1400e9fc2`
- `ntoskrnl!SeFreePrivileges` at `0x1400e9fda`
- `ntoskrnl!SeFreePrivileges` at `0x1400e9fda`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea47c`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea47c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea395`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea464`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea395`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ea464`
- `ntoskrnl!EtwActivityIdControl` at `0x1400e9e56`
- `ntoskrnl!EtwActivityIdControl` at `0x1400e9e56`
- `ntoskrnl!ExAllocatePool2` at `0x1400ea0e1`
- `ntoskrnl!ExAllocatePool2` at `0x1400ea0e1`

## string_xrefs

- `0x1400ea095`: `VhdmpiCreateHandler: File object in IRP indicates empty token, but is not for a DVD device.`
- `0x1400ea1cb`: `VhdmpiCreateHandler: unable to open backing store (0x%08x)`
- `0x1400ea344`: `VhdmpiCreateHandler: VHD open attempt failed (0x%08x)`
- `0x1400e9e29`: `VhdmpiCreateHandler: enter with file object %p`
- `0x1400e9e3e`: `VhdmpiCreateHandler`
- `0x1400e9ef2`: `VhdmpiCreateHandler`
- `0x1400ea0af`: `VhdmpiCreateHandler`
- `0x1400ea12b`: `VhdmpiCreateHandler`
- `0x1400ea1bb`: `VhdmpiCreateHandler`
- `0x1400ea2f8`: `VhdmpiCreateHandler`
- `0x1400ea334`: `VhdmpiCreateHandler`
- `0x1400ea4ca`: `VhdmpiCreateHandler`
- `0x1400e9edb`: `VhdmpiCreateHandler: invalid EA device or vendor id`
- `0x1400ea2e1`: `VhdmpiCreateHandler: Access not granted.`

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
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents((int)"VhdmpiCreateHandler", 3545, 5, 16, "VhdmpiCreateHandler: enter with file object %p", v7);
  EtwActivityIdControl(3u, &ActivityId);
  if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(v8, VirtualDiskHandleCreateBegin, &ActivityId, 0);
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
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
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
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
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 1) )
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
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
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
    && (unsigned int)dword_1400876D0 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
  {
    TraceEvents((int)"VhdmpiCreateHandler", 3851, 2, v39, "Return with status 0x%08X", v38);
  }
  return v38;
}

```

## disassembly

```asm
0x1400e9d84  push    rbp
0x1400e9d86  push    rbx
0x1400e9d87  push    rsi
0x1400e9d88  push    rdi
0x1400e9d89  push    r12
0x1400e9d8b  push    r13
0x1400e9d8d  push    r14
0x1400e9d8f  push    r15
0x1400e9d91  lea     rbp, [rsp-8]
0x1400e9d96  sub     rsp, 108h
0x1400e9d9d  mov     rax, cs:__security_cookie
0x1400e9da4  xor     rax, rsp
0x1400e9da7  mov     [rbp+40h+var_48], rax
0x1400e9dab  mov     r12, [rcx+0B8h]
0x1400e9db2  xor     edi, edi
0x1400e9db4  xorps   xmm0, xmm0
0x1400e9db7  mov     [rbp+40h+var_98], 0
0x1400e9dbe  movups  xmmword ptr [rbp+40h+var_A8.Length], xmm0
0x1400e9dc2  mov     [rbp+40h+var_88], rdi
0x1400e9dc6  xor     esi, esi
0x1400e9dc8  mov     dword ptr [rbp+40h+var_C0], 0C0000001h
0x1400e9dcf  lea     r15d, [rdi+10h]
0x1400e9dd3  mov     rax, [r12+8]
0x1400e9dd8  xor     r14d, r14d
0x1400e9ddb  mov     r8, [r12+30h]
0x1400e9de0  mov     r13, rcx
0x1400e9de3  mov     [rbp+40h+var_80], rax
0x1400e9de7  mov     eax, cs:dword_1400876D0
0x1400e9ded  mov     [rbp+40h+var_BB], dil
0x1400e9df1  mov     [rbp+40h+var_BC], dil
0x1400e9df5  mov     [rbp+40h+var_B8], edi
0x1400e9df8  mov     [rbp+40h+var_68], r12
0x1400e9dfc  mov     [rbp+40h+var_60], r8
0x1400e9e00  mov     [rbp+40h+P], rsi
0x1400e9e04  movups  xmmword ptr [rbp+40h+var_78], xmm0
0x1400e9e08  movups  xmmword ptr [rbp+40h+ActivityId.Data1], xmm0
0x1400e9e0c  cmp     eax, 5
0x1400e9e0f  jbe     short loc_1400E9E4D
0x1400e9e11  mov     edx, r15d
0x1400e9e14  lea     rcx, dword_1400876D0
0x1400e9e1b  call    _tlgKeywordOn
0x1400e9e20  test    al, al
0x1400e9e22  jz      short loc_1400E9E4D
0x1400e9e24  mov     [rsp+140h+Privileges], r8; char
0x1400e9e29  lea     rax, aVhdmpicreateha_9; "VhdmpiCreateHandler: enter with file ob"...
0x1400e9e30  lea     r8d, [rdi+5]; int
0x1400e9e34  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400e9e39  mov     edx, 0DD9h; int
0x1400e9e3e  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400e9e45  mov     r9d, r15d; int
0x1400e9e48  call    TraceEvents
0x1400e9e4d  lea     rdx, [rbp+40h+ActivityId]; ActivityId
0x1400e9e51  mov     ecx, 3; ControlCode
0x1400e9e56  call    cs:__imp_EtwActivityIdControl
0x1400e9e5d  nop     dword ptr [rax+rax+00h]
0x1400e9e62  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400e9e69  jz      short loc_1400E9E7E
0x1400e9e6b  xor     r9d, r9d
0x1400e9e6e  lea     r8, [rbp+40h+ActivityId]
0x1400e9e72  lea     rdx, VirtualDiskHandleCreateBegin
0x1400e9e79  call    McTemplateK0p_EtwWriteTransfer
0x1400e9e7e  lea     r8, [rbp+40h+var_BC]; unsigned __int8 *
0x1400e9e82  mov     rcx, r13; struct _IRP *
0x1400e9e85  lea     rdx, [rbp+40h+var_78]; struct _VHDMP_CREATE_INFORMATION *
0x1400e9e89  call    ?VhdmpiValidateCreateRequest@@YAJPEAU_IRP@@PEAU_VHDMP_CREATE_INFORMATION@@PEAE@Z; VhdmpiValidateCreateRequest(_IRP *,_VHDMP_CREATE_INFORMATION *,uchar *)
0x1400e9e8e  mov     dword ptr [rbp+40h+var_C0], eax
0x1400e9e91  mov     ebx, 2
0x1400e9e96  test    eax, eax
0x1400e9e98  js      loc_1400EA304
0x1400e9e9e  cmp     [rbp+40h+var_BC], sil
0x1400e9ea2  jnz     loc_1400EA304
0x1400e9ea8  mov     r14, [rbp+40h+var_78]
0x1400e9eac  xor     edx, edx
0x1400e9eae  lea     rcx, [r14+10h]
0x1400e9eb2  call    VhdmpiGetDriveType
0x1400e9eb7  mov     [rbp+40h+var_B8], eax
0x1400e9eba  test    eax, eax
0x1400e9ebc  jnz     short loc_1400E9F0A
0x1400e9ebe  mov     eax, cs:dword_1400876D0
0x1400e9ec4  cmp     eax, ebx
0x1400e9ec6  jbe     short loc_1400E9EFE
0x1400e9ec8  mov     rdx, r15
0x1400e9ecb  lea     rcx, dword_1400876D0
0x1400e9ed2  call    _tlgKeywordOn
0x1400e9ed7  test    al, al
0x1400e9ed9  jz      short loc_1400E9EFE
0x1400e9edb  lea     rax, aVhdmpicreateha; "VhdmpiCreateHandler: invalid EA device "...
0x1400e9ee2  mov     edx, 0DEFh; int
0x1400e9ee7  mov     r9d, r15d; int
0x1400e9eea  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400e9eef  mov     r8d, ebx; int
0x1400e9ef2  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400e9ef9  call    TraceEvents
0x1400e9efe  mov     dword ptr [rbp+40h+var_C0], 0C000000Dh
0x1400e9f05  jmp     loc_1400EA30A
0x1400e9f0a  mov     ecx, eax
0x1400e9f0c  sub     ecx, 1
0x1400e9f0f  jz      short loc_1400E9F55
0x1400e9f11  sub     ecx, 1
0x1400e9f14  jz      short loc_1400E9F4C
0x1400e9f16  sub     ecx, 1
0x1400e9f19  jz      short loc_1400E9F25
0x1400e9f1b  cmp     ecx, 1
0x1400e9f1e  jz      short loc_1400E9F4C
0x1400e9f20  xor     r15d, r15d
0x1400e9f23  jmp     short loc_1400E9F5C
0x1400e9f25  mov     rcx, r14; struct _VIRTUAL_DISK_EA_BUFFER *
0x1400e9f28  call    ?VhdmpiValidateIsoFlags@@YAJPEAU_VIRTUAL_DISK_EA_BUFFER@@@Z; VhdmpiValidateIsoFlags(_VIRTUAL_DISK_EA_BUFFER *)
0x1400e9f2d  mov     dword ptr [rbp+40h+var_C0], eax
0x1400e9f30  test    eax, eax
0x1400e9f32  js      loc_1400EA304
0x1400e9f38  mov     rcx, cs:?VhdmpiIsoSecurityDescriptor@@3PEAXEA; void * VhdmpiIsoSecurityDescriptor
0x1400e9f3f  lea     r15, IsoParser
0x1400e9f46  mov     [rbp+40h+SecurityDescriptor], rcx
0x1400e9f4a  jmp     short loc_1400E9F67
0x1400e9f4c  lea     r15, Vhd2Parser
0x1400e9f53  jmp     short loc_1400E9F5C
0x1400e9f55  lea     r15, Vhd1Parser
0x1400e9f5c  mov     rax, cs:?VhdmpiVhdSecurityDescriptor@@3PEAXEA; void * VhdmpiVhdSecurityDescriptor
0x1400e9f63  mov     [rbp+40h+SecurityDescriptor], rax
0x1400e9f67  test    byte ptr [r12+2], 1
0x1400e9f6d  mov     r12b, 1
0x1400e9f70  jnz     short loc_1400E9F76
0x1400e9f72  mov     r12b, [r13+40h]
0x1400e9f76  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400e9f7d  nop     dword ptr [rax+rax+00h]
0x1400e9f82  mov     rcx, [rbp+40h+var_80]
0x1400e9f86  lea     r8, [rbp+40h+var_C0]
0x1400e9f8a  mov     [rsp+140h+AccessStatus], r8; AccessStatus
0x1400e9f8f  lea     r8, [rbp+40h+var_98]
0x1400e9f93  mov     [rsp+140h+GrantedAccess], r8; GrantedAccess
0x1400e9f98  xor     r8d, r8d; SubjectContextLocked
0x1400e9f9b  mov     [rsp+140h+AccessMode], r12b; AccessMode
0x1400e9fa0  mov     rdx, [rcx+8]
0x1400e9fa4  mov     r9d, [rcx+10h]; DesiredAccess
0x1400e9fa8  add     rdx, 20h ; ' '; SubjectSecurityContext
0x1400e9fac  mov     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x1400e9fb0  mov     [rsp+140h+GenericMapping], rax; GenericMapping
0x1400e9fb5  lea     rax, [rbp+40h+var_88]
0x1400e9fb9  mov     [rsp+140h+Privileges], rax; char
0x1400e9fbe  mov     [rsp+140h+PreviouslyGrantedAccess], esi; PreviouslyGrantedAccess
0x1400e9fc2  call    cs:__imp_SeAccessCheck
0x1400e9fc9  nop     dword ptr [rax+rax+00h]
0x1400e9fce  mov     rcx, [rbp+40h+var_88]; Privileges
0x1400e9fd2  mov     r12b, al
0x1400e9fd5  test    rcx, rcx
0x1400e9fd8  jz      short loc_1400E9FE6
0x1400e9fda  call    cs:__imp_SeFreePrivileges
0x1400e9fe1  nop     dword ptr [rax+rax+00h]
0x1400e9fe6  test    r12b, r12b
0x1400e9fe9  jz      loc_1400EA2BE
0x1400e9fef  cmp     dword ptr [rbp+40h+var_C0], esi
0x1400e9ff2  jl      loc_1400EA2BE
0x1400e9ff8  lea     rdx, [rbp+40h+var_BB]; unsigned __int8 *
0x1400e9ffc  mov     rcx, r13; struct _IRP *
0x1400e9fff  call    ?VhdmpiCheckForSharedVhd@@YAJPEAU_IRP@@PEAE@Z; VhdmpiCheckForSharedVhd(_IRP *,uchar *)
0x1400ea004  mov     dword ptr [rbp+40h+var_C0], eax
0x1400ea007  test    eax, eax
0x1400ea009  js      loc_1400EA304
0x1400ea00f  mov     rax, [rbp+40h+var_68]
0x1400ea013  test    byte ptr [rax+2], 1
0x1400ea017  jnz     short loc_1400EA020
0x1400ea019  cmp     byte ptr [r13+40h], 1
0x1400ea01e  jnz     short loc_1400EA023
0x1400ea020  mov     sil, 1
0x1400ea023  mov     r12, [rbp+40h+var_60]
0x1400ea027  movups  xmm0, xmmword ptr [r12+58h]
0x1400ea02d  movups  xmmword ptr [rbp+40h+var_A8.Length], xmm0
0x1400ea031  psrldq  xmm0, 8
0x1400ea036  movq    rax, xmm0
0x1400ea03b  cmp     word ptr [rax], 5Ch ; '\'
0x1400ea03f  jnz     short loc_1400EA055
0x1400ea041  add     rax, rbx
0x1400ea044  mov     [rbp+40h+var_A8.Buffer], rax
0x1400ea048  mov     eax, 0FFFEh
0x1400ea04d  add     [rbp+40h+var_A8.Length], ax
0x1400ea051  add     [rbp+40h+var_A8.MaximumLength], ax
0x1400ea055  lea     rdx, [rbp+40h+P]
0x1400ea059  lea     rcx, [rbp+40h+var_A8]
0x1400ea05d  call    VhdmpiDuplicateUnicodeStringToString
0x1400ea062  lea     rcx, [rbp+40h+var_A8]; struct _UNICODE_STRING *
0x1400ea066  call    ?VhdmpiIsEmptyPathToken@@YAEPEAU_UNICODE_STRING@@@Z; VhdmpiIsEmptyPathToken(_UNICODE_STRING *)
0x1400ea06b  test    al, al
0x1400ea06d  jz      short loc_1400EA0D1
0x1400ea06f  cmp     dword ptr [r14+10h], 1
0x1400ea074  jz      short loc_1400EA0CB
0x1400ea076  mov     eax, cs:dword_1400876D0
0x1400ea07c  cmp     eax, ebx
0x1400ea07e  jbe     short loc_1400EA0BB
0x1400ea080  mov     edx, 10h
0x1400ea085  lea     rcx, dword_1400876D0
0x1400ea08c  call    _tlgKeywordOn
0x1400ea091  test    al, al
0x1400ea093  jz      short loc_1400EA0BB
0x1400ea095  lea     rax, aVhdmpicreateha_10; "VhdmpiCreateHandler: File object in IRP"...
0x1400ea09c  mov     edx, 0E63h; int
0x1400ea0a1  mov     r9d, 10h; int
0x1400ea0a7  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400ea0ac  mov     r8d, ebx; int
0x1400ea0af  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400ea0b6  call    TraceEvents
0x1400ea0bb  mov     dword ptr [rbp+40h+var_C0], 0C000000Dh
0x1400ea0c2  mov     rsi, [rbp+40h+P]
0x1400ea0c6  jmp     loc_1400EA30A
0x1400ea0cb  xor     eax, eax
0x1400ea0cd  mov     [rbp+40h+var_A8.Length], ax
0x1400ea0d1  mov     edx, 1C0h
0x1400ea0d6  mov     ecx, 48h ; 'H'
0x1400ea0db  mov     r8d, 63444856h
0x1400ea0e1  call    cs:__imp_ExAllocatePool2
0x1400ea0e8  nop     dword ptr [rax+rax+00h]
0x1400ea0ed  mov     rdi, rax
0x1400ea0f0  test    rax, rax
0x1400ea0f3  jnz     short loc_1400EA140
0x1400ea0f5  mov     ecx, cs:dword_1400876D0
0x1400ea0fb  cmp     ecx, ebx
0x1400ea0fd  jbe     short loc_1400EA137
0x1400ea0ff  lea     edx, [rax+1]
0x1400ea102  lea     rcx, dword_1400876D0
0x1400ea109  call    _tlgKeywordOn
0x1400ea10e  test    al, al
0x1400ea110  jz      short loc_1400EA137
0x1400ea112  mov     ecx, 0E7Eh
0x1400ea117  lea     rax, aFailedToAlloca_0; "Failed to allocate handle context"
0x1400ea11e  mov     r9d, edx; int
0x1400ea121  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400ea126  mov     edx, ecx; int
0x1400ea128  mov     r8d, ebx; int
0x1400ea12b  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400ea132  call    TraceEvents
0x1400ea137  mov     dword ptr [rbp+40h+var_C0], 0C000009Ah
0x1400ea13e  jmp     short loc_1400EA0C2
0x1400ea140  mov     rax, [rbp+40h+var_80]
0x1400ea144  lea     rdx, [rbp+40h+var_A8]; struct _UNICODE_STRING *
0x1400ea148  mov     r9b, [rbp+40h+var_BB]; unsigned __int8
0x1400ea14c  mov     r8, r14; struct _VIRTUAL_DISK_EA_BUFFER *
0x1400ea14f  mov     rcx, rdi; struct _VHD_HANDLE_CONTEXT *
0x1400ea152  mov     rax, [rax+8]
0x1400ea156  add     rax, 20h ; ' '
0x1400ea15a  mov     [rsp+140h+GenericMapping], rax; struct _SECURITY_SUBJECT_CONTEXT *
0x1400ea15f  mov     rax, [rbp+40h+var_78+8]
0x1400ea163  mov     [rsp+140h+Privileges], rax; void *
0x1400ea168  mov     byte ptr [rsp+140h+PreviouslyGrantedAccess], sil; char
0x1400ea16d  call    ?VhdmpiInitializeHandleContext@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_UNICODE_STRING@@PEAU_VIRTUAL_DISK_EA_BUFFER@@EEPEAXPEAU_SECURITY_SUBJECT_CONTEXT@@@Z; VhdmpiInitializeHandleContext(_VHD_HANDLE_CONTEXT *,_UNICODE_STRING *,_VIRTUAL_DISK_EA_BUFFER *,uchar,uchar,void *,_SECURITY_SUBJECT_CONTEXT *)
0x1400ea172  mov     dword ptr [rbp+40h+var_C0], eax
0x1400ea175  test    eax, eax
0x1400ea177  js      short loc_1400EA1E2
0x1400ea179  cmp     [rbp+40h+var_B8], 4
0x1400ea17d  jz      short loc_1400EA1EB
0x1400ea17f  lea     r8, [rbp+40h+var_A8]; struct _UNICODE_STRING *
0x1400ea183  mov     rdx, rdi; struct _VHD_HANDLE_CONTEXT *
0x1400ea186  mov     rcx, r15; struct _BACKING_STORE_PARSER *
0x1400ea189  call    VhdmpiCreateOrShareVirtualDisk
0x1400ea18e  mov     dword ptr [rbp+40h+var_C0], eax
0x1400ea191  test    eax, eax
0x1400ea193  jns     short loc_1400EA1FE
0x1400ea195  mov     eax, cs:dword_1400876D0
0x1400ea19b  cmp     eax, ebx
0x1400ea19d  jbe     short loc_1400EA1E2
0x1400ea19f  mov     r15d, 10h
0x1400ea1a5  lea     rcx, dword_1400876D0
0x1400ea1ac  mov     edx, r15d
0x1400ea1af  call    _tlgKeywordOn
0x1400ea1b4  test    al, al
0x1400ea1b6  jz      short loc_1400EA1E2
0x1400ea1b8  mov     eax, dword ptr [rbp+40h+var_C0]
0x1400ea1bb  lea     rcx, aVhdmpicreateha_1; "VhdmpiCreateHandler"
0x1400ea1c2  mov     dword ptr [rsp+140h+Privileges], eax; char
0x1400ea1c6  mov     edx, 0E9Fh; int
0x1400ea1cb  lea     rax, aVhdmpicreateha_5; "VhdmpiCreateHandler: unable to open bac"...
0x1400ea1d2  mov     r9d, r15d; int
0x1400ea1d5  mov     r8d, ebx; int
0x1400ea1d8  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax; char *
0x1400ea1dd  call    TraceEvents
0x1400ea1e2  mov     rsi, [rbp+40h+P]
0x1400ea1e6  jmp     loc_1400EA304
0x1400ea1eb  lea     rdx, [rbp+40h+var_A8]; struct _UNICODE_STRING *
0x1400ea1ef  mov     rcx, rdi; struct _VHD_HANDLE_CONTEXT *
0x1400ea1f2  call    VhdmpiCreateOrShareVhdSet
0x1400ea1f7  mov     dword ptr [rbp+40h+var_C0], eax
0x1400ea1fa  test    eax, eax
0x1400ea1fc  js      short loc_1400EA1E2
0x1400ea1fe  mov     rsi, [rbp+40h+P]
0x1400ea202  mov     [r12+20h], rdi
0x1400ea207  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400ea20e  jz      loc_1400EA2B2
0x1400ea214  mov     rax, [rdi+38h]
0x1400ea218  test    rax, rax
0x1400ea21b  jz      short loc_1400EA226
0x1400ea21d  mov     r15, [rax+0B00h]
0x1400ea224  jmp     short loc_1400EA229
0x1400ea226  xor     r15d, r15d
0x1400ea229  mov     edx, [r14+38h]
0x1400ea22d  mov     r8d, [r14+30h]
0x1400ea231  mov     r9d, [r14+2Ch]
0x1400ea235  mov     ecx, [r14+3Ch]
0x1400ea239  mov     r10d, [r14+28h]
0x1400ea23d  mov     r11d, [r14+34h]
0x1400ea241  mov     rax, [rdi+188h]
0x1400ea248  lea     rdi, VhdmpZeroGuid
  ... truncated ...
```
