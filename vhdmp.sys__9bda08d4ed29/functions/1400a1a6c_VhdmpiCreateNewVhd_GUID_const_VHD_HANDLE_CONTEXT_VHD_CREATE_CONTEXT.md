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

- `0x1400eb690`

## callees

- `0x1400010d0`
- `0x140001130`
- `0x14001dfd4`
- `0x140023980`
- `0x140025ab8`
- `0x140036284`
- `0x140049d48`
- `0x140049ec8`
- `0x14004a974`
- `0x14004aa08`
- `0x14004dc10`
- `0x14004def0`
- `0x14004e2c8`
- `0x14004e498`
- `0x14004ed68`
- `0x14005dbb0`
- `0x14005dc30`
- `0x14005dce0`
- `0x14005e100`
- `0x1400a19f0`
- `0x1400a1a6c`
- `0x1400a2db4`
- `0x1400a2e80`
- `0x1400a3cd0`
- `0x1400a3e2c`
- `0x1400a3ed4`
- `0x1400cef5c`
- `0x1400cfd88`
- `0x1400d0300`
- `0x1400d036c`
- `0x1400e987c`
- `0x1400ea944`

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
- `0x1400a1deb`: `Failed to open parent (0x%08x)`
- `0x1400a1e91`: `Failed to acquire parent RCT access (0x%08x)`
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
  unsigned __int64 v9; // rdx
  struct _VHD_VIRTUAL_DISK *v10; // rsi
  int v11; // r12d
  unsigned int v12; // r14d
  unsigned int v13; // r13d
  const void *v14; // r8
  unsigned int v15; // edx
  int v16; // r9d
  __int64 v17; // r15
  __int64 v18; // rcx
  const wchar_t *v19; // rax
  struct _VHD_HANDLE_CONTEXT *v20; // r12
  unsigned int v21; // r9d
  int BackingStoreChain; // ebx
  struct _BACKING_STORE_PARSER *v23; // r8
  int v24; // ecx
  __int64 v25; // rax
  const wchar_t *v26; // rcx
  const wchar_t *v27; // rax
  struct _FILE_OBJECT *v28; // r13
  int v29; // eax
  __int64 v30; // r8
  __int64 (__fastcall *v31)(struct _VHD_BACKING_STORE_HEADER *, unsigned __int64, __int64, _QWORD); // rax
  int v32; // eax
  __int64 v33; // r14
  HANDLE v34; // r14
  int v35; // ecx
  __int64 v36; // rcx
  const wchar_t *v37; // rax
  int v39; // eax
  unsigned __int8 (__fastcall *v40)(_QWORD, _QWORD, struct _BACKING_STORE_PARSER *, _QWORD); // rax
  __int64 v41; // rax
  bool v42; // zf
  char v43; // al
  unsigned __int16 v44; // dx
  char *v45; // rax
  unsigned int v46; // r9d
  __int64 (__fastcall *v47)(_QWORD, unsigned __int64, struct _BACKING_STORE_PARSER *, _QWORD); // rax
  __int64 v48; // rax
  int v49; // eax
  int BackingStoreWithMatchingParent; // eax
  struct _FILE_OBJECT *v51; // rsi
  int PhysicalDiskProperties; // eax
  int v53; // eax
  int v54; // eax
  unsigned __int64 v55; // rbx
  unsigned __int64 v56; // r12
  int v57; // eax
  unsigned __int64 v58; // rax
  unsigned __int64 v59; // r14
  unsigned int v60; // esi
  __int64 v61; // rax
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  struct _VHD_BACKING_STORE_HEADER *v64; // rbx
  __int64 v65; // rax
  __int64 v66; // rax
  struct _VHD_BACKING_STORE_HEADER *v67; // rcx
  void (__fastcall *v68)(struct _VHD_BACKING_STORE_HEADER *, _OWORD *); // rax
  int v69; // r8d
  __int64 v70; // rcx
  const wchar_t *v71; // rax
  struct _BACKING_STORE_PARSER *v72; // r12
  int v73; // eax
  unsigned __int16 v74; // dx
  char *v75; // rax
  int RctFiles; // eax
  int v77; // eax
  int v78; // eax
  struct _VHD_BACKING_STORE_HEADER *v79; // rcx
  unsigned int v80; // eax
  unsigned __int64 v81; // rdx
  int v82; // eax
  char *v83; // r8
  struct _VHD_BACKING_STORE_HEADER *v84; // rdi
  int v85; // eax
  int v86; // [rsp+20h] [rbp-E0h]
  char v87[8]; // [rsp+28h] [rbp-D8h]
  char v88[8]; // [rsp+50h] [rbp-B0h]
  char v89; // [rsp+58h] [rbp-A8h]
  char v91[8]; // [rsp+68h] [rbp-98h] BYREF
  PVOID Object; // [rsp+70h] [rbp-90h] BYREF
  struct _VHD_VIRTUAL_DISK *v93; // [rsp+78h] [rbp-88h] BYREF
  char v94; // [rsp+80h] [rbp-80h]
  char v95; // [rsp+81h] [rbp-7Fh]
  char v96; // [rsp+82h] [rbp-7Eh]
  char v97; // [rsp+83h] [rbp-7Dh]
  char v98[4]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v99; // [rsp+88h] [rbp-78h] BYREF
  struct _VHD_BACKING_STORE_HEADER *v100; // [rsp+90h] [rbp-70h]
  unsigned __int64 v101; // [rsp+98h] [rbp-68h]
  __int64 v102; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v103; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v104; // [rsp+ACh] [rbp-54h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp-50h] BYREF
  struct _BACKING_STORE_PARSER *v106; // [rsp+B8h] [rbp-48h]
  const struct _GUID *v107; // [rsp+C0h] [rbp-40h] BYREF
  struct _VHD_BACKING_STORE_HEADER *v108; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v109; // [rsp+D0h] [rbp-30h] BYREF
  GUID v110; // [rsp+D8h] [rbp-28h] BYREF
  const struct _GUID *v111; // [rsp+E8h] [rbp-18h]
  GUID ActivityId; // [rsp+F0h] [rbp-10h] BYREF
  const struct _GUID *v113; // [rsp+100h] [rbp+0h]
  _OWORD v114[10]; // [rsp+110h] [rbp+10h] BYREF
  __int128 Buf1; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 Buf2; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v117[96]; // [rsp+1D0h] [rbp+D0h] BYREF

  v107 = a1;
  v91[0] = 0;
  v99 = 0;
  memset(v117, 0, sizeof(v117));
  memset(v114, 0, sizeof(v114));
  v111 = 0;
  v110 = 0;
  VhdmpiGetBackingStoreChainAccessProperties(a2, 1, v91, &v99);
  v5 = *((_QWORD *)a3 + 40);
  v6 = 0;
  v108 = 0;
  *(_QWORD *)&Buf1 = 0;
  v7 = 0;
  *(_QWORD *)&Buf2 = 0;
  v8 = 0;
  v101 = 0;
  v9 = 8;
  v109 = 0;
  v10 = 0;
  v11 = 0;
  v100 = *(struct _VHD_BACKING_STORE_HEADER **)(v5 + 144);
  v12 = 0;
  v89 = 0;
  v13 = 0;
  v93 = 0;
  v106 = *(struct _BACKING_STORE_PARSER **)v100;
  Handle = 0;
  Object = 0;
  v96 = 0;
  v94 = 0;
  v102 = 0;
  *(_QWORD *)v88 = v5;
  *(_DWORD *)v98 = 0;
  v95 = 0;
  v103 = 0;
  v104 = 0;
  v97 = 0;
  if ( (unsigned int)dword_1400876D0 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    {
      TraceEvents("VhdmpiCreateNewVhd", 0x3FAu, 4u, v9, "Virtual disk: 0x%p Context: 0x%p", v14, a3);
      v6 = 0;
      v9 = 8;
    }
    v7 = 0;
  }
  if ( *((_WORD *)a3 + 104) == (_WORD)v6 )
    goto LABEL_46;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, v9) )
    TraceEvents("VhdmpiCreateNewVhd", 0x407u, 4u, v15, "diff disk");
  v113 = 0;
  ActivityId = 0;
  EtwActivityIdControl(3u, &ActivityId);
  v113 = v107;
  if ( (unsigned int)dword_140087708 <= 4 )
  {
    v17 = *(_QWORD *)v88;
  }
  else if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    v17 = *(_QWORD *)v88;
    v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v88 + 144LL) + 120LL);
    v19 = L"Unknown";
    if ( v18 )
      v19 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)v88 + 144LL) + 120LL);
    v102 = (__int64)v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v18,
      (unsigned int)&dword_14007CAF4,
      (unsigned int)&ActivityId,
      v16,
      (__int64)&v102);
  }
  else
  {
    v17 = *(_QWORD *)v88;
  }
  v20 = a2;
  v21 = v99;
  if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
    v21 = 0;
  BackingStoreChain = VhdmpiCreateBackingStoreChain(
                        a2,
                        v106,
                        (struct _UNICODE_STRING *)a3 + 13,
                        v17,
                        1,
                        0,
                        ((*((_DWORD *)a2 + 1) & 2) != 0) | (unsigned __int8)(v91[0] != 0 ? 2 : 0),
                        v21,
                        (__int64 *)&v108);
  if ( BackingStoreChain < 0
    && (unsigned int)dword_140087708 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    *(_DWORD *)v98 = BackingStoreChain;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v24,
      (unsigned int)byte_14007CA8D,
      (unsigned int)&ActivityId,
      (_DWORD)v113,
      (__int64)v98);
  }
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    v25 = *(_QWORD *)(v17 + 144);
    *(_DWORD *)v98 = BackingStoreChain;
    v26 = *(const wchar_t **)(v25 + 120);
    v27 = L"Unknown";
    if ( v26 )
      v27 = v26;
    v102 = (__int64)v27;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v26,
      (unsigned int)byte_14007CAB5,
      (unsigned int)&ActivityId,
      (_DWORD)v113,
      (__int64)&v102,
      (__int64)v98);
  }
  v6 = 0;
  if ( BackingStoreChain >= 0 )
  {
    v8 = v108;
    if ( *((_BYTE *)a3 + 263) )
    {
      if ( !v91[0] )
      {
        BackingStoreChain = -1073741811;
LABEL_32:
        v8 = v108;
        goto LABEL_33;
      }
      v29 = VhdmpiAcquireRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16), v108);
      v6 = 0;
      BackingStoreChain = v29;
      if ( v29 < 0 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        {
          TraceEvents(
            "VhdmpiCreateNewVhd",
            0x44Cu,
            2u,
            (unsigned int)v23,
            "Failed to acquire parent RCT access (0x%08x)",
            BackingStoreChain);
          goto LABEL_31;
        }
LABEL_33:
        v28 = (struct _FILE_OBJECT *)Object;
        goto LABEL_61;
      }
      v89 = 1;
    }
    v102 = (*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, unsigned __int64, struct _BACKING_STORE_PARSER *, _QWORD))(*(_QWORD *)v8 + 160LL))(
             v8,
             v9,
             v23,
             0);
    v6 = 0;
    v31 = *(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, unsigned __int64, __int64, _QWORD))(*(_QWORD *)v8 + 240LL);
    if ( v31 )
    {
      v11 = v31(v8, v9, v30, 0);
      v6 = 0;
    }
    else
    {
      v11 = 0;
    }
    v7 = *((_DWORD *)v8 + 17);
    *(_DWORD *)v98 = v7;
LABEL_46:
    if ( *((_WORD *)a3 + 96) == (_WORD)v6 )
    {
      v23 = v106;
    }
    else
    {
      if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        TraceEvents("VhdmpiCreateNewVhd", 0x468u, 4u, 8u, "source specified.");
      v32 = VhdmpiTryOpenPhysicalDisk((const struct _UNICODE_STRING *)a3 + 12, &Handle, (struct _FILE_OBJECT **)&Object);
      v6 = 0;
      BackingStoreChain = v32;
      if ( v32 < 0 )
        goto LABEL_58;
      if ( Handle )
      {
        if ( *((_DWORD *)a3 + 44) == 2 )
        {
          if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
            goto LABEL_57;
          TraceEvents("VhdmpiCreateNewVhd", 0x4D8u, 2u, 8u, "parent with physical source is not valid!");
LABEL_56:
          v6 = 0;
LABEL_57:
          BackingStoreChain = -1073741811;
LABEL_58:
          v10 = v93;
LABEL_59:
          v28 = (struct _FILE_OBJECT *)Object;
LABEL_60:
          v20 = a2;
          goto LABEL_61;
        }
        if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          TraceEvents("VhdmpiCreateNewVhd", 0x4E0u, 4u, 8u, "source is not a file...");
        v51 = (struct _FILE_OBJECT *)Object;
        PhysicalDiskProperties = VhdmpiGetPhysicalDiskProperties((PFILE_OBJECT)Object, &v109, &v103, &v104);
        v6 = 0;
        BackingStoreChain = PhysicalDiskProperties;
        if ( PhysicalDiskProperties < 0 )
          goto LABEL_58;
        if ( *((_BYTE *)a3 + 260) )
        {
          v53 = VhdmpiTakePhysicalDiskOwnership(v51, (struct VHD_DISK_OWNERSHIP *)v117);
          v10 = v93;
          v6 = 0;
          BackingStoreChain = v53;
          if ( v53 < 0 )
            goto LABEL_59;
          v94 = 1;
        }
        else
        {
          v10 = v93;
        }
        v13 = v104;
        v12 = v103;
        v101 = v109;
      }
      else
      {
        v9 = *((_QWORD *)a3 + 23);
        if ( !v9 )
        {
          if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
            goto LABEL_57;
          TraceEvents("VhdmpiCreateNewVhd", 0x47Au, 2u, 8u, "Failed to find parser");
          goto LABEL_56;
        }
        v39 = VhdmpiOpenSourceVirtualDisk(
                a2,
                (const struct _BACKING_STORE_PARSER *)v9,
                (const struct _UNICODE_STRING *)a3 + 12,
                &v93);
        v6 = 0;
        BackingStoreChain = v39;
        if ( v39 < 0 )
          goto LABEL_58;
        v10 = v93;
        if ( *((_BYTE *)a3 + 280)
          || (v40 = *(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, struct _BACKING_STORE_PARSER *, _QWORD))(*((_QWORD *)a3 + 23) + 560LL)) != 0
          && v40(*((_QWORD *)v93 + 18), 0, v23, 0) )
        {
          if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
            TraceEvents(
              "VhdmpiCreateNewVhd",
              0x495u,
              2u,
              8u,
              "Conversion to or from a PMEM-compatible disk is not supported");
          BackingStoreChain = -1073741637;
          goto LABEL_118;
        }
        v41 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, struct _BACKING_STORE_PARSER *, __int64))(*((_QWORD *)a3 + 23) + 160LL))(
                *((_QWORD *)v10 + 18),
                v9,
                v23,
                v6);
        v42 = *((_DWORD *)a3 + 44) == 2;
        v101 = v41;
        if ( v42 )
        {
          v43 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a3 + 23) + 112LL))(*((_QWORD *)v10 + 18));
          v6 = 0;
          if ( !v43 && !*((_BYTE *)a3 + 262) )
          {
            if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
              goto LABEL_101;
            v44 = 1187;
            v45 = "parent with non-diff source is not valid!";
            v46 = 8;
LABEL_100:
            TraceEvents("VhdmpiCreateNewVhd", v44, 2u, v46, v45);
            v6 = 0;
LABEL_101:
            BackingStoreChain = -1073741811;
            goto LABEL_59;
          }
        }
        else
        {
          v6 = 0;
        }
        v47 = *(__int64 (__fastcall **)(_QWORD, unsigned __int64, struct _BACKING_STORE_PARSER *, _QWORD))(*((_QWORD *)a3 + 23) + 240LL);
        if ( v47 )
        {
          v12 = v47(*((_QWORD *)v10 + 18), v9, v23, 0);
          v6 = 0;
        }
        else
        {
          v12 = 0;
        }
        v48 = *((_QWORD *)v10 + 18);
        v13 = *(_DWORD *)(v48 + 68);
        if ( *((_DWORD *)a3 + 44) == 2 )
        {
          if ( *((_BYTE *)a3 + 262) )
          {
            v49 = VhdmpiAcquireRctAccessForChain(
                    (struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16),
                    *((struct _VHD_BACKING_STORE_HEADER **)v10 + 18));
            v6 = 0;
            BackingStoreChain = v49;
            if ( v49 < 0 )
              goto LABEL_59;
            v95 = 1;
          }
          else
          {
            v9 = (unsigned __int64)a3 + 224;
            if ( *((_WORD *)a3 + 112) )
            {
              BackingStoreWithMatchingParent = VhdmpiFindBackingStoreWithMatchingParent(
                                                 v10,
                                                 (const struct _UNICODE_STRING *)v9,
                                                 (struct _VHD_BACKING_STORE_HEADER **)&Buf2);
              v6 = 0;
              BackingStoreChain = BackingStoreWithMatchingParent;
              if ( BackingStoreWithMatchingParent < 0 )
                goto LABEL_59;
              v48 = Buf2;
            }
            *(_QWORD *)&Buf1 = v48;
          }
        }
      }
      v23 = v106;
      if ( v12 == 4096 && v106 == (struct _BACKING_STORE_PARSER *)&Vhd1Parser )
      {
        BackingStoreChain = -1073741811;
        if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          goto LABEL_59;
        TraceEvents(
          "VhdmpiCreateNewVhd",
          0x50Du,
          2u,
          (unsigned int)v23,
          "source LogicalSectorSize is not supported by VHD1");
        goto LABEL_118;
      }
      v7 = *(_DWORD *)v98;
    }
    if ( *((_BYTE *)a3 + 280) != (_BYTE)v6 )
    {
      if ( *((_DWORD *)a3 + 62) == (_DWORD)v6 )
        *((_DWORD *)a3 + 62) = 4096;
      if ( *((_DWORD *)a3 + 63) == (_DWORD)v6 )
        *((_DWORD *)a3 + 63) = 4096;
    }
    v54 = *((_DWORD *)a3 + 62);
    if ( !v54 )
    {
      if ( v12 )
      {
        if ( v11 && v12 != v11 )
        {
          BackingStoreChain = -1073741811;
          if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
            goto LABEL_58;
          TraceEvents(
            "VhdmpiCreateNewVhd",
            0x52Eu,
            2u,
            (unsigned int)v23,
            "source LogicalSectorSize does not match parent");
          goto LABEL_152;
        }
        *((_DWORD *)a3 + 62) = v12;
      }
      else
      {
        v57 = 512;
        if ( v11 )
          v57 = v11;
        *((_DWORD *)a3 + 62) = v57;
      }
LABEL_154:
      v55 = *((_QWORD *)a3 + 30);
      v10 = v93;
      if ( v55 )
      {
        v58 = v101;
      }
      else
      {
        if ( !v93 )
        {
          v34 = Handle;
          if ( !Handle )
          {
            if ( !v8 )
            {
              v28 = (struct _FILE_OBJECT *)Object;
              BackingStoreChain = -1073741811;
              goto LABEL_67;
            }
            v56 = v102;
            *((_QWORD *)a3 + 30) = v102;
            v55 = v56;
            goto LABEL_183;
          }
        }
        v58 = v101;
        *((_QWORD *)a3 + 30) = v101;
        v55 = v58;
      }
      v34 = Handle;
      if ( (v10 || Handle) && v58 > v55 )
      {
        if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          goto LABEL_101;
        v44 = 1398;
        v45 = "source is too big for VHD";
LABEL_181:
        v46 = (unsigned int)v23;
        goto LABEL_100;
      }
      v56 = v102;
LABEL_183:
      if ( v8 && (v10 || v34) )
      {
        v59 = v101;
        if ( v101 != v55 )
        {
          if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
            goto LABEL_101;
          v44 = 1410;
          v45 = "source doesn't match new VHD in diff-to-diff";
          goto LABEL_181;
        }
      }
      else
      {
        v59 = v101;
      }
      v60 = *((_DWORD *)a3 + 62);
      v9 = v55 % v60;
      if ( v9 )
        goto LABEL_57;
      if ( *((_DWORD *)a3 + 63) )
      {
        v13 = *((_DWORD *)a3 + 63);
        goto LABEL_200;
      }
      if ( *((_DWORD *)v23 + 6) == (_DWORD)v6 )
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
      v13 = *((_DWORD *)v23 + 7);
LABEL_196:
      *((_DWORD *)a3 + 63) = v13;
LABEL_200:
      memset(v114, 0, sizeof(v114));
      LODWORD(v114[0]) = *((_DWORD *)a3 + 44);
      DWORD1(v114[0]) = *((_DWORD *)a3 + 64);
      LODWORD(v114[8]) = *((_DWORD *)a3 + 74);
      v61 = *((_QWORD *)a3 + 38);
      *((_QWORD *)&v114[0] + 1) = __PAIR64__(v13, v60);
      v10 = v93;
      *((_QWORD *)&v114[8] + 1) = v61;
      v62 = *(_OWORD *)((char *)a3 + 264);
      v63 = *(_OWORD *)((char *)a3 + 280);
      v114[1] = v62;
      v114[7] = v63;
      if ( !v8 || v93 || (*(_QWORD *)&v114[3] = v56, v55 <= v56) )
        *(_QWORD *)&v114[3] = v55;
      *((_QWORD *)&v114[3] + 1) = v8;
      if ( !*((_BYTE *)a3 + 261) )
      {
        if ( v93 )
          *(_QWORD *)&v114[4] = *((_QWORD *)v93 + 18);
        else
          *(_QWORD *)&v114[4] = v8;
      }
      v28 = (struct _FILE_OBJECT *)Object;
      *(_QWORD *)&v114[6] = Object;
      *((_QWORD *)&v114[4] + 1) = Buf1;
      *((_QWORD *)&v114[5] + 1) = v93;
      *((_QWORD *)&v114[6] + 1) = v59;
      if ( *((_BYTE *)a3 + 262) )
        *(_QWORD *)&v114[5] = (char *)a3 + 224;
      v114[2] = v62;
      if ( *((_BYTE *)v106 + 52) )
      {
        if ( v93 )
        {
          v64 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v93 + 18);
          v65 = *(_QWORD *)v64;
          if ( v8 )
          {
            Buf1 = 0;
            Buf2 = 0;
            (*(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, __int128 *, _QWORD))(v65 + 200))(v64, &Buf1, 0);
            (*(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, __int128 *))(*(_QWORD *)v8 + 216LL))(v8, &Buf2);
            if ( !memcmp(&Buf1, &Buf2, 0x10u) )
            {
              v66 = *(_QWORD *)v64;
              v67 = v64;
LABEL_223:
              v68 = *(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, _OWORD *))(v66 + 216);
              goto LABEL_224;
            }
            if ( (unsigned int)dword_1400876D0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 1) )
              TraceEvents("VhdmpiCreateNewVhd", 0x613u, 3u, 1u, "Attaching a virtual disk to an incompatible parent.");
          }
          else
          {
            v68 = *(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, _OWORD *))(v65 + 216);
            if ( v68 )
            {
              v67 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v93 + 18);
LABEL_224:
              v68(v67, &v114[2]);
            }
          }
        }
        else if ( v8 && v55 >= v56 )
        {
          v66 = *(_QWORD *)v8;
          v67 = v8;
          goto LABEL_223;
        }
      }
      EtwActivityIdControl(3u, &v110);
      v111 = v107;
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
      {
        v70 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v88 + 144LL) + 120LL);
        v71 = L"Unknown";
        if ( v70 )
          v71 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)v88 + 144LL) + 120LL);
        v107 = (const struct _GUID *)v71;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v70,
          (unsigned int)byte_14007CA4B,
          (unsigned int)&v110,
          v69,
          (__int64)&v107);
      }
      v72 = v106;
      v114[9] = v110;
      v97 = 1;
      v73 = (*((__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, char *, _OWORD *, _QWORD))v106 + 21))(
              v100,
              (char *)a3 + 96,
              v114,
              0);
      v6 = 0;
      BackingStoreChain = v73;
      if ( v73 < 0 )
      {
        if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          goto LABEL_60;
        v74 = 1607;
        v75 = "VHD initialization failed(0x%08x).";
        goto LABEL_234;
      }
      if ( v89 && (unsigned __int8)VhdmpiIsRctEnabled(v8, v9) )
      {
        RctFiles = VhdmpiCreateRctFiles(v100);
        v6 = 0;
        BackingStoreChain = RctFiles;
        if ( RctFiles < 0 )
          goto LABEL_60;
        v96 = 1;
        v77 = VhdmpiAcquireRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16), v100);
        v6 = 0;
        BackingStoreChain = v77;
        if ( v77 < 0 )
        {
          v10 = v93;
          goto LABEL_60;
        }
        BackingStoreChain = VhdmpiPopulateRctFiles(*((struct VHD_RCT_STATE **)v100 + 227), 1, *((_QWORD *)v8 + 227));
        if ( BackingStoreChain >= 0 && *(_QWORD *)&v114[3] < *((_QWORD *)a3 + 30) )
          BackingStoreChain = VhdmpiResizeRctFile(*((struct VHD_RCT_STATE **)v100 + 227));
        VhdmpiReleaseRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16), v100);
        v10 = v93;
        v6 = 0;
        if ( BackingStoreChain < 0 )
          goto LABEL_60;
      }
      else
      {
        VhdmpiDeleteRctFiles((char *)v100 + 72, v9, v23, v6);
      }
      v78 = VhdmpiInitAndLoadAndVerifyBackingStore(v100, 2);
      v6 = 0;
      BackingStoreChain = v78;
      if ( v78 < 0 )
      {
        if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          goto LABEL_60;
        v74 = 1692;
        v75 = "failed to finalize initialization of backing store information (0x%08x).";
LABEL_234:
        *(_DWORD *)v87 = BackingStoreChain;
        TraceEvents("VhdmpiCreateNewVhd", v74, 2u, (unsigned int)v23, v75, *(_QWORD *)v87);
        goto LABEL_119;
      }
      v79 = v100;
      v80 = *((_DWORD *)v100 + 16);
      *(_DWORD *)(*(_QWORD *)v88 + 72LL) = v80;
      _BitScanForward(&v80, v80);
      *(_DWORD *)(*(_QWORD *)v88 + 76LL) = v80;
      v81 = *((_QWORD *)a3 + 30);
      if ( *(_QWORD *)&v114[3] < v81 )
      {
        v82 = (*((__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, unsigned __int64, struct _BACKING_STORE_PARSER *, _QWORD))v72
               + 42))(
                v79,
                v81,
                v23,
                0);
        v6 = 0;
        BackingStoreChain = v82;
        if ( v82 < 0 )
        {
          v33 = *(_QWORD *)v88;
          goto LABEL_268;
        }
        *(_QWORD *)&v114[3] = *((_QWORD *)a3 + 30);
      }
      v33 = *(_QWORD *)v88;
      v83 = (char *)a3 + 96;
      v84 = v100;
      LOBYTE(v86) = 1;
      v85 = (*((__int64 (__fastcall **)(char *, struct _VHD_BACKING_STORE_HEADER *, char *, _OWORD *, int))v72 + 23))(
              *(char **)v88,
              v100,
              v83,
              v114,
              v86);
      v6 = 0;
      BackingStoreChain = v85;
      if ( v85 >= 0 )
      {
        v20 = a2;
        if ( v8 )
        {
          if ( v89 )
          {
            VhdmpiReleaseRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16), v8);
            v6 = 0;
            v89 = 0;
          }
          if ( (*((_DWORD *)a2 + 1) & 2) == 0 )
          {
            VhdmpiAttachParentBackingStoreChain(v84, v8);
            v6 = 0;
            v8 = 0;
          }
          *((_DWORD *)v84 + 291) = 2;
        }
        if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        {
          TraceEvents(
            "VhdmpiCreateNewVhd",
            0x6F7u,
            4u,
            (unsigned int)v23,
            "new VHD 0x%p successfully created",
            *(const void **)v88);
          v6 = 0;
        }
        BackingStoreChain = v6;
        goto LABEL_62;
      }
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      {
        TraceEvents(
          "VhdmpiCreateNewVhd",
          0x6CCu,
          2u,
          (unsigned int)v23,
          "VHD final initialization failed(0x%08x).",
          BackingStoreChain);
        v20 = a2;
        v6 = 0;
        goto LABEL_62;
      }
LABEL_268:
      v20 = a2;
      goto LABEL_62;
    }
    if ( !v12 || v54 == v12 )
    {
      if ( !v11 || v54 == v11 )
        goto LABEL_154;
      BackingStoreChain = -1073741811;
      if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        goto LABEL_58;
      TraceEvents("VhdmpiCreateNewVhd", 0x556u, 2u, (unsigned int)v23, "child LogicalSectorSize does not match parent");
    }
    else
    {
      BackingStoreChain = -1073741811;
      if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        goto LABEL_58;
      TraceEvents(
        "VhdmpiCreateNewVhd",
        0x547u,
        2u,
        (unsigned int)v23,
        "destination LogicalSectorSize does not match source");
    }
LABEL_152:
    v10 = v93;
LABEL_118:
    v28 = (struct _FILE_OBJECT *)Object;
LABEL_119:
    v6 = 0;
    goto LABEL_60;
  }
  if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    goto LABEL_32;
  TraceEvents("VhdmpiCreateNewVhd", 0x431u, 2u, (unsigned int)v23, "Failed to open parent (0x%08x)", BackingStoreChain);
  v8 = v108;
LABEL_31:
  v28 = (struct _FILE_OBJECT *)Object;
  v6 = 0;
LABEL_61:
  v33 = *(_QWORD *)v88;
LABEL_62:
  if ( v8 )
  {
    if ( v89 != (_BYTE)v6 )
      VhdmpiReleaseRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)v20 + 16), v8);
    LOBYTE(v6) = v91[0];
    VhdmpiReleaseBackingStoreChainAccess((_DWORD)v20, (_DWORD)v8, -1, v6, v99);
    VhdmpiReleaseBackingStoreChain(v8, v33);
    v6 = 0;
  }
  v34 = Handle;
LABEL_67:
  if ( v94 != (_BYTE)v6 )
  {
    VhdmpiReleasePhysicalDiskOwnership(v28, (struct VHD_DISK_OWNERSHIP *)v117);
    v6 = 0;
  }
  if ( Object )
  {
    ObfDereferenceObject(Object);
    v6 = 0;
  }
  if ( v34 )
  {
    ZwClose(v34);
    v6 = 0;
  }
  if ( v10 )
  {
    if ( v95 != (_BYTE)v6 )
      VhdmpiReleaseRctAccessForChain(
        (struct _VHD_HANDLE_CONTEXT *)((char *)a2 + 16),
        *((struct _VHD_BACKING_STORE_HEADER **)v10 + 18));
    VhdmpiCloseSourceVirtualDisk(a2, v10);
    v6 = 0;
  }
  if ( v96 != (_BYTE)v6 )
  {
    VhdmpiDeleteRctFiles((char *)v100 + 72, v9, v23, v6);
    LOBYTE(v6) = 0;
  }
  if ( v97 != (_BYTE)v6 )
  {
    if ( BackingStoreChain < 0
      && (unsigned int)dword_140087708 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
    {
      v99 = BackingStoreChain;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v35,
        (unsigned int)byte_14007CA23,
        (unsigned int)&v110,
        (_DWORD)v111,
        (__int64)&v99);
    }
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
    {
      v99 = BackingStoreChain;
      v36 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v88 + 144LL) + 120LL);
      v37 = L"Unknown";
      if ( v36 )
        v37 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)v88 + 144LL) + 120LL);
      v107 = (const struct _GUID *)v37;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v36,
        (unsigned int)&unk_14007C9D8,
        (unsigned int)&v110,
        (_DWORD)v111,
        (__int64)&v107,
        (__int64)&v99);
    }
  }
  return (unsigned int)BackingStoreChain;
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
0x1400a1b51  mov     eax, cs:dword_1400876D0
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
0x1400a1b89  lea     rcx, dword_1400876D0
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
0x1400a1be2  mov     eax, cs:dword_1400876D0
0x1400a1be8  cmp     eax, 4
0x1400a1beb  jbe     short loc_1400A1C25
0x1400a1bed  lea     rcx, dword_1400876D0
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
0x1400a1c49  mov     eax, cs:dword_140087708
0x1400a1c4f  mov     [rbp+170h+var_170], r9
0x1400a1c53  cmp     eax, 4
0x1400a1c56  jbe     short loc_1400A1CB4
0x1400a1c58  mov     edx, 10000h
0x1400a1c5d  lea     rcx, dword_140087708
0x1400a1c64  call    _tlgKeywordOn
0x1400a1c69  xor     r8d, r8d
0x1400a1c6c  test    al, al
0x1400a1c6e  jz      short loc_1400A1CAD
0x1400a1c70  mov     r15, qword ptr [rsp+270h+var_220]
0x1400a1c75  lea     r8, [rbp+170h+ActivityId]
0x1400a1c79  lea     rdx, dword_14007CAF4
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
0x1400a1d1c  mov     eax, cs:dword_140087708
0x1400a1d22  cmp     eax, 2
0x1400a1d25  jbe     short loc_1400A1D5C
0x1400a1d27  mov     edx, 10000h
0x1400a1d2c  lea     rcx, dword_140087708
0x1400a1d33  call    _tlgKeywordOn
0x1400a1d38  test    al, al
0x1400a1d3a  jz      short loc_1400A1D5C
0x1400a1d3c  mov     r9, [rbp+170h+var_170]
0x1400a1d40  lea     rax, [rbp+170h+var_1EC]
0x1400a1d44  lea     r8, [rbp+170h+ActivityId]
0x1400a1d48  mov     [rsp+270h+var_250], rax
0x1400a1d4d  lea     rdx, byte_14007CA8D
0x1400a1d54  mov     dword ptr [rbp+170h+var_1EC], ebx
0x1400a1d57  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400a1d5c  mov     eax, cs:dword_140087708
0x1400a1d62  cmp     eax, 4
0x1400a1d65  jbe     short loc_1400A1DC2
0x1400a1d67  mov     edx, 10000h
0x1400a1d6c  lea     rcx, dword_140087708
0x1400a1d73  call    _tlgKeywordOn
0x1400a1d78  test    al, al
0x1400a1d7a  jz      short loc_1400A1DC2
0x1400a1d7c  mov     rax, [r15+90h]
0x1400a1d83  lea     r8, [rbp+170h+ActivityId]
0x1400a1d87  mov     r9, [rbp+170h+var_170]
0x1400a1d8b  lea     rdx, byte_14007CAB5
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
0x1400a1dc9  mov     eax, cs:dword_1400876D0
0x1400a1dcf  cmp     eax, 2
0x1400a1dd2  jbe     short loc_1400A1E26
0x1400a1dd4  lea     r8d, [r9+8]
0x1400a1dd8  mov     edx, r8d
0x1400a1ddb  lea     rcx, dword_1400876D0
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
0x1400a1e6f  mov     eax, cs:dword_1400876D0
0x1400a1e75  cmp     eax, 2
0x1400a1e78  jbe     short loc_1400A1E2A
0x1400a1e7a  lea     r8d, [r9+8]
0x1400a1e7e  mov     edx, r8d
0x1400a1e81  lea     rcx, dword_1400876D0
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
0x1400a1f18  mov     eax, cs:dword_1400876D0
0x1400a1f1e  lea     r13, dword_1400876D0
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
