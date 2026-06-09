# AsrVhd::DiskBuildVhdInfo(ushort const *,ulong,_ASR_VIRTUAL_DISK_INFO * *)

- ea: `0x14005a294`
- end: `0x14005a8e6`
- name: `?DiskBuildVhdInfo@AsrVhd@@SAHPEBGKPEAPEAU_ASR_VIRTUAL_DISK_INFO@@@Z`
- size: `1618`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct _ASR_VIRTUAL_DISK_INFO **)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005c798`

## callees

- `0x140021ca0`
- `0x140021f14`
- `0x1400227a0`
- `0x1400235a8`
- `0x140025abc`
- `0x140025b00`
- `0x140059484`
- `0x14005a294`
- `0x14005a8ec`
- `0x14005ab34`
- `0x14005b208`
- `0x140091560`
- `0x1400916f0`
- `0x1400921dc`
- `0x1400d257c`
- `0x1400d26c8`
- `0x1400d3198`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14005a5e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14005a64a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14005a5e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14005a64a`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x14005a86d`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x14005a86d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005a8b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005a8b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a7c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a7ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a80f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a7c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a7ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a80f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x14005a6f5`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x14005a6f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a5a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a5af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a88d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a8a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a5a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a5af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a88d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a8a0`

## string_xrefs

- `0x14005a3a2`: `::StringCchCopy( STRING_CCH_PARAM( wszVolume ), wszDevicePath )`

## pseudocode

```c
__int64 __fastcall AsrVhd::DiskBuildVhdInfo(const unsigned __int16 *a1, __int64 a2, struct _ASR_VIRTUAL_DISK_INFO **a3)
{
  unsigned int v5; // ebx
  struct _STORAGE_DEPENDENCY_INFO *v6; // r15
  unsigned int v7; // esi
  DWORD LastError; // edi
  struct _DRIVE_LAYOUT_INFORMATION_EX *v9; // rcx
  int v10; // edx
  int v11; // r9d
  const char *v12; // rax
  unsigned __int16 *v13; // r13
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  DWORD v17; // eax
  int v18; // edx
  const char *v19; // rcx
  DWORD v20; // eax
  struct _ASR_VIRTUAL_DISK_INFO *v21; // rax
  struct _ASR_VIRTUAL_DISK_INFO *v22; // r14
  void *v23; // rax
  unsigned __int16 *v24; // r12
  unsigned __int64 v25; // r12
  __int64 v26; // r13
  __int64 v27; // rdx
  const unsigned __int16 *v28; // rbx
  __int64 v29; // r8
  __int64 v30; // r13
  unsigned __int64 v31; // rdx
  __int64 v32; // rax
  char v33; // al
  unsigned __int16 *pv; // [rsp+40h] [rbp-C0h]
  struct _STORAGE_DEPENDENCY_INFO *v36; // [rsp+48h] [rbp-B8h] BYREF
  struct _ASR_VIRTUAL_DISK_INFO *v37; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v38; // [rsp+58h] [rbp-A8h]
  struct _ASR_VIRTUAL_DISK_INFO **v39; // [rsp+60h] [rbp-A0h]
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF

  v39 = a3;
  TraceFunctionEnter(L"AsrVhd::DiskBuildVhdInfo");
  v5 = 0;
  v37 = 0;
  v36 = 0;
  pv = 0;
  v6 = 0;
  memset_0(FileName, 0, 0x20Au);
  if ( !a3 )
  {
    v7 = 0;
    LastError = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_6;
    }
    v10 = 52;
    v11 = 87;
    v12 = "ppVirtualDiskInfo";
    goto LABEL_5;
  }
  *a3 = 0;
  v14 = StringCchCopyW(FileName, 0x105u, a1);
  if ( v14 < 0 )
  {
    v7 = 0;
    LastError = WIN32_FROM_HRESULT((unsigned int)v14);
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v15 = StringCchCopyW(FileName, 0x105u, a1);
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        53,
        (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
        v15,
        "::StringCchCopy( STRING_CCH_PARAM( wszVolume ), wszDevicePath )");
    }
    goto LABEL_6;
  }
  v16 = -1;
  do
    ++v16;
  while ( FileName[v16] );
  if ( !(_DWORD)v16 )
  {
    v7 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v17 = GetLastError();
      v18 = 54;
      v19 = "ulLen > 0";
      goto LABEL_17;
    }
    goto LABEL_6;
  }
  if ( FileName[(unsigned int)(v16 - 1)] == 92 )
  {
    if ( 2 * (unsigned __int64)(unsigned int)(v16 - 1) >= 0x20A )
      _report_rangecheckfailure();
    FileName[(unsigned int)(v16 - 1)] = 0;
  }
  v7 = 1;
  if ( !(unsigned int)AsrVhd::GetDeviceDependencyInformation(FileName, 1u, STORAGE_DEPENDENCY_INFO_VERSION_2, &v36) )
  {
    v7 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v20 = GetLastError();
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        55,
        (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
        v20,
        "GetDeviceDependencyInformation( wszVolume, TRUE, STORAGE_DEPENDENCY_INFO_VERSION_2, &pVhdInfo )");
    }
    v6 = v36;
    goto LABEL_6;
  }
  v6 = v36;
  LastError = 0;
  if ( !v36 )
  {
    v13 = 0;
    goto LABEL_71;
  }
  v21 = (struct _ASR_VIRTUAL_DISK_INFO *)ASR_ALLOC(0x10u);
  v37 = v21;
  v22 = v21;
  if ( !v21 )
  {
    v11 = 14;
    v7 = 0;
    LastError = 14;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_6;
    }
    v10 = 56;
    v12 = "pVirtualDiskInfo";
    goto LABEL_5;
  }
  *((_DWORD *)v21 + 3) = 0;
  v23 = ASR_ALLOC(32 * v6->NumberEntries);
  *(_QWORD *)v22 = v23;
  if ( !v23 )
  {
    v11 = 14;
    v7 = 0;
    LastError = 14;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_6;
    }
    v10 = 57;
    v12 = "pVirtualDiskInfo->m_rgVhdFileInfo";
LABEL_5:
    WPP_SF_Ds(
      *(_QWORD *)v9->Gpt.DiskId.Data4,
      v10,
      (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
      v11,
      v12);
    goto LABEL_6;
  }
  v24 = 0;
  *((_DWORD *)v22 + 2) = v6->NumberEntries;
  while ( 1 )
  {
    LODWORD(v36) = v5;
    if ( v5 >= v6->NumberEntries )
    {
      qsort(*(void **)v22, *((unsigned int *)v22 + 2), 0x20u, AsrVhd::CompareSequence);
      v37 = 0;
      *v39 = v22;
      goto LABEL_69;
    }
    CoTaskMemFree(pv);
    CoTaskMemFree(v24);
    v25 = (unsigned __int64)v5 << 6;
    v26 = v5;
    v38 = v25;
    v27 = *(__int64 *)((char *)&v6->Version2Entries[0].HostVolumeName + v25);
    v28 = *(PWSTR *)((char *)&v6->Version2Entries[0].DependentVolumeRelativePath + v25);
    if ( !v27 )
      goto LABEL_74;
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)(v27 + 2 * v29) );
    if ( (unsigned int)_o__wcsnicmp(
                         *(PWSTR *)((char *)&v6->Version2Entries[0].DependentVolumeRelativePath + v25),
                         v27,
                         v29) )
    {
      v24 = SafeStrJoin(*(const unsigned __int16 **)((char *)&v6->Version2Entries[0].HostVolumeName + v25), v28);
      if ( !v24 )
      {
        v11 = 14;
        v7 = 0;
        LastError = 14;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
        {
          goto LABEL_6;
        }
        v10 = 60;
LABEL_51:
        v12 = "wszVhdFileNameModified";
        goto LABEL_5;
      }
    }
    else
    {
LABEL_74:
      if ( (unsigned int)_o__wcsnicmp(L"\\Device\\", v28, 8) )
      {
        v24 = SafeStrClone(v28);
        if ( !v24 )
        {
          v11 = 14;
          v7 = 0;
          LastError = 14;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
          {
            goto LABEL_6;
          }
          v10 = 59;
          goto LABEL_51;
        }
      }
      else
      {
        v24 = SafeStrJoin(L"\\\\?\\GlobalRoot", v28);
        if ( !v24 )
        {
          v11 = 14;
          v7 = 0;
          LastError = 14;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
          {
            goto LABEL_6;
          }
          v10 = 58;
          goto LABEL_51;
        }
      }
    }
    v30 = 32 * v26;
    if ( !(unsigned int)GetVolumeNameAndRelativeFilePath(
                          v24,
                          (unsigned __int16 **)(v30 + *(_QWORD *)v22),
                          (unsigned __int16 **)(v30 + *(_QWORD *)v22 + 8)) )
      break;
    pv = SafeStrJoin(*(const unsigned __int16 **)(*(_QWORD *)v22 + v30), L"\\");
    if ( GetDriveTypeW(pv) != 3 )
    {
      v7 = 0;
      LastError = 50;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v32 = *(_QWORD *)(*(_QWORD *)v22 + v30 + 8);
        v13 = pv;
        WPP_SF_DsSS(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          63,
          (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
          50,
          (__int64)"ERROR_NOT_SUPPORTED",
          (__int64)pv,
          v32);
        goto LABEL_71;
      }
LABEL_69:
      v13 = pv;
      goto LABEL_71;
    }
    v31 = v38;
    v5 = (_DWORD)v36 + 1;
    *(_WORD *)(*(_QWORD *)(*(_QWORD *)v22 + v30) + 2LL) = 63;
    *(_DWORD *)(*(_QWORD *)v22 + v30 + 20) = 0x200000;
    *(_DWORD *)(*(_QWORD *)v22 + v30 + 16) = *(DEPENDENT_DISK_FLAG *)((char *)&v6->Version1Entries[0].DependencyTypeFlags
                                                                    + v31);
    *(_DWORD *)(*(_QWORD *)v22 + v30 + 24) = *(ULONG *)((char *)&v6->Version2Entries[0].AncestorLevel + v31);
  }
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
  {
    v33 = GetLastError();
    WPP_SF_SD(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      61,
      (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
      (_DWORD)v24,
      v33);
  }
  v7 = 0;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    v17 = GetLastError();
    v18 = 62;
    v19 = "GetLastError()";
LABEL_17:
    WPP_SF_Ds(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      v18,
      (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
      v17,
      v19);
  }
LABEL_6:
  v13 = 0;
LABEL_71:
  CoTaskMemFree(v13);
  AsrFreeVirtualDiskInfo(&v37);
  CoTaskMemFree(v6);
  TraceFunctionExit(L"AsrVhd::DiskBuildVhdInfo");
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x14005a294  mov     [rsp-8+arg_8], rbx
0x14005a299  push    rbp
0x14005a29a  push    rsi
0x14005a29b  push    rdi
0x14005a29c  push    r12
0x14005a29e  push    r13
0x14005a2a0  push    r14
0x14005a2a2  push    r15
0x14005a2a4  lea     rbp, [rsp-190h]
0x14005a2ac  sub     rsp, 290h
0x14005a2b3  mov     rax, cs:__security_cookie
0x14005a2ba  xor     rax, rsp
0x14005a2bd  mov     [rbp+1C0h+var_40], rax
0x14005a2c4  mov     r13, r8
0x14005a2c7  mov     [rsp+2C0h+var_260], r8
0x14005a2cc  mov     r14, rcx
0x14005a2cf  lea     rcx, aAsrvhdDiskbuil; "AsrVhd::DiskBuildVhdInfo"
0x14005a2d6  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x14005a2db  xor     ebx, ebx
0x14005a2dd  lea     rcx, [rsp+2C0h+FileName]; void *
0x14005a2e2  mov     edi, 20Ah
0x14005a2e7  mov     [rsp+2C0h+var_270], rbx
0x14005a2ec  mov     r8d, edi; Size
0x14005a2ef  mov     [rsp+2C0h+var_278], rbx
0x14005a2f4  xor     edx, edx; Val
0x14005a2f6  mov     [rsp+2C0h+pv], rbx
0x14005a2fb  mov     r15d, ebx
0x14005a2fe  call    memset_0
0x14005a303  test    r13, r13
0x14005a306  jnz     short loc_14005A350
0x14005a308  mov     esi, ebx
0x14005a30a  lea     edi, [rbx+57h]
0x14005a30d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a314  lea     rbx, WPP_GLOBAL_Control
0x14005a31b  cmp     rcx, rbx
0x14005a31e  jz      short loc_14005A348
0x14005a320  test    byte ptr [rcx+1Ch], 8
0x14005a324  jz      short loc_14005A348
0x14005a326  lea     edx, [rdi-23h]
0x14005a329  mov     r9d, edi
0x14005a32c  lea     rax, aPpvirtualdiski; "ppVirtualDiskInfo"
0x14005a333  mov     [rsp+2C0h+var_2A0], rax
0x14005a338  mov     rcx, [rcx+10h]
0x14005a33c  lea     r8, WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids
0x14005a343  call    WPP_SF_Ds
0x14005a348  mov     r13, rsi
0x14005a34b  jmp     loc_14005A88A
0x14005a350  mov     r12d, 105h
0x14005a356  mov     [r13+0], rbx
0x14005a35a  mov     edx, r12d; unsigned __int64
0x14005a35d  lea     rcx, [rsp+2C0h+FileName]; unsigned __int16 *
0x14005a362  mov     r8, r14; unsigned __int16 *
0x14005a365  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14005a36a  test    eax, eax
0x14005a36c  jns     short loc_14005A3D2
0x14005a36e  mov     ecx, eax
0x14005a370  mov     esi, ebx
0x14005a372  call    WIN32_FROM_HRESULT
0x14005a377  mov     edi, eax
0x14005a379  mov     rax, cs:WPP_GLOBAL_Control
0x14005a380  lea     rbx, WPP_GLOBAL_Control
0x14005a387  cmp     rax, rbx
0x14005a38a  jz      short loc_14005A348
0x14005a38c  test    byte ptr [rax+1Ch], 8
0x14005a390  jz      short loc_14005A348
0x14005a392  mov     r8, r14; unsigned __int16 *
0x14005a395  lea     rcx, [rsp+2C0h+FileName]; unsigned __int16 *
0x14005a39a  mov     edx, r12d; unsigned __int64
0x14005a39d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14005a3a2  lea     rcx, aStringcchcopyS; "::StringCchCopy( STRING_CCH_PARAM( wszV"...
0x14005a3a9  mov     edx, 35h ; '5'
0x14005a3ae  mov     [rsp+2C0h+var_2A0], rcx
0x14005a3b3  lea     r8, WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids
0x14005a3ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a3c1  mov     r9d, eax
0x14005a3c4  mov     rcx, [rcx+10h]
0x14005a3c8  call    WPP_SF_Ds
0x14005a3cd  jmp     loc_14005A348
0x14005a3d2  lea     rcx, [rsp+2C0h+FileName]
0x14005a3d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005a3db  inc     rax
0x14005a3de  cmp     [rcx+rax*2], bx
0x14005a3e2  jnz     short loc_14005A3DB
0x14005a3e4  test    eax, eax
0x14005a3e6  jnz     short loc_14005A439
0x14005a3e8  mov     esi, ebx
0x14005a3ea  call    cs:__imp_GetLastError
0x14005a3f0  mov     edi, eax
0x14005a3f2  mov     rax, cs:WPP_GLOBAL_Control
0x14005a3f9  lea     rbx, WPP_GLOBAL_Control
0x14005a400  cmp     rax, rbx
0x14005a403  jz      loc_14005A348
0x14005a409  test    byte ptr [rax+1Ch], 8
0x14005a40d  jz      loc_14005A348
0x14005a413  call    cs:__imp_GetLastError
0x14005a419  mov     edx, 36h ; '6'
0x14005a41e  lea     rcx, aUllen0; "ulLen > 0"
0x14005a425  mov     [rsp+2C0h+var_2A0], rcx
0x14005a42a  mov     r9d, eax
0x14005a42d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a434  jmp     loc_14005A338
0x14005a439  lea     ecx, [rax-1]
0x14005a43c  add     rcx, rcx
0x14005a43f  cmp     [rsp+rcx+2C0h+FileName], 5Ch ; '\'
0x14005a445  jnz     short loc_14005A455
0x14005a447  cmp     rcx, rdi
0x14005a44a  jnb     loc_14005A4D2
0x14005a450  mov     [rsp+rcx+2C0h+FileName], bx
0x14005a455  mov     esi, 1
0x14005a45a  lea     r9, [rsp+2C0h+var_278]; struct _STORAGE_DEPENDENCY_INFO **
0x14005a45f  mov     dl, sil; unsigned __int8
0x14005a462  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x14005a467  lea     r8d, [rsi+1]; enum _STORAGE_DEPENDENCY_INFO_VERSION
0x14005a46b  call    ?GetDeviceDependencyInformation@AsrVhd@@SAHPEBGEW4_STORAGE_DEPENDENCY_INFO_VERSION@@PEAPEAU_STORAGE_DEPENDENCY_INFO@@@Z; AsrVhd::GetDeviceDependencyInformation(ushort const *,uchar,_STORAGE_DEPENDENCY_INFO_VERSION,_STORAGE_DEPENDENCY_INFO * *)
0x14005a470  test    eax, eax
0x14005a472  jnz     short loc_14005A4D8
0x14005a474  mov     esi, ebx
0x14005a476  call    cs:__imp_GetLastError
0x14005a47c  mov     edi, eax
0x14005a47e  mov     rax, cs:WPP_GLOBAL_Control
0x14005a485  lea     rbx, WPP_GLOBAL_Control
0x14005a48c  cmp     rax, rbx
0x14005a48f  jz      short loc_14005A4C8
0x14005a491  test    byte ptr [rax+1Ch], 8
0x14005a495  jz      short loc_14005A4C8
0x14005a497  call    cs:__imp_GetLastError
0x14005a49d  lea     rcx, aGetdevicedepen; "GetDeviceDependencyInformation( wszVolu"...
0x14005a4a4  mov     edx, 37h ; '7'
0x14005a4a9  mov     [rsp+2C0h+var_2A0], rcx
0x14005a4ae  lea     r8, WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids
0x14005a4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a4bc  mov     r9d, eax
0x14005a4bf  mov     rcx, [rcx+10h]
0x14005a4c3  call    WPP_SF_Ds
0x14005a4c8  mov     r15, [rsp+2C0h+var_278]
0x14005a4cd  jmp     loc_14005A348
0x14005a4d2  call    __report_rangecheckfailure
0x14005a4d8  mov     r15, [rsp+2C0h+var_278]
0x14005a4dd  mov     edi, ebx
0x14005a4df  test    r15, r15
0x14005a4e2  jz      loc_14005A887
0x14005a4e8  mov     ecx, 10h; Size
0x14005a4ed  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x14005a4f2  mov     [rsp+2C0h+var_270], rax
0x14005a4f7  mov     r14, rax
0x14005a4fa  test    rax, rax
0x14005a4fd  jnz     short loc_14005A538
0x14005a4ff  lea     r9d, [rax+0Eh]
0x14005a503  mov     esi, ebx
0x14005a505  mov     edi, r9d
0x14005a508  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a50f  lea     rbx, WPP_GLOBAL_Control
0x14005a516  cmp     rcx, rbx
0x14005a519  jz      loc_14005A348
0x14005a51f  test    byte ptr [rcx+1Ch], 8
0x14005a523  jz      loc_14005A348
0x14005a529  lea     edx, [rax+38h]
0x14005a52c  lea     rax, aPvirtualdiskin_0; "pVirtualDiskInfo"
0x14005a533  jmp     loc_14005A333
0x14005a538  mov     [rax+0Ch], ebx
0x14005a53b  mov     ecx, [r15+4]
0x14005a53f  shl     ecx, 5; Size
0x14005a542  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x14005a547  mov     [r14], rax
0x14005a54a  test    rax, rax
0x14005a54d  jnz     short loc_14005A588
0x14005a54f  lea     r9d, [rax+0Eh]
0x14005a553  mov     esi, ebx
0x14005a555  mov     edi, r9d
0x14005a558  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a55f  lea     rbx, WPP_GLOBAL_Control
0x14005a566  cmp     rcx, rbx
0x14005a569  jz      loc_14005A348
0x14005a56f  test    byte ptr [rcx+1Ch], 8
0x14005a573  jz      loc_14005A348
0x14005a579  lea     edx, [rax+39h]
0x14005a57c  lea     rax, aPvirtualdiskin; "pVirtualDiskInfo->m_rgVhdFileInfo"
0x14005a583  jmp     loc_14005A333
0x14005a588  mov     eax, [r15+4]
0x14005a58c  mov     r12, rbx
0x14005a58f  mov     [r14+8], eax
0x14005a593  mov     dword ptr [rsp+2C0h+var_278], ebx
0x14005a597  cmp     ebx, [r15+4]
0x14005a59b  jnb     loc_14005A859
0x14005a5a1  mov     rcx, [rsp+2C0h+pv]; pv
0x14005a5a6  call    cs:__imp_CoTaskMemFree
0x14005a5ac  mov     rcx, r12; pv
0x14005a5af  call    cs:__imp_CoTaskMemFree
0x14005a5b5  mov     r12d, ebx
0x14005a5b8  xor     eax, eax
0x14005a5ba  shl     r12, 6
0x14005a5be  mov     r13d, ebx
0x14005a5c1  mov     [rsp+2C0h+var_268], r12
0x14005a5c6  mov     rdx, [r12+r15+30h]
0x14005a5cb  mov     rbx, [r12+r15+40h]
0x14005a5d0  test    rdx, rdx
0x14005a5d3  jz      short loc_14005A63A
0x14005a5d5  or      r8, 0FFFFFFFFFFFFFFFFh
0x14005a5d9  inc     r8
0x14005a5dc  cmp     [rdx+r8*2], ax
0x14005a5e1  jnz     short loc_14005A5D9
0x14005a5e3  mov     rcx, rbx
0x14005a5e6  call    cs:__imp__o__wcsnicmp
0x14005a5ec  test    eax, eax
0x14005a5ee  jz      short loc_14005A63A
0x14005a5f0  mov     rcx, [r12+r15+30h]; unsigned __int16 *
0x14005a5f5  mov     rdx, rbx; unsigned __int16 *
0x14005a5f8  call    ?SafeStrJoin@@YAPEAGPEBG0@Z; SafeStrJoin(ushort const *,ushort const *)
0x14005a5fd  xor     ebx, ebx
0x14005a5ff  mov     r12, rax
0x14005a602  test    rax, rax
0x14005a605  jnz     loc_14005A6BC
0x14005a60b  lea     r9d, [rax+0Eh]
0x14005a60f  mov     esi, ebx
0x14005a611  mov     edi, r9d
0x14005a614  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a61b  lea     rbx, WPP_GLOBAL_Control
0x14005a622  cmp     rcx, rbx
0x14005a625  jz      loc_14005A348
0x14005a62b  test    byte ptr [rcx+1Ch], 8
0x14005a62f  jz      loc_14005A348
0x14005a635  lea     edx, [rax+3Ch]
0x14005a638  jmp     short loc_14005A69A
0x14005a63a  mov     r8d, 8
0x14005a640  lea     rcx, aDevice; "\\Device\\"
0x14005a647  mov     rdx, rbx
0x14005a64a  call    cs:__imp__o__wcsnicmp
0x14005a650  test    eax, eax
0x14005a652  jnz     short loc_14005A6A6
0x14005a654  mov     rdx, rbx; unsigned __int16 *
0x14005a657  lea     rcx, aGlobalroot; "\\\\?\\GlobalRoot"
0x14005a65e  call    ?SafeStrJoin@@YAPEAGPEBG0@Z; SafeStrJoin(ushort const *,ushort const *)
0x14005a663  xor     ebx, ebx
0x14005a665  mov     r12, rax
0x14005a668  test    rax, rax
0x14005a66b  jnz     short loc_14005A6BC
0x14005a66d  lea     r9d, [rax+0Eh]
0x14005a671  mov     esi, ebx
0x14005a673  mov     edi, r9d
0x14005a676  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a67d  lea     rbx, WPP_GLOBAL_Control
0x14005a684  cmp     rcx, rbx
0x14005a687  jz      loc_14005A348
0x14005a68d  test    byte ptr [rcx+1Ch], 8
0x14005a691  jz      loc_14005A348
0x14005a697  lea     edx, [rax+3Ah]
0x14005a69a  lea     rax, aWszvhdfilename; "wszVhdFileNameModified"
0x14005a6a1  jmp     loc_14005A333
0x14005a6a6  mov     rcx, rbx; unsigned __int16 *
0x14005a6a9  call    ?SafeStrClone@@YAPEAGPEBG@Z; SafeStrClone(ushort const *)
0x14005a6ae  xor     ebx, ebx
0x14005a6b0  mov     r12, rax
0x14005a6b3  test    rax, rax
0x14005a6b6  jz      loc_14005A824
0x14005a6bc  mov     rdx, [r14]
0x14005a6bf  mov     rcx, r12; unsigned __int16 *
0x14005a6c2  shl     r13, 5
0x14005a6c6  add     rdx, r13; unsigned __int16 **
0x14005a6c9  lea     r8, [rdx+8]; unsigned __int16 **
0x14005a6cd  call    ?GetVolumeNameAndRelativeFilePath@@YAHPEBGPEAPEAG1@Z; GetVolumeNameAndRelativeFilePath(ushort const *,ushort * *,ushort * *)
0x14005a6d2  test    eax, eax
0x14005a6d4  jz      loc_14005A7A9
0x14005a6da  mov     rcx, [r14]
0x14005a6dd  lea     rdx, pszSrc; "\\"
0x14005a6e4  mov     rcx, [rcx+r13]; unsigned __int16 *
0x14005a6e8  call    ?SafeStrJoin@@YAPEAGPEBG0@Z; SafeStrJoin(ushort const *,ushort const *)
0x14005a6ed  mov     rcx, rax; lpRootPathName
0x14005a6f0  mov     [rsp+2C0h+pv], rax
0x14005a6f5  call    cs:__imp_GetDriveTypeW
0x14005a6fb  cmp     eax, 3
0x14005a6fe  jnz     short loc_14005A743
0x14005a700  mov     rax, [r14]
0x14005a703  mov     rdx, [rsp+2C0h+var_268]
0x14005a708  mov     ebx, dword ptr [rsp+2C0h+var_278]
0x14005a70c  add     ebx, esi
0x14005a70e  mov     rcx, [rax+r13]
0x14005a712  mov     word ptr [rcx+2], 3Fh ; '?'
0x14005a718  mov     rax, [r14]
0x14005a71b  mov     dword ptr [rax+r13+14h], 200000h
0x14005a724  mov     rcx, [r14]
0x14005a727  mov     eax, [rdx+r15+8]
0x14005a72c  mov     [rcx+r13+10h], eax
0x14005a731  mov     rcx, [r14]
0x14005a734  mov     eax, [rdx+r15+24h]
0x14005a739  mov     [rcx+r13+18h], eax
0x14005a73e  jmp     loc_14005A593
0x14005a743  mov     esi, ebx
0x14005a745  mov     edi, 32h ; '2'
0x14005a74a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a751  lea     rbx, WPP_GLOBAL_Control
0x14005a758  cmp     rcx, rbx
0x14005a75b  jz      loc_14005A880
0x14005a761  test    byte ptr [rcx+1Ch], 8
0x14005a765  jz      loc_14005A880
0x14005a76b  mov     rax, [r14]
0x14005a76e  lea     edx, [rdi+0Dh]
0x14005a771  mov     rcx, [rcx+10h]
0x14005a775  lea     r8, WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids
0x14005a77c  mov     r9d, edi
0x14005a77f  mov     rax, [rax+r13+8]
  ... truncated ...
```
