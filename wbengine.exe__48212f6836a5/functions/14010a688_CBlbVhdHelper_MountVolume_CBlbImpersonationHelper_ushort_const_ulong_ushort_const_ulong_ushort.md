# CBlbVhdHelper::MountVolume(CBlbImpersonationHelper *,ushort const *,ulong,ushort const *,ulong,ushort * *)

- ea: `0x14010a688`
- end: `0x14010b0db`
- name: `?MountVolume@CBlbVhdHelper@@SAJPEAVCBlbImpersonationHelper@@PEBGK1KPEAPEAG@Z`
- size: `2643`
- prototype: `__int64 __fastcall(struct CBlbImpersonationHelper *this, PCWSTR, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `28`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002d79c`
- `0x14002e4e0`
- `0x140030644`
- `0x14004a690`
- `0x14005a62c`
- `0x140108698`
- `0x140109db8`

## callees

- `0x140006ca8`
- `0x140006d94`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x14003e280`
- `0x1400507a4`
- `0x1400889f0`
- `0x140088ba4`
- `0x1400f007c`
- `0x1400f046c`
- `0x1400f07dc`
- `0x1400f105c`
- `0x140107f88`
- `0x14010a688`
- `0x14010b9e0`
- `0x14010bc2c`
- `0x14010c394`
- `0x14010c4b8`
- `0x14010cb9c`
- `0x140110d3c`
- `0x1401116c4`
- `0x1401118c0`
- `0x140111bf4`
- `0x1401170b0`
- `0x140124d1c`
- `0x14012780c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14010a845`
- `KERNEL32!EnterCriticalSection` at `0x14010a845`
- `msvcrt!wcsrchr` at `0x14010a791`
- `msvcrt!wcsrchr` at `0x14010a791`
- `ole32!CoTaskMemFree` at `0x14010aff3`
- `ole32!CoTaskMemFree` at `0x14010b00c`
- `ole32!CoTaskMemFree` at `0x14010b026`
- `ole32!CoTaskMemFree` at `0x14010b03b`
- `ole32!CoTaskMemFree` at `0x14010b058`
- `ole32!CoTaskMemFree` at `0x14010b076`
- `ole32!CoTaskMemFree` at `0x14010aff3`
- `ole32!CoTaskMemFree` at `0x14010b00c`
- `ole32!CoTaskMemFree` at `0x14010b026`
- `ole32!CoTaskMemFree` at `0x14010b03b`
- `ole32!CoTaskMemFree` at `0x14010b058`
- `ole32!CoTaskMemFree` at `0x14010b076`

## string_xrefs

- `0x14010a762`: `pwszVolumeDevicePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbVhdHelper::MountVolume(
        struct CBlbImpersonationHelper *this,
        WCHAR *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 **a6)
{
  WCHAR *v10; // rdi
  wchar_t *v11; // rax
  int IsVhdVersionOld; // ebx
  PVOID *v13; // rcx
  int v14; // eax
  PVOID *v15; // rdx
  int v16; // edx
  int v17; // r9d
  CBlbVhd *v18; // r15
  unsigned __int16 *v19; // r13
  int v20; // eax
  int VHD; // eax
  unsigned __int16 *v22; // r13
  int v23; // eax
  unsigned __int16 **v24; // rax
  unsigned int v25; // r13d
  const WCHAR *v26; // rcx
  struct CBlbImpersonationHelper *v27; // rdx
  __int64 v28; // rdx
  int v29; // r12d
  unsigned int v30; // edx
  const WCHAR *v31; // r14
  int v32; // eax
  int v33; // edx
  int v34; // r9d
  int VolumePathOnMountedVhd; // eax
  int v36; // eax
  const unsigned __int16 *v37; // rsi
  char v39; // [rsp+20h] [rbp-A9h]
  unsigned __int16 **v40; // [rsp+30h] [rbp-99h]
  PCWSTR Path; // [rsp+38h] [rbp-91h] BYREF
  unsigned __int16 *v42; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int16 *v43; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 *v44; // [rsp+50h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-71h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v47[2]; // [rsp+68h] [rbp-61h] BYREF
  char v48; // [rsp+78h] [rbp-51h]
  _OWORD v49[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-29h]
  int v51; // [rsp+A8h] [rbp-21h]
  int v52; // [rsp+B0h] [rbp-19h]
  __int64 v53; // [rsp+B8h] [rbp-11h]
  int v54; // [rsp+C0h] [rbp-9h]
  __int64 v55; // [rsp+C8h] [rbp-1h]
  char v56; // [rsp+D0h] [rbp+7h]
  int v57; // [rsp+128h] [rbp+5Fh]
  unsigned __int8 v58; // [rsp+130h] [rbp+67h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
  }
  pv = 0;
  lpFileName = 0;
  v10 = 0;
  Path = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  memset(v49, 0, sizeof(v49));
  v50 = 0;
  v51 = 10;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v52 = 0;
  v58 = 0;
  if ( !a2 || !*a2 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbvhdhelper.cpp", 0x1F0u, "wszVhdFile && *wszVhdFile");
  if ( !a6 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbvhdhelper.cpp", 0x1F1u, "pwszVolumeDevicePath");
  v57 = a3 & 4;
  if ( (a3 & 4) == 0 )
    goto LABEL_68;
  v11 = wcsrchr(a2, 0x5Cu);
  if ( v11 == (wchar_t *)-2LL )
  {
    IsVhdVersionOld = -2147024809;
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_167;
  }
  v40 = 0;
  v14 = CBlbVhdHelper::_CreateTemporaryFileNames(a4, v11 + 1, (unsigned __int16 **)&Path, &v42);
  IsVhdVersionOld = v14;
  if ( v14 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 27;
      v39 = v14;
      v17 = (int)a2;
LABEL_18:
      WPP_SF_Sd((unsigned int)v13[2], v16, (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids, v17, v39);
LABEL_19:
      v10 = (WCHAR *)Path;
LABEL_20:
      v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_21:
      v18 = (CBlbVhd *)v40;
      goto LABEL_44;
    }
LABEL_22:
    v10 = (WCHAR *)Path;
    goto LABEL_21;
  }
  if ( !a4 )
  {
    v47[0] = &CBlbLock::`vftable';
    v47[1] = &CBlbVhdHelper::m_csVhdLock;
    EnterCriticalSection(&CBlbVhdHelper::m_csVhdLock);
    v48 = 1;
    v19 = v42;
    v20 = BlbCheckCreateDirectory(v42, 1u, 0, 0);
    IsVhdVersionOld = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
          (_DWORD)v19,
          v20);
      }
      CBlbLock::ReleaseLock((CBlbLock *)v47);
      CBlbLock::~CBlbLock((CBlbLock *)v47);
      goto LABEL_19;
    }
    if ( v20 == 1 && !CBlbVhdHelper::m_bTempDirCreated )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids, v19);
      }
      IsVhdVersionOld = -2147024713;
      CBlbLock::ReleaseLock((CBlbLock *)v47);
      CBlbLock::~CBlbLock((CBlbLock *)v47);
      v10 = (WCHAR *)Path;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_163;
    }
    CBlbVhdHelper::m_bTempDirCreated = 1;
    CBlbLock::ReleaseLock((CBlbLock *)v47);
    CBlbLock::~CBlbLock((CBlbLock *)v47);
    goto LABEL_38;
  }
  v22 = v42;
  v23 = BlbCheckCreateDirectory(v42, 1u, 0, 0);
  IsVhdVersionOld = v23;
  if ( v23 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v16 = 30;
    v39 = v23;
LABEL_54:
    v17 = (int)v22;
    goto LABEL_18;
  }
  if ( this )
  {
    IsVhdVersionOld = CBlbImpersonationHelper::ImpersonateCaller(this, 0);
    if ( IsVhdVersionOld < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
        goto LABEL_19;
      }
      goto LABEL_22;
    }
  }
  IsVhdVersionOld = BLB_SECURITY_HELPER::ResetTreeSecurity(v22, 0, 0);
  if ( this )
    CBlbImpersonationHelper::Revert(this);
  if ( IsVhdVersionOld < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v16 = 32;
    v39 = IsVhdVersionOld;
    goto LABEL_54;
  }
LABEL_38:
  v10 = (WCHAR *)Path;
  VHD = CBlbVhd::CreateVHD(this, Path, a2, 0, a5);
  IsVhdVersionOld = VHD;
  if ( VHD < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    v15 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
        (_DWORD)v10,
        VHD);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    v18 = 0;
    goto LABEL_44;
  }
LABEL_68:
  v24 = (unsigned __int16 **)operator new(0x10u);
  v40 = v24;
  Path = (PCWSTR)v24;
  if ( v24 )
  {
    *v24 = 0;
    v24[1] = (unsigned __int16 *)-1LL;
    v25 = CBlbVhdHelper::_ConvertBlbVhdMountFlags(a3);
    if ( this )
    {
      IsVhdVersionOld = CBlbImpersonationHelper::ImpersonateCaller(this, 0);
      if ( IsVhdVersionOld < 0 )
        goto LABEL_20;
    }
    v26 = v10;
    if ( !v10 )
      v26 = a2;
    IsVhdVersionOld = CBlbVhd::IsVhdVersionOld(v26, &v58);
    if ( this )
      CBlbImpersonationHelper::Revert(this);
    if ( IsVhdVersionOld < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
      goto LABEL_20;
    }
    if ( v10 )
      a2 = v10;
    v18 = (CBlbVhd *)v40;
    IsVhdVersionOld = CBlbVhd::Initialize(
                        v40,
                        this,
                        a2,
                        (VIRTUAL_DISK_ACCESS_MASK)((v25 & 1) != 0 ? VIRTUAL_DISK_ACCESS_READ : VIRTUAL_DISK_ACCESS_ALL));
    if ( IsVhdVersionOld < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v28 = 36;
      goto LABEL_87;
    }
    IsVhdVersionOld = CBlbVhd::MountVHD((CBlbVhd *)v40, v27, v25, (unsigned __int16 **)&lpFileName);
    if ( IsVhdVersionOld < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v28 = 37;
      goto LABEL_87;
    }
    v29 = a3 & 1;
    if ( v29 || (v30 = 1, v57) )
      v30 = 3;
    v31 = lpFileName;
    v32 = BlbModifyDiskAttributes(lpFileName, v30, 0);
    IsVhdVersionOld = v32;
    if ( v32 >= 0 )
    {
      if ( v29 || !v57 || (v32 = BlbModifyDiskAttributes(v31, 2u, 1u), IsVhdVersionOld = v32, v32 >= 0) )
      {
        VolumePathOnMountedVhd = CBlbVhdHelper::_FindVolumePathOnMountedVhd(v31, v58, &v44, &v43);
        IsVhdVersionOld = VolumePathOnMountedVhd;
        if ( VolumePathOnMountedVhd < 0 )
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          v15 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              40,
              (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
              (_DWORD)v31,
              VolumePathOnMountedVhd);
            v13 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( IsVhdVersionOld != -2139619249 )
            IsVhdVersionOld = -2139619068;
LABEL_44:
          if ( IsVhdVersionOld == -2147024784 || IsVhdVersionOld == -2147024857 )
            IsVhdVersionOld = -2139618972;
          if ( !v18 )
            goto LABEL_158;
          goto LABEL_48;
        }
        v36 = CBlbVdsHelperLibrary::MountVolumes((CBlbVdsHelperLibrary *)v49, &v44, 1u);
        if ( v36 < 0 )
        {
          v15 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              41,
              (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
              (_DWORD)v44,
              v36);
          }
          IsVhdVersionOld = -2139619068;
LABEL_48:
          CBlbVhd::`scalar deleting destructor'(v18, (unsigned int)v15);
          goto LABEL_157;
        }
        v32 = BlbutilRemoveTrailingBackslash(v43, (unsigned __int16 **)&pv);
        IsVhdVersionOld = v32;
        if ( v32 >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids, v31);
          }
          v37 = (const unsigned __int16 *)pv;
          IsVhdVersionOld = CBlbVhdHelper::_CheckVolumeHasSurfaced((unsigned __int16 *)pv, v29 ^ 1u);
          if ( IsVhdVersionOld < 0 )
          {
            v13 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_44;
            }
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids,
              (_DWORD)v37,
              IsVhdVersionOld);
LABEL_88:
            v13 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_44;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids, v37);
          }
          IsVhdVersionOld = CBlbVhdHelper::_AddVhdContext((struct CBlbVhd *)v40, v37, v10, 1);
          if ( IsVhdVersionOld >= 0 )
          {
            IsVhdVersionOld = BlbutilDuplicateString(v37, a6, 0);
            if ( IsVhdVersionOld >= 0 )
              goto LABEL_157;
            v18 = 0;
            v13 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_44;
            }
            v28 = 47;
          }
          else
          {
            v13 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_44;
            }
            v28 = 46;
          }
LABEL_87:
          WPP_SF_d(v13[2], v28, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
          goto LABEL_88;
        }
        v13 = (PVOID *)WPP_GLOBAL_Control;
        v15 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_44;
        }
        v33 = 42;
        v34 = (int)v43;
LABEL_103:
        WPP_SF_Sd((unsigned int)v13[2], v33, (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids, v34, v32);
        goto LABEL_88;
      }
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v33 = 39;
    }
    else
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v33 = 38;
    }
    v34 = (int)v31;
    goto LABEL_103;
  }
  IsVhdVersionOld = -2147024882;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_158;
  }
  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
LABEL_157:
  v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_158:
  if ( pv )
  {
    CoTaskMemFree(pv);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpFileName )
  {
    CoTaskMemFree((LPVOID)lpFileName);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  v19 = v42;
LABEL_163:
  if ( v10 )
  {
    CoTaskMemFree(v10);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v19 )
  {
    CoTaskMemFree(v19);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_167:
  if ( v43 )
  {
    CoTaskMemFree(v43);
    v43 = 0;
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v44 )
  {
    CoTaskMemFree(v44);
    v44 = 0;
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
    WPP_SF_(v13[2], 48, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
  CBlbVdsHelperLibrary::~CBlbVdsHelperLibrary((CBlbVdsHelperLibrary *)v49);
  return (unsigned int)IsVhdVersionOld;
}

```

## disassembly

```asm
0x14010a688  mov     [rsp-8+arg_0], rbx
0x14010a68d  push    rbp
0x14010a68e  push    rsi
0x14010a68f  push    rdi
0x14010a690  push    r12
0x14010a692  push    r13
0x14010a694  push    r14
0x14010a696  push    r15
0x14010a698  lea     rbp, [rsp-17h]
0x14010a69d  sub     rsp, 0E0h
0x14010a6a4  mov     r15, r9
0x14010a6a7  mov     r12d, r8d
0x14010a6aa  mov     r14, rdx
0x14010a6ad  mov     rsi, rcx
0x14010a6b0  lea     rax, WPP_GLOBAL_Control
0x14010a6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a6be  cmp     rcx, rax
0x14010a6c1  jz      short loc_14010A6E4
0x14010a6c3  test    byte ptr [rcx+1Ch], 1
0x14010a6c7  jz      short loc_14010A6E4
0x14010a6c9  cmp     byte ptr [rcx+19h], 4
0x14010a6cd  jb      short loc_14010A6E4
0x14010a6cf  mov     edx, 1Ah
0x14010a6d4  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010a6db  mov     rcx, [rcx+10h]
0x14010a6df  call    WPP_SF_
0x14010a6e4  xor     eax, eax
0x14010a6e6  mov     [rbp+47h+pv], rax
0x14010a6ea  mov     [rbp+47h+lpFileName], rax
0x14010a6ee  mov     edi, eax
0x14010a6f0  mov     [rsp+110h+Path], rax
0x14010a6f5  mov     [rsp+110h+var_D0], rax
0x14010a6fa  xor     r13d, r13d
0x14010a6fd  mov     [rsp+110h+var_C8], r13
0x14010a702  mov     [rbp+47h+var_C0], r13
0x14010a706  xorps   xmm0, xmm0
0x14010a709  movdqa  [rbp+47h+var_90], xmm0
0x14010a70e  xorps   xmm1, xmm1
0x14010a711  movdqa  [rbp+47h+var_80], xmm1
0x14010a716  mov     [rbp+47h+var_70], r13
0x14010a71a  mov     [rbp+47h+var_68], 0Ah
0x14010a721  mov     [rbp+47h+var_58], r13
0x14010a725  mov     [rbp+47h+var_50], r13d
0x14010a729  mov     [rbp+47h+var_48], r13
0x14010a72d  mov     [rbp+47h+var_40], r13b
0x14010a731  mov     [rbp+47h+var_60], r13d
0x14010a735  mov     [rbp+47h+arg_10], r13b
0x14010a739  test    r14, r14
0x14010a73c  jz      short loc_14010A744
0x14010a73e  cmp     [r14], r13w
0x14010a742  jnz     short loc_14010A75C
0x14010a744  lea     r8, aWszvhdfileWszv; "wszVhdFile && *wszVhdFile"
0x14010a74b  mov     edx, 1F0h; unsigned int
0x14010a750  lea     rcx, aBaseStorBlbEng_8; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14010a757  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14010a75c  cmp     [rbp+47h+arg_28], r13
0x14010a760  jnz     short loc_14010A77A
0x14010a762  lea     r8, aPwszvolumedevi; "pwszVolumeDevicePath"
0x14010a769  mov     edx, 1F1h; unsigned int
0x14010a76e  lea     rcx, aBaseStorBlbEng_8; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14010a775  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14010a77a  mov     eax, r12d
0x14010a77d  and     eax, 4
0x14010a780  mov     [rbp+47h+arg_8], eax
0x14010a783  jz      loc_14010AAE8
0x14010a789  mov     edx, 5Ch ; '\'; Ch
0x14010a78e  mov     rcx, r14; Str
0x14010a791  call    cs:__imp_wcsrchr
0x14010a797  lea     rdx, [rax+2]; unsigned __int16 *
0x14010a79b  test    rdx, rdx
0x14010a79e  jnz     short loc_14010A7B1
0x14010a7a0  mov     ebx, 80070057h
0x14010a7a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a7ac  jmp     loc_14010B04B
0x14010a7b1  mov     [rsp+110h+var_E0], r13
0x14010a7b6  lea     r9, [rsp+110h+var_D0]; unsigned __int16 **
0x14010a7bb  lea     r8, [rsp+110h+Path]; unsigned __int16 **
0x14010a7c0  mov     rcx, r15; unsigned __int16 *
0x14010a7c3  call    ?_CreateTemporaryFileNames@CBlbVhdHelper@@CAJPEBG0PEAPEAG1@Z; CBlbVhdHelper::_CreateTemporaryFileNames(ushort const *,ushort const *,ushort * *,ushort * *)
0x14010a7c8  mov     ebx, eax
0x14010a7ca  test    eax, eax
0x14010a7cc  jns     short loc_14010A826
0x14010a7ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a7d5  lea     rdx, WPP_GLOBAL_Control
0x14010a7dc  cmp     rcx, rdx
0x14010a7df  jz      short loc_14010A81F
0x14010a7e1  test    byte ptr [rcx+1Ch], 1
0x14010a7e5  jz      short loc_14010A81F
0x14010a7e7  cmp     byte ptr [rcx+19h], 2
0x14010a7eb  jb      short loc_14010A81F
0x14010a7ed  mov     edx, 1Bh
0x14010a7f2  mov     dword ptr [rsp+110h+var_F0], eax
0x14010a7f6  mov     r9, r14
0x14010a7f9  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010a800  mov     rcx, [rcx+10h]
0x14010a804  call    WPP_SF_Sd
0x14010a809  mov     rdi, [rsp+110h+Path]
0x14010a80e  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a815  mov     r15, [rsp+110h+var_E0]
0x14010a81a  jmp     loc_14010A9AC
0x14010a81f  mov     rdi, [rsp+110h+Path]
0x14010a824  jmp     short loc_14010A815
0x14010a826  test    r15, r15
0x14010a829  jnz     loc_14010A9D7
0x14010a82f  lea     rax, ??_7CBlbLock@@6B@; const CBlbLock::`vftable'
0x14010a836  mov     [rbp+47h+var_A8], rax
0x14010a83a  lea     rcx, ?m_csVhdLock@CBlbVhdHelper@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14010a841  mov     [rbp+47h+var_A0], rcx
0x14010a845  call    cs:__imp_EnterCriticalSection
0x14010a84b  mov     [rbp+47h+var_98], 1
0x14010a84f  xor     r9d, r9d; unsigned __int16 *
0x14010a852  xor     r8d, r8d; unsigned __int8
0x14010a855  mov     dl, 1; unsigned __int8
0x14010a857  mov     r13, [rsp+110h+var_D0]
0x14010a85c  mov     rcx, r13; unsigned __int16 *
0x14010a85f  call    ?BlbCheckCreateDirectory@@YAJPEAGEE0@Z; BlbCheckCreateDirectory(ushort *,uchar,uchar,ushort *)
0x14010a864  mov     ebx, eax
0x14010a866  test    eax, eax
0x14010a868  jns     short loc_14010A8BB
0x14010a86a  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a871  lea     r14, WPP_GLOBAL_Control
0x14010a878  cmp     rcx, r14
0x14010a87b  jz      short loc_14010A8A4
0x14010a87d  test    byte ptr [rcx+1Ch], 1
0x14010a881  jz      short loc_14010A8A4
0x14010a883  cmp     byte ptr [rcx+19h], 2
0x14010a887  jb      short loc_14010A8A4
0x14010a889  lea     edx, [r15+1Ch]
0x14010a88d  mov     dword ptr [rsp+110h+var_F0], eax
0x14010a891  mov     r9, r13
0x14010a894  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010a89b  mov     rcx, [rcx+10h]
0x14010a89f  call    WPP_SF_Sd
0x14010a8a4  lea     rcx, [rbp+47h+var_A8]; this
0x14010a8a8  call    ?ReleaseLock@CBlbLock@@QEAAXXZ; CBlbLock::ReleaseLock(void)
0x14010a8ad  lea     rcx, [rbp+47h+var_A8]; this
0x14010a8b1  call    ??1CBlbLock@@UEAA@XZ; CBlbLock::~CBlbLock(void)
0x14010a8b6  jmp     loc_14010A809
0x14010a8bb  cmp     eax, 1
0x14010a8be  jnz     short loc_14010A925
0x14010a8c0  cmp     cs:?m_bTempDirCreated@CBlbVhdHelper@@0EA, 0; uchar CBlbVhdHelper::m_bTempDirCreated
0x14010a8c7  jnz     short loc_14010A925
0x14010a8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a8d0  lea     rdx, WPP_GLOBAL_Control
0x14010a8d7  cmp     rcx, rdx
0x14010a8da  jz      short loc_14010A8FD
0x14010a8dc  test    [rcx+1Ch], al
0x14010a8df  jz      short loc_14010A8FD
0x14010a8e1  cmp     byte ptr [rcx+19h], 4
0x14010a8e5  jb      short loc_14010A8FD
0x14010a8e7  lea     edx, [rax+1Ch]
0x14010a8ea  mov     r9, r13
0x14010a8ed  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010a8f4  mov     rcx, [rcx+10h]
0x14010a8f8  call    WPP_SF_S
0x14010a8fd  mov     ebx, 800700B7h
0x14010a902  lea     rcx, [rbp+47h+var_A8]; this
0x14010a906  call    ?ReleaseLock@CBlbLock@@QEAAXXZ; CBlbLock::ReleaseLock(void)
0x14010a90b  lea     rcx, [rbp+47h+var_A8]; this
0x14010a90f  call    ??1CBlbLock@@UEAA@XZ; CBlbLock::~CBlbLock(void)
0x14010a914  mov     rdi, [rsp+110h+Path]
0x14010a919  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a920  jmp     loc_14010B01E
0x14010a925  mov     cs:?m_bTempDirCreated@CBlbVhdHelper@@0EA, 1; uchar CBlbVhdHelper::m_bTempDirCreated
0x14010a92c  lea     rcx, [rbp+47h+var_A8]; this
0x14010a930  call    ?ReleaseLock@CBlbLock@@QEAAXXZ; CBlbLock::ReleaseLock(void)
0x14010a935  lea     rcx, [rbp+47h+var_A8]; this
0x14010a939  call    ??1CBlbLock@@UEAA@XZ; CBlbLock::~CBlbLock(void)
0x14010a93e  mov     eax, [rbp+47h+arg_20]
0x14010a941  mov     dword ptr [rsp+110h+var_F0], eax; unsigned int
0x14010a945  xor     r9d, r9d; unsigned __int64
0x14010a948  mov     r8, r14; PCWSTR
0x14010a94b  mov     rdi, [rsp+110h+Path]
0x14010a950  mov     rdx, rdi; Path
0x14010a953  mov     rcx, rsi; this
0x14010a956  call    ?CreateVHD@CBlbVhd@@SAJPEAVCBlbImpersonationHelper@@PEBG1_KK@Z; CBlbVhd::CreateVHD(CBlbImpersonationHelper *,ushort const *,ushort const *,unsigned __int64,ulong)
0x14010a95b  mov     ebx, eax
0x14010a95d  xor     r13d, r13d
0x14010a960  test    eax, eax
0x14010a962  jns     loc_14010AAE8
0x14010a968  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a96f  lea     rdx, WPP_GLOBAL_Control
0x14010a976  cmp     rcx, rdx
0x14010a979  jz      short loc_14010A9A9
0x14010a97b  test    byte ptr [rcx+1Ch], 1
0x14010a97f  jz      short loc_14010A9A9
0x14010a981  cmp     byte ptr [rcx+19h], 2
0x14010a985  jb      short loc_14010A9A9
0x14010a987  lea     edx, [r13+21h]
0x14010a98b  mov     dword ptr [rsp+110h+var_F0], eax
0x14010a98f  mov     r9, rdi
0x14010a992  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010a999  mov     rcx, [rcx+10h]
0x14010a99d  call    WPP_SF_Sd
0x14010a9a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a9a9  mov     r15, r13
0x14010a9ac  cmp     ebx, 80070070h
0x14010a9b2  jz      short loc_14010A9BC
0x14010a9b4  cmp     ebx, 80070027h
0x14010a9ba  jnz     short loc_14010A9C1
0x14010a9bc  mov     ebx, 80780164h
0x14010a9c1  test    r15, r15
0x14010a9c4  jz      loc_14010AFE7
0x14010a9ca  mov     rcx, r15; this
0x14010a9cd  call    ??_GCBlbVhd@@QEAAPEAXI@Z; CBlbVhd::`scalar deleting destructor'(uint)
0x14010a9d2  jmp     loc_14010AFE0
0x14010a9d7  xor     r9d, r9d; unsigned __int16 *
0x14010a9da  xor     r8d, r8d; unsigned __int8
0x14010a9dd  mov     dl, 1; unsigned __int8
0x14010a9df  mov     r13, [rsp+110h+var_D0]
0x14010a9e4  mov     rcx, r13; unsigned __int16 *
0x14010a9e7  call    ?BlbCheckCreateDirectory@@YAJPEAGEE0@Z; BlbCheckCreateDirectory(ushort *,uchar,uchar,ushort *)
0x14010a9ec  mov     ebx, eax
0x14010a9ee  test    eax, eax
0x14010a9f0  jns     short loc_14010AA2E
0x14010a9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a9f9  lea     rdx, WPP_GLOBAL_Control
0x14010aa00  cmp     rcx, rdx
0x14010aa03  jz      loc_14010A81F
0x14010aa09  test    byte ptr [rcx+1Ch], 1
0x14010aa0d  jz      loc_14010A81F
0x14010aa13  cmp     byte ptr [rcx+19h], 2
0x14010aa17  jb      loc_14010A81F
0x14010aa1d  mov     edx, 1Eh
0x14010aa22  mov     dword ptr [rsp+110h+var_F0], eax
0x14010aa26  mov     r9, r13
0x14010aa29  jmp     loc_14010A7F9
0x14010aa2e  test    rsi, rsi
0x14010aa31  jz      short loc_14010AA8B
0x14010aa33  xor     edx, edx; unsigned __int8
0x14010aa35  mov     rcx, rsi; this
0x14010aa38  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x14010aa3d  mov     ebx, eax
0x14010aa3f  test    eax, eax
0x14010aa41  jns     short loc_14010AA8B
0x14010aa43  mov     rcx, cs:WPP_GLOBAL_Control
0x14010aa4a  lea     rdx, WPP_GLOBAL_Control
0x14010aa51  cmp     rcx, rdx
0x14010aa54  jz      loc_14010A81F
0x14010aa5a  test    byte ptr [rcx+1Ch], 1
0x14010aa5e  jz      loc_14010A81F
0x14010aa64  cmp     byte ptr [rcx+19h], 2
0x14010aa68  jb      loc_14010A81F
0x14010aa6e  mov     edx, 1Fh
0x14010aa73  mov     r9d, eax
0x14010aa76  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010aa7d  mov     rcx, [rcx+10h]
0x14010aa81  call    WPP_SF_d
0x14010aa86  jmp     loc_14010A809
0x14010aa8b  xor     r8d, r8d; unsigned __int8
0x14010aa8e  xor     edx, edx; unsigned __int16 *
0x14010aa90  mov     rcx, r13; unsigned __int16 *
0x14010aa93  call    ?ResetTreeSecurity@BLB_SECURITY_HELPER@@SAJPEBG0E@Z; BLB_SECURITY_HELPER::ResetTreeSecurity(ushort const *,ushort const *,uchar)
0x14010aa98  mov     ebx, eax
0x14010aa9a  test    rsi, rsi
0x14010aa9d  jz      short loc_14010AAA7
0x14010aa9f  mov     rcx, rsi; this
0x14010aaa2  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x14010aaa7  test    ebx, ebx
0x14010aaa9  jns     loc_14010A93E
0x14010aaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14010aab6  lea     rdx, WPP_GLOBAL_Control
0x14010aabd  cmp     rcx, rdx
0x14010aac0  jz      loc_14010A81F
0x14010aac6  test    byte ptr [rcx+1Ch], 1
0x14010aaca  jz      loc_14010A81F
0x14010aad0  cmp     byte ptr [rcx+19h], 2
0x14010aad4  jb      loc_14010A81F
0x14010aada  mov     edx, 20h ; ' '
0x14010aadf  mov     dword ptr [rsp+110h+var_F0], ebx
0x14010aae3  jmp     loc_14010AA26
0x14010aae8  mov     ecx, 10h; Size
0x14010aaed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14010aaf2  mov     [rsp+110h+var_E0], rax
0x14010aaf7  mov     [rsp+110h+Path], rax
0x14010aafc  test    rax, rax
0x14010aaff  jz      loc_14010AFA7
0x14010ab05  mov     [rax], r13
0x14010ab08  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x14010ab10  mov     ecx, r12d; unsigned int
0x14010ab13  call    ?_ConvertBlbVhdMountFlags@CBlbVhdHelper@@CAKK@Z; CBlbVhdHelper::_ConvertBlbVhdMountFlags(ulong)
0x14010ab18  mov     r13d, eax
0x14010ab1b  mov     ecx, eax
0x14010ab1d  and     cl, 1
0x14010ab20  neg     cl
0x14010ab22  sbb     r15d, r15d
0x14010ab25  and     r15d, 0FFCE0000h
0x14010ab2c  test    rsi, rsi
0x14010ab2f  jz      short loc_14010AB45
0x14010ab31  xor     edx, edx; unsigned __int8
0x14010ab33  mov     rcx, rsi; this
0x14010ab36  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x14010ab3b  mov     ebx, eax
0x14010ab3d  test    eax, eax
0x14010ab3f  js      loc_14010A80E
0x14010ab45  lea     rdx, [rbp+47h+arg_10]; unsigned __int8 *
0x14010ab49  test    rdi, rdi
0x14010ab4c  mov     rcx, rdi
0x14010ab4f  jnz     short loc_14010AB54
0x14010ab51  mov     rcx, r14; Path
  ... truncated ...
```
