# CBlbVdsHelperLibrary::FillDiskInformation(_WSB_DISK_INFO *,IVdsService *,IVdsDisk *,bool)

- ea: `0x140125bf0`
- end: `0x1401267e9`
- name: `?FillDiskInformation@CBlbVdsHelperLibrary@@AEAAJPEAU_WSB_DISK_INFO@@PEAUIVdsService@@PEAUIVdsDisk@@_N@Z`
- size: `3065`
- prototype: `__int64 __fastcall(CBlbVdsHelperLibrary *__hidden this, struct _WSB_DISK_INFO *, struct IVdsService *, struct IVdsDisk *, bool)`
- caller_count: `2`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x140125810`
- `0x140128620`

## callees

- `0x140005334`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x140014bc0`
- `0x140015010`
- `0x14003c434`
- `0x14003c54c`
- `0x1400889f0`
- `0x14008ba2c`
- `0x14008f8ec`
- `0x1400f76f0`
- `0x140107fb0`
- `0x140121f14`
- `0x14012365c`
- `0x1401244c0`
- `0x140124b3c`
- `0x140124cb0`
- `0x140125bf0`
- `0x1401267f0`
- `0x14012c024`
- `0x140137010`

## import_xrefs

- `msvcrt!_wtol` at `0x140125ccf`
- `msvcrt!_wtol` at `0x140125ccf`
- `ole32!CoTaskMemAlloc` at `0x140125c33`
- `ole32!CoTaskMemAlloc` at `0x140125ee9`
- `ole32!CoTaskMemAlloc` at `0x140125f16`
- `ole32!CoTaskMemAlloc` at `0x140125f43`
- `ole32!CoTaskMemAlloc` at `0x140125f70`
- `ole32!CoTaskMemAlloc` at `0x140125c33`
- `ole32!CoTaskMemAlloc` at `0x140125ee9`
- `ole32!CoTaskMemAlloc` at `0x140125f16`
- `ole32!CoTaskMemAlloc` at `0x140125f43`
- `ole32!CoTaskMemAlloc` at `0x140125f70`
- `ole32!CoTaskMemFree` at `0x140125fbd`
- `ole32!CoTaskMemFree` at `0x140125fe2`
- `ole32!CoTaskMemFree` at `0x140126027`
- `ole32!CoTaskMemFree` at `0x14012603b`
- `ole32!CoTaskMemFree` at `0x1401263ad`
- `ole32!CoTaskMemFree` at `0x14012666c`
- `ole32!CoTaskMemFree` at `0x140126795`
- `ole32!CoTaskMemFree` at `0x1401267ab`
- `ole32!CoTaskMemFree` at `0x140125fbd`
- `ole32!CoTaskMemFree` at `0x140125fe2`
- `ole32!CoTaskMemFree` at `0x140126027`
- `ole32!CoTaskMemFree` at `0x14012603b`
- `ole32!CoTaskMemFree` at `0x1401263ad`
- `ole32!CoTaskMemFree` at `0x14012666c`
- `ole32!CoTaskMemFree` at `0x140126795`
- `ole32!CoTaskMemFree` at `0x1401267ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CBlbVdsHelperLibrary::FillDiskInformation(
        CBlbVdsHelperLibrary *this,
        struct _WSB_DISK_INFO *a2,
        struct IVdsService *a3,
        struct IVdsDisk *a4,
        bool a5)
{
  unsigned __int16 *v7; // r13
  _OWORD *v8; // rbx
  int DeviceProperties; // esi
  int v10; // eax
  int v11; // r9d
  int v12; // r8d
  unsigned int v13; // eax
  PVOID *v14; // rcx
  _DWORD *v15; // rax
  void *v16; // rax
  void *v17; // rax
  void *v18; // rax
  void *v19; // rax
  char v20; // bl
  int i; // eax
  void *v22; // rcx
  void *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rax
  HRESULT (__stdcall *GetObjectA)(IVdsService *, VDS_OBJECT_ID, VDS_OBJECT_TYPE, IUnknown **); // rbx
  _QWORD *v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  struct IUnknown *v31; // rcx
  struct IUnknown *v32; // rax
  int v33; // ebx
  int BitLockerFlags; // eax
  PVOID *v35; // rcx
  int FileSystemSpace; // eax
  int SystemVolumeGlobalRootPath; // eax
  int v38; // ebx
  int VolumeFileSystem; // eax
  int v40; // eax
  PVOID *v42; // rcx
  __int64 v43; // rbx
  int v44; // [rsp+28h] [rbp-51h]
  int v45; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 *v46; // [rsp+40h] [rbp-39h] BYREF
  _DWORD *v47; // [rsp+48h] [rbp-31h] BYREF
  struct IUnknown *v48; // [rsp+50h] [rbp-29h] BYREF
  struct IUnknown *v49; // [rsp+58h] [rbp-21h] BYREF
  int v50; // [rsp+60h] [rbp-19h]
  unsigned int v51[2]; // [rsp+68h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v53[2]; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int64 v54[8]; // [rsp+88h] [rbp+Fh] BYREF

  v7 = 0;
  v46 = 0;
  pv = 0;
  v8 = CoTaskMemAlloc(0x80u);
  v53[0] = v8;
  memset_0(v8, 0, 0x80u);
  if ( ((int (__fastcall *)(struct IVdsDisk *, _OWORD *))a4->lpVtbl->GetProperties)(a4, v8) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
    }
    DeviceProperties = 0;
LABEL_148:
    VDS_DISK_PROP_SMART<_VDS_DISK_PROP>::~VDS_DISK_PROP_SMART<_VDS_DISK_PROP>((__int64)v53);
    return (unsigned int)DeviceProperties;
  }
  *((_OWORD *)a2 + 1) = *v8;
  DeviceProperties = BlbutilDuplicateString(*((const unsigned __int16 **)v8 + 13), (unsigned __int16 **)a2 + 5, 0);
  if ( DeviceProperties < 0 )
    goto LABEL_148;
  *((_DWORD *)a2 + 8) = _wtol((const wchar_t *)(*((_QWORD *)v8 + 12) + 34LL));
  *((_QWORD *)a2 + 6) = *((_QWORD *)v8 + 5);
  DeviceProperties = BlbQueryDeviceProperties(*((LPCWSTR *)v8 + 15), (unsigned int *)a2 + 26);
  if ( DeviceProperties < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
    }
    goto LABEL_148;
  }
  if ( a5 )
  {
    *(_DWORD *)a2 = *((_DWORD *)a2 + 12);
    *((_WORD *)a2 + 2) = *((_WORD *)a2 + 16);
    *((_QWORD *)a2 + 7) = *((_QWORD *)a2 + 6);
    *((_DWORD *)a2 + 17) = 0;
    goto LABEL_156;
  }
  if ( *((_DWORD *)v8 + 17) == 1 )
    *(_DWORD *)a2 = *((_DWORD *)v8 + 18);
  else
    *(_OWORD *)a2 = *(_OWORD *)((char *)v8 + 72);
  v47 = 0;
  v45 = 0;
  v10 = ((__int64 (__fastcall *)(struct IVdsDisk *, _DWORD **, int *))a4->lpVtbl->QueryExtents)(a4, &v47, &v45);
  DeviceProperties = v10;
  if ( v10 < 0 )
  {
    if ( v10 != -2147212220 )
      BlbAssert("base\\stor\\blb\\wsbutil\\wsbvdshelperlibrary.cpp", 0x65Au, "hr == VDS_E_PACK_OFFLINE");
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
    }
    *((_QWORD *)a2 + 7) = 0;
    *((_DWORD *)a2 + 17) = 0;
    *((_BYTE *)a2 + 64) = 1;
    DeviceProperties = 0;
LABEL_26:
    VDS_STRUCTURES_SMART<unsigned short *>::~VDS_STRUCTURES_SMART<unsigned short *>((void **)&v47);
LABEL_199:
    CoTaskMemFree(v7);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_148;
  }
  v11 = 0;
  v12 = 102;
  while ( 1 )
  {
    if ( v11 >= v45 )
    {
      v15 = (_DWORD *)((char *)a2 + 104);
      goto LABEL_43;
    }
    v13 = v47[20 * v11 + 4];
    if ( (v13 > 6 || !_bittest(&v12, v13)) && v13 != 0x7FFF )
      break;
    ++v11;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v44 = v47[20 * v11 + 4];
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 4u )
      WPP_SF_d(v14[2], 82, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
  }
  v15 = (_DWORD *)((char *)a2 + 104);
  *((_DWORD *)a2 + 26) |= 8u;
LABEL_43:
  if ( *((_BYTE *)this + 80) )
    *v15 |= 0x10u;
  *((_QWORD *)a2 + 7) = 0;
  v16 = CoTaskMemAlloc(16LL * v45);
  *((_QWORD *)a2 + 9) = v16;
  if ( v16 )
  {
    memset_0(v16, 0, 16LL * v45);
    v17 = CoTaskMemAlloc(4LL * v45);
    *((_QWORD *)a2 + 10) = v17;
    if ( v17 )
    {
      memset_0(v17, 0, 4LL * v45);
      v18 = CoTaskMemAlloc(8LL * v45);
      *((_QWORD *)a2 + 11) = v18;
      if ( v18 )
      {
        memset_0(v18, 0, 8LL * v45);
        v19 = CoTaskMemAlloc(8LL * v45);
        *((_QWORD *)a2 + 12) = v19;
        if ( v19 )
        {
          v20 = 1;
          memset_0(v19, 0, 8LL * v45);
          *((_DWORD *)a2 + 17) = 0;
          for ( i = 0; ; i = v50 + 1 )
          {
            v50 = i;
            if ( i >= v45 )
            {
              if ( v20 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
                }
                *((_QWORD *)a2 + 7) = *((_QWORD *)a2 + 6);
              }
              VDS_STRUCTURES_SMART<unsigned short *>::~VDS_STRUCTURES_SMART<unsigned short *>((void **)&v47);
LABEL_156:
              v42 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_dS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  95,
                  (unsigned int)WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
                  *((_DWORD *)a2 + 8),
                  *((_QWORD *)a2 + 5));
                v42 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( !*((_DWORD *)a2 + 17) )
              {
                if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 1) != 0 && *((_BYTE *)v42 + 25) >= 4u )
                  WPP_SF_d(v42[2], 96, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
                *((_BYTE *)a2 + 64) = 1;
                v42 = (PVOID *)WPP_GLOBAL_Control;
              }
              v43 = 0;
              while ( 2 )
              {
                if ( (unsigned int)v43 >= *((_DWORD *)a2 + 17) )
                  goto LABEL_199;
                if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 1) != 0 && *((_BYTE *)v42 + 25) >= 4u )
                {
                  WPP_SF_S(
                    v42[2],
                    97,
                    WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
                    *(_QWORD *)(*((_QWORD *)a2 + 11) + 8 * v43));
                  v42 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( (*(_BYTE *)(*((_QWORD *)a2 + 10) + 4 * v43) & 1) != 0 )
                {
                  if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 1) != 0 && *((_BYTE *)v42 + 25) >= 4u )
                  {
                    WPP_SF_(v42[2], 98, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
                    goto LABEL_192;
                  }
                }
                else
                {
                  CoTaskMemFree(v7);
                  v46 = 0;
                  DeviceProperties = BlbutilQueryVolumeName(
                                       (struct _GUID *)(*((_QWORD *)a2 + 9) + 16 * v43),
                                       *(_DWORD *)(*((_QWORD *)a2 + 10) + 4 * v43),
                                       &v46,
                                       0);
                  if ( DeviceProperties < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
                    }
                    v7 = v46;
                    goto LABEL_199;
                  }
                  v7 = v46;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    WPP_SF_S(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      100,
                      WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
                      v46);
                  }
                  DeviceProperties = BlbQueryVolumeLabel(v7, (unsigned __int16 **)(*((_QWORD *)a2 + 12) + 8 * v43));
                  if ( DeviceProperties >= 0 )
                  {
                    v42 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                    {
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        102,
                        WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
                        *(_QWORD *)(*((_QWORD *)a2 + 12) + 8 * v43));
LABEL_192:
                      v42 = (PVOID *)WPP_GLOBAL_Control;
                    }
                  }
                  else
                  {
                    v42 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        101,
                        WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
                      v42 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    DeviceProperties = 0;
                  }
                }
                v43 = (unsigned int)(v43 + 1);
                continue;
              }
            }
            v22 = *(void **)(*((_QWORD *)a2 + 11) + 8LL * *((unsigned int *)a2 + 17));
            if ( v22 )
            {
              CoTaskMemFree(v22);
              *(_QWORD *)(*((_QWORD *)a2 + 11) + 8LL * *((unsigned int *)a2 + 17)) = 0;
            }
            v23 = *(void **)(*((_QWORD *)a2 + 12) + 8LL * *((unsigned int *)a2 + 17));
            if ( v23 )
            {
              CoTaskMemFree(v23);
              *(_QWORD *)(*((_QWORD *)a2 + 12) + 8LL * *((unsigned int *)a2 + 17)) = 0;
            }
            *(_DWORD *)(*((_QWORD *)a2 + 10) + 4LL * *((unsigned int *)a2 + 17)) = 0;
            *(GUID *)(*((_QWORD *)a2 + 9) + 16LL * *((unsigned int *)a2 + 17)) = GUID_NULL;
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( v7 )
            {
              CoTaskMemFree(v7);
              v7 = 0;
              v46 = 0;
            }
            v24 = 20LL * v50;
            *(_QWORD *)v51 = v24 * 4;
            v25 = v47[v24 + 4];
            switch ( v25 )
            {
              case 1:
              case 0x7FFF:
                *((_QWORD *)a2 + 7) += *(_QWORD *)&v47[v24 + 8];
                break;
              case 2:
                v26 = *(_QWORD *)&v47[v24 + 10] - *(_QWORD *)&GUID_NULL.Data1;
                if ( !v26 )
                  v26 = *(_QWORD *)&v47[v24 + 12] - *(_QWORD *)GUID_NULL.Data4;
                if ( v26 )
                {
                  v48 = 0;
                  v49 = 0;
                  GetObjectA = a3->lpVtbl->GetObjectA;
                  v28 = ATL::CComPtrBase<IRegisteredTask>::operator&(&v48);
                  *(_OWORD *)v54 = *(_OWORD *)((char *)v47 + *(_QWORD *)v51 + 40);
                  if ( ((int (__fastcall *)(struct IVdsService *, unsigned __int64 *, __int64, _QWORD *, int))GetObjectA)(
                         a3,
                         v54,
                         11,
                         v28,
                         v44) < 0 )
                  {
                    v29 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                    {
                      v30 = 83;
                      goto LABEL_70;
                    }
                    goto LABEL_71;
                  }
                  v31 = v48;
                  v32 = v49;
                  if ( v49 != v48 )
                  {
                    ATL::AtlComQIPtrAssign(&v49, v48, &GUID_88306bb2_e71f_478c_86a2_79da200a0f11);
                    v31 = v48;
                    v32 = v49;
                  }
                  if ( !v32 )
                  {
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v49);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v48);
                    VDS_STRUCTURES_SMART<unsigned short *>::~VDS_STRUCTURES_SMART<unsigned short *>((void **)&v47);
                    DeviceProperties = -2147467262;
                    goto LABEL_148;
                  }
                  if ( v31 )
                  {
                    ATL::AtlComPtrAssign(&v48, 0);
                    v32 = v49;
                  }
                  if ( (int)CBlbVdsHelperLibrary::FillVolumeInformation(
                              (CBlbVdsHelperLibrary *)v31,
                              *((struct _GUID **)a2 + 9),
                              *((unsigned __int16 ***)a2 + 11),
                              *((_DWORD *)a2 + 17),
                              (struct IVdsVolume *)v32) >= 0 )
                  {
                    if ( (int)BlbutilQueryVolumeName(
                                (struct _GUID *)(*((_QWORD *)a2 + 9) + 16LL * *((unsigned int *)a2 + 17)),
                                *(_DWORD *)(*((_QWORD *)a2 + 10) + 4LL * *((unsigned int *)a2 + 17)),
                                &v46,
                                0) >= 0 )
                    {
                      v33 = 1;
                      v7 = v46;
                      DeviceProperties = BlbQueryVolumeFileSystem(v46, (unsigned __int16 **)&pv);
                      if ( DeviceProperties < 0 )
                      {
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            86,
                            WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
                        }
                        DeviceProperties = 0;
                        v33 = 0;
                      }
                      if ( pv )
                      {
                        v54[0] = 0;
                        v51[0] = 0;
                        BitLockerFlags = BlbQueryBitLockerFlags(v7, 1u, v51);
                        DeviceProperties = BitLockerFlags;
                        if ( BitLockerFlags >= 0 )
                        {
                          v35 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        else
                        {
                          v35 = (PVOID *)WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                          {
                            WPP_SF_Sd(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              87,
                              (unsigned int)WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
                              (_DWORD)v7,
                              BitLockerFlags);
                            v35 = (PVOID *)WPP_GLOBAL_Control;
                          }
                          DeviceProperties = 0;
                        }
                        if ( (v51[0] & 0x800) != 0 )
                        {
                          if ( v35 != &WPP_GLOBAL_Control
                            && (*((_BYTE *)v35 + 28) & 1) != 0
                            && *((_BYTE *)v35 + 25) >= 4u )
                          {
                            WPP_SF_(v35[2], 89, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
                          }
                        }
                        else
                        {
                          FileSystemSpace = BlbQueryFileSystemSpace(v7, (unsigned __int64 *)v51, v54);
                          DeviceProperties = FileSystemSpace;
                          if ( FileSystemSpace < 0 )
                          {
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                            {
                              WPP_SF_Sd(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                88,
                                (unsigned int)WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
                                (_DWORD)v7,
                                FileSystemSpace);
                            }
                            DeviceProperties = 0;
                          }
                        }
                        *((_QWORD *)a2 + 7) += v54[0];
                      }
                      else if ( v33 )
                      {
                        *((_QWORD *)a2 + 7) += *(_QWORD *)((char *)v47 + *(_QWORD *)v51 + 32);
                      }
                      ++*((_DWORD *)a2 + 17);
                      goto LABEL_72;
                    }
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                    {
                      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
                    }
                    DeviceProperties = 0;
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v49);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v48);
                    v7 = v46;
                  }
                  else
                  {
                    v29 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                    {
                      v30 = 84;
LABEL_70:
                      WPP_SF_d(v29[2], v30, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
                    }
LABEL_71:
                    DeviceProperties = 0;
LABEL_72:
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v49);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v48);
                  }
LABEL_73:
                  v20 = 0;
                  continue;
                }
LABEL_144:
                v20 = 0;
                continue;
              case 4:
                v20 = 0;
                *(_DWORD *)(*((_QWORD *)a2 + 10) + 4LL * *((unsigned int *)a2 + 17)) |= 1u;
                CoTaskMemFree(v7);
                v46 = 0;
                SystemVolumeGlobalRootPath = BlbutilGetSystemVolumeGlobalRootPath(&v46);
                if ( SystemVolumeGlobalRootPath >= 0 )
                {
                  v7 = v46;
                  DeviceProperties = BlbutilDuplicateString(
                                       v46,
                                       (unsigned __int16 **)(*((_QWORD *)a2 + 11) + 8LL * *((unsigned int *)a2 + 17)),
                                       0);
                  if ( DeviceProperties < 0 )
                    goto LABEL_26;
                  v38 = 1;
                  VolumeFileSystem = BlbQueryVolumeFileSystem(v7, (unsigned __int16 **)&pv);
                  DeviceProperties = VolumeFileSystem;
                  if ( VolumeFileSystem < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                    {
                      WPP_SF_Sd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        92,
                        (unsigned int)WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
                        (_DWORD)v7,
                        VolumeFileSystem);
                    }
                    DeviceProperties = 0;
                    v38 = 0;
                  }
                  if ( pv )
                  {
                    v54[0] = 0;
                    v40 = BlbQueryFileSystemSpace(v7, (unsigned __int64 *)&v48, v54);
                    DeviceProperties = v40;
                    if ( v40 >= 0 )
                    {
                      *((_QWORD *)a2 + 7) += v54[0];
                    }
                    else
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                      {
                        WPP_SF_Sd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          93,
                          (unsigned int)WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
                          (_DWORD)v7,
                          v40);
                      }
                      DeviceProperties = 0;
                    }
                  }
                  else if ( v38 )
                  {
                    *((_QWORD *)a2 + 7) += *(_QWORD *)((char *)v47 + *(_QWORD *)v51 + 32);
                  }
                  ++*((_DWORD *)a2 + 17);
                  goto LABEL_73;
                }
                v7 = v46;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    91,
                    (unsigned int)WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
                    (_DWORD)v46,
                    SystemVolumeGlobalRootPath);
                }
                DeviceProperties = 0;
                break;
              default:
                goto LABEL_144;
            }
          }
        }
      }
    }
  }
  VDS_STRUCTURES_SMART<unsigned short *>::~VDS_STRUCTURES_SMART<unsigned short *>((void **)&v47);
  VDS_DISK_PROP_SMART<_VDS_DISK_PROP>::~VDS_DISK_PROP_SMART<_VDS_DISK_PROP>((__int64)v53);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140125bf0  mov     rax, rsp
0x140125bf3  mov     [rax+10h], rbx
0x140125bf7  mov     [rax+20h], r9
0x140125bfb  mov     [rax+18h], r8
0x140125bff  mov     [rax+8], rcx
0x140125c03  push    rbp
0x140125c04  push    rsi
0x140125c05  push    rdi
0x140125c06  push    r12
0x140125c08  push    r13
0x140125c0a  push    r14
0x140125c0c  push    r15
0x140125c0e  lea     rbp, [rax-57h]
0x140125c12  sub     rsp, 90h
0x140125c19  mov     rsi, r9
0x140125c1c  mov     rdi, rdx
0x140125c1f  xor     r13d, r13d
0x140125c22  mov     [rbp+4Fh+var_88], r13
0x140125c26  mov     [rbp+4Fh+pv], r13
0x140125c2a  mov     r14d, 80h
0x140125c30  mov     ecx, r14d; cb
0x140125c33  call    cs:__imp_CoTaskMemAlloc
0x140125c39  mov     rbx, rax
0x140125c3c  mov     [rbp+4Fh+var_50], rax
0x140125c40  mov     r8d, r14d; Size
0x140125c43  xor     edx, edx; Val
0x140125c45  mov     rcx, rax; void *
0x140125c48  call    memset_0
0x140125c4d  nop
0x140125c4e  mov     rax, [rsi]
0x140125c51  mov     rdx, rbx
0x140125c54  mov     rcx, rsi
0x140125c57  mov     rax, [rax+18h]
0x140125c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140125c60  test    eax, eax
0x140125c62  jns     short loc_140125CA5
0x140125c64  lea     r15, WPP_GLOBAL_Control
0x140125c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140125c72  cmp     rcx, r15
0x140125c75  jz      short loc_140125C9E
0x140125c77  lea     r14d, [r13+1]
0x140125c7b  test    [rcx+1Ch], r14b
0x140125c7f  jz      short loc_140125C9E
0x140125c81  cmp     byte ptr [rcx+19h], 2
0x140125c85  jb      short loc_140125C9E
0x140125c87  lea     edx, [r13+4Fh]
0x140125c8b  mov     r9d, eax
0x140125c8e  lea     r8, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x140125c95  mov     rcx, [rcx+10h]
0x140125c99  call    WPP_SF_d
0x140125c9e  xor     esi, esi
0x140125ca0  jmp     loc_14012652B
0x140125ca5  movups  xmm0, xmmword ptr [rbx]
0x140125ca8  movdqu  xmmword ptr [rdi+10h], xmm0
0x140125cad  lea     rdx, [rdi+28h]; unsigned __int16 **
0x140125cb1  xor     r8d, r8d; unsigned __int64
0x140125cb4  mov     rcx, [rbx+68h]; unsigned __int16 *
0x140125cb8  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140125cbd  mov     esi, eax
0x140125cbf  test    eax, eax
0x140125cc1  js      loc_14012652B
0x140125cc7  mov     rcx, [rbx+60h]
0x140125ccb  add     rcx, 22h ; '"'; String
0x140125ccf  call    cs:__imp__wtol
0x140125cd5  mov     [rdi+20h], eax
0x140125cd8  mov     rax, [rbx+28h]
0x140125cdc  mov     [rdi+30h], rax
0x140125ce0  lea     rdx, [rdi+68h]; unsigned int *
0x140125ce4  mov     rcx, [rbx+78h]; lpFileName
0x140125ce8  call    ?BlbQueryDeviceProperties@@YAJPEAGPEAK@Z; BlbQueryDeviceProperties(ushort *,ulong *)
0x140125ced  mov     esi, eax
0x140125cef  test    eax, eax
0x140125cf1  jns     short loc_140125D40
0x140125cf3  lea     r15, WPP_GLOBAL_Control
0x140125cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x140125d01  cmp     rcx, r15
0x140125d04  jz      loc_14012652B
0x140125d0a  mov     r14d, 1
0x140125d10  test    [rcx+1Ch], r14b
0x140125d14  jz      loc_14012652B
0x140125d1a  cmp     byte ptr [rcx+19h], 2
0x140125d1e  jb      loc_14012652B
0x140125d24  lea     edx, [r14+4Fh]
0x140125d28  mov     r9d, eax
0x140125d2b  lea     r8, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x140125d32  mov     rcx, [rcx+10h]
0x140125d36  call    WPP_SF_d
0x140125d3b  jmp     loc_14012652B
0x140125d40  lea     r15, WPP_GLOBAL_Control
0x140125d47  mov     r14d, 1
0x140125d4d  lea     r12, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x140125d54  cmp     [rbp+4Fh+arg_20], 0
0x140125d58  jz      short loc_140125D7B
0x140125d5a  mov     eax, [rdi+30h]
0x140125d5d  mov     [rdi], eax
0x140125d5f  movzx   eax, word ptr [rdi+20h]
0x140125d63  mov     [rdi+4], ax
0x140125d67  mov     rax, [rdi+30h]
0x140125d6b  mov     [rdi+38h], rax
0x140125d6f  mov     dword ptr [rdi+44h], 0
0x140125d76  jmp     loc_140126579
0x140125d7b  cmp     [rbx+44h], r14d
0x140125d7f  jnz     short loc_140125D88
0x140125d81  mov     eax, [rbx+48h]
0x140125d84  mov     [rdi], eax
0x140125d86  jmp     short loc_140125D90
0x140125d88  movups  xmm0, xmmword ptr [rbx+48h]
0x140125d8c  movdqu  xmmword ptr [rdi], xmm0
0x140125d90  mov     [rbp+4Fh+var_80], 0
0x140125d98  mov     [rbp+4Fh+var_90], 0
0x140125d9f  mov     rcx, [rbp+4Fh+arg_18]
0x140125da3  mov     rax, [rcx]
0x140125da6  lea     r8, [rbp+4Fh+var_90]
0x140125daa  lea     rdx, [rbp+4Fh+var_80]
0x140125dae  mov     rax, [rax+30h]
0x140125db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140125db7  mov     esi, eax
0x140125db9  test    eax, eax
0x140125dbb  jns     short loc_140125E2B
0x140125dbd  cmp     eax, 80042444h
0x140125dc2  jz      short loc_140125DDC
0x140125dc4  lea     r8, aHrVdsEPackOffl; "hr == VDS_E_PACK_OFFLINE"
0x140125dcb  mov     edx, 65Ah; unsigned int
0x140125dd0  lea     rcx, aBaseStorBlbWsb_6; "base\\stor\\blb\\wsbutil\\wsbvdshelperl"...
0x140125dd7  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140125ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x140125de3  cmp     rcx, r15
0x140125de6  jz      short loc_140125E08
0x140125de8  test    [rcx+1Ch], r14b
0x140125dec  jz      short loc_140125E08
0x140125dee  cmp     byte ptr [rcx+19h], 3
0x140125df2  jb      short loc_140125E08
0x140125df4  mov     edx, 51h ; 'Q'
0x140125df9  mov     r9d, esi
0x140125dfc  mov     r8, r12
0x140125dff  mov     rcx, [rcx+10h]
0x140125e03  call    WPP_SF_d
0x140125e08  mov     qword ptr [rdi+38h], 0
0x140125e10  mov     dword ptr [rdi+44h], 0
0x140125e17  mov     [rdi+40h], r14b
0x140125e1b  xor     esi, esi
0x140125e1d  lea     rcx, [rbp+4Fh+var_80]
0x140125e21  call    ??1?$VDS_STRUCTURES_SMART@PEAG@@QEAA@XZ; VDS_STRUCTURES_SMART<ushort *>::~VDS_STRUCTURES_SMART<ushort *>(void)
0x140125e26  jmp     loc_140126792
0x140125e2b  mov     rdx, [rbp+4Fh+var_80]
0x140125e2f  xor     r9d, r9d
0x140125e32  lea     r8d, [r9+66h]
0x140125e36  cmp     r9d, [rbp+4Fh+var_90]
0x140125e3a  jge     loc_140125EC8
0x140125e40  movsxd  rax, r9d
0x140125e43  lea     rcx, [rax+rax*4]
0x140125e47  add     rcx, rcx
0x140125e4a  mov     eax, [rdx+rcx*8+10h]
0x140125e4e  cmp     eax, 6
0x140125e51  ja      short loc_140125E59
0x140125e53  bt      r8d, eax
0x140125e57  jb      short loc_140125E60
0x140125e59  cmp     eax, 7FFFh
0x140125e5e  jnz     short loc_140125E65
0x140125e60  add     r9d, r14d
0x140125e63  jmp     short loc_140125E36
0x140125e65  mov     rcx, cs:WPP_GLOBAL_Control
0x140125e6c  cmp     rcx, r15
0x140125e6f  jz      short loc_140125EBF
0x140125e71  test    [rcx+1Ch], r14b
0x140125e75  jz      short loc_140125E99
0x140125e77  cmp     byte ptr [rcx+19h], 4
0x140125e7b  jb      short loc_140125E99
0x140125e7d  mov     edx, 4Eh ; 'N'
0x140125e82  mov     [rsp+20h], eax
0x140125e86  mov     r8, r12
0x140125e89  mov     rcx, [rcx+10h]
0x140125e8d  call    WPP_SF_dd
0x140125e92  mov     rcx, cs:WPP_GLOBAL_Control
0x140125e99  cmp     rcx, r15
0x140125e9c  jz      short loc_140125EBF
0x140125e9e  test    [rcx+1Ch], r14b
0x140125ea2  jz      short loc_140125EBF
0x140125ea4  cmp     byte ptr [rcx+19h], 4
0x140125ea8  jb      short loc_140125EBF
0x140125eaa  mov     edx, 52h ; 'R'
0x140125eaf  mov     r9d, [rdi+20h]
0x140125eb3  mov     r8, r12
0x140125eb6  mov     rcx, [rcx+10h]
0x140125eba  call    WPP_SF_d
0x140125ebf  lea     rax, [rdi+68h]
0x140125ec3  or      dword ptr [rax], 8
0x140125ec6  jmp     short loc_140125ECC
0x140125ec8  lea     rax, [rdi+68h]
0x140125ecc  mov     rcx, [rbp+4Fh+arg_0]
0x140125ed0  cmp     byte ptr [rcx+50h], 0
0x140125ed4  jz      short loc_140125ED9
0x140125ed6  or      dword ptr [rax], 10h
0x140125ed9  mov     qword ptr [rdi+38h], 0
0x140125ee1  movsxd  rcx, [rbp+4Fh+var_90]
0x140125ee5  shl     rcx, 4; cb
0x140125ee9  call    cs:__imp_CoTaskMemAlloc
0x140125eef  mov     [rdi+48h], rax
0x140125ef3  test    rax, rax
0x140125ef6  jz      loc_1401267B6
0x140125efc  movsxd  r8, [rbp+4Fh+var_90]
0x140125f00  shl     r8, 4; Size
0x140125f04  xor     edx, edx; Val
0x140125f06  mov     rcx, rax; void *
0x140125f09  call    memset_0
0x140125f0e  movsxd  rcx, [rbp+4Fh+var_90]
0x140125f12  shl     rcx, 2; cb
0x140125f16  call    cs:__imp_CoTaskMemAlloc
0x140125f1c  mov     [rdi+50h], rax
0x140125f20  test    rax, rax
0x140125f23  jz      loc_1401267B6
0x140125f29  movsxd  r8, [rbp+4Fh+var_90]
0x140125f2d  shl     r8, 2; Size
0x140125f31  xor     edx, edx; Val
0x140125f33  mov     rcx, rax; void *
0x140125f36  call    memset_0
0x140125f3b  movsxd  rcx, [rbp+4Fh+var_90]
0x140125f3f  shl     rcx, 3; cb
0x140125f43  call    cs:__imp_CoTaskMemAlloc
0x140125f49  mov     [rdi+58h], rax
0x140125f4d  test    rax, rax
0x140125f50  jz      loc_1401267B6
0x140125f56  movsxd  r8, [rbp+4Fh+var_90]
0x140125f5a  shl     r8, 3; Size
0x140125f5e  xor     edx, edx; Val
0x140125f60  mov     rcx, rax; void *
0x140125f63  call    memset_0
0x140125f68  movsxd  rcx, [rbp+4Fh+var_90]
0x140125f6c  shl     rcx, 3; cb
0x140125f70  call    cs:__imp_CoTaskMemAlloc
0x140125f76  mov     [rdi+60h], rax
0x140125f7a  test    rax, rax
0x140125f7d  jz      loc_1401267B6
0x140125f83  mov     bl, r14b
0x140125f86  movsxd  r8, [rbp+4Fh+var_90]
0x140125f8a  shl     r8, 3; Size
0x140125f8e  xor     edx, edx; Val
0x140125f90  mov     rcx, rax; void *
0x140125f93  call    memset_0
0x140125f98  mov     dword ptr [rdi+44h], 0
0x140125f9f  xor     eax, eax
0x140125fa1  mov     [rbp+4Fh+var_68], eax
0x140125fa4  cmp     eax, [rbp+4Fh+var_90]
0x140125fa7  jge     loc_14012653B
0x140125fad  mov     ecx, [rdi+44h]
0x140125fb0  mov     rax, [rdi+58h]
0x140125fb4  mov     rcx, [rax+rcx*8]; pv
0x140125fb8  test    rcx, rcx
0x140125fbb  jz      short loc_140125FD2
0x140125fbd  call    cs:__imp_CoTaskMemFree
0x140125fc3  mov     ecx, [rdi+44h]
0x140125fc6  mov     rax, [rdi+58h]
0x140125fca  mov     qword ptr [rax+rcx*8], 0
0x140125fd2  mov     ecx, [rdi+44h]
0x140125fd5  mov     rax, [rdi+60h]
0x140125fd9  mov     rcx, [rax+rcx*8]; pv
0x140125fdd  test    rcx, rcx
0x140125fe0  jz      short loc_140125FF7
0x140125fe2  call    cs:__imp_CoTaskMemFree
0x140125fe8  mov     ecx, [rdi+44h]
0x140125feb  mov     rax, [rdi+60h]
0x140125fef  mov     qword ptr [rax+rcx*8], 0
0x140125ff7  mov     edx, [rdi+44h]
0x140125ffa  mov     rax, [rdi+50h]
0x140125ffe  mov     dword ptr [rax+rdx*4], 0
0x140126005  mov     edx, [rdi+44h]
0x140126008  add     rdx, rdx
0x14012600b  mov     rax, [rdi+48h]
0x14012600f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140126016  movdqu  xmmword ptr [rax+rdx*8], xmm0
0x14012601b  mov     rax, [rbp+4Fh+pv]
0x14012601f  test    rax, rax
0x140126022  jz      short loc_140126033
0x140126024  mov     rcx, rax; pv
0x140126027  call    cs:__imp_CoTaskMemFree
0x14012602d  xor     eax, eax
0x14012602f  mov     [rbp+4Fh+pv], rax
0x140126033  test    r13, r13
0x140126036  jz      short loc_140126048
0x140126038  mov     rcx, r13; pv
0x14012603b  call    cs:__imp_CoTaskMemFree
0x140126041  xor     r13d, r13d
0x140126044  mov     [rbp+4Fh+var_88], r13
0x140126048  movsxd  rax, [rbp+4Fh+var_68]
0x14012604c  lea     rdx, [rax+rax*4]
0x140126050  shl     rdx, 4
0x140126054  mov     qword ptr [rbp+4Fh+var_60], rdx
0x140126058  mov     rcx, [rbp+4Fh+var_80]
0x14012605c  mov     eax, [rdx+rcx+10h]
0x140126060  cmp     eax, r14d
0x140126063  jz      loc_1401264F5
0x140126069  cmp     eax, 7FFFh
0x14012606e  jz      loc_1401264F5
0x140126074  cmp     eax, 2
0x140126077  jnz     loc_140126391
0x14012607d  mov     rax, [rdx+rcx+28h]
0x140126082  sub     rax, qword ptr cs:GUID_NULL.Data1
0x140126089  jnz     short loc_140126097
0x14012608b  mov     rax, [rdx+rcx+30h]
0x140126090  sub     rax, qword ptr cs:GUID_NULL.Data4
  ... truncated ...
```
