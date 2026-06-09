# CDeviceShim::GetCompatFlags(IUnknown *,ushort const *,ulong *)

- ea: `0x14000cbd0`
- end: `0x14000dc46`
- name: `?GetCompatFlags@CDeviceShim@@SAJPEAUIUnknown@@PEBGPEAK@Z`
- size: `4214`
- prototype: `static int(struct IUnknown *, const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `30`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002629c`
- `0x140037954`
- `0x14005c458`
- `0x14005c690`

## callees

- `0x1400065e0`
- `0x140007020`
- `0x140008eac`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000b504`
- `0x14000c920`
- `0x14000c9cc`
- `0x14000cbd0`
- `0x14000e20c`
- `0x14000e848`
- `0x1400105a0`
- `0x140015100`
- `0x14001b620`
- `0x140024688`
- `0x140032eec`
- `0x14003325c`
- `0x14003b91c`
- `0x14003e5f4`
- `0x14003f17c`
- `0x14003f240`
- `0x14003fad8`
- `0x140046d6c`
- `0x140047798`
- `0x14004a79c`
- `0x14004a834`
- `0x140061210`
- `0x14006a278`
- `0x14006a6c0`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14000cd18`
- `KERNEL32!CompareStringW` at `0x14000cd3f`
- `KERNEL32!CompareStringW` at `0x14000cd68`
- `KERNEL32!CompareStringW` at `0x14000cdcd`
- `KERNEL32!CompareStringW` at `0x14000cdf6`
- `KERNEL32!CompareStringW` at `0x14000ce5e`
- `KERNEL32!CompareStringW` at `0x14000ce8b`
- `KERNEL32!CompareStringW` at `0x14000ceb8`
- `KERNEL32!CompareStringW` at `0x14000cee5`
- `KERNEL32!CompareStringW` at `0x14000cf12`
- `KERNEL32!CompareStringW` at `0x14000cf3b`
- `KERNEL32!CompareStringW` at `0x14000cf64`
- `KERNEL32!CompareStringW` at `0x14000cf8d`
- `KERNEL32!CompareStringW` at `0x14000cff5`
- `KERNEL32!CompareStringW` at `0x14000d01e`
- `KERNEL32!CompareStringW` at `0x14000d07c`
- `KERNEL32!CompareStringW` at `0x14000d0a5`
- `KERNEL32!CompareStringW` at `0x14000d103`
- `KERNEL32!CompareStringW` at `0x14000d12c`
- `KERNEL32!CompareStringW` at `0x14000d18a`
- `KERNEL32!CompareStringW` at `0x14000d1b7`
- `KERNEL32!CompareStringW` at `0x14000d1e0`
- `KERNEL32!CompareStringW` at `0x14000d2fa`
- `KERNEL32!CompareStringW` at `0x14000d35b`
- `KERNEL32!CompareStringW` at `0x14000dac6`
- `KERNEL32!CompareStringW` at `0x14000daee`
- `KERNEL32!CompareStringW` at `0x14000cd18`
- `KERNEL32!CompareStringW` at `0x14000cd3f`
- `KERNEL32!CompareStringW` at `0x14000cd68`
- `KERNEL32!CompareStringW` at `0x14000cdcd`
- `KERNEL32!CompareStringW` at `0x14000cdf6`
- `KERNEL32!CompareStringW` at `0x14000ce5e`
- `KERNEL32!CompareStringW` at `0x14000ce8b`
- `KERNEL32!CompareStringW` at `0x14000ceb8`
- `KERNEL32!CompareStringW` at `0x14000cee5`
- `KERNEL32!CompareStringW` at `0x14000cf12`
- `KERNEL32!CompareStringW` at `0x14000cf3b`
- `KERNEL32!CompareStringW` at `0x14000cf64`
- `KERNEL32!CompareStringW` at `0x14000cf8d`
- `KERNEL32!CompareStringW` at `0x14000cff5`
- `KERNEL32!CompareStringW` at `0x14000d01e`
- `KERNEL32!CompareStringW` at `0x14000d07c`
- `KERNEL32!CompareStringW` at `0x14000d0a5`
- `KERNEL32!CompareStringW` at `0x14000d103`
- `KERNEL32!CompareStringW` at `0x14000d12c`
- `KERNEL32!CompareStringW` at `0x14000d18a`
- `KERNEL32!CompareStringW` at `0x14000d1b7`
- `KERNEL32!CompareStringW` at `0x14000d1e0`
- `KERNEL32!CompareStringW` at `0x14000d2fa`
- `KERNEL32!CompareStringW` at `0x14000d35b`
- `KERNEL32!CompareStringW` at `0x14000dac6`
- `KERNEL32!CompareStringW` at `0x14000daee`
- `OLEAUT32!__imp_SysFreeString` at `0x14000da09`
- `OLEAUT32!__imp_SysFreeString` at `0x14000da09`

## string_xrefs

- `0x14000d413`: `CompatFlags`
- `0x14000d456`: `CompatFlags`
- `0x14000d062`: `Linksys`
- `0x14000d170`: `D-Link Systems, Inc`
- `0x14000d7c1`: `DeviceCompatFlags`
- `0x14000d802`: `DeviceCompatFlags`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDeviceShim::GetCompatFlags(struct IUnknown *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  int DeviceInfo; // r12d
  int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rax
  PCNZWCH v12; // rbx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int DeviceProperty; // eax
  int v16; // r8d
  _DWORD *v17; // rdi
  unsigned int v18; // ebx
  int v19; // ebx
  PCNZWCH v20; // rbx
  int v21; // r14d
  PVOID *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // r8d
  PCNZWCH *v27; // rcx
  PVOID *v28; // r10
  PCNZWCH lpString1; // [rsp+30h] [rbp-69h] BYREF
  PCNZWCH v31; // [rsp+38h] [rbp-61h] BYREF
  PCNZWCH v32; // [rsp+40h] [rbp-59h] BYREF
  void *Buf1; // [rsp+48h] [rbp-51h] BYREF
  wchar_t *Buffer; // [rsp+50h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-41h] BYREF
  HKEY v36; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v37[2]; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v38[3]; // [rsp+78h] [rbp-21h] BYREF
  HKEY hKey[12]; // [rsp+90h] [rbp-9h] BYREF
  PCNZWCH lpSubKey; // [rsp+118h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qSq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)&WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids,
      (_DWORD)a1,
      (__int64)a2,
      (char)a3);
  }
  lpString1 = (PCNZWCH)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v32 = (PCNZWCH)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v31 = (PCNZWCH)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Buf1 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  *a3 = 0;
  if ( *((_DWORD *)g_WMCService + 34) )
    *a3 = 8;
  DeviceInfo = CDeviceShim::GetDeviceInfo(
                 (_DWORD)a1,
                 (_DWORD)a2,
                 (unsigned int)&lpString1,
                 (unsigned int)&v32,
                 (__int64)&v31,
                 (__int64)&Buf1);
  v7 = 1;
  if ( DeviceInfo < 0 )
    goto LABEL_90;
  if ( (CompareStringW(0x7Fu, 1u, lpString1, -1, L"Microsoft", -1) == 2
     || CompareStringW(0x7Fu, 1u, lpString1, -1, L"Microsoft Corporation", -1) == 2)
    && CompareStringW(0x7Fu, 1u, v32, -1, L"Windows Media Player", -1) == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
    }
    *a3 |= 0x48u;
    goto LABEL_72;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Microsoft Corporation", -1) == 2
    && CompareStringW(0x7Fu, 1u, v32, -1, L"Xbox 360", -1) == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
    }
    *a3 |= 0x1014u;
    goto LABEL_72;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"RCA", -1) == 2
    || CompareStringW(0x7Fu, 1u, v32, -1, L"RM4100", -1) == 2
    || CompareStringW(0x7Fu, 1u, v31, -1, L"RM4100", -1) == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
    }
    *a3 |= 0x16u;
  }
  else
  {
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Roku", -1) == 2
      && (CompareStringW(0x7Fu, 1u, v31, -1, L"M500", -1) == 2
       || CompareStringW(0x7Fu, 1u, v31, -1, L"M1000", -1) == 2
       || CompareStringW(0x7Fu, 1u, v31, -1, L"M2000", -1) == 2
       || CompareStringW(0x7Fu, 1u, v31, -1, L"R1000", -1) == 2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
      }
      *a3 |= 0x94u;
      goto LABEL_72;
    }
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Rockford Corporation", -1) == 2
      && CompareStringW(0x7Fu, 1u, v32, -1, L"DMS1", -1) == 2 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_62;
      }
      v9 = 19;
LABEL_61:
      WPP_SF_(v8[2], v9, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
LABEL_62:
      *a3 |= 4u;
      goto LABEL_72;
    }
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Linksys", -1) == 2
      && CompareStringW(0x7Fu, 1u, v32, -1, L"WML11B", -1) == 2 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_62;
      }
      v9 = 20;
      goto LABEL_61;
    }
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"LG Electronics, Inc.", -1) == 2
      && CompareStringW(0x7Fu, 1u, v32, -1, L"LG LRM-519", -1) == 2 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_62;
      }
      v9 = 21;
      goto LABEL_61;
    }
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"D-Link Systems, Inc", -1) == 2
      && (CompareStringW(0x7Fu, 1u, v31, -1, L"DSM-320", -1) == 2
       || CompareStringW(0x7Fu, 1u, v31, -1, L"DSM-320RD", -1) == 2) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_62;
      }
      v9 = 22;
      goto LABEL_61;
    }
    if ( !*lpString1 && !*v32 && !*v31 )
      *a3 |= 0x40u;
  }
LABEL_72:
  v10 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Find(
          &Buf1,
          L"DLNADOC/",
          0);
  if ( v10 != -1 )
  {
    v11 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
            &Buf1,
            &bstrString,
            (unsigned int)(v10 + 8));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
      v11,
      &lpSubKey,
      L" ");
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&bstrString);
    v12 = lpSubKey;
    if ( CompareStringW(0x7Fu, 1u, lpSubKey, -1, L"1.00", -1) == 2 )
    {
      *a3 &= 0xFFFFFFEA;
      *a3 |= 2u;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_89;
      }
      v14 = 23;
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, v12, -1, L"1.50", -1) != 2 )
      {
        if ( (unsigned __int16)(*v12 - 50) <= 7u )
        {
          *a3 &= 0xFFFFFFE2;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids, v12);
          }
        }
        goto LABEL_89;
      }
      *a3 &= 0xFFFFFFE2;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
LABEL_89:
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
        v7 = 1;
        goto LABEL_90;
      }
      v14 = 24;
    }
    WPP_SF_(v13[2], v14, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
    goto LABEL_89;
  }
LABEL_90:
  CDevicesDB::CDevicesDB((CDevicesDB *)&v36);
  v36 = (HKEY)&CRendererDevicesDB::`vftable';
  LODWORD(lpSubKey) = 0;
  DeviceProperty = CDevicesDB::GetDeviceProperty((CDevicesDB *)&v36, a2, L"CompatFlags", (unsigned int *)&lpSubKey);
  v17 = Buf1;
  if ( DeviceProperty )
  {
    v7 = 0;
    if ( *((int *)Buf1 - 4) < 0 )
      goto LABEL_226;
    v23 = ATL::strstrT<ATL::ChTraitsOS<unsigned short>>(Buf1, L"MS-DeviceCaps/");
    if ( !v23 )
      goto LABEL_226;
    v24 = (v23 - (__int64)v17) >> 1;
    if ( (_DWORD)v24 == -1 )
      goto LABEL_226;
    v25 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
            &Buf1,
            &bstrString,
            (unsigned int)(v24 + 14));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
      v25,
      &Buffer,
      L") ");
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&bstrString);
    if ( swscanf(Buffer, L"%u", &lpSubKey) == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids, *a3);
      }
      *a3 = (unsigned int)lpSubKey;
      v7 = 1;
    }
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&Buffer);
    if ( !v7 )
    {
LABEL_226:
      if ( !(unsigned int)CDevicesDB::GetDeviceProperty(
                            (CDevicesDB *)&v36,
                            a2,
                            L"DeviceCompatFlags",
                            (unsigned int *)&lpSubKey) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v26, *a3, (char)lpSubKey, (__int64)L"DeviceCompatFlags");
        }
        *a3 = (unsigned int)lpSubKey;
        v7 = 1;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v16, *a3, (char)lpSubKey, (__int64)L"CompatFlags");
    }
    *a3 = (unsigned int)lpSubKey;
  }
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v37);
  if ( v7 || DeviceInfo < 0 || !*((_DWORD *)lpString1 - 4) )
    goto LABEL_179;
  memset(hKey, 0, 24);
  v18 = ATL::CRegKey::Open(
          (ATL::CRegKey *)hKey,
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0\\DeviceShims",
          0x20119u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids, v18);
  }
  if ( v18 )
    goto LABEL_178;
  v36 = 0;
  v37[0] = 0;
  v37[1] = 0;
  v19 = ATL::CRegKey::Open((ATL::CRegKey *)&v36, hKey[0], lpString1, 0x20119u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)&WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids,
      (_DWORD)lpString1,
      v19);
  }
  if ( v19 )
    goto LABEL_177;
  memset(v38, 0, sizeof(v38));
  while ( *((_DWORD *)v32 - 4) || *((_DWORD *)v31 - 4) || *(v17 - 4) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpSubKey);
    if ( *((_DWORD *)v32 - 4) )
      ATL::CSimpleStringT<unsigned short,0>::operator=(&lpSubKey, &v32);
    if ( *((_DWORD *)v31 - 4) )
    {
      if ( *((_DWORD *)lpSubKey - 4) )
        ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, L"\\");
      ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, (const void **)&v31);
    }
    if ( *(v17 - 4) )
    {
      if ( *((_DWORD *)lpSubKey - 4) )
        ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, L"\\");
      ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, (const void **)&Buf1);
    }
    v20 = lpSubKey;
    v21 = ATL::CRegKey::Open((ATL::CRegKey *)v38, v36, lpSubKey, 0x20119u);
    v22 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids,
        (_DWORD)v20,
        v21);
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !v21 )
    {
      if ( !(unsigned int)CDeviceShim::GetCompatFlagsValue((struct ATL::CRegKey *)v38, a3) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids, v20);
        }
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
        goto LABEL_176;
      }
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *(v17 - 4) )
    {
      if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 && *((_BYTE *)v22 + 25) >= 5u )
        WPP_SF_S(v22[2], 33, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids, v17);
      ATL::CSimpleStringT<unsigned short,0>::Empty(&Buf1);
      v17 = Buf1;
    }
    else
    {
      if ( *((_DWORD *)v31 - 4) )
      {
        if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 && *((_BYTE *)v22 + 25) >= 5u )
          WPP_SF_S(v22[2], 34, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids, v31);
        v27 = &v31;
      }
      else
      {
        if ( !*((_DWORD *)v32 - 4) )
          goto LABEL_165;
        if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 && *((_BYTE *)v22 + 25) >= 5u )
          WPP_SF_S(v22[2], 35, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids, v32);
        v27 = &v32;
      }
      ATL::CSimpleStringT<unsigned short,0>::Empty(v27);
    }
LABEL_165:
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
  }
  if ( !(unsigned int)CDeviceShim::GetCompatFlagsValue((struct ATL::CRegKey *)&v36, a3)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
  }
LABEL_176:
  ATL::CRegKey::Close((ATL::CRegKey *)v38);
LABEL_177:
  ATL::CRegKey::Close((ATL::CRegKey *)&v36);
LABEL_178:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_179:
  *a3 &= ~0x1000000u;
  if ( a1 )
  {
    LODWORD(lpSubKey) = 0;
    ATL::CComQIPtr<IUPnPRemoteEndpointInfo,&__s_GUID const _GUID_c92eb863_0269_4aff_9c72_75321bba2952>::CComQIPtr<IUPnPRemoteEndpointInfo,&__s_GUID const _GUID_c92eb863_0269_4aff_9c72_75321bba2952>(
      &Buffer,
      a1);
    if ( Buffer )
    {
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"IsRemoteConnection");
      if ( (*(int (__fastcall **)(wchar_t *, BSTR, PCNZWCH *))(*(_QWORD *)Buffer + 24LL))(Buffer, bstrString, &lpSubKey) >= 0
        && (_DWORD)lpSubKey )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
        }
        *a3 = *a3 & 0xFEFFBFBD | 0x1004002;
      }
      SysFreeString(bstrString);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&Buffer);
  }
  if ( (*a3 & 4) != 0 )
  {
    *a3 |= 8u;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
    }
    *a3 &= ~0x40u;
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
      goto LABEL_199;
    }
  }
  else
  {
LABEL_199:
    v28 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(char *)a3 < 0 )
  {
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Microsoft Corporation", -1) == 2
      && CompareStringW(0x7Fu, 1u, v32, -1, L"Xbox 360", -1) == 2
      && *a3 == 4754 )
    {
      *a3 = 13970;
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
        goto LABEL_208;
      }
    }
    else
    {
LABEL_208:
      v28 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( (*a3 & 8) != 0 )
  {
    *a3 |= 2u;
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
      v28 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( (*(_BYTE *)a3 & 3) == 3 )
  {
    *a3 &= ~1u;
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
        v28 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_219;
    }
  }
  else
  {
LABEL_219:
    if ( v28 != &WPP_GLOBAL_Control
      && (*((_BYTE *)v28 + 28) & 1) != 0
      && *((unsigned __int8 *)v28 + 25) >= ((DeviceInfo >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_Dd(v28[2], 43, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids, (unsigned int)DeviceInfo);
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 6));
  ATL::CStringData::Release((ATL::CStringData *)(v31 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v32 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(lpString1 - 12));
  return (unsigned int)DeviceInfo;
}

```

## disassembly

```asm
0x14000cbd0  push    rbp
0x14000cbd2  push    rbx
0x14000cbd3  push    rsi
0x14000cbd4  push    rdi
0x14000cbd5  push    r12
0x14000cbd7  push    r13
0x14000cbd9  push    r14
0x14000cbdb  push    r15
0x14000cbdd  lea     rbp, [rsp-1Fh]
0x14000cbe2  sub     rsp, 0B8h
0x14000cbe9  mov     rsi, r8
0x14000cbec  mov     r14, rdx
0x14000cbef  mov     r15, rcx
0x14000cbf2  lea     rax, WPP_GLOBAL_Control
0x14000cbf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc00  cmp     rcx, rax
0x14000cc03  jz      short loc_14000CC33
0x14000cc05  test    byte ptr [rcx+1Ch], 1
0x14000cc09  jz      short loc_14000CC33
0x14000cc0b  cmp     byte ptr [rcx+19h], 5
0x14000cc0f  jb      short loc_14000CC33
0x14000cc11  mov     edx, 0Eh
0x14000cc16  mov     qword ptr [rsp+0F0h+cchCount2], r8
0x14000cc1b  mov     [rsp+0F0h+lpString2], r14
0x14000cc20  mov     r9, r15
0x14000cc23  lea     r8, WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids
0x14000cc2a  mov     rcx, [rcx+10h]
0x14000cc2e  call    WPP_SF_qSq
0x14000cc33  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000cc3a  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000cc41  mov     rcx, rbx
0x14000cc44  mov     rax, [rax+18h]
0x14000cc48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc4d  add     rax, 18h
0x14000cc51  mov     [rbp+57h+lpString1], rax
0x14000cc55  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000cc5c  mov     rcx, rbx
0x14000cc5f  mov     rax, [rax+18h]
0x14000cc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc68  add     rax, 18h
0x14000cc6c  mov     [rbp+57h+var_B0], rax
0x14000cc70  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000cc77  mov     rcx, rbx
0x14000cc7a  mov     rax, [rax+18h]
0x14000cc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc83  add     rax, 18h
0x14000cc87  mov     [rbp+57h+var_B8], rax
0x14000cc8b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000cc92  mov     rcx, rbx
0x14000cc95  mov     rax, [rax+18h]
0x14000cc99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc9e  add     rax, 18h
0x14000cca2  mov     [rbp+57h+Buf1], rax
0x14000cca6  mov     dword ptr [rsi], 0
0x14000ccac  mov     rax, cs:g_WMCService
0x14000ccb3  cmp     dword ptr [rax+88h], 0
0x14000ccba  jz      short loc_14000CCC2
0x14000ccbc  mov     dword ptr [rsi], 8
0x14000ccc2  lea     rax, [rbp+57h+Buf1]
0x14000ccc6  mov     qword ptr [rsp+0F0h+cchCount2], rax
0x14000cccb  lea     rax, [rbp+57h+var_B8]
0x14000cccf  mov     [rsp+0F0h+lpString2], rax
0x14000ccd4  lea     r9, [rbp+57h+var_B0]
0x14000ccd8  lea     r8, [rbp+57h+lpString1]
0x14000ccdc  mov     rdx, r14
0x14000ccdf  mov     rcx, r15
0x14000cce2  call    ?GetDeviceInfo@CDeviceShim@@CAJPEAUIUnknown@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@222@Z; CDeviceShim::GetDeviceInfo(IUnknown *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14000cce7  mov     r12d, eax
0x14000ccea  or      edi, 0FFFFFFFFh
0x14000cced  lea     r13d, [rdi+3]
0x14000ccf1  lea     ebx, [rdi+2]
0x14000ccf4  test    eax, eax
0x14000ccf6  js      loc_14000D3F4
0x14000ccfc  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cd00  lea     rax, aMicrosoft; "Microsoft"
0x14000cd07  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cd0c  mov     r9d, edi; cchCount1
0x14000cd0f  mov     r8, [rbp+57h+lpString1]; lpString1
0x14000cd13  mov     edx, ebx; dwCmpFlags
0x14000cd15  lea     ecx, [rbx+7Eh]; Locale
0x14000cd18  call    cs:__imp_CompareStringW
0x14000cd1e  cmp     eax, r13d
0x14000cd21  jz      short loc_14000CD4A
0x14000cd23  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cd27  lea     rax, aMicrosoftCorpo; "Microsoft Corporation"
0x14000cd2e  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cd33  mov     r9d, edi; cchCount1
0x14000cd36  mov     r8, [rbp+57h+lpString1]; lpString1
0x14000cd3a  mov     edx, ebx; dwCmpFlags
0x14000cd3c  lea     ecx, [rbx+7Eh]; Locale
0x14000cd3f  call    cs:__imp_CompareStringW
0x14000cd45  cmp     eax, r13d
0x14000cd48  jnz     short loc_14000CDAF
0x14000cd4a  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cd4e  lea     rax, aWindowsMediaPl; "Windows Media Player"
0x14000cd55  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cd5a  mov     r9d, edi; cchCount1
0x14000cd5d  mov     r8, [rbp+57h+var_B0]; lpString1
0x14000cd61  mov     edx, ebx; dwCmpFlags
0x14000cd63  mov     ecx, 7Fh; Locale
0x14000cd68  call    cs:__imp_CompareStringW
0x14000cd6e  cmp     eax, r13d
0x14000cd71  jnz     short loc_14000CDAF
0x14000cd73  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd7a  lea     rax, WPP_GLOBAL_Control
0x14000cd81  cmp     rcx, rax
0x14000cd84  jz      short loc_14000CDA7
0x14000cd86  test    [rcx+1Ch], r13b
0x14000cd8a  jz      short loc_14000CDA7
0x14000cd8c  cmp     byte ptr [rcx+19h], 4
0x14000cd90  jb      short loc_14000CDA7
0x14000cd92  mov     edx, 0Fh
0x14000cd97  lea     r8, WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids
0x14000cd9e  mov     rcx, [rcx+10h]
0x14000cda2  call    WPP_SF_
0x14000cda7  or      dword ptr [rsi], 48h
0x14000cdaa  jmp     loc_14000D290
0x14000cdaf  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cdb3  lea     rax, aMicrosoftCorpo; "Microsoft Corporation"
0x14000cdba  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cdbf  mov     r9d, edi; cchCount1
0x14000cdc2  mov     r8, [rbp+57h+lpString1]; lpString1
0x14000cdc6  mov     edx, ebx; dwCmpFlags
0x14000cdc8  mov     ecx, 7Fh; Locale
0x14000cdcd  call    cs:__imp_CompareStringW
0x14000cdd3  cmp     eax, r13d
0x14000cdd6  jnz     short loc_14000CE40
0x14000cdd8  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cddc  lea     rax, aXbox360; "Xbox 360"
0x14000cde3  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cde8  mov     r9d, edi; cchCount1
0x14000cdeb  mov     r8, [rbp+57h+var_B0]; lpString1
0x14000cdef  mov     edx, ebx; dwCmpFlags
0x14000cdf1  mov     ecx, 7Fh; Locale
0x14000cdf6  call    cs:__imp_CompareStringW
0x14000cdfc  cmp     eax, r13d
0x14000cdff  jnz     short loc_14000CE40
0x14000ce01  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ce08  lea     rax, WPP_GLOBAL_Control
0x14000ce0f  cmp     rcx, rax
0x14000ce12  jz      short loc_14000CE35
0x14000ce14  test    [rcx+1Ch], r13b
0x14000ce18  jz      short loc_14000CE35
0x14000ce1a  cmp     byte ptr [rcx+19h], 4
0x14000ce1e  jb      short loc_14000CE35
0x14000ce20  mov     edx, 10h
0x14000ce25  lea     r8, WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids
0x14000ce2c  mov     rcx, [rcx+10h]
0x14000ce30  call    WPP_SF_
0x14000ce35  or      dword ptr [rsi], 1014h
0x14000ce3b  jmp     loc_14000D290
0x14000ce40  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000ce44  lea     rax, aRca; "RCA"
0x14000ce4b  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000ce50  mov     r9d, edi; cchCount1
0x14000ce53  mov     r8, [rbp+57h+lpString1]; lpString1
0x14000ce57  mov     edx, ebx; dwCmpFlags
0x14000ce59  mov     ecx, 7Fh; Locale
0x14000ce5e  call    cs:__imp_CompareStringW
0x14000ce64  cmp     eax, r13d
0x14000ce67  jz      loc_14000D259
0x14000ce6d  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000ce71  lea     rax, aRm4100; "RM4100"
0x14000ce78  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000ce7d  mov     r9d, edi; cchCount1
0x14000ce80  mov     r8, [rbp+57h+var_B0]; lpString1
0x14000ce84  mov     edx, ebx; dwCmpFlags
0x14000ce86  mov     ecx, 7Fh; Locale
0x14000ce8b  call    cs:__imp_CompareStringW
0x14000ce91  cmp     eax, r13d
0x14000ce94  jz      loc_14000D259
0x14000ce9a  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000ce9e  lea     rax, aRm4100; "RM4100"
0x14000cea5  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000ceaa  mov     r9d, edi; cchCount1
0x14000cead  mov     r8, [rbp+57h+var_B8]; lpString1
0x14000ceb1  mov     edx, ebx; dwCmpFlags
0x14000ceb3  mov     ecx, 7Fh; Locale
0x14000ceb8  call    cs:__imp_CompareStringW
0x14000cebe  cmp     eax, r13d
0x14000cec1  jz      loc_14000D259
0x14000cec7  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cecb  lea     rax, aRoku; "Roku"
0x14000ced2  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000ced7  mov     r9d, edi; cchCount1
0x14000ceda  mov     r8, [rbp+57h+lpString1]; lpString1
0x14000cede  mov     edx, ebx; dwCmpFlags
0x14000cee0  mov     ecx, 7Fh; Locale
0x14000cee5  call    cs:__imp_CompareStringW
0x14000ceeb  cmp     eax, r13d
0x14000ceee  jnz     loc_14000CFD7
0x14000cef4  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cef8  lea     rax, aM500; "M500"
0x14000ceff  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cf04  mov     r9d, edi; cchCount1
0x14000cf07  mov     r8, [rbp+57h+var_B8]; lpString1
0x14000cf0b  mov     edx, ebx; dwCmpFlags
0x14000cf0d  mov     ecx, 7Fh; Locale
0x14000cf12  call    cs:__imp_CompareStringW
0x14000cf18  cmp     eax, r13d
0x14000cf1b  jz      short loc_14000CF98
0x14000cf1d  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cf21  lea     rax, aM1000; "M1000"
0x14000cf28  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cf2d  mov     r9d, edi; cchCount1
0x14000cf30  mov     r8, [rbp+57h+var_B8]; lpString1
0x14000cf34  mov     edx, ebx; dwCmpFlags
0x14000cf36  mov     ecx, 7Fh; Locale
0x14000cf3b  call    cs:__imp_CompareStringW
0x14000cf41  cmp     eax, r13d
0x14000cf44  jz      short loc_14000CF98
0x14000cf46  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cf4a  lea     rax, aM2000; "M2000"
0x14000cf51  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cf56  mov     r9d, edi; cchCount1
0x14000cf59  mov     r8, [rbp+57h+var_B8]; lpString1
0x14000cf5d  mov     edx, ebx; dwCmpFlags
0x14000cf5f  mov     ecx, 7Fh; Locale
0x14000cf64  call    cs:__imp_CompareStringW
0x14000cf6a  cmp     eax, r13d
0x14000cf6d  jz      short loc_14000CF98
0x14000cf6f  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cf73  lea     rax, aR1000; "R1000"
0x14000cf7a  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cf7f  mov     r9d, edi; cchCount1
0x14000cf82  mov     r8, [rbp+57h+var_B8]; lpString1
0x14000cf86  mov     edx, ebx; dwCmpFlags
0x14000cf88  mov     ecx, 7Fh; Locale
0x14000cf8d  call    cs:__imp_CompareStringW
0x14000cf93  cmp     eax, r13d
0x14000cf96  jnz     short loc_14000CFD7
0x14000cf98  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cf9f  lea     rax, WPP_GLOBAL_Control
0x14000cfa6  cmp     rcx, rax
0x14000cfa9  jz      short loc_14000CFCC
0x14000cfab  test    [rcx+1Ch], r13b
0x14000cfaf  jz      short loc_14000CFCC
0x14000cfb1  cmp     byte ptr [rcx+19h], 4
0x14000cfb5  jb      short loc_14000CFCC
0x14000cfb7  mov     edx, 12h
0x14000cfbc  lea     r8, WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids
0x14000cfc3  mov     rcx, [rcx+10h]
0x14000cfc7  call    WPP_SF_
0x14000cfcc  or      dword ptr [rsi], 94h
0x14000cfd2  jmp     loc_14000D290
0x14000cfd7  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000cfdb  lea     rax, aRockfordCorpor; "Rockford Corporation"
0x14000cfe2  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000cfe7  mov     r9d, edi; cchCount1
0x14000cfea  mov     r8, [rbp+57h+lpString1]; lpString1
0x14000cfee  mov     edx, ebx; dwCmpFlags
0x14000cff0  mov     ecx, 7Fh; Locale
0x14000cff5  call    cs:__imp_CompareStringW
0x14000cffb  cmp     eax, r13d
0x14000cffe  jnz     short loc_14000D05E
0x14000d000  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000d004  lea     rax, aDms1; "DMS1"
0x14000d00b  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000d010  mov     r9d, edi; cchCount1
0x14000d013  mov     r8, [rbp+57h+var_B0]; lpString1
0x14000d017  mov     edx, ebx; dwCmpFlags
0x14000d019  mov     ecx, 7Fh; Locale
0x14000d01e  call    cs:__imp_CompareStringW
0x14000d024  cmp     eax, r13d
0x14000d027  jnz     short loc_14000D05E
0x14000d029  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d030  lea     rax, WPP_GLOBAL_Control
0x14000d037  cmp     rcx, rax
0x14000d03a  jz      loc_14000D21F
0x14000d040  test    [rcx+1Ch], r13b
0x14000d044  jz      loc_14000D21F
0x14000d04a  cmp     byte ptr [rcx+19h], 4
0x14000d04e  jb      loc_14000D21F
0x14000d054  mov     edx, 13h
0x14000d059  jmp     loc_14000D20F
0x14000d05e  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000d062  lea     rax, aLinksys; "Linksys"
0x14000d069  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000d06e  mov     r9d, edi; cchCount1
0x14000d071  mov     r8, [rbp+57h+lpString1]; lpString1
0x14000d075  mov     edx, ebx; dwCmpFlags
0x14000d077  mov     ecx, 7Fh; Locale
0x14000d07c  call    cs:__imp_CompareStringW
0x14000d082  cmp     eax, r13d
0x14000d085  jnz     short loc_14000D0E5
0x14000d087  mov     [rsp+0F0h+cchCount2], edi; cchCount2
0x14000d08b  lea     rax, aWml11b; "WML11B"
0x14000d092  mov     [rsp+0F0h+lpString2], rax; lpString2
0x14000d097  mov     r9d, edi; cchCount1
0x14000d09a  mov     r8, [rbp+57h+var_B0]; lpString1
0x14000d09e  mov     edx, ebx; dwCmpFlags
0x14000d0a0  mov     ecx, 7Fh; Locale
0x14000d0a5  call    cs:__imp_CompareStringW
0x14000d0ab  cmp     eax, r13d
0x14000d0ae  jnz     short loc_14000D0E5
0x14000d0b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0b7  lea     rax, WPP_GLOBAL_Control
0x14000d0be  cmp     rcx, rax
0x14000d0c1  jz      loc_14000D21F
0x14000d0c7  test    [rcx+1Ch], r13b
  ... truncated ...
```
