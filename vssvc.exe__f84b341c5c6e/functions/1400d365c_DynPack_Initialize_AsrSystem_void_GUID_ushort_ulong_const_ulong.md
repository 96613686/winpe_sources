# DynPack::Initialize(AsrSystem *,void *,_GUID *,ushort *,ulong const *,ulong)

- ea: `0x1400d365c`
- end: `0x1400d3f68`
- name: `?Initialize@DynPack@@QEAAHPEAVAsrSystem@@PEAXPEAU_GUID@@PEAGPEBKK@Z`
- size: `2316`
- prototype: `int(DynPack *__hidden this, struct AsrSystem *, void *, struct _GUID *, unsigned __int16 *, const unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400d2d28`

## callees

- `0x140010170`
- `0x140021ca0`
- `0x1400235a8`
- `0x14005b208`
- `0x14007b664`
- `0x140091560`
- `0x1400919a0`
- `0x1400919c4`
- `0x1400d257c`
- `0x1400d3354`
- `0x1400d3544`
- `0x1400d3588`
- `0x1400d365c`
- `0x1400d4088`
- `0x1400d4e88`
- `0x1400d7c94`
- `0x1400d969c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d39af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3a9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d39af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3a9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d372e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d37da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d390c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d392d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d372e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d37da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d390c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d392d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d396d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d3976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d3981`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d396d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d3976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d3981`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DynPack::Initialize(
        DynPack *this,
        struct AsrSystem *a2,
        void *a3,
        struct _GUID *a4,
        unsigned __int16 *a5,
        const unsigned int *a6,
        unsigned int a7)
{
  void *v11; // r12
  DynDisk *v12; // r13
  DynVolume *v13; // rsi
  unsigned int v14; // ebx
  DWORD LastError; // edi
  DWORD v16; // eax
  _OWORD *v17; // rax
  DWORD v18; // eax
  unsigned __int64 v19; // rbx
  __int64 v20; // rax
  bool v21; // cf
  unsigned __int64 v22; // rax
  unsigned __int64 *v23; // rax
  unsigned int v24; // edi
  __int64 v25; // rsi
  _DWORD *v26; // rdx
  __int64 i; // rdx
  DWORD v28; // eax
  unsigned int v29; // edx
  int v31; // r14d
  __int64 v32; // rdi
  AsrSystem *v33; // r12
  int v34; // esi
  __int64 *j; // rax
  __int64 v36; // rdi
  DWORD v37; // eax
  int v38; // edx
  const char *v39; // rcx
  struct _ASR_DISK_INFO *v40; // rsi
  int v41; // eax
  int v42; // eax
  struct _GUID *v43; // r12
  unsigned __int64 v44; // rdi
  __int64 v45; // rax
  unsigned __int64 v46; // rax
  unsigned __int64 *v47; // rax
  unsigned int v48; // esi
  DynVolume *v49; // rdi
  _DWORD *v50; // rdx
  DWORD v51; // eax
  int v52; // r9d
  struct _DRIVE_LAYOUT_INFORMATION_EX *v53; // rax
  int v54; // edx
  const char *v55; // rcx
  int v56; // [rsp+28h] [rbp-A9h]
  void *v57; // [rsp+30h] [rbp-A1h] BYREF
  DynVolume *v58; // [rsp+38h] [rbp-99h]
  LPVOID v59; // [rsp+40h] [rbp-91h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-89h]
  LPVOID pv; // [rsp+50h] [rbp-81h] BYREF
  struct _ASR_DISK_INFO *v62; // [rsp+58h] [rbp-79h] BYREF
  struct _GUID *v63; // [rsp+60h] [rbp-71h]
  unsigned __int16 *v64; // [rsp+68h] [rbp-69h]
  AsrSystem *v65; // [rsp+70h] [rbp-61h]
  unsigned __int64 *v66; // [rsp+78h] [rbp-59h]
  struct _GUID InBuffer; // [rsp+80h] [rbp-51h] BYREF
  struct _GUID v68; // [rsp+90h] [rbp-41h] BYREF
  struct _GUID v69; // [rsp+A0h] [rbp-31h] BYREF
  unsigned __int16 v70[20]; // [rsp+B0h] [rbp-21h] BYREF

  v63 = a4;
  hDevice = a3;
  v65 = a2;
  v64 = a5;
  TraceFunctionEnter(L"DynPack::Initialize");
  v69 = 0;
  v59 = 0;
  InBuffer = 0;
  pv = 0;
  v68 = 0;
  v11 = 0;
  v57 = 0;
  v12 = 0;
  v13 = 0;
  v62 = 0;
  if ( !a2 )
  {
    v14 = 0;
    v52 = 87;
    LastError = 87;
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_35;
    }
    v54 = 10;
    v55 = "pAsrSys";
LABEL_108:
    WPP_SF_Ds(
      *(_QWORD *)v53->Gpt.DiskId.Data4,
      v54,
      (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
      v52,
      v55);
    goto LABEL_35;
  }
  if ( !a4 )
  {
    v14 = 0;
    v52 = 87;
    LastError = 87;
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_35;
    }
    v54 = 11;
    v55 = "pInPackId";
    goto LABEL_108;
  }
  if ( !v64 )
  {
    v14 = 0;
    v52 = 87;
    LastError = 87;
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_35;
    }
    v54 = 12;
    v55 = "pmwszCriticalVolumes";
    goto LABEL_108;
  }
  InBuffer = *a4;
  if ( !(unsigned int)DoIoctlCall(a3, 0x764330u, &InBuffer, 0x10u, &pv) )
  {
    v14 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v16 = GetLastError();
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        13,
        (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
        v16,
        "GetLastError()");
    }
    goto LABEL_35;
  }
  v17 = pv;
  *((_OWORD *)this + 2) = *(_OWORD *)pv;
  *((_OWORD *)this + 3) = v17[1];
  *((_OWORD *)this + 4) = v17[2];
  *((_OWORD *)this + 5) = v17[3];
  *((_DWORD *)this + 24) = *((_DWORD *)v17 + 16);
  v68 = *a4;
  if ( !(unsigned int)DoIoctlCall(a3, 0x764328u, &v68, 0x10u, &v57) )
  {
    v14 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v18 = GetLastError();
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        14,
        (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
        v18,
        "GetLastError()");
    }
    goto LABEL_34;
  }
  v11 = v57;
  v19 = *(unsigned int *)v57;
  v20 = 144 * v19;
  if ( !is_mul_ok(v19, 0x90u) )
    v20 = -1;
  v21 = __CFADD__(v20, 8);
  v22 = v20 + 8;
  if ( v21 )
    v22 = -1;
  v23 = (unsigned __int64 *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
  v66 = v23;
  if ( v23 )
  {
    *v23 = v19;
    v12 = (DynDisk *)(v23 + 1);
    `eh vector constructor iterator'(
      v23 + 1,
      0x90u,
      (unsigned int)v19,
      (void (*)(void *))DynDisk::DynDisk,
      guard_check_icall_nop);
  }
  else
  {
    v12 = 0;
  }
  if ( !v12 )
  {
    v14 = 0;
    v52 = 14;
    LastError = 14;
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_35;
    }
    v54 = 15;
    v55 = "pDynDiskList";
    goto LABEL_108;
  }
  v24 = 0;
  v25 = 0;
  v14 = 1;
  while ( 1 )
  {
    v26 = v57;
    if ( (unsigned int)v25 >= *(_DWORD *)v57 )
      break;
    if ( !DynDisk::Initialize(
            (DynDisk *)((char *)v12 + 144 * v25),
            hDevice,
            v63,
            (struct _GUID *)((char *)v57 + 16 * (unsigned int)v25 + 4)) )
    {
      v14 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v28 = GetLastError();
        WPP_SF_Dsd(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          16,
          (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
          v28,
          (__int64)"GetLastError()",
          v25);
      }
      goto LABEL_33;
    }
    for ( i = 0; (unsigned int)i < a7; i = (unsigned int)(i + 1) )
    {
      if ( a6[i] == *((_DWORD *)v12 + 36 * v25 + 12) )
      {
        ++v24;
        break;
      }
    }
    v25 = (unsigned int)(v25 + 1);
  }
  if ( v24 && v24 < *(_DWORD *)v57 )
  {
    LogEvent(0xA003u, 1u, 0);
    v14 = 0;
    LastError = 11;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        17,
        (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
        11,
        "ERROR_BAD_FORMAT");
    }
    goto LABEL_33;
  }
  v31 = 0;
  v32 = 0;
  v33 = v65;
  while ( (unsigned int)v32 < *v26 && !v31 )
  {
    if ( !*((_BYTE *)v12 + 144 * v32 + 73) )
    {
      v34 = *((_DWORD *)v12 + 36 * v32 + 12);
      TraceFunctionEnter(L"AsrSystem::IsCriticalDisk");
      for ( j = (__int64 *)*((_QWORD *)v33 + 2); ; j = (__int64 *)*j )
      {
        v31 = 0;
        if ( !j )
          break;
        if ( *((_DWORD *)j + 16) == v34 )
        {
          v31 = *((_DWORD *)j + 19);
          break;
        }
      }
      TraceFunctionExit(L"AsrSystem::IsCriticalDisk");
      SetLastError(0);
      v26 = v57;
    }
    v32 = (unsigned int)(v32 + 1);
  }
  v36 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v36 >= *v26 )
    {
      v43 = v63;
      v69 = *v63;
      if ( (unsigned int)DoIoctlCall(hDevice, 0x76432Cu, &v69, 0x10u, &v59) )
      {
        v44 = *(unsigned int *)v59;
        v45 = 280 * v44;
        if ( !is_mul_ok(v44, 0x118u) )
          v45 = -1;
        v21 = __CFADD__(v45, 8);
        v46 = v45 + 8;
        if ( v21 )
          v46 = -1;
        v47 = (unsigned __int64 *)operator new[](v46, (const struct std::nothrow_t *)&std::nothrow);
        v66 = v47;
        if ( v47 )
        {
          *v47 = v44;
          v13 = (DynVolume *)(v47 + 1);
          v58 = (DynVolume *)(v47 + 1);
          `eh vector constructor iterator'(
            v47 + 1,
            0x118u,
            (unsigned int)v44,
            (void (*)(void *))DynVolume::DynVolume,
            (void (*)(void *))DynVolume::~DynVolume);
        }
        else
        {
          v13 = 0;
          v58 = 0;
        }
        if ( v13 )
        {
          v48 = 0;
          v49 = v58;
          while ( 1 )
          {
            v50 = v59;
            if ( v48 >= *(_DWORD *)v59 )
            {
              LastError = 0;
              *(struct _GUID *)this = *v43;
              v11 = v57;
              *((_DWORD *)this + 25) = *(_DWORD *)v57;
              *((_DWORD *)this + 28) = *v50;
              *((_QWORD *)this + 13) = v12;
              v12 = 0;
              *((_QWORD *)this + 15) = v58;
              v13 = 0;
              *((_DWORD *)this + 32) = v31;
              goto LABEL_35;
            }
            if ( !DynVolume::Initialize(
                    (DynVolume *)((char *)v49 + 280 * v48),
                    hDevice,
                    v43,
                    (struct _GUID *)((char *)v59 + 16 * v48 + 4),
                    v64) )
              break;
            ++v48;
          }
          v14 = 0;
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v51 = GetLastError();
            WPP_SF_Dsd(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              24,
              (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
              v51,
              (__int64)"GetLastError()",
              v48);
          }
          v13 = v58;
        }
        else
        {
          v14 = 0;
          LastError = 14;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              23,
              (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
              14,
              "pDynVolList");
          }
        }
        goto LABEL_34;
      }
      v14 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
        goto LABEL_33;
      }
      v37 = GetLastError();
      v38 = 22;
      v39 = "GetLastError()";
LABEL_64:
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        v38,
        (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
        v37,
        v39);
      goto LABEL_33;
    }
    if ( (unsigned int)AsrSystem::GetSifDiskBySifDevNum(v33, *((_DWORD *)v12 + 36 * v36 + 12), &v62) )
      break;
    if ( GetLastError() != 1168 )
    {
      v14 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
        goto LABEL_33;
      }
      v37 = GetLastError();
      v38 = 19;
      v39 = "GetLastError() == ERROR_NOT_FOUND";
      goto LABEL_64;
    }
LABEL_67:
    v36 = (unsigned int)(v36 + 1);
    v26 = v57;
  }
  if ( !v31 )
    goto LABEL_67;
  v40 = v62;
  if ( !*((_QWORD *)v62 + 14) )
    goto LABEL_67;
  v41 = StringCchPrintfW(v70, 0x14u, L"%lu", *((unsigned int *)v62 + 16));
  if ( v41 >= 0 )
  {
    LogEvent(0xA005u, 1u, 1, v70);
    v14 = 0;
    LastError = WIN32_FROM_HRESULT(2147755018LL);
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Dsd(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        21,
        (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
        -2147212278,
        (__int64)"VSS_E_ASRERROR_DYNAMIC_VHD_NOT_SUPPORTED",
        *((_DWORD *)v40 + 16));
    }
  }
  else
  {
    v14 = 0;
    LastError = WIN32_FROM_HRESULT((unsigned int)v41);
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v42 = StringCchPrintfW(v70, 0x14u, L"%lu", *((unsigned int *)v40 + 16));
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        20,
        (unsigned int)WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids,
        v42,
        "::StringCchPrintf( ARRAY_COUNT_PARAM(wszDiskNumber), L\"%lu\", pDiskInfo->DeviceNumber )",
        v56);
    }
  }
LABEL_33:
  v13 = 0;
LABEL_34:
  v11 = v57;
LABEL_35:
  CoTaskMemFree(pv);
  CoTaskMemFree(v11);
  CoTaskMemFree(v59);
  if ( v12 )
    DynDisk::`vector deleting destructor'(v12, v29);
  if ( v13 )
    DynVolume::`vector deleting destructor'(v13, v29);
  TraceFunctionExit(L"DynPack::Initialize");
  SetLastError(LastError);
  return v14;
}

```

## disassembly

```asm
0x1400d365c  mov     [rsp-8+arg_8], rbx
0x1400d3661  push    rbp
0x1400d3662  push    rsi
0x1400d3663  push    rdi
0x1400d3664  push    r12
0x1400d3666  push    r13
0x1400d3668  push    r14
0x1400d366a  push    r15
0x1400d366c  lea     rbp, [rsp-0Fh]
0x1400d3671  sub     rsp, 0E0h
0x1400d3678  mov     rax, cs:__security_cookie
0x1400d367f  xor     rax, rsp
0x1400d3682  mov     [rbp+3Fh+var_38], rax
0x1400d3686  mov     rbx, r9
0x1400d3689  mov     [rbp+3Fh+var_B0], rbx
0x1400d368d  mov     rdi, r8
0x1400d3690  mov     [rsp+110h+hDevice], r8
0x1400d3695  mov     r14, rdx
0x1400d3698  mov     [rbp+3Fh+var_A0], rdx
0x1400d369c  mov     r15, rcx
0x1400d369f  mov     rax, [rbp+3Fh+arg_20]
0x1400d36a3  mov     [rbp+3Fh+var_A8], rax
0x1400d36a7  lea     rcx, aDynpackInitial; "DynPack::Initialize"
0x1400d36ae  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d36b3  xorps   xmm0, xmm0
0x1400d36b6  movups  [rbp+3Fh+var_70], xmm0
0x1400d36ba  xor     eax, eax
0x1400d36bc  mov     [rsp+110h+var_D0], rax
0x1400d36c1  movups  [rbp+3Fh+InBuffer], xmm0
0x1400d36c5  mov     [rsp+110h+pv], rax
0x1400d36ca  xorps   xmm1, xmm1
0x1400d36cd  movups  [rbp+3Fh+var_80], xmm1
0x1400d36d1  mov     r12d, eax
0x1400d36d4  mov     [rsp+110h+var_E0], rax
0x1400d36d9  mov     r13d, eax
0x1400d36dc  mov     esi, eax
0x1400d36de  mov     [rbp+3Fh+var_B8], rax
0x1400d36e2  test    r14, r14
0x1400d36e5  jz      loc_1400D3F2F
0x1400d36eb  test    rbx, rbx
0x1400d36ee  jz      loc_1400D3EDE
0x1400d36f4  cmp     [rbp+3Fh+var_A8], rax
0x1400d36f8  jz      loc_1400D3EA5
0x1400d36fe  movups  xmm0, xmmword ptr [rbx]
0x1400d3701  movdqu  [rbp+3Fh+InBuffer], xmm0
0x1400d3706  lea     rax, [rsp+110h+pv]
0x1400d370b  mov     [rsp+110h+var_F0], rax; void **
0x1400d3710  lea     r14d, [rsi+10h]
0x1400d3714  mov     r9d, r14d; nInBufferSize
0x1400d3717  lea     r8, [rbp+3Fh+InBuffer]; lpInBuffer
0x1400d371b  mov     edx, 764330h; dwIoControlCode
0x1400d3720  mov     rcx, rdi; hDevice
0x1400d3723  call    ?DoIoctlCall@@YAHPEAXK0KPEAPEAX@Z; DoIoctlCall(void *,ulong,void *,ulong,void * *)
0x1400d3728  test    eax, eax
0x1400d372a  jnz     short loc_1400D377F
0x1400d372c  xor     ebx, ebx
0x1400d372e  call    cs:__imp_GetLastError
0x1400d3734  mov     edi, eax
0x1400d3736  lea     rcx, WPP_GLOBAL_Control
0x1400d373d  mov     rax, cs:WPP_GLOBAL_Control
0x1400d3744  cmp     rax, rcx
0x1400d3747  jz      loc_1400D3968
0x1400d374d  test    byte ptr [rax+1Ch], 8
0x1400d3751  jz      loc_1400D3968
0x1400d3757  call    cs:__imp_GetLastError
0x1400d375d  lea     edx, [rsi+0Dh]
0x1400d3760  lea     rcx, aGetlasterror_1; "GetLastError()"
0x1400d3767  mov     [rsp+110h+var_F0], rcx
0x1400d376c  mov     r9d, eax
0x1400d376f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d3776  mov     rcx, [rcx+10h]
0x1400d377a  jmp     loc_1400D3F1E
0x1400d377f  mov     rax, [rsp+110h+pv]
0x1400d3784  movups  xmm0, xmmword ptr [rax]
0x1400d3787  movups  xmmword ptr [r15+20h], xmm0
0x1400d378c  movups  xmm1, xmmword ptr [rax+10h]
0x1400d3790  movups  xmmword ptr [r15+30h], xmm1
0x1400d3795  movups  xmm0, xmmword ptr [rax+20h]
0x1400d3799  movups  xmmword ptr [r15+40h], xmm0
0x1400d379e  movups  xmm1, xmmword ptr [rax+30h]
0x1400d37a2  movups  xmmword ptr [r15+50h], xmm1
0x1400d37a7  mov     eax, [rax+40h]
0x1400d37aa  mov     [r15+60h], eax
0x1400d37ae  movups  xmm0, xmmword ptr [rbx]
0x1400d37b1  movdqu  [rbp+3Fh+var_80], xmm0
0x1400d37b6  lea     rax, [rsp+110h+var_E0]
0x1400d37bb  mov     [rsp+110h+var_F0], rax; void **
0x1400d37c0  mov     r9d, r14d; nInBufferSize
0x1400d37c3  lea     r8, [rbp+3Fh+var_80]; lpInBuffer
0x1400d37c7  mov     edx, 764328h; dwIoControlCode
0x1400d37cc  mov     rcx, rdi; hDevice
0x1400d37cf  call    ?DoIoctlCall@@YAHPEAXK0KPEAPEAX@Z; DoIoctlCall(void *,ulong,void *,ulong,void * *)
0x1400d37d4  test    eax, eax
0x1400d37d6  jnz     short loc_1400D3837
0x1400d37d8  xor     ebx, ebx
0x1400d37da  call    cs:__imp_GetLastError
0x1400d37e0  mov     edi, eax
0x1400d37e2  lea     rcx, WPP_GLOBAL_Control
0x1400d37e9  mov     rax, cs:WPP_GLOBAL_Control
0x1400d37f0  cmp     rax, rcx
0x1400d37f3  jz      loc_1400D3963
0x1400d37f9  test    byte ptr [rax+1Ch], 8
0x1400d37fd  jz      loc_1400D3963
0x1400d3803  call    cs:__imp_GetLastError
0x1400d3809  lea     edx, [rbx+0Eh]
0x1400d380c  lea     rcx, aGetlasterror_1; "GetLastError()"
0x1400d3813  mov     [rsp+110h+var_F0], rcx
0x1400d3818  mov     r9d, eax
0x1400d381b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d3822  mov     rcx, [rcx+10h]
0x1400d3826  lea     r8, WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids
0x1400d382d  call    WPP_SF_Ds
0x1400d3832  jmp     loc_1400D3963
0x1400d3837  mov     r12, [rsp+110h+var_E0]
0x1400d383c  mov     ebx, [r12]
0x1400d3840  mov     edi, 90h
0x1400d3845  mov     eax, edi
0x1400d3847  mul     rbx
0x1400d384a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400d3851  cmovb   rax, rcx
0x1400d3855  add     rax, 8
0x1400d3859  cmovb   rax, rcx
0x1400d385d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400d3864  mov     rcx, rax; unsigned __int64
0x1400d3867  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400d386c  mov     [rbp+3Fh+var_98], rax
0x1400d3870  test    rax, rax
0x1400d3873  jz      short loc_1400D389E
0x1400d3875  mov     [rax], rbx
0x1400d3878  lea     r13, [rax+8]
0x1400d387c  lea     rax, _guard_check_icall_nop
0x1400d3883  mov     [rsp+110h+var_F0], rax; void (*)(void *)
0x1400d3888  lea     r9, ??0DynDisk@@QEAA@XZ; void (*)(void *)
0x1400d388f  mov     r8d, ebx; unsigned __int64
0x1400d3892  mov     edx, edi; unsigned __int64
0x1400d3894  mov     rcx, r13; void *
0x1400d3897  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400d389c  jmp     short loc_1400D38A1
0x1400d389e  xor     r13d, r13d
0x1400d38a1  test    r13, r13
0x1400d38a4  jz      loc_1400D3E6F
0x1400d38aa  mov     r12, [rbp+3Fh+arg_28]
0x1400d38ae  xor     edi, edi
0x1400d38b0  xor     esi, esi
0x1400d38b2  lea     ebx, [rdi+1]
0x1400d38b5  mov     rdx, [rsp+110h+var_E0]
0x1400d38ba  cmp     esi, [rdx]
0x1400d38bc  jnb     loc_1400D39DE
0x1400d38c2  mov     ecx, esi
0x1400d38c4  lea     r14, [rsi+rsi*8]
0x1400d38c8  shl     r14, 4
0x1400d38cc  add     r14, r13
0x1400d38cf  shl     rcx, 4
0x1400d38d3  lea     r9, [rdx+4]
0x1400d38d7  add     r9, rcx; struct _GUID *
0x1400d38da  mov     r8, [rbp+3Fh+var_B0]; struct _GUID *
0x1400d38de  mov     rdx, [rsp+110h+hDevice]; void *
0x1400d38e3  mov     rcx, r14; this
0x1400d38e6  call    ?Initialize@DynDisk@@QEAAHPEAXPEAU_GUID@@1@Z; DynDisk::Initialize(void *,_GUID *,_GUID *)
0x1400d38eb  test    eax, eax
0x1400d38ed  jz      short loc_1400D390A
0x1400d38ef  xor     edx, edx
0x1400d38f1  cmp     edx, [rbp+3Fh+arg_30]
0x1400d38f4  jnb     short loc_1400D3906
0x1400d38f6  mov     eax, [r14+30h]
0x1400d38fa  cmp     [r12+rdx*4], eax
0x1400d38fe  jz      short loc_1400D3904
0x1400d3900  add     edx, ebx
0x1400d3902  jmp     short loc_1400D38F1
0x1400d3904  add     edi, ebx
0x1400d3906  add     esi, ebx
0x1400d3908  jmp     short loc_1400D38B5
0x1400d390a  xor     ebx, ebx
0x1400d390c  call    cs:__imp_GetLastError
0x1400d3912  mov     edi, eax
0x1400d3914  lea     rcx, WPP_GLOBAL_Control
0x1400d391b  mov     rax, cs:WPP_GLOBAL_Control
0x1400d3922  cmp     rax, rcx
0x1400d3925  jz      short loc_1400D3960
0x1400d3927  test    byte ptr [rax+1Ch], 8
0x1400d392b  jz      short loc_1400D3960
0x1400d392d  call    cs:__imp_GetLastError
0x1400d3933  lea     edx, [rbx+10h]
0x1400d3936  mov     [rsp+110h+var_E8], esi
0x1400d393a  lea     rcx, aGetlasterror_1; "GetLastError()"
0x1400d3941  mov     [rsp+110h+var_F0], rcx
0x1400d3946  mov     r9d, eax
0x1400d3949  lea     r8, WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids
0x1400d3950  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d3957  mov     rcx, [rcx+10h]
0x1400d395b  call    WPP_SF_Dsd
0x1400d3960  mov     rsi, rbx
0x1400d3963  mov     r12, [rsp+110h+var_E0]
0x1400d3968  mov     rcx, [rsp+110h+pv]; pv
0x1400d396d  call    cs:__imp_CoTaskMemFree
0x1400d3973  mov     rcx, r12; pv
0x1400d3976  call    cs:__imp_CoTaskMemFree
0x1400d397c  mov     rcx, [rsp+110h+var_D0]; pv
0x1400d3981  call    cs:__imp_CoTaskMemFree
0x1400d3987  test    r13, r13
0x1400d398a  jz      short loc_1400D3994
0x1400d398c  mov     rcx, r13; this
0x1400d398f  call    ??_EDynDisk@@QEAAPEAXI@Z; DynDisk::`vector deleting destructor'(uint)
0x1400d3994  test    rsi, rsi
0x1400d3997  jz      short loc_1400D39A1
0x1400d3999  mov     rcx, rsi; this
0x1400d399c  call    ??_EDynVolume@@QEAAPEAXI@Z; DynVolume::`vector deleting destructor'(uint)
0x1400d39a1  lea     rcx, aDynpackInitial; "DynPack::Initialize"
0x1400d39a8  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400d39ad  mov     ecx, edi; dwErrCode
0x1400d39af  call    cs:__imp_SetLastError
0x1400d39b5  mov     eax, ebx
0x1400d39b7  mov     rcx, [rbp+3Fh+var_38]
0x1400d39bb  xor     rcx, rsp; StackCookie
0x1400d39be  call    __security_check_cookie
0x1400d39c3  mov     rbx, [rsp+110h+arg_8]
0x1400d39cb  add     rsp, 0E0h
0x1400d39d2  pop     r15
0x1400d39d4  pop     r14
0x1400d39d6  pop     r13
0x1400d39d8  pop     r12
0x1400d39da  pop     rdi
0x1400d39db  pop     rsi
0x1400d39dc  pop     rbp
0x1400d39dd  retn
0x1400d39de  test    edi, edi
0x1400d39e0  jz      short loc_1400D3A42
0x1400d39e2  cmp     edi, [rdx]
0x1400d39e4  jnb     short loc_1400D3A42
0x1400d39e6  xor     r8d, r8d; int
0x1400d39e9  mov     edx, ebx; unsigned __int16
0x1400d39eb  mov     ecx, 0A003h; dwEventID
0x1400d39f0  call    ?LogEvent@@YAHKGHZZ; LogEvent(ulong,ushort,int,...)
0x1400d39f5  xor     ebx, ebx
0x1400d39f7  lea     edi, [rbx+0Bh]
0x1400d39fa  lea     rcx, WPP_GLOBAL_Control
0x1400d3a01  mov     rax, cs:WPP_GLOBAL_Control
0x1400d3a08  cmp     rax, rcx
0x1400d3a0b  jz      loc_1400D3960
0x1400d3a11  test    byte ptr [rax+1Ch], 8
0x1400d3a15  jz      loc_1400D3960
0x1400d3a1b  lea     edx, [rbx+11h]
0x1400d3a1e  lea     rcx, aErrorBadFormat; "ERROR_BAD_FORMAT"
0x1400d3a25  mov     [rsp+110h+var_F0], rcx
0x1400d3a2a  mov     r9d, edi
0x1400d3a2d  mov     rcx, [rax+10h]
0x1400d3a31  lea     r8, WPP_f95732df0cb0356c2a969d46555fa37e_Traceguids
0x1400d3a38  call    WPP_SF_Ds
0x1400d3a3d  jmp     loc_1400D3960
0x1400d3a42  xor     r14d, r14d
0x1400d3a45  xor     edi, edi
0x1400d3a47  mov     r12, [rbp+3Fh+var_A0]
0x1400d3a4b  cmp     edi, [rdx]
0x1400d3a4d  jnb     short loc_1400D3AAB
0x1400d3a4f  test    r14d, r14d
0x1400d3a52  jnz     short loc_1400D3AAB
0x1400d3a54  lea     rcx, [rdi+rdi*8]
0x1400d3a58  add     rcx, rcx
0x1400d3a5b  cmp     [r13+rcx*8+49h], r14b
0x1400d3a60  jnz     short loc_1400D3AA7
0x1400d3a62  mov     esi, [r13+rcx*8+30h]
0x1400d3a67  lea     rcx, aAsrsystemIscri; "AsrSystem::IsCriticalDisk"
0x1400d3a6e  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d3a73  mov     rax, [r12+10h]
0x1400d3a78  xor     r14d, r14d
0x1400d3a7b  test    rax, rax
0x1400d3a7e  jz      short loc_1400D3A8E
0x1400d3a80  cmp     [rax+40h], esi
0x1400d3a83  jz      short loc_1400D3A8A
0x1400d3a85  mov     rax, [rax]
0x1400d3a88  jmp     short loc_1400D3A78
0x1400d3a8a  mov     r14d, [rax+4Ch]
0x1400d3a8e  lea     rcx, aAsrsystemIscri; "AsrSystem::IsCriticalDisk"
0x1400d3a95  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400d3a9a  xor     ecx, ecx; dwErrCode
0x1400d3a9c  call    cs:__imp_SetLastError
0x1400d3aa2  mov     rdx, [rsp+110h+var_E0]
0x1400d3aa7  add     edi, ebx
0x1400d3aa9  jmp     short loc_1400D3A4B
0x1400d3aab  xor     edi, edi
0x1400d3aad  cmp     edi, [rdx]
0x1400d3aaf  jnb     loc_1400D3C54
0x1400d3ab5  lea     rdx, [rdi+rdi*8]
0x1400d3ab9  add     rdx, rdx
0x1400d3abc  lea     r8, [rbp+3Fh+var_B8]; struct _ASR_DISK_INFO **
0x1400d3ac0  mov     edx, [r13+rdx*8+30h]; unsigned int
0x1400d3ac5  mov     rcx, r12; this
0x1400d3ac8  call    ?GetSifDiskBySifDevNum@AsrSystem@@QEAAHKPEAPEAU_ASR_DISK_INFO@@@Z; AsrSystem::GetSifDiskBySifDevNum(ulong,_ASR_DISK_INFO * *)
0x1400d3acd  test    eax, eax
0x1400d3acf  jnz     short loc_1400D3B31
0x1400d3ad1  call    cs:__imp_GetLastError
0x1400d3ad7  cmp     eax, 490h
0x1400d3adc  jz      short loc_1400D3B41
0x1400d3ade  xor     ebx, ebx
0x1400d3ae0  call    cs:__imp_GetLastError
0x1400d3ae6  mov     edi, eax
0x1400d3ae8  lea     rcx, WPP_GLOBAL_Control
0x1400d3aef  mov     rax, cs:WPP_GLOBAL_Control
0x1400d3af6  cmp     rax, rcx
0x1400d3af9  jz      loc_1400D3960
  ... truncated ...
```
