# WmiMsvmVirtualEthernetSwitchSettingData::GetPropertiesSelf(IVmWmiClientContext *,ulong,ushort * *,tagVARIANT *)

- ea: `0x140072ca0`
- end: `0x1400738f8`
- name: `?GetPropertiesSelf@WmiMsvmVirtualEthernetSwitchSettingData@@MEAAXPEAUIVmWmiClientContext@@KPEAPEAGPEAUtagVARIANT@@@Z`
- size: `3160`
- prototype: `void __fastcall(WmiMsvmVirtualEthernetSwitchSettingData *__hidden this, struct IVmWmiClientContext *, unsigned int, unsigned __int16 **, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14001a000`
- `0x140022640`
- `0x140032594`
- `0x140043dc8`
- `0x140051c08`
- `0x140053808`
- `0x140054fc8`
- `0x14005df58`
- `0x140060d88`
- `0x1400634f4`
- `0x140063794`
- `0x140072ca0`
- `0x140073a48`
- `0x140073aa0`
- `0x140073cd0`
- `0x140074270`
- `0x14007b380`
- `0x140081828`
- `0x1400819d4`
- `0x140082388`
- `0x1400826e0`
- `0x140084480`
- `0x140096cdc`
- `0x140097760`
- `0x140099fac`
- `0x1400b17d8`
- `0x1400b189c`
- `0x1400cff7c`
- `0x1401268bc`
- `0x14014aa00`
- `0x14017902c`
- `0x140188e18`
- `0x14023d6f8`
- `0x14028de54`
- `0x140314f60`
- `0x1404828e0`
- `0x14071ecf8`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072d4c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072ddc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072e73`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072f4f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072fad`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140073017`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400730f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140073166`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400731cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140073232`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007329a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007330c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140073366`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007357d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072d4c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072ddc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072e73`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072f4f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140072fad`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140073017`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400730f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140073166`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400731cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140073232`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007329a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007330c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140073366`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007357d`
- `vmsif!VmsIfSwitchPropertyEnumerate` at `0x1400733db`
- `vmsif!VmsIfSwitchPropertyEnumerate` at `0x1400733db`
- `vmsif!VmsIfSwitchPropertyListFree` at `0x140073550`
- `vmsif!VmsIfSwitchPropertyListFree` at `0x140073550`
- `vmsif!VmsIfSwitchExtensionFree` at `0x1400730c7`
- `vmsif!VmsIfSwitchExtensionFree` at `0x1400730c7`
- `vmsif!VmsIfDriverClose` at `0x1400738c3`
- `vmsif!VmsIfDriverClose` at `0x1400738c3`

## string_xrefs

- `0x14007335f`: `RequiredExtensionIds`
- `0x140073010`: `ExtensionOrder`
- `0x140073305`: `BypassExtensionStack`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall WmiMsvmVirtualEthernetSwitchSettingData::GetPropertiesSelf(
        WmiMsvmVirtualEthernetSwitchSettingData *this,
        struct IVmWmiClientContext *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        struct tagVARIANT *a5)
{
  int v9; // ebx
  unsigned int v10; // r13d
  __m128i si128; // xmm6
  __int64 v12; // r14
  int v13; // eax
  int v14; // ebx
  unsigned int v15; // r14d
  __int64 v16; // r13
  int v17; // eax
  SAFEARRAY *v18; // rdx
  int v19; // ebx
  unsigned int v20; // r14d
  __int64 v21; // r15
  int v22; // eax
  VARIANTARG *v23; // rbx
  SAFEARRAY *v24; // rdx
  int v25; // ebx
  unsigned int v26; // r14d
  __int64 v27; // r13
  int v28; // eax
  VARIANTARG *v29; // rcx
  int v30; // ebx
  unsigned int v31; // r14d
  __int64 v32; // r13
  int v33; // eax
  Vml::VmVariant *v34; // rcx
  int v35; // ebx
  unsigned int v36; // r14d
  __int64 v37; // r13
  int v38; // eax
  WmiMsvmVirtualEthernetSwitchSettingData *v39; // rcx
  SAFEARRAY *v40; // rdx
  int v41; // ebx
  unsigned int v42; // r14d
  __int64 v43; // r15
  int v44; // eax
  struct tagVARIANT *v45; // r14
  LONG v46; // ebx
  int v47; // ebx
  unsigned int v48; // r14d
  __int64 v49; // r13
  int v50; // eax
  Vml::VmVariant *v51; // rcx
  int v52; // ebx
  unsigned int v53; // r14d
  __int64 v54; // r13
  int v55; // eax
  Vml::VmVariant *v56; // rcx
  int v57; // ebx
  unsigned int v58; // r14d
  __int64 v59; // r13
  int v60; // eax
  Vml::VmVariant *v61; // rcx
  int v62; // ebx
  unsigned int v63; // r14d
  __int64 v64; // r13
  int v65; // eax
  struct tagVARIANT *v66; // r14
  LONG v67; // ebx
  int v68; // ebx
  unsigned int v69; // r14d
  __int64 v70; // r15
  int v71; // eax
  Vml::VmVariant *v72; // rbx
  int v73; // r14d
  unsigned int v74; // r15d
  __int64 v75; // r13
  int v76; // eax
  VARIANTARG *v77; // r15
  unsigned int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // r14
  unsigned int v81; // r13d
  __int64 v82; // r8
  __int64 v83; // r14
  unsigned int i; // ebx
  SAFEARRAY *v85; // rdx
  int v86; // ebx
  __int64 v87; // r15
  int v88; // eax
  VARIANTARG *v89; // rdi
  int v90; // eax
  int v91; // eax
  WmiMsvmVirtualEthernetSwitchSettingData *v92; // rsi
  int v93; // eax
  __int64 v94; // rax
  __int128 *p_Src; // r8
  struct IVmWmiClientContext *v96; // rbx
  int v97; // eax
  struct IVmWmiClientContext *v98; // rax
  int v99; // [rsp+28h] [rbp-C1h]
  struct IVmWmiClientContext *v100; // [rsp+38h] [rbp-B1h] BYREF
  __int64 v101; // [rsp+40h] [rbp-A9h] BYREF
  SAFEARRAY *psa; // [rsp+48h] [rbp-A1h] BYREF
  SAFEARRAY *v103; // [rsp+50h] [rbp-99h] BYREF
  WmiMsvmVirtualEthernetSwitchSettingData *v104; // [rsp+58h] [rbp-91h] BYREF
  WmiMsvmVirtualEthernetSwitchSettingData *v105; // [rsp+60h] [rbp-89h] BYREF
  __int64 v106; // [rsp+68h] [rbp-81h] BYREF
  LPVOID v107[3]; // [rsp+70h] [rbp-79h] BYREF
  struct _GUID v108; // [rsp+88h] [rbp-61h] BYREF
  __int64 v109; // [rsp+98h] [rbp-51h]
  __int64 v110; // [rsp+A8h] [rbp-41h] BYREF
  __int64 v111; // [rsp+B0h] [rbp-39h] BYREF
  __int64 v112; // [rsp+B8h] [rbp-31h] BYREF
  __int128 Src; // [rsp+C0h] [rbp-29h] BYREF
  __m128i v114; // [rsp+D0h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+57h]

  v100 = a2;
  v104 = this;
  v112 = 0;
  VmsIfHandle::VmsIfHandle((VmsIfHandle *)&v112);
  v105 = (WmiMsvmVirtualEthernetSwitchSettingData *)((char *)this - 24);
  WmiMsvmVirtualEthernetSwitchSettingData::GetInfo((WmiMsvmVirtualEthernetSwitchSettingData *)((char *)this - 24));
  VmWmiCimManagedElement::GetPropertiesSelf(this, a2, a3, a4, a5);
  v9 = 0;
  v10 = a3;
  while ( 1 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v9 == v10 )
      break;
    v12 = v9 + ((v10 - v9) >> 1);
    v13 = _o__wcsicmp(L"InstanceId", a4[v12]);
    if ( !v13 )
    {
      if ( &a5[v12] )
      {
        Src = 0;
        v114 = si128;
        LOWORD(Src) = 0;
        Vml::FormatString(&Src, (wchar_t *)L"Microsoft:%s");
        Vml::VmVariant::Assign(&a5[v12], (OLECHAR *)&Src);
        std::wstring::_Tidy_deallocate(&Src);
      }
      break;
    }
    if ( v13 >= 0 )
      v9 = v12 + 1;
    else
      v10 = v9 + ((v10 - v9) >> 1);
  }
  v14 = 0;
  v15 = a3;
  while ( v14 != v15 )
  {
    v16 = v14 + ((v15 - v14) >> 1);
    v17 = _o__wcsicmp(L"VirtualSystemIdentifier", a4[v16]);
    if ( !v17 )
    {
      if ( &a5[v16] )
      {
        psa = 0;
        Vml::VmBstr::Assign((Vml::VmBstr *)&psa, (const unsigned __int16 *)v104 + 8);
        v18 = psa;
        psa = 0;
        Vml::VmVariant::Attach((Vml::VmVariant *)&a5[v16], &v18->cDims);
        Vml::VmBstr::~VmBstr((Vml::VmBstr *)&psa);
      }
      break;
    }
    if ( v17 >= 0 )
      v14 = v16 + 1;
    else
      v15 = v14 + ((v15 - v14) >> 1);
  }
  v19 = 0;
  v20 = a3;
  while ( v19 != v20 )
  {
    v21 = v19 + ((v20 - v19) >> 1);
    v22 = _o__wcsicmp(L"Notes", a4[v21]);
    if ( !v22 )
    {
      v23 = &a5[v19 + ((v20 - v19) >> 1)];
      if ( v23 )
      {
        v103 = 0;
        Vml::VmSafeArray::VmSafeArray((Vml::VmSafeArray *)&v103, 8u, 0, 1u, 0);
        psa = 0;
        Vml::VmBstr::Assign((Vml::VmBstr *)&psa, (const unsigned __int16 *)v104 + 394);
        Vml::VmSafeArray::PutElement((Vml::VmSafeArray *)&v103, 0, &psa);
        v24 = v103;
        v103 = 0;
        Vml::VmVariant::Attach(v23, v24);
        Vml::VmBstr::~VmBstr((Vml::VmBstr *)&psa);
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v103);
      }
      break;
    }
    if ( v22 >= 0 )
      v19 = v21 + 1;
    else
      v20 = v19 + ((v20 - v19) >> 1);
  }
  v25 = 0;
  v26 = a3;
  while ( v25 != v26 )
  {
    v27 = v25 + ((v26 - v25) >> 1);
    v28 = _o__wcsicmp(L"VirtualSystemType", a4[v27]);
    if ( !v28 )
    {
      v29 = &a5[v27];
      if ( v29 )
        Vml::VmVariant::Assign(v29, (OLECHAR *)L"DMTF:Virtual Ethernet Switch");
      break;
    }
    if ( v28 >= 0 )
      v25 = v27 + 1;
    else
      v26 = v25 + ((v26 - v25) >> 1);
  }
  v30 = 0;
  v31 = a3;
  while ( v30 != v31 )
  {
    v32 = v30 + ((v31 - v30) >> 1);
    v33 = _o__wcsicmp(L"IOVPreferred", a4[v32]);
    if ( !v33 )
    {
      v34 = (Vml::VmVariant *)&a5[v32];
      if ( v34 )
        Vml::VmVariant::Assign(v34, *((_BYTE *)v104 + 3636) != 0);
      break;
    }
    if ( v33 >= 0 )
      v30 = v32 + 1;
    else
      v31 = v30 + ((v31 - v30) >> 1);
  }
  v35 = 0;
  v36 = a3;
  while ( v35 != v36 )
  {
    v37 = v35 + ((v36 - v35) >> 1);
    v38 = _o__wcsicmp(L"ExtensionOrder", a4[v37]);
    if ( !v38 )
    {
      if ( &a5[v37] )
      {
        LODWORD(v103) = 0;
        *(_OWORD *)v107 = 0;
        WmiMsvmVirtualEthernetSwitchSettingData::LoadExtensions(
          v105,
          (unsigned int *)&v103,
          (struct _VMSIF_SWITCH_EXTENSION **)v107);
        psa = 0;
        WmiMsvmVirtualEthernetSwitchSettingData::GetExtensionPaths(
          v39,
          v100,
          (unsigned int)v103,
          (struct _VMSIF_SWITCH_EXTENSION *)v107[0],
          &psa);
        v40 = psa;
        psa = 0;
        Vml::VmVariant::Attach(&a5[v37], v40);
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&psa);
        if ( v107[0] )
          VmsIfSwitchExtensionFree();
      }
      break;
    }
    if ( v38 >= 0 )
      v35 = v37 + 1;
    else
      v36 = v35 + ((v36 - v35) >> 1);
  }
  v41 = 0;
  v42 = a3;
  while ( v41 != v42 )
  {
    v43 = v41 + ((v42 - v41) >> 1);
    v44 = _o__wcsicmp(L"BandwidthReservationMode", a4[v43]);
    if ( !v44 )
    {
      v45 = &a5[v41 + ((v42 - v41) >> 1)];
      if ( v45 )
      {
        v46 = *((_DWORD *)v104 + 910);
        Vml::VmVariant::Clear((Vml::VmVariant *)v45);
        v45->vt = 19;
        v45->lVal = v46;
      }
      break;
    }
    if ( v44 >= 0 )
      v41 = v43 + 1;
    else
      v42 = v41 + ((v42 - v41) >> 1);
  }
  v47 = 0;
  v48 = a3;
  while ( v47 != v48 )
  {
    v49 = v47 + ((v48 - v47) >> 1);
    v50 = _o__wcsicmp(L"PacketDirectEnabled", a4[v49]);
    if ( !v50 )
    {
      v51 = (Vml::VmVariant *)&a5[v49];
      if ( v51 )
        Vml::VmVariant::Assign(v51, *((_BYTE *)v104 + 3644) & 1);
      break;
    }
    if ( v50 >= 0 )
      v47 = v49 + 1;
    else
      v48 = v47 + ((v48 - v47) >> 1);
  }
  v52 = 0;
  v53 = a3;
  while ( v52 != v53 )
  {
    v54 = v52 + ((v53 - v52) >> 1);
    v55 = _o__wcsicmp(L"TeamingEnabled", a4[v54]);
    if ( !v55 )
    {
      v56 = (Vml::VmVariant *)&a5[v54];
      if ( v56 )
        Vml::VmVariant::Assign(v56, (*((_DWORD *)v104 + 911) & 2) != 0);
      break;
    }
    if ( v55 >= 0 )
      v52 = v54 + 1;
    else
      v53 = v52 + ((v53 - v52) >> 1);
  }
  v57 = 0;
  v58 = a3;
  while ( v57 != v58 )
  {
    v59 = v57 + ((v58 - v57) >> 1);
    v60 = _o__wcsicmp(L"AllowNetLbfoTeams", a4[v59]);
    if ( !v60 )
    {
      v61 = (Vml::VmVariant *)&a5[v59];
      if ( v61 )
        Vml::VmVariant::Assign(v61, *((_DWORD *)v104 + 911) & 0x100);
      break;
    }
    if ( v60 >= 0 )
      v57 = v59 + 1;
    else
      v58 = v57 + ((v58 - v57) >> 1);
  }
  v62 = 0;
  v63 = a3;
  while ( v62 != v63 )
  {
    v64 = v62 + ((v63 - v62) >> 1);
    v65 = _o__wcsicmp(L"MaxNumMACAddress", a4[v64]);
    if ( !v65 )
    {
      v66 = &a5[v64];
      if ( v66 )
      {
        v67 = *((_DWORD *)v104 + 837);
        Vml::VmVariant::Clear((Vml::VmVariant *)&a5[v64]);
        v66->vt = 19;
        v66->lVal = v67;
      }
      break;
    }
    if ( v65 >= 0 )
      v62 = v64 + 1;
    else
      v63 = v62 + ((v63 - v62) >> 1);
  }
  v68 = 0;
  v69 = a3;
  while ( v68 != v69 )
  {
    v70 = v68 + ((v69 - v68) >> 1);
    v71 = _o__wcsicmp(L"BypassExtensionStack", a4[v70]);
    if ( !v71 )
    {
      v72 = (Vml::VmVariant *)&a5[v68 + ((v69 - v68) >> 1)];
      goto LABEL_98;
    }
    if ( v71 >= 0 )
      v68 = v70 + 1;
    else
      v69 = v68 + ((v69 - v68) >> 1);
  }
  v72 = 0;
LABEL_98:
  v73 = 0;
  v74 = a3;
  while ( v73 != v74 )
  {
    v75 = v73 + ((v74 - v73) >> 1);
    v105 = (WmiMsvmVirtualEthernetSwitchSettingData *)(unsigned int)v75;
    v76 = _o__wcsicmp(L"RequiredExtensionIds", a4[v75]);
    if ( !v76 )
    {
      v77 = &a5[(_QWORD)v105];
      goto LABEL_106;
    }
    if ( v76 >= 0 )
      v73 = v75 + 1;
    else
      v74 = v73 + ((v74 - v73) >> 1);
  }
  v77 = 0;
LABEL_106:
  if ( v72 || v77 )
  {
    v109 = 0;
    *(_QWORD *)&v108.Data1 = 0;
    *(_QWORD *)v108.Data4 = v112;
    v78 = VmsIfSwitchPropertyEnumerate(v112, (char *)v104 + 16, VMS_SWITCH_POLICY_EXTENSION_SETTINGS_GUID, 256);
    if ( v78 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x170,
        (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualethernetswitchsettingdata.cpp",
        (const char *)v78,
        (unsigned int)&v108);
    v79 = *(_QWORD *)&v108.Data1;
    if ( **(_DWORD **)&v108.Data1 )
    {
      v80 = *(_QWORD *)(*(_QWORD *)&v108.Data1 + 32LL);
      if ( !v80 || *(_DWORD *)(*(_QWORD *)&v108.Data1 + 28LL) < 0xCu )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A0,
          (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualethernetswitchsettingdata.cpp",
          (const char *)0x8007000DLL,
          (int)&v108);
      if ( v72 )
      {
        Vml::VmVariant::Assign(v72, *(_BYTE *)v80 != 0);
        v79 = *(_QWORD *)&v108.Data1;
      }
      if ( !v77 )
        goto LABEL_126;
      if ( *(_DWORD *)(v80 + 8) < 0xCu
        || (v81 = *(_DWORD *)(v80 + 4),
            v82 = *(unsigned int *)(v80 + 8),
            *(unsigned int *)(v79 + 28) < v82 + 16 * (unsigned __int64)v81) )
      {
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x196,
          (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualethernetswitchsettingdata.cpp",
          (const char *)0x8007000DLL,
          (int)&v108);
      }
      v103 = 0;
      v83 = v82 + v80;
      Vml::VmSafeArray::Create((Vml::VmSafeArray *)&v103, 8u, v82, v81, &v108);
      for ( i = 0; i < v81; ++i )
      {
        psa = 0;
        Vml::VmGuid::ToString((const struct _GUID *)(v83 + 16LL * i), (struct Vml::VmBstr *)&psa, 0);
        Vml::VmSafeArray::PutElement((Vml::VmSafeArray *)&v103, i, &psa);
        Vml::VmBstr::~VmBstr((Vml::VmBstr *)&psa);
      }
      v85 = v103;
      v103 = 0;
      Vml::VmVariant::Attach(v77, v85);
      Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v103);
    }
    else
    {
      if ( !v72 )
        goto LABEL_126;
      Vml::VmVariant::Assign(v72, 0);
    }
    v79 = *(_QWORD *)&v108.Data1;
LABEL_126:
    if ( v79 )
      VmsIfSwitchPropertyListFree(*(_QWORD *)v108.Data4);
  }
  v86 = 0;
  while ( v86 != a3 )
  {
    v87 = v86 + ((a3 - v86) >> 1);
    v88 = _o__wcsicmp(L"AssociatedResourcePool", a4[v87]);
    if ( !v88 )
    {
      v89 = &a5[v87];
      if ( v89 )
      {
        LODWORD(v103) = 0;
        psa = 0;
        Vml::VmSafeArray::VmSafeArray((Vml::VmSafeArray *)&psa, 8u, 0, 0, 0);
        v106 = 0;
        v105 = 0;
        v107[0] = 0;
        v111 = 0;
        v90 = (*(__int64 (__fastcall **)(struct IVmWmiClientContext *, __int64 *))(*(_QWORD *)v100 + 48LL))(v100, &v111);
        if ( v90 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1B5,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualethernetswitchsettingdata.cpp",
            (const char *)(unsigned int)v90,
            v99);
        Vml::VmComPtr<IVmResourcePoolManager>::CreateInstance(v107, &CLSID_VmResourcePoolManager);
        v91 = (*(__int64 (__fastcall **)(LPVOID, GUID *, WmiMsvmVirtualEthernetSwitchSettingData **))(*(_QWORD *)v107[0] + 56LL))(
                v107[0],
                &CLSID_VmEthernetConnectionResourcePool,
                &v105);
        if ( v91 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1BA,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualethernetswitchsettingdata.cpp",
            (const char *)(unsigned int)v91,
            v99);
        v92 = v104;
        while ( (*(int (__fastcall **)(WmiMsvmVirtualEthernetSwitchSettingData *, __int64, __int64 *, SAFEARRAY **))(*(_QWORD *)v105 + 24LL))(
                  v105,
                  1,
                  &v106,
                  &v103) >= 0
             && (_DWORD)v103 )
        {
          v104 = 0;
          Vml::VmComPtr<IVmEthernetConnectionResourcePool>::VmComPtr<IVmEthernetConnectionResourcePool>(
            (__int64)&v104,
            &v106);
          if ( v104 )
          {
            if ( !(*(unsigned int (__fastcall **)(WmiMsvmVirtualEthernetSwitchSettingData *, __int64))(*(_QWORD *)v104 + 24LL))(
                    v104,
                    (__int64)v92 + 16) )
            {
              v108 = 0;
              Src = 0;
              v114 = si128;
              LOWORD(Src) = 0;
              v100 = 0;
              v101 = 0;
              v93 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v106 + 24LL))(v106, &v108);
              if ( v93 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1CD,
                  (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualethernetswitchsettingdata.cpp",
                  (const char *)(unsigned int)v93,
                  v99);
              v94 = Vml::VmComMultiInstanceObject<Vml::VmWmiObjectPropertyBag>::CreateInstance<unsigned short const (&)[29]>(L"Msvm_ResourcePool");
              Vml::VmComPtr<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>::Attach<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>(
                &v100,
                v94);
              Vml::VmGuid::ToString(&v108, &Src);
              p_Src = &Src;
              if ( v114.m128i_i64[1] > 7uLL )
                p_Src = (__int128 *)Src;
              Vml::VmBstr::Format((Vml::VmBstr *)&v101, L"Microsoft:%ws", p_Src);
              v96 = v100;
              Vml::VmWmiObjectPropertyBagBase::AddProperty<Vml::VmBstr>((char *)v100 + 24, L"InstanceID", &v101);
              v110 = 0;
              v97 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64 *))(*(_QWORD *)v111 + 32LL))(
                      v111,
                      ((unsigned __int64)v96 + 24) & -(__int64)(v96 != 0),
                      &v110);
              if ( v97 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1D6,
                  (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualethernetswitchsettingdata.cpp",
                  (const char *)(unsigned int)v97,
                  v99);
              Vml::VmSafeArray::PushBack((Vml::VmSafeArray *)&psa, &v110);
              Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v110);
              Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v101);
              Vml::VmComPtr<VmmsClusterVmSwitchConnection>::~VmComPtr<VmmsClusterVmSwitchConnection>(&v100);
              std::wstring::_Tidy_deallocate(&Src);
            }
            v98 = v104;
            v104 = 0;
            v100 = v98;
            Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v100);
          }
          Vml::VmComPtr<IVmmsGuestStateMirroring>::Reset(&v106);
          Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v104);
        }
        if ( Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&psa) )
          Vml::VmVariant::Assign(v89, psa);
        Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v111);
        Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(v107);
        Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v105);
        Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v106);
        Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&psa);
      }
      break;
    }
    if ( v88 >= 0 )
      v86 = v87 + 1;
    else
      a3 = v86 + ((a3 - v86) >> 1);
  }
  if ( v112 )
    VmsIfDriverClose();
}

```

## disassembly

```asm
0x140072ca0  mov     rax, rsp
0x140072ca3  push    rbp
0x140072ca4  push    rbx
0x140072ca5  push    rsi
0x140072ca6  push    rdi
0x140072ca7  push    r12
0x140072ca9  push    r13
0x140072cab  push    r14
0x140072cad  push    r15
0x140072caf  lea     rbp, [rax-57h]
0x140072cb3  sub     rsp, 0F8h
0x140072cba  movaps  xmmword ptr [rax-58h], xmm6
0x140072cbe  mov     rax, cs:__security_cookie
0x140072cc5  xor     rax, rsp
0x140072cc8  mov     qword ptr [rbp+4Fh+var_58], rax
0x140072ccc  mov     r12, r9
0x140072ccf  mov     edi, r8d
0x140072cd2  mov     r14, rdx
0x140072cd5  mov     [rsp+130h+var_100], rdx
0x140072cda  mov     rbx, rcx
0x140072cdd  mov     [rsp+130h+var_E0], rcx
0x140072ce2  mov     rsi, [rbp+4Fh+arg_20]
0x140072ce6  mov     [rbp+4Fh+var_80], 0
0x140072cee  lea     rcx, [rbp+4Fh+var_80]; this
0x140072cf2  call    ??0VmsIfHandle@@QEAA@XZ; VmsIfHandle::VmsIfHandle(void)
0x140072cf7  nop
0x140072cf8  lea     rax, [rbx-18h]
0x140072cfc  mov     [rsp+130h+var_D8], rax
0x140072d01  mov     rcx, rax; this
0x140072d04  call    ?GetInfo@WmiMsvmVirtualEthernetSwitchSettingData@@AEAAXXZ; WmiMsvmVirtualEthernetSwitchSettingData::GetInfo(void)
0x140072d09  mov     [rsp+20h], rsi; struct tagVARIANT *
0x140072d0e  mov     r9, r12; unsigned __int16 **
0x140072d11  mov     r8d, edi; unsigned int
0x140072d14  mov     rdx, r14; struct IVmWmiClientContext *
0x140072d17  mov     rcx, rbx; this
0x140072d1a  call    ?GetPropertiesSelf@VmWmiCimManagedElement@@MEAAXPEAUIVmWmiClientContext@@KPEAPEAGPEAUtagVARIANT@@@Z; VmWmiCimManagedElement::GetPropertiesSelf(IVmWmiClientContext *,ulong,ushort * *,tagVARIANT *)
0x140072d1f  xor     ebx, ebx
0x140072d21  mov     r13d, edi
0x140072d24  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x140072d2c  cmp     ebx, r13d
0x140072d2f  jz      loc_140072DB7
0x140072d35  mov     r14d, r13d
0x140072d38  sub     r14d, ebx
0x140072d3b  shr     r14d, 1
0x140072d3e  add     r14d, ebx
0x140072d41  mov     rdx, [r12+r14*8]
0x140072d45  lea     rcx, aInstanceid; "InstanceId"
0x140072d4c  call    cs:__imp__o__wcsicmp
0x140072d53  nop     dword ptr [rax+rax+00h]
0x140072d58  test    eax, eax
0x140072d5a  jz      short loc_140072D69
0x140072d5c  jns     short loc_140072D63
0x140072d5e  mov     r13d, r14d
0x140072d61  jmp     short loc_140072D24
0x140072d63  lea     ebx, [r14+1]
0x140072d67  jmp     short loc_140072D24
0x140072d69  lea     rax, [r14+r14*2]
0x140072d6d  lea     rbx, [rsi+rax*8]
0x140072d71  test    rbx, rbx
0x140072d74  jz      short loc_140072DB7
0x140072d76  xorps   xmm0, xmm0
0x140072d79  movups  [rbp+4Fh+Src], xmm0
0x140072d7d  movdqu  [rbp+4Fh+var_68], xmm6
0x140072d82  xor     eax, eax
0x140072d84  mov     word ptr [rbp+4Fh+Src], ax
0x140072d88  mov     r8, [rsp+130h+var_E0]
0x140072d8d  add     r8, 10h
0x140072d91  lea     rdx, aMicrosoftS; "Microsoft:%s"
0x140072d98  lea     rcx, [rbp+4Fh+Src]; Src
0x140072d9c  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x140072da1  lea     rdx, [rbp+4Fh+Src]; strIn
0x140072da5  mov     rcx, rbx; pvarg
0x140072da8  call    ?Assign@VmVariant@Vml@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Vml::VmVariant::Assign(std::wstring const &)
0x140072dad  nop
0x140072dae  lea     rcx, [rbp+4Fh+Src]
0x140072db2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140072db7  xor     ebx, ebx
0x140072db9  mov     r14d, edi
0x140072dbc  cmp     ebx, r14d
0x140072dbf  jz      loc_140072E4B
0x140072dc5  mov     r13d, r14d
0x140072dc8  sub     r13d, ebx
0x140072dcb  shr     r13d, 1
0x140072dce  add     r13d, ebx
0x140072dd1  mov     rdx, [r12+r13*8]
0x140072dd5  lea     rcx, aVirtualsystemi; "VirtualSystemIdentifier"
0x140072ddc  call    cs:__imp__o__wcsicmp
0x140072de3  nop     dword ptr [rax+rax+00h]
0x140072de8  test    eax, eax
0x140072dea  jz      short loc_140072DF9
0x140072dec  jns     short loc_140072DF3
0x140072dee  mov     r14d, r13d
0x140072df1  jmp     short loc_140072DBC
0x140072df3  lea     ebx, [r13+1]
0x140072df7  jmp     short loc_140072DBC
0x140072df9  lea     rax, ds:0[r13*2]
0x140072e01  add     rax, r13
0x140072e04  lea     rbx, [rsi+rax*8]
0x140072e08  test    rbx, rbx
0x140072e0b  jz      short loc_140072E4B
0x140072e0d  mov     [rsp+130h+psa], 0
0x140072e16  mov     rdx, [rsp+130h+var_E0]
0x140072e1b  add     rdx, 10h; unsigned __int16 *
0x140072e1f  lea     rcx, [rsp+130h+psa]; this
0x140072e24  call    ?Assign@VmBstr@Vml@@QEAAXPEBG@Z; Vml::VmBstr::Assign(ushort const *)
0x140072e29  nop
0x140072e2a  mov     rdx, [rsp+130h+psa]; unsigned __int16 *
0x140072e2f  mov     [rsp+130h+psa], 0
0x140072e38  mov     rcx, rbx; this
0x140072e3b  call    ?Attach@VmVariant@Vml@@QEAAXPEAG@Z; Vml::VmVariant::Attach(ushort *)
0x140072e40  nop
0x140072e41  lea     rcx, [rsp+130h+psa]; this
0x140072e46  call    ??1VmBstr@Vml@@QEAA@XZ; Vml::VmBstr::~VmBstr(void)
0x140072e4b  xor     ebx, ebx
0x140072e4d  mov     r14d, edi
0x140072e50  cmp     ebx, r14d
0x140072e53  jz      loc_140072F2E
0x140072e59  mov     r15d, r14d
0x140072e5c  sub     r15d, ebx
0x140072e5f  shr     r15d, 1
0x140072e62  add     r15d, ebx
0x140072e65  mov     r13d, r15d
0x140072e68  mov     rdx, [r12+r15*8]
0x140072e6c  lea     rcx, aNotes; "Notes"
0x140072e73  call    cs:__imp__o__wcsicmp
0x140072e7a  nop     dword ptr [rax+rax+00h]
0x140072e7f  test    eax, eax
0x140072e81  jz      short loc_140072E90
0x140072e83  jns     short loc_140072E8A
0x140072e85  mov     r14d, r15d
0x140072e88  jmp     short loc_140072E50
0x140072e8a  lea     ebx, [r15+1]
0x140072e8e  jmp     short loc_140072E50
0x140072e90  lea     rax, ds:0[r15*2]
0x140072e98  add     rax, r13
0x140072e9b  lea     rbx, [rsi+rax*8]
0x140072e9f  test    rbx, rbx
0x140072ea2  jz      loc_140072F2E
0x140072ea8  mov     [rsp+130h+var_E8], 0
0x140072eb1  mov     edx, 8; unsigned __int16
0x140072eb6  mov     qword ptr [rsp+20h], 0; void *
0x140072ebf  lea     r9d, [rdx-7]; unsigned int
0x140072ec3  xor     r8d, r8d; int
0x140072ec6  lea     rcx, [rsp+130h+var_E8]; this
0x140072ecb  call    ??0VmSafeArray@Vml@@QEAA@GJIPEAX@Z; Vml::VmSafeArray::VmSafeArray(ushort,long,uint,void *)
0x140072ed0  nop
0x140072ed1  mov     [rsp+130h+psa], 0
0x140072eda  mov     rdx, [rsp+130h+var_E0]
0x140072edf  add     rdx, 314h; unsigned __int16 *
0x140072ee6  lea     rcx, [rsp+130h+psa]; this
0x140072eeb  call    ?Assign@VmBstr@Vml@@QEAAXPEBG@Z; Vml::VmBstr::Assign(ushort const *)
0x140072ef0  nop
0x140072ef1  lea     r8, [rsp+130h+psa]; void *
0x140072ef6  xor     edx, edx; int
0x140072ef8  lea     rcx, [rsp+130h+var_E8]; this
0x140072efd  call    ?PutElement@VmSafeArray@Vml@@QEAAXJPEBX@Z; Vml::VmSafeArray::PutElement(long,void const *)
0x140072f02  mov     rdx, [rsp+130h+var_E8]; psa
0x140072f07  mov     [rsp+130h+var_E8], 0
0x140072f10  mov     rcx, rbx; pvarg
0x140072f13  call    ?Attach@VmVariant@Vml@@QEAAXPEAUtagSAFEARRAY@@@Z; Vml::VmVariant::Attach(tagSAFEARRAY *)
0x140072f18  nop
0x140072f19  lea     rcx, [rsp+130h+psa]; this
0x140072f1e  call    ??1VmBstr@Vml@@QEAA@XZ; Vml::VmBstr::~VmBstr(void)
0x140072f23  nop
0x140072f24  lea     rcx, [rsp+130h+var_E8]; this
0x140072f29  call    ??1VmSafeArray@Vml@@QEAA@XZ; Vml::VmSafeArray::~VmSafeArray(void)
0x140072f2e  xor     ebx, ebx
0x140072f30  mov     r14d, edi
0x140072f33  cmp     ebx, r14d
0x140072f36  jz      short loc_140072F8C
0x140072f38  mov     r13d, r14d
0x140072f3b  sub     r13d, ebx
0x140072f3e  shr     r13d, 1
0x140072f41  add     r13d, ebx
0x140072f44  mov     rdx, [r12+r13*8]
0x140072f48  lea     rcx, aVirtualsystemt; "VirtualSystemType"
0x140072f4f  call    cs:__imp__o__wcsicmp
0x140072f56  nop     dword ptr [rax+rax+00h]
0x140072f5b  test    eax, eax
0x140072f5d  jz      short loc_140072F6C
0x140072f5f  jns     short loc_140072F66
0x140072f61  mov     r14d, r13d
0x140072f64  jmp     short loc_140072F33
0x140072f66  lea     ebx, [r13+1]
0x140072f6a  jmp     short loc_140072F33
0x140072f6c  lea     rax, ds:0[r13*2]
0x140072f74  add     rax, r13
0x140072f77  lea     rcx, [rsi+rax*8]; pvarg
0x140072f7b  test    rcx, rcx
0x140072f7e  jz      short loc_140072F8C
0x140072f80  lea     rdx, aDmtfVirtualEth; "DMTF:Virtual Ethernet Switch"
0x140072f87  call    ?Assign@VmVariant@Vml@@QEAAXPEBG@Z; Vml::VmVariant::Assign(ushort const *)
0x140072f8c  xor     ebx, ebx
0x140072f8e  mov     r14d, edi
0x140072f91  cmp     ebx, r14d
0x140072f94  jz      short loc_140072FF2
0x140072f96  mov     r13d, r14d
0x140072f99  sub     r13d, ebx
0x140072f9c  shr     r13d, 1
0x140072f9f  add     r13d, ebx
0x140072fa2  mov     rdx, [r12+r13*8]
0x140072fa6  lea     rcx, aIovpreferred; "IOVPreferred"
0x140072fad  call    cs:__imp__o__wcsicmp
0x140072fb4  nop     dword ptr [rax+rax+00h]
0x140072fb9  test    eax, eax
0x140072fbb  jz      short loc_140072FCA
0x140072fbd  jns     short loc_140072FC4
0x140072fbf  mov     r14d, r13d
0x140072fc2  jmp     short loc_140072F91
0x140072fc4  lea     ebx, [r13+1]
0x140072fc8  jmp     short loc_140072F91
0x140072fca  lea     rax, ds:0[r13*2]
0x140072fd2  add     rax, r13
0x140072fd5  lea     rcx, [rsi+rax*8]; this
0x140072fd9  test    rcx, rcx
0x140072fdc  jz      short loc_140072FF2
0x140072fde  mov     rax, [rsp+130h+var_E0]
0x140072fe3  cmp     byte ptr [rax+0E34h], 0
0x140072fea  setnz   dl; bool
0x140072fed  call    ?Assign@VmVariant@Vml@@QEAAX_N@Z; Vml::VmVariant::Assign(bool)
0x140072ff2  xor     ebx, ebx
0x140072ff4  mov     r14d, edi
0x140072ff7  cmp     ebx, r14d
0x140072ffa  jz      loc_1400730D3
0x140073000  mov     r13d, r14d
0x140073003  sub     r13d, ebx
0x140073006  shr     r13d, 1
0x140073009  add     r13d, ebx
0x14007300c  mov     rdx, [r12+r13*8]
0x140073010  lea     rcx, aExtensionorder; "ExtensionOrder"
0x140073017  call    cs:__imp__o__wcsicmp
0x14007301e  nop     dword ptr [rax+rax+00h]
0x140073023  test    eax, eax
0x140073025  jz      short loc_140073034
0x140073027  jns     short loc_14007302E
0x140073029  mov     r14d, r13d
0x14007302c  jmp     short loc_140072FF7
0x14007302e  lea     ebx, [r13+1]
0x140073032  jmp     short loc_140072FF7
0x140073034  lea     rax, ds:0[r13*2]
0x14007303c  add     rax, r13
0x14007303f  lea     rbx, [rsi+rax*8]
0x140073043  test    rbx, rbx
0x140073046  jz      loc_1400730D3
0x14007304c  mov     dword ptr [rsp+130h+var_E8], 0
0x140073054  xorps   xmm0, xmm0
0x140073057  movups  xmmword ptr [rbp+4Fh+var_C8], xmm0
0x14007305b  mov     [rbp+4Fh+var_C8], 0
0x140073063  lea     r8, [rbp+4Fh+var_C8]; struct _VMSIF_SWITCH_EXTENSION **
0x140073067  lea     rdx, [rsp+130h+var_E8]; unsigned int *
0x14007306c  mov     rcx, [rsp+130h+var_D8]; this
0x140073071  call    ?LoadExtensions@WmiMsvmVirtualEthernetSwitchSettingData@@AEAAJPEAKPEAPEAU_VMSIF_SWITCH_EXTENSION@@@Z; WmiMsvmVirtualEthernetSwitchSettingData::LoadExtensions(ulong *,_VMSIF_SWITCH_EXTENSION * *)
0x140073076  mov     [rsp+130h+psa], 0
0x14007307f  lea     rax, [rsp+130h+psa]
0x140073084  mov     [rsp+20h], rax; struct tagSAFEARRAY **
0x140073089  mov     r9, [rbp+4Fh+var_C8]; struct _VMSIF_SWITCH_EXTENSION *
0x14007308d  mov     r8d, dword ptr [rsp+130h+var_E8]; unsigned int
0x140073092  mov     rdx, [rsp+130h+var_100]; struct IVmWmiClientContext *
0x140073097  call    ?GetExtensionPaths@WmiMsvmVirtualEthernetSwitchSettingData@@AEAAXPEAUIVmWmiClientContext@@KPEAU_VMSIF_SWITCH_EXTENSION@@PEAPEAUtagSAFEARRAY@@@Z; WmiMsvmVirtualEthernetSwitchSettingData::GetExtensionPaths(IVmWmiClientContext *,ulong,_VMSIF_SWITCH_EXTENSION *,tagSAFEARRAY * *)
0x14007309c  mov     rdx, [rsp+130h+psa]; psa
0x1400730a1  mov     [rsp+130h+psa], 0
0x1400730aa  mov     rcx, rbx; pvarg
0x1400730ad  call    ?Attach@VmVariant@Vml@@QEAAXPEAUtagSAFEARRAY@@@Z; Vml::VmVariant::Attach(tagSAFEARRAY *)
0x1400730b2  nop
0x1400730b3  lea     rcx, [rsp+130h+psa]; this
0x1400730b8  call    ??1VmSafeArray@Vml@@QEAA@XZ; Vml::VmSafeArray::~VmSafeArray(void)
0x1400730bd  nop
0x1400730be  mov     rcx, [rbp+4Fh+var_C8]
0x1400730c2  test    rcx, rcx
0x1400730c5  jz      short loc_1400730D3
0x1400730c7  call    cs:__imp_VmsIfSwitchExtensionFree
0x1400730ce  nop     dword ptr [rax+rax+00h]
0x1400730d3  xor     ebx, ebx
0x1400730d5  mov     r14d, edi
0x1400730d8  cmp     ebx, r14d
0x1400730db  jz      short loc_140073145
0x1400730dd  mov     r15d, r14d
0x1400730e0  sub     r15d, ebx
0x1400730e3  shr     r15d, 1
0x1400730e6  add     r15d, ebx
0x1400730e9  mov     r13d, r15d
0x1400730ec  mov     rdx, [r12+r15*8]
0x1400730f0  lea     rcx, aBandwidthreser; "BandwidthReservationMode"
0x1400730f7  call    cs:__imp__o__wcsicmp
0x1400730fe  nop     dword ptr [rax+rax+00h]
0x140073103  test    eax, eax
0x140073105  jz      short loc_140073114
0x140073107  jns     short loc_14007310E
0x140073109  mov     r14d, r15d
0x14007310c  jmp     short loc_1400730D8
0x14007310e  lea     ebx, [r15+1]
0x140073112  jmp     short loc_1400730D8
0x140073114  lea     rax, ds:0[r15*2]
0x14007311c  add     rax, r13
0x14007311f  lea     r14, [rsi+rax*8]
0x140073123  test    r14, r14
0x140073126  jz      short loc_140073145
0x140073128  mov     rax, [rsp+130h+var_E0]
0x14007312d  mov     ebx, [rax+0E38h]
0x140073133  mov     rcx, r14; this
  ... truncated ...
```
