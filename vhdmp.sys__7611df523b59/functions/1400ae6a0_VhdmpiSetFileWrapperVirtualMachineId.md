# VhdmpiSetFileWrapperVirtualMachineId

- ea: `0x1400ae6a0`
- end: `0x1400af0c1`
- name: `VhdmpiSetFileWrapperVirtualMachineId`
- size: `2593`
- prototype: `__int64 __fastcall(struct _VHD_FILE_WRAPPER *)`
- caller_count: `4`
- callee_count: `19`
- tags: `file_ops, installer_update`

## callers

- `0x14004d308`
- `0x14004e940`
- `0x1400cff8c`
- `0x1400e565c`

## callees

- `0x140019070`
- `0x14001b7fc`
- `0x14001bc68`
- `0x1400201d0`
- `0x140023560`
- `0x14002dc84`
- `0x14002debc`
- `0x14002e0cc`
- `0x14002e138`
- `0x14002e210`
- `0x14002e250`
- `0x140035e94`
- `0x1400aafe8`
- `0x1400ac4f8`
- `0x1400ae6a0`
- `0x1400ca2b8`
- `0x1400d0ff4`
- `0x1400e6e6c`
- `0x1400e8fd8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400aef8d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400aefc4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400aefec`
- `ntoskrnl!ObfDereferenceObject` at `0x1400aef8d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400aefc4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400aefec`
- `ntoskrnl!ZwClose` at `0x1400aefa5`
- `ntoskrnl!ZwClose` at `0x1400aefd8`
- `ntoskrnl!ZwClose` at `0x1400af001`
- `ntoskrnl!ZwClose` at `0x1400aefa5`
- `ntoskrnl!ZwClose` at `0x1400aefd8`
- `ntoskrnl!ZwClose` at `0x1400af001`

## string_xrefs

- `0x1400ae7e1`: `VhdmpiSetFileWrapperVirtualMachineId`
- `0x1400aea64`: `VhdmpiSetFileWrapperVirtualMachineId`
- `0x1400aeb53`: `VhdmpiSetFileWrapperVirtualMachineId`
- `0x1400aec32`: `VhdmpiSetFileWrapperVirtualMachineId`
- `0x1400af080`: `VhdmpiSetFileWrapperVirtualMachineId`
- `0x1400af061`: ` (file '%wZ')Update result: 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiSetFileWrapperVirtualMachineId(struct _VHD_FILE_WRAPPER *a1, _OWORD *a2, __int64 a3, int a4)
{
  char v4; // r12
  int v5; // edi
  _OWORD *v6; // rsi
  struct _VHD_FILE_WRAPPER *v7; // r13
  struct _FILE_OBJECT *v8; // r15
  unsigned __int64 v9; // rax
  struct _FILE_OBJECT *v10; // r14
  int VolumeStableGuid; // edi
  __int128 v12; // xmm6
  unsigned int v13; // r14d
  unsigned int v14; // r15d
  int v15; // r12d
  int v16; // r13d
  char *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rcx
  struct _VHD_FILE_WRAPPER *v23; // rcx
  __int64 v24; // r9
  struct _FILE_OBJECT *v25; // rsi
  unsigned int v26; // edx
  unsigned __int16 v27; // cx
  char *v28; // rax
  unsigned __int8 v29; // di
  unsigned int v30; // edx
  __int64 v31; // r8
  int v32; // r14d
  int v33; // r15d
  int v34; // r12d
  int v35; // r13d
  unsigned int v36; // edx
  __int64 v37; // r9
  struct _VHD_FILE_WRAPPER *v38; // rcx
  int v39; // eax
  __int64 v40; // r8
  void *v41; // r14
  int v42; // edx
  unsigned int v43; // r8d
  struct _FILE_OBJECT **v45; // [rsp+30h] [rbp-130h]
  unsigned __int8 *v46; // [rsp+38h] [rbp-128h]
  __int64 v47; // [rsp+40h] [rbp-120h]
  __int64 v48; // [rsp+48h] [rbp-118h]
  __int64 v49; // [rsp+50h] [rbp-110h]
  __int64 v50; // [rsp+58h] [rbp-108h]
  __int64 v51; // [rsp+60h] [rbp-100h]
  __int64 v52; // [rsp+68h] [rbp-F8h]
  int v53; // [rsp+68h] [rbp-F8h]
  __int64 v54; // [rsp+70h] [rbp-F0h]
  __int64 v55; // [rsp+78h] [rbp-E8h]
  __int64 v56; // [rsp+80h] [rbp-E0h]
  __int64 v57; // [rsp+88h] [rbp-D8h]
  int v58; // [rsp+88h] [rbp-D8h]
  __int64 v59; // [rsp+90h] [rbp-D0h]
  int v60; // [rsp+90h] [rbp-D0h]
  __int64 v61; // [rsp+98h] [rbp-C8h]
  int v62; // [rsp+98h] [rbp-C8h]
  __int64 v63; // [rsp+A0h] [rbp-C0h]
  int v64; // [rsp+A0h] [rbp-C0h]
  __int64 v65; // [rsp+A8h] [rbp-B8h]
  int v66; // [rsp+A8h] [rbp-B8h]
  __int64 v67; // [rsp+B0h] [rbp-B0h]
  int v68; // [rsp+B0h] [rbp-B0h]
  __int64 v69; // [rsp+B8h] [rbp-A8h]
  int v70; // [rsp+B8h] [rbp-A8h]
  __int64 v71; // [rsp+C0h] [rbp-A0h]
  int v72; // [rsp+C0h] [rbp-A0h]
  __int64 v73; // [rsp+C8h] [rbp-98h]
  int v74; // [rsp+C8h] [rbp-98h]
  __int64 v75; // [rsp+D0h] [rbp-90h]
  int v76; // [rsp+D0h] [rbp-90h]
  __int64 v77; // [rsp+D8h] [rbp-88h]
  int v78; // [rsp+D8h] [rbp-88h]
  __int64 v79; // [rsp+E0h] [rbp-80h] BYREF
  __int64 v80; // [rsp+E8h] [rbp-78h]
  __int64 v81; // [rsp+F0h] [rbp-70h]
  __int64 v82; // [rsp+F8h] [rbp-68h]
  __int128 v83; // [rsp+100h] [rbp-60h] BYREF
  HANDLE Handle; // [rsp+110h] [rbp-50h]
  HANDLE v85; // [rsp+118h] [rbp-48h]
  HANDLE v86; // [rsp+120h] [rbp-40h] BYREF
  PVOID Object[2]; // [rsp+128h] [rbp-38h] BYREF
  int v88; // [rsp+138h] [rbp-28h]
  struct _FILE_OBJECT *v89; // [rsp+140h] [rbp-20h]
  void *v90; // [rsp+148h] [rbp-18h] BYREF
  struct _FILE_OBJECT *v91; // [rsp+150h] [rbp-10h] BYREF
  void *v92; // [rsp+158h] [rbp-8h] BYREF
  struct _FILE_OBJECT *v93; // [rsp+160h] [rbp+0h] BYREF
  __int64 v94; // [rsp+168h] [rbp+8h] BYREF
  struct _FILE_OBJECT *v95; // [rsp+170h] [rbp+10h]
  struct _FILE_OBJECT *v96; // [rsp+178h] [rbp+18h]
  __int128 v97; // [rsp+180h] [rbp+20h] BYREF
  unsigned __int8 v100; // [rsp+200h] [rbp+A0h]

  v100 = a3;
  v4 = 0;
  v94 = 0;
  v89 = 0;
  Object[0] = 0;
  v85 = 0;
  v5 = a4;
  v90 = 0;
  v6 = a2;
  Handle = 0;
  v7 = a1;
  v92 = 0;
  v8 = 0;
  v9 = *(_QWORD *)((char *)a1 + 548);
  v10 = 0;
  v83 = 0;
  LOWORD(v79) = 0;
  v97 = 0;
  v86 = 0;
  v96 = 0;
  v91 = 0;
  BYTE2(v79) = 0;
  v95 = 0;
  v93 = 0;
  if ( __PAIR128__(*(_QWORD *)((char *)a1 + 556), v9) == *a2 )
    return 0;
  v12 = *(_OWORD *)((char *)a1 + 548);
  v88 = *((_DWORD *)a1 + 35);
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
  {
    v13 = *((unsigned __int8 *)v7 + 563);
    v14 = *((unsigned __int8 *)v7 + 562);
    v15 = *((unsigned __int8 *)v7 + 561);
    v16 = *((unsigned __int8 *)v7 + 560);
    v78 = *((unsigned __int8 *)v6 + 15);
    v76 = *((unsigned __int8 *)v6 + 14);
    v74 = *((unsigned __int8 *)v6 + 13);
    v72 = *((unsigned __int8 *)v6 + 12);
    v70 = *((unsigned __int8 *)v6 + 11);
    v68 = *((unsigned __int8 *)v6 + 10);
    v66 = *((unsigned __int8 *)v6 + 9);
    v64 = *((unsigned __int8 *)v6 + 8);
    v62 = *((unsigned __int16 *)v6 + 3);
    v60 = *((unsigned __int16 *)v6 + 2);
    v6 = a2;
    Object[1] = (PVOID)__PAIR64__(v14, v13);
    v58 = *(_DWORD *)a2;
    HIDWORD(v79) = *((unsigned __int8 *)a1 + 559);
    LODWORD(v80) = *((unsigned __int8 *)a1 + 558);
    HIDWORD(v80) = *((unsigned __int8 *)a1 + 557);
    LODWORD(v81) = *((unsigned __int8 *)a1 + 556);
    HIDWORD(v81) = *((unsigned __int16 *)a1 + 277);
    LODWORD(v82) = *((unsigned __int16 *)a1 + 276);
    v53 = v16;
    v7 = a1;
    TraceEvents(
      "VhdmpiSetFileWrapperVirtualMachineId",
      0x1BE3u,
      4u,
      0x800u,
      " (file '%wZ')Updating VM ID from {%08X-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x} to {%08X-%04x-%04x-%02x%02x-%0"
      "2x%02x%02x%02x%02x%02x}",
      a1,
      *((_DWORD *)a1 + 137),
      v82,
      HIDWORD(v81),
      v81,
      HIDWORD(v80),
      v80,
      HIDWORD(v79),
      v53,
      v15,
      v14,
      v13,
      v58,
      v60,
      v62,
      v64,
      v66,
      v68,
      v70,
      v72,
      v74,
      v76,
      v78,
      v79,
      v80,
      v81,
      v82);
    v10 = v95;
    v4 = 0;
    v8 = v96;
    v5 = a4;
  }
  v17 = (char *)v7 + 568;
  if ( !*((_DWORD *)v7 + 150) )
    goto LABEL_7;
  VhdmpiAcquirePassiveLock((char *)v7 + 568, a2, a3);
  *(_OWORD *)((char *)v7 + 548) = *v6;
  if ( !(unsigned __int8)VhdmpiIsRemoteSmbFile(v7) && !(unsigned __int8)VhdmpiCsvResiliencyRequired(v19, v18, v20, v21) )
  {
    VolumeStableGuid = 0;
LABEL_78:
    VhdmpiReleasePassiveLock(v17);
    goto LABEL_79;
  }
  v4 = 1;
  if ( (unsigned int)(*((_DWORD *)v7 + 150) - 1) > 1 )
  {
LABEL_7:
    VolumeStableGuid = -1073741823;
    goto LABEL_77;
  }
  if ( (unsigned __int8)VhdmpiIsRemoteSmbFile(v7) )
    VhdmpiChangeCacheMode(v22, v5, 0);
  if ( !(unsigned __int8)VhdmpiIsRemoteSmbFile(v7) )
  {
    v25 = v89;
    goto LABEL_42;
  }
  LOBYTE(v24) = v100;
  VolumeStableGuid = VhdmpiOpenBackingFile(
                       v23,
                       0x80000000,
                       3,
                       v24,
                       1,
                       &v86,
                       (struct _FILE_OBJECT **)Object,
                       (unsigned __int8 *)&v79);
  if ( VolumeStableGuid < 0 )
  {
    v25 = (struct _FILE_OBJECT *)Object[0];
    goto LABEL_72;
  }
  if ( !*((_BYTE *)v7 + 489) || *((_BYTE *)v7 + 488) )
  {
    v25 = (struct _FILE_OBJECT *)Object[0];
    if ( *((_QWORD *)Object[0] + 3) != *((_QWORD *)v7 + 62) )
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
        TraceEvents(
          "VhdmpiSetFileWrapperVirtualMachineId",
          0x1C6Cu,
          2u,
          v36,
          " (file '%wZ')FsContext changed between original lock file and lock file with new GUID: %p vs %p",
          v7,
          *((_QWORD *)v7 + 62),
          v25->FsContext);
      goto LABEL_35;
    }
    goto LABEL_42;
  }
  v25 = (struct _FILE_OBJECT *)Object[0];
  v89 = (struct _FILE_OBJECT *)Object[0];
  VolumeStableGuid = VhdmpiGetVolumeStableGuid(Object[0], &v83);
  if ( VolumeStableGuid < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
    {
      v27 = 7232;
      v28 = " (file '%wZ')Failed to query Volume Stable Guid: 0x%08x";
LABEL_22:
      LODWORD(v45) = VolumeStableGuid;
      TraceEvents("VhdmpiSetFileWrapperVirtualMachineId", v27, 2u, v26, v28, v7, v45);
      goto LABEL_72;
    }
    goto LABEL_72;
  }
  v29 = BYTE8(v83);
  if ( v83 != *(_OWORD *)((char *)v7 + 504) )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
    {
      v32 = *((unsigned __int8 *)v7 + 519);
      v33 = *((unsigned __int8 *)v7 + 518);
      v34 = *((unsigned __int8 *)v7 + 517);
      v35 = *((unsigned __int8 *)v7 + 516);
      LODWORD(v82) = *((unsigned __int8 *)a1 + 515);
      HIDWORD(v81) = *((unsigned __int8 *)a1 + 514);
      LODWORD(v81) = *((unsigned __int8 *)a1 + 513);
      HIDWORD(v80) = *((unsigned __int8 *)a1 + 512);
      LODWORD(v80) = *((unsigned __int16 *)a1 + 255);
      HIDWORD(v79) = *((unsigned __int16 *)a1 + 254);
      LODWORD(v77) = HIBYTE(v83);
      LODWORD(v75) = BYTE14(v83);
      LODWORD(v73) = BYTE13(v83);
      LODWORD(v71) = BYTE12(v83);
      LODWORD(v69) = BYTE11(v83);
      LODWORD(v67) = BYTE10(v83);
      LODWORD(v65) = BYTE9(v83);
      LODWORD(v63) = v29;
      LODWORD(v61) = WORD3(v83);
      LODWORD(v59) = WORD2(v83);
      LODWORD(v57) = v83;
      LODWORD(v56) = v32;
      LODWORD(v55) = v33;
      LODWORD(v54) = v34;
      LODWORD(v52) = v35;
      v7 = a1;
      LODWORD(v51) = v82;
      LODWORD(v50) = HIDWORD(v81);
      LODWORD(v49) = v81;
      LODWORD(v48) = HIDWORD(v80);
      LODWORD(v47) = v80;
      LODWORD(v46) = HIDWORD(v79);
      LODWORD(v45) = *((_DWORD *)a1 + 126);
      TraceEvents(
        "VhdmpiSetFileWrapperVirtualMachineId",
        0x1C4Au,
        2u,
        0x800u,
        " (file '%wZ')VolumeId changed between original lock file and lock file with new GUID: {%08X-%04x-%04x-%02x%02x-%"
        "02x%02x%02x%02x%02x%02x} vs {%08X-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
        a1,
        v45,
        v46,
        v47,
        v48,
        v49,
        v50,
        v51,
        v52,
        v54,
        v55,
        v56,
        v57,
        v59,
        v61,
        v63,
        v65,
        v67,
        v69,
        v71,
        v73,
        v75,
        v77);
      v25 = v89;
      v17 = (char *)a1 + 568;
      v4 = 1;
    }
    goto LABEL_35;
  }
  VolumeStableGuid = VhdmpiGetFileId(v86, &v94);
  if ( VolumeStableGuid >= 0 )
  {
    if ( v94 != *((_QWORD *)v7 + 62) )
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
        TraceEvents(
          "VhdmpiSetFileWrapperVirtualMachineId",
          0x1C5Fu,
          2u,
          v30,
          " (file '%wZ')FileId changed between original lock file and lock file with new GUID: %lld vs %lld",
          v7,
          *((_QWORD *)v7 + 62),
          v31);
LABEL_35:
      VolumeStableGuid = -1073741436;
      goto LABEL_72;
    }
LABEL_42:
    if ( *((_DWORD *)v7 + 150) == 2 && (unsigned __int8)VhdmpiIsRemoteSmbFile(v7) )
    {
      VolumeStableGuid = VhdmpiBeginImpersonation(*((PACCESS_TOKEN *)v7 + 42), (__int64)&v97);
      if ( VolumeStableGuid < 0 )
        goto LABEL_72;
      LOBYTE(v37) = v100;
      VolumeStableGuid = VhdmpiOpenBackingFile(v7, 0x80000000, 1, v37, 1, &v90, &v91, (unsigned __int8 *)&v79 + 1);
      VhdmpiEndImpersonation((__int64)&v97);
      v8 = v91;
      if ( VolumeStableGuid < 0 )
      {
        v41 = v90;
LABEL_68:
        if ( v8 )
          ObfDereferenceObject(v8);
        if ( v41 )
          ZwClose(v41);
        goto LABEL_72;
      }
      v85 = v90;
    }
    if ( *((_QWORD *)v7 + 49) && (unsigned __int8)VhdmpiIsRemoteSmbFile(v7) )
    {
      v39 = VhdmpiOpenBackingFile(v38, 0x80000000, 1, 0, 1, &v92, &v93, (unsigned __int8 *)&v79 + 2);
      v10 = v93;
      VolumeStableGuid = v39;
      if ( v39 < 0 )
      {
        Handle = v92;
        goto LABEL_63;
      }
      Handle = v92;
    }
    VolumeStableGuid = 0;
    if ( v25 )
    {
      VhdmpiSuspendSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 176));
      VhdmpiCloseSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 176));
      LOBYTE(v40) = v100;
      VhdmpiSaveAccessContext((__int64)v7, 0, v40);
      VhdmpiSetSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 176), v86, v25);
      v86 = 0;
      v25 = 0;
      VhdmpiResumeSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 176));
    }
    if ( *((_DWORD *)v7 + 150) == 2 && v8 )
    {
      if ( *((_DWORD *)v7 + 162) == 1 )
        *((_DWORD *)v7 + 163) = VhdmpiSetQoSLogicalFlowId(v7, v8, (char *)v7 + 656);
      VhdmpiSuspendSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 280));
      VhdmpiCloseSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 280));
      VhdmpiSetSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 280), v85, v8);
      v85 = 0;
      v8 = 0;
      VhdmpiResumeSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 280));
    }
    if ( *((_QWORD *)v7 + 49) )
    {
      if ( !v10 )
      {
LABEL_65:
        if ( Handle )
          ZwClose(Handle);
        v41 = v85;
        v17 = (char *)v7 + 568;
        goto LABEL_68;
      }
      if ( *((_DWORD *)v7 + 162) == 1 )
        *((_DWORD *)v7 + 163) = VhdmpiSetQoSLogicalFlowId(v7, v10, (char *)v7 + 656);
      VhdmpiSuspendSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 384));
      VhdmpiCloseSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 384));
      VhdmpiSaveAccessContext((__int64)v7, 2, 0);
      VhdmpiSetSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 384), Handle, v10);
      Handle = 0;
      v10 = 0;
      VhdmpiResumeSafeFileReference((struct _VHD_FILE_WRAPPER *)((char *)v7 + 384));
    }
LABEL_63:
    if ( v10 )
      ObfDereferenceObject(v10);
    goto LABEL_65;
  }
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
  {
    v27 = 7253;
    v28 = " (file '%wZ')Failed to query FileId: 0x%08x";
    goto LABEL_22;
  }
LABEL_72:
  if ( v25 )
    ObfDereferenceObject(v25);
  if ( v86 )
    ZwClose(v86);
  if ( VolumeStableGuid >= 0 )
    goto LABEL_78;
LABEL_77:
  v42 = v88;
  *(_OWORD *)((char *)v7 + 548) = v12;
  VhdmpiChangeCacheMode((__int64)v7, v42, 0);
  if ( v4 )
    goto LABEL_78;
LABEL_79:
  if ( VolumeStableGuid < 0
    && (unsigned int)dword_140087708 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
  {
    LODWORD(v45) = VolumeStableGuid;
    TraceEvents("VhdmpiSetFileWrapperVirtualMachineId", 0x1D48u, 2u, v43, " (file '%wZ')Update result: 0x%08x", v7, v45);
  }
  return (unsigned int)VolumeStableGuid;
}

```

## disassembly

```asm
0x1400ae6a0  mov     rax, rsp
0x1400ae6a3  mov     [rax+20h], r9d
0x1400ae6a7  mov     [rax+18h], r8b
0x1400ae6ab  mov     [rax+10h], rdx
0x1400ae6af  mov     [rax+8], rcx
0x1400ae6b3  push    rbp
0x1400ae6b4  push    rbx
0x1400ae6b5  push    rsi
0x1400ae6b6  push    rdi
0x1400ae6b7  push    r12
0x1400ae6b9  push    r13
0x1400ae6bb  push    r14
0x1400ae6bd  push    r15
0x1400ae6bf  lea     rbp, [rsp-48h]
0x1400ae6c4  sub     rsp, 1A8h
0x1400ae6cb  xor     r12d, r12d
0x1400ae6ce  movaps  xmmword ptr [rax-58h], xmm6
0x1400ae6d2  mov     eax, r12d
0x1400ae6d5  mov     [rbp+80h+var_78], r12
0x1400ae6d9  mov     [rbp+80h+var_A0], rax
0x1400ae6dd  xorps   xmm0, xmm0
0x1400ae6e0  mov     [rbp+80h+Object], rax
0x1400ae6e4  xorps   xmm1, xmm1
0x1400ae6e7  mov     [rbp+80h+var_C8], rax
0x1400ae6eb  mov     edi, r9d
0x1400ae6ee  mov     [rbp+80h+var_98], rax
0x1400ae6f2  mov     rsi, rdx
0x1400ae6f5  mov     [rbp+80h+Handle], rax
0x1400ae6f9  mov     r13, rcx
0x1400ae6fc  mov     [rbp+80h+var_88], rax
0x1400ae700  mov     r15d, r12d
0x1400ae703  mov     rax, [rcx+224h]
0x1400ae70a  mov     r14d, r12d
0x1400ae70d  movups  [rbp+80h+var_E0], xmm0
0x1400ae711  mov     [rbp+80h+var_100], r12b
0x1400ae715  movups  [rbp+80h+var_60], xmm1
0x1400ae719  mov     [rbp+80h+var_C0], r12
0x1400ae71d  mov     [rbp+80h+var_FF], r12b
0x1400ae721  mov     [rbp+80h+var_68], r12
0x1400ae725  mov     [rbp+80h+var_90], r12
0x1400ae729  mov     [rbp+80h+var_FE], r12b
0x1400ae72d  mov     [rbp+80h+var_70], r12
0x1400ae731  mov     [rbp+80h+var_80], r12
0x1400ae735  cmp     rax, [rdx]
0x1400ae738  jnz     short loc_1400AE74F
0x1400ae73a  mov     rax, [rcx+22Ch]
0x1400ae741  cmp     rax, [rdx+8]
0x1400ae745  jnz     short loc_1400AE74F
0x1400ae747  mov     edi, r12d
0x1400ae74a  jmp     loc_1400AF08C
0x1400ae74f  mov     eax, [rcx+8Ch]
0x1400ae755  movups  xmm6, xmmword ptr [rcx+224h]
0x1400ae75c  mov     [rbp+80h+var_A8], eax
0x1400ae75f  mov     eax, cs:dword_140087708
0x1400ae765  cmp     eax, 4
0x1400ae768  jbe     loc_1400AE925
0x1400ae76e  mov     edx, 800h
0x1400ae773  lea     rcx, dword_140087708
0x1400ae77a  call    _tlgKeywordOn
0x1400ae77f  test    al, al
0x1400ae781  jz      loc_1400AE925
0x1400ae787  movzx   eax, byte ptr [rsi+0Fh]
0x1400ae78b  movzx   r14d, byte ptr [r13+233h]
0x1400ae793  movzx   r15d, byte ptr [r13+232h]
0x1400ae79b  movzx   ecx, byte ptr [rsi+0Eh]
0x1400ae79f  movzx   edx, byte ptr [rsi+0Dh]
0x1400ae7a3  movzx   r8d, byte ptr [rsi+0Ch]
0x1400ae7a8  movzx   r9d, byte ptr [rsi+0Bh]
0x1400ae7ad  movzx   r10d, byte ptr [rsi+0Ah]
0x1400ae7b2  movzx   r11d, byte ptr [rsi+9]
0x1400ae7b7  movzx   ebx, byte ptr [rsi+8]
0x1400ae7bb  movzx   edi, word ptr [rsi+6]
0x1400ae7bf  movzx   r12d, byte ptr [r13+231h]
0x1400ae7c7  movzx   esi, word ptr [rsi+4]
0x1400ae7cb  movzx   r13d, byte ptr [r13+230h]
0x1400ae7d3  mov     dword ptr [rsp+1E0h+var_108], eax
0x1400ae7da  mov     dword ptr [rsp+1E0h+var_110], ecx
0x1400ae7e1  lea     rcx, aVhdmpisetfilew; "VhdmpiSetFileWrapperVirtualMachineId"
0x1400ae7e8  mov     dword ptr [rsp+1E0h+var_118], edx
0x1400ae7ef  mov     edx, 1BE3h; int
0x1400ae7f4  mov     dword ptr [rsp+1E0h+var_120], r8d
0x1400ae7fc  mov     r8d, 4; int
0x1400ae802  mov     dword ptr [rsp+1E0h+var_128], r9d
0x1400ae80a  mov     r9d, 800h; int
0x1400ae810  mov     dword ptr [rsp+1E0h+var_130], r10d
0x1400ae818  mov     dword ptr [rsp+1E0h+var_138], r11d
0x1400ae820  mov     dword ptr [rsp+1E0h+var_140], ebx
0x1400ae827  mov     dword ptr [rsp+1E0h+var_148], edi
0x1400ae82e  mov     dword ptr [rsp+1E0h+var_150], esi
0x1400ae835  mov     rsi, [rbp+80h+arg_8]
0x1400ae83c  mov     dword ptr [rbp+80h+var_B0], r14d
0x1400ae840  mov     r14, qword ptr [rbp+80h+arg_0]
0x1400ae847  mov     dword ptr [rbp+80h+var_B0+4], r15d
0x1400ae84b  mov     r15, qword ptr [rbp+80h+arg_0]
0x1400ae852  mov     eax, [rsi]
0x1400ae854  movzx   r14d, byte ptr [r14+22Fh]
0x1400ae85c  mov     dword ptr [rsp+1E0h+var_158], eax
0x1400ae863  mov     [rbp+80h+var_FC], r14d
0x1400ae867  movzx   r14d, byte ptr [r15+22Eh]
0x1400ae86f  mov     eax, [rbp+80h+var_FC]
0x1400ae872  mov     [rbp+80h+var_F8], r14d
0x1400ae876  movzx   r14d, byte ptr [r15+22Dh]
0x1400ae87e  mov     [rbp+80h+var_F4], r14d
0x1400ae882  movzx   r14d, byte ptr [r15+22Ch]
0x1400ae88a  mov     [rbp+80h+var_F0], r14d
0x1400ae88e  movzx   r14d, word ptr [r15+22Ah]
0x1400ae896  mov     [rbp+80h+var_EC], r14d
0x1400ae89a  movzx   r14d, word ptr [r15+228h]
0x1400ae8a2  mov     r15d, dword ptr [rbp+80h+var_B0+4]
0x1400ae8a6  mov     dword ptr [rbp+80h+var_E8], r14d
0x1400ae8aa  mov     r14d, dword ptr [rbp+80h+var_B0]
0x1400ae8ae  mov     dword ptr [rsp+1E0h+var_160], r14d
0x1400ae8b6  mov     dword ptr [rsp+1E0h+var_168], r15d
0x1400ae8bb  mov     dword ptr [rsp+1E0h+var_170], r12d
0x1400ae8c0  mov     dword ptr [rsp+1E0h+var_178], r13d
0x1400ae8c5  mov     r13, qword ptr [rbp+80h+arg_0]
0x1400ae8cc  mov     dword ptr [rsp+1E0h+var_180], eax
0x1400ae8d0  mov     eax, [rbp+80h+var_F8]
0x1400ae8d3  mov     dword ptr [rsp+1E0h+var_188], eax
0x1400ae8d7  mov     eax, [rbp+80h+var_F4]
0x1400ae8da  mov     dword ptr [rsp+1E0h+var_190], eax
0x1400ae8de  mov     eax, [rbp+80h+var_F0]
0x1400ae8e1  mov     dword ptr [rsp+1E0h+var_198], eax
0x1400ae8e5  mov     eax, [rbp+80h+var_EC]
0x1400ae8e8  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x1400ae8ec  mov     eax, dword ptr [rbp+80h+var_E8]
0x1400ae8ef  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x1400ae8f3  mov     eax, [r13+224h]
0x1400ae8fa  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x1400ae8fe  lea     rax, aFileWzUpdating; " (file '%wZ')Updating VM ID from {%08X-"...
0x1400ae905  mov     [rsp+1E0h+var_1B8], r13; char
0x1400ae90a  mov     [rsp+1E0h+var_1C0], rax; char *
0x1400ae90f  call    TraceEvents
0x1400ae914  mov     r14, [rbp+80h+var_70]
0x1400ae918  xor     r12d, r12d
0x1400ae91b  mov     r15, [rbp+80h+var_68]
0x1400ae91f  mov     edi, [rbp+80h+arg_18]
0x1400ae925  lea     rbx, [r13+238h]
0x1400ae92c  cmp     [r13+258h], r12d
0x1400ae933  jnz     short loc_1400AE93F
0x1400ae935  mov     edi, 0C0000001h
0x1400ae93a  jmp     loc_1400AF011
0x1400ae93f  mov     rcx, rbx
0x1400ae942  call    VhdmpiAcquirePassiveLock
0x1400ae947  movups  xmm0, xmmword ptr [rsi]
0x1400ae94a  mov     rcx, r13
0x1400ae94d  movdqu  xmmword ptr [r13+224h], xmm0
0x1400ae956  call    VhdmpiIsRemoteSmbFile
0x1400ae95b  test    al, al
0x1400ae95d  jnz     short loc_1400AE970
0x1400ae95f  call    VhdmpiCsvResiliencyRequired
0x1400ae964  test    al, al
0x1400ae966  jnz     short loc_1400AE970
0x1400ae968  mov     edi, r12d
0x1400ae96b  jmp     loc_1400AF02D
0x1400ae970  mov     eax, [r13+258h]
0x1400ae977  mov     r12d, 1
0x1400ae97d  sub     eax, r12d
0x1400ae980  cmp     eax, r12d
0x1400ae983  ja      short loc_1400AE935
0x1400ae985  mov     rcx, r13
0x1400ae988  call    VhdmpiIsRemoteSmbFile
0x1400ae98d  test    al, al
0x1400ae98f  jz      short loc_1400AE99B
0x1400ae991  xor     r8d, r8d
0x1400ae994  mov     edx, edi
0x1400ae996  call    ?VhdmpiChangeCacheMode@@YAEPEAU_VHD_FILE_WRAPPER@@W4_VHD_FILE_WRAPPER_CACHE_MODE@@E@Z; VhdmpiChangeCacheMode(_VHD_FILE_WRAPPER *,_VHD_FILE_WRAPPER_CACHE_MODE,uchar)
0x1400ae99b  mov     rcx, r13
0x1400ae99e  call    VhdmpiIsRemoteSmbFile
0x1400ae9a3  test    al, al
0x1400ae9a5  jz      loc_1400AED79
0x1400ae9ab  mov     r9b, [rbp+80h+arg_10]; unsigned __int8
0x1400ae9b2  lea     rax, [rbp+80h+var_100]
0x1400ae9b6  mov     [rsp+1E0h+var_1A8], rax; unsigned __int8 *
0x1400ae9bb  mov     edx, 80000000h; unsigned int
0x1400ae9c0  lea     rax, [rbp+80h+Object]
0x1400ae9c4  mov     r8d, 3; unsigned int
0x1400ae9ca  mov     [rsp+1E0h+var_1B0], rax; struct _FILE_OBJECT **
0x1400ae9cf  lea     rax, [rbp+80h+var_C0]
0x1400ae9d3  mov     [rsp+1E0h+var_1B8], rax; void **
0x1400ae9d8  mov     byte ptr [rsp+1E0h+var_1C0], r12b; char
0x1400ae9dd  call    ?VhdmpiOpenBackingFile@@YAJPEAU_VHD_FILE_WRAPPER@@KKEEPEAPEAXPEAPEAU_FILE_OBJECT@@PEAE@Z; VhdmpiOpenBackingFile(_VHD_FILE_WRAPPER *,ulong,ulong,uchar,uchar,void * *,_FILE_OBJECT * *,uchar *)
0x1400ae9e2  mov     edi, eax
0x1400ae9e4  test    eax, eax
0x1400ae9e6  js      loc_1400AED70
0x1400ae9ec  cmp     byte ptr [r13+1E9h], 0
0x1400ae9f4  jz      loc_1400AED19
0x1400ae9fa  cmp     byte ptr [r13+1E8h], 0
0x1400aea02  jnz     loc_1400AED19
0x1400aea08  mov     rsi, [rbp+80h+Object]
0x1400aea0c  lea     rdx, [rbp+80h+var_E0]
0x1400aea10  mov     rcx, rsi
0x1400aea13  mov     [rbp+80h+var_A0], rsi
0x1400aea17  call    VhdmpiGetVolumeStableGuid
0x1400aea1c  mov     edi, eax
0x1400aea1e  test    eax, eax
0x1400aea20  jns     short loc_1400AEA80
0x1400aea22  mov     eax, cs:dword_140087708
0x1400aea28  cmp     eax, 2
0x1400aea2b  jbe     loc_1400AEFE4
0x1400aea31  mov     edx, 800h
0x1400aea36  lea     rcx, dword_140087708
0x1400aea3d  call    _tlgKeywordOn
0x1400aea42  test    al, al
0x1400aea44  jz      loc_1400AEFE4
0x1400aea4a  mov     ecx, 1C40h
0x1400aea4f  lea     rax, aFileWzFailedTo_3; " (file '%wZ')Failed to query Volume Sta"...
0x1400aea56  mov     r9d, edx; int
0x1400aea59  mov     dword ptr [rsp+1E0h+var_1B0], edi
0x1400aea5d  mov     edx, ecx; int
0x1400aea5f  mov     [rsp+1E0h+var_1B8], r13; char
0x1400aea64  lea     rcx, aVhdmpisetfilew; "VhdmpiSetFileWrapperVirtualMachineId"
0x1400aea6b  mov     [rsp+1E0h+var_1C0], rax; char *
0x1400aea70  mov     r8d, 2; int
0x1400aea76  call    TraceEvents
0x1400aea7b  jmp     loc_1400AEFE4
0x1400aea80  mov     rax, qword ptr [rbp+80h+var_E0]
0x1400aea84  mov     rdi, qword ptr [rbp+80h+var_E0+8]
0x1400aea88  cmp     rax, [r13+1F8h]
0x1400aea8f  jnz     loc_1400AEB6A
0x1400aea95  cmp     rdi, [r13+200h]
0x1400aea9c  jnz     loc_1400AEB6A
0x1400aeaa2  mov     rcx, [rbp+80h+var_C0]; void *
0x1400aeaa6  lea     rdx, [rbp+80h+var_78]; __int64 *
0x1400aeaaa  call    ?VhdmpiGetFileId@@YAJPEAXPEA_J@Z; VhdmpiGetFileId(void *,__int64 *)
0x1400aeaaf  mov     edi, eax
0x1400aeab1  test    eax, eax
0x1400aeab3  jns     short loc_1400AEAEE
0x1400aeab5  mov     eax, cs:dword_140087708
0x1400aeabb  cmp     eax, 2
0x1400aeabe  jbe     loc_1400AEFE4
0x1400aeac4  mov     edx, 800h
0x1400aeac9  lea     rcx, dword_140087708
0x1400aead0  call    _tlgKeywordOn
0x1400aead5  test    al, al
0x1400aead7  jz      loc_1400AEFE4
0x1400aeadd  mov     ecx, 1C55h
0x1400aeae2  lea     rax, aFileWzFailedTo_2; " (file '%wZ')Failed to query FileId: 0x"...
0x1400aeae9  jmp     loc_1400AEA56
0x1400aeaee  mov     r8, [rbp+80h+var_78]
0x1400aeaf2  cmp     r8, [r13+1F0h]
0x1400aeaf9  jz      loc_1400AED7D
0x1400aeaff  mov     eax, cs:dword_140087708
0x1400aeb05  cmp     eax, 2
0x1400aeb08  jbe     loc_1400AED0F
0x1400aeb0e  mov     edx, 800h
0x1400aeb13  lea     rcx, dword_140087708
0x1400aeb1a  call    _tlgKeywordOn
0x1400aeb1f  test    al, al
0x1400aeb21  jz      loc_1400AED0F
0x1400aeb27  mov     rax, [r13+1F0h]
0x1400aeb2e  mov     ecx, 1C5Fh
0x1400aeb33  mov     [rsp+1E0h+var_1A8], r8
0x1400aeb38  mov     [rsp+1E0h+var_1B0], rax
0x1400aeb3d  lea     rax, aFileWzFileidCh; " (file '%wZ')FileId changed between ori"...
0x1400aeb44  mov     r9d, edx; int
0x1400aeb47  mov     [rsp+1E0h+var_1B8], r13; char
0x1400aeb4c  mov     edx, ecx; int
0x1400aeb4e  mov     [rsp+1E0h+var_1C0], rax; char *
0x1400aeb53  lea     rcx, aVhdmpisetfilew; "VhdmpiSetFileWrapperVirtualMachineId"
0x1400aeb5a  mov     r8d, 2; int
0x1400aeb60  call    TraceEvents
0x1400aeb65  jmp     loc_1400AED0F
0x1400aeb6a  mov     eax, cs:dword_140087708
0x1400aeb70  cmp     eax, 2
0x1400aeb73  jbe     loc_1400AED0F
0x1400aeb79  mov     edx, 800h
0x1400aeb7e  lea     rcx, dword_140087708
0x1400aeb85  call    _tlgKeywordOn
0x1400aeb8a  test    al, al
0x1400aeb8c  jz      loc_1400AED0F
0x1400aeb92  mov     rcx, qword ptr [rbp+80h+arg_0]
0x1400aeb99  movzx   r14d, byte ptr [r13+207h]
0x1400aeba1  movzx   r15d, byte ptr [r13+206h]
0x1400aeba9  movzx   r12d, byte ptr [r13+205h]
0x1400aebb1  movzx   edx, byte ptr [rbp+80h+var_E0+0Dh]
0x1400aebb5  movzx   r8d, byte ptr [rbp+80h+var_E0+0Ch]
0x1400aebba  movzx   r9d, byte ptr [rbp+80h+var_E0+0Bh]
0x1400aebbf  mov     rax, qword ptr [rbp+80h+arg_0]
0x1400aebc6  movzx   r13d, byte ptr [r13+204h]
0x1400aebce  movzx   r10d, byte ptr [rbp+80h+var_E0+0Ah]
0x1400aebd3  movzx   r11d, byte ptr [rbp+80h+var_E0+9]
0x1400aebd8  movzx   eax, byte ptr [rax+203h]
0x1400aebdf  movzx   esi, word ptr [rbp+80h+var_E0+4]
0x1400aebe3  mov     dword ptr [rbp+80h+var_E8], eax
0x1400aebe6  movzx   eax, byte ptr [rcx+202h]
0x1400aebed  mov     [rbp+80h+var_EC], eax
0x1400aebf0  movzx   eax, byte ptr [rcx+201h]
0x1400aebf7  mov     [rbp+80h+var_F0], eax
0x1400aebfa  movzx   eax, byte ptr [rcx+200h]
0x1400aec01  mov     [rbp+80h+var_F4], eax
0x1400aec04  movzx   eax, word ptr [rcx+1FEh]
0x1400aec0b  mov     [rbp+80h+var_F8], eax
0x1400aec0e  movzx   eax, word ptr [rcx+1FCh]
0x1400aec15  movzx   ecx, byte ptr [rbp+80h+var_E0+0Eh]
0x1400aec19  mov     [rbp+80h+var_FC], eax
0x1400aec1c  movzx   eax, byte ptr [rbp+80h+var_E0+0Fh]
0x1400aec20  mov     dword ptr [rsp+1E0h+var_108], eax
0x1400aec27  mov     rax, qword ptr [rbp+80h+var_E0]
0x1400aec2b  mov     dword ptr [rsp+1E0h+var_110], ecx
  ... truncated ...
```
