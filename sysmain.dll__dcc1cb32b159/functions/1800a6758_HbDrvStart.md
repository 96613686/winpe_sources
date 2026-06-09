# HbDrvStart

- ea: `0x1800a6758`
- end: `0x1800a6f87`
- name: `HbDrvStart`
- size: `2095`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18006a020`

## callees

- `0x180021e0c`
- `0x1800382e0`
- `0x1800383e8`
- `0x18003cbe4`
- `0x18003cffc`
- `0x18004e3f4`
- `0x18005ec74`
- `0x180062090`
- `0x180064170`
- `0x180066144`
- `0x180069980`
- `0x18006b91c`
- `0x1800702fc`
- `0x180070e34`
- `0x18009fe2c`
- `0x1800a0aa0`
- `0x1800a1c80`
- `0x1800a2234`
- `0x1800a28e4`
- `0x1800a5818`
- `0x1800a6758`
- `0x1800a713c`
- `0x1800b57c0`
- `0x1800b62c8`
- `0x1800b645a`
- `0x1800b64c0`
- `0x1800b6580`
- `0x1800b7010`

## import_xrefs

- `ntdll!NtClose` at `0x1800a6e5c`
- `ntdll!NtClose` at `0x1800a6e5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a6e8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a6e8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a6a97`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a6a97`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6d5e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6d5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a6c9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a6c9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a6e21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a6e7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a6e21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a6e7b`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuGetControlDeviceHandle` at `0x1800a6883`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuGetControlDeviceHandle` at `0x1800a6883`

## string_xrefs

- `0x1800a6b54`: `HybridDriveCacheRebalance`
- `0x1800a6b71`: `HybridDriveCachePrepopulate`

## pseudocode

```c
__int64 __fastcall HbDrvStart(__int64 a1, __int64 a2)
{
  char *v3; // r13
  unsigned int v4; // r15d
  unsigned int SystemVolumeInfo; // ebx
  __int64 v6; // rcx
  char v7; // cl
  unsigned int SupportedVolumes; // eax
  unsigned int v9; // r12d
  __int64 v10; // rdx
  int v11; // edi
  unsigned int v12; // r14d
  HRESULT v13; // eax
  struct _RTL_CRITICAL_SECTION *v14; // r10
  _DWORD *v15; // rsi
  unsigned int v16; // r12d
  unsigned int v17; // r14d
  char *v18; // rcx
  char *v19; // rdi
  __int64 i; // rsi
  __int64 v21; // rcx
  unsigned int v22; // edi
  __int64 v23; // r8
  LSTATUS updated; // [rsp+50h] [rbp-B0h]
  unsigned int IsSupportedHhd; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v27; // [rsp+58h] [rbp-A8h] BYREF
  BOOL v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v29; // [rsp+64h] [rbp-9Ch] BYREF
  int v30; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v31; // [rsp+6Ch] [rbp-94h]
  unsigned __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  char *v33; // [rsp+78h] [rbp-88h] BYREF
  LPVOID lpMem; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v38[3]; // [rsp+A0h] [rbp-60h] BYREF
  char v39; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v40; // [rsp+BCh] [rbp-44h]
  _OWORD *v41; // [rsp+C0h] [rbp-40h]
  unsigned int v42; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+EC0h] [rbp+DC0h]
  int v46; // [rsp+EC8h] [rbp+DC8h]
  __int128 v47; // [rsp+ED0h] [rbp+DD0h] BYREF
  __int64 v48; // [rsp+EE0h] [rbp+DE0h]
  __int64 v49; // [rsp+EF0h] [rbp+DF0h] BYREF
  int v50; // [rsp+EF8h] [rbp+DF8h]
  _OWORD v51[2]; // [rsp+F00h] [rbp+E00h] BYREF
  __int128 v52; // [rsp+F20h] [rbp+E20h]
  unsigned int *v53; // [rsp+F30h] [rbp+E30h]
  __int64 v54; // [rsp+F38h] [rbp+E38h]
  unsigned int *v55; // [rsp+F40h] [rbp+E40h]
  __int64 v56; // [rsp+F48h] [rbp+E48h]
  __int64 *v57; // [rsp+F50h] [rbp+E50h]
  __int64 v58; // [rsp+F58h] [rbp+E58h]
  _OWORD v59[24]; // [rsp+F60h] [rbp+E60h] BYREF
  wchar_t pszDest[264]; // [rsp+10E0h] [rbp+FE0h] BYREF

  v37 = a2;
  IsSupportedHhd = 0;
  v32 = 0;
  v49 = 0;
  v50 = 0;
  v27 = 0;
  v28 = 0;
  v30 = 0;
  v3 = 0;
  Handle = 0;
  v4 = 0;
  v33 = 0;
  lpMem = 0;
  hKey = 0;
  v31 = 0;
  v29 = 0;
  memset(v51, 0, sizeof(v51));
  v52 = 0;
  memset_0(v38, 0, 0xE50u);
  v48 = 0;
  v47 = 0;
  memset_0(pszDest, 0, 0x208u);
  memset_0(v59, 0, sizeof(v59));
  if ( (unsigned int)PfsRegQueryValue(
                       *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1432LL),
                       (unsigned int)L"HybridDriveEnabled",
                       4,
                       4,
                       (__int64)&v30) )
    v30 = 0;
  if ( (int)SmuGetControlDeviceHandle(&Handle, 3221225472LL) < 0 || !Handle )
  {
    SystemVolumeInfo = 1058;
    updated = 1058;
LABEL_50:
    IsSupportedHhd = 0;
    goto LABEL_51;
  }
  SystemVolumeInfo = HbDrvGetSystemVolumeInfo(*(_QWORD *)&PfSvcGlobals + 1576LL, v51);
  if ( SystemVolumeInfo )
  {
    if ( SystemVolumeInfo == 50 )
      SystemVolumeInfo = 1058;
    updated = SystemVolumeInfo;
    goto LABEL_50;
  }
  v6 = *((_QWORD *)&v51[0] + 1);
  _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)&v51[0] + 1) + 16LL) + 20LL), 1u);
  *(_QWORD *)(a1 + 8) = *(_QWORD *)(v6 + 16);
  *(_QWORD *)a1 = *(_QWORD *)&v51[0];
  IsSupportedHhd = HbDrvIsSupportedHhd(
                     (unsigned int)v51,
                     (unsigned int)&lpMem,
                     (unsigned int)&v32,
                     (unsigned int)&v39,
                     (__int64)&v28);
  if ( IsSupportedHhd )
  {
    if ( v32 >= 0x2CB417800LL )
    {
      v7 = *((_BYTE *)lpMem + 44);
    }
    else
    {
      v7 = 3;
      if ( *((_BYTE *)lpMem + 44) < 3u )
        v7 = *((_BYTE *)lpMem + 44);
    }
    *(_BYTE *)(a1 + 18) = v7;
    SupportedVolumes = HbDrvGetSupportedVolumes(v51, *(_QWORD *)&PfSvcGlobals + 1576LL, v59);
    v4 = v31;
    SystemVolumeInfo = SupportedVolumes;
    updated = SupportedVolumes;
    if ( SupportedVolumes )
      goto LABEL_51;
    v28 = v32 >= 0x2CB417800LL;
  }
  else
  {
    *(_BYTE *)(a1 + 18) = 0;
    v28 = 0;
  }
  *(_BYTE *)(a1 + 16) = v39;
  HbDrvUpdateAttachStates(*(_DWORD *)&PfSvcGlobals + 1576, (unsigned int)v59, v4, 0, 0);
  if ( (unsigned int)HbDrvGetAttachStateForVolume(v51, &v27) )
    v9 = IsSupportedHhd != 0 ? 2 : 0;
  else
    v9 = v27;
  v10 = *(unsigned __int8 *)(a1 + 18);
  v29 = v9;
  HbDrvUpdateCachingPriorityRegistryKeys(IsSupportedHhd, v10, v51, v9);
  v11 = IsSupportedHhd;
  if ( !v9 )
    goto LABEL_29;
  if ( v9 != 1 && v9 != 2 )
  {
    if ( v9 == 3 )
    {
      v11 = 1;
LABEL_30:
      v12 = 0;
      IsSupportedHhd = 0;
LABEL_31:
      if ( v4 )
      {
        updated = RegCreateKeyExW(
                    *(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL),
                    L"HybridDrivePerformance",
                    0,
                    0,
                    0,
                    0xF003Fu,
                    0,
                    &hKey,
                    0);
        SystemVolumeInfo = updated;
        if ( updated )
          goto LABEL_51;
        updated = HbDrvPerfResultRead((DWORD)hKey);
        SystemVolumeInfo = updated;
        if ( updated )
          goto LABEL_51;
        if ( HIWORD(v50) != 1 )
        {
          updated = HbDrvUpdateAttachStates(*(_DWORD *)&PfSvcGlobals + 1576, (unsigned int)v59, v4, updated + 3, 0);
          SystemVolumeInfo = updated;
          if ( updated )
            goto LABEL_51;
          v11 = 1;
          v50 = 65541;
          updated = PfsRegSetValue(hKey, L"DeviceTestInformation", 3, 12, &v49);
          SystemVolumeInfo = updated;
          if ( updated )
            goto LABEL_51;
        }
      }
      goto LABEL_37;
    }
    if ( v9 != 4 )
      goto LABEL_26;
LABEL_29:
    v11 = 0;
    goto LABEL_30;
  }
LABEL_26:
  v12 = IsSupportedHhd;
  if ( !IsSupportedHhd )
    goto LABEL_31;
LABEL_37:
  v27 = v11;
  PfTaskUpdateTaskSettings((__int64)L"HybridDriveCacheRebalance", (__int64)HbDrvTskSetEnabledCallback, (__int64)&v27);
  v27 = v12;
  PfTaskUpdateTaskSettings(
    (__int64)L"HybridDriveCachePrepopulate",
    (__int64)HbDrvTskSetEnabledIfMaintenanceCallback,
    (__int64)&v27);
  if ( !IsSupportedHhd )
  {
    SystemVolumeInfo = 1058;
    updated = 1058;
    goto LABEL_51;
  }
  v13 = StringCchPrintfW(pszDest, 0x104u, L"%s\\%s", *(_QWORD *)&PfSvcGlobals + 888LL, L"HybridDrive.vbm");
  if ( v13 < 0 )
  {
    SystemVolumeInfo = (unsigned __int16)v13;
    updated = (unsigned __int16)v13;
    goto LABEL_51;
  }
  v40 = v4;
  v38[0] = HbDrvAlwaysContinueCallback;
  v44 = 0;
  v41 = v59;
  v46 = *(unsigned __int8 *)(a1 + 18);
  v43 = 0;
  v45 = 0xFFFFFFFFLL;
  if ( (unsigned int)HbDrvDeserializeBitmaps(v38, pszDest, &v33, &v42) )
  {
    updated = HbDrvPrepareEmptyBitmaps((unsigned int)v38, (unsigned int)v59, v4, 0, (__int64)&v33, (__int64)&v42);
    SystemVolumeInfo = updated;
    if ( updated )
    {
      v3 = v33;
      goto LABEL_51;
    }
  }
  v3 = v33;
  HbDrvSetBitmaps(v38, v33);
  if ( !v28 )
  {
LABEL_48:
    SystemVolumeInfo = 0;
    updated = 0;
    goto LABEL_51;
  }
  updated = HbDrvEnableCsSupport();
  SystemVolumeInfo = updated;
  if ( !updated )
  {
    GetSystemTimeAsFileTime((LPFILETIME)(a1 + 24));
    v32 = PfsActionItemGetCurrentTime() + 144000000000LL;
    PfsActionItemQueueEx(v14 + 43);
    *(_BYTE *)(a1 + 17) |= 1u;
    goto LABEL_48;
  }
LABEL_51:
  v15 = (_DWORD *)v37;
  *(_DWORD *)v37 = 0;
  if ( IsSupportedHhd )
  {
    if ( v30 )
      goto LABEL_57;
    PfsRegSetValue(*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1432LL), L"HybridDriveEnabled", 4, 4, &IsSupportedHhd);
  }
  else
  {
    if ( !v30 )
      goto LABEL_57;
    RegDeleteValueW(*(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL), L"HybridDriveEnabled");
  }
  *v15 = 1;
LABEL_57:
  HbDrvVolumeInfoCleanup(v51);
  PfDiContextCleanup(&v47);
  if ( v3 )
  {
    v16 = v42;
    v17 = 0;
    if ( v42 )
    {
      v18 = v3 + 24;
      do
      {
        v19 = &v18[104 * v17];
        if ( *((_QWORD *)v19 + 1) )
        {
          for ( i = 0; (unsigned int)i < *((_DWORD *)v19 + 13); i = (unsigned int)(i + 1) )
          {
            if ( (unsigned __int8)RtlpSparseBitmapCheckRangeArrayPage(v19, (unsigned int)i) )
            {
              v21 = *(_QWORD *)(*((_QWORD *)v19 + 1) + 8 * i);
              if ( v21 )
                (*((void (__fastcall **)(__int64))v19 + 5))(v21);
            }
            else
            {
              LODWORD(i) = i + 511;
            }
          }
          RtlpSparseBitmapRangeArrayCleanup(v19, *((_QWORD *)v19 + 1), *((_QWORD *)v19 + 3));
          v18 = v3 + 24;
        }
        ++v17;
      }
      while ( v17 < v16 );
      v4 = v31;
    }
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v3);
  }
  v22 = 0;
  if ( v4 )
  {
    do
      HbDrvVolumeInfoCleanup(&v59[3 * v22++]);
    while ( v22 < v4 );
    SystemVolumeInfo = updated;
  }
  if ( Handle )
    NtClose(Handle);
  if ( lpMem )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, lpMem);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (unsigned int)dword_1800D2258 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D2258, 0x400000000000LL) )
  {
    v28 = IsSupportedHhd;
    *((_QWORD *)&v52 + 1) = v23;
    *(_QWORD *)&v52 = &v28;
    v27 = v29;
    v53 = &v27;
    v55 = &v29;
    v57 = &v37;
    v54 = v23;
    v56 = v23;
    v29 = SystemVolumeInfo;
    v37 = 0x1000000;
    v58 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800D2258, byte_1800C641D, 0, 0, 6, v51);
  }
  return SystemVolumeInfo;
}

```

## disassembly

```asm
0x1800a6758  mov     [rsp-8+arg_10], rbx
0x1800a675d  push    rbp
0x1800a675e  push    rsi
0x1800a675f  push    rdi
0x1800a6760  push    r12
0x1800a6762  push    r13
0x1800a6764  push    r14
0x1800a6766  push    r15
0x1800a6768  lea     rbp, [rsp-1200h]
0x1800a6770  mov     eax, 1300h
0x1800a6775  call    _alloca_probe
0x1800a677a  sub     rsp, rax
0x1800a677d  mov     rax, cs:__security_cookie
0x1800a6784  xor     rax, rsp
0x1800a6787  mov     [rbp+1230h+var_40], rax
0x1800a678e  xor     r12d, r12d
0x1800a6791  mov     [rbp+1230h+var_1298], rdx
0x1800a6795  xorps   xmm0, xmm0
0x1800a6798  mov     [rsp+1330h+var_12DC], r12d
0x1800a679d  xor     eax, eax
0x1800a679f  mov     [rsp+1330h+var_12C0], r12
0x1800a67a4  mov     rsi, rcx
0x1800a67a7  mov     [rbp+1230h+var_440], rax
0x1800a67ae  xor     edx, edx; Val
0x1800a67b0  mov     [rbp+1230h+var_438], eax
0x1800a67b6  lea     rcx, [rbp+1230h+var_1290]; void *
0x1800a67ba  mov     [rsp+1330h+var_12D8], r12d
0x1800a67bf  mov     r8d, 0E50h; Size
0x1800a67c5  mov     [rsp+1330h+var_12D0], r12d
0x1800a67ca  mov     [rsp+1330h+var_12C8], r12d
0x1800a67cf  mov     r13d, r12d
0x1800a67d2  mov     [rbp+1230h+Handle], r12
0x1800a67d6  mov     r15d, r12d
0x1800a67d9  mov     [rsp+1330h+var_12B8], r12
0x1800a67de  mov     [rbp+1230h+lpMem], r12
0x1800a67e2  mov     [rbp+1230h+hKey], r12
0x1800a67e6  mov     [rsp+1330h+var_12C4], r12d
0x1800a67eb  mov     [rsp+1330h+var_12CC], r12d
0x1800a67f0  movups  [rbp+1230h+var_430], xmm0
0x1800a67f7  movups  [rbp+1230h+var_420], xmm0
0x1800a67fe  movups  [rbp+1230h+var_410], xmm0
0x1800a6805  call    memset_0
0x1800a680a  xorps   xmm0, xmm0
0x1800a680d  lea     rcx, [rbp+1230h+pszDest]; void *
0x1800a6814  xor     eax, eax
0x1800a6816  xor     edx, edx; Val
0x1800a6818  mov     r8d, 208h; Size
0x1800a681e  mov     [rbp+1230h+var_450], rax
0x1800a6825  movups  [rbp+1230h+var_460], xmm0
0x1800a682c  call    memset_0
0x1800a6831  xor     edx, edx; Val
0x1800a6833  lea     rcx, [rbp+1230h+var_3D0]; void *
0x1800a683a  mov     r8d, 180h; Size
0x1800a6840  call    memset_0
0x1800a6845  mov     rcx, cs:PfSvcGlobals
0x1800a684c  lea     r9d, [r12+4]
0x1800a6851  lea     rax, [rsp+1330h+var_12C8]
0x1800a6856  mov     r8d, r9d
0x1800a6859  lea     rdx, aHybriddriveena; "HybridDriveEnabled"
0x1800a6860  mov     qword ptr [rsp+1330h+dwOptions], rax
0x1800a6865  mov     rcx, [rcx+598h]
0x1800a686c  call    PfsRegQueryValue
0x1800a6871  test    eax, eax
0x1800a6873  jz      short loc_1800A687A
0x1800a6875  mov     [rsp+1330h+var_12C8], r12d
0x1800a687a  mov     edx, 0C0000000h
0x1800a687f  lea     rcx, [rbp+1230h+Handle]
0x1800a6883  call    cs:__imp_SmuGetControlDeviceHandle
0x1800a6889  mov     r14d, 1
0x1800a688f  test    eax, eax
0x1800a6891  js      loc_1800A6CEE
0x1800a6897  cmp     [rbp+1230h+Handle], r12
0x1800a689b  jz      loc_1800A6CEE
0x1800a68a1  mov     rcx, cs:PfSvcGlobals
0x1800a68a8  lea     rdx, [rbp+1230h+var_430]
0x1800a68af  add     rcx, 628h
0x1800a68b6  call    HbDrvGetSystemVolumeInfo
0x1800a68bb  mov     ebx, eax
0x1800a68bd  test    eax, eax
0x1800a68bf  jz      short loc_1800A68D5
0x1800a68c1  cmp     ebx, 32h ; '2'
0x1800a68c4  mov     eax, 422h
0x1800a68c9  cmovz   ebx, eax
0x1800a68cc  mov     [rsp+1330h+var_12E0], ebx
0x1800a68d0  jmp     loc_1800A6CF9
0x1800a68d5  mov     rcx, qword ptr [rbp+1230h+var_430+8]
0x1800a68dc  mov     rax, [rcx+10h]
0x1800a68e0  lock add [rax+14h], r14d
0x1800a68e5  mov     rax, [rcx+10h]
0x1800a68e9  lea     r9, [rbp+1230h+var_1278]
0x1800a68ed  mov     [rsi+8], rax
0x1800a68f1  lea     r8, [rsp+1330h+var_12C0]
0x1800a68f6  mov     rax, qword ptr [rbp+1230h+var_430]
0x1800a68fd  lea     rdx, [rbp+1230h+lpMem]
0x1800a6901  mov     [rsi], rax
0x1800a6904  lea     rcx, [rbp+1230h+var_430]
0x1800a690b  lea     rax, [rsp+1330h+var_12D0]
0x1800a6910  mov     qword ptr [rsp+1330h+dwOptions], rax
0x1800a6915  call    HbDrvIsSupportedHhd
0x1800a691a  mov     [rsp+1330h+var_12DC], eax
0x1800a691e  test    eax, eax
0x1800a6920  jz      short loc_1800A699D
0x1800a6922  mov     rdx, [rbp+1230h+lpMem]
0x1800a6926  mov     rdi, 2CB417800h
0x1800a6930  cmp     [rsp+1330h+var_12C0], rdi
0x1800a6935  jnb     short loc_1800A6948
0x1800a6937  movzx   eax, byte ptr [rdx+2Ch]
0x1800a693b  mov     ecx, 3
0x1800a6940  cmp     [rdx+2Ch], cl
0x1800a6943  cmovb   ecx, eax
0x1800a6946  jmp     short loc_1800A694B
0x1800a6948  mov     cl, [rdx+2Ch]
0x1800a694b  mov     [rsi+12h], cl
0x1800a694e  lea     rax, [rsp+1330h+var_12C4]
0x1800a6953  mov     rdx, cs:PfSvcGlobals
0x1800a695a  lea     r8, [rbp+1230h+var_3D0]
0x1800a6961  add     rdx, 628h
0x1800a6968  mov     qword ptr [rsp+1330h+dwOptions], rax
0x1800a696d  lea     rcx, [rbp+1230h+var_430]
0x1800a6974  call    HbDrvGetSupportedVolumes
0x1800a6979  mov     r15d, [rsp+1330h+var_12C4]
0x1800a697e  mov     ebx, eax
0x1800a6980  mov     [rsp+1330h+var_12E0], eax
0x1800a6984  test    eax, eax
0x1800a6986  jnz     loc_1800A6CFE
0x1800a698c  cmp     [rsp+1330h+var_12C0], rdi
0x1800a6991  mov     ebx, r12d
0x1800a6994  setnb   bl
0x1800a6997  mov     [rsp+1330h+var_12D0], ebx
0x1800a699b  jmp     short loc_1800A69A6
0x1800a699d  mov     [rsi+12h], r12b
0x1800a69a1  mov     [rsp+1330h+var_12D0], r12d
0x1800a69a6  mov     al, [rbp+1230h+var_1278]
0x1800a69a9  lea     rdx, [rbp+1230h+var_3D0]
0x1800a69b0  mov     [rsi+10h], al
0x1800a69b3  xor     r9d, r9d
0x1800a69b6  mov     rcx, cs:PfSvcGlobals
0x1800a69bd  mov     r8d, r15d
0x1800a69c0  add     rcx, 628h
0x1800a69c7  mov     [rsp+1330h+dwOptions], r12d
0x1800a69cc  call    HbDrvUpdateAttachStates
0x1800a69d1  lea     rdx, [rsp+1330h+var_12D8]
0x1800a69d6  lea     rcx, [rbp+1230h+var_430]
0x1800a69dd  call    HbDrvGetAttachStateForVolume
0x1800a69e2  mov     ecx, [rsp+1330h+var_12DC]
0x1800a69e6  test    eax, eax
0x1800a69e8  jz      short loc_1800A69F7
0x1800a69ea  mov     eax, ecx
0x1800a69ec  neg     eax
0x1800a69ee  sbb     r12d, r12d
0x1800a69f1  and     r12d, 2
0x1800a69f5  jmp     short loc_1800A69FC
0x1800a69f7  mov     r12d, [rsp+1330h+var_12D8]
0x1800a69fc  movzx   edx, byte ptr [rsi+12h]
0x1800a6a00  lea     r8, [rbp+1230h+var_430]
0x1800a6a07  mov     r9d, r12d
0x1800a6a0a  mov     [rsp+1330h+var_12CC], r12d
0x1800a6a0f  call    HbDrvUpdateCachingPriorityRegistryKeys
0x1800a6a14  mov     edi, [rsp+1330h+var_12DC]
0x1800a6a18  mov     ecx, r12d
0x1800a6a1b  xor     r12d, r12d
0x1800a6a1e  test    ecx, ecx
0x1800a6a20  jz      short loc_1800A6A48
0x1800a6a22  sub     ecx, r14d
0x1800a6a25  jz      short loc_1800A6A36
0x1800a6a27  sub     ecx, r14d
0x1800a6a2a  jz      short loc_1800A6A36
0x1800a6a2c  sub     ecx, r14d
0x1800a6a2f  jz      short loc_1800A6A43
0x1800a6a31  cmp     ecx, r14d
0x1800a6a34  jz      short loc_1800A6A48
0x1800a6a36  mov     r14d, edi
0x1800a6a39  test    edi, edi
0x1800a6a3b  jnz     loc_1800A6B44
0x1800a6a41  jmp     short loc_1800A6A53
0x1800a6a43  mov     edi, r14d
0x1800a6a46  jmp     short loc_1800A6A4B
0x1800a6a48  mov     edi, r12d
0x1800a6a4b  mov     r14d, r12d
0x1800a6a4e  mov     [rsp+1330h+var_12DC], r12d
0x1800a6a53  test    r15d, r15d
0x1800a6a56  jz      loc_1800A6B44
0x1800a6a5c  mov     rcx, cs:PfSvcGlobals
0x1800a6a63  lea     rax, [rbp+1230h+hKey]
0x1800a6a67  mov     [rsp+1330h+lpdwDisposition], r12; lpdwDisposition
0x1800a6a6c  lea     rdx, aHybriddriveper; "HybridDrivePerformance"
0x1800a6a73  mov     [rsp+1330h+phkResult], rax; phkResult
0x1800a6a78  xor     r9d, r9d; lpClass
0x1800a6a7b  mov     [rsp+1330h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800a6a80  xor     r8d, r8d; Reserved
0x1800a6a83  mov     rcx, [rcx+598h]; hKey
0x1800a6a8a  mov     [rsp+1330h+samDesired], 0F003Fh; samDesired
0x1800a6a92  mov     [rsp+1330h+dwOptions], r12d; dwOptions
0x1800a6a97  call    cs:__imp_RegCreateKeyExW
0x1800a6a9d  mov     [rsp+1330h+var_12E0], eax
0x1800a6aa1  mov     ebx, eax
0x1800a6aa3  test    eax, eax
0x1800a6aa5  jnz     loc_1800A6B8F
0x1800a6aab  mov     rcx, [rbp+1230h+hKey]; dwOptions
0x1800a6aaf  lea     rdx, [rbp+1230h+var_440]
0x1800a6ab6  call    HbDrvPerfResultRead
0x1800a6abb  mov     [rsp+1330h+var_12E0], eax
0x1800a6abf  mov     ebx, eax
0x1800a6ac1  test    eax, eax
0x1800a6ac3  jnz     loc_1800A6B8F
0x1800a6ac9  lea     eax, [rbx+1]
0x1800a6acc  cmp     word ptr [rbp+1230h+var_438+2], ax
0x1800a6ad3  jz      short loc_1800A6B44
0x1800a6ad5  mov     rcx, cs:PfSvcGlobals
0x1800a6adc  lea     r9d, [rbx+3]
0x1800a6ae0  add     rcx, 628h
0x1800a6ae7  mov     [rsp+1330h+dwOptions], r12d
0x1800a6aec  mov     r8d, r15d
0x1800a6aef  lea     rdx, [rbp+1230h+var_3D0]
0x1800a6af6  call    HbDrvUpdateAttachStates
0x1800a6afb  mov     [rsp+1330h+var_12E0], eax
0x1800a6aff  mov     ebx, eax
0x1800a6b01  test    eax, eax
0x1800a6b03  jnz     loc_1800A6B8F
0x1800a6b09  mov     rcx, [rbp+1230h+hKey]
0x1800a6b0d  lea     edi, [rax+1]
0x1800a6b10  lea     rax, [rbp+1230h+var_440]
0x1800a6b17  mov     [rbp+1230h+var_438], 10005h
0x1800a6b21  lea     r9d, [rbx+0Ch]
0x1800a6b25  mov     qword ptr [rsp+1330h+dwOptions], rax
0x1800a6b2a  lea     r8d, [rbx+3]
0x1800a6b2e  lea     rdx, aDevicetestinfo; "DeviceTestInformation"
0x1800a6b35  call    PfsRegSetValue
0x1800a6b3a  mov     [rsp+1330h+var_12E0], eax
0x1800a6b3e  mov     ebx, eax
0x1800a6b40  test    eax, eax
0x1800a6b42  jnz     short loc_1800A6B8F
0x1800a6b44  lea     r8, [rsp+1330h+var_12D8]
0x1800a6b49  mov     [rsp+1330h+var_12D8], edi
0x1800a6b4d  lea     rdx, ?HbDrvTskSetEnabledCallback@@YAJPEAUITaskSettings3@@PEAUIMaintenanceSettings@@PEAKPEAX@Z; HbDrvTskSetEnabledCallback(ITaskSettings3 *,IMaintenanceSettings *,ulong *,void *)
0x1800a6b54  lea     rcx, aHybriddrivecac_0; "HybridDriveCacheRebalance"
0x1800a6b5b  call    PfTaskUpdateTaskSettings
0x1800a6b60  lea     r8, [rsp+1330h+var_12D8]
0x1800a6b65  mov     [rsp+1330h+var_12D8], r14d
0x1800a6b6a  lea     rdx, ?HbDrvTskSetEnabledIfMaintenanceCallback@@YAJPEAUITaskSettings3@@PEAUIMaintenanceSettings@@PEAKPEAX@Z; HbDrvTskSetEnabledIfMaintenanceCallback(ITaskSettings3 *,IMaintenanceSettings *,ulong *,void *)
0x1800a6b71  lea     rcx, aHybriddrivecac; "HybridDriveCachePrepopulate"
0x1800a6b78  call    PfTaskUpdateTaskSettings
0x1800a6b7d  cmp     [rsp+1330h+var_12DC], r12d
0x1800a6b82  jnz     short loc_1800A6B9A
0x1800a6b84  mov     eax, 422h
0x1800a6b89  mov     ebx, eax
0x1800a6b8b  mov     [rsp+1330h+var_12E0], eax
0x1800a6b8f  mov     r14d, 1
0x1800a6b95  jmp     loc_1800A6CFE
0x1800a6b9a  mov     r9, cs:PfSvcGlobals
0x1800a6ba1  lea     rax, aHybriddriveVbm; "HybridDrive.vbm"
0x1800a6ba8  add     r9, 378h
0x1800a6baf  mov     qword ptr [rsp+1330h+dwOptions], rax
0x1800a6bb4  lea     r8, aSS; "%s\\%s"
0x1800a6bbb  mov     edx, 104h; cchDest
0x1800a6bc0  lea     rcx, [rbp+1230h+pszDest]; pszDest
0x1800a6bc7  call    StringCchPrintfW
0x1800a6bcc  test    eax, eax
0x1800a6bce  jns     short loc_1800A6BD9
0x1800a6bd0  movzx   ebx, ax
0x1800a6bd3  mov     [rsp+1330h+var_12E0], ebx
0x1800a6bd7  jmp     short loc_1800A6B8F
0x1800a6bd9  lea     rax, HbDrvAlwaysContinueCallback
0x1800a6be0  mov     [rbp+1230h+var_1274], r15d
0x1800a6be4  mov     [rbp+1230h+var_1290], rax
0x1800a6be8  lea     r9, [rbp+1230h+var_1268]
0x1800a6bec  lea     rax, [rbp+1230h+var_3D0]
0x1800a6bf3  mov     [rbp+1230h+var_1258], r12
0x1800a6bf7  mov     [rbp+1230h+var_1270], rax
0x1800a6bfb  lea     r8, [rsp+1330h+var_12B8]
0x1800a6c00  movzx   eax, byte ptr [rsi+12h]
0x1800a6c04  lea     rdx, [rbp+1230h+pszDest]
0x1800a6c0b  mov     [rbp+1230h+var_468], eax
0x1800a6c11  lea     rcx, [rbp+1230h+var_1290]
0x1800a6c15  mov     eax, 0FFFFFFFFh
0x1800a6c1a  mov     [rbp+1230h+var_1260], r12
0x1800a6c1e  mov     [rbp+1230h+var_470], rax
0x1800a6c25  call    HbDrvDeserializeBitmaps
0x1800a6c2a  test    eax, eax
0x1800a6c2c  jz      short loc_1800A6C6B
0x1800a6c2e  lea     rax, [rbp+1230h+var_1268]
0x1800a6c32  xor     r9d, r9d
0x1800a6c35  mov     qword ptr [rsp+1330h+samDesired], rax
0x1800a6c3a  lea     rdx, [rbp+1230h+var_3D0]
0x1800a6c41  lea     rax, [rsp+1330h+var_12B8]
0x1800a6c46  mov     r8d, r15d
0x1800a6c49  lea     rcx, [rbp+1230h+var_1290]
0x1800a6c4d  mov     qword ptr [rsp+1330h+dwOptions], rax
0x1800a6c52  call    HbDrvPrepareEmptyBitmaps
0x1800a6c57  mov     [rsp+1330h+var_12E0], eax
0x1800a6c5b  mov     ebx, eax
0x1800a6c5d  test    eax, eax
0x1800a6c5f  jz      short loc_1800A6C6B
0x1800a6c61  mov     r13, [rsp+1330h+var_12B8]
0x1800a6c66  jmp     loc_1800A6B8F
0x1800a6c6b  mov     r13, [rsp+1330h+var_12B8]
0x1800a6c70  lea     rcx, [rbp+1230h+var_1290]
0x1800a6c74  mov     rdx, r13
0x1800a6c77  call    HbDrvSetBitmaps
0x1800a6c7c  cmp     [rsp+1330h+var_12D0], r12d
  ... truncated ...
```
