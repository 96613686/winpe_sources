# CreatePartition(IVdsService *,int,_DISKCFG_PARTITION_TYPE,int,unsigned __int64 *,unsigned __int64)

- ea: `0x18003e3c0`
- end: `0x18003ee4d`
- name: `?CreatePartition@@YAJPEAUIVdsService@@HW4_DISKCFG_PARTITION_TYPE@@HPEA_K_K@Z`
- size: `2701`
- prototype: `__int64 __fastcall(struct IVdsService *, unsigned int, __int64, int, unsigned __int64 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800244d4`
- `0x180026054`

## callees

- `0x180039394`
- `0x18003e030`
- `0x18003e3c0`
- `0x1800409cc`
- `0x180041338`
- `0x1800417a8`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18003e8c8`
- `RPCRT4!UuidCreate` at `0x18003e8c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e659`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e763`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e79c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ed7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ed98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ede3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e659`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e763`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e79c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ed7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ed98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ede3`

## string_xrefs

- `0x18003e487`: `CreatePartition: Need to decide the type of the partition to create`
- `0x18003e710`: `CreatePartition: Failed to convert disk [%d] to %s; hr = 0x%x`
- `0x18003e6d7`: `CreatePartition: Automatically converted disk [%d] to %s. The offset for the partition to create is updated to 0 (means no preference).`
- `0x18003e4dd`: `CreatePartition: Asked to create partition of unknown DC type 0x%x`
- `0x18003e505`: `CreatePartition: Failed to decide the type of the partition to create, hr = 0x%x`
- `0x18003ed50`: `CreatePartition: Disk %d doesn't support creation of partitions of the specified type`
- `0x18003e72e`: `CreatePartition: Failed to get property and partition count for disk %d, hr = 0x%x`
- `0x18003ece9`: `CreatePartition: Failure while waiting for partition creation; hr = 0x%x, hrWait = 0x%x`
- `0x18003eccc`: `CreatePartition: Got invalid offset of 0`
- `0x18003ecb1`: `CreatePartition: Successfully created partition on disk %d at {offset = [%I64u], size = [%I64u]}`
- `0x18003ec02`: `CreatePartition: Requesting creation of partition with { offset = [0x%I64x], size [0x%I64x] }`
- `0x18003ed29`: `CreatePartition: Requested partition looks invalid (offset = [%I64u], size = [%I64u])`

## pseudocode

```c
__int64 __fastcall CreatePartition(
        struct IVdsService *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        unsigned __int64 *a5,
        unsigned __int64 a6)
{
  int v6; // r14d
  int Disk; // ebx
  int v11; // eax
  int v12; // edi
  unsigned int v13; // esi
  unsigned __int64 v14; // r14
  struct IVdsDisk *v15; // rcx
  const wchar_t *v16; // rax
  const wchar_t *v17; // rax
  __int64 v18; // xmm0_8
  __int16 v19; // ax
  RPC_STATUS v20; // eax
  struct IVdsDisk *v21; // rbx
  struct IVdsAdvancedDisk *v22; // r12
  unsigned __int64 v23; // rsi
  const wchar_t *v24; // r9
  struct IVdsDiskVtbl *lpVtbl; // rax
  int v26; // edi
  int v27; // eax
  __int64 v28; // r8
  LPVOID v29; // rdx
  char v30; // al
  int v31; // ebx
  int v32; // r12d
  _QWORD *v33; // r10
  int v34; // r11d
  unsigned __int64 v35; // r9
  unsigned __int64 v36; // r8
  unsigned __int64 v37; // rcx
  const wchar_t *v38; // r9
  unsigned __int64 *v39; // rdi
  __int64 v40; // rax
  struct IVdsAdvancedDisk2 **v42; // [rsp+20h] [rbp-E0h]
  struct IVdsAdvancedDisk2 **v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  struct IVdsDisk *v46; // [rsp+50h] [rbp-B0h] BYREF
  struct IVdsAdvancedDisk *v47; // [rsp+58h] [rbp-A8h] BYREF
  struct IVdsDisk *v48; // [rsp+60h] [rbp-A0h] BYREF
  struct IVdsAdvancedDisk *v49; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 *v50; // [rsp+70h] [rbp-90h]
  LPVOID v51; // [rsp+78h] [rbp-88h] BYREF
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+88h] [rbp-78h]
  unsigned __int64 v54; // [rsp+90h] [rbp-70h]
  struct IVdsAdvancedDisk *v55; // [rsp+98h] [rbp-68h]
  _OWORD v56[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v57; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v58[4]; // [rsp+C4h] [rbp-3Ch] BYREF
  __int16 v59; // [rsp+C8h] [rbp-38h]
  __int64 v60; // [rsp+CAh] [rbp-36h]
  int v61; // [rsp+D2h] [rbp-2Eh]
  __int16 v62; // [rsp+D6h] [rbp-2Ah]
  UUID Uuid; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v64; // [rsp+E8h] [rbp-18h]
  int v65; // [rsp+104h] [rbp+4h]
  LPVOID v66; // [rsp+118h] [rbp+18h]
  LPVOID v67; // [rsp+120h] [rbp+20h]
  LPVOID v68; // [rsp+128h] [rbp+28h]
  LPVOID v69; // [rsp+130h] [rbp+30h]
  LPVOID v70; // [rsp+138h] [rbp+38h]
  int v71; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v72[64]; // [rsp+144h] [rbp+44h] BYREF
  int v73; // [rsp+184h] [rbp+84h]
  LPVOID v74; // [rsp+198h] [rbp+98h]
  LPVOID v75; // [rsp+1A0h] [rbp+A0h]
  LPVOID v76; // [rsp+1A8h] [rbp+A8h]
  LPVOID v77; // [rsp+1B0h] [rbp+B0h]
  LPVOID v78; // [rsp+1B8h] [rbp+B8h]

  v6 = 0;
  v50 = a5;
  v46 = 0;
  v49 = 0;
  if ( !a1 || (a2 & 0x80000000) != 0 || !a5 )
    return 2147942487LL;
  Disk = GetDisk(a1, a2, &v46, &v49, 0);
  if ( Disk < 0 || !v46 )
    goto LABEL_160;
  if ( v49 )
  {
    v71 = 0;
    memset_0(v72, 0, 0x7Cu);
    if ( a4 == 1 )
    {
      v44 = 0;
      LibLog(&g_VdsLibLog, 0x4000000, L"CreatePartition: Need to decide the type of the partition to create");
      v11 = ResolvePartitionTypeToCreate(a2, &v44);
      Disk = v11;
      if ( v11 < 0 )
      {
        LibLog(
          &g_VdsLibLog,
          0x2000000,
          L"CreatePartition: Failed to decide the type of the partition to create, hr = 0x%x",
          (unsigned int)v11);
        goto LABEL_150;
      }
      v12 = v44;
      if ( v44 == 4 || v44 == 5 || v44 == 6 || v44 == 7 )
      {
        v13 = 2;
        goto LABEL_21;
      }
      if ( v44 != 1 && v44 != 2 && v44 != 3 )
      {
        LibLog(
          &g_VdsLibLog,
          0x2000000,
          L"CreatePartition: Asked to create partition of unknown DC type 0x%x",
          (unsigned int)v44);
        Disk = -2147211931;
LABEL_150:
        if ( v74 )
        {
          CoTaskMemFree(v74);
          v74 = 0;
        }
        if ( v75 )
        {
          CoTaskMemFree(v75);
          v75 = 0;
        }
        if ( v76 )
        {
          CoTaskMemFree(v76);
          v76 = 0;
        }
        if ( v77 )
        {
          CoTaskMemFree(v77);
          v77 = 0;
        }
        if ( v78 )
          CoTaskMemFree(v78);
LABEL_160:
        if ( v49 )
        {
          ((void (__fastcall *)(struct IVdsAdvancedDisk *))v49->lpVtbl->Release)(v49);
          v49 = 0;
        }
        goto LABEL_162;
      }
    }
    else
    {
      v12 = 1;
    }
    v13 = 1;
LABEL_21:
    pv = 0;
    if ( !v46 )
      goto LABEL_149;
    Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *))v46->lpVtbl->GetPack)(v46, &pv);
    if ( Disk == -2147212265 )
    {
      if ( !pv )
      {
        v6 = 1;
        Disk = 0;
        goto LABEL_27;
      }
    }
    else if ( !pv )
    {
      goto LABEL_27;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
LABEL_27:
    if ( Disk < 0 )
      goto LABEL_150;
    if ( v6 == 1 )
    {
      Disk = ConvertUnallocatedDisk(a1, a2, v13, &v46, &v49);
      v14 = 0;
      goto LABEL_62;
    }
    v14 = 0;
    v57 = 0;
    memset_0(v58, 0, 0x7Cu);
    v44 = 0;
    Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, unsigned int *))v46->lpVtbl->GetProperties)(v46, &v57);
    if ( Disk < 0 )
      goto LABEL_51;
    v48 = 0;
    v47 = 0;
    Disk = GetDisk(a1, a2, &v48, &v47, 0);
    if ( Disk >= 0 )
    {
      v15 = v48;
      if ( !v48 )
        goto LABEL_37;
      if ( !v47 )
        goto LABEL_39;
      pv = 0;
      Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk *, LPVOID *, int *))v47->lpVtbl->QueryPartitions)(
               v47,
               &pv,
               &v44);
      if ( pv )
        CoTaskMemFree(pv);
    }
    v15 = v48;
LABEL_37:
    if ( v47 )
    {
      ((void (__fastcall *)(struct IVdsAdvancedDisk *))v47->lpVtbl->Release)(v47);
      v15 = v48;
      v47 = 0;
    }
LABEL_39:
    if ( v15 )
      ((void (__fastcall *)(struct IVdsDisk *))v15->lpVtbl->Release)(v15);
    if ( Disk >= 0 )
    {
      if ( v65 != v13 && !v44 )
      {
        Disk = ConvertDiskStyle(a1, a2, v13);
        if ( Disk < 0 )
        {
          v17 = L"MBR";
          if ( v13 != 1 )
            v17 = L"GPT";
          LibLog(
            &g_VdsLibLog,
            0x2000000,
            L"CreatePartition: Failed to convert disk [%d] to %s; hr = 0x%x",
            a2,
            v17,
            Disk);
        }
        else
        {
          *v50 = 0;
          v16 = L"MBR";
          if ( v13 != 1 )
            v16 = L"GPT";
          LibLog(
            &g_VdsLibLog,
            0x4000000,
            L"CreatePartition: Automatically converted disk [%d] to %s. The offset for the partition to create is updated "
             "to 0 (means no preference).",
            a2,
            v16);
        }
      }
      goto LABEL_52;
    }
LABEL_51:
    LODWORD(v42) = Disk;
    LibLog(
      &g_VdsLibLog,
      0x2000000,
      L"CreatePartition: Failed to get property and partition count for disk %d, hr = 0x%x",
      a2,
      v42);
LABEL_52:
    if ( v66 )
    {
      CoTaskMemFree(v66);
      v66 = 0;
    }
    if ( v67 )
    {
      CoTaskMemFree(v67);
      v67 = 0;
    }
    if ( v68 )
    {
      CoTaskMemFree(v68);
      v68 = 0;
    }
    if ( v69 )
    {
      CoTaskMemFree(v69);
      v69 = 0;
    }
    if ( v70 )
      CoTaskMemFree(v70);
LABEL_62:
    if ( Disk < 0 )
      goto LABEL_150;
    Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, int *))v46->lpVtbl->GetProperties)(v46, &v71);
    if ( Disk < 0 )
      goto LABEL_150;
    if ( v73 != v13 )
    {
      Disk = -2147211931;
      LibLog(
        &g_VdsLibLog,
        0x2000000,
        L"CreatePartition: Disk %d doesn't support creation of partitions of the specified type",
        a2);
      goto LABEL_150;
    }
    memset_0(&v57, 0, 0x78u);
    v57 = v13;
    if ( v13 == 1 )
    {
      v59 = (unsigned __int8)((v12 != 3) + 5);
      goto LABEL_80;
    }
    v64 = 0x8000000000000000uLL;
    switch ( v12 )
    {
      case 5:
        v18 = *(_QWORD *)((char *)&PARTITION_MSFT_RESERVED_GUID.Data1 + 2);
        v61 = *(_DWORD *)&PARTITION_MSFT_RESERVED_GUID.Data4[2];
        v19 = *(_WORD *)&PARTITION_MSFT_RESERVED_GUID.Data4[6];
        v59 = -7402;
        break;
      case 6:
        v18 = *(_QWORD *)((char *)&PARTITION_SYSTEM_GUID.Data1 + 2);
        v61 = *(_DWORD *)&PARTITION_SYSTEM_GUID.Data4[2];
        v19 = *(_WORD *)&PARTITION_SYSTEM_GUID.Data4[6];
        v59 = 29480;
        break;
      case 7:
        v18 = *(_QWORD *)((char *)&PARTITION_MSFT_RECOVERY_GUID.Data1 + 2);
        v61 = *(_DWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data4[2];
        v62 = *(_WORD *)&PARTITION_MSFT_RECOVERY_GUID.Data4[6];
        v64 = 0x8000000000000001uLL;
        v59 = -17500;
        goto LABEL_75;
      default:
        v18 = *(_QWORD *)((char *)&PARTITION_BASIC_DATA_GUID.Data1 + 2);
        v61 = *(_DWORD *)&PARTITION_BASIC_DATA_GUID.Data4[2];
        v19 = *(_WORD *)&PARTITION_BASIC_DATA_GUID.Data4[6];
        v59 = -24414;
        break;
    }
    v62 = v19;
LABEL_75:
    v60 = v18;
    v20 = UuidCreate(&Uuid);
    if ( v20 )
    {
      if ( v20 > 0 )
        Disk = (unsigned __int16)v20 | 0x80070000;
      else
        Disk = v20;
    }
    if ( Disk < 0 )
      goto LABEL_150;
LABEL_80:
    v21 = v46;
    LODWORD(v48) = v12 == 2;
    if ( v46 )
    {
      v22 = v49;
      v55 = v49;
      if ( v49 )
      {
        v23 = a6;
        v24 = L"True";
        pv = 0;
        v53 = 0;
        LODWORD(v47) = 0;
        v54 = 0;
        if ( v12 != 2 )
          v24 = L"False";
        LibLog(
          &g_VdsLibLog,
          0x4000000,
          L"FindFreeExtent: Trying to find extent matching these criteria (byte offset of 0 implies no offset preference):"
           " [WithinContainer = %s] [Size >= 0x%I64x bytes] [Byte offset = 0x%I64x]",
          v24,
          a6,
          *v50);
        lpVtbl = v21->lpVtbl;
        v26 = 0;
        v52 = 0;
        if ( ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))lpVtbl->QueryInterface)(
               v21,
               &IID_IVdsAdvancedDisk,
               &v52) >= 0
          && v52 )
        {
          v44 = 0;
          v51 = 0;
          v27 = (*(__int64 (__fastcall **)(__int64, LPVOID *, int *))(*(_QWORD *)v52 + 32LL))(v52, &v51, &v44);
          v29 = v51;
          if ( v27 >= 0 )
          {
            v28 = 0;
            if ( v44 > 0 )
            {
              do
              {
                if ( v26 )
                  break;
                if ( *((_DWORD *)v51 + 36 * (int)v28) == 1 )
                {
                  v30 = *((_BYTE *)v51 + 144 * (int)v28 + 32);
                  if ( v30 == 5 || v30 == 15 )
                  {
                    v26 = 1;
                    v14 = *((_QWORD *)v51 + 18 * (int)v28 + 2);
                    v53 = *((_QWORD *)v51 + 18 * (int)v28 + 3);
                  }
                }
                v28 = (unsigned int)(v28 + 1);
              }
              while ( (int)v28 < v44 );
              v54 = v14;
            }
          }
          if ( v51 )
          {
            CoTaskMemFree(v51);
            v51 = 0;
          }
          if ( v52 )
            (*(void (__fastcall **)(__int64, LPVOID, __int64))(*(_QWORD *)v52 + 16LL))(v52, v29, v28);
        }
        Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, struct IVdsAdvancedDisk **))v21->lpVtbl->QueryExtents)(
                 v21,
                 &pv,
                 &v47);
        if ( Disk < 0 )
        {
LABEL_128:
          if ( pv )
            CoTaskMemFree(pv);
          if ( Disk < 0 )
            goto LABEL_150;
          v39 = v50;
          if ( !*v50 || v23 < 0x100000 )
          {
            LibLog(
              &g_VdsLibLog,
              0x2000000,
              L"CreatePartition: Requested partition looks invalid (offset = [%I64u], size = [%I64u])");
            Disk = -2147467259;
            goto LABEL_150;
          }
          pv = 0;
          LibLog(
            &g_VdsLibLog,
            0x4000000,
            L"CreatePartition: Requesting creation of partition with { offset = [0x%I64x], size [0x%I64x] }");
          Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk *, unsigned __int64, unsigned __int64, unsigned int *, LPVOID *))v22->lpVtbl->CreatePartition)(
                   v22,
                   *v39,
                   v23,
                   &v57,
                   &pv);
          if ( Disk >= 0 )
          {
            if ( !pv )
              goto LABEL_150;
            v44 = 0;
            memset(v56, 0, sizeof(v56));
            Disk = (*(__int64 (__fastcall **)(LPVOID, int *, _OWORD *))(*(_QWORD *)pv + 32LL))(pv, &v44, v56);
            if ( Disk >= 0 && v44 >= 0 && LODWORD(v56[0]) == 10 )
            {
              v40 = *((_QWORD *)&v56[0] + 1);
              *v39 = *((_QWORD *)&v56[0] + 1);
              if ( v40 )
              {
                LibLog(
                  &g_VdsLibLog,
                  0x4000000,
                  L"CreatePartition: Successfully created partition on disk %d at {offset = [%I64u], size = [%I64u]}",
                  a2,
                  v40,
                  v23);
              }
              else
              {
                Disk = -2147467259;
                LibLog(&g_VdsLibLog, 0x2000000, L"CreatePartition: Got invalid offset of 0");
              }
            }
            else
            {
              LODWORD(v43) = v44;
              LibLog(
                &g_VdsLibLog,
                0x2000000,
                L"CreatePartition: Failure while waiting for partition creation; hr = 0x%x, hrWait = 0x%x",
                (unsigned int)Disk,
                v43);
              if ( Disk >= 0 )
              {
                Disk = -2147024883;
                if ( v44 < 0 )
                  Disk = v44;
              }
            }
          }
          if ( pv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          goto LABEL_150;
        }
        v31 = 0;
        v32 = 0;
        while ( 1 )
        {
          if ( v32 >= (int)v47 )
          {
            LibLog(
              &g_VdsLibLog,
              0x4000000,
              L"FindFreeExtent: Found no free extents matching criteria on specified disk");
            v22 = v55;
            Disk = 1;
            goto LABEL_128;
          }
          v33 = pv;
          v34 = 0;
          if ( v26 == 1 && v14 && v53 && *((_QWORD *)pv + 10 * v32 + 3) >= v14 )
            v34 = *((_QWORD *)pv + 10 * v32 + 3) < v14 + v53;
          if ( *((_DWORD *)pv + 20 * v32 + 4) == 1 )
          {
            v35 = *((_QWORD *)pv + 10 * v32 + 4);
            if ( v35 >= 0x100000 && v34 == (_DWORD)v48 && v35 >= v23 )
            {
              v36 = *((_QWORD *)pv + 10 * v32 + 3);
              v37 = *v50;
              if ( !*v50 )
              {
                *v50 = v36;
                if ( !v23 )
                  v23 = v33[10 * v32 + 4];
                v31 = 1;
LABEL_122:
                v38 = L"True";
                if ( !v34 )
                  v38 = L"False";
                LibLog(
                  &g_VdsLibLog,
                  0x4000000,
                  L"FindFreeExtent: Found suitable extent: [WithinContainer = %s], [Byte size of found extent = 0x%I64x], "
                   "[Byte offset of found extent = 0x%I64x], [Return size of found extent = 0x%I64x], [Return offset of f"
                   "ound extent = 0x%I64x].",
                  v38,
                  v33[10 * v32 + 4],
                  v33[10 * v32 + 3],
                  v23,
                  v36);
                goto LABEL_125;
              }
              if ( v37 >= v36 && v37 < v35 + v36 && v23 + v37 <= v35 + v36 )
              {
                if ( !v23 )
                  v23 = v36 + v35 - v37;
                v31 = 1;
                v36 = *v50;
                goto LABEL_122;
              }
            }
          }
LABEL_125:
          v14 = v54;
          ++v32;
          if ( v31 )
          {
            v22 = v55;
            Disk = 0;
            goto LABEL_128;
          }
        }
      }
    }
LABEL_149:
    Disk = -2147024809;
    goto LABEL_150;
  }
LABEL_162:
  if ( v46 )
    ((void (__fastcall *)(struct IVdsDisk *))v46->lpVtbl->Release)(v46);
  return (unsigned int)Disk;
}

```

## disassembly

```asm
0x18003e3c0  mov     [rsp-8+arg_10], rbx
0x18003e3c5  push    rbp
0x18003e3c6  push    rsi
0x18003e3c7  push    rdi
0x18003e3c8  push    r12
0x18003e3ca  push    r13
0x18003e3cc  push    r14
0x18003e3ce  push    r15
0x18003e3d0  lea     rbp, [rsp-0D0h]
0x18003e3d8  sub     rsp, 1D0h
0x18003e3df  mov     rax, cs:__security_cookie
0x18003e3e6  xor     rax, rsp
0x18003e3e9  mov     [rbp+100h+var_40], rax
0x18003e3f0  mov     rax, [rbp+100h+arg_20]
0x18003e3f7  xor     r14d, r14d
0x18003e3fa  mov     [rsp+200h+var_190], rax
0x18003e3ff  mov     edi, r9d
0x18003e402  mov     [rsp+200h+var_1B0], r14
0x18003e407  mov     r13d, edx
0x18003e40a  mov     [rsp+200h+var_198], r14
0x18003e40f  mov     r12, rcx
0x18003e412  test    rcx, rcx
0x18003e415  jz      loc_18003EE1E
0x18003e41b  test    edx, edx
0x18003e41d  js      loc_18003EE1E
0x18003e423  test    rax, rax
0x18003e426  jz      loc_18003EE1E
0x18003e42c  lea     r9, [rsp+200h+var_198]; struct IVdsAdvancedDisk **
0x18003e431  mov     [rsp+200h+var_1E0], r14; struct IVdsAdvancedDisk2 **
0x18003e436  lea     r8, [rsp+200h+var_1B0]; struct IVdsDisk **
0x18003e43b  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x18003e440  mov     ebx, eax
0x18003e442  test    eax, eax
0x18003e444  js      loc_18003EDE9
0x18003e44a  cmp     [rsp+200h+var_1B0], r14
0x18003e44f  jz      loc_18003EDE9
0x18003e455  cmp     [rsp+200h+var_198], r14
0x18003e45a  jz      loc_18003EE04
0x18003e460  xor     edx, edx; Val
0x18003e462  mov     [rbp+100h+var_C0], r14d
0x18003e466  lea     r8d, [r14+7Ch]; Size
0x18003e46a  lea     rcx, [rbp+100h+var_BC]; void *
0x18003e46e  call    memset_0
0x18003e473  lea     r15d, [r14+1]
0x18003e477  lea     rsi, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18003e47e  cmp     edi, r15d
0x18003e481  jnz     loc_18003E51E
0x18003e487  lea     r8, aCreatepartitio_7; "CreatePartition: Need to decide the typ"...
0x18003e48e  mov     [rsp+200h+var_1C0], r14d
0x18003e493  mov     edx, 4000000h
0x18003e498  mov     rcx, rsi
0x18003e49b  call    LibLog
0x18003e4a0  lea     rdx, [rsp+200h+var_1C0]
0x18003e4a5  mov     ecx, r13d
0x18003e4a8  call    ResolvePartitionTypeToCreate
0x18003e4ad  mov     ebx, eax
0x18003e4af  test    eax, eax
0x18003e4b1  js      short loc_18003E502
0x18003e4b3  mov     edi, [rsp+200h+var_1C0]
0x18003e4b7  cmp     edi, 4
0x18003e4ba  jz      short loc_18003E4FB
0x18003e4bc  cmp     edi, 5
0x18003e4bf  jz      short loc_18003E4FB
0x18003e4c1  cmp     edi, 6
0x18003e4c4  jz      short loc_18003E4FB
0x18003e4c6  cmp     edi, 7
0x18003e4c9  jz      short loc_18003E4FB
0x18003e4cb  cmp     edi, r15d
0x18003e4ce  jz      short loc_18003E521
0x18003e4d0  cmp     edi, 2
0x18003e4d3  jz      short loc_18003E521
0x18003e4d5  cmp     edi, 3
0x18003e4d8  jz      short loc_18003E521
0x18003e4da  mov     r9d, edi
0x18003e4dd  lea     r8, aCreatepartitio_9; "CreatePartition: Asked to create partit"...
0x18003e4e4  mov     edx, 2000000h
0x18003e4e9  mov     rcx, rsi
0x18003e4ec  call    LibLog
0x18003e4f1  mov     ebx, 80042565h
0x18003e4f6  jmp     loc_18003ED73
0x18003e4fb  mov     esi, 2
0x18003e500  jmp     short loc_18003E524
0x18003e502  mov     r9d, eax
0x18003e505  lea     r8, aCreatepartitio_0; "CreatePartition: Failed to decide the t"...
0x18003e50c  mov     edx, 2000000h
0x18003e511  mov     rcx, rsi
0x18003e514  call    LibLog
0x18003e519  jmp     loc_18003ED73
0x18003e51e  mov     edi, r15d
0x18003e521  mov     esi, r15d
0x18003e524  mov     rcx, [rsp+200h+var_1B0]
0x18003e529  mov     [rsp+200h+pv], r14
0x18003e52e  test    rcx, rcx
0x18003e531  jz      loc_18003ED6E
0x18003e537  mov     rax, [rcx]
0x18003e53a  lea     rdx, [rsp+200h+pv]
0x18003e53f  mov     rax, [rax+20h]
0x18003e543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e548  mov     rcx, [rsp+200h+pv]
0x18003e54d  mov     ebx, eax
0x18003e54f  cmp     eax, 80042417h
0x18003e554  jnz     short loc_18003E562
0x18003e556  test    rcx, rcx
0x18003e559  jnz     short loc_18003E567
0x18003e55b  mov     r14d, r15d
0x18003e55e  xor     ebx, ebx
0x18003e560  jmp     short loc_18003E573
0x18003e562  test    rcx, rcx
0x18003e565  jz      short loc_18003E573
0x18003e567  mov     rax, [rcx]
0x18003e56a  mov     rax, [rax+10h]
0x18003e56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e573  test    ebx, ebx
0x18003e575  js      loc_18003ED69
0x18003e57b  mov     r15d, 2000000h
0x18003e581  cmp     r14d, 1
0x18003e585  jnz     short loc_18003E5AE
0x18003e587  lea     rax, [rsp+200h+var_198]
0x18003e58c  mov     r8d, esi; enum _VDS_PARTITION_STYLE
0x18003e58f  lea     r9, [rsp+200h+var_1B0]; struct IVdsDisk **
0x18003e594  mov     [rsp+200h+var_1E0], rax; struct IVdsAdvancedDisk **
0x18003e599  mov     edx, r13d; int
0x18003e59c  mov     rcx, r12; struct IVdsService *
0x18003e59f  call    ?ConvertUnallocatedDisk@@YAJPEAUIVdsService@@HW4_VDS_PARTITION_STYLE@@PEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@@Z; ConvertUnallocatedDisk(IVdsService *,int,_VDS_PARTITION_STYLE,IVdsDisk * *,IVdsAdvancedDisk * *)
0x18003e5a4  mov     ebx, eax
0x18003e5a6  xor     r14d, r14d
0x18003e5a9  jmp     loc_18003E7A2
0x18003e5ae  test    r14d, r14d
0x18003e5b1  jnz     loc_18003E7AC
0x18003e5b7  xor     r14d, r14d
0x18003e5ba  lea     rcx, [rbp+100h+var_13C]; void *
0x18003e5be  xor     edx, edx; Val
0x18003e5c0  mov     [rbp+100h+var_140], r14d
0x18003e5c4  lea     r8d, [r14+7Ch]; Size
0x18003e5c8  call    memset_0
0x18003e5cd  mov     rcx, [rsp+200h+var_1B0]
0x18003e5d2  lea     rdx, [rbp+100h+var_140]
0x18003e5d6  mov     [rsp+200h+var_1C0], r14d
0x18003e5db  mov     rax, [rcx]
0x18003e5de  mov     rax, [rax+18h]
0x18003e5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5e7  mov     ebx, eax
0x18003e5e9  test    eax, eax
0x18003e5eb  js      loc_18003E72A
0x18003e5f1  lea     r9, [rsp+200h+var_1A8]; struct IVdsAdvancedDisk **
0x18003e5f6  mov     [rsp+200h+var_1A0], r14
0x18003e5fb  lea     r8, [rsp+200h+var_1A0]; struct IVdsDisk **
0x18003e600  mov     [rsp+200h+var_1A8], r14
0x18003e605  mov     edx, r13d; int
0x18003e608  mov     [rsp+200h+var_1E0], r14; struct IVdsAdvancedDisk2 **
0x18003e60d  mov     rcx, r12; struct IVdsService *
0x18003e610  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x18003e615  mov     ebx, eax
0x18003e617  test    eax, eax
0x18003e619  js      short loc_18003E65F
0x18003e61b  mov     rcx, [rsp+200h+var_1A0]
0x18003e620  test    rcx, rcx
0x18003e623  jz      short loc_18003E664
0x18003e625  mov     r9, [rsp+200h+var_1A8]
0x18003e62a  test    r9, r9
0x18003e62d  jz      short loc_18003E687
0x18003e62f  mov     [rsp+200h+pv], r14
0x18003e634  lea     r8, [rsp+200h+var_1C0]
0x18003e639  mov     rax, [r9]
0x18003e63c  lea     rdx, [rsp+200h+pv]
0x18003e641  mov     rcx, r9
0x18003e644  mov     rax, [rax+20h]
0x18003e648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e64d  mov     rcx, [rsp+200h+pv]; pv
0x18003e652  mov     ebx, eax
0x18003e654  test    rcx, rcx
0x18003e657  jz      short loc_18003E65F
0x18003e659  call    cs:__imp_CoTaskMemFree
0x18003e65f  mov     rcx, [rsp+200h+var_1A0]
0x18003e664  mov     rdx, [rsp+200h+var_1A8]
0x18003e669  test    rdx, rdx
0x18003e66c  jz      short loc_18003E687
0x18003e66e  mov     rax, [rdx]
0x18003e671  mov     rcx, rdx
0x18003e674  mov     rax, [rax+10h]
0x18003e678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e67d  mov     rcx, [rsp+200h+var_1A0]
0x18003e682  mov     [rsp+200h+var_1A8], r14
0x18003e687  test    rcx, rcx
0x18003e68a  jz      short loc_18003E698
0x18003e68c  mov     rax, [rcx]
0x18003e68f  mov     rax, [rax+10h]
0x18003e693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e698  test    ebx, ebx
0x18003e69a  js      loc_18003E72A
0x18003e6a0  cmp     [rbp+100h+var_FC], esi
0x18003e6a3  jz      loc_18003E747
0x18003e6a9  cmp     [rsp+200h+var_1C0], r14d
0x18003e6ae  jnz     loc_18003E747
0x18003e6b4  mov     r8d, esi; enum _VDS_PARTITION_STYLE
0x18003e6b7  mov     edx, r13d; int
0x18003e6ba  mov     rcx, r12; struct IVdsService *
0x18003e6bd  call    ?ConvertDiskStyle@@YAJPEAUIVdsService@@HW4_VDS_PARTITION_STYLE@@@Z; ConvertDiskStyle(IVdsService *,int,_VDS_PARTITION_STYLE)
0x18003e6c2  lea     rcx, aGpt; "GPT"
0x18003e6c9  mov     ebx, eax
0x18003e6cb  mov     r9d, r13d
0x18003e6ce  test    eax, eax
0x18003e6d0  js      short loc_18003E6FB
0x18003e6d2  mov     rax, [rsp+200h+var_190]
0x18003e6d7  lea     r8, aCreatepartitio_6; "CreatePartition: Automatically converte"...
0x18003e6de  cmp     esi, 1
0x18003e6e1  mov     edx, 4000000h
0x18003e6e6  mov     [rax], r14
0x18003e6e9  lea     rax, aMbr; "MBR"
0x18003e6f0  cmovnz  rax, rcx
0x18003e6f4  mov     [rsp+200h+var_1E0], rax
0x18003e6f9  jmp     short loc_18003E73B
0x18003e6fb  cmp     esi, 1
0x18003e6fe  mov     dword ptr [rsp+200h+var_1D8], ebx
0x18003e702  lea     rax, aMbr; "MBR"
0x18003e709  mov     edx, r15d
0x18003e70c  cmovnz  rax, rcx
0x18003e710  lea     r8, aCreatepartitio_3; "CreatePartition: Failed to convert disk"...
0x18003e717  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18003e71e  mov     [rsp+200h+var_1E0], rax
0x18003e723  call    LibLog
0x18003e728  jmp     short loc_18003E747
0x18003e72a  mov     dword ptr [rsp+200h+var_1E0], ebx
0x18003e72e  lea     r8, aCreatepartitio_8; "CreatePartition: Failed to get property"...
0x18003e735  mov     r9d, r13d
0x18003e738  mov     edx, r15d
0x18003e73b  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18003e742  call    LibLog
0x18003e747  mov     rcx, [rbp+100h+var_E8]; pv
0x18003e74b  test    rcx, rcx
0x18003e74e  jz      short loc_18003E75A
0x18003e750  call    cs:__imp_CoTaskMemFree
0x18003e756  mov     [rbp+100h+var_E8], r14
0x18003e75a  mov     rcx, [rbp+100h+var_E0]; pv
0x18003e75e  test    rcx, rcx
0x18003e761  jz      short loc_18003E76D
0x18003e763  call    cs:__imp_CoTaskMemFree
0x18003e769  mov     [rbp+100h+var_E0], r14
0x18003e76d  mov     rcx, [rbp+100h+var_D8]; pv
0x18003e771  test    rcx, rcx
0x18003e774  jz      short loc_18003E780
0x18003e776  call    cs:__imp_CoTaskMemFree
0x18003e77c  mov     [rbp+100h+var_D8], r14
0x18003e780  mov     rcx, [rbp+100h+var_D0]; pv
0x18003e784  test    rcx, rcx
0x18003e787  jz      short loc_18003E793
0x18003e789  call    cs:__imp_CoTaskMemFree
0x18003e78f  mov     [rbp+100h+var_D0], r14
0x18003e793  mov     rcx, [rbp+100h+var_C8]; pv
0x18003e797  test    rcx, rcx
0x18003e79a  jz      short loc_18003E7A2
0x18003e79c  call    cs:__imp_CoTaskMemFree
0x18003e7a2  test    ebx, ebx
0x18003e7a4  js      loc_18003ED73
0x18003e7aa  jmp     short loc_18003E7AF
0x18003e7ac  xor     r14d, r14d
0x18003e7af  mov     rcx, [rsp+200h+var_1B0]
0x18003e7b4  lea     rdx, [rbp+100h+var_C0]
0x18003e7b8  mov     rax, [rcx]
0x18003e7bb  mov     rax, [rax+18h]
0x18003e7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7c4  mov     ebx, eax
0x18003e7c6  test    eax, eax
0x18003e7c8  js      loc_18003ED73
0x18003e7ce  cmp     [rbp+100h+var_7C], esi
0x18003e7d4  jnz     loc_18003ED4B
0x18003e7da  xor     edx, edx; Val
0x18003e7dc  lea     rcx, [rbp+100h+var_140]; void *
0x18003e7e0  lea     r8d, [rdx+78h]; Size
0x18003e7e4  call    memset_0
0x18003e7e9  mov     [rbp+100h+var_140], esi
0x18003e7ec  cmp     esi, 1
0x18003e7ef  jnz     short loc_18003E805
0x18003e7f1  cmp     edi, 3
0x18003e7f4  mov     byte ptr [rbp+100h+var_138+1], r14b
0x18003e7f8  setnz   al
0x18003e7fb  add     al, 5
0x18003e7fd  mov     byte ptr [rbp+100h+var_138], al
0x18003e800  jmp     loc_18003E8E9
0x18003e805  cmp     esi, 2
0x18003e808  jnz     loc_18003ED44
0x18003e80e  mov     rax, 8000000000000000h
0x18003e818  mov     [rbp+100h+var_118], rax
0x18003e81c  cmp     edi, 5
0x18003e81f  jnz     short loc_18003E841
0x18003e821  mov     eax, dword ptr cs:PARTITION_MSFT_RESERVED_GUID.Data4+2
0x18003e827  movsd   xmm0, qword ptr cs:PARTITION_MSFT_RESERVED_GUID.Data1+2
0x18003e82f  mov     [rbp+100h+var_12E], eax
0x18003e832  movzx   eax, word ptr cs:PARTITION_MSFT_RESERVED_GUID.Data4+6
0x18003e839  mov     [rbp+100h+var_138], 0E316h
0x18003e83f  jmp     short loc_18003E8BB
0x18003e841  cmp     edi, 6
0x18003e844  jnz     short loc_18003E866
0x18003e846  mov     eax, dword ptr cs:PARTITION_SYSTEM_GUID.Data4+2
0x18003e84c  movsd   xmm0, qword ptr cs:PARTITION_SYSTEM_GUID.Data1+2
0x18003e854  mov     [rbp+100h+var_12E], eax
0x18003e857  movzx   eax, word ptr cs:PARTITION_SYSTEM_GUID.Data4+6
0x18003e85e  mov     [rbp+100h+var_138], 7328h
0x18003e864  jmp     short loc_18003E8BB
0x18003e866  cmp     edi, 7
  ... truncated ...
```
