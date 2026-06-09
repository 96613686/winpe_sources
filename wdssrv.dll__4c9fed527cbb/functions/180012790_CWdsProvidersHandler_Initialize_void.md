# CWdsProvidersHandler::Initialize(void)

- ea: `0x180012790`
- end: `0x180013258`
- name: `?Initialize@CWdsProvidersHandler@@QEAAKXZ`
- size: `2760`
- prototype: `__int64 __fastcall(CWdsProvidersHandler *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009da4`

## callees

- `0x18000195c`
- `0x180001984`
- `0x1800023c0`
- `0x180003944`
- `0x180010a00`
- `0x180010b44`
- `0x180012084`
- `0x1800122f4`
- `0x1800123d8`
- `0x1800124ac`
- `0x180012790`
- `0x18001c11e`
- `0x18001c12a`
- `0x18001d010`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x180012850`
- `KERNEL32!InterlockedPushEntrySList` at `0x180012850`
- `KERNEL32!InitializeCriticalSection` at `0x1800130bc`
- `KERNEL32!InitializeCriticalSection` at `0x1800130bc`
- `KERNEL32!LeaveCriticalSection` at `0x18001316f`
- `KERNEL32!LeaveCriticalSection` at `0x18001316f`
- `KERNEL32!EnterCriticalSection` at `0x18001311e`
- `KERNEL32!EnterCriticalSection` at `0x18001311e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800128e6`
- `ADVAPI32!RegOpenKeyExW` at `0x180012ab6`
- `ADVAPI32!RegOpenKeyExW` at `0x180012e72`
- `ADVAPI32!RegOpenKeyExW` at `0x1800128e6`
- `ADVAPI32!RegOpenKeyExW` at `0x180012ab6`
- `ADVAPI32!RegOpenKeyExW` at `0x180012e72`
- `ADVAPI32!RegCloseKey` at `0x1800128b6`
- `ADVAPI32!RegCloseKey` at `0x180012a8e`
- `ADVAPI32!RegCloseKey` at `0x180012d8a`
- `ADVAPI32!RegCloseKey` at `0x180012da4`
- `ADVAPI32!RegCloseKey` at `0x180012e49`
- `ADVAPI32!RegCloseKey` at `0x1800128b6`
- `ADVAPI32!RegCloseKey` at `0x180012a8e`
- `ADVAPI32!RegCloseKey` at `0x180012d8a`
- `ADVAPI32!RegCloseKey` at `0x180012da4`
- `ADVAPI32!RegCloseKey` at `0x180012e49`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012a1d`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012c93`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012cbd`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012cd7`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012d46`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012d63`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800131c1`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800131da`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012a1d`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012c93`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012cbd`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012cd7`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012d46`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180012d63`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800131c1`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800131da`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012aec`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012e03`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012e28`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012e9a`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012aec`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012e03`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012e28`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012e9a`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180012fb8`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180012ff0`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180013029`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180012fb8`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180012ff0`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180013029`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180012a41`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180012a41`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180012f16`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180012f82`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180013247`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180012f16`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180012f82`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180013247`
- `WdsServerCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x180012b6f`
- `WdsServerCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x180012ca8`
- `WdsServerCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x1800131ac`
- `WdsServerCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x180012b6f`
- `WdsServerCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x180012ca8`
- `WdsServerCommonLib!?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z` at `0x1800131ac`
- `WdsServerCommonLib!?EnumKeyFirst@CRegKey@@QEAAKPEAPEAX@Z` at `0x180012924`
- `WdsServerCommonLib!?EnumKeyFirst@CRegKey@@QEAAKPEAPEAX@Z` at `0x180012924`
- `WdsServerCommonLib!?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z` at `0x180012956`
- `WdsServerCommonLib!?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z` at `0x180012bda`
- `WdsServerCommonLib!?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z` at `0x180012956`
- `WdsServerCommonLib!?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z` at `0x180012bda`
- `WdsServerCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x180012b0f`
- `WdsServerCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x180012b0f`
- `WdsServerCommonLib!?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z` at `0x180012b52`
- `WdsServerCommonLib!?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z` at `0x180012b52`
- `WdsServerCommonLib!?GetValueExpSzOrSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180012edd`
- `WdsServerCommonLib!?GetValueExpSzOrSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180012edd`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180012f49`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180012f49`
- `WdsServerCommonLib!?EnumKeyClose@CRegKey@@QEAAKPEAX@Z` at `0x180012d22`
- `WdsServerCommonLib!?EnumKeyClose@CRegKey@@QEAAKPEAX@Z` at `0x180012d22`

## string_xrefs

- `0x1800128d8`: `System\CurrentControlSet\Services\WDSServer\Providers`
- `0x180012ad9`: `[%s] Failed to open registry key for WDS Provider.`
- `0x180012e87`: `[%s] Failed to open registry key for WDS Provider.`
- `0x180012deb`: `[%s] Provider configuration is being processed.`
- `0x180012ed2`: `ProviderDll`

## pseudocode

```c
__int64 __fastcall CWdsProvidersHandler::Initialize(CWdsProvidersHandler *this)
{
  char *v1; // r13
  struct _RTL_CRITICAL_SECTION *v2; // r14
  _DWORD *v3; // rdi
  unsigned int v4; // r15d
  int v5; // esi
  struct _SLIST_ENTRY *v6; // rax
  __int64 v7; // rdx
  struct _SLIST_ENTRY *v8; // rbx
  unsigned __int64 ValueBool; // rbx
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // r15d
  unsigned int v16; // esi
  _DWORD *v17; // rax
  __int64 v18; // rdx
  const WCHAR *v19; // r12
  int v20; // eax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  void *v23; // rax
  void *v24; // r13
  __int64 v25; // rax
  HKEY v26; // rbx
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rdx
  unsigned __int16 ***v30; // r13
  unsigned int *v31; // r12
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  void **v35; // r15
  unsigned int v36; // r13d
  __int64 v37; // rdx
  unsigned int v38; // ecx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rsi
  void **v42; // rdi
  __int64 v43; // rsi
  const WCHAR *v45; // r12
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  struct _RTL_CRITICAL_SECTION *v52; // rax
  struct _RTL_CRITICAL_SECTION *v53; // rsi
  unsigned int v54; // eax
  __int64 v55; // rdx
  unsigned int v56; // eax
  __int64 v57; // rdx
  HKEY phkResult; // [rsp+40h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-71h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int16 *v61; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int16 *v62; // [rsp+60h] [rbp-59h] BYREF
  int v63; // [rsp+68h] [rbp-51h] BYREF
  int v64; // [rsp+6Ch] [rbp-4Dh] BYREF
  int v65; // [rsp+70h] [rbp-49h]
  __int64 v66; // [rsp+78h] [rbp-41h]
  void **v67; // [rsp+80h] [rbp-39h] BYREF
  void *v68; // [rsp+88h] [rbp-31h] BYREF
  void *Src; // [rsp+90h] [rbp-29h] BYREF
  __int64 v70; // [rsp+98h] [rbp-21h]
  __int64 i; // [rsp+A8h] [rbp-11h]
  __int64 v72; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-1h]
  __int64 v74; // [rsp+C8h] [rbp+Fh]
  unsigned int v76; // [rsp+128h] [rbp+6Fh] BYREF
  int v77; // [rsp+130h] [rbp+77h] BYREF
  int v78; // [rsp+138h] [rbp+7Fh]

  v1 = (char *)this + 64;
  hKey = 0;
  v2 = 0;
  phkResult = 0;
  v3 = 0;
  lpSubKey = 0;
  v4 = 0;
  v61 = 0;
  v5 = 0;
  v62 = 0;
  v68 = 0;
  v78 = 0;
  v77 = 0;
  v64 = 0;
  v63 = 0;
  Src = 0;
  v70 = 0;
  v72 = 0;
  v73 = 0;
  v67 = 0;
  v76 = 0;
  v74 = (__int64)this + 64;
  while ( 1 )
  {
    v6 = (struct _SLIST_ENTRY *)operator new(0x890u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v6;
    if ( !v6 )
      break;
    *((_QWORD *)&v6[134].Next + 1) = 0;
    v6[135].Next = 0;
    *((_QWORD *)&v6->Next + 1) = 0;
    v6[1].Next = 0;
    v6->Next = 0;
    *((_QWORD *)&v6[1].Next + 1) = 0;
    LODWORD(v6[2].Next) = 0;
    ProviderRequest::Cleanup((ProviderRequest *)v6);
    InterlockedPushEntrySList((PSLIST_HEADER)v1, v8 + 136);
    _InterlockedIncrement((volatile signed __int32 *)v1 + 4);
    if ( (unsigned int)++v5 >= 0x100 )
    {
      *((_DWORD *)v1 + 9) = 1024;
      goto LABEL_6;
    }
  }
  v4 = 8;
LABEL_6:
  ValueBool = (unsigned int)ElValidateWin32(v4, v7, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 257);
  if ( (unsigned int)ElValidateWin32(ValueBool, v10, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 258) )
    goto LABEL_44;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v11 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\WDSServer\\Providers",
          0,
          0x20119u,
          &hKey);
  ValueBool = (unsigned int)ElValidateWin32(v11, v12, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 265);
  if ( (unsigned int)ElValidateWin32(ValueBool, v13, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 266)
    || (ValueBool = CRegKey::EnumKeyFirst((CRegKey *)&hKey, &v68),
        (unsigned int)ElValidateWin32(ValueBool, v14, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 272)) )
  {
LABEL_44:
    v36 = v76;
    v35 = v67;
  }
  else
  {
    if ( !CRegKey::EnumKeyNext((CRegKey *)&hKey, v68, (unsigned __int16 **)&lpSubKey) )
    {
      v15 = HIDWORD(v70);
      v16 = v70;
      do
      {
        v17 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
        v3 = v17;
        if ( !v17 )
        {
          v3 = 0;
          LODWORD(ValueBool) = 8;
          goto LABEL_44;
        }
        v17[2] = 1;
        LODWORD(ValueBool) = 0;
        *((_QWORD *)v17 + 2) = 0;
        *(_QWORD *)v17 = &CProviderEntry::`vftable';
        v17[6] = 0;
        *((_QWORD *)v17 + 4) = 0;
        v17[10] = 0;
        v19 = lpSubKey;
        if ( v15 == v16 )
        {
          v20 = v16 >> 1;
          if ( v16 >> 1 < 0x20 )
            v20 = 32;
          v21 = v20 + v16;
          if ( (unsigned int)v21 < v16 )
          {
            LODWORD(ValueBool) = WIN32_FROM_HRESULT(-2147024362);
            if ( (_DWORD)ValueBool )
              goto LABEL_25;
          }
          else
          {
            v66 = v20 + v16;
            v22 = 8 * v21;
            if ( !is_mul_ok(v21, 8u) )
              v22 = -1;
            v23 = operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
            v24 = v23;
            if ( !v23 )
            {
              LODWORD(ValueBool) = 8;
              goto LABEL_25;
            }
            memmove_0(v23, Src, 8LL * v16);
            WdsPrivateHpFree(Src);
            v16 = v66;
            Src = v24;
            LODWORD(v70) = v66;
          }
        }
        v25 = v15++;
        HIDWORD(v70) = v15;
        *((_QWORD *)Src + v25) = v19;
LABEL_25:
        if ( (unsigned int)ElValidateWin32(
                             (unsigned int)ValueBool,
                             v18,
                             "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                             281) )
          goto LABEL_44;
        lpSubKey = 0;
        v26 = hKey;
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        v27 = RegOpenKeyExW(v26, v19, 0, 0x20119u, &phkResult);
        if ( (unsigned int)ElValidateWin32(v27, v28, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 288) )
        {
          CTrace::Trace(
            (CTrace *)qword_180039310,
            0x100000u,
            L"[%s] Failed to open registry key for WDS Provider.",
            v19);
        }
        else
        {
          ValueBool = CRegKey::GetValueBool((CRegKey *)&phkResult, L"Disabled", v3 + 6);
          if ( (unsigned int)ElValidateWin32(ValueBool, v29, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 297) )
            goto LABEL_44;
          *((_QWORD *)v3 + 2) = v19;
          v30 = (unsigned __int16 ***)(v3 + 8);
          v31 = v3 + 10;
          LODWORD(ValueBool) = CRegKey::GetValueMultiSz(
                                 (CRegKey *)&phkResult,
                                 L"RequiredProviders",
                                 (unsigned __int16 ***)v3 + 4,
                                 v3 + 10);
          if ( (_DWORD)ValueBool == 2 )
          {
            LODWORD(ValueBool) = 0;
            CRegKey::FreeMultiSz(*v30, *v31);
            *v30 = 0;
            *v31 = 0;
          }
          if ( (unsigned int)ElValidateWin32(
                               (unsigned int)ValueBool,
                               v32,
                               "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                               312) )
            goto LABEL_44;
          ValueBool = (unsigned int)CDynArray<CProviderEntry *,CDeallocateRelease>::AddItem(&v72, v3);
          if ( (unsigned int)ElValidateWin32(ValueBool, v33, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 315) )
            goto LABEL_44;
          v3 = 0;
        }
      }
      while ( !CRegKey::EnumKeyNext((CRegKey *)&hKey, v68, (unsigned __int16 **)&lpSubKey) );
    }
    ValueBool = (unsigned int)ConstructDependencyGraph(&v72, &v67, &v76);
    if ( (unsigned int)ElValidateWin32(ValueBool, v34, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 330) )
      goto LABEL_44;
    v35 = v67;
    v36 = v76;
    ValueBool = (unsigned int)TopologicalSort<CProviderEntry *>(&v72, v67, v76);
    if ( !(unsigned int)ElValidateWin32(ValueBool, v37, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 335) )
    {
      v38 = HIDWORD(v73);
      v39 = 0;
      v65 = 0;
      LODWORD(v66) = HIDWORD(v73);
      if ( HIDWORD(v73) )
      {
        v40 = v72;
        for ( i = v72; ; v40 = i )
        {
          v41 = 0;
          LODWORD(ValueBool) = 0;
          if ( (unsigned int)v39 < v38 )
            v41 = *(_QWORD *)(v40 + 8 * v39);
          else
            LODWORD(ValueBool) = 1413;
          if ( (unsigned int)ElValidateWin32(
                               (unsigned int)ValueBool,
                               v40,
                               "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                               346) )
            break;
          v45 = *(const WCHAR **)(v41 + 16);
          CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[%s] Provider configuration is being processed.", v45);
          if ( *(_DWORD *)(v41 + 24) )
          {
            CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[%s] Provider is disabled.", v45);
          }
          else
          {
            ValueBool = (unsigned __int64)hKey;
            if ( phkResult )
            {
              RegCloseKey(phkResult);
              phkResult = 0;
            }
            LODWORD(ValueBool) = RegOpenKeyExW((HKEY)ValueBool, v45, 0, 0x20119u, &phkResult);
            if ( (_DWORD)ValueBool )
            {
              CTrace::Trace(
                (CTrace *)qword_180039310,
                0x100000u,
                L"[%s] Failed to open registry key for WDS Provider.",
                v45);
              if ( (unsigned int)ElValidateWin32(
                                   (unsigned int)ValueBool,
                                   v46,
                                   "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                                   374) )
                break;
            }
            LODWORD(ValueBool) = CRegKey::GetValueExpSzOrSz((CRegKey *)&phkResult, L"ProviderDll", &v61);
            if ( (_DWORD)ValueBool )
            {
              CEventLog::Log((CEventLog *)qword_180039300, 0xC1010203, 2);
              if ( (unsigned int)ElValidateWin32(
                                   (unsigned int)ValueBool,
                                   v47,
                                   "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                                   387) )
                break;
            }
            LODWORD(ValueBool) = CRegKey::GetValueSz((CRegKey *)&phkResult, L"InitRoutine", &v62);
            if ( (_DWORD)ValueBool )
            {
              CEventLog::Log((CEventLog *)qword_180039300, 0xC1010204, 2);
              if ( (unsigned int)ElValidateWin32(
                                   (unsigned int)ValueBool,
                                   v48,
                                   "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                                   397) )
                break;
            }
            ValueBool = CRegKey::GetValueDwordWithDefault((CRegKey *)&phkResult, L"IsCritical", 0, (unsigned int *)&v77);
            if ( (unsigned int)ElValidateWin32(
                                 ValueBool,
                                 v49,
                                 "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                                 407) )
              break;
            ValueBool = CRegKey::GetValueDwordWithDefault(
                          (CRegKey *)&phkResult,
                          L"TraceDisabled",
                          0,
                          (unsigned int *)&v64);
            if ( (unsigned int)ElValidateWin32(
                                 ValueBool,
                                 v50,
                                 "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                                 416) )
              break;
            ValueBool = CRegKey::GetValueDwordWithDefault(
                          (CRegKey *)&phkResult,
                          L"TraceFlags",
                          0xFFFFFFFF,
                          (unsigned int *)&v63);
            if ( (unsigned int)ElValidateWin32(
                                 ValueBool,
                                 v51,
                                 "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                                 424) )
              break;
            v52 = (struct _RTL_CRITICAL_SECTION *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
            v53 = v52;
            if ( !v52 )
            {
              v2 = 0;
              LODWORD(ValueBool) = 8;
              break;
            }
            v52->LockCount = 1;
            v52[6].SpinCount = 0;
            v52->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWdsProvider::`vftable';
            v52[7].DebugInfo = 0;
            v52->OwningThread = 0;
            v52->LockSemaphore = 0;
            memset_0(&v52[1], 0, 0xA0u);
            LODWORD(v53[6].DebugInfo) = 0;
            LODWORD(v53[6].OwningThread) = 0;
            LODWORD(v53->SpinCount) = 0;
            InitializeCriticalSection(v53 + 5);
            v54 = CWdsProvider::Initialize((CWdsProvider *)v53, v77, v64, v63, v74);
            v56 = ElValidateWin32(v54, v55, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 438);
            LODWORD(ValueBool) = v56;
            if ( v56 )
            {
              v2 = v53;
              if ( v77
                && (unsigned int)ElValidateWin32(v56, v57, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 454) )
              {
                break;
              }
            }
            else
            {
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
              if ( *(_QWORD *)this )
              {
                v53[6].SpinCount = 0;
                v53[7].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)*((_QWORD *)this + 1);
                *(_QWORD *)(*((_QWORD *)this + 1) + 272LL) = v53;
                *((_QWORD *)this + 1) = v53;
              }
              else
              {
                *((_QWORD *)this + 1) = v53;
                *(_QWORD *)this = v53;
                v53[6].SpinCount = 0;
                v53[7].DebugInfo = 0;
              }
              ++*((_DWORD *)this + 14);
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
              ++v78;
              v2 = 0;
            }
            CRegKey::FreeMultiSz(0, 0);
            if ( v61 )
            {
              WdsPrivateHpFree(v61);
              v61 = 0;
            }
            if ( v62 )
            {
              WdsPrivateHpFree(v62);
              v62 = 0;
            }
            if ( v2 )
            {
              ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v2->DebugInfo->CriticalSection)(v2);
              v2 = 0;
            }
          }
          v38 = v66;
          v39 = (unsigned int)(v65 + 1);
          v65 = v39;
          if ( (unsigned int)v39 >= (unsigned int)v66 )
          {
            if ( !v78 )
              goto LABEL_103;
            LODWORD(ValueBool) = 0;
            break;
          }
        }
      }
      else
      {
LABEL_103:
        LODWORD(ValueBool) = -1056898558;
        CEventLog::Log((CEventLog *)qword_180039300, 0xC1010202, 0, 0);
      }
    }
  }
  if ( lpSubKey )
  {
    WdsPrivateHpFree((void *)lpSubKey);
    lpSubKey = 0;
  }
  CRegKey::FreeMultiSz(0, 0);
  if ( v61 )
  {
    WdsPrivateHpFree(v61);
    v61 = 0;
  }
  if ( v62 )
  {
    WdsPrivateHpFree(v62);
    v62 = 0;
  }
  if ( v2 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v2->DebugInfo->ProcessLocksList.Flink)(v2, 1);
  if ( v3 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
  if ( v68 )
    CRegKey::EnumKeyClose((CRegKey *)&hKey, v68);
  if ( v35 )
  {
    if ( v36 )
    {
      v42 = v35;
      v43 = v36;
      do
      {
        if ( *v42 )
        {
          WdsPrivateHpFree(*v42);
          *v42 = 0;
        }
        ++v42;
        --v43;
      }
      while ( v43 );
    }
    WdsPrivateHpFree(v35);
  }
  CDynArray<CProviderEntry *,CDeallocateRelease>::Clear(&v72);
  CDynArray<unsigned short *,CDeallocateString>::~CDynArray<unsigned short *,CDeallocateString>(&Src);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)ValueBool;
}

```

## disassembly

```asm
0x180012790  mov     [rsp-8+arg_0], rcx
0x180012795  push    rbp
0x180012796  push    rbx
0x180012797  push    rsi
0x180012798  push    rdi
0x180012799  push    r12
0x18001279b  push    r13
0x18001279d  push    r14
0x18001279f  push    r15
0x1800127a1  lea     rbp, [rsp-1Fh]
0x1800127a6  sub     rsp, 0D8h
0x1800127ad  xor     r12d, r12d
0x1800127b0  lea     r13, [rcx+40h]
0x1800127b4  mov     [rbp+57h+hKey], r12
0x1800127b8  mov     r14d, r12d
0x1800127bb  mov     [rbp+57h+var_D0], r12
0x1800127bf  mov     edi, r12d
0x1800127c2  mov     [rbp+57h+lpSubKey], r12
0x1800127c6  mov     r15d, r12d
0x1800127c9  mov     [rbp+57h+var_B8], r12
0x1800127cd  mov     esi, r12d
0x1800127d0  mov     [rbp+57h+var_B0], r12
0x1800127d4  mov     [rbp+57h+var_88], r12
0x1800127d8  mov     [rbp+57h+arg_18], r12d
0x1800127dc  mov     [rbp+57h+arg_10], r12d
0x1800127e0  mov     [rbp+57h+var_A4], r12d
0x1800127e4  mov     [rbp+57h+var_A8], r12d
0x1800127e8  mov     [rbp+57h+Src], r12
0x1800127ec  mov     [rbp+57h+var_78], r12
0x1800127f0  mov     [rbp+57h+var_60], r12
0x1800127f4  mov     [rbp+57h+var_58], r12
0x1800127f8  mov     [rbp+57h+var_90], r12
0x1800127fc  mov     [rbp+57h+arg_8], r12d
0x180012800  mov     [rbp+57h+var_48], r13
0x180012804  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001280b  mov     ecx, 890h; unsigned __int64
0x180012810  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012815  mov     rbx, rax
0x180012818  test    rax, rax
0x18001281b  jz      short loc_180012875
0x18001281d  mov     rcx, rax; this
0x180012820  mov     [rax+868h], r12
0x180012827  mov     [rax+870h], r12
0x18001282e  mov     [rax+8], r12
0x180012832  mov     [rax+10h], r12
0x180012836  mov     [rax], r12
0x180012839  mov     [rax+18h], r12
0x18001283d  mov     [rax+20h], r12d
0x180012841  call    ?Cleanup@ProviderRequest@@QEAAXXZ; ProviderRequest::Cleanup(void)
0x180012846  lea     rdx, [rbx+880h]; ListEntry
0x18001284d  mov     rcx, r13; ListHead
0x180012850  call    cs:__imp_InterlockedPushEntrySList
0x180012857  nop     dword ptr [rax+rax+00h]
0x18001285c  lock inc dword ptr [r13+10h]
0x180012861  inc     esi
0x180012863  cmp     esi, 100h
0x180012869  jb      short loc_180012804
0x18001286b  mov     dword ptr [r13+24h], 400h
0x180012873  jmp     short loc_18001287B
0x180012875  mov     r15d, 8
0x18001287b  lea     r13, aBaseEcoWdsWdss_16; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x180012882  mov     r9d, 101h
0x180012888  mov     r8, r13
0x18001288b  mov     ecx, r15d
0x18001288e  call    ElValidateWin32
0x180012893  mov     r9d, 102h
0x180012899  mov     r8, r13
0x18001289c  mov     ecx, eax
0x18001289e  mov     ebx, eax
0x1800128a0  call    ElValidateWin32
0x1800128a5  test    eax, eax
0x1800128a7  jnz     loc_180012C82
0x1800128ad  mov     rcx, [rbp+57h+hKey]; hKey
0x1800128b1  test    rcx, rcx
0x1800128b4  jz      short loc_1800128C6
0x1800128b6  call    cs:__imp_RegCloseKey
0x1800128bd  nop     dword ptr [rax+rax+00h]
0x1800128c2  mov     [rbp+57h+hKey], r12
0x1800128c6  lea     rax, [rbp+57h+hKey]
0x1800128ca  mov     r9d, 20119h; samDesired
0x1800128d0  xor     r8d, r8d; ulOptions
0x1800128d3  mov     [rsp+110h+phkResult], rax; phkResult
0x1800128d8  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WD"...
0x1800128df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800128e6  call    cs:__imp_RegOpenKeyExW
0x1800128ed  nop     dword ptr [rax+rax+00h]
0x1800128f2  mov     r9d, 109h
0x1800128f8  mov     r8, r13
0x1800128fb  mov     ecx, eax
0x1800128fd  call    ElValidateWin32
0x180012902  mov     r9d, 10Ah
0x180012908  mov     r8, r13
0x18001290b  mov     ecx, eax
0x18001290d  mov     ebx, eax
0x18001290f  call    ElValidateWin32
0x180012914  test    eax, eax
0x180012916  jnz     loc_180012C82
0x18001291c  lea     rdx, [rbp+57h+var_88]
0x180012920  lea     rcx, [rbp+57h+hKey]
0x180012924  call    cs:__imp_?EnumKeyFirst@CRegKey@@QEAAKPEAPEAX@Z; CRegKey::EnumKeyFirst(void * *)
0x18001292b  nop     dword ptr [rax+rax+00h]
0x180012930  mov     r9d, 110h
0x180012936  mov     r8, r13
0x180012939  mov     ecx, eax
0x18001293b  mov     ebx, eax
0x18001293d  call    ElValidateWin32
0x180012942  test    eax, eax
0x180012944  jnz     loc_180012C82
0x18001294a  mov     rdx, [rbp+57h+var_88]
0x18001294e  lea     r8, [rbp+57h+lpSubKey]
0x180012952  lea     rcx, [rbp+57h+hKey]
0x180012956  call    cs:__imp_?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z; CRegKey::EnumKeyNext(void *,ushort * *)
0x18001295d  nop     dword ptr [rax+rax+00h]
0x180012962  test    eax, eax
0x180012964  jnz     loc_180012BEE
0x18001296a  mov     r15d, dword ptr [rbp+57h+var_78+4]
0x18001296e  mov     esi, dword ptr [rbp+57h+var_78]
0x180012971  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012978  mov     ecx, 30h ; '0'; unsigned __int64
0x18001297d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012982  mov     rdi, rax
0x180012985  test    rax, rax
0x180012988  jz      loc_180012C7A
0x18001298e  mov     dword ptr [rax+8], 1
0x180012995  xor     ebx, ebx
0x180012997  mov     [rdi+10h], r12
0x18001299b  lea     rax, ??_7CProviderEntry@@6B@; const CProviderEntry::`vftable'
0x1800129a2  mov     [rdi], rax
0x1800129a5  mov     [rdi+18h], r12d
0x1800129a9  mov     [rdi+20h], r12
0x1800129ad  mov     [rdi+28h], r12d
0x1800129b1  mov     r12, [rbp+57h+lpSubKey]
0x1800129b5  cmp     r15d, esi
0x1800129b8  jnz     loc_180012A53
0x1800129be  lea     ecx, [rbx+20h]
0x1800129c1  mov     eax, esi
0x1800129c3  shr     eax, 1
0x1800129c5  cmp     eax, ecx
0x1800129c7  cmovb   eax, ecx
0x1800129ca  lea     ecx, [rax+rsi]
0x1800129cd  cmp     ecx, esi
0x1800129cf  jb      short loc_180012A3C
0x1800129d1  mov     [rbp+57h+var_98], rcx
0x1800129d5  lea     eax, [rbx+8]
0x1800129d8  mul     rcx
0x1800129db  lea     rcx, [rbx-1]
0x1800129df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800129e6  cmovo   rax, rcx
0x1800129ea  mov     rcx, rax; unsigned __int64
0x1800129ed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800129f2  mov     r13, rax
0x1800129f5  test    rax, rax
0x1800129f8  jnz     short loc_180012A06
0x1800129fa  lea     ebx, [rax+8]
0x1800129fd  lea     r13, aBaseEcoWdsWdss_16; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x180012a04  jmp     short loc_180012A65
0x180012a06  mov     rdx, [rbp+57h+Src]; Src
0x180012a0a  mov     rcx, r13; void *
0x180012a0d  mov     r8d, esi
0x180012a10  shl     r8, 3; Size
0x180012a14  call    memmove_0
0x180012a19  mov     rcx, [rbp+57h+Src]
0x180012a1d  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180012a24  nop     dword ptr [rax+rax+00h]
0x180012a29  mov     esi, dword ptr [rbp+57h+var_98]
0x180012a2c  mov     [rbp+57h+Src], r13
0x180012a30  lea     r13, aBaseEcoWdsWdss_16; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x180012a37  mov     dword ptr [rbp+57h+var_78], esi
0x180012a3a  jmp     short loc_180012A53
0x180012a3c  mov     ecx, 80070216h
0x180012a41  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180012a48  nop     dword ptr [rax+rax+00h]
0x180012a4d  mov     ebx, eax
0x180012a4f  test    eax, eax
0x180012a51  jnz     short loc_180012A65
0x180012a53  mov     rcx, [rbp+57h+Src]
0x180012a57  mov     eax, r15d
0x180012a5a  inc     r15d
0x180012a5d  mov     dword ptr [rbp+57h+var_78+4], r15d
0x180012a61  mov     [rcx+rax*8], r12
0x180012a65  mov     r9d, 119h
0x180012a6b  mov     r8, r13
0x180012a6e  mov     ecx, ebx
0x180012a70  call    ElValidateWin32
0x180012a75  test    eax, eax
0x180012a77  jnz     loc_180012C82
0x180012a7d  and     [rbp+57h+lpSubKey], r14
0x180012a81  mov     rcx, [rbp+57h+var_D0]; hKey
0x180012a85  mov     rbx, [rbp+57h+hKey]
0x180012a89  test    rcx, rcx
0x180012a8c  jz      short loc_180012A9E
0x180012a8e  call    cs:__imp_RegCloseKey
0x180012a95  nop     dword ptr [rax+rax+00h]
0x180012a9a  and     [rbp+57h+var_D0], r14
0x180012a9e  lea     rax, [rbp+57h+var_D0]
0x180012aa2  mov     r9d, 20119h; samDesired
0x180012aa8  xor     r8d, r8d; ulOptions
0x180012aab  mov     [rsp+110h+phkResult], rax; phkResult
0x180012ab0  mov     rdx, r12; lpSubKey
0x180012ab3  mov     rcx, rbx; hKey
0x180012ab6  call    cs:__imp_RegOpenKeyExW
0x180012abd  nop     dword ptr [rax+rax+00h]
0x180012ac2  mov     r9d, 120h
0x180012ac8  mov     r8, r13
0x180012acb  mov     ecx, eax
0x180012acd  call    ElValidateWin32
0x180012ad2  test    eax, eax
0x180012ad4  jz      short loc_180012B00
0x180012ad6  mov     r9, r12
0x180012ad9  lea     r8, aSFailedToOpenR; "[%s] Failed to open registry key for WD"...
0x180012ae0  mov     edx, 100000h
0x180012ae5  lea     rcx, qword_180039310
0x180012aec  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180012af3  nop     dword ptr [rax+rax+00h]
0x180012af8  xor     r12d, r12d
0x180012afb  jmp     loc_180012BCE
0x180012b00  lea     r8, [rdi+18h]
0x180012b04  lea     rdx, aDisabled; "Disabled"
0x180012b0b  lea     rcx, [rbp+57h+var_D0]
0x180012b0f  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x180012b16  nop     dword ptr [rax+rax+00h]
0x180012b1b  mov     r9d, 129h
0x180012b21  mov     r8, r13
0x180012b24  mov     ecx, eax
0x180012b26  mov     ebx, eax
0x180012b28  call    ElValidateWin32
0x180012b2d  test    eax, eax
0x180012b2f  jnz     loc_180012C82
0x180012b35  mov     [rdi+10h], r12
0x180012b39  lea     r13, [rdi+20h]
0x180012b3d  lea     r12, [rdi+28h]
0x180012b41  mov     r8, r13
0x180012b44  mov     r9, r12
0x180012b47  lea     rdx, aRequiredprovid; "RequiredProviders"
0x180012b4e  lea     rcx, [rbp+57h+var_D0]
0x180012b52  call    cs:__imp_?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z; CRegKey::GetValueMultiSz(ushort const *,ushort * * *,ulong *)
0x180012b59  nop     dword ptr [rax+rax+00h]
0x180012b5e  mov     ebx, eax
0x180012b60  cmp     eax, 2
0x180012b63  jnz     short loc_180012B83
0x180012b65  mov     edx, [r12]
0x180012b69  xor     ebx, ebx
0x180012b6b  mov     rcx, [r13+0]
0x180012b6f  call    cs:__imp_?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z; CRegKey::FreeMultiSz(ushort * *,ulong)
0x180012b76  nop     dword ptr [rax+rax+00h]
0x180012b7b  and     [r13+0], rbx
0x180012b7f  and     [r12], ebx
0x180012b83  lea     r13, aBaseEcoWdsWdss_16; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x180012b8a  mov     r9d, 138h
0x180012b90  mov     r8, r13
0x180012b93  mov     ecx, ebx
0x180012b95  call    ElValidateWin32
0x180012b9a  xor     r12d, r12d
0x180012b9d  test    eax, eax
0x180012b9f  jnz     loc_180012C82
0x180012ba5  mov     rdx, rdi
0x180012ba8  lea     rcx, [rbp+57h+var_60]
0x180012bac  call    ?AddItem@?$CDynArray@PEAUCProviderEntry@@VCDeallocateRelease@@@@QEAAKPEAUCProviderEntry@@@Z; CDynArray<CProviderEntry *,CDeallocateRelease>::AddItem(CProviderEntry *)
0x180012bb1  mov     r9d, 13Bh
0x180012bb7  mov     r8, r13
0x180012bba  mov     ecx, eax
0x180012bbc  mov     ebx, eax
0x180012bbe  call    ElValidateWin32
0x180012bc3  test    eax, eax
0x180012bc5  jnz     loc_180012C82
0x180012bcb  mov     edi, r12d
0x180012bce  mov     rdx, [rbp+57h+var_88]
0x180012bd2  lea     r8, [rbp+57h+lpSubKey]
0x180012bd6  lea     rcx, [rbp+57h+hKey]
0x180012bda  call    cs:__imp_?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z; CRegKey::EnumKeyNext(void *,ushort * *)
0x180012be1  nop     dword ptr [rax+rax+00h]
0x180012be6  test    eax, eax
0x180012be8  jz      loc_180012971
0x180012bee  lea     r8, [rbp+57h+arg_8]
0x180012bf2  lea     rdx, [rbp+57h+var_90]
0x180012bf6  lea     rcx, [rbp+57h+var_60]
0x180012bfa  call    ?ConstructDependencyGraph@@YAKAEAV?$CDynArray@PEAUCProviderEntry@@VCDeallocateRelease@@@@PEAPEAPEAHPEAK@Z; ConstructDependencyGraph(CDynArray<CProviderEntry *,CDeallocateRelease> &,int * * *,ulong *)
0x180012bff  mov     r9d, 14Ah
0x180012c05  mov     r8, r13
0x180012c08  mov     ecx, eax
0x180012c0a  mov     ebx, eax
0x180012c0c  call    ElValidateWin32
0x180012c11  test    eax, eax
0x180012c13  jnz     short loc_180012C82
0x180012c15  mov     r15, [rbp+57h+var_90]
0x180012c19  lea     rcx, [rbp+57h+var_60]
0x180012c1d  mov     r13d, [rbp+57h+arg_8]
0x180012c21  mov     rdx, r15
0x180012c24  mov     r8d, r13d
0x180012c27  call    ??$TopologicalSort@PEAUCProviderEntry@@@@YAKAEAV?$CDynArray@PEAUCProviderEntry@@VCDeallocateRelease@@@@PEAPEAHK@Z; TopologicalSort<CProviderEntry *>(CDynArray<CProviderEntry *,CDeallocateRelease> &,int * *,ulong)
0x180012c2c  mov     r9d, 14Fh
0x180012c32  lea     r8, aBaseEcoWdsWdss_16; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x180012c39  mov     ecx, eax
0x180012c3b  mov     ebx, eax
0x180012c3d  call    ElValidateWin32
0x180012c42  test    eax, eax
0x180012c44  jnz     short loc_180012C8A
0x180012c46  mov     ecx, dword ptr [rbp+57h+var_58+4]
0x180012c49  mov     eax, r12d
0x180012c4c  mov     [rbp+57h+var_A0], eax
  ... truncated ...
```
