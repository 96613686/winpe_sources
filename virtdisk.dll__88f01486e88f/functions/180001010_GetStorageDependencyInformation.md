# GetStorageDependencyInformation

- ea: `0x180001010`
- end: `0x180001a35`
- name: `GetStorageDependencyInformation`
- size: `2597`
- prototype: `DWORD __stdcall(HANDLE ObjectHandle, GET_STORAGE_DEPENDENCY_FLAG Flags, ULONG StorageDependencyInfoSize, PSTORAGE_DEPENDENCY_INFO StorageDependencyInfo, PULONG SizeUsed)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001010`
- `0x180001a40`
- `0x1800020a0`
- `0x180005fd6`
- `0x1800063a8`
- `0x180006fac`
- `0x1800076cc`
- `0x180008834`
- `0x180009934`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180001163`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180001163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019da`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000112d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001335`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000112d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001335`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800017f1`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800017f1`
- `ntdll!RtlFreeHeap` at `0x180001237`
- `ntdll!RtlFreeHeap` at `0x180001392`
- `ntdll!RtlFreeHeap` at `0x1800013d3`
- `ntdll!RtlFreeHeap` at `0x1800015bd`
- `ntdll!RtlFreeHeap` at `0x180001237`
- `ntdll!RtlFreeHeap` at `0x180001392`
- `ntdll!RtlFreeHeap` at `0x1800013d3`
- `ntdll!RtlFreeHeap` at `0x1800015bd`
- `ntdll!RtlAllocateHeap` at `0x1800010ce`
- `ntdll!RtlAllocateHeap` at `0x1800012ea`
- `ntdll!RtlAllocateHeap` at `0x1800010ce`
- `ntdll!RtlAllocateHeap` at `0x1800012ea`

## pseudocode

```c
DWORD __stdcall GetStorageDependencyInformation(
        HANDLE ObjectHandle,
        GET_STORAGE_DEPENDENCY_FLAG Flags,
        ULONG StorageDependencyInfoSize,
        PSTORAGE_DEPENDENCY_INFO StorageDependencyInfo,
        PULONG SizeUsed)
{
  size_t v8; // rsi
  _QWORD *v9; // rcx
  STORAGE_DEPENDENCY_INFO_VERSION Version; // r15d
  __int32 v11; // r14d
  ULONG *lpOutBuffer; // r13
  DWORD StorageDependencyForDiskLevel1; // ebx
  ULONG v14; // eax
  DWORD nOutBufferSize; // r15d
  unsigned __int64 *Heap; // r14
  DWORD LastError; // eax
  void *v19; // r8
  unsigned __int64 v20; // rax
  ULONG *v21; // rbp
  int v22; // ecx
  ULONG v23; // ecx
  __int64 i; // r8
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  ULONG v27; // ebp
  unsigned int v28; // edx
  int v29; // r8d
  __int64 v30; // rcx
  unsigned int v31; // eax
  ULONG v32; // r9d
  ULONG v33; // r9d
  unsigned int v34; // r8d
  int v35; // ebp
  WCHAR *v36; // r12
  DWORD j; // eax
  ULONG *v38; // rdx
  char *v39; // rcx
  ULONG *v40; // rdx
  PSTORAGE_DEPENDENCY_INFO v41; // rcx
  unsigned int v42; // ecx
  char *v43; // rbx
  unsigned int v44; // esi
  _WORD *v45; // r14
  unsigned int v46; // eax
  void *v47; // rdx
  unsigned __int64 v48; // rbx
  PSTORAGE_DEPENDENCY_INFO v49; // rdx
  __int64 v50; // rax
  WCHAR *v51; // rbx
  __int64 v52; // rax
  WCHAR *v53; // r12
  unsigned __int64 v54; // rbx
  PSTORAGE_DEPENDENCY_INFO v55; // rsi
  __int64 v56; // rax
  ULONG *v57; // r14
  WCHAR *v58; // rbx
  unsigned int v59; // eax
  PWSTR DependencyDeviceName; // rcx
  unsigned __int64 v61; // rdx
  int v62; // r8d
  unsigned int v63; // ecx
  __int64 v65; // rax
  int v67; // [rsp+40h] [rbp-78h] BYREF
  PSTORAGE_DEPENDENCY_INFO v68; // [rsp+48h] [rbp-70h]
  __int64 InBuffer; // [rsp+50h] [rbp-68h] BYREF
  ULONG *v70; // [rsp+58h] [rbp-60h]
  void *Src; // [rsp+60h] [rbp-58h]
  __int64 v72; // [rsp+68h] [rbp-50h] BYREF
  int v73; // [rsp+70h] [rbp-48h]
  DWORD lpBytesReturned; // [rsp+C8h] [rbp+10h] BYREF
  DWORD BytesReturned; // [rsp+D8h] [rbp+20h] BYREF

  v8 = StorageDependencyInfoSize;
  InBuffer = 0;
  BytesReturned = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9229377d603935d2be71936b1a3734cd_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !StorageDependencyInfo || (unsigned int)v8 < 0x48 )
    goto LABEL_21;
  Version = StorageDependencyInfo->Version;
  if ( (unsigned int)(StorageDependencyInfo->Version - 1) > 1 )
  {
    StorageDependencyForDiskLevel1 = 124;
    goto LABEL_27;
  }
  if ( (Flags & 0xFFFFFFFC) != 0 )
    goto LABEL_21;
  v11 = Flags & 1;
  if ( (Flags & 2) != 0 )
  {
    if ( (Flags & 1) != 0 )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 4u )
        WPP_SF_(v9[2], 12, WPP_9229377d603935d2be71936b1a3734cd_Traceguids);
      memset_0(StorageDependencyInfo, 0, v8);
      if ( Version == STORAGE_DEPENDENCY_INFO_VERSION_1 )
      {
        StorageDependencyForDiskLevel1 = QueryStorageDependencyForDiskLevel1(ObjectHandle);
      }
      else if ( Version == STORAGE_DEPENDENCY_INFO_VERSION_2 )
      {
        StorageDependencyForDiskLevel1 = QueryStorageDependencyForDiskLevel2(ObjectHandle);
      }
      else
      {
        StorageDependencyForDiskLevel1 = 124;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_9229377d603935d2be71936b1a3734cd_Traceguids,
          StorageDependencyForDiskLevel1);
        v9 = WPP_GLOBAL_Control;
      }
      goto LABEL_27;
    }
LABEL_21:
    StorageDependencyForDiskLevel1 = 87;
    goto LABEL_27;
  }
  lpOutBuffer = (ULONG *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)(v8 + 4172));
  if ( !lpOutBuffer )
  {
    v9 = WPP_GLOBAL_Control;
    StorageDependencyForDiskLevel1 = 14;
    goto LABEL_27;
  }
  LODWORD(InBuffer) = Version;
  HIDWORD(InBuffer) = 2 - (v11 != 0);
  if ( !DeviceIoControl(ObjectHandle, 0x901F0u, &InBuffer, 8u, lpOutBuffer, v8 + 4172, &BytesReturned, 0) )
  {
    StorageDependencyForDiskLevel1 = GetLastError();
    if ( v11 && !GetFileTime(ObjectHandle, 0, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9229377d603935d2be71936b1a3734cd_Traceguids);
      }
      memset_0(StorageDependencyInfo, 0, v8);
      if ( Version != STORAGE_DEPENDENCY_INFO_VERSION_1 )
      {
        if ( Version == STORAGE_DEPENDENCY_INFO_VERSION_2 )
          StorageDependencyForDiskLevel1 = QueryStorageDependencyForDiskLevel2(ObjectHandle);
        else
          StorageDependencyForDiskLevel1 = 124;
        goto LABEL_17;
      }
      lpBytesReturned = 0;
      nOutBufferSize = 72;
      v67 = 1;
      while ( 1 )
      {
        Heap = (unsigned __int64 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, nOutBufferSize);
        if ( !Heap )
        {
          StorageDependencyForDiskLevel1 = 14;
          goto LABEL_17;
        }
        if ( DeviceIoControl(ObjectHandle, 0x2D118Cu, &v67, 4u, Heap, nOutBufferSize, &lpBytesReturned, 0) )
          goto LABEL_39;
        LastError = GetLastError();
        StorageDependencyForDiskLevel1 = LastError;
        if ( LastError != 122 && LastError != 234 )
          break;
        v20 = Heap[1];
        if ( v20 <= nOutBufferSize )
          break;
        nOutBufferSize = Heap[1];
        if ( v20 != (unsigned int)v20 )
          goto LABEL_44;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      }
      if ( StorageDependencyForDiskLevel1 == 1
        || StorageDependencyForDiskLevel1 == 87
        || StorageDependencyForDiskLevel1 == 50
        || StorageDependencyForDiskLevel1 == 120
        || StorageDependencyForDiskLevel1 == -2147467263 )
      {
        *((_DWORD *)Heap + 1) = 0;
LABEL_39:
        if ( !*((_DWORD *)Heap + 1) )
        {
          StorageDependencyForDiskLevel1 = -1069940715;
          v19 = Heap;
LABEL_41:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
          goto LABEL_17;
        }
        v21 = (ULONG *)Heap;
      }
      else
      {
LABEL_44:
        v21 = 0;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        if ( StorageDependencyForDiskLevel1 )
        {
LABEL_17:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              WPP_9229377d603935d2be71936b1a3734cd_Traceguids,
              StorageDependencyForDiskLevel1);
          }
          goto LABEL_26;
        }
      }
      v22 = 28 * v21[1];
      StorageDependencyInfo->Version = STORAGE_DEPENDENCY_INFO_VERSION_1;
      StorageDependencyInfo->NumberEntries = v21[1];
      v23 = v22 + 72;
      if ( SizeUsed )
        *SizeUsed = v23;
      if ( (unsigned int)v8 >= v23 )
      {
        for ( i = 0;
              (unsigned int)i < StorageDependencyInfo->NumberEntries;
              *(_DWORD *)&StorageDependencyInfo->Version2Entries[0].VirtualStorageType.VendorId.Data4[v25 + 4] = v21[2 * v26 + 8] )
        {
          v25 = 28LL * (unsigned int)i;
          v26 = 6 * i;
          i = (unsigned int)(i + 1);
          StorageDependencyInfo->Version1Entries[v25 / 0x1C].DependencyTypeFlags = v21[2 * v26 + 2];
          *(ULONG *)((char *)&StorageDependencyInfo->Version2Entries[0].ProviderSpecificFlags + v25) = v21[2 * v26 + 3];
          *(struct _STORAGE_DEPENDENCY_INFO *)((char *)&StorageDependencyInfo->Version2Entries[0].VirtualStorageType.DeviceId
                                             + v25) = *(PSTORAGE_DEPENDENCY_INFO)&v21[2 * v26 + 4];
        }
        StorageDependencyForDiskLevel1 = 0;
      }
      else
      {
        StorageDependencyForDiskLevel1 = 122;
      }
      v19 = v21;
      goto LABEL_41;
    }
    if ( StorageDependencyForDiskLevel1 != 1
      && StorageDependencyForDiskLevel1 != 87
      && StorageDependencyForDiskLevel1 != 120
      && StorageDependencyForDiskLevel1 != -2147467263 )
    {
      goto LABEL_26;
    }
    lpOutBuffer[1] = 0;
  }
  v14 = lpOutBuffer[1];
  if ( !v14 && v11 )
  {
    StorageDependencyForDiskLevel1 = -1069940715;
    goto LABEL_26;
  }
  if ( Version != STORAGE_DEPENDENCY_INFO_VERSION_1 )
  {
    v28 = 0;
    v27 = (v14 << 6) + 72;
    if ( !v14 )
      goto LABEL_100;
    while ( 1 )
    {
      v29 = 60;
      v30 = 17LL * v28;
      v31 = lpOutBuffer[v30 + 14];
      v32 = v27 + lpOutBuffer[v30 + 16];
      if ( lpOutBuffer[v30 + 18] > 0x3C )
        v29 = lpOutBuffer[v30 + 18];
      if ( v31 > 0x206 )
      {
        lpOutBuffer[v30 + 14] = 518;
        v31 = 518;
      }
      v33 = v29 + v32;
      v34 = lpOutBuffer[v30 + 12];
      if ( v34 <= 0x206 )
      {
        if ( !v34 )
        {
          v35 = 526;
          if ( !v31 )
            v35 = 8;
          goto LABEL_99;
        }
      }
      else
      {
        lpOutBuffer[v30 + 12] = 518;
      }
      v35 = 1044;
      if ( !v31 )
        v35 = 526;
LABEL_99:
      v27 = v33 + v35;
      if ( ++v28 >= lpOutBuffer[1] )
        goto LABEL_100;
    }
  }
  v27 = 28 * v14 + 72;
LABEL_100:
  if ( (unsigned int)v8 < v27 )
  {
    if ( SizeUsed )
      *SizeUsed = v27;
    StorageDependencyForDiskLevel1 = 122;
    StorageDependencyInfo->NumberEntries = lpOutBuffer[1];
    goto LABEL_26;
  }
  memset_0(StorageDependencyInfo, 0, v8);
  StorageDependencyInfo->Version = Version;
  StorageDependencyInfo->NumberEntries = lpOutBuffer[1];
  v36 = (WCHAR *)((char *)StorageDependencyInfo->Version1Entries + 64 * (unsigned __int64)lpOutBuffer[1]);
  for ( j = 0; ; j = lpBytesReturned + 1 )
  {
    lpBytesReturned = j;
    if ( j >= StorageDependencyInfo->NumberEntries )
      break;
    if ( Version == STORAGE_DEPENDENCY_INFO_VERSION_1 )
    {
      v38 = &lpOutBuffer[8 * j];
      v39 = (char *)StorageDependencyInfo + 28 * j;
      *((_DWORD *)v39 + 2) = v38[3];
      *((_DWORD *)v39 + 3) = v38[4];
      *((_OWORD *)v39 + 1) = *(_OWORD *)(v38 + 5);
      *((_DWORD *)v39 + 8) = v38[9];
      continue;
    }
    v40 = &lpOutBuffer[17 * j];
    v41 = StorageDependencyInfo + 4 * (unsigned __int64)j;
    v68 = v41;
    v70 = v40;
    v41->Version1Entries[0].DependencyTypeFlags = v40[3];
    v41->Version2Entries[0].ProviderSpecificFlags = v40[4];
    v41->Version2Entries[0].AncestorLevel = v40[10];
    *(struct _STORAGE_DEPENDENCY_INFO *)&v41->Version2Entries[0].VirtualStorageType.DeviceId = *(PSTORAGE_DEPENDENCY_INFO)(v40 + 5);
    *(_DWORD *)&v41->Version2Entries[0].VirtualStorageType.VendorId.Data4[4] = v40[9];
    v41->Version2Entries[0].HostVolumeName = v36;
    v42 = v40[12];
    v43 = (char *)lpOutBuffer + v40[11];
    v44 = v40[16];
    v45 = (_WORD *)((char *)lpOutBuffer + v40[15]);
    v67 = v42;
    Src = v45;
    if ( v42 == 22 && v44 > 8 )
    {
      if ( RtlCompareMemory(v43, L"\\Device\\Mup", 0x16u) == 22 )
      {
        v46 = 4;
        v44 -= 4;
        v45 += 2;
        if ( v44 > 2 )
        {
          while ( 1 )
          {
            v46 += 2;
            v44 -= 2;
            if ( *v45 == 92 )
              break;
            ++v45;
            if ( v44 <= 2 )
              goto LABEL_122;
          }
          for ( ++v45; v44 > 2; v44 -= 2 )
          {
            if ( *v45 == 92 )
              break;
            v46 += 2;
            ++v45;
          }
        }
LABEL_122:
        v47 = Src;
        *v36++ = 92;
        v48 = v46;
        memcpy_0(v36, v47, v46);
        v49 = v68;
        v68->Version2Entries[0].HostVolumeName[(v48 >> 1) + 1] = 0;
        goto LABEL_125;
      }
      v42 = v67;
    }
    GetVolumeNameFromNtVolumeName(v43, v42, v36);
    v49 = v68;
LABEL_125:
    v50 = -1;
    do
      ++v50;
    while ( v36[v50] );
    v51 = &v36[v50 + 1];
    v49->Version2Entries[0].DependentVolumeName = v51;
    GetVolumeNameFromNtVolumeName((char *)lpOutBuffer + v70[13], v70[14], v51);
    v52 = -1;
    do
      ++v52;
    while ( v51[v52] );
    v53 = &v51[v52 + 1];
    v68->Version2Entries[0].DependentVolumeRelativePath = v53;
    if ( v44 )
    {
      v54 = v44;
      memcpy_0(v53, v45, v44);
      v55 = v68;
      v68->Version2Entries[0].DependentVolumeRelativePath[v54 >> 1] = 0;
    }
    else
    {
      v55 = v68;
      *v53 = 0;
    }
    v56 = -1;
    do
      ++v56;
    while ( v53[v56] );
    v57 = v70;
    v58 = &v53[v56 + 1];
    v55->Version2Entries[0].DependencyDeviceName = v58;
    v59 = v57[18];
    if ( v59 )
    {
      memcpy_0(v58, (char *)lpOutBuffer + v57[17], v59);
      DependencyDeviceName = v55->Version2Entries[0].DependencyDeviceName;
      v61 = (unsigned __int64)v57[18] >> 1;
      v72 = 0;
      v73 = 0;
      DependencyDeviceName[v61] = 0;
      if ( !GetNtDiskNumber(v55->Version2Entries[0].DependencyDeviceName, (__int64)&v72) )
      {
        v62 = 0;
        v63 = 1;
        do
        {
          v63 *= 10;
          v62 += 2;
        }
        while ( HIDWORD(v72) / v63 );
        if ( (_DWORD)v72 == 7 || (_DWORD)v72 == 36
           ? StringCbPrintfW(v58, (unsigned int)(v62 + 38), L"\\\\.\\PHYSICALDRIVE%d")
           : StringCbPrintfW(v58, (unsigned int)(v62 + 22), L"\\\\.\\CDROM%d") )
        {
          StorageDependencyForDiskLevel1 = GetLastError();
          goto LABEL_26;
        }
      }
    }
    else
    {
      *v58 = 0;
    }
    v65 = -1;
    while ( v58[++v65] != 0 )
      ;
    v36 = &v58[v65 + 1];
  }
  if ( SizeUsed )
    *SizeUsed = v27;
  StorageDependencyForDiskLevel1 = 0;
LABEL_26:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpOutBuffer);
  v9 = WPP_GLOBAL_Control;
LABEL_27:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 4u )
    WPP_SF_d(v9[2], 11, WPP_9229377d603935d2be71936b1a3734cd_Traceguids, StorageDependencyForDiskLevel1);
  return StorageDependencyForDiskLevel1;
}

```

## disassembly

```asm
0x180001010  mov     r11, rsp
0x180001013  push    rbx
0x180001014  sub     rsp, 0B0h
0x18000101b  mov     [r11+8], rbp
0x18000101f  xor     eax, eax
0x180001021  mov     [r11-10h], rsi
0x180001025  mov     ebx, edx
0x180001027  mov     [r11-18h], rdi
0x18000102b  mov     rbp, rcx
0x18000102e  mov     [r11-20h], r12
0x180001032  mov     rdi, r9
0x180001035  mov     esi, r8d
0x180001038  mov     [r11-68h], rax
0x18000103c  mov     [r11+20h], eax
0x180001040  mov     rcx, cs:WPP_GLOBAL_Control
0x180001047  lea     r12, WPP_GLOBAL_Control
0x18000104e  cmp     rcx, r12
0x180001051  jz      short loc_18000105D
0x180001053  test    byte ptr [rcx+1Ch], 20h
0x180001057  jnz     loc_18000152E
0x18000105d  mov     [rsp+0B8h+var_28], r13
0x180001065  mov     [rsp+0B8h+var_30], r14
0x18000106d  mov     [rsp+0B8h+var_38], r15
0x180001075  test    rdi, rdi
0x180001078  jz      loc_1800011F7
0x18000107e  cmp     esi, 48h ; 'H'
0x180001081  jb      loc_1800011F7
0x180001087  mov     r15d, [rdi]
0x18000108a  lea     eax, [r15-1]
0x18000108e  cmp     eax, 1
0x180001091  ja      loc_180001559
0x180001097  test    ebx, 0FFFFFFFCh
0x18000109d  jnz     loc_1800011F7
0x1800010a3  mov     r14d, ebx
0x1800010a6  and     r14d, 1
0x1800010aa  test    bl, 2
0x1800010ad  jnz     loc_1800013F3
0x1800010b3  mov     rcx, gs:60h
0x1800010bc  lea     ebx, [rsi+104Ch]
0x1800010c2  mov     r8d, ebx; Size
0x1800010c5  mov     edx, 8; Flags
0x1800010ca  mov     rcx, [rcx+30h]; HeapHandle
0x1800010ce  call    cs:__imp_RtlAllocateHeap
0x1800010d5  nop     dword ptr [rax+rax+00h]
0x1800010da  mov     r13, rax
0x1800010dd  test    rax, rax
0x1800010e0  jz      loc_1800014C1
0x1800010e6  mov     [rsp+0B8h+lpOverlapped], 0; lpOverlapped
0x1800010ef  lea     r8, [rsp+0B8h+InBuffer]; lpInBuffer
0x1800010f4  mov     eax, r14d
0x1800010f7  mov     [rsp+0B8h+InBuffer], r15d
0x1800010fc  neg     eax
0x1800010fe  mov     edx, 901F0h; dwIoControlCode
0x180001103  lea     rax, [rsp+0B8h+BytesReturned]
0x18000110b  sbb     ecx, ecx
0x18000110d  mov     [rsp+0B8h+lpBytesReturned], rax; lpBytesReturned
0x180001112  add     ecx, 2
0x180001115  mov     [rsp+0B8h+nOutBufferSize], ebx; nOutBufferSize
0x180001119  mov     [rsp+0B8h+var_64], ecx
0x18000111d  mov     ebx, 8
0x180001122  mov     r9d, ebx; nInBufferSize
0x180001125  mov     [rsp+0B8h+lpOutBuffer], r13; lpOutBuffer
0x18000112a  mov     rcx, rbp; hDevice
0x18000112d  call    cs:__imp_DeviceIoControl
0x180001134  nop     dword ptr [rax+rax+00h]
0x180001139  test    eax, eax
0x18000113b  jnz     loc_18000120B
0x180001141  call    cs:__imp_GetLastError
0x180001148  nop     dword ptr [rax+rax+00h]
0x18000114d  mov     ebx, eax
0x18000114f  test    r14d, r14d
0x180001152  jz      loc_18000148B
0x180001158  xor     r9d, r9d; lpLastWriteTime
0x18000115b  xor     r8d, r8d; lpLastAccessTime
0x18000115e  xor     edx, edx; lpCreationTime
0x180001160  mov     rcx, rbp; hFile
0x180001163  call    cs:__imp_GetFileTime
0x18000116a  nop     dword ptr [rax+rax+00h]
0x18000116f  test    eax, eax
0x180001171  jnz     loc_18000148B
0x180001177  mov     rcx, cs:WPP_GLOBAL_Control
0x18000117e  cmp     rcx, r12
0x180001181  jz      short loc_18000118D
0x180001183  test    byte ptr [rcx+1Ch], 20h
0x180001187  jnz     loc_180001587
0x18000118d  mov     r8, rsi; Size
0x180001190  xor     edx, edx; Val
0x180001192  mov     rcx, rdi; void *
0x180001195  call    memset_0
0x18000119a  cmp     r15d, 1
0x18000119e  jz      loc_1800012B9
0x1800011a4  cmp     r15d, 2
0x1800011a8  jnz     loc_18000151A
0x1800011ae  mov     r9, [rsp+0B8h+SizeUsed]
0x1800011b6  mov     r8, rdi
0x1800011b9  mov     edx, esi
0x1800011bb  mov     rcx, rbp; hDevice
0x1800011be  call    QueryStorageDependencyForDiskLevel2
0x1800011c3  mov     ebx, eax
0x1800011c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800011cc  cmp     rcx, r12
0x1800011cf  jz      short loc_180001225
0x1800011d1  test    byte ptr [rcx+1Ch], 20h
0x1800011d5  jz      short loc_180001225
0x1800011d7  cmp     byte ptr [rcx+19h], 4
0x1800011db  jb      short loc_180001225
0x1800011dd  mov     rcx, [rcx+10h]
0x1800011e1  lea     r8, WPP_9229377d603935d2be71936b1a3734cd_Traceguids
0x1800011e8  mov     edx, 0Dh
0x1800011ed  mov     r9d, ebx
0x1800011f0  call    WPP_SF_d
0x1800011f5  jmp     short loc_180001225
0x1800011f7  mov     ebx, 57h ; 'W'
0x1800011fc  jmp     short loc_18000124A
0x1800011fe  mov     dword ptr [r13+4], 0
0x180001206  mov     ebx, 8
0x18000120b  mov     eax, [r13+4]
0x18000120f  test    eax, eax
0x180001211  jnz     loc_18000164A
0x180001217  test    r14d, r14d
0x18000121a  jz      loc_18000164A
0x180001220  mov     ebx, 0C03A0015h
0x180001225  mov     rcx, gs:60h
0x18000122e  mov     r8, r13; P
0x180001231  xor     edx, edx; Flags
0x180001233  mov     rcx, [rcx+30h]; HeapHandle
0x180001237  call    cs:__imp_RtlFreeHeap
0x18000123e  nop     dword ptr [rax+rax+00h]
0x180001243  mov     rcx, cs:WPP_GLOBAL_Control
0x18000124a  mov     r15, [rsp+0B8h+var_38]
0x180001252  cmp     rcx, r12
0x180001255  mov     r12, [rsp+0B8h+var_20]
0x18000125d  mov     r14, [rsp+0B8h+var_30]
0x180001265  mov     r13, [rsp+0B8h+var_28]
0x18000126d  mov     rdi, [rsp+0B8h+var_18]
0x180001275  mov     rsi, [rsp+0B8h+var_10]
0x18000127d  mov     rbp, [rsp+0B8h+arg_0]
0x180001285  jnz     short loc_180001293
0x180001287  mov     eax, ebx
0x180001289  add     rsp, 0B0h
0x180001290  pop     rbx
0x180001291  retn
0x180001293  test    byte ptr [rcx+1Ch], 20h
0x180001297  jz      short loc_180001287
0x180001299  cmp     byte ptr [rcx+19h], 4
0x18000129d  jb      short loc_180001287
0x18000129f  mov     rcx, [rcx+10h]
0x1800012a3  lea     r8, WPP_9229377d603935d2be71936b1a3734cd_Traceguids
0x1800012aa  mov     edx, 0Bh
0x1800012af  mov     r9d, ebx
0x1800012b2  call    WPP_SF_d
0x1800012b7  jmp     short loc_180001287
0x1800012b9  mov     [rsp+0B8h+arg_8], 0
0x1800012c4  mov     r15d, 48h ; 'H'
0x1800012ca  mov     [rsp+0B8h+var_78], 1
0x1800012d2  mov     rcx, gs:60h
0x1800012db  mov     edx, 8; Flags
0x1800012e0  mov     r8d, r15d; Size
0x1800012e3  mov     r12d, r15d
0x1800012e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800012ea  call    cs:__imp_RtlAllocateHeap
0x1800012f1  nop     dword ptr [rax+rax+00h]
0x1800012f6  mov     r14, rax
0x1800012f9  test    rax, rax
0x1800012fc  jz      loc_1800014B7
0x180001302  mov     [rsp+0B8h+lpOverlapped], 0; lpOverlapped
0x18000130b  lea     rax, [rsp+0B8h+arg_8]
0x180001313  mov     [rsp+0B8h+lpBytesReturned], rax; lpBytesReturned
0x180001318  lea     r8, [rsp+0B8h+var_78]; lpInBuffer
0x18000131d  mov     [rsp+0B8h+nOutBufferSize], r15d; nOutBufferSize
0x180001322  mov     r9d, 4; nInBufferSize
0x180001328  mov     edx, 2D118Ch; dwIoControlCode
0x18000132d  mov     [rsp+0B8h+lpOutBuffer], r14; lpOutBuffer
0x180001332  mov     rcx, rbp; hDevice
0x180001335  call    cs:__imp_DeviceIoControl
0x18000133c  nop     dword ptr [rax+rax+00h]
0x180001341  test    eax, eax
0x180001343  jnz     short loc_180001370
0x180001345  call    cs:__imp_GetLastError
0x18000134c  nop     dword ptr [rax+rax+00h]
0x180001351  mov     ebx, eax
0x180001353  cmp     eax, 7Ah ; 'z'
0x180001356  jz      short loc_1800013AA
0x180001358  cmp     eax, 0EAh
0x18000135d  jz      short loc_1800013AA
0x18000135f  cmp     ebx, 1
0x180001362  jnz     loc_1800014D2
0x180001368  mov     dword ptr [r14+4], 0
0x180001370  cmp     dword ptr [r14+4], 0
0x180001375  jnz     loc_1800015CE
0x18000137b  mov     ebx, 0C03A0015h
0x180001380  mov     r8, r14; P
0x180001383  mov     rcx, gs:60h
0x18000138c  xor     edx, edx; Flags
0x18000138e  mov     rcx, [rcx+30h]; HeapHandle
0x180001392  call    cs:__imp_RtlFreeHeap
0x180001399  nop     dword ptr [rax+rax+00h]
0x18000139e  lea     r12, WPP_GLOBAL_Control
0x1800013a5  jmp     loc_1800011C5
0x1800013aa  mov     rax, [r14+8]
0x1800013ae  cmp     rax, r12
0x1800013b1  jbe     short loc_18000135F
0x1800013b3  mov     r15d, eax
0x1800013b6  cmp     rax, r15
0x1800013b9  jz      loc_1800015AB
0x1800013bf  mov     rcx, gs:60h
0x1800013c8  mov     r8, r14; P
0x1800013cb  xor     edx, edx; Flags
0x1800013cd  xor     ebp, ebp
0x1800013cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800013d3  call    cs:__imp_RtlFreeHeap
0x1800013da  nop     dword ptr [rax+rax+00h]
0x1800013df  test    ebx, ebx
0x1800013e1  jz      loc_1800015D1
0x1800013e7  lea     r12, WPP_GLOBAL_Control
0x1800013ee  jmp     loc_1800011C5
0x1800013f3  test    r14d, r14d
0x1800013f6  jz      loc_1800011F7
0x1800013fc  cmp     rcx, r12
0x1800013ff  jz      short loc_18000140B
0x180001401  test    byte ptr [rcx+1Ch], 20h
0x180001405  jnz     loc_180001563
0x18000140b  mov     r8, rsi; Size
0x18000140e  xor     edx, edx; Val
0x180001410  mov     rcx, rdi; void *
0x180001413  call    memset_0
0x180001418  cmp     r15d, 1
0x18000141c  jz      loc_1800014FE
0x180001422  cmp     r15d, 2
0x180001426  jnz     loc_180001524
0x18000142c  mov     r9, [rsp+0B8h+SizeUsed]
0x180001434  mov     r8, rdi
0x180001437  mov     edx, esi
0x180001439  mov     rcx, rbp; hDevice
0x18000143c  call    QueryStorageDependencyForDiskLevel2
0x180001441  mov     ebx, eax
0x180001443  mov     rcx, cs:WPP_GLOBAL_Control
0x18000144a  cmp     rcx, r12
0x18000144d  jz      loc_18000124A
0x180001453  test    byte ptr [rcx+1Ch], 20h
0x180001457  jz      loc_18000124A
0x18000145d  cmp     byte ptr [rcx+19h], 4
0x180001461  jb      loc_18000124A
0x180001467  mov     rcx, [rcx+10h]
0x18000146b  lea     r8, WPP_9229377d603935d2be71936b1a3734cd_Traceguids
0x180001472  mov     edx, 0Dh
0x180001477  mov     r9d, ebx
0x18000147a  call    WPP_SF_d
0x18000147f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001486  jmp     loc_18000124A
0x18000148b  cmp     ebx, 1
0x18000148e  jz      loc_1800011FE
0x180001494  cmp     ebx, 57h ; 'W'
0x180001497  jz      loc_1800011FE
0x18000149d  cmp     ebx, 78h ; 'x'
0x1800014a0  jz      loc_1800011FE
0x1800014a6  cmp     ebx, 80004001h
0x1800014ac  jnz     loc_180001225
0x1800014b2  jmp     loc_1800011FE
0x1800014b7  mov     ebx, 0Eh
0x1800014bc  jmp     loc_1800013E7
0x1800014c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800014c8  mov     ebx, 0Eh
0x1800014cd  jmp     loc_18000124A
0x1800014d2  cmp     ebx, 57h ; 'W'
0x1800014d5  jz      loc_180001368
0x1800014db  cmp     ebx, 32h ; '2'
0x1800014de  jz      loc_180001368
0x1800014e4  cmp     ebx, 78h ; 'x'
0x1800014e7  jz      loc_180001368
0x1800014ed  cmp     ebx, 80004001h
0x1800014f3  jz      loc_180001368
0x1800014f9  jmp     loc_1800013BF
0x1800014fe  mov     r9, [rsp+0B8h+SizeUsed]
0x180001506  mov     r8, rdi
0x180001509  mov     edx, esi
0x18000150b  mov     rcx, rbp; hDevice
0x18000150e  call    QueryStorageDependencyForDiskLevel1
0x180001513  mov     ebx, eax
0x180001515  jmp     loc_180001443
0x18000151a  mov     ebx, 7Ch ; '|'
0x18000151f  jmp     loc_1800011C5
0x180001524  mov     ebx, 7Ch ; '|'
0x180001529  jmp     loc_180001443
0x18000152e  cmp     byte ptr [rcx+19h], 4
0x180001532  jb      loc_18000105D
0x180001538  mov     rcx, [rcx+10h]
0x18000153c  lea     r8, WPP_9229377d603935d2be71936b1a3734cd_Traceguids
0x180001543  mov     edx, 0Ah
0x180001548  call    WPP_SF_
0x18000154d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001554  jmp     loc_18000105D
0x180001559  mov     ebx, 7Ch ; '|'
0x18000155e  jmp     loc_18000124A
0x180001563  cmp     byte ptr [rcx+19h], 4
0x180001567  jb      loc_18000140B
0x18000156d  mov     rcx, [rcx+10h]
0x180001571  lea     r8, WPP_9229377d603935d2be71936b1a3734cd_Traceguids
0x180001578  mov     edx, 0Ch
0x18000157d  call    WPP_SF_
  ... truncated ...
```
