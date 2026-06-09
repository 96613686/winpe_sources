# CWdsDeviceControllerManager::LoadProvidersFromRegistry(void)

- ea: `0x1800036dc`
- end: `0x180003ac3`
- name: `?LoadProvidersFromRegistry@CWdsDeviceControllerManager@@AEAAKXZ`
- size: `999`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180001e14`

## callees

- `0x1800036dc`
- `0x180003acc`
- `0x180006bec`
- `0x180006c98`
- `0x180013600`
- `0x180013648`
- `0x180013760`
- `0x180014d58`
- `0x180014ee0`
- `0x1800150b8`
- `0x180015660`
- `0x1800157a4`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003710`
- `KERNEL32!EnterCriticalSection` at `0x180003710`
- `KERNEL32!LeaveCriticalSection` at `0x180003a8e`
- `KERNEL32!LeaveCriticalSection` at `0x180003a8e`
- `ADVAPI32!RegCloseKey` at `0x18000375e`
- `ADVAPI32!RegCloseKey` at `0x180003852`
- `ADVAPI32!RegCloseKey` at `0x1800039e7`
- `ADVAPI32!RegCloseKey` at `0x180003a6e`
- `ADVAPI32!RegCloseKey` at `0x180003a81`
- `ADVAPI32!RegCloseKey` at `0x18000375e`
- `ADVAPI32!RegCloseKey` at `0x180003852`
- `ADVAPI32!RegCloseKey` at `0x1800039e7`
- `ADVAPI32!RegCloseKey` at `0x180003a6e`
- `ADVAPI32!RegCloseKey` at `0x180003a81`
- `ADVAPI32!RegOpenKeyExW` at `0x180003788`
- `ADVAPI32!RegOpenKeyExW` at `0x180003874`
- `ADVAPI32!RegOpenKeyExW` at `0x180003788`
- `ADVAPI32!RegOpenKeyExW` at `0x180003874`
- `ADVAPI32!RegEnumKeyExW` at `0x180003831`
- `ADVAPI32!RegEnumKeyExW` at `0x180003831`
- `ole32!CLSIDFromString` at `0x180003999`
- `ole32!CLSIDFromString` at `0x180003999`

## string_xrefs

- `0x18000377a`: `System\CurrentControlSet\Services\WDSServer\Providers\wdsdcmgr\Providers`
- `0x180003908`: `Provider [%s] disabled by registry setting`
- `0x180003923`: `CLSID`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::LoadProvidersFromRegistry(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rdi
  OLECHAR *v3; // rsi
  LSTATUS v4; // eax
  const char *v5; // rdx
  LSTATUS ValueSz; // ebx
  const char *v7; // rdx
  unsigned int v8; // eax
  DWORD *v9; // r15
  int v10; // r14d
  HKEY v11; // rbx
  const char *v12; // rdx
  unsigned int Value; // eax
  const char *v14; // rdx
  const char *v15; // rdx
  const char *v16; // rdx
  const char *v17; // rdx
  const char *v18; // rdx
  HKEY phkResult; // [rsp+48h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-11h] BYREF
  int v22; // [rsp+58h] [rbp-9h] BYREF
  unsigned int v23; // [rsp+5Ch] [rbp-5h] BYREF
  DWORD cchName[2]; // [rsp+60h] [rbp-1h] BYREF
  LPCOLESTR lpsz; // [rsp+68h] [rbp+7h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+70h] [rbp+Fh] BYREF
  CLSID pclsid; // [rsp+78h] [rbp+17h] BYREF

  EnterCriticalSection(this);
  hKey = 0;
  *(_QWORD *)&pclsid.Data1 = 0;
  v2 = 0;
  *(_QWORD *)pclsid.Data4 = 0;
  v3 = 0;
  phkResult = 0;
  v23 = 0;
  *(_QWORD *)cchName = 0;
  lpsz = 0;
  CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocatePointer>::Clear(&this[4]);
  CDynArray<CWdsDeviceControllerManager::CManagementEntry *,CDeallocatePointer>::Clear(&this[4].LockSemaphore);
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\wdsdcmgr\\Providers",
         0,
         0x20119u,
         &hKey);
  ValueSz = v4;
  if ( v4 == 2 )
  {
    ValueSz = 0;
  }
  else if ( !ElValidateWin32(v4, v5, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x47Du) )
  {
    ValueSz = CRegKey::EnumKeyFirst((CRegKey *)&hKey, (void **)cchName);
    v8 = ElValidateWin32(ValueSz, v7, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x480u);
    v9 = *(DWORD **)cchName;
    if ( !v8 )
    {
      while ( 1 )
      {
        cchName[0] = 256;
        v2 = operator new[](0x200u, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v2 )
          break;
        if ( RegEnumKeyExW(hKey, *v9, (LPWSTR)v2, cchName, 0, 0, 0, &ftLastWriteTime) )
        {
          operator delete(v2);
          v2 = 0;
          break;
        }
        ++*v9;
        v10 = 0;
        v11 = hKey;
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        ValueSz = RegOpenKeyExW(v11, (LPCWSTR)v2, 0, 0x20119u, &phkResult);
        if ( ElValidateWin32(
               ValueSz,
               v12,
               "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
               0x489u) )
        {
          break;
        }
        v22 = 0;
        Value = CRegKey::GetValue((CRegKey *)&phkResult, L"Disabled", 4u, &v22, 4u);
        ValueSz = Value;
        if ( Value )
        {
          if ( Value == 2 )
            ValueSz = 0;
        }
        else
        {
          LOBYTE(v10) = v22 != 0;
        }
        if ( ElValidateWin32(
               ValueSz,
               v14,
               "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
               0x48Du) )
        {
          break;
        }
        if ( v10 )
        {
          if ( g_ErrLibTraceFunctionEx )
            g_ErrLibTraceFunctionEx(0x20000u, L"Provider [%s] disabled by registry setting", v2);
        }
        else
        {
          ValueSz = CRegKey::GetValueSz((CRegKey *)&phkResult, L"CLSID", (unsigned __int16 **)&lpsz);
          if ( ElValidateWin32(
                 ValueSz,
                 v15,
                 "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                 0x499u)
            || (ValueSz = CRegKey::GetValue((CRegKey *)&phkResult, L"Priority", 4u, &v23, 4u),
                ElValidateWin32(
                  ValueSz,
                  v16,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0x49Du)) )
          {
            v3 = (OLECHAR *)lpsz;
            break;
          }
          v3 = (OLECHAR *)lpsz;
          ValueSz = CLSIDFromString(lpsz, &pclsid);
          if ( (int)ElValidateHr(
                      ValueSz,
                      v17,
                      "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                      0x4A0u) < 0 )
          {
            if ( ValueSz < 0 && (ValueSz & 0x1FFF0000) == 0x70000 )
              ValueSz = (unsigned __int16)ValueSz;
            break;
          }
          ValueSz = CWdsDeviceControllerManager::LoadProvider(
                      (CWdsDeviceControllerManager *)this,
                      (const unsigned __int16 *)v2,
                      &pclsid,
                      v23);
          if ( ElValidateWin32(
                 ValueSz,
                 v18,
                 "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                 0x4A3u) )
          {
            break;
          }
        }
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        operator delete(v2);
        if ( v3 )
        {
          operator delete(v3);
          v3 = 0;
          lpsz = 0;
        }
      }
    }
    if ( v9 )
      operator delete(v9);
    if ( v2 )
      operator delete(v2);
    if ( v3 )
      operator delete(v3);
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  LeaveCriticalSection(this);
  return (unsigned int)ValueSz;
}

```

## disassembly

```asm
0x1800036dc  mov     rax, rsp
0x1800036df  mov     [rax+10h], rbx
0x1800036e3  mov     [rax+18h], rsi
0x1800036e7  mov     [rax+20h], rdi
0x1800036eb  push    rbp
0x1800036ec  push    r12
0x1800036ee  push    r13
0x1800036f0  push    r14
0x1800036f2  push    r15
0x1800036f4  lea     rbp, [rax-5Fh]
0x1800036f8  sub     rsp, 90h
0x1800036ff  mov     rax, cs:__security_cookie
0x180003706  xor     rax, rsp
0x180003709  mov     [rbp+57h+var_30], rax
0x18000370d  mov     r13, rcx
0x180003710  call    cs:__imp_EnterCriticalSection
0x180003716  xor     r12d, r12d
0x180003719  lea     rcx, [r13+0A0h]
0x180003720  xor     eax, eax
0x180003722  mov     [rbp+57h+hKey], r12
0x180003726  mov     qword ptr [rbp+57h+pclsid.Data1], rax
0x18000372a  mov     edi, r12d
0x18000372d  mov     qword ptr [rbp+57h+pclsid.Data4], rax
0x180003731  mov     esi, r12d
0x180003734  mov     [rbp+57h+var_70], r12
0x180003738  mov     [rbp+57h+var_5C], r12d
0x18000373c  mov     qword ptr [rbp+57h+cchName], r12
0x180003740  mov     [rbp+57h+lpsz], r12
0x180003744  call    ?Clear@?$CDynArray@PEAUCQueryEntry@CWdsDeviceControllerManager@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocatePointer>::Clear(void)
0x180003749  lea     rcx, [r13+0B8h]
0x180003750  call    ?Clear@?$CDynArray@PEAUCManagementEntry@CWdsDeviceControllerManager@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsDeviceControllerManager::CManagementEntry *,CDeallocatePointer>::Clear(void)
0x180003755  mov     rcx, [rbp+57h+hKey]; hKey
0x180003759  test    rcx, rcx
0x18000375c  jz      short loc_180003768
0x18000375e  call    cs:__imp_RegCloseKey
0x180003764  mov     [rbp+57h+hKey], r12
0x180003768  lea     rax, [rbp+57h+hKey]
0x18000376c  mov     r9d, 20119h; samDesired
0x180003772  xor     r8d, r8d; ulOptions
0x180003775  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18000377a  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\WD"...
0x180003781  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003788  call    cs:__imp_RegOpenKeyExW
0x18000378e  mov     ebx, eax
0x180003790  cmp     eax, 2
0x180003793  jnz     short loc_18000379D
0x180003795  mov     ebx, r12d
0x180003798  jmp     loc_180003A65
0x18000379d  lea     r14, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800037a4  mov     r9d, 47Dh; unsigned int
0x1800037aa  mov     r8, r14; char *
0x1800037ad  mov     ecx, eax; unsigned int
0x1800037af  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800037b4  test    eax, eax
0x1800037b6  jnz     loc_180003A65
0x1800037bc  lea     rdx, [rbp+57h+cchName]; void **
0x1800037c0  lea     rcx, [rbp+57h+hKey]; this
0x1800037c4  call    ?EnumKeyFirst@CRegKey@@QEAAKPEAPEAX@Z; CRegKey::EnumKeyFirst(void * *)
0x1800037c9  mov     r9d, 480h; unsigned int
0x1800037cf  mov     r8, r14; char *
0x1800037d2  mov     ecx, eax; unsigned int
0x1800037d4  mov     ebx, eax
0x1800037d6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800037db  mov     r15, qword ptr [rbp+57h+cchName]
0x1800037df  test    eax, eax
0x1800037e1  jnz     loc_180003A3E
0x1800037e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800037ee  mov     [rbp+57h+cchName], 100h
0x1800037f5  mov     ecx, 200h; unsigned __int64
0x1800037fa  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800037ff  mov     rdi, rax
0x180003802  test    rax, rax
0x180003805  jz      loc_180003A3E
0x18000380b  mov     edx, [r15]; dwIndex
0x18000380e  lea     rax, [rbp+57h+ftLastWriteTime]
0x180003812  mov     rcx, [rbp+57h+hKey]; hKey
0x180003816  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000381a  mov     [rsp+0B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000381f  mov     r8, rdi; lpName
0x180003822  mov     [rsp+0B0h+lpcchClass], r12; lpcchClass
0x180003827  mov     [rsp+0B0h+lpClass], r12; lpClass
0x18000382c  mov     [rsp+0B0h+phkResult], r12; lpReserved
0x180003831  call    cs:__imp_RegEnumKeyExW
0x180003837  test    eax, eax
0x180003839  jnz     loc_180003A33
0x18000383f  inc     dword ptr [r15]
0x180003842  mov     rcx, [rbp+57h+var_70]; hKey
0x180003846  mov     r14d, r12d
0x180003849  mov     rbx, [rbp+57h+hKey]
0x18000384d  test    rcx, rcx
0x180003850  jz      short loc_18000385C
0x180003852  call    cs:__imp_RegCloseKey
0x180003858  mov     [rbp+57h+var_70], r12
0x18000385c  lea     rax, [rbp+57h+var_70]
0x180003860  mov     r9d, 20119h; samDesired
0x180003866  xor     r8d, r8d; ulOptions
0x180003869  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18000386e  mov     rdx, rdi; lpSubKey
0x180003871  mov     rcx, rbx; hKey
0x180003874  call    cs:__imp_RegOpenKeyExW
0x18000387a  mov     r9d, 489h; unsigned int
0x180003880  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180003887  mov     ecx, eax; unsigned int
0x180003889  mov     ebx, eax
0x18000388b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180003890  test    eax, eax
0x180003892  jnz     loc_180003A3E
0x180003898  mov     eax, 4
0x18000389d  mov     [rbp+57h+var_60], r12d
0x1800038a1  mov     r8d, eax; unsigned int
0x1800038a4  mov     dword ptr [rsp+0B0h+phkResult], eax; unsigned int
0x1800038a8  lea     r9, [rbp+57h+var_60]; void *
0x1800038ac  lea     rdx, aDisabled; "Disabled"
0x1800038b3  lea     rcx, [rbp+57h+var_70]; this
0x1800038b7  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x1800038bc  mov     ebx, eax
0x1800038be  test    eax, eax
0x1800038c0  jnz     short loc_1800038CC
0x1800038c2  cmp     [rbp+57h+var_60], r12d
0x1800038c6  setnz   r14b
0x1800038ca  jmp     short loc_1800038D4
0x1800038cc  cmp     eax, 2
0x1800038cf  jnz     short loc_1800038D4
0x1800038d1  mov     ebx, r12d
0x1800038d4  mov     r9d, 48Dh; unsigned int
0x1800038da  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800038e1  mov     ecx, ebx; unsigned int
0x1800038e3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800038e8  test    eax, eax
0x1800038ea  jnz     loc_180003A3E
0x1800038f0  test    r14d, r14d
0x1800038f3  jz      short loc_18000391F
0x1800038f5  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800038fc  test    rax, rax
0x1800038ff  jz      loc_1800039DE
0x180003905  mov     r8, rdi
0x180003908  lea     rdx, aProviderSDisab; "Provider [%s] disabled by registry sett"...
0x18000390f  mov     ecx, 20000h
0x180003914  call    cs:__guard_dispatch_icall_fptr
0x18000391a  jmp     loc_1800039DE
0x18000391f  lea     r8, [rbp+57h+lpsz]; unsigned __int16 **
0x180003923  lea     rdx, aClsid; "CLSID"
0x18000392a  lea     rcx, [rbp+57h+var_70]; this
0x18000392e  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x180003933  lea     r14, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000393a  mov     r9d, 499h; unsigned int
0x180003940  mov     r8, r14; char *
0x180003943  mov     ecx, eax; unsigned int
0x180003945  mov     ebx, eax
0x180003947  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000394c  test    eax, eax
0x18000394e  jnz     loc_180003A2D
0x180003954  mov     eax, 4
0x180003959  lea     r9, [rbp+57h+var_5C]; void *
0x18000395d  mov     r8d, eax; unsigned int
0x180003960  mov     dword ptr [rsp+0B0h+phkResult], eax; unsigned int
0x180003964  lea     rdx, aPriority; "Priority"
0x18000396b  lea     rcx, [rbp+57h+var_70]; this
0x18000396f  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180003974  mov     r9d, 49Dh; unsigned int
0x18000397a  mov     r8, r14; char *
0x18000397d  mov     ecx, eax; unsigned int
0x18000397f  mov     ebx, eax
0x180003981  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180003986  test    eax, eax
0x180003988  jnz     loc_180003A2D
0x18000398e  mov     rsi, [rbp+57h+lpsz]
0x180003992  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180003996  mov     rcx, rsi; lpsz
0x180003999  call    cs:__imp_CLSIDFromString
0x18000399f  mov     r9d, 4A0h; unsigned int
0x1800039a5  mov     r8, r14; char *
0x1800039a8  mov     ecx, eax; int
0x1800039aa  mov     ebx, eax
0x1800039ac  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800039b1  test    eax, eax
0x1800039b3  js      short loc_180003A16
0x1800039b5  mov     r9d, [rbp+57h+var_5C]; unsigned int
0x1800039b9  lea     r8, [rbp+57h+pclsid]; struct _GUID *
0x1800039bd  mov     rdx, rdi; unsigned __int16 *
0x1800039c0  mov     rcx, r13; this
0x1800039c3  call    ?LoadProvider@CWdsDeviceControllerManager@@AEAAKPEBGPEAU_GUID@@K@Z; CWdsDeviceControllerManager::LoadProvider(ushort const *,_GUID *,ulong)
0x1800039c8  mov     r9d, 4A3h; unsigned int
0x1800039ce  mov     r8, r14; char *
0x1800039d1  mov     ecx, eax; unsigned int
0x1800039d3  mov     ebx, eax
0x1800039d5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800039da  test    eax, eax
0x1800039dc  jnz     short loc_180003A3E
0x1800039de  mov     rcx, [rbp+57h+var_70]; hKey
0x1800039e2  test    rcx, rcx
0x1800039e5  jz      short loc_1800039F1
0x1800039e7  call    cs:__imp_RegCloseKey
0x1800039ed  mov     [rbp+57h+var_70], r12
0x1800039f1  mov     rcx, rdi; Block
0x1800039f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800039f9  test    rsi, rsi
0x1800039fc  jz      loc_1800037E7
0x180003a02  mov     rcx, rsi; Block
0x180003a05  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a0a  mov     rsi, r12
0x180003a0d  mov     [rbp+57h+lpsz], r12
0x180003a11  jmp     loc_1800037E7
0x180003a16  test    ebx, ebx
0x180003a18  jns     short loc_180003A3E
0x180003a1a  mov     eax, ebx
0x180003a1c  and     eax, 1FFF0000h
0x180003a21  cmp     eax, 70000h
0x180003a26  jnz     short loc_180003A3E
0x180003a28  movzx   ebx, bx
0x180003a2b  jmp     short loc_180003A3E
0x180003a2d  mov     rsi, [rbp+57h+lpsz]
0x180003a31  jmp     short loc_180003A3E
0x180003a33  mov     rcx, rdi; Block
0x180003a36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a3b  mov     rdi, r12
0x180003a3e  test    r15, r15
0x180003a41  jz      short loc_180003A4B
0x180003a43  mov     rcx, r15; Block
0x180003a46  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a4b  test    rdi, rdi
0x180003a4e  jz      short loc_180003A58
0x180003a50  mov     rcx, rdi; Block
0x180003a53  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a58  test    rsi, rsi
0x180003a5b  jz      short loc_180003A65
0x180003a5d  mov     rcx, rsi; Block
0x180003a60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a65  mov     rcx, [rbp+57h+var_70]; hKey
0x180003a69  test    rcx, rcx
0x180003a6c  jz      short loc_180003A78
0x180003a6e  call    cs:__imp_RegCloseKey
0x180003a74  mov     [rbp+57h+var_70], r12
0x180003a78  mov     rcx, [rbp+57h+hKey]; hKey
0x180003a7c  test    rcx, rcx
0x180003a7f  jz      short loc_180003A8B
0x180003a81  call    cs:__imp_RegCloseKey
0x180003a87  mov     [rbp+57h+hKey], r12
0x180003a8b  mov     rcx, r13; lpCriticalSection
0x180003a8e  call    cs:__imp_LeaveCriticalSection
0x180003a94  mov     eax, ebx
0x180003a96  mov     rcx, [rbp+57h+var_30]
0x180003a9a  xor     rcx, rsp; StackCookie
0x180003a9d  call    __security_check_cookie
0x180003aa2  lea     r11, [rsp+0B0h+var_20]
0x180003aaa  mov     rbx, [r11+38h]
0x180003aae  mov     rsi, [r11+40h]
0x180003ab2  mov     rdi, [r11+48h]
0x180003ab6  mov     rsp, r11
0x180003ab9  pop     r15
0x180003abb  pop     r14
0x180003abd  pop     r13
0x180003abf  pop     r12
0x180003ac1  pop     rbp
0x180003ac2  retn
```
