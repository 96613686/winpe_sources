# CreateVirtualDisk

- ea: `0x180002740`
- end: `0x1800036ee`
- name: `CreateVirtualDisk`
- size: `4014`
- prototype: `DWORD __stdcall(PVIRTUAL_STORAGE_TYPE VirtualStorageType, PCWSTR Path, VIRTUAL_DISK_ACCESS_MASK VirtualDiskAccessMask, PSECURITY_DESCRIPTOR SecurityDescriptor, CREATE_VIRTUAL_DISK_FLAG Flags, ULONG ProviderSpecificFlags, PCREATE_VIRTUAL_DISK_PARAMETERS Parameters, LPOVERLAPPED Overlapped, PHANDLE Handle)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000648c`

## callees

- `0x180002740`
- `0x180003700`
- `0x180003800`
- `0x180003930`
- `0x180004560`
- `0x1800049d0`
- `0x180004ed0`
- `0x180005200`
- `0x1800063a8`
- `0x18000648c`
- `0x180006aac`
- `0x180006e38`
- `0x180006edc`
- `0x180006fac`
- `0x18000707c`
- `0x18000712c`
- `0x1800072f0`
- `0x1800092e0`
- `0x18000a018`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002c04`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002c24`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002c04`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000353a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000356d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000353a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000356d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036c5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000352a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000355d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000352a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000355d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002bde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000319a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002bde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000319a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180002c40`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800035ea`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180002c40`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800035ea`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800028f5`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800028f5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002f2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002f2a`
- `ntdll!RtlNtStatusToDosError` at `0x180002eea`
- `ntdll!RtlNtStatusToDosError` at `0x180002eea`
- `ntdll!RtlFreeHeap` at `0x180002cb0`
- `ntdll!RtlFreeHeap` at `0x180002cd3`
- `ntdll!RtlFreeHeap` at `0x180002d15`
- `ntdll!RtlFreeHeap` at `0x180002d46`
- `ntdll!RtlFreeHeap` at `0x180002d7d`
- `ntdll!RtlFreeHeap` at `0x180002da7`
- `ntdll!RtlFreeHeap` at `0x180002dcf`
- `ntdll!RtlFreeHeap` at `0x180002cb0`
- `ntdll!RtlFreeHeap` at `0x180002cd3`
- `ntdll!RtlFreeHeap` at `0x180002d15`
- `ntdll!RtlFreeHeap` at `0x180002d46`
- `ntdll!RtlFreeHeap` at `0x180002d7d`
- `ntdll!RtlFreeHeap` at `0x180002da7`
- `ntdll!RtlFreeHeap` at `0x180002dcf`
- `ntdll!RtlAllocateHeap` at `0x180003220`
- `ntdll!RtlAllocateHeap` at `0x180003220`
- `ntdll!RtlInitUnicodeString` at `0x180002ebe`
- `ntdll!RtlInitUnicodeString` at `0x180002ebe`

## pseudocode

```c
DWORD __stdcall CreateVirtualDisk(
        PVIRTUAL_STORAGE_TYPE VirtualStorageType,
        PCWSTR Path,
        VIRTUAL_DISK_ACCESS_MASK VirtualDiskAccessMask,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        CREATE_VIRTUAL_DISK_FLAG Flags,
        ULONG ProviderSpecificFlags,
        PCREATE_VIRTUAL_DISK_PARAMETERS Parameters,
        LPOVERLAPPED Overlapped,
        PHANDLE Handle)
{
  PCWSTR v10; // rax
  WCHAR *v11; // rdx
  WCHAR *v14; // r9
  void *v15; // r8
  _QWORD *v16; // rcx
  PHANDLE v17; // rsi
  ULONG FinalFilePath; // edi
  __int64 v19; // rbx
  CREATE_VIRTUAL_DISK_VERSION Version; // eax
  WCHAR *SourceLimitPath; // rdi
  OPEN_VIRTUAL_DISK_FLAG OpenFlags; // r13d
  PCWSTR ParentPath; // rcx
  const WCHAR *SourcePath; // r15
  char v25; // r11
  char *v26; // r12
  unsigned int v27; // r10d
  __int64 v28; // rax
  size_t v29; // r11
  PVOID v30; // r13
  __int64 v31; // rax
  __int32 v32; // r11d
  wchar_t *v33; // r15
  char *Heap; // rax
  const WCHAR *v35; // r14
  char LastError; // al
  int v37; // r8d
  int v39; // r8d
  NTSTATUS v40; // eax
  int v41; // eax
  ULONG VhdSetRsvd; // eax
  HANDLE v43; // r15
  _OWORD *v44; // rdx
  GUID ResiliencyGuid; // xmm0
  int v46; // eax
  int v47; // r9d
  PVIRTUAL_STORAGE_TYPE v48; // rdi
  int v49; // ecx
  int v50; // edx
  int v51; // ecx
  int v52; // edx
  int v53; // r13d
  PVOID ProcessHeap; // rcx
  CREATE_VIRTUAL_DISK_VERSION v55; // eax
  __int64 v56; // rcx
  char *v57; // r9
  LPCWSTR v58; // rdx
  size_t v59; // r8
  unsigned __int64 v60; // rdi
  unsigned int v61; // eax
  size_t v62; // r8
  unsigned __int64 v63; // rdi
  PVOID v64; // rdx
  unsigned int v65; // eax
  size_t v66; // r8
  unsigned __int64 v67; // rdi
  __int64 v68; // rdi
  const void *v69; // rdx
  size_t v70; // r8
  int v71; // r8d
  DWORD v72; // eax
  int v73; // r8d
  int v74; // edx
  int v75; // r8d
  char v76; // [rsp+58h] [rbp-B0h]
  bool v77; // [rsp+59h] [rbp-AFh] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A8h]
  PVOID Src; // [rsp+68h] [rbp-A0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+70h] [rbp-98h] BYREF
  char Size; // [rsp+78h] [rbp-90h] BYREF
  __int16 Size_1; // [rsp+79h] [rbp-8Fh]
  DWORD Size_4; // [rsp+7Ch] [rbp-8Ch]
  void *v84; // [rsp+80h] [rbp-88h]
  PVOID v85; // [rsp+88h] [rbp-80h]
  unsigned int v86; // [rsp+90h] [rbp-78h] BYREF
  HANDLE hFile; // [rsp+98h] [rbp-70h] BYREF
  PVOID P; // [rsp+A0h] [rbp-68h]
  LPCWSTR lpNewFileName; // [rsp+A8h] [rbp-60h]
  __int32 v90; // [rsp+B0h] [rbp-58h] BYREF
  size_t v91; // [rsp+B4h] [rbp-54h] BYREF
  size_t lpBytesReturned; // [rsp+BCh] [rbp-4Ch] BYREF
  size_t v93; // [rsp+C8h] [rbp-40h]
  size_t pcchLength[2]; // [rsp+D0h] [rbp-38h] BYREF
  int v95; // [rsp+E0h] [rbp-28h]
  __int32 v96; // [rsp+E4h] [rbp-24h]
  __int64 v97; // [rsp+E8h] [rbp-20h] BYREF
  WCHAR *v98; // [rsp+F0h] [rbp-18h]
  _UNICODE_STRING DestinationString; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v100; // [rsp+108h] [rbp+0h] BYREF
  __int64 v101[2]; // [rsp+110h] [rbp+8h] BYREF
  __int64 v102; // [rsp+120h] [rbp+18h]
  int v103; // [rsp+128h] [rbp+20h]
  __int128 v104; // [rsp+130h] [rbp+28h] BYREF
  _OWORD v105[3]; // [rsp+140h] [rbp+38h] BYREF
  char Handlea; // [rsp+208h] [rbp+100h]

  P = 0;
  v10 = Path;
  hObject = (HANDLE)-1LL;
  v11 = 0;
  v100 = -1;
  lpExistingFileName = 0;
  v95 = 0;
  Src = 0;
  v91 = 0;
  v14 = 0;
  lpNewFileName = 0;
  v15 = 0;
  pcchLength[0] = 0;
  v93 = 0;
  v86 = 0;
  v85 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v90 = 0;
  memset(v105, 0, 44);
  hFile = (HANDLE)-1LL;
  v84 = 0;
  lpBytesReturned = 0;
  LODWORD(v97) = 0;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_0a153a6dcad731a9943f71b10be1e25e_Traceguids);
    v16 = WPP_GLOBAL_Control;
    v11 = (WCHAR *)lpExistingFileName;
    v15 = v84;
    v14 = (WCHAR *)v85;
    v10 = Path;
  }
  if ( VirtualStorageType )
  {
    if ( v10 )
    {
      if ( (Flags & 0xFFFFF800) == 0 && (Flags & 0x48) != 0x48 )
      {
        v96 = Flags & 0x400;
        if ( (Flags & 0x400) == 0 || (Flags & 0x80u) != 0 )
        {
          if ( Parameters )
          {
            v17 = Handle;
            if ( !Handle )
            {
              FinalFilePath = 87;
              goto LABEL_97;
            }
            if ( (unsigned int)(Parameters->Version - 1) > 3 )
            {
              v19 = (__int64)hObject;
              FinalFilePath = 87;
              goto LABEL_96;
            }
            if ( SecurityDescriptor )
            {
              if ( !IsValidSecurityDescriptor(SecurityDescriptor) )
              {
                v19 = (__int64)hObject;
                FinalFilePath = 87;
                goto LABEL_96;
              }
              v11 = (WCHAR *)lpExistingFileName;
              v15 = v84;
              v14 = (WCHAR *)v85;
            }
            if ( (VirtualDiskAccessMask & 0xFFC0FFFF) != 0 )
            {
              v19 = (__int64)hObject;
              FinalFilePath = 87;
              goto LABEL_96;
            }
            Version = Parameters->Version;
            SourceLimitPath = 0;
            OpenFlags = OPEN_VIRTUAL_DISK_FLAG_NONE;
            v98 = 0;
            if ( Version == CREATE_VIRTUAL_DISK_VERSION_1 )
            {
              ParentPath = Parameters->Version1.ParentPath;
              SourcePath = Parameters->Version1.SourcePath;
            }
            else
            {
              if ( Version != CREATE_VIRTUAL_DISK_VERSION_2 )
              {
                if ( Version < CREATE_VIRTUAL_DISK_VERSION_3 )
                {
                  SourcePath = 0;
                  ParentPath = 0;
                  goto LABEL_33;
                }
                SourceLimitPath = (WCHAR *)Parameters->Version3.SourceLimitPath;
                v98 = SourceLimitPath;
              }
              OpenFlags = Parameters->Version2.OpenFlags;
              if ( (OpenFlags & 0xFFFFFFB4) != 0 )
              {
                v19 = (__int64)hObject;
                FinalFilePath = 87;
                goto LABEL_96;
              }
              ParentPath = Parameters->Version1.SourcePath;
              SourcePath = Parameters->Version2.SourcePath;
            }
LABEL_33:
            v25 = 0;
            Size_1 = 0;
            v26 = 0;
            Handlea = 0;
            v27 = 192;
            Size_4 = 192;
            v76 = 0;
            if ( ParentPath )
            {
              v28 = -1;
              do
                ++v28;
              while ( ParentPath[v28] );
              if ( (_DWORD)v28 )
              {
                FinalFilePath = GetFinalFilePath(ParentPath, &Src, &v91, v14);
                if ( FinalFilePath )
                  goto LABEL_61;
                v11 = (WCHAR *)lpExistingFileName;
                v27 = v91 + 192;
                v15 = v84;
                v14 = (WCHAR *)v85;
                if ( (unsigned int)(v91 + 192) < 0xC0 )
                {
                  v30 = Src;
                  FinalFilePath = 534;
                  v19 = (__int64)hObject;
LABEL_87:
                  if ( v30 )
                  {
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
                    v11 = (WCHAR *)lpExistingFileName;
                    v15 = v84;
                    v14 = (WCHAR *)v85;
                  }
                  if ( v14 && v14 != v98 )
                  {
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
                    v11 = (WCHAR *)lpExistingFileName;
                    v15 = v84;
                  }
                  if ( v15 )
                  {
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
                    v11 = (WCHAR *)lpExistingFileName;
                  }
                  if ( v11 )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
                  goto LABEL_96;
                }
                SourceLimitPath = v98;
                v25 = 0;
                Size_4 = v91 + 192;
              }
            }
            if ( !SourcePath )
            {
LABEL_52:
              v86 = 0;
              if ( !SourceLimitPath )
                goto LABEL_115;
              v31 = -1;
              do
                ++v31;
              while ( SourceLimitPath[v31] );
              if ( (_DWORD)v31 )
              {
                if ( (Flags & 0x10) != 0 )
                {
                  v14 = SourceLimitPath;
                  v85 = SourceLimitPath;
                  v32 = 2 * v31 + 2;
                  v86 = 16;
                }
                else
                {
                  FinalFilePath = GetFinalFilePath(SourceLimitPath, &DestinationString, &v90, v14);
                  if ( FinalFilePath )
                  {
                    v85 = *(PVOID *)&DestinationString.Length;
                    goto LABEL_61;
                  }
                  v14 = *(WCHAR **)&DestinationString.Length;
                  v32 = v90;
                  v11 = (WCHAR *)lpExistingFileName;
                  v15 = v84;
                  v27 = Size_4;
                  v85 = *(PVOID *)&DestinationString.Length;
                }
                HIDWORD(v91) = v32;
                if ( v27 + v32 < v27 )
                {
                  v30 = Src;
                  FinalFilePath = 534;
                  v19 = (__int64)hObject;
                  v25 = Handlea;
                  goto LABEL_84;
                }
                Size_4 = v27 + v32;
              }
              else
              {
LABEL_115:
                if ( (Flags & 0x10) != 0 )
                {
                  v30 = Src;
                  FinalFilePath = 87;
                  v19 = (__int64)hObject;
                  goto LABEL_84;
                }
              }
              if ( (VirtualStorageType->DeviceId & 0xFFFFFFFB) == 0 )
              {
                Size = 0;
                v77 = 0;
                DestinationString = 0;
                *(_OWORD *)pcchLength = 0;
                *(_OWORD *)v101 = 0;
                v104 = 0;
                RtlInitUnicodeString(&DestinationString, Path);
                v40 = ClusKRTLParseFileName(
                        (unsigned int)&DestinationString,
                        (unsigned int)pcchLength,
                        v39,
                        (unsigned int)v101,
                        (__int64)&v104);
                if ( v40 < 0 )
                {
                  FinalFilePath = RtlNtStatusToDosError(v40);
                  if ( FinalFilePath )
                    goto LABEL_61;
                }
                v41 = CompareStringW(0x7Fu, 1u, (PCNZWCH)pcchLength[1], LOWORD(pcchLength[0]) >> 1, L"vhds", 4);
                if ( !v41 )
                  goto LABEL_198;
                if ( v41 == 2 )
                {
                  FinalFilePath = CheckRsvdSupport(&v104, &Size, &v77);
                  if ( FinalFilePath )
                    goto LABEL_61;
                  if ( Size && v77 )
                  {
                    VhdSetRsvd = CreateVhdSetRsvd(
                                   (wchar_t *)Path,
                                   (__int64)v101,
                                   VirtualDiskAccessMask,
                                   Flags,
                                   ProviderSpecificFlags,
                                   (__int64)Parameters,
                                   (LPOVERLAPPED)lpNewFileName,
                                   v93,
                                   (__int64)v17);
                    v19 = (__int64)*v17;
                    FinalFilePath = VhdSetRsvd;
LABEL_200:
                    v33 = (wchar_t *)P;
                    goto LABEL_201;
                  }
                }
              }
              v90 = Flags & 0x200;
              v77 = v90 != 0;
              FinalFilePath = CreateTargetFile(Path, SecurityDescriptor, v90 != 0, &hFile);
              if ( !FinalFilePath )
              {
                v43 = hFile;
                LOBYTE(Size_1) = 1;
                FinalFilePath = GetFinalFilePathWithHandle(hFile);
                if ( (Flags & 0x80u) == 0 || (unsigned int)SetSparseAttribute(v43) )
                {
                  CloseHandle(v43);
                  hFile = (HANDLE)-1LL;
                  if ( !FinalFilePath )
                  {
                    v44 = 0;
                    if ( Parameters->Version >= CREATE_VIRTUAL_DISK_VERSION_2 )
                    {
                      ResiliencyGuid = Parameters->Version4.ResiliencyGuid;
                      DWORD2(v105[0]) = 0;
                      v44 = v105;
                      *(_QWORD *)&v105[0] = 2;
                      *(GUID *)((char *)v105 + 12) = ResiliencyGuid;
                    }
                    if ( VirtualStorageType->DeviceId == 4 && (Flags & 8) == 0 )
                      OpenFlags |= 0x40u;
                    v33 = (wchar_t *)P;
                    v46 = OpenFlags | 0x200;
                    if ( !v90 )
                      v46 = OpenFlags;
                    v47 = v46 | 0x400;
                    if ( !v96 )
                      v47 = v46;
                    FinalFilePath = OpenVirtualDiskInternal(
                                      VirtualStorageType,
                                      P,
                                      (unsigned int)VirtualDiskAccessMask,
                                      v47 | 2u,
                                      1,
                                      v44,
                                      &v100,
                                      1);
                    hObject = (HANDLE)v100;
                    if ( v100 == -1 )
                    {
                      v19 = -1;
LABEL_201:
                      v30 = Src;
                      goto LABEL_202;
                    }
                    v48 = VirtualStorageType;
                    if ( VirtualStorageType->DeviceId != 4 )
                      goto LABEL_138;
                    FinalFilePath = GetBackingFilePath(v33, (__int64)&lpExistingFileName, (__int64)&v97);
                    if ( !FinalFilePath )
                    {
                      v48 = VirtualStorageType;
                      if ( VirtualStorageType->DeviceId != 4 || (Flags & 8) == 0 )
                        goto LABEL_138;
                      FinalFilePath = CreateTargetFile(lpExistingFileName, SecurityDescriptor, v77, &hFile);
                      if ( !FinalFilePath )
                      {
                        HIBYTE(Size_1) = 1;
                        CloseHandle(hFile);
                        if ( Size_4 + (unsigned int)lpBytesReturned < Size_4 )
                        {
                          v30 = Src;
                          FinalFilePath = 534;
                          v19 = (__int64)hObject;
                          LOBYTE(Heap) = 0;
                          goto LABEL_66;
                        }
                        v86 |= 0x40u;
                        v48 = VirtualStorageType;
                        Size_4 += lpBytesReturned;
LABEL_138:
                        v49 = v86 | 1;
                        if ( (Flags & 1) == 0 )
                          v49 = v86;
                        v50 = v49 | 2;
                        if ( (Flags & 2) == 0 )
                          v50 = v49;
                        v51 = v50 | 4;
                        if ( (Flags & 4) == 0 )
                          v51 = v50;
                        v52 = v51 | 0x20;
                        if ( (Flags & 0x20) == 0 )
                          v52 = v51;
                        v53 = v52 | 0x80;
                        ProcessHeap = NtCurrentPeb()->ProcessHeap;
                        if ( (Flags & 0x100) == 0 )
                          v53 = v52;
                        Heap = (char *)RtlAllocateHeap(ProcessHeap, 8u, Size_4);
                        v26 = Heap;
                        if ( !Heap )
                        {
                          v30 = Src;
                          FinalFilePath = 14;
                          v19 = (__int64)hObject;
LABEL_66:
                          if ( v19 != -1 )
                          {
                            CloseHandle((HANDLE)v19);
                            LOBYTE(Heap) = v76;
                            v19 = -1;
                          }
                          if ( (_BYTE)Size_1 )
                          {
                            DeleteFileW(Path);
                            LOBYTE(Heap) = v76;
                          }
                          v35 = lpExistingFileName;
                          if ( HIBYTE(Size_1) )
                          {
                            DeleteFileW(lpExistingFileName);
                            LOBYTE(Heap) = v76;
                          }
                          if ( (_BYTE)Heap )
                          {
                            if ( !MoveFileW(v35, lpNewFileName) )
                            {
                              LastError = GetLastError();
                              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                              {
                                WPP_SF_SSd(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  22,
                                  v37,
                                  (_DWORD)v35,
                                  (__int64)lpNewFileName,
                                  LastError);
                              }
                            }
                          }
LABEL_78:
                          if ( !v26 )
                          {
LABEL_80:
                            if ( v33 )
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
                            v25 = Handlea;
                            goto LABEL_83;
                          }
LABEL_79:
                          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v26);
                          goto LABEL_80;
                        }
                        *(_DWORD *)Heap = 1;
                        *((_DWORD *)Heap + 20) = v53;
                        *((_DWORD *)Heap + 21) = ProviderSpecificFlags;
                        *(_OWORD *)(Heap + 4) = *(_OWORD *)&v48->DeviceId;
                        *((_DWORD *)Heap + 5) = *(_DWORD *)&v48->VendorId.Data4[4];
                        v55 = Parameters->Version;
                        if ( Parameters->Version == CREATE_VIRTUAL_DISK_VERSION_1 )
                        {
                          *((_QWORD *)v26 + 11) = *(_QWORD *)&Parameters->Version4.BlockSizeInBytes;
                          *((_DWORD *)v26 + 24) = 0;
                          *((_QWORD *)v26 + 13) = Parameters->Version1.MaximumSize;
                        }
                        else if ( v55 == CREATE_VIRTUAL_DISK_VERSION_2 )
                        {
                          *((_QWORD *)v26 + 11) = *(_QWORD *)&Parameters->Version4.BlockSizeInBytes;
                          *((_DWORD *)v26 + 24) = Parameters->Version2.PhysicalSectorSizeInBytes;
                          *((_QWORD *)v26 + 13) = Parameters->Version1.MaximumSize;
                          *(VIRTUAL_STORAGE_TYPE *)(v26 + 24) = Parameters->Version4.ParentVirtualStorageType;
                          *(VIRTUAL_STORAGE_TYPE *)(v26 + 44) = Parameters->Version4.SourceVirtualStorageType;
                        }
                        else
                        {
                          hFile = 0;
                          if ( v55 < CREATE_VIRTUAL_DISK_VERSION_3 )
                          {
LABEL_158:
                            v30 = Src;
                            if ( !Src
                              || (FinalFilePath = ValidateDifferencingCreateParameters(v48, *((_QWORD *)v26 + 13), Src)) == 0 )
                            {
                              v56 = *(_QWORD *)hFile - *((_QWORD *)v26 + 8);
                              if ( *(_QWORD *)hFile == *((_QWORD *)v26 + 8) )
                                v56 = *((_QWORD *)hFile + 1) - *((_QWORD *)v26 + 9);
                              if ( v56 )
                                *((_OWORD *)v26 + 4) = *(_OWORD *)hFile;
                              else
                                GenerateUniqueID(v26 + 64);
                              v57 = v26 + 192;
                              hFile = v26 + 192;
                              if ( lpNewFileName )
                              {
                                v58 = lpNewFileName;
                                *((_DWORD *)v26 + 30) = 192;
                                v59 = (unsigned int)v93;
                                *((_DWORD *)v26 + 31) = v93;
                                v60 = (unsigned int)v59;
                                memcpy_0(v26 + 192, v58, v59);
                                v57 = &v26[2 * (v60 >> 1) + 192];
                                hFile = v57;
                              }
                              if ( v30 )
                              {
                                *((_DWORD *)v26 + 28) = (_DWORD)v57 - (_DWORD)v26;
                                v61 = v91;
                                v62 = (unsigned int)v91;
                                *((_DWORD *)v26 + 29) = v91;
                                v63 = v61;
                                memcpy_0(v57, v30, v62);
                                v57 = (char *)hFile + 2 * (v63 >> 1);
                                hFile = v57;
                              }
                              v64 = v85;
                              if ( v85 )
                              {
                                *((_DWORD *)v26 + 32) = (_DWORD)v57 - (_DWORD)v26;
                                v65 = HIDWORD(v91);
                                v66 = HIDWORD(v91);
                                *((_DWORD *)v26 + 33) = HIDWORD(v91);
                                v67 = v65;
                                memcpy_0(v57, v64, v66);
                                v57 = (char *)hFile + 2 * (v67 >> 1);
                              }
                              v68 = (__int64)v84;
                              if ( v84 && (Flags & 0x40) == 0 )
                              {
                                v69 = v84;
                                *((_DWORD *)v26 + 34) = (_DWORD)v57 - (_DWORD)v26;
                                v70 = (unsigned int)lpBytesReturned;
                                *((_DWORD *)v26 + 35) = lpBytesReturned;
                                memcpy_0(v57, v69, v70);
                              }
                              if ( Parameters->Version == CREATE_VIRTUAL_DISK_VERSION_4 )
                              {
                                *(GUID *)(v26 + 164) = Parameters->Version4.PmemAddressAbstractionType;
                                *((_QWORD *)v26 + 23) = Parameters->Version4.DataAlignment;
                              }
                              v19 = (__int64)hObject;
                              if ( VirtualStorageType->DeviceId == 4 )
                              {
                                if ( !DeviceIoControl(
                                        hObject,
                                        0x2D1A54u,
                                        v26,
                                        Size_4,
                                        0,
                                        0,
                                        (LPDWORD)&lpBytesReturned + 1,
                                        Overlapped) )
                                {
LABEL_178:
                                  FinalFilePath = GetLastError();
                                  goto LABEL_202;
                                }
                              }
                              else if ( !DeviceIoControl(
                                           hObject,
                                           0x2D1924u,
                                           v26,
                                           Size_4,
                                           0,
                                           0,
                                           (LPDWORD)&lpBytesReturned + 1,
                                           Overlapped) )
                              {
                                goto LABEL_178;
                              }
                              if ( VirtualStorageType->DeviceId == 4 && (Flags & 0x40) != 0 )
                              {
                                HIDWORD(v101[0]) = 0;
                                v102 = 0;
                                v103 = 0;
                                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                                {
                                  WPP_SF_SS(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    19,
                                    v71,
                                    (_DWORD)lpNewFileName,
                                    (__int64)lpExistingFileName);
                                }
                                if ( !MoveFileW(lpNewFileName, lpExistingFileName) )
                                {
                                  v72 = GetLastError();
                                  FinalFilePath = v72;
                                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                  {
                                    WPP_SF_SSd(
                                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                                      20,
                                      v73,
                                      (_DWORD)lpNewFileName,
                                      (__int64)lpExistingFileName,
                                      v72);
                                  }
LABEL_202:
                                  if ( !FinalFilePath )
                                    goto LABEL_78;
                                  goto LABEL_64;
                                }
                                LODWORD(v101[0]) = 3;
                                v101[1] = v68;
                                FinalFilePath = ModifyVhdSet((HANDLE)v19);
                                if ( FinalFilePath )
                                {
                                  LOBYTE(Heap) = 1;
                                  v76 = 1;
                                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                  {
                                    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v74, v75, (_DWORD)v84, FinalFilePath);
                                    LOBYTE(Heap) = 1;
                                  }
LABEL_65:
                                  if ( FinalFilePath == 997 )
                                    goto LABEL_78;
                                  goto LABEL_66;
                                }
                              }
                              FinalFilePath = 0;
                              goto LABEL_79;
                            }
LABEL_63:
                            v19 = (__int64)hObject;
LABEL_64:
                            LOBYTE(Heap) = 0;
                            goto LABEL_65;
                          }
                          *((_QWORD *)v26 + 11) = *(_QWORD *)&Parameters->Version4.BlockSizeInBytes;
                          *((_DWORD *)v26 + 24) = Parameters->Version2.PhysicalSectorSizeInBytes;
                          *((_QWORD *)v26 + 13) = Parameters->Version1.MaximumSize;
                          *(VIRTUAL_STORAGE_TYPE *)(v26 + 24) = Parameters->Version4.ParentVirtualStorageType;
                          *(VIRTUAL_STORAGE_TYPE *)(v26 + 44) = Parameters->Version4.SourceVirtualStorageType;
                          *((_DWORD *)v26 + 20) = v53 | 8;
                          *(VIRTUAL_STORAGE_TYPE *)(v26 + 144) = Parameters->Version4.BackingStorageType;
                        }
                        hFile = &Parameters->Version1;
                        goto LABEL_158;
                      }
                    }
LABEL_62:
                    v30 = Src;
                    goto LABEL_63;
                  }
LABEL_199:
                  v19 = (__int64)hObject;
                  goto LABEL_200;
                }
LABEL_198:
                FinalFilePath = GetLastError();
                goto LABEL_199;
              }
LABEL_61:
              v33 = (wchar_t *)P;
              goto LABEL_62;
            }
            if ( !(unsigned int)GetFinalFilePath(SourcePath, pcchLength, &v86, v14) )
            {
              lpNewFileName = (LPCWSTR)pcchLength[0];
              LODWORD(v29) = v86;
              v93 = v86;
              Handlea = 1;
LABEL_50:
              v11 = (WCHAR *)lpExistingFileName;
              v15 = v84;
              v14 = (WCHAR *)v85;
              v27 = Size_4 + v29;
              v25 = Handlea;
              if ( v27 < Size_4 )
              {
                v30 = Src;
                FinalFilePath = 534;
                v19 = (__int64)hObject;
LABEL_84:
                if ( lpNewFileName && v25 )
                {
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)lpNewFileName);
                  v11 = (WCHAR *)lpExistingFileName;
                  v15 = v84;
                  v14 = (WCHAR *)v85;
                }
                goto LABEL_87;
              }
              Size_4 = v27;
              goto LABEL_52;
            }
            pcchLength[0] = v86;
            lpNewFileName = SourcePath;
            if ( StringCchLengthW(SourcePath, 0x7FFFu, pcchLength) )
            {
              v30 = Src;
              FinalFilePath = 87;
              v19 = (__int64)hObject;
              v25 = 0;
            }
            else
            {
              if ( pcchLength[0] <= 0xFFFFFFFF && (unsigned int)(LODWORD(pcchLength[0]) + 1) >= LODWORD(pcchLength[0]) )
              {
                v29 = 2LL * (unsigned int)(LODWORD(pcchLength[0]) + 1);
                v93 = v29;
                if ( v29 <= 0xFFFFFFFF )
                  goto LABEL_50;
              }
              v30 = Src;
              FinalFilePath = 534;
              v19 = (__int64)hObject;
              v25 = 0;
            }
LABEL_83:
            v14 = (WCHAR *)v85;
            v15 = v84;
            v11 = (WCHAR *)lpExistingFileName;
            goto LABEL_84;
          }
        }
      }
    }
  }
  v17 = Handle;
  FinalFilePath = 87;
  if ( Handle )
  {
    v19 = (__int64)hObject;
LABEL_96:
    *v17 = (HANDLE)v19;
    v16 = WPP_GLOBAL_Control;
  }
LABEL_97:
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 0x20) != 0 && *((_BYTE *)v16 + 25) >= 4u )
    WPP_SF_d(v16[2], 23, &WPP_0a153a6dcad731a9943f71b10be1e25e_Traceguids, FinalFilePath);
  return FinalFilePath;
}

```

## disassembly

```asm
0x180002740  mov     rax, rsp
0x180002743  mov     [rax+20h], r9
0x180002747  mov     [rax+18h], r8d
0x18000274b  mov     [rax+10h], rdx
0x18000274f  mov     [rax+8], rcx
0x180002753  push    rbp
0x180002754  push    rdi
0x180002755  lea     rbp, [rax-0B8h]
0x18000275c  sub     rsp, 1A8h
0x180002763  xor     r10d, r10d
0x180002766  mov     [rax-18h], rbx
0x18000276a  mov     [rax-28h], r12
0x18000276e  xorps   xmm0, xmm0
0x180002771  mov     [rax-40h], r15
0x180002775  mov     rbx, rcx
0x180002778  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000277f  mov     [rbp+0B0h+P], r10
0x180002783  mov     rax, rdx
0x180002786  mov     [rsp+1B0h+hObject], rcx
0x18000278b  mov     edx, r10d
0x18000278e  mov     [rbp+0B0h+var_B0], rcx
0x180002792  mov     r11d, r10d
0x180002795  mov     [rsp+1B0h+lpExistingFileName], rdx
0x18000279a  mov     r15, r9
0x18000279d  mov     [rbp+0B0h+var_D8], r10d
0x1800027a1  mov     r12d, r8d
0x1800027a4  mov     [rsp+1B0h+Src], r10
0x1800027a9  movups  [rbp+0B0h+var_68], xmm0
0x1800027ad  mov     dword ptr [rbp+0B0h+var_104], r10d
0x1800027b1  mov     r9d, r10d
0x1800027b4  mov     [rbp+0B0h+lpNewFileName], r10
0x1800027b8  mov     r8d, r10d
0x1800027bb  mov     [rbp+0B0h+pcchLength], r10
0x1800027bf  mov     [rbp+0B0h+var_F0], r11
0x1800027c3  mov     [rbp+0B0h+var_128], r10d
0x1800027c7  mov     [rbp+0B0h+var_130], r10
0x1800027cb  mov     qword ptr [rbp+0B0h+DestinationString.Length], r10
0x1800027cf  mov     dword ptr [rbp+0B0h+var_104+4], r10d
0x1800027d3  mov     [rbp+0B0h+var_108], r10d
0x1800027d7  mov     dword ptr [rbp+0B0h+var_FC+4], r10d
0x1800027db  movups  [rbp+0B0h+var_78], xmm0
0x1800027df  mov     [rbp+0B0h+hFile], rcx
0x1800027e3  movups  [rbp+0B0h+var_68+0Ch], xmm0
0x1800027e7  mov     [rsp+1B0h+var_138], r10
0x1800027ec  mov     dword ptr [rbp+0B0h+var_FC], r10d
0x1800027f0  mov     dword ptr [rbp+0B0h+var_D0], r10d
0x1800027f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027fb  lea     r11, WPP_GLOBAL_Control
0x180002802  cmp     rcx, r11
0x180002805  jz      short loc_18000284E
0x180002807  test    byte ptr [rcx+1Ch], 20h
0x18000280b  jz      short loc_18000284E
0x18000280d  cmp     byte ptr [rcx+19h], 4
0x180002811  jb      short loc_18000284E
0x180002813  mov     rcx, [rcx+10h]
0x180002817  lea     r8, WPP_0a153a6dcad731a9943f71b10be1e25e_Traceguids
0x18000281e  mov     edx, 12h
0x180002823  call    WPP_SF_
0x180002828  mov     rcx, cs:WPP_GLOBAL_Control
0x18000282f  lea     r11, WPP_GLOBAL_Control
0x180002836  mov     rdx, [rsp+1B0h+lpExistingFileName]
0x18000283b  xor     r10d, r10d
0x18000283e  mov     r8, [rsp+1B0h+var_138]
0x180002843  mov     r9, [rbp+0B0h+var_130]
0x180002847  mov     rax, [rbp+0B0h+lpFileName]
0x18000284e  mov     [rsp+1B0h+var_18], rsi
0x180002856  mov     [rsp+1B0h+var_30], r14
0x18000285e  test    rbx, rbx
0x180002861  jz      short loc_1800028A0
0x180002863  test    rax, rax
0x180002866  jz      short loc_1800028A0
0x180002868  mov     r14d, [rbp+0B0h+Flags]
0x18000286f  test    r14d, 0FFFFF800h
0x180002876  jnz     short loc_1800028A0
0x180002878  mov     eax, r14d
0x18000287b  and     eax, 48h
0x18000287e  cmp     al, 48h ; 'H'
0x180002880  jz      short loc_1800028A0
0x180002882  mov     eax, r14d
0x180002885  and     eax, 400h
0x18000288a  mov     [rbp+0B0h+var_D4], eax
0x18000288d  jz      short loc_180002894
0x18000288f  test    r14b, r14b
0x180002892  jns     short loc_1800028A0
0x180002894  mov     rbx, [rbp+0B0h+Parameters]
0x18000289b  test    rbx, rbx
0x18000289e  jnz     short loc_1800028BF
0x1800028a0  mov     rsi, [rbp+0B0h+Handle]
0x1800028a7  mov     edi, 57h ; 'W'
0x1800028ac  test    rsi, rsi
0x1800028af  jz      loc_180002DF4
0x1800028b5  mov     rbx, [rsp+1B0h+hObject]
0x1800028ba  jmp     loc_180002DEA
0x1800028bf  mov     rsi, [rbp+0B0h+Handle]
0x1800028c6  test    rsi, rsi
0x1800028c9  jnz     short loc_1800028D5
0x1800028cb  mov     edi, 57h ; 'W'
0x1800028d0  jmp     loc_180002DF4
0x1800028d5  mov     eax, [rbx]
0x1800028d7  dec     eax
0x1800028d9  cmp     eax, 3
0x1800028dc  jbe     short loc_1800028ED
0x1800028de  mov     rbx, [rsp+1B0h+hObject]
0x1800028e3  mov     edi, 57h ; 'W'
0x1800028e8  jmp     loc_180002DEA
0x1800028ed  test    r15, r15
0x1800028f0  jz      short loc_18000292C
0x1800028f2  mov     rcx, r15; pSecurityDescriptor
0x1800028f5  call    cs:__imp_IsValidSecurityDescriptor
0x1800028fc  nop     dword ptr [rax+rax+00h]
0x180002901  lea     r11, WPP_GLOBAL_Control
0x180002908  test    eax, eax
0x18000290a  jnz     short loc_18000291B
0x18000290c  mov     rbx, [rsp+1B0h+hObject]
0x180002911  mov     edi, 57h ; 'W'
0x180002916  jmp     loc_180002DEA
0x18000291b  mov     rdx, [rsp+1B0h+lpExistingFileName]
0x180002920  xor     r10d, r10d
0x180002923  mov     r8, [rsp+1B0h+var_138]
0x180002928  mov     r9, [rbp+0B0h+var_130]
0x18000292c  test    r12d, 0FFC0FFFFh
0x180002933  jz      short loc_180002944
0x180002935  mov     rbx, [rsp+1B0h+hObject]
0x18000293a  mov     edi, 57h ; 'W'
0x18000293f  jmp     loc_180002DEA
0x180002944  mov     eax, [rbx]
0x180002946  mov     rdi, r10
0x180002949  mov     [rsp+1B0h+var_28], r13
0x180002951  mov     r13d, r10d
0x180002954  mov     [rbp+0B0h+var_C8], r10
0x180002958  cmp     eax, 1
0x18000295b  jnz     short loc_180002967
0x18000295d  mov     rcx, [rbx+28h]
0x180002961  mov     r15, [rbx+30h]
0x180002965  jmp     short loc_1800029C5
0x180002967  cmp     eax, 2
0x18000296a  jz      short loc_18000297C
0x18000296c  cmp     eax, 3
0x18000296f  jl      short loc_1800029BF
0x180002971  mov     rdi, [rbx+80h]
0x180002978  mov     [rbp+0B0h+var_C8], rdi
0x18000297c  mov     r13d, 40h ; '@'
0x180002982  mov     rax, rbx
0x180002985  mov     r15d, 38h ; '8'
0x18000298b  mov     r11, rbx
0x18000298e  mov     ecx, 30h ; '0'
0x180002993  mov     r10, rbx
0x180002996  mov     r13d, [rbx+r13]
0x18000299a  test    r13d, 0FFFFFFB4h
0x1800029a1  jz      short loc_1800029B2
0x1800029a3  mov     rbx, [rsp+1B0h+hObject]
0x1800029a8  mov     edi, 57h ; 'W'
0x1800029ad  jmp     loc_180002DDB
0x1800029b2  mov     rcx, [rcx+r10]
0x1800029b6  xor     r10d, r10d
0x1800029b9  mov     r15, [r15+r11]
0x1800029bd  jmp     short loc_1800029C5
0x1800029bf  mov     r15, r10
0x1800029c2  mov     rcx, r10
0x1800029c5  xor     r11b, r11b
0x1800029c8  mov     byte ptr [rsp+1B0h+Size+1], 0
0x1800029cd  mov     byte ptr [rsp+1B0h+Size+2], 0
0x1800029d2  mov     r12, r10
0x1800029d5  mov     byte ptr [rbp+0B0h+Handle], r11b
0x1800029dc  mov     r10d, 0C0h
0x1800029e2  mov     dword ptr [rsp+1B0h+Size+4], r10d
0x1800029e7  mov     byte ptr [rsp+1B0h+var_160], r11b
0x1800029ec  test    rcx, rcx
0x1800029ef  jz      short loc_180002A4D
0x1800029f1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800029f8  inc     rax
0x1800029fb  cmp     word ptr [rcx+rax*2], 0
0x180002a00  jnz     short loc_1800029F8
0x180002a02  test    eax, eax
0x180002a04  jz      short loc_180002A4D
0x180002a06  lea     r8, [rbp+0B0h+var_104]
0x180002a0a  lea     rdx, [rsp+1B0h+Src]
0x180002a0f  call    GetFinalFilePath
0x180002a14  mov     edi, eax
0x180002a16  test    eax, eax
0x180002a18  jnz     loc_180002BB9
0x180002a1e  mov     r10d, dword ptr [rbp+0B0h+var_104]
0x180002a22  mov     eax, 0C0h
0x180002a27  mov     rdx, [rsp+1B0h+lpExistingFileName]
0x180002a2c  add     r10d, 0C0h
0x180002a33  mov     r8, [rsp+1B0h+var_138]
0x180002a38  mov     r9, [rbp+0B0h+var_130]
0x180002a3c  cmp     r10d, eax
0x180002a3f  jb      short loc_180002A86
0x180002a41  mov     rdi, [rbp+0B0h+var_C8]
0x180002a45  xor     r11b, r11b
0x180002a48  mov     dword ptr [rsp+1B0h+Size+4], r10d
0x180002a4d  test    r15, r15
0x180002a50  jz      loc_180002B34
0x180002a56  lea     r8, [rbp+0B0h+var_128]
0x180002a5a  mov     rcx, r15
0x180002a5d  lea     rdx, [rbp+0B0h+pcchLength]
0x180002a61  call    GetFinalFilePath
0x180002a66  test    eax, eax
0x180002a68  jnz     short loc_180002A9A
0x180002a6a  mov     r11, [rbp+0B0h+pcchLength]
0x180002a6e  mov     [rbp+0B0h+lpNewFileName], r11
0x180002a72  mov     r11d, [rbp+0B0h+var_128]
0x180002a76  mov     [rbp+0B0h+var_F0], r11
0x180002a7a  mov     byte ptr [rbp+0B0h+Handle], 1
0x180002a81  jmp     loc_180002B0C
0x180002a86  mov     r13, [rsp+1B0h+Src]
0x180002a8b  mov     edi, 216h
0x180002a90  mov     rbx, [rsp+1B0h+hObject]
0x180002a95  jmp     loc_180002D2F
0x180002a9a  mov     eax, [rbp+0B0h+var_128]
0x180002a9d  lea     r8, [rbp+0B0h+pcchLength]; pcchLength
0x180002aa1  mov     edx, 7FFFh; cchMax
0x180002aa6  mov     [rbp+0B0h+pcchLength], rax
0x180002aaa  mov     rcx, r15; psz
0x180002aad  mov     [rbp+0B0h+lpNewFileName], r15
0x180002ab1  call    StringCchLengthW
0x180002ab6  test    eax, eax
0x180002ab8  jz      short loc_180002AD1
0x180002aba  mov     r13, [rsp+1B0h+Src]
0x180002abf  mov     edi, 57h ; 'W'
0x180002ac4  mov     rbx, [rsp+1B0h+hObject]
0x180002ac9  xor     r11b, r11b
0x180002acc  jmp     loc_180002CE7
0x180002ad1  mov     rax, [rbp+0B0h+pcchLength]
0x180002ad5  mov     edx, 0FFFFFFFFh
0x180002ada  cmp     rax, rdx
0x180002add  ja      short loc_180002AE6
0x180002adf  lea     ecx, [rax+1]
0x180002ae2  cmp     ecx, eax
0x180002ae4  jnb     short loc_180002AFD
0x180002ae6  mov     r13, [rsp+1B0h+Src]
0x180002aeb  mov     edi, 216h
0x180002af0  mov     rbx, [rsp+1B0h+hObject]
0x180002af5  xor     r11b, r11b
0x180002af8  jmp     loc_180002CE7
0x180002afd  mov     r11d, ecx
0x180002b00  add     r11, r11
0x180002b03  mov     [rbp+0B0h+var_F0], r11
0x180002b07  cmp     r11, rdx
0x180002b0a  ja      short loc_180002AE6
0x180002b0c  mov     eax, dword ptr [rsp+1B0h+Size+4]
0x180002b10  mov     rdx, [rsp+1B0h+lpExistingFileName]
0x180002b15  mov     r8, [rsp+1B0h+var_138]
0x180002b1a  mov     r9, [rbp+0B0h+var_130]
0x180002b1e  lea     r10d, [rax+r11]
0x180002b22  movzx   r11d, byte ptr [rbp+0B0h+Handle]
0x180002b2a  cmp     r10d, eax
0x180002b2d  jb      short loc_180002B9D
0x180002b2f  mov     dword ptr [rsp+1B0h+Size+4], r10d
0x180002b34  mov     [rbp+0B0h+var_128], 0
0x180002b3b  test    rdi, rdi
0x180002b3e  jz      loc_180002FE2
0x180002b44  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002b4b  inc     rax
0x180002b4e  cmp     word ptr [rdi+rax*2], 0
0x180002b53  jnz     short loc_180002B4B
0x180002b55  test    eax, eax
0x180002b57  jz      loc_180002FE2
0x180002b5d  test    r14b, 10h
0x180002b61  jnz     loc_180002E52
0x180002b67  lea     r8, [rbp+0B0h+var_108]
0x180002b6b  mov     rcx, rdi
0x180002b6e  lea     rdx, [rbp+0B0h+DestinationString]
0x180002b72  call    GetFinalFilePath
0x180002b77  mov     edi, eax
0x180002b79  test    eax, eax
0x180002b7b  jnz     short loc_180002BB1
0x180002b7d  mov     r9, qword ptr [rbp+0B0h+DestinationString.Length]
0x180002b81  mov     r11d, [rbp+0B0h+var_108]
0x180002b85  mov     rdx, [rsp+1B0h+lpExistingFileName]
0x180002b8a  mov     r8, [rsp+1B0h+var_138]
0x180002b8f  mov     r10d, dword ptr [rsp+1B0h+Size+4]
0x180002b94  mov     [rbp+0B0h+var_130], r9
0x180002b98  jmp     loc_180002E68
0x180002b9d  mov     r13, [rsp+1B0h+Src]
0x180002ba2  mov     edi, 216h
0x180002ba7  mov     rbx, [rsp+1B0h+hObject]
0x180002bac  jmp     loc_180002CF5
0x180002bb1  mov     rdx, qword ptr [rbp+0B0h+DestinationString.Length]
0x180002bb5  mov     [rbp+0B0h+var_130], rdx
0x180002bb9  mov     r15, [rbp+0B0h+P]
0x180002bbd  mov     r13, [rsp+1B0h+Src]
0x180002bc2  mov     rbx, [rsp+1B0h+hObject]
0x180002bc7  xor     al, al
0x180002bc9  cmp     edi, 3E5h
0x180002bcf  jz      loc_180002C99
0x180002bd5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002bd9  jz      short loc_180002BF6
0x180002bdb  mov     rcx, rbx; hObject
0x180002bde  call    cs:__imp_CloseHandle
0x180002be5  nop     dword ptr [rax+rax+00h]
0x180002bea  movzx   eax, byte ptr [rsp+1B0h+var_160]
0x180002bef  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180002bf6  cmp     byte ptr [rsp+1B0h+Size+1], 0
0x180002bfb  jz      short loc_180002C15
0x180002bfd  mov     rcx, [rbp+0B0h+lpFileName]; lpFileName
0x180002c04  call    cs:__imp_DeleteFileW
0x180002c0b  nop     dword ptr [rax+rax+00h]
0x180002c10  movzx   eax, byte ptr [rsp+1B0h+var_160]
  ... truncated ...
```
