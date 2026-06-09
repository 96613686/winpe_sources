# VhdmpiCreateNewVhd(_GUID const &,_VHD_HANDLE_CONTEXT *,_VHD_CREATE_CONTEXT *)

- ea: `0x1400a1a6c`
- end: `0x1400a2dac`
- name: `?VhdmpiCreateNewVhd@@YAJAEBU_GUID@@PEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_CREATE_CONTEXT@@@Z`
- size: `4928`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _VHD_HANDLE_CONTEXT *, struct _VHD_CREATE_CONTEXT *)`
- caller_count: `1`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x1400eb700`

## callees

- `0x1400010d0`
- `0x140001130`
- `0x14001dbb4`
- `0x140023560`
- `0x140025698`
- `0x140035e94`
- `0x140049958`
- `0x140049ad8`
- `0x14004a584`
- `0x14004a618`
- `0x14004d820`
- `0x14004db00`
- `0x14004ded8`
- `0x14004e0a8`
- `0x14004e978`
- `0x14005d7c0`
- `0x14005d840`
- `0x14005d8e0`
- `0x14005dd00`
- `0x1400a19f0`
- `0x1400a1a6c`
- `0x1400a2db4`
- `0x1400a2e80`
- `0x1400a3cd0`
- `0x1400a3e2c`
- `0x1400a3ed4`
- `0x1400cefcc`
- `0x1400cfdf8`
- `0x1400d0370`
- `0x1400d03dc`
- `0x1400e98ec`
- `0x1400ea9b4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400a2064`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a2064`
- `ntoskrnl!ZwClose` at `0x1400a207b`
- `ntoskrnl!ZwClose` at `0x1400a207b`
- `ntoskrnl!EtwActivityIdControl` at `0x1400a1c39`
- `ntoskrnl!EtwActivityIdControl` at `0x1400a29cf`
- `ntoskrnl!EtwActivityIdControl` at `0x1400a1c39`
- `ntoskrnl!EtwActivityIdControl` at `0x1400a29cf`

## string_xrefs

- `0x1400a1bbd`: `VhdmpiCreateNewVhd`
- `0x1400a1c19`: `VhdmpiCreateNewVhd`
- `0x1400a1e04`: `VhdmpiCreateNewVhd`
- `0x1400a1eaa`: `VhdmpiCreateNewVhd`
- `0x1400a1f57`: `VhdmpiCreateNewVhd`
- `0x1400a1fcb`: `VhdmpiCreateNewVhd`
- `0x1400a2296`: `VhdmpiCreateNewVhd`
- `0x1400a2394`: `VhdmpiCreateNewVhd`
- `0x1400a241c`: `VhdmpiCreateNewVhd`
- `0x1400a24f7`: `VhdmpiCreateNewVhd`
- `0x1400a25ac`: `VhdmpiCreateNewVhd`
- `0x1400a2983`: `VhdmpiCreateNewVhd`
- `0x1400a2ac2`: `VhdmpiCreateNewVhd`
- `0x1400a2ccb`: `VhdmpiCreateNewVhd`
- `0x1400a2d77`: `VhdmpiCreateNewVhd`
- `0x1400a1e91`: `Failed to acquire parent RCT access (0x%08x)`
- `0x1400a1deb`: `Failed to open parent (0x%08x)`
- `0x1400a237a`: `Conversion to or from a PMEM-compatible disk is not supported`
- `0x1400a2972`: `Attaching a virtual disk to an incompatible parent.`
- `0x1400a2d5d`: `new VHD 0x%p successfully created`

## pseudocode

```c
__int64 __fastcall VhdmpiCreateNewVhd(
        const struct _GUID *a1,
        struct _VHD_HANDLE_CONTEXT *a2,
        struct _VHD_CREATE_CONTEXT *a3)
{
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ecx
  struct _VHD_BACKING_STORE_HEADER *v8; // r15
  __int64 v9; // rdx
  struct _VHD_VIRTUAL_DISK *v10; // rsi
  int v11; // r12d
  unsigned int v12; // r14d
  unsigned int v13; // r13d
  char v14; // r8
  int v15; // edx
  __int64 v16; // r9
  __int64 v17; // r15
  __int64 v18; // rcx
  int *v19; // rax
  struct _VHD_HANDLE_CONTEXT *v20; // r12
  int v21; // edx
  int v22; // r9d
  __int64 v23; // rdx
  int v24; // ebx
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rcx
  int *v28; // rax
  int v29; // r8d
  struct _FILE_OBJECT *v30; // r13
  int v31; // eax
  int v32; // r8d
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 (__fastcall *v35)(struct _VHD_BACKING_STORE_HEADER *, __int64, __int64, _QWORD); // rax
  int v36; // eax
  const struct _BACKING_STORE_PARSER *v37; // rdx
  int v38; // edx
  char *v39; // rax
  __int64 v40; // r14
  HANDLE v41; // r14
  __int64 v42; // rcx
  int *v43; // rax
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  unsigned __int8 (__fastcall *v48)(_QWORD, _QWORD, __int64, _QWORD); // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // r8
  bool v52; // zf
  char v53; // al
  int v54; // edx
  char *v55; // rax
  int v56; // r9d
  __int64 (__fastcall *v57)(_QWORD, __int64, __int64, _QWORD); // rax
  __int64 v58; // rax
  int v59; // eax
  int BackingStoreWithMatchingParent; // eax
  struct _FILE_OBJECT *v61; // rsi
  int PhysicalDiskProperties; // eax
  int v63; // eax
  __int64 v64; // r8
  int v65; // r8d
  int v66; // eax
  int v67; // r8d
  int v68; // edx
  char *v69; // rax
  unsigned __int64 v70; // rbx
  int *v71; // r12
  int v72; // eax
  unsigned __int64 v73; // rax
  int v74; // r8d
  unsigned __int64 v75; // r14
  unsigned int v76; // esi
  __int64 v77; // rax
  __int128 v78; // xmm0
  __int128 v79; // xmm1
  struct _VHD_BACKING_STORE_HEADER *v80; // rbx
  __int64 v81; // rax
  __int64 v82; // rax
  struct _VHD_BACKING_STORE_HEADER *v83; // rcx
  void (__fastcall *v84)(struct _VHD_BACKING_STORE_HEADER *, _OWORD *); // rax
  __int64 v85; // r8
  __int64 v86; // rcx
  int *v87; // rax
  __int64 v88; // r12
  int v89; // eax
  int v90; // r8d
  int v91; // edx
  char *v92; // rax
  int RctFiles; // eax
  int v94; // eax
  int v95; // eax
  __int64 v96; // r8
  struct _VHD_BACKING_STORE_HEADER *v97; // rcx
  unsigned int v98; // eax
  unsigned __int64 v99; // rdx
  int v100; // eax
  char *v101; // r8
  struct _VHD_BACKING_STORE_HEADER *v102; // rdi
  int v103; // eax
  int v104; // r8d
  int v105; // r8d
  int v106; // [rsp+20h] [rbp-E0h]
  char *v107; // [rsp+20h] [rbp-E0h]
  char v108; // [rsp+28h] [rbp-D8h]
  char v109[8]; // [rsp+50h] [rbp-B0h]
  char v110; // [rsp+58h] [rbp-A8h]
  char v112[8]; // [rsp+68h] [rbp-98h] BYREF
  PVOID Object; // [rsp+70h] [rbp-90h] BYREF
  struct _VHD_VIRTUAL_DISK *v114; // [rsp+78h] [rbp-88h] BYREF
  char v115; // [rsp+80h] [rbp-80h]
  char v116; // [rsp+81h] [rbp-7Fh]
  char v117; // [rsp+82h] [rbp-7Eh]
  char v118; // [rsp+83h] [rbp-7Dh]
  char v119[4]; // [rsp+84h] [rbp-7Ch] BYREF
  int v120; // [rsp+88h] [rbp-78h] BYREF
  struct _VHD_BACKING_STORE_HEADER *v121; // [rsp+90h] [rbp-70h]
  unsigned __int64 v122; // [rsp+98h] [rbp-68h]
  int *v123; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v124; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v125; // [rsp+ACh] [rbp-54h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v127; // [rsp+B8h] [rbp-48h]
  const GUID *v128; // [rsp+C0h] [rbp-40h] BYREF
  struct _VHD_BACKING_STORE_HEADER *v129; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v130; // [rsp+D0h] [rbp-30h] BYREF
  GUID v131; // [rsp+D8h] [rbp-28h] BYREF
  const GUID *v132; // [rsp+E8h] [rbp-18h]
  GUID ActivityId; // [rsp+F0h] [rbp-10h] BYREF
  const GUID *v134; // [rsp+100h] [rbp+0h]
  _OWORD v135[10]; // [rsp+110h] [rbp+10h] BYREF
  __int128 Buf1; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 Buf2; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v138[96]; // [rsp+1D0h] [rbp+D0h] BYREF

  v128 = a1;
  v112[0] = 0;
  v120 = 0;
  memset(v138, 0, sizeof(v138));
  memset(v135, 0, sizeof(v135));
  v132 = 0;
  v131 = 0;
  VhdmpiGetBackingStoreChainAccessProperties(a2, 1, v112, &v120);
  v5 = *((_QWORD *)a3 + 40);
  LODWORD(v6) = 0;
  v129 = 0;
  *(_QWORD *)&Buf1 = 0;
  v7 = 0;
  *(_QWORD *)&Buf2 = 0;
  v8 = 0;
  v122 = 0;
  v9 = 8;
  v130 = 0;
  v10 = 0;
  v11 = 0;
  v121 = *(struct _VHD_BACKING_STORE_HEADER **)(v5 + 144);
  v12 = 0;
  v110 = 0;
  v13 = 0;
  v114 = 0;
  v127 = *(_QWORD *)v121;
  Handle = 0;
  Object = 0;
  v117 = 0;
  v115 = 0;
  v123 = 0;
  *(_QWORD *)v109 = v5;
  *(_DWORD *)v119 = 0;
  v116 = 0;
  v124 = 0;
  v125 = 0;
  v118 = 0;
  if ( (unsigned int)dword_140087708 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
    {
      TraceEvents((int)"VhdmpiCreateNewVhd", 1018, 4, v9, "Virtual disk: 0x%p Context: 0x%p", v14);
      LODWORD(v6) = 0;
      v9 = 8;
    }
    v7 = 0;
  }
  if ( *((_WORD *)a3 + 104) == (_WORD)v6 )
    goto LABEL_46;
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, v9) )
    TraceEvents((int)"VhdmpiCreateNewVhd", 1031, 4, v15, "diff disk", v108);
  v134 = 0;
  ActivityId = 0;
  EtwActivityIdControl(3u, &ActivityId);
  v134 = v128;
  if ( (unsigned int)dword_1400876D0 <= 4 )
  {
    v17 = *(_QWORD *)v109;
  }
  else if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v17 = *(_QWORD *)v109;
    v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v109 + 144LL) + 120LL);
    v19 = (int *)L"Unknown";
    if ( v18 )
      v19 = *(int **)(*(_QWORD *)(*(_QWORD *)v109 + 144LL) + 120LL);
    v123 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v18,
      (__int64)&dword_14007CACC,
      (__int64)&ActivityId,
      v16,
      &v123);
  }
  else
  {
    v17 = *(_QWORD *)v109;
  }
  v20 = a2;
  v21 = 0;
  v22 = v120;
  if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
    v22 = 0;
  LOBYTE(v21) = (*((_DWORD *)a2 + 1) & 2) != 0;
  v24 = VhdmpiCreateBackingStoreChain(a2, v127, (char *)a3 + 208, v17, 1, 0, v21 | (v112[0] != 0 ? 2 : 0), v22, &v129);
  if ( v24 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v107 = v119;
    *(_DWORD *)v119 = v24;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>();
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v26 = *(_QWORD *)(v17 + 144);
    *(_DWORD *)v119 = v24;
    v27 = *(_QWORD *)(v26 + 120);
    v28 = (int *)L"Unknown";
    if ( v27 )
      v28 = (int *)v27;
    v123 = v28;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v27,
      (unsigned __int8 *)byte_14007CA8D,
      &ActivityId,
      v134,
      &v123,
      (__int64)v119);
  }
  LODWORD(v6) = 0;
  if ( v24 >= 0 )
  {
    v8 = v129;
    if ( *((_BYTE *)a3 + 263) )
    {
      if ( !v112[0] )
      {
        v24 = -1073741811;
LABEL_32:
        v8 = v129;
        goto LABEL_33;
      }
      v31 = VhdmpiAcquireRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16), v129);
      LODWORD(v6) = 0;
      v24 = v31;
      if ( v31 < 0 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
        {
          TraceEvents((int)"VhdmpiCreateNewVhd", 1100, 2, v32, "Failed to acquire parent RCT access (0x%08x)", v24);
          goto LABEL_31;
        }
LABEL_33:
        v30 = (struct _FILE_OBJECT *)Object;
        goto LABEL_61;
      }
      v110 = 1;
    }
    v123 = (int *)(*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, __int64, __int64, _QWORD, char *))(*(_QWORD *)v8 + 160LL))(
                    v8,
                    v23,
                    v25,
                    0,
                    v107);
    LODWORD(v6) = 0;
    v35 = *(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, __int64, __int64, _QWORD))(*(_QWORD *)v8 + 240LL);
    if ( v35 )
    {
      v11 = v35(v8, v33, v34, 0);
      LODWORD(v6) = 0;
    }
    else
    {
      v11 = 0;
    }
    v7 = *((_DWORD *)v8 + 17);
    *(_DWORD *)v119 = v7;
LABEL_46:
    if ( *((_WORD *)a3 + 96) == (_WORD)v6 )
    {
      v64 = v127;
    }
    else
    {
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
        TraceEvents((int)"VhdmpiCreateNewVhd", 1128, 4, 8, "source specified.", v108);
      v36 = VhdmpiTryOpenPhysicalDisk((const struct _UNICODE_STRING *)a3 + 12, &Handle, (struct _FILE_OBJECT **)&Object);
      LODWORD(v6) = 0;
      v24 = v36;
      if ( v36 < 0 )
        goto LABEL_58;
      if ( Handle )
      {
        if ( *((_DWORD *)a3 + 44) == 2 )
        {
          if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
            goto LABEL_57;
          v38 = 1240;
          v39 = "parent with physical source is not valid!";
LABEL_56:
          TraceEvents((int)"VhdmpiCreateNewVhd", v38, 2, 8, v39, v108);
          LODWORD(v6) = 0;
LABEL_57:
          v24 = -1073741811;
LABEL_58:
          v10 = v114;
LABEL_59:
          v30 = (struct _FILE_OBJECT *)Object;
LABEL_60:
          v20 = a2;
          goto LABEL_61;
        }
        if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
          TraceEvents((int)"VhdmpiCreateNewVhd", 1248, 4, 8, "source is not a file...", v108);
        v61 = (struct _FILE_OBJECT *)Object;
        PhysicalDiskProperties = VhdmpiGetPhysicalDiskProperties((PFILE_OBJECT)Object, &v130, &v124, &v125);
        LODWORD(v6) = 0;
        v24 = PhysicalDiskProperties;
        if ( PhysicalDiskProperties < 0 )
          goto LABEL_58;
        if ( *((_BYTE *)a3 + 260) )
        {
          v63 = VhdmpiTakePhysicalDiskOwnership(v61, (struct VHD_DISK_OWNERSHIP *)v138);
          v10 = v114;
          LODWORD(v6) = 0;
          v24 = v63;
          if ( v63 < 0 )
            goto LABEL_59;
          v115 = 1;
        }
        else
        {
          v10 = v114;
        }
        v13 = v125;
        v12 = v124;
        v122 = v130;
      }
      else
      {
        v37 = (const struct _BACKING_STORE_PARSER *)*((_QWORD *)a3 + 23);
        if ( !v37 )
        {
          if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
            goto LABEL_57;
          v38 = 1146;
          v39 = "Failed to find parser";
          goto LABEL_56;
        }
        v45 = VhdmpiOpenSourceVirtualDisk(a2, v37, (const struct _UNICODE_STRING *)a3 + 12, &v114);
        v6 = 0;
        v24 = v45;
        if ( v45 < 0 )
          goto LABEL_58;
        v10 = v114;
        if ( *((_BYTE *)a3 + 280)
          || (v48 = *(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(*((_QWORD *)a3 + 23) + 560LL)) != 0
          && v48(*((_QWORD *)v114 + 18), 0, v47, 0) )
        {
          if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
            TraceEvents(
              (int)"VhdmpiCreateNewVhd",
              1173,
              2,
              8,
              "Conversion to or from a PMEM-compatible disk is not supported",
              v108);
          v24 = -1073741637;
          goto LABEL_118;
        }
        v49 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(*((_QWORD *)a3 + 23) + 160LL))(
                *((_QWORD *)v10 + 18),
                v46,
                v47,
                v6);
        v52 = *((_DWORD *)a3 + 44) == 2;
        v122 = v49;
        if ( v52 )
        {
          v53 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a3 + 23) + 112LL))(*((_QWORD *)v10 + 18));
          LODWORD(v6) = 0;
          if ( !v53 && !*((_BYTE *)a3 + 262) )
          {
            if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
              goto LABEL_101;
            v54 = 1187;
            v55 = "parent with non-diff source is not valid!";
            v56 = 8;
LABEL_100:
            TraceEvents((int)"VhdmpiCreateNewVhd", v54, 2, v56, v55, v108);
            LODWORD(v6) = 0;
LABEL_101:
            v24 = -1073741811;
            goto LABEL_59;
          }
        }
        else
        {
          LODWORD(v6) = 0;
        }
        v57 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(*((_QWORD *)a3 + 23) + 240LL);
        if ( v57 )
        {
          v12 = v57(*((_QWORD *)v10 + 18), v50, v51, 0);
          LODWORD(v6) = 0;
        }
        else
        {
          v12 = 0;
        }
        v58 = *((_QWORD *)v10 + 18);
        v13 = *(_DWORD *)(v58 + 68);
        if ( *((_DWORD *)a3 + 44) == 2 )
        {
          if ( *((_BYTE *)a3 + 262) )
          {
            v59 = VhdmpiAcquireRctAccessForChain(
                    (struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16),
                    *((struct _VHD_BACKING_STORE_HEADER **)v10 + 18));
            LODWORD(v6) = 0;
            v24 = v59;
            if ( v59 < 0 )
              goto LABEL_59;
            v116 = 1;
          }
          else
          {
            if ( *((_WORD *)a3 + 112) )
            {
              BackingStoreWithMatchingParent = VhdmpiFindBackingStoreWithMatchingParent(
                                                 v10,
                                                 (const struct _UNICODE_STRING *)a3 + 14,
                                                 (struct _VHD_BACKING_STORE_HEADER **)&Buf2);
              LODWORD(v6) = 0;
              v24 = BackingStoreWithMatchingParent;
              if ( BackingStoreWithMatchingParent < 0 )
                goto LABEL_59;
              v58 = Buf2;
            }
            *(_QWORD *)&Buf1 = v58;
          }
        }
      }
      v64 = v127;
      if ( v12 == 4096 && (char **)v127 == &Vhd1Parser )
      {
        v24 = -1073741811;
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
          goto LABEL_59;
        TraceEvents((int)"VhdmpiCreateNewVhd", 1293, 2, v65, "source LogicalSectorSize is not supported by VHD1", v108);
        goto LABEL_118;
      }
      v7 = *(_DWORD *)v119;
    }
    if ( *((_BYTE *)a3 + 280) != (_BYTE)v6 )
    {
      if ( *((_DWORD *)a3 + 62) == (_DWORD)v6 )
        *((_DWORD *)a3 + 62) = 4096;
      if ( *((_DWORD *)a3 + 63) == (_DWORD)v6 )
        *((_DWORD *)a3 + 63) = 4096;
    }
    v66 = *((_DWORD *)a3 + 62);
    if ( !v66 )
    {
      if ( v12 )
      {
        if ( v11 && v12 != v11 )
        {
          v24 = -1073741811;
          if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
            goto LABEL_58;
          v68 = 1326;
          v69 = "source LogicalSectorSize does not match parent";
          goto LABEL_152;
        }
        *((_DWORD *)a3 + 62) = v12;
      }
      else
      {
        v72 = 512;
        if ( v11 )
          v72 = v11;
        *((_DWORD *)a3 + 62) = v72;
      }
LABEL_154:
      v70 = *((_QWORD *)a3 + 30);
      v10 = v114;
      if ( v70 )
      {
        v73 = v122;
      }
      else
      {
        if ( !v114 )
        {
          v41 = Handle;
          if ( !Handle )
          {
            if ( !v8 )
            {
              v30 = (struct _FILE_OBJECT *)Object;
              v24 = -1073741811;
              goto LABEL_67;
            }
            v71 = v123;
            *((_QWORD *)a3 + 30) = v123;
            v70 = (unsigned __int64)v71;
            goto LABEL_183;
          }
        }
        v73 = v122;
        *((_QWORD *)a3 + 30) = v122;
        v70 = v73;
      }
      v41 = Handle;
      if ( (v10 || Handle) && v73 > v70 )
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
          goto LABEL_101;
        v54 = 1398;
        v55 = "source is too big for VHD";
LABEL_181:
        v56 = v74;
        goto LABEL_100;
      }
      v71 = v123;
LABEL_183:
      if ( v8 && (v10 || v41) )
      {
        v75 = v122;
        if ( v122 != v70 )
        {
          if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
            goto LABEL_101;
          v54 = 1410;
          v55 = "source doesn't match new VHD in diff-to-diff";
          goto LABEL_181;
        }
      }
      else
      {
        v75 = v122;
      }
      v76 = *((_DWORD *)a3 + 62);
      if ( v70 % v76 )
        goto LABEL_57;
      if ( *((_DWORD *)a3 + 63) )
      {
        v13 = *((_DWORD *)a3 + 63);
        goto LABEL_200;
      }
      if ( *(_DWORD *)(v64 + 24) == (_DWORD)v6 )
      {
        if ( v13 )
          goto LABEL_196;
        if ( v7 )
        {
          *((_DWORD *)a3 + 63) = v7;
          v13 = v7;
          goto LABEL_200;
        }
      }
      v13 = *(_DWORD *)(v64 + 28);
LABEL_196:
      *((_DWORD *)a3 + 63) = v13;
LABEL_200:
      memset(v135, 0, sizeof(v135));
      LODWORD(v135[0]) = *((_DWORD *)a3 + 44);
      DWORD1(v135[0]) = *((_DWORD *)a3 + 64);
      LODWORD(v135[8]) = *((_DWORD *)a3 + 74);
      v77 = *((_QWORD *)a3 + 38);
      *((_QWORD *)&v135[0] + 1) = __PAIR64__(v13, v76);
      v10 = v114;
      *((_QWORD *)&v135[8] + 1) = v77;
      v78 = *(_OWORD *)((char *)a3 + 264);
      v79 = *(_OWORD *)((char *)a3 + 280);
      v135[1] = v78;
      v135[7] = v79;
      if ( !v8 || v114 || (*(_QWORD *)&v135[3] = v71, v70 <= (unsigned __int64)v71) )
        *(_QWORD *)&v135[3] = v70;
      *((_QWORD *)&v135[3] + 1) = v8;
      if ( !*((_BYTE *)a3 + 261) )
      {
        if ( v114 )
          *(_QWORD *)&v135[4] = *((_QWORD *)v114 + 18);
        else
          *(_QWORD *)&v135[4] = v8;
      }
      v30 = (struct _FILE_OBJECT *)Object;
      *(_QWORD *)&v135[6] = Object;
      *((_QWORD *)&v135[4] + 1) = Buf1;
      *((_QWORD *)&v135[5] + 1) = v114;
      *((_QWORD *)&v135[6] + 1) = v75;
      if ( *((_BYTE *)a3 + 262) )
        *(_QWORD *)&v135[5] = (char *)a3 + 224;
      v135[2] = v78;
      if ( *(_BYTE *)(v127 + 52) )
      {
        if ( v114 )
        {
          v80 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v114 + 18);
          v81 = *(_QWORD *)v80;
          if ( v8 )
          {
            Buf1 = 0;
            Buf2 = 0;
            (*(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, __int128 *, _QWORD))(v81 + 200))(v80, &Buf1, 0);
            (*(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, __int128 *))(*(_QWORD *)v8 + 216LL))(v8, &Buf2);
            if ( !memcmp(&Buf1, &Buf2, 0x10u) )
            {
              v82 = *(_QWORD *)v80;
              v83 = v80;
LABEL_223:
              v84 = *(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, _OWORD *))(v82 + 216);
              goto LABEL_224;
            }
            if ( (unsigned int)dword_140087708 > 3 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 1) )
              TraceEvents(
                (int)"VhdmpiCreateNewVhd",
                1555,
                3,
                1,
                "Attaching a virtual disk to an incompatible parent.",
                v108);
          }
          else
          {
            v84 = *(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, _OWORD *))(v81 + 216);
            if ( v84 )
            {
              v83 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v114 + 18);
LABEL_224:
              v84(v83, &v135[2]);
            }
          }
        }
        else if ( v8 && v70 >= (unsigned __int64)v71 )
        {
          v82 = *(_QWORD *)v8;
          v83 = v8;
          goto LABEL_223;
        }
      }
      EtwActivityIdControl(3u, &v131);
      v132 = v128;
      if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
      {
        v86 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v109 + 144LL) + 120LL);
        v87 = (int *)L"Unknown";
        if ( v86 )
          v87 = *(int **)(*(_QWORD *)(*(_QWORD *)v109 + 144LL) + 120LL);
        v128 = (const GUID *)v87;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v86,
          (__int64)byte_14007CA4B,
          (__int64)&v131,
          v85,
          &v128);
      }
      v88 = v127;
      v135[9] = v131;
      v118 = 1;
      v89 = (*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, char *, _OWORD *, _QWORD))(v127 + 168))(
              v121,
              (char *)a3 + 96,
              v135,
              0);
      LODWORD(v6) = 0;
      v24 = v89;
      if ( v89 < 0 )
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
          goto LABEL_60;
        v91 = 1607;
        v92 = "VHD initialization failed(0x%08x).";
        goto LABEL_234;
      }
      if ( v110 && (unsigned __int8)VhdmpiIsRctEnabled(v8) )
      {
        RctFiles = VhdmpiCreateRctFiles((__int64)v121);
        LODWORD(v6) = 0;
        v24 = RctFiles;
        if ( RctFiles < 0 )
          goto LABEL_60;
        v117 = 1;
        v94 = VhdmpiAcquireRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16), v121);
        LODWORD(v6) = 0;
        v24 = v94;
        if ( v94 < 0 )
        {
          v10 = v114;
          goto LABEL_60;
        }
        v24 = VhdmpiPopulateRctFiles(*((struct VHD_RCT_STATE **)v121 + 227), 1, *((_QWORD *)v8 + 227));
        if ( v24 >= 0 && *(_QWORD *)&v135[3] < *((_QWORD *)a3 + 30) )
          v24 = VhdmpiResizeRctFile(*((struct VHD_RCT_STATE **)v121 + 227));
        VhdmpiReleaseRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16), v121);
        v10 = v114;
        LODWORD(v6) = 0;
        if ( v24 < 0 )
          goto LABEL_60;
      }
      else
      {
        VhdmpiDeleteRctFiles((char *)v121 + 72);
      }
      v95 = VhdmpiInitAndLoadAndVerifyBackingStore(v121, 2);
      LODWORD(v6) = 0;
      v24 = v95;
      if ( v95 < 0 )
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
          goto LABEL_60;
        v91 = 1692;
        v92 = "failed to finalize initialization of backing store information (0x%08x).";
LABEL_234:
        TraceEvents((int)"VhdmpiCreateNewVhd", v91, 2, v90, v92, v24);
        goto LABEL_119;
      }
      v97 = v121;
      v98 = *((_DWORD *)v121 + 16);
      *(_DWORD *)(*(_QWORD *)v109 + 72LL) = v98;
      _BitScanForward(&v98, v98);
      *(_DWORD *)(*(_QWORD *)v109 + 76LL) = v98;
      v99 = *((_QWORD *)a3 + 30);
      if ( *(_QWORD *)&v135[3] < v99 )
      {
        v100 = (*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, unsigned __int64, __int64, _QWORD))(v88 + 336))(
                 v97,
                 v99,
                 v96,
                 0);
        LODWORD(v6) = 0;
        v24 = v100;
        if ( v100 < 0 )
        {
          v40 = *(_QWORD *)v109;
          goto LABEL_268;
        }
        *(_QWORD *)&v135[3] = *((_QWORD *)a3 + 30);
      }
      v40 = *(_QWORD *)v109;
      v101 = (char *)a3 + 96;
      v102 = v121;
      LOBYTE(v106) = 1;
      v103 = (*(__int64 (__fastcall **)(char *, struct _VHD_BACKING_STORE_HEADER *, char *, _OWORD *, int))(v88 + 184))(
               *(char **)v109,
               v121,
               v101,
               v135,
               v106);
      LODWORD(v6) = 0;
      v24 = v103;
      if ( v103 >= 0 )
      {
        v20 = a2;
        if ( v8 )
        {
          if ( v110 )
          {
            VhdmpiReleaseRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16), v8);
            LODWORD(v6) = 0;
            v110 = 0;
          }
          if ( (*((_DWORD *)a2 + 1) & 2) == 0 )
          {
            VhdmpiAttachParentBackingStoreChain(v102, v8);
            LODWORD(v6) = 0;
            v8 = 0;
          }
          *((_DWORD *)v102 + 291) = 2;
        }
        if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
        {
          TraceEvents((int)"VhdmpiCreateNewVhd", 1783, 4, v105, "new VHD 0x%p successfully created", v109[0]);
          LODWORD(v6) = 0;
        }
        v24 = v6;
        goto LABEL_62;
      }
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      {
        TraceEvents((int)"VhdmpiCreateNewVhd", 1740, 2, v104, "VHD final initialization failed(0x%08x).", v24);
        v20 = a2;
        LODWORD(v6) = 0;
        goto LABEL_62;
      }
LABEL_268:
      v20 = a2;
      goto LABEL_62;
    }
    if ( !v12 || v66 == v12 )
    {
      if ( !v11 || v66 == v11 )
        goto LABEL_154;
      v24 = -1073741811;
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
        goto LABEL_58;
      v68 = 1366;
      v69 = "child LogicalSectorSize does not match parent";
    }
    else
    {
      v24 = -1073741811;
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
        goto LABEL_58;
      v68 = 1351;
      v69 = "destination LogicalSectorSize does not match source";
    }
LABEL_152:
    TraceEvents((int)"VhdmpiCreateNewVhd", v68, 2, v67, v69, v108);
    v10 = v114;
LABEL_118:
    v30 = (struct _FILE_OBJECT *)Object;
LABEL_119:
    LODWORD(v6) = 0;
    goto LABEL_60;
  }
  if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
    goto LABEL_32;
  TraceEvents((int)"VhdmpiCreateNewVhd", 1073, 2, v29, "Failed to open parent (0x%08x)", v24);
  v8 = v129;
LABEL_31:
  v30 = (struct _FILE_OBJECT *)Object;
  LODWORD(v6) = 0;
LABEL_61:
  v40 = *(_QWORD *)v109;
LABEL_62:
  if ( v8 )
  {
    if ( v110 != (_BYTE)v6 )
      VhdmpiReleaseRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)v20 + 16), v8);
    LOBYTE(v6) = v112[0];
    VhdmpiReleaseBackingStoreChainAccess((_DWORD)v20, (_DWORD)v8, -1, v6, v120);
    VhdmpiReleaseBackingStoreChain(v8, v40);
    LOBYTE(v6) = 0;
  }
  v41 = Handle;
LABEL_67:
  if ( v115 != (_BYTE)v6 )
  {
    VhdmpiReleasePhysicalDiskOwnership(v30, (struct VHD_DISK_OWNERSHIP *)v138);
    LOBYTE(v6) = 0;
  }
  if ( Object )
  {
    ObfDereferenceObject(Object);
    LOBYTE(v6) = 0;
  }
  if ( v41 )
  {
    ZwClose(v41);
    LOBYTE(v6) = 0;
  }
  if ( v10 )
  {
    if ( v116 != (_BYTE)v6 )
      VhdmpiReleaseRctAccessForChain(
        (struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16),
        *((struct _VHD_BACKING_STORE_HEADER **)v10 + 18));
    VhdmpiCloseSourceVirtualDisk(a2, v10);
    LOBYTE(v6) = 0;
  }
  if ( v117 != (_BYTE)v6 )
  {
    VhdmpiDeleteRctFiles((char *)v121 + 72);
    LOBYTE(v6) = 0;
  }
  if ( v118 != (_BYTE)v6 )
  {
    if ( v24 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
    {
      v120 = v24;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>();
    }
    if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
    {
      v120 = v24;
      v42 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v109 + 144LL) + 120LL);
      v43 = (int *)L"Unknown";
      if ( v42 )
        v43 = *(int **)(*(_QWORD *)(*(_QWORD *)v109 + 144LL) + 120LL);
      v128 = (const GUID *)v43;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v42,
        (unsigned __int8 *)&unk_14007CA00,
        &v131,
        v132,
        (int **)&v128,
        (__int64)&v120);
    }
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1400a1a6c  mov     [rsp-8+arg_18], rbx
0x1400a1a71  push    rbp
0x1400a1a72  push    rsi
0x1400a1a73  push    rdi
0x1400a1a74  push    r12
0x1400a1a76  push    r13
0x1400a1a78  push    r14
0x1400a1a7a  push    r15
0x1400a1a7c  lea     rbp, [rsp-140h]
0x1400a1a84  sub     rsp, 240h
0x1400a1a8b  mov     rax, cs:__security_cookie
0x1400a1a92  xor     rax, rsp
0x1400a1a95  mov     [rbp+170h+var_40], rax
0x1400a1a9c  xor     eax, eax
0x1400a1a9e  mov     [rsp+270h+var_210], rdx
0x1400a1aa3  mov     rdi, r8
0x1400a1aa6  mov     [rbp+170h+var_1B0], rcx
0x1400a1aaa  mov     rbx, rdx
0x1400a1aad  mov     [rsp+270h+var_208], al
0x1400a1ab1  xor     edx, edx; Val
0x1400a1ab3  mov     [rbp+170h+var_1E8], eax
0x1400a1ab6  lea     r8d, [rax+60h]; Size
0x1400a1aba  lea     rcx, [rbp+170h+var_A0]; void *
0x1400a1ac1  call    memset
0x1400a1ac6  xor     edx, edx; Val
0x1400a1ac8  lea     rcx, [rbp+170h+var_160]; void *
0x1400a1acc  mov     r8d, 0A0h; Size
0x1400a1ad2  call    memset
0x1400a1ad7  xor     eax, eax
0x1400a1ad9  lea     r9, [rbp+170h+var_1E8]
0x1400a1add  xorps   xmm0, xmm0
0x1400a1ae0  mov     [rbp+170h+var_188], rax
0x1400a1ae4  lea     r8, [rsp+270h+var_208]
0x1400a1ae9  mov     rcx, rbx
0x1400a1aec  movups  xmmword ptr [rbp+170h+var_198.Data1], xmm0
0x1400a1af0  lea     edx, [rax+1]
0x1400a1af3  call    VhdmpiGetBackingStoreChainAccessProperties
0x1400a1af8  mov     r8, [rdi+140h]
0x1400a1aff  xor     r9d, r9d
0x1400a1b02  mov     eax, r9d
0x1400a1b05  mov     [rbp+170h+var_1A8], r9
0x1400a1b09  mov     qword ptr [rbp+170h+Buf1], rax
0x1400a1b10  mov     ecx, r9d
0x1400a1b13  mov     qword ptr [rbp+170h+Buf2], rax
0x1400a1b1a  mov     r15d, r9d
0x1400a1b1d  mov     [rbp+170h+var_1D8], rax
0x1400a1b21  lea     edx, [r9+8]
0x1400a1b25  mov     [rbp+170h+var_1A0], rax
0x1400a1b29  mov     esi, r9d
0x1400a1b2c  mov     rax, [r8+90h]
0x1400a1b33  mov     r12d, r9d
0x1400a1b36  mov     [rbp+170h+var_1E0], rax
0x1400a1b3a  mov     r14d, r9d
0x1400a1b3d  mov     [rsp+270h+var_218], r9b
0x1400a1b42  mov     r13d, r9d
0x1400a1b45  mov     [rsp+270h+var_1F8], r9
0x1400a1b4a  mov     rax, [rax]
0x1400a1b4d  mov     [rbp+170h+var_1B8], rax
0x1400a1b51  mov     eax, cs:dword_140087708
0x1400a1b57  mov     [rbp+170h+Handle], r9
0x1400a1b5b  mov     [rsp+270h+Object], r9
0x1400a1b60  mov     [rbp+170h+var_1EE], r9b
0x1400a1b64  mov     [rbp+170h+var_1F0], r9b
0x1400a1b68  mov     [rbp+170h+var_1D0], r9
0x1400a1b6c  mov     qword ptr [rsp+270h+var_220], r8
0x1400a1b71  mov     dword ptr [rbp+170h+var_1EC], ecx
0x1400a1b74  mov     [rbp+170h+var_1EF], r9b
0x1400a1b78  mov     [rbp+170h+var_1C8], r9d
0x1400a1b7c  mov     [rbp+170h+var_1C4], r9d
0x1400a1b80  mov     [rbp+170h+var_1ED], r9b
0x1400a1b84  cmp     eax, 4
0x1400a1b87  jbe     short loc_1400A1BD1
0x1400a1b89  lea     rcx, dword_140087708
0x1400a1b90  call    _tlgKeywordOn
0x1400a1b95  test    al, al
0x1400a1b97  jz      short loc_1400A1BCF
0x1400a1b99  mov     ecx, 3FAh
0x1400a1b9e  mov     [rsp+270h+var_240], rdi
0x1400a1ba3  mov     qword ptr [rsp+270h+var_248], r8; char
0x1400a1ba8  lea     rax, aVirtualDisk0xP; "Virtual disk: 0x%p Context: 0x%p"
0x1400a1baf  mov     r9d, edx; int
0x1400a1bb2  mov     [rsp+270h+var_250], rax; char *
0x1400a1bb7  mov     edx, ecx; int
0x1400a1bb9  lea     r8d, [rsi+4]; int
0x1400a1bbd  lea     rcx, aVhdmpicreatene_0; "VhdmpiCreateNewVhd"
0x1400a1bc4  call    TraceEvents
0x1400a1bc9  xor     r9d, r9d
0x1400a1bcc  lea     edx, [rsi+8]
0x1400a1bcf  mov     ecx, esi
0x1400a1bd1  lea     rbx, [rdi+0D0h]
0x1400a1bd8  cmp     [rbx], r9w
0x1400a1bdc  jz      loc_1400A1F07
0x1400a1be2  mov     eax, cs:dword_140087708
0x1400a1be8  cmp     eax, 4
0x1400a1beb  jbe     short loc_1400A1C25
0x1400a1bed  lea     rcx, dword_140087708
0x1400a1bf4  call    _tlgKeywordOn
0x1400a1bf9  test    al, al
0x1400a1bfb  jz      short loc_1400A1C25
0x1400a1bfd  mov     ecx, 407h
0x1400a1c02  lea     rax, aDiffDisk; "diff disk"
0x1400a1c09  mov     r9d, edx; int
0x1400a1c0c  mov     [rsp+270h+var_250], rax; char *
0x1400a1c11  mov     edx, ecx; int
0x1400a1c13  mov     r8d, 4; int
0x1400a1c19  lea     rcx, aVhdmpicreatene_0; "VhdmpiCreateNewVhd"
0x1400a1c20  call    TraceEvents
0x1400a1c25  xor     eax, eax
0x1400a1c27  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x1400a1c2b  xorps   xmm0, xmm0
0x1400a1c2e  mov     [rbp+170h+var_170], rax
0x1400a1c32  movups  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x1400a1c36  lea     ecx, [rax+3]; ControlCode
0x1400a1c39  call    cs:__imp_EtwActivityIdControl
0x1400a1c40  nop     dword ptr [rax+rax+00h]
0x1400a1c45  mov     r9, [rbp+170h+var_1B0]
0x1400a1c49  mov     eax, cs:dword_1400876D0
0x1400a1c4f  mov     [rbp+170h+var_170], r9
0x1400a1c53  cmp     eax, 4
0x1400a1c56  jbe     short loc_1400A1CB4
0x1400a1c58  mov     edx, 10000h
0x1400a1c5d  lea     rcx, dword_1400876D0
0x1400a1c64  call    _tlgKeywordOn
0x1400a1c69  xor     r8d, r8d
0x1400a1c6c  test    al, al
0x1400a1c6e  jz      short loc_1400A1CAD
0x1400a1c70  mov     r15, qword ptr [rsp+270h+var_220]
0x1400a1c75  lea     r8, [rbp+170h+ActivityId]
0x1400a1c79  lea     rdx, dword_14007CACC
0x1400a1c80  mov     rax, [r15+90h]
0x1400a1c87  mov     rcx, [rax+78h]
0x1400a1c8b  lea     rax, aUnknown; "Unknown"
0x1400a1c92  test    rcx, rcx
0x1400a1c95  cmovnz  rax, rcx
0x1400a1c99  mov     [rbp+170h+var_1D0], rax
0x1400a1c9d  lea     rax, [rbp+170h+var_1D0]
0x1400a1ca1  mov     [rsp+270h+var_250], rax
0x1400a1ca6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1400a1cab  jmp     short loc_1400A1CB9
0x1400a1cad  mov     r15, qword ptr [rsp+270h+var_220]
0x1400a1cb2  jmp     short loc_1400A1CBC
0x1400a1cb4  mov     r15, qword ptr [rsp+270h+var_220]
0x1400a1cb9  xor     r8d, r8d
0x1400a1cbc  mov     r12, [rsp+270h+var_210]
0x1400a1cc1  mov     edx, r8d
0x1400a1cc4  mov     r9d, [rbp+170h+var_1E8]
0x1400a1cc8  mov     al, [rsp+270h+var_208]
0x1400a1ccc  mov     ecx, [r12+4]
0x1400a1cd1  bt      ecx, 1
0x1400a1cd5  cmovb   r9d, r8d
0x1400a1cd9  setb    dl
0x1400a1cdc  neg     al
0x1400a1cde  lea     rax, [rbp+170h+var_1A8]
0x1400a1ce2  mov     [rsp+270h+var_230], rax
0x1400a1ce7  sbb     ecx, ecx
0x1400a1ce9  mov     [rsp+270h+var_238], r9d
0x1400a1cee  and     ecx, 2
0x1400a1cf1  or      ecx, edx
0x1400a1cf3  mov     r9, r15
0x1400a1cf6  mov     rdx, [rbp+170h+var_1B8]
0x1400a1cfa  mov     dword ptr [rsp+270h+var_240], ecx
0x1400a1cfe  mov     rcx, r12
0x1400a1d01  mov     qword ptr [rsp+270h+var_248], r8
0x1400a1d06  mov     r8, rbx
0x1400a1d09  mov     dword ptr [rsp+270h+var_250], 1
0x1400a1d11  call    VhdmpiCreateBackingStoreChain
0x1400a1d16  mov     ebx, eax
0x1400a1d18  test    eax, eax
0x1400a1d1a  jns     short loc_1400A1D5C
0x1400a1d1c  mov     eax, cs:dword_1400876D0
0x1400a1d22  cmp     eax, 2
0x1400a1d25  jbe     short loc_1400A1D5C
0x1400a1d27  mov     edx, 10000h
0x1400a1d2c  lea     rcx, dword_1400876D0
0x1400a1d33  call    _tlgKeywordOn
0x1400a1d38  test    al, al
0x1400a1d3a  jz      short loc_1400A1D5C
0x1400a1d3c  mov     r9, [rbp+170h+var_170]
0x1400a1d40  lea     rax, [rbp+170h+var_1EC]
0x1400a1d44  lea     r8, [rbp+170h+ActivityId]
0x1400a1d48  mov     [rsp+270h+var_250], rax
0x1400a1d4d  lea     rdx, word_14007CB02
0x1400a1d54  mov     dword ptr [rbp+170h+var_1EC], ebx
0x1400a1d57  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400a1d5c  mov     eax, cs:dword_1400876D0
0x1400a1d62  cmp     eax, 4
0x1400a1d65  jbe     short loc_1400A1DC2
0x1400a1d67  mov     edx, 10000h
0x1400a1d6c  lea     rcx, dword_1400876D0
0x1400a1d73  call    _tlgKeywordOn
0x1400a1d78  test    al, al
0x1400a1d7a  jz      short loc_1400A1DC2
0x1400a1d7c  mov     rax, [r15+90h]
0x1400a1d83  lea     r8, [rbp+170h+ActivityId]
0x1400a1d87  mov     r9, [rbp+170h+var_170]
0x1400a1d8b  lea     rdx, byte_14007CA8D
0x1400a1d92  mov     dword ptr [rbp+170h+var_1EC], ebx
0x1400a1d95  mov     rcx, [rax+78h]
0x1400a1d99  lea     rax, aUnknown; "Unknown"
0x1400a1da0  test    rcx, rcx
0x1400a1da3  cmovnz  rax, rcx
0x1400a1da7  mov     [rbp+170h+var_1D0], rax
0x1400a1dab  lea     rax, [rbp+170h+var_1EC]
0x1400a1daf  mov     qword ptr [rsp+270h+var_248], rax; char
0x1400a1db4  lea     rax, [rbp+170h+var_1D0]
0x1400a1db8  mov     [rsp+270h+var_250], rax
0x1400a1dbd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400a1dc2  xor     r9d, r9d
0x1400a1dc5  test    ebx, ebx
0x1400a1dc7  jns     short loc_1400A1E34
0x1400a1dc9  mov     eax, cs:dword_140087708
0x1400a1dcf  cmp     eax, 2
0x1400a1dd2  jbe     short loc_1400A1E26
0x1400a1dd4  lea     r8d, [r9+8]
0x1400a1dd8  mov     edx, r8d
0x1400a1ddb  lea     rcx, dword_140087708
0x1400a1de2  call    _tlgKeywordOn
0x1400a1de7  test    al, al
0x1400a1de9  jz      short loc_1400A1E26
0x1400a1deb  lea     rax, aFailedToOpenPa_0; "Failed to open parent (0x%08x)"
0x1400a1df2  mov     dword ptr [rsp+270h+var_248], ebx; char
0x1400a1df6  mov     r9d, r8d; int
0x1400a1df9  mov     [rsp+270h+var_250], rax; char *
0x1400a1dfe  mov     r8d, 2; int
0x1400a1e04  lea     rcx, aVhdmpicreatene_0; "VhdmpiCreateNewVhd"
0x1400a1e0b  mov     edx, 431h; int
0x1400a1e10  call    TraceEvents
0x1400a1e15  mov     r15, [rbp+170h+var_1A8]
0x1400a1e19  mov     r13, [rsp+270h+Object]
0x1400a1e1e  xor     r9d, r9d
0x1400a1e21  jmp     loc_1400A1FEE
0x1400a1e26  mov     r15, [rbp+170h+var_1A8]
0x1400a1e2a  mov     r13, [rsp+270h+Object]
0x1400a1e2f  jmp     loc_1400A1FEE
0x1400a1e34  mov     r15, [rbp+170h+var_1A8]
0x1400a1e38  cmp     [rdi+107h], r9b
0x1400a1e3f  jz      loc_1400A1EC5
0x1400a1e45  cmp     [rsp+270h+var_208], r9b
0x1400a1e4a  jnz     short loc_1400A1E53
0x1400a1e4c  mov     ebx, 0C000000Dh
0x1400a1e51  jmp     short loc_1400A1E26
0x1400a1e53  lea     rcx, [r12+10h]; struct VHD_SECURITY_CONTEXT *
0x1400a1e58  mov     r8d, 1
0x1400a1e5e  mov     rdx, r15; struct _VHD_BACKING_STORE_HEADER *
0x1400a1e61  call    VhdmpiAcquireRctAccessForBackingStore
0x1400a1e66  xor     r9d, r9d
0x1400a1e69  mov     ebx, eax
0x1400a1e6b  test    eax, eax
0x1400a1e6d  jns     short loc_1400A1EC0
0x1400a1e6f  mov     eax, cs:dword_140087708
0x1400a1e75  cmp     eax, 2
0x1400a1e78  jbe     short loc_1400A1E2A
0x1400a1e7a  lea     r8d, [r9+8]
0x1400a1e7e  mov     edx, r8d
0x1400a1e81  lea     rcx, dword_140087708
0x1400a1e88  call    _tlgKeywordOn
0x1400a1e8d  test    al, al
0x1400a1e8f  jz      short loc_1400A1E2A
0x1400a1e91  lea     rax, aFailedToAcquir; "Failed to acquire parent RCT access (0x"...
0x1400a1e98  mov     dword ptr [rsp+270h+var_248], ebx; char
0x1400a1e9c  mov     r9d, r8d; int
0x1400a1e9f  mov     [rsp+270h+var_250], rax; char *
0x1400a1ea4  mov     r8d, 2; int
0x1400a1eaa  lea     rcx, aVhdmpicreatene_0; "VhdmpiCreateNewVhd"
0x1400a1eb1  mov     edx, 44Ch; int
0x1400a1eb6  call    TraceEvents
0x1400a1ebb  jmp     loc_1400A1E19
0x1400a1ec0  mov     [rsp+270h+var_218], 1
0x1400a1ec5  mov     rax, [r15]
0x1400a1ec8  mov     rcx, r15
0x1400a1ecb  mov     rax, [rax+0A0h]
0x1400a1ed2  call    _guard_dispatch_icall
0x1400a1ed7  mov     [rbp+170h+var_1D0], rax
0x1400a1edb  mov     rax, [r15]
0x1400a1ede  xor     r9d, r9d
0x1400a1ee1  mov     rax, [rax+0F0h]
0x1400a1ee8  test    rax, rax
0x1400a1eeb  jz      short loc_1400A1EFD
0x1400a1eed  mov     rcx, r15
0x1400a1ef0  call    _guard_dispatch_icall
0x1400a1ef5  mov     r12d, eax
0x1400a1ef8  xor     r9d, r9d
0x1400a1efb  jmp     short loc_1400A1F00
0x1400a1efd  mov     r12d, r9d
0x1400a1f00  mov     ecx, [r15+44h]
0x1400a1f04  mov     dword ptr [rbp+170h+var_1EC], ecx
0x1400a1f07  lea     rsi, [rdi+0C0h]
0x1400a1f0e  cmp     [rsi], r9w
0x1400a1f12  jz      loc_1400A250D
0x1400a1f18  mov     eax, cs:dword_140087708
0x1400a1f1e  lea     r13, dword_140087708
0x1400a1f25  mov     r14d, 8
0x1400a1f2b  cmp     eax, 4
0x1400a1f2e  jbe     short loc_1400A1F63
0x1400a1f30  mov     edx, r14d
0x1400a1f33  mov     rcx, r13
0x1400a1f36  call    _tlgKeywordOn
0x1400a1f3b  test    al, al
0x1400a1f3d  jz      short loc_1400A1F63
0x1400a1f3f  lea     rax, aSourceSpecifie; "source specified."
  ... truncated ...
```
