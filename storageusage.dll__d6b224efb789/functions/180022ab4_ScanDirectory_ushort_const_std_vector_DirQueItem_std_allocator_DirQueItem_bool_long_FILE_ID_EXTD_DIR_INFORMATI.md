# ScanDirectory(ushort const *,std::vector<DirQueItem,std::allocator<DirQueItem>>,bool,long (*)(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool),DIRECTORY_SCAN_FUNC_ARGS *,void *)

- ea: `0x180022ab4`
- end: `0x1800238bb`
- name: `?ScanDirectory@@YAJPEBGV?$vector@UDirQueItem@@V?$allocator@UDirQueItem@@@std@@@std@@_NP6AJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@2@Z4PEAX@Z`
- size: `3591`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b6b4`
- `0x1800227a4`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x18000eab8`
- `0x180015bac`
- `0x180016f30`
- `0x18001c940`
- `0x18001f050`
- `0x18001f218`
- `0x180020104`
- `0x18002016c`
- `0x18002054c`
- `0x18002057c`
- `0x180020b5c`
- `0x180020bc0`
- `0x180022684`
- `0x180022ab4`
- `0x1800238c4`
- `0x180023944`
- `0x180023aa4`
- `0x180023cdc`
- `0x180023e3c`
- `0x180024150`
- `0x18002415c`
- `0x180024178`
- `0x18002af30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023753`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002387d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023753`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002387d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022bc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002372a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002386e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022bc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002372a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002386e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022bd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022bd3`
- `ntdll!NtQueryDirectoryFile` at `0x1800231d3`
- `ntdll!NtQueryDirectoryFile` at `0x1800231d3`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180022f0c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180022f0c`
- `ntdll!NtCreateFile` at `0x180022fa8`
- `ntdll!NtCreateFile` at `0x180022fa8`
- `ntdll!NtClose` at `0x180023767`
- `ntdll!NtClose` at `0x180023852`
- `ntdll!NtClose` at `0x180023767`
- `ntdll!NtClose` at `0x180023852`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ScanDirectory(
        const unsigned __int16 *a1,
        _QWORD *a2,
        char a3,
        __int64 (__fastcall *a4)(struct _FILE_ID_EXTD_DIR_INFORMATION *, struct DIRECTORY_SCAN_FUNC_ARGS *, __int64, __int64),
        __int64 a5,
        __int64 a6)
{
  _QWORD *v7; // rdi
  const unsigned __int16 *v8; // r14
  __int64 v9; // r15
  int v10; // esi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v12; // rdx
  __int64 v13; // r11
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int16 *v19; // rcx
  wchar_t *v20; // rax
  __int64 v21; // rdx
  char *v22; // rcx
  unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  char *v25; // rbx
  unsigned __int16 *v26; // rcx
  wchar_t *v27; // rax
  __int64 v28; // rdx
  _OWORD *v29; // rax
  wchar_t *v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // r13d
  signed int v33; // eax
  int v34; // eax
  __int16 v35; // ax
  __int16 v36; // ax
  _OWORD *v37; // rax
  _OWORD *v38; // r8
  unsigned __int16 *v39; // rcx
  __int64 v40; // rdx
  _OWORD *v41; // rax
  wchar_t *v42; // rcx
  __int64 v43; // rdx
  __int16 v44; // ax
  NTSTATUS v45; // eax
  __int64 v46; // r9
  unsigned int Information; // r14d
  int v48; // r15d
  unsigned __int16 *v49; // rcx
  wchar_t *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r9
  char *v53; // rdi
  unsigned int v54; // ecx
  unsigned __int64 v55; // rbx
  int v56; // r9d
  __int16 *v57; // rdi
  __int64 v58; // rdx
  unsigned __int16 *v59; // r8
  __int16 v60; // ax
  unsigned __int16 *v61; // rcx
  int v62; // edx
  int v63; // edx
  int v64; // eax
  __int64 v65; // rdx
  unsigned __int64 v66; // rax
  unsigned __int64 v67; // rbx
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rdi
  __int64 v71; // rbx
  __int64 v72; // rax
  __int64 v73; // rcx
  int v74; // eax
  int v75; // eax
  _OWORD *v76; // rcx
  unsigned __int16 *v77; // rax
  __int64 v78; // rdx
  char *v79; // rcx
  unsigned __int16 *v80; // rax
  __int64 v81; // rdx
  __int64 v82; // r8
  __int64 v83; // r9
  PVOID v84; // rbx
  HANDLE v85; // rax
  HANDLE v86; // rax
  unsigned int v87; // ebx
  HANDLE v89; // rax
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-E0h]
  signed int v91; // [rsp+60h] [rbp-A0h] BYREF
  struct DIRECTORY_SCAN_FUNC_ARGS *v92; // [rsp+68h] [rbp-98h] BYREF
  bool v93; // [rsp+70h] [rbp-90h] BYREF
  char v94; // [rsp+71h] [rbp-8Fh] BYREF
  struct _FILE_ID_EXTD_DIR_INFORMATION *v95; // [rsp+78h] [rbp-88h] BYREF
  PVOID FileInformation; // [rsp+80h] [rbp-80h]
  _QWORD *v97; // [rsp+88h] [rbp-78h]
  int v98; // [rsp+90h] [rbp-70h]
  __int128 v99; // [rsp+98h] [rbp-68h] BYREF
  __int128 v100; // [rsp+A8h] [rbp-58h]
  __int64 v101; // [rsp+B8h] [rbp-48h]
  int v102; // [rsp+C0h] [rbp-40h]
  __int64 (__fastcall *v103)(struct _FILE_ID_EXTD_DIR_INFORMATION *, struct DIRECTORY_SCAN_FUNC_ARGS *, __int64, __int64); // [rsp+C8h] [rbp-38h]
  void *FileHandle; // [rsp+D0h] [rbp-30h] BYREF
  ULONG CreateOptions; // [rsp+D8h] [rbp-28h]
  __int64 v106; // [rsp+E0h] [rbp-20h]
  LPVOID lpMem[2]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v108; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v109; // [rsp+100h] [rbp+0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  _OWORD v111[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v112; // [rsp+138h] [rbp+38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v114[8]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t Source[264]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t v116[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v117[264]; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int16 v118[260]; // [rsp+7E0h] [rbp+6E0h] BYREF
  char v119; // [rsp+9E8h] [rbp+8E8h] BYREF
  unsigned __int16 v120[260]; // [rsp+BF0h] [rbp+AF0h] BYREF
  wchar_t v121[260]; // [rsp+DF8h] [rbp+CF8h] BYREF
  _BYTE v122[520]; // [rsp+1000h] [rbp+F00h] BYREF
  char v123; // [rsp+1208h] [rbp+1108h] BYREF
  unsigned __int16 v124; // [rsp+1410h] [rbp+1310h] BYREF
  unsigned __int16 v125; // [rsp+1412h] [rbp+1312h]
  unsigned __int16 v126; // [rsp+1414h] [rbp+1314h]

  v103 = a4;
  v7 = a2;
  v97 = a2;
  v8 = a1;
  v109 = a1;
  v114[6] = a2;
  v92 = (struct DIRECTORY_SCAN_FUNC_ARGS *)a5;
  v9 = a6;
  v106 = a6;
  v91 = 0;
  IoStatusBlock = 0;
  CreateOptions = *(_DWORD *)(a5 + 4);
  v98 = *(_DWORD *)(a5 + 8);
  v10 = 0;
  v95 = 0;
  *(_OWORD *)lpMem = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  FileHandle = 0;
  v99 = 0;
  v100 = 0;
  v101 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&v99);
  memset_0(Source, 0, 0x208u);
  memset_0(v120, 0, sizeof(v120));
  memset_0(v121, 0, sizeof(v121));
  memset(v111, 0, sizeof(v111));
  v112 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(v111);
  ProcessHeap = GetProcessHeap();
  FileInformation = HeapAlloc(ProcessHeap, 0, 0x8000u);
  if ( !FileInformation )
  {
    v91 = -2147024882;
    goto LABEL_94;
  }
  StringCbCopyW(Source, v12, v8);
  v13 = v101;
  v14 = v100;
  if ( (unsigned __int64)v100 <= v101 + 1 )
  {
    std::deque<RegQueItem>::_Growmap(&v99);
    v13 = v101;
    v14 = v100;
  }
  *((_QWORD *)&v100 + 1) &= v14 - 1;
  v15 = v13 + *((_QWORD *)&v100 + 1);
  v16 = std::deque<RegQueItem>::_Getblock(&v99, v13 + *((_QWORD *)&v100 + 1));
  if ( !*(_QWORD *)(*((_QWORD *)&v99 + 1) + 8 * v16) )
    *(_QWORD *)(*((_QWORD *)&v99 + 1) + 8 * v16) = std::_Allocate<16,std::_Default_allocate_traits>(520);
  v17 = std::_Deque_val<std::_Deque_simple_types<RegQueItem>>::_Address_subscript(&v99, v15);
  std::_Default_allocator_traits<std::allocator<RegQueItem>>::construct<RegQueItem,RegQueItem const &>(v18, v17, Source);
  ++v101;
  if ( a3 )
  {
    memset_0(v117, 0, 0x208u);
    v91 = CompactDirPath(
            (struct DirQueItem *)Source,
            v8,
            *((const unsigned __int16 **)v92 + 2),
            (struct DirQueItem *)v117);
    if ( v91 < 0 )
      goto LABEL_93;
    v19 = v118;
    v20 = Source;
    v21 = 4;
    do
    {
      *(_OWORD *)v19 = *(_OWORD *)v20;
      *((_OWORD *)v19 + 1) = *((_OWORD *)v20 + 1);
      *((_OWORD *)v19 + 2) = *((_OWORD *)v20 + 2);
      *((_OWORD *)v19 + 3) = *((_OWORD *)v20 + 3);
      *((_OWORD *)v19 + 4) = *((_OWORD *)v20 + 4);
      *((_OWORD *)v19 + 5) = *((_OWORD *)v20 + 5);
      *((_OWORD *)v19 + 6) = *((_OWORD *)v20 + 6);
      *((_OWORD *)v19 + 7) = *((_OWORD *)v20 + 7);
      v19 += 64;
      v20 += 64;
      --v21;
    }
    while ( v21 );
    *(_QWORD *)v19 = *(_QWORD *)v20;
    v22 = &v119;
    v23 = v117;
    v24 = 4;
    do
    {
      *(_OWORD *)v22 = *(_OWORD *)v23;
      *((_OWORD *)v22 + 1) = *((_OWORD *)v23 + 1);
      *((_OWORD *)v22 + 2) = *((_OWORD *)v23 + 2);
      *((_OWORD *)v22 + 3) = *((_OWORD *)v23 + 3);
      *((_OWORD *)v22 + 4) = *((_OWORD *)v23 + 4);
      *((_OWORD *)v22 + 5) = *((_OWORD *)v23 + 5);
      *((_OWORD *)v22 + 6) = *((_OWORD *)v23 + 6);
      *((_OWORD *)v22 + 7) = *((_OWORD *)v23 + 7);
      v22 += 128;
      v23 += 64;
      --v24;
    }
    while ( v24 );
    *(_QWORD *)v22 = *(_QWORD *)v23;
    std::queue<std::pair<DirQueItem,DirQueItem>>::push(v111, v118);
  }
  v108 = 0;
  v102 = 1;
  v25 = (char *)FileInformation;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v101 )
          goto LABEL_93;
        v26 = v118;
        v27 = Source;
        v28 = 4;
        do
        {
          *(_OWORD *)v26 = *(_OWORD *)v27;
          *((_OWORD *)v26 + 1) = *((_OWORD *)v27 + 1);
          *((_OWORD *)v26 + 2) = *((_OWORD *)v27 + 2);
          *((_OWORD *)v26 + 3) = *((_OWORD *)v27 + 3);
          *((_OWORD *)v26 + 4) = *((_OWORD *)v27 + 4);
          *((_OWORD *)v26 + 5) = *((_OWORD *)v27 + 5);
          *((_OWORD *)v26 + 6) = *((_OWORD *)v27 + 6);
          *((_OWORD *)v26 + 7) = *((_OWORD *)v27 + 7);
          v26 += 64;
          v27 += 64;
          --v28;
        }
        while ( v28 );
        *(_QWORD *)v26 = *(_QWORD *)v27;
        v91 = CheckTaskCancelled(v9, v95, v92, v118);
        if ( v91 < 0 )
          goto LABEL_93;
        v29 = (_OWORD *)std::queue<std::pair<DirQueItem,DirQueItem>>::front(&v99);
        v30 = Source;
        v31 = 4;
        do
        {
          *(_OWORD *)v30 = *v29;
          *((_OWORD *)v30 + 1) = v29[1];
          *((_OWORD *)v30 + 2) = v29[2];
          *((_OWORD *)v30 + 3) = v29[3];
          *((_OWORD *)v30 + 4) = v29[4];
          *((_OWORD *)v30 + 5) = v29[5];
          *((_OWORD *)v30 + 6) = v29[6];
          *((_OWORD *)v30 + 7) = v29[7];
          v30 += 64;
          v29 += 8;
          --v31;
        }
        while ( v31 );
        *(_QWORD *)v30 = *(_QWORD *)v29;
        std::deque<DirQueItem>::pop_front(&v99);
        v32 = wcsnlen_s(Source, 0x104u);
        memset_0(v116, 0, 0x208u);
        v91 = CompactDirPath(
                (struct DirQueItem *)Source,
                v8,
                *((const unsigned __int16 **)v92 + 2),
                (struct DirQueItem *)v116);
        if ( v91 < 0 )
          goto LABEL_93;
        v33 = RtlDosPathNameToNtPathName_U_WithStatus(Source, lpMem, 0, 0);
        if ( v33 > 0 )
          v33 = (unsigned __int16)v33 | 0x80070000;
        v91 = v33;
        if ( v33 >= 0 )
          break;
        RecordDirScanFailures(v95, v92, v116, v33, 0xDEu);
      }
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)lpMem;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v34 = NtCreateFile(
              &FileHandle,
              0x100001u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x80u,
              7u,
              1u,
              CreateOptions,
              0,
              0);
      if ( v34 > 0 )
        v34 = (unsigned __int16)v34 | 0x80070000;
      v91 = v34;
      if ( v34 >= 0 )
        break;
      RecordDirScanFailures(v95, v92, v116, v34, 0xF3u);
    }
    *((_QWORD *)v92 + 4) = Source;
    v35 = wcsnlen_s(Source, 0x104u);
    *((_WORD *)v92 + 12) = 2 * v35;
    *((_WORD *)v92 + 13) = 520;
    *((_QWORD *)v92 + 6) = v116;
    v36 = wcsnlen_s(v116, 0x104u);
    *((_WORD *)v92 + 20) = 2 * v36;
    *((_WORD *)v92 + 21) = 520;
    *((_QWORD *)v92 + 9) = 0;
    if ( a3 )
      break;
LABEL_39:
    v45 = NtQueryDirectoryFile(
            FileHandle,
            0,
            0,
            0,
            &IoStatusBlock,
            v25,
            0x8000u,
            FileMaximumInformation|FileBasicInformation,
            0,
            0,
            0);
    if ( v45 == 259 )
    {
      RecordDirScanFailures(v95, v92, v116, 259, 0x120u);
    }
    else if ( v45 < 0 )
    {
      goto LABEL_106;
    }
    Information = IoStatusBlock.Information;
    if ( LODWORD(IoStatusBlock.Information) )
    {
      v48 = 0;
      while ( 1 )
      {
        v49 = v118;
        v50 = Source;
        v51 = 4;
        do
        {
          *(_OWORD *)v49 = *(_OWORD *)v50;
          *((_OWORD *)v49 + 1) = *((_OWORD *)v50 + 1);
          *((_OWORD *)v49 + 2) = *((_OWORD *)v50 + 2);
          *((_OWORD *)v49 + 3) = *((_OWORD *)v50 + 3);
          *((_OWORD *)v49 + 4) = *((_OWORD *)v50 + 4);
          *((_OWORD *)v49 + 5) = *((_OWORD *)v50 + 5);
          *((_OWORD *)v49 + 6) = *((_OWORD *)v50 + 6);
          *((_OWORD *)v49 + 7) = *((_OWORD *)v50 + 7);
          v49 += 64;
          v50 += 64;
          --v51;
        }
        while ( v51 );
        *(_QWORD *)v49 = *(_QWORD *)v50;
        v91 = CheckTaskCancelled(v106, v95, v92, v118);
        if ( v91 < 0 )
          goto LABEL_93;
        v10 += v48;
        if ( v10 + 88 > Information )
          goto LABEL_38;
        v53 = &v25[v10];
        v95 = (struct _FILE_ID_EXTD_DIR_INFORMATION *)v53;
        v48 = *(_DWORD *)v53;
        v54 = *((_DWORD *)v53 + 15);
        if ( v10 + v54 + 88 > Information )
          v54 = Information - v10 - 88;
        if ( (*((_DWORD *)v53 + 14) & 0x410) != 0x10 )
        {
          *((_QWORD *)v92 + 9) += *((_QWORD *)v53 + 6);
          if ( (v98 & 4) != 0 )
          {
            LOBYTE(v52) = a3;
            v91 = v103(v95, v92, 4, v52);
            if ( v91 < 0 )
              goto LABEL_93;
          }
          goto LABEL_63;
        }
        v55 = (unsigned __int64)v54 >> 1;
        if ( v55 + v32 + 2LL > 0x104 )
        {
          if ( (v98 & 2) != 0 )
          {
            v82 = 2;
LABEL_92:
            LOBYTE(v52) = a3;
            v91 = v103(v95, v92, v82, v52);
            if ( v91 < 0 )
              goto LABEL_93;
          }
        }
        else
        {
          memset_0(&v124, 0, 0x208u);
          if ( v55 > 0x7FFFFFFE )
          {
            v56 = -2147024809;
            v91 = -2147024809;
LABEL_61:
            RecordDirScanFailures(v95, v92, v116, v56, 0x154u);
            goto LABEL_62;
          }
          v57 = (__int16 *)(v53 + 88);
          v58 = 260;
          v59 = &v124;
          do
          {
            if ( !v55 )
              break;
            v60 = *v57;
            if ( !*v57 )
              break;
            ++v57;
            *v59++ = v60;
            --v55;
            --v58;
          }
          while ( v58 );
          v56 = v58 == 0 ? 0x8007007A : 0;
          v61 = v59 - 1;
          if ( v58 )
            v61 = v59;
          *v61 = 0;
          v91 = v58 == 0 ? 0x8007007A : 0;
          if ( !v58 )
            goto LABEL_61;
          v62 = v124 - 46;
          if ( v124 == 46 )
            v62 = v125;
          if ( !v62 )
            goto LABEL_62;
          v63 = v124 - 46;
          if ( v124 == 46 )
          {
            v63 = v125 - 46;
            if ( v125 == 46 )
              v63 = v126;
          }
          if ( !v63 )
            goto LABEL_62;
          memset_0(v117, 0, 0x208u);
          v64 = StringCchPrintfW(v117, 0x104u, L"%s\\%s", Source, &v124);
          v91 = v64;
          if ( v64 >= 0 )
          {
            v94 = 0;
            v65 = v97[1];
            v66 = 0xFC0FC0FC0FC0FC1LL * ((v65 - *v97) >> 3);
            if ( !v66
              || (v67 = v108, v108 >= v66)
              || (v114[0] = &v91,
                  v114[1] = v117,
                  v114[2] = &v94,
                  v114[3] = &v95,
                  v114[4] = &v92,
                  v114[5] = v116,
                  (unsigned __int8)std::none_of_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_DirQueItem_______lambda_6c86c0106d87337bf10abc307b097053___(
                                     *v97,
                                     v65,
                                     v114)) )
            {
              v68 = v101;
              v69 = v100;
              if ( (unsigned __int64)v100 <= v101 + 1 )
              {
                std::deque<RegQueItem>::_Growmap(&v99);
                v68 = v101;
                v69 = v100;
              }
              *((_QWORD *)&v100 + 1) &= v69 - 1;
              v70 = v68 + *((_QWORD *)&v100 + 1);
              v71 = std::deque<RegQueItem>::_Getblock(&v99, v68 + *((_QWORD *)&v100 + 1));
              if ( !*(_QWORD *)(*((_QWORD *)&v99 + 1) + 8 * v71) )
                *(_QWORD *)(*((_QWORD *)&v99 + 1) + 8 * v71) = std::_Allocate<16,std::_Default_allocate_traits>(520);
              v72 = std::_Deque_val<std::_Deque_simple_types<RegQueItem>>::_Address_subscript(&v99, v70);
              std::_Default_allocator_traits<std::allocator<RegQueItem>>::construct<RegQueItem,RegQueItem const &>(
                v73,
                v72,
                v117);
              ++v101;
              if ( a3 )
              {
                memset_0(v118, 0, sizeof(v118));
                v74 = v102++;
                LODWORD(AllocationSize) = v74;
                v75 = StringCchPrintfW(v118, 0x104u, L"%s\\%d", v121, AllocationSize);
                v91 = v75;
                if ( v75 < 0 )
                {
                  RecordDirScanFailures(v95, v92, v121, v75, 0x175u);
                  goto LABEL_62;
                }
                v76 = v122;
                v77 = v117;
                v78 = 4;
                do
                {
                  *v76 = *(_OWORD *)v77;
                  v76[1] = *((_OWORD *)v77 + 1);
                  v76[2] = *((_OWORD *)v77 + 2);
                  v76[3] = *((_OWORD *)v77 + 3);
                  v76[4] = *((_OWORD *)v77 + 4);
                  v76[5] = *((_OWORD *)v77 + 5);
                  v76[6] = *((_OWORD *)v77 + 6);
                  v76[7] = *((_OWORD *)v77 + 7);
                  v76 += 8;
                  v77 += 64;
                  --v78;
                }
                while ( v78 );
                *(_QWORD *)v76 = *(_QWORD *)v77;
                v79 = &v123;
                v80 = v118;
                v81 = 4;
                do
                {
                  *(_OWORD *)v79 = *(_OWORD *)v80;
                  *((_OWORD *)v79 + 1) = *((_OWORD *)v80 + 1);
                  *((_OWORD *)v79 + 2) = *((_OWORD *)v80 + 2);
                  *((_OWORD *)v79 + 3) = *((_OWORD *)v80 + 3);
                  *((_OWORD *)v79 + 4) = *((_OWORD *)v80 + 4);
                  *((_OWORD *)v79 + 5) = *((_OWORD *)v80 + 5);
                  *((_OWORD *)v79 + 6) = *((_OWORD *)v80 + 6);
                  *((_OWORD *)v79 + 7) = *((_OWORD *)v80 + 7);
                  v79 += 128;
                  v80 += 64;
                  --v81;
                }
                while ( v81 );
                *(_QWORD *)v79 = *(_QWORD *)v80;
                std::queue<std::pair<DirQueItem,DirQueItem>>::push(v111, v122);
              }
              if ( (v98 & 1) != 0 )
              {
                v82 = 1;
                goto LABEL_92;
              }
            }
            else
            {
              v108 = v67 + 1;
            }
          }
          else
          {
            RecordDirScanFailures(v95, v92, v116, v64, 0x15Bu);
          }
        }
LABEL_62:
        v25 = (char *)FileInformation;
LABEL_63:
        if ( !v48 )
        {
LABEL_38:
          v10 = 0;
          goto LABEL_39;
        }
      }
    }
LABEL_106:
    if ( (v98 & 8) != 0 )
    {
      if ( *((_QWORD *)v92 + 9) )
      {
        if ( v95 )
        {
          LOBYTE(v46) = a3;
          v91 = v103(v95, v92, 8, v46);
          if ( v91 < 0 )
            goto LABEL_93;
        }
      }
    }
    if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      NtClose(FileHandle);
      FileHandle = 0;
    }
    v8 = v109;
    v9 = v106;
    if ( lpMem[1] )
    {
      v89 = GetProcessHeap();
      HeapFree(v89, 0, lpMem[1]);
      lpMem[1] = 0;
    }
  }
  v37 = (_OWORD *)std::queue<std::pair<DirQueItem,DirQueItem>>::front(v111);
  v38 = v37;
  v39 = v120;
  v40 = 4;
  do
  {
    *(_OWORD *)v39 = *v37;
    *((_OWORD *)v39 + 1) = v37[1];
    *((_OWORD *)v39 + 2) = v37[2];
    *((_OWORD *)v39 + 3) = v37[3];
    *((_OWORD *)v39 + 4) = v37[4];
    *((_OWORD *)v39 + 5) = v37[5];
    *((_OWORD *)v39 + 6) = v37[6];
    *((_OWORD *)v39 + 7) = v37[7];
    v39 += 64;
    v37 += 8;
    --v40;
  }
  while ( v40 );
  *(_QWORD *)v39 = *(_QWORD *)v37;
  v41 = (_OWORD *)((char *)v38 + 520);
  v42 = v121;
  v43 = 4;
  do
  {
    *(_OWORD *)v42 = *v41;
    *((_OWORD *)v42 + 1) = v41[1];
    *((_OWORD *)v42 + 2) = v41[2];
    *((_OWORD *)v42 + 3) = v41[3];
    *((_OWORD *)v42 + 4) = v41[4];
    *((_OWORD *)v42 + 5) = v41[5];
    *((_OWORD *)v42 + 6) = v41[6];
    *((_OWORD *)v42 + 7) = v41[7];
    v42 += 64;
    v41 += 8;
    --v43;
  }
  while ( v43 );
  *(_QWORD *)v42 = *(_QWORD *)v41;
  std::deque<DirQueItem>::pop_front(v111);
  v93 = 0;
  v91 = WcscmpFromEnd(v120, Source, &v93);
  if ( v91 >= 0 && v93 )
  {
    *((_QWORD *)v92 + 8) = v121;
    v44 = wcsnlen_s(v121, 0x104u);
    *((_WORD *)v92 + 28) = 2 * v44;
    *((_WORD *)v92 + 29) = 520;
    goto LABEL_39;
  }
  v91 = -2147418113;
  RecordDirScanFailures(v95, v92, v116, -2147418113, 0x106u);
LABEL_93:
  v7 = v97;
LABEL_94:
  WriteDirScanFailureBuffer(v92);
  LOBYTE(v83) = a3;
  v91 = v103(0, v92, 16, v83);
  v84 = FileInformation;
  if ( FileInformation )
  {
    v85 = GetProcessHeap();
    HeapFree(v85, 0, v84);
  }
  if ( lpMem[1] )
  {
    v86 = GetProcessHeap();
    HeapFree(v86, 0, lpMem[1]);
  }
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    NtClose(FileHandle);
  v87 = v91;
  std::deque<std::pair<DirQueItem,DirQueItem>>::~deque<std::pair<DirQueItem,DirQueItem>>(v111);
  std::deque<RegQueItem>::~deque<RegQueItem>(&v99);
  std::vector<DirQueItem>::_Tidy(v7);
  return v87;
}

```

## disassembly

```asm
0x180022ab4  push    rbp
0x180022ab6  push    rbx
0x180022ab7  push    rsi
0x180022ab8  push    rdi
0x180022ab9  push    r12
0x180022abb  push    r13
0x180022abd  push    r14
0x180022abf  push    r15
0x180022ac1  lea     rbp, [rsp-1538h]
0x180022ac9  mov     eax, 1638h
0x180022ace  call    _alloca_probe
0x180022ad3  sub     rsp, rax
0x180022ad6  mov     rax, cs:__security_cookie
0x180022add  xor     rax, rsp
0x180022ae0  mov     [rbp+1570h+var_50], rax
0x180022ae7  mov     [rbp+1570h+var_15A8], r9
0x180022aeb  mov     r12b, r8b
0x180022aee  mov     rdi, rdx
0x180022af1  mov     [rbp+1570h+var_15E8], rdx
0x180022af5  mov     r14, rcx
0x180022af8  mov     [rbp+1570h+var_1570], rcx
0x180022afc  mov     rax, [rbp+1570h+arg_20]
0x180022b03  mov     [rbp+1570h+var_14D0], rdx
0x180022b0a  mov     [rsp+1670h+var_1608], rax
0x180022b0f  mov     r15, [rbp+1570h+arg_28]
0x180022b16  mov     [rbp+1570h+var_1590], r15
0x180022b1a  mov     [rsp+1670h+var_1610], 0
0x180022b22  xorps   xmm0, xmm0
0x180022b25  movups  xmmword ptr [rbp+1570h+IoStatusBlock], xmm0
0x180022b29  mov     ecx, [rax+4]
0x180022b2c  mov     [rbp+1570h+var_1598], ecx
0x180022b2f  mov     esi, [rax+8]
0x180022b32  mov     [rbp+1570h+var_15E0], esi
0x180022b35  xor     esi, esi
0x180022b37  mov     [rsp+1670h+var_15F8], rsi
0x180022b3c  movups  xmmword ptr [rbp+1570h+lpMem], xmm0
0x180022b40  xorps   xmm1, xmm1
0x180022b43  movups  xmmword ptr [rbp+1570h+ObjectAttributes.Length], xmm1
0x180022b47  movups  xmmword ptr [rbp+1570h+ObjectAttributes.ObjectName], xmm1
0x180022b4b  movups  xmmword ptr [rbp+1570h+ObjectAttributes.SecurityDescriptor], xmm1
0x180022b4f  mov     [rbp+1570h+FileHandle], rsi
0x180022b53  movdqu  [rbp+1570h+var_15D8], xmm0
0x180022b58  movdqu  [rbp+1570h+var_15C8], xmm1
0x180022b5d  mov     [rbp+1570h+var_15B8], rsi
0x180022b61  lea     rcx, [rbp+1570h+var_15D8]
0x180022b65  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x180022b6a  nop
0x180022b6b  mov     r13d, 208h
0x180022b71  mov     r8d, r13d; Size
0x180022b74  xor     edx, edx; Val
0x180022b76  lea     rcx, [rbp+1570h+Source]; void *
0x180022b7d  call    memset_0
0x180022b82  mov     r8d, r13d; Size
0x180022b85  xor     edx, edx; Val
0x180022b87  lea     rcx, [rbp+1570h+var_A80]; void *
0x180022b8e  call    memset_0
0x180022b93  mov     r8d, r13d; Size
0x180022b96  xor     edx, edx; Val
0x180022b98  lea     rcx, [rbp+1570h+var_878]; void *
0x180022b9f  call    memset_0
0x180022ba4  xorps   xmm0, xmm0
0x180022ba7  movdqu  [rbp+1570h+var_1558], xmm0
0x180022bac  xorps   xmm1, xmm1
0x180022baf  movdqu  [rbp+1570h+var_1548], xmm1
0x180022bb4  mov     [rbp+1570h+var_1538], rsi
0x180022bb8  lea     rcx, [rbp+1570h+var_1558]
0x180022bbc  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x180022bc1  nop
0x180022bc2  call    cs:__imp_GetProcessHeap
0x180022bc8  mov     rcx, rax; hHeap
0x180022bcb  xor     edx, edx; dwFlags
0x180022bcd  mov     r8d, 8000h; dwBytes
0x180022bd3  call    cs:__imp_HeapAlloc
0x180022bd9  mov     [rbp+1570h+FileInformation], rax
0x180022bdd  test    rax, rax
0x180022be0  jnz     short loc_180022BEF
0x180022be2  mov     [rsp+1670h+var_1610], 8007000Eh
0x180022bea  jmp     loc_1800236FA
0x180022bef  mov     r8, r14; unsigned __int16 *
0x180022bf2  lea     rcx, [rbp+1570h+Source]; unsigned __int16 *
0x180022bf9  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180022bfe  mov     r11, [rbp+1570h+var_15B8]
0x180022c02  lea     rax, [r11+1]
0x180022c06  mov     rcx, qword ptr [rbp+1570h+var_15C8]
0x180022c0a  cmp     rcx, rax
0x180022c0d  ja      short loc_180022C20
0x180022c0f  lea     rcx, [rbp+1570h+var_15D8]
0x180022c13  call    ?_Growmap@?$deque@URegQueItem@@V?$allocator@URegQueItem@@@std@@@std@@AEAAX_K@Z; std::deque<RegQueItem>::_Growmap(unsigned __int64)
0x180022c18  mov     r11, [rbp+1570h+var_15B8]
0x180022c1c  mov     rcx, qword ptr [rbp+1570h+var_15C8]
0x180022c20  lea     rax, [rcx-1]
0x180022c24  mov     rcx, qword ptr [rbp+1570h+var_15C8+8]
0x180022c28  and     rcx, rax
0x180022c2b  mov     qword ptr [rbp+1570h+var_15C8+8], rcx
0x180022c2f  lea     rdi, [r11+rcx]
0x180022c33  mov     rdx, rdi
0x180022c36  lea     rcx, [rbp+1570h+var_15D8]
0x180022c3a  call    ?_Getblock@?$deque@URegQueItem@@V?$allocator@URegQueItem@@@std@@@std@@AEBA_J_K@Z; std::deque<RegQueItem>::_Getblock(unsigned __int64)
0x180022c3f  mov     rbx, rax
0x180022c42  mov     rcx, qword ptr [rbp+1570h+var_15D8+8]
0x180022c46  cmp     [rcx+rax*8], rsi
0x180022c4a  jnz     short loc_180022C5C
0x180022c4c  mov     rcx, r13
0x180022c4f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180022c54  mov     rcx, qword ptr [rbp+1570h+var_15D8+8]
0x180022c58  mov     [rcx+rbx*8], rax
0x180022c5c  mov     rdx, rdi
0x180022c5f  lea     rcx, [rbp+1570h+var_15D8]
0x180022c63  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@URegQueItem@@@std@@@std@@QEAAPEAURegQueItem@@_K@Z; std::_Deque_val<std::_Deque_simple_types<RegQueItem>>::_Address_subscript(unsigned __int64)
0x180022c68  lea     r8, [rbp+1570h+Source]
0x180022c6f  mov     rdx, rax
0x180022c72  call    ??$construct@URegQueItem@@AEBU1@@?$_Default_allocator_traits@V?$allocator@URegQueItem@@@std@@@std@@SAXAEAV?$allocator@URegQueItem@@@1@QEAURegQueItem@@AEBU3@@Z; std::_Default_allocator_traits<std::allocator<RegQueItem>>::construct<RegQueItem,RegQueItem const &>(std::allocator<RegQueItem> &,RegQueItem * const,RegQueItem const &)
0x180022c77  inc     [rbp+1570h+var_15B8]
0x180022c7b  mov     edi, 80h
0x180022c80  test    r12b, r12b
0x180022c83  jz      loc_180022D99
0x180022c89  mov     r8, r13; Size
0x180022c8c  xor     edx, edx; Val
0x180022c8e  lea     rcx, [rbp+1570h+var_10A0]; void *
0x180022c95  call    memset_0
0x180022c9a  lea     r9, [rbp+1570h+var_10A0]; struct DirQueItem *
0x180022ca1  mov     r8, [rsp+1670h+var_1608]
0x180022ca6  mov     r8, [r8+10h]; unsigned __int16 *
0x180022caa  mov     rdx, r14; unsigned __int16 *
0x180022cad  lea     rcx, [rbp+1570h+Source]; struct DirQueItem *
0x180022cb4  call    ?CompactDirPath@@YAJAEAUDirQueItem@@PEBG10@Z; CompactDirPath(DirQueItem &,ushort const *,ushort const *,DirQueItem &)
0x180022cb9  mov     [rsp+1670h+var_1610], eax
0x180022cbd  test    eax, eax
0x180022cbf  js      loc_1800236F6
0x180022cc5  lea     rcx, [rbp+1570h+var_E90]
0x180022ccc  lea     rax, [rbp+1570h+Source]
0x180022cd3  lea     edx, [rdi-7Ch]
0x180022cd6  movups  xmm0, xmmword ptr [rax]
0x180022cd9  movups  xmmword ptr [rcx], xmm0
0x180022cdc  movups  xmm1, xmmword ptr [rax+10h]
0x180022ce0  movups  xmmword ptr [rcx+10h], xmm1
0x180022ce4  movups  xmm0, xmmword ptr [rax+20h]
0x180022ce8  movups  xmmword ptr [rcx+20h], xmm0
0x180022cec  movups  xmm1, xmmword ptr [rax+30h]
0x180022cf0  movups  xmmword ptr [rcx+30h], xmm1
0x180022cf4  movups  xmm0, xmmword ptr [rax+40h]
0x180022cf8  movups  xmmword ptr [rcx+40h], xmm0
0x180022cfc  movups  xmm1, xmmword ptr [rax+50h]
0x180022d00  movups  xmmword ptr [rcx+50h], xmm1
0x180022d04  movups  xmm0, xmmword ptr [rax+60h]
0x180022d08  movups  xmmword ptr [rcx+60h], xmm0
0x180022d0c  movups  xmm1, xmmword ptr [rax+70h]
0x180022d10  movups  xmmword ptr [rcx+70h], xmm1
0x180022d14  add     rcx, rdi
0x180022d17  add     rax, rdi
0x180022d1a  sub     rdx, 1
0x180022d1e  jnz     short loc_180022CD6
0x180022d20  mov     rax, [rax]
0x180022d23  mov     [rcx], rax
0x180022d26  lea     rcx, [rbp+1570h+var_C88]
0x180022d2d  lea     rax, [rbp+1570h+var_10A0]
0x180022d34  mov     edx, 4
0x180022d39  movups  xmm0, xmmword ptr [rax]
0x180022d3c  movups  xmmword ptr [rcx], xmm0
0x180022d3f  movups  xmm1, xmmword ptr [rax+10h]
0x180022d43  movups  xmmword ptr [rcx+10h], xmm1
0x180022d47  movups  xmm0, xmmword ptr [rax+20h]
0x180022d4b  movups  xmmword ptr [rcx+20h], xmm0
0x180022d4f  movups  xmm1, xmmword ptr [rax+30h]
0x180022d53  movups  xmmword ptr [rcx+30h], xmm1
0x180022d57  movups  xmm0, xmmword ptr [rax+40h]
0x180022d5b  movups  xmmword ptr [rcx+40h], xmm0
0x180022d5f  movups  xmm1, xmmword ptr [rax+50h]
0x180022d63  movups  xmmword ptr [rcx+50h], xmm1
0x180022d67  movups  xmm0, xmmword ptr [rax+60h]
0x180022d6b  movups  xmmword ptr [rcx+60h], xmm0
0x180022d6f  movups  xmm1, xmmword ptr [rax+70h]
0x180022d73  movups  xmmword ptr [rcx+70h], xmm1
0x180022d77  add     rcx, rdi
0x180022d7a  add     rax, rdi
0x180022d7d  sub     rdx, 1
0x180022d81  jnz     short loc_180022D39
0x180022d83  mov     rax, [rax]
0x180022d86  mov     [rcx], rax
0x180022d89  lea     rdx, [rbp+1570h+var_E90]
0x180022d90  lea     rcx, [rbp+1570h+var_1558]
0x180022d94  call    ?push@?$queue@U?$pair@UDirQueItem@@U1@@std@@V?$deque@U?$pair@UDirQueItem@@U1@@std@@V?$allocator@U?$pair@UDirQueItem@@U1@@std@@@2@@2@@std@@QEAAX$$QEAU?$pair@UDirQueItem@@U1@@2@@Z; std::queue<std::pair<DirQueItem,DirQueItem>>::push(std::pair<DirQueItem,DirQueItem> &&)
0x180022d99  mov     [rbp+1570h+var_1578], rsi
0x180022d9d  mov     [rbp+1570h+var_15B0], 1
0x180022da4  mov     rbx, [rbp+1570h+FileInformation]
0x180022da8  cmp     [rbp+1570h+var_15B8], rsi
0x180022dac  jz      loc_1800236F6
0x180022db2  lea     rcx, [rbp+1570h+var_E90]
0x180022db9  lea     rax, [rbp+1570h+Source]
0x180022dc0  mov     edx, 4
0x180022dc5  movups  xmm0, xmmword ptr [rax]
0x180022dc8  movups  xmmword ptr [rcx], xmm0
0x180022dcb  movups  xmm1, xmmword ptr [rax+10h]
0x180022dcf  movups  xmmword ptr [rcx+10h], xmm1
0x180022dd3  movups  xmm0, xmmword ptr [rax+20h]
0x180022dd7  movups  xmmword ptr [rcx+20h], xmm0
0x180022ddb  movups  xmm1, xmmword ptr [rax+30h]
0x180022ddf  movups  xmmword ptr [rcx+30h], xmm1
0x180022de3  movups  xmm0, xmmword ptr [rax+40h]
0x180022de7  movups  xmmword ptr [rcx+40h], xmm0
0x180022deb  movups  xmm1, xmmword ptr [rax+50h]
0x180022def  movups  xmmword ptr [rcx+50h], xmm1
0x180022df3  movups  xmm0, xmmword ptr [rax+60h]
0x180022df7  movups  xmmword ptr [rcx+60h], xmm0
0x180022dfb  movups  xmm1, xmmword ptr [rax+70h]
0x180022dff  movups  xmmword ptr [rcx+70h], xmm1
0x180022e03  add     rcx, rdi
0x180022e06  add     rax, rdi
0x180022e09  sub     rdx, 1
0x180022e0d  jnz     short loc_180022DC5
0x180022e0f  mov     rax, [rax]
0x180022e12  mov     [rcx], rax
0x180022e15  lea     r9, [rbp+1570h+var_E90]
0x180022e1c  mov     r8, [rsp+1670h+var_1608]
0x180022e21  mov     rdx, [rsp+1670h+var_15F8]
0x180022e26  mov     rcx, r15
0x180022e29  call    ?CheckTaskCancelled@@YAJPEAXPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@UDirQueItem@@@Z; CheckTaskCancelled(void *,_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,DirQueItem)
0x180022e2e  mov     [rsp+1670h+var_1610], eax
0x180022e32  test    eax, eax
0x180022e34  js      loc_1800236F6
0x180022e3a  lea     rcx, [rbp+1570h+var_15D8]
0x180022e3e  call    ?front@?$queue@U?$pair@UDirQueItem@@U1@@std@@V?$deque@U?$pair@UDirQueItem@@U1@@std@@V?$allocator@U?$pair@UDirQueItem@@U1@@std@@@2@@2@@std@@QEAAAEAU?$pair@UDirQueItem@@U1@@2@XZ; std::queue<std::pair<DirQueItem,DirQueItem>>::front(void)
0x180022e43  lea     rcx, [rbp+1570h+Source]
0x180022e4a  mov     edx, 4
0x180022e4f  movups  xmm0, xmmword ptr [rax]
0x180022e52  movups  xmmword ptr [rcx], xmm0
0x180022e55  movups  xmm1, xmmword ptr [rax+10h]
0x180022e59  movups  xmmword ptr [rcx+10h], xmm1
0x180022e5d  movups  xmm0, xmmword ptr [rax+20h]
0x180022e61  movups  xmmword ptr [rcx+20h], xmm0
0x180022e65  movups  xmm1, xmmword ptr [rax+30h]
0x180022e69  movups  xmmword ptr [rcx+30h], xmm1
0x180022e6d  movups  xmm0, xmmword ptr [rax+40h]
0x180022e71  movups  xmmword ptr [rcx+40h], xmm0
0x180022e75  movups  xmm1, xmmword ptr [rax+50h]
0x180022e79  movups  xmmword ptr [rcx+50h], xmm1
0x180022e7d  movups  xmm0, xmmword ptr [rax+60h]
0x180022e81  movups  xmmword ptr [rcx+60h], xmm0
0x180022e85  movups  xmm1, xmmword ptr [rax+70h]
0x180022e89  movups  xmmword ptr [rcx+70h], xmm1
0x180022e8d  add     rcx, rdi
0x180022e90  add     rax, rdi
0x180022e93  sub     rdx, 1
0x180022e97  jnz     short loc_180022E4F
0x180022e99  mov     rax, [rax]
0x180022e9c  mov     [rcx], rax
0x180022e9f  lea     rcx, [rbp+1570h+var_15D8]
0x180022ea3  call    ?pop_front@?$deque@UDirQueItem@@V?$allocator@UDirQueItem@@@std@@@std@@QEAAXXZ; std::deque<DirQueItem>::pop_front(void)
0x180022ea8  mov     edx, 104h; MaxCount
0x180022ead  lea     rcx, [rbp+1570h+Source]; Source
0x180022eb4  call    wcsnlen_s
0x180022eb9  mov     r13, rax
0x180022ebc  xor     edx, edx; Val
0x180022ebe  mov     r8d, 208h; Size
0x180022ec4  lea     rcx, [rbp+1570h+var_12B0]; void *
0x180022ecb  call    memset_0
0x180022ed0  lea     r9, [rbp+1570h+var_12B0]; struct DirQueItem *
0x180022ed7  mov     r8, [rsp+1670h+var_1608]
0x180022edc  mov     r8, [r8+10h]; unsigned __int16 *
0x180022ee0  mov     rdx, r14; unsigned __int16 *
0x180022ee3  lea     rcx, [rbp+1570h+Source]; struct DirQueItem *
0x180022eea  call    ?CompactDirPath@@YAJAEAUDirQueItem@@PEBG10@Z; CompactDirPath(DirQueItem &,ushort const *,ushort const *,DirQueItem &)
0x180022eef  mov     [rsp+1670h+var_1610], eax
0x180022ef3  test    eax, eax
0x180022ef5  js      loc_1800236F6
0x180022efb  xor     r9d, r9d
0x180022efe  xor     r8d, r8d
0x180022f01  lea     rdx, [rbp+1570h+lpMem]
0x180022f05  lea     rcx, [rbp+1570h+Source]
0x180022f0c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180022f12  test    eax, eax
0x180022f14  jle     short loc_180022F1E
0x180022f16  movzx   eax, ax
0x180022f19  or      eax, 80070000h
0x180022f1e  mov     [rsp+1670h+var_1610], eax
0x180022f22  test    eax, eax
0x180022f24  jns     short loc_180022F4C
0x180022f26  mov     dword ptr [rsp+1670h+AllocationSize], 0DEh; unsigned int
0x180022f2e  mov     r9d, eax; int
0x180022f31  lea     r8, [rbp+1570h+var_12B0]; unsigned __int16 *
0x180022f38  mov     rdx, [rsp+1670h+var_1608]; struct DIRECTORY_SCAN_FUNC_ARGS *
0x180022f3d  mov     rcx, [rsp+1670h+var_15F8]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x180022f42  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x180022f47  jmp     loc_180022DA8
0x180022f4c  mov     [rbp+1570h+ObjectAttributes.Length], 30h ; '0'
0x180022f53  mov     [rbp+1570h+ObjectAttributes.RootDirectory], rsi
0x180022f57  mov     [rbp+1570h+ObjectAttributes.Attributes], 40h ; '@'
0x180022f5e  lea     rax, [rbp+1570h+lpMem]
0x180022f62  mov     [rbp+1570h+ObjectAttributes.ObjectName], rax
0x180022f66  xorps   xmm0, xmm0
0x180022f69  movdqu  xmmword ptr [rbp+1570h+ObjectAttributes.SecurityDescriptor], xmm0
0x180022f6e  mov     [rsp+1670h+EaLength], esi; EaLength
0x180022f72  mov     [rsp+1670h+EaBuffer], rsi; EaBuffer
0x180022f77  mov     eax, [rbp+1570h+var_1598]
0x180022f7a  mov     [rsp+1670h+CreateOptions], eax; CreateOptions
0x180022f7e  mov     [rsp+1670h+CreateDisposition], 1; CreateDisposition
0x180022f86  mov     [rsp+1670h+ShareAccess], 7; ShareAccess
0x180022f8e  mov     [rsp+1670h+FileAttributes], edi; FileAttributes
0x180022f92  mov     [rsp+1670h+AllocationSize], rsi; AllocationSize
0x180022f97  lea     r9, [rbp+1570h+IoStatusBlock]; IoStatusBlock
  ... truncated ...
```
