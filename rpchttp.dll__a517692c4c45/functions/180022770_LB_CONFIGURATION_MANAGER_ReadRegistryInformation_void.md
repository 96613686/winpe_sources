# LB_CONFIGURATION_MANAGER::ReadRegistryInformation(void)

- ea: `0x180022770`
- end: `0x180023056`
- name: `?ReadRegistryInformation@LB_CONFIGURATION_MANAGER@@QEAAJXZ`
- size: `2278`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021e90`
- `0x1800220f4`

## callees

- `0x180020b64`
- `0x180021e20`
- `0x1800222b4`
- `0x180022770`
- `0x18002305c`
- `0x180023ff4`
- `0x1800240d8`
- `0x180024611`

## import_xrefs

- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18002294d`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18002294d`
- `ntdll!RtlLeaveCriticalSection` at `0x180022de7`
- `ntdll!RtlLeaveCriticalSection` at `0x180022e00`
- `ntdll!RtlLeaveCriticalSection` at `0x180022e1b`
- `ntdll!RtlLeaveCriticalSection` at `0x180022ec8`
- `ntdll!RtlLeaveCriticalSection` at `0x180022f26`
- `ntdll!RtlLeaveCriticalSection` at `0x180022f62`
- `ntdll!RtlLeaveCriticalSection` at `0x180022de7`
- `ntdll!RtlLeaveCriticalSection` at `0x180022e00`
- `ntdll!RtlLeaveCriticalSection` at `0x180022e1b`
- `ntdll!RtlLeaveCriticalSection` at `0x180022ec8`
- `ntdll!RtlLeaveCriticalSection` at `0x180022f26`
- `ntdll!RtlLeaveCriticalSection` at `0x180022f62`
- `ntdll!RtlEnterCriticalSection` at `0x180022b9b`
- `ntdll!RtlEnterCriticalSection` at `0x180022b9b`
- `KERNEL32!CompareFileTime` at `0x180022c1a`
- `KERNEL32!CompareFileTime` at `0x180022c1a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800227f9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800229b6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800227f9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800229b6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180022894`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180022894`
- `ADVAPI32!RegEnumKeyExW` at `0x180022903`
- `ADVAPI32!RegEnumKeyExW` at `0x180022903`
- `ADVAPI32!RegCloseKey` at `0x180022fbc`
- `ADVAPI32!RegCloseKey` at `0x180022fcb`
- `ADVAPI32!RegCloseKey` at `0x180022fbc`
- `ADVAPI32!RegCloseKey` at `0x180022fcb`
- `ADVAPI32!RegGetValueW` at `0x1800229fc`
- `ADVAPI32!RegGetValueW` at `0x180022a58`
- `ADVAPI32!RegGetValueW` at `0x180022acb`
- `ADVAPI32!RegGetValueW` at `0x180022e64`
- `ADVAPI32!RegGetValueW` at `0x1800229fc`
- `ADVAPI32!RegGetValueW` at `0x180022a58`
- `ADVAPI32!RegGetValueW` at `0x180022acb`
- `ADVAPI32!RegGetValueW` at `0x180022e64`
- `RPCRT4!I_RpcFree` at `0x180022b1e`
- `RPCRT4!I_RpcFree` at `0x180022e9f`
- `RPCRT4!I_RpcFree` at `0x180022ebb`
- `RPCRT4!I_RpcFree` at `0x18002303a`
- `RPCRT4!I_RpcFree` at `0x180022b1e`
- `RPCRT4!I_RpcFree` at `0x180022e9f`
- `RPCRT4!I_RpcFree` at `0x180022ebb`
- `RPCRT4!I_RpcFree` at `0x18002303a`
- `RPCRT4!I_RpcAllocate` at `0x1800228ba`
- `RPCRT4!I_RpcAllocate` at `0x18002292f`
- `RPCRT4!I_RpcAllocate` at `0x180022a92`
- `RPCRT4!I_RpcAllocate` at `0x180022dd6`
- `RPCRT4!I_RpcAllocate` at `0x1800228ba`
- `RPCRT4!I_RpcAllocate` at `0x18002292f`
- `RPCRT4!I_RpcAllocate` at `0x180022a92`
- `RPCRT4!I_RpcAllocate` at `0x180022dd6`
- `RPCRT4!UuidFromStringW` at `0x18002298d`
- `RPCRT4!UuidFromStringW` at `0x180022e86`
- `RPCRT4!UuidFromStringW` at `0x18002298d`
- `RPCRT4!UuidFromStringW` at `0x180022e86`

## string_xrefs

- `0x180022798`: `Software\Microsoft\Rpc\RpcProxy\LBSConfiguration`
- `0x1800229ee`: `ConfigurationType`
- `0x180022d8e`: `NoSecurity`

## pseudocode

```c
__int64 __fastcall LB_CONFIGURATION_MANAGER::ReadRegistryInformation(PRTL_CRITICAL_SECTION CriticalSection)
{
  PRTL_CRITICAL_SECTION v1; // r14
  LB_RESOURCE_ID_CONFIG_ENTRY *v2; // rdi
  int v3; // r13d
  LSTATUS v4; // eax
  WCHAR *v5; // r12
  LB_RESOURCE_ID_CONFIG_ENTRY *v6; // rsi
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // r9
  unsigned int v10; // eax
  DWORD v11; // esi
  LSTATUS v12; // eax
  char *v13; // rax
  unsigned int v14; // edx
  LSTATUS v15; // eax
  unsigned int v16; // edx
  LSTATUS ValueW; // eax
  LSTATUS v18; // eax
  unsigned int v19; // eax
  void *v20; // rax
  LSTATUS v21; // eax
  LB_RESOURCE_ID_CONFIG_ENTRY **v22; // rax
  unsigned int v23; // edx
  LB_RESOURCE_ID_CONFIG_ENTRY *v24; // rbx
  int v25; // r14d
  FILETIME **p_LockCount; // rbx
  FILETIME **v27; // rcx
  FILETIME **v28; // rax
  LB_RESOURCE_ID_CONFIG_ENTRY *v29; // rsi
  FILETIME *v30; // rdi
  LB_RESOURCE_ID_CONFIG_ENTRY **v31; // r13
  FILETIME *v32; // r15
  LB_RESOURCE_ID_CONFIG_ENTRY **v33; // rcx
  LB_RESOURCE_ID_CONFIG_ENTRY **v34; // rax
  FILETIME *v35; // rax
  FILETIME *v36; // rsi
  LB_RESOURCE_ID_CONFIG_ENTRY *v37; // rcx
  LB_RESOURCE_ID_CONFIG_ENTRY *i; // rax
  LB_RESOURCE_ID_CONFIG_ENTRY *v39; // rcx
  LB_RESOURCE_ID_CONFIG_ENTRY **v40; // rdx
  FILETIME *v41; // rdx
  int RegistryDword; // eax
  ULONG_PTR *p_SpinCount; // r15
  int v44; // eax
  void *v45; // rsi
  LSTATUS v46; // eax
  int v47; // eax
  unsigned int LockSemaphore_high; // eax
  DWORD v49; // ecx
  LB_RESOURCE_ID_CONFIG_ENTRY *v50; // rdi
  LB_RESOURCE_ID_CONFIG_ENTRY *v51; // rcx
  unsigned __int16 lpcbMaxSubKeyLen; // [rsp+28h] [rbp-81h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-41h] BYREF
  LB_RESOURCE_ID_CONFIG_ENTRY *v55; // [rsp+70h] [rbp-39h] BYREF
  LB_RESOURCE_ID_CONFIG_ENTRY **v56; // [rsp+78h] [rbp-31h]
  DWORD v57; // [rsp+80h] [rbp-29h] BYREF
  DWORD v58; // [rsp+84h] [rbp-25h] BYREF
  DWORD cchName; // [rsp+88h] [rbp-21h] BYREF
  DWORD cSubKeys; // [rsp+8Ch] [rbp-1Dh] BYREF
  DWORD pcbData; // [rsp+90h] [rbp-19h] BYREF
  int pvData; // [rsp+94h] [rbp-15h] BYREF
  HKEY hkey; // [rsp+98h] [rbp-11h] BYREF
  LPCWSTR Strings[2]; // [rsp+A0h] [rbp-9h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+B0h] [rbp+7h] BYREF
  int v67; // [rsp+118h] [rbp+6Fh]

  v56 = &v55;
  hKey = 0;
  v55 = (LB_RESOURCE_ID_CONFIG_ENTRY *)&v55;
  v1 = CriticalSection;
  hkey = 0;
  pcbData = 0;
  pvData = 0;
  cSubKeys = 0;
  v2 = 0;
  cbMaxSubKeyLen = 0;
  v3 = 0;
  v57 = 0;
  cchName = 0;
  ftLastWriteTime = 0;
  v67 = 0;
  v58 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc\\RpcProxy\\LBSConfiguration", 0, 0x20019u, &hKey);
  if ( v4 == 2 )
  {
    v5 = 0;
    hKey = 0;
    goto LABEL_3;
  }
  if ( v4 )
    return 14;
LABEL_9:
  if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    ++cbMaxSubKeyLen;
    v10 = 2 * cbMaxSubKeyLen;
    if ( !is_mul_ok(cbMaxSubKeyLen, 2u) )
      v10 = -1;
    v5 = (WCHAR *)I_RpcAllocate(v10);
    v11 = 0;
    if ( !v5 )
    {
      v7 = 14;
      goto LABEL_116;
    }
    while ( v11 < cSubKeys )
    {
      cchName = cbMaxSubKeyLen;
      v12 = RegEnumKeyExW(hKey, v11, v5, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( v12 == 259 )
        goto LABEL_37;
      if ( v12 )
        goto LABEL_118;
      if ( cchName + 1 > cbMaxSubKeyLen )
        goto LABEL_37;
      v13 = (char *)I_RpcAllocate(0x98u);
      v2 = (LB_RESOURCE_ID_CONFIG_ENTRY *)v13;
      if ( !v13 )
      {
        v2 = 0;
        goto LABEL_118;
      }
      *((_DWORD *)v13 + 4) = 1;
      RtlInitializeCriticalSectionAndSpinCount((PRTL_CRITICAL_SECTION)(v13 + 48), 0xBB8u);
      *((_QWORD *)v2 + 14) = 0;
      *((_QWORD *)v2 + 4) = (char *)v2 + 24;
      *((_QWORD *)v2 + 3) = (char *)v2 + 24;
      *((_DWORD *)v2 + 10) = 0;
      *((_QWORD *)v2 + 17) = 0;
      *(_QWORD *)v2 = 0;
      *((_QWORD *)v2 + 1) = 0;
      *((_QWORD *)v2 + 15) = 0;
      *((_QWORD *)v2 + 16) = 0;
      _InterlockedAdd(&AllocatedResourceConfigEntries, 1u);
      v7 = UuidFromStringW(v5, (UUID *)((char *)v2 + 88));
      if ( v7 )
      {
        LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(v2, v14);
        v11 = 1;
        goto LABEL_116;
      }
      v15 = RegOpenKeyExW(hKey, v5, 0, 0x20019u, &hkey);
      if ( v15 == 2 )
      {
        LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(v2, v16);
LABEL_37:
        I_RpcFree(v5);
        v24 = v55;
        while ( v24 != (LB_RESOURCE_ID_CONFIG_ENTRY *)&v55 )
        {
          v2 = v24;
          v24 = *(LB_RESOURCE_ID_CONFIG_ENTRY **)v24;
          if ( v2 )
            LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(v2, v23);
        }
        goto LABEL_9;
      }
      if ( v15 )
        goto LABEL_42;
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"ConfigurationType", 0x18u, 0, &pvData, &pcbData);
      if ( ValueW == 2 )
        goto LABEL_22;
      if ( ValueW )
        goto LABEL_42;
      if ( pvData != 1 )
      {
        v25 = 1;
        v7 = 1722;
        goto LABEL_120;
      }
      *((_DWORD *)v2 + 26) = 1;
      v57 = 0;
      v18 = RegGetValueW(hkey, 0, L"ServerFarm", 2u, 0, 0, &v57);
      if ( v18 == 2 )
        goto LABEL_22;
      if ( v18 )
        goto LABEL_42;
      v19 = 2 * (v57 + 1);
      if ( !is_mul_ok(v57 + 1, 2u) )
        v19 = -1;
      v20 = I_RpcAllocate(v19);
      *((_QWORD *)v2 + 14) = v20;
      if ( !v20 )
      {
LABEL_42:
        LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(v2, v16);
        goto LABEL_118;
      }
      v21 = RegGetValueW(hkey, 0, L"ServerFarm", 2u, 0, v20, &v57);
      if ( v21 == 2 )
      {
LABEL_22:
        LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(v2, v16);
      }
      else
      {
        if ( v21 )
          goto LABEL_42;
        *((struct _FILETIME *)v2 + 18) = ftLastWriteTime;
        v22 = v56;
        if ( *v56 != (LB_RESOURCE_ID_CONFIG_ENTRY *)&v55 )
LABEL_89:
          __fastfail(3u);
        *((_QWORD *)v2 + 1) = v56;
        *(_QWORD *)v2 = &v55;
        *v22 = v2;
        v56 = (LB_RESOURCE_ID_CONFIG_ENTRY **)v2;
      }
      ++v11;
    }
LABEL_3:
    v6 = v55;
    while ( v6 != (LB_RESOURCE_ID_CONFIG_ENTRY *)&v55 )
    {
      v2 = v6;
      v6 = *(LB_RESOURCE_ID_CONFIG_ENTRY **)v6;
      v7 = LB_RESOURCE_ID_CONFIG_ENTRY::ParseConfiguration(v2);
      if ( v7 )
      {
        v3 = 1;
        goto LABEL_119;
      }
    }
    LODWORD(Strings[0]) = 0;
    RtlEnterCriticalSection(v1);
    p_LockCount = (FILETIME **)&v1[1].LockCount;
    v27 = *(FILETIME ***)&v1[1].LockCount;
    while ( v27 != p_LockCount )
    {
      v28 = v27;
      v27 = (FILETIME **)*v27;
      *((_DWORD *)v28 + 31) = 0;
    }
    v29 = v55;
    if ( v55 != (LB_RESOURCE_ID_CONFIG_ENTRY *)&v55 )
    {
      do
      {
        v30 = *p_LockCount;
        v31 = *(LB_RESOURCE_ID_CONFIG_ENTRY ***)v29;
        if ( *p_LockCount != (FILETIME *)p_LockCount )
        {
          do
          {
            v32 = (FILETIME *)*v30;
            if ( !v30[15].dwLowDateTime && !memcmp_0(&v30[11], (char *)v29 + 88, 0x10u) )
            {
              v30[15].dwHighDateTime = 1;
              *((_DWORD *)v29 + 31) = 1;
              if ( CompareFileTime(v30 + 18, (const FILETIME *)v29 + 18) >= 0 )
              {
                LB_RESOURCE_ID_CONFIG_ENTRY::RemoveLifetimeReference(v29);
              }
              else
              {
                v30[15].dwLowDateTime = 1;
                LB_RESOURCE_ID_CONFIG_ENTRY::RemoveLifetimeReference((LB_RESOURCE_ID_CONFIG_ENTRY *)v30);
                v33 = *(LB_RESOURCE_ID_CONFIG_ENTRY ***)v29;
                if ( *(_QWORD *)v29 )
                {
                  v34 = (LB_RESOURCE_ID_CONFIG_ENTRY **)*((_QWORD *)v29 + 1);
                  if ( v34 )
                  {
                    if ( v33[1] != v29 || *v34 != v29 )
                      goto LABEL_89;
                    *v34 = (LB_RESOURCE_ID_CONFIG_ENTRY *)v33;
                    v33[1] = (LB_RESOURCE_ID_CONFIG_ENTRY *)v34;
                    *(_QWORD *)v29 = 0;
                    *((_QWORD *)v29 + 1) = 0;
                  }
                }
                *((_QWORD *)v29 + 17) = v1;
                v35 = *p_LockCount;
                if ( (FILETIME **)(*p_LockCount)[1] != p_LockCount )
                  goto LABEL_89;
                *(_QWORD *)v29 = v35;
                *((_QWORD *)v29 + 1) = p_LockCount;
                v35[1] = (FILETIME)v29;
                *p_LockCount = (FILETIME *)v29;
                LODWORD(Strings[0]) = 1;
              }
            }
            v30 = v32;
          }
          while ( v32 != (FILETIME *)p_LockCount );
        }
        v2 = v29;
        v29 = (LB_RESOURCE_ID_CONFIG_ENTRY *)v31;
      }
      while ( v31 != &v55 );
      v3 = (int)Strings[0];
    }
    v36 = *p_LockCount;
    if ( *p_LockCount != (FILETIME *)p_LockCount )
    {
      do
      {
        v37 = (LB_RESOURCE_ID_CONFIG_ENTRY *)v36;
        v36 = (FILETIME *)*v36;
        if ( !*((_DWORD *)v37 + 31) && !*((_DWORD *)v37 + 30) )
        {
          *((_DWORD *)v37 + 30) = 1;
          LB_RESOURCE_ID_CONFIG_ENTRY::RemoveLifetimeReference(v37);
          v3 = 1;
        }
      }
      while ( v36 != (FILETIME *)p_LockCount );
      v1 = CriticalSection;
    }
    for ( i = v55; i != (LB_RESOURCE_ID_CONFIG_ENTRY *)&v55; i = v39 )
    {
      v39 = *(LB_RESOURCE_ID_CONFIG_ENTRY **)i;
      if ( !*((_DWORD *)i + 31) )
      {
        if ( v39 )
        {
          v40 = (LB_RESOURCE_ID_CONFIG_ENTRY **)*((_QWORD *)i + 1);
          if ( v40 )
          {
            if ( *((LB_RESOURCE_ID_CONFIG_ENTRY **)v39 + 1) != i || *v40 != i )
              goto LABEL_89;
            *v40 = v39;
            *((_QWORD *)v39 + 1) = v40;
            *(_QWORD *)i = 0;
            *((_QWORD *)i + 1) = 0;
          }
        }
        *((_QWORD *)i + 17) = v1;
        v41 = *p_LockCount;
        if ( (FILETIME **)(*p_LockCount)[1] != p_LockCount )
          goto LABEL_89;
        *(_QWORD *)i = v41;
        v3 = 1;
        *((_QWORD *)i + 1) = p_LockCount;
        v41[1] = (FILETIME)i;
        *p_LockCount = (FILETIME *)i;
      }
      v2 = i;
    }
    HIDWORD(v1[1].LockSemaphore) = *p_LockCount != (FILETIME *)p_LockCount;
    if ( hKey )
    {
      RegistryDword = ReadRegistryDword(hKey, L"NoSecurity", (unsigned int *)&v1[1].LockSemaphore);
      v7 = RegistryDword;
      if ( RegistryDword == 2 )
      {
        LODWORD(v1[1].LockSemaphore) = 0;
      }
      else if ( RegistryDword )
      {
        RtlLeaveCriticalSection(v1);
        v11 = 0;
        v3 = 0;
        v25 = 0;
        goto LABEL_121;
      }
      p_SpinCount = &v1[1].SpinCount;
      v44 = ReadRegistryDword(hKey, L"ResponseTimeout", (unsigned int *)&v1[1].SpinCount);
      v7 = v44;
      if ( v44 == 2 )
      {
        *(_DWORD *)p_SpinCount = 20000;
      }
      else if ( v44 )
      {
        RtlLeaveCriticalSection(v1);
        goto LABEL_94;
      }
      v58 = 37;
      v45 = I_RpcAllocate(0x4Au);
      if ( !v45 )
      {
        RtlLeaveCriticalSection(v1);
        v7 = 14;
LABEL_94:
        v11 = 0;
        v3 = 0;
        v25 = 0;
        goto LABEL_121;
      }
      v58 *= 2;
      v46 = RegGetValueW(hKey, 0, L"AssumeResourceUUID", 2u, 0, v45, &v58);
      if ( v46 == 2 )
      {
        HIDWORD(v1[1].SpinCount) = 0;
        v7 = 0;
      }
      else if ( v46 )
      {
        v7 = 14;
      }
      else
      {
        v7 = UuidFromStringW((RPC_WSTR)v45, (UUID *)&v1[2]);
        if ( v7 )
        {
          I_RpcFree(v5);
          v5 = (WCHAR *)v45;
          v67 = 1;
          v45 = 0;
        }
        else
        {
          HIDWORD(v1[1].SpinCount) = 1;
        }
      }
      I_RpcFree(v45);
      if ( v7 )
      {
        RtlLeaveCriticalSection(v1);
        v3 = 0;
        v25 = 0;
        v11 = v67;
        goto LABEL_121;
      }
      g_LBSResponseTimeout = *(_DWORD *)p_SpinCount;
      g_fAssumeResourceUUIDPresent = HIDWORD(v1[1].SpinCount);
      if ( g_fAssumeResourceUUIDPresent )
        g_AssumeResourceUUID = *(GUID *)&v1[2].DebugInfo;
      v47 = ReadRegistryDword(hKey, L"ServersInRelevantSet", (unsigned int *)&v1[2].LockSemaphore + 1);
      v7 = v47;
      if ( v47 != 2 )
      {
        if ( v47 )
        {
          RtlLeaveCriticalSection(v1);
          v11 = v67;
          v3 = 0;
LABEL_116:
          v25 = 0;
          goto LABEL_121;
        }
        LockSemaphore_high = HIDWORD(v1[2].LockSemaphore);
        goto LABEL_112;
      }
    }
    else
    {
      g_LBSResponseTimeout = 20000;
      g_fAssumeResourceUUIDPresent = 0;
    }
    LockSemaphore_high = 0;
LABEL_112:
    g_NumberOfServersInRelevantSet = LockSemaphore_high;
    g_LBActive = HIDWORD(v1[1].LockSemaphore);
    RtlLeaveCriticalSection(v1);
    if ( v3 )
    {
      Strings[0] = 0;
      LogEventCommon(0x40000005u, Strings, 1u, v8, 4u, lpcbMaxSubKeyLen);
    }
    v3 = 0;
    v7 = 0;
    v11 = v67;
    v25 = 0;
    goto LABEL_121;
  }
  v5 = 0;
LABEL_118:
  v7 = 14;
LABEL_119:
  v25 = 0;
LABEL_120:
  v11 = 0;
LABEL_121:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v11 )
  {
    v49 = -1073741818;
  }
  else
  {
    if ( !v25 )
    {
      if ( v3 )
        LogBadConfigEntryError((struct _GUID *)((char *)v2 + 88), *((unsigned __int16 **)v2 + 14));
      goto LABEL_132;
    }
    v49 = -1073741817;
  }
  Strings[1] = v5;
  Strings[0] = 0;
  LogEventCommon(v49, Strings, 2u, v8, 1u, lpcbMaxSubKeyLen);
LABEL_132:
  v50 = v55;
  while ( v50 != (LB_RESOURCE_ID_CONFIG_ENTRY *)&v55 )
  {
    v51 = v50;
    v50 = *(LB_RESOURCE_ID_CONFIG_ENTRY **)v50;
    LB_RESOURCE_ID_CONFIG_ENTRY::RemoveLifetimeReference(v51);
  }
  if ( v5 )
    I_RpcFree(v5);
  return v7;
}

```

## disassembly

```asm
0x180022770  mov     [rsp-8+arg_0], rcx
0x180022775  push    rbp
0x180022776  push    rbx
0x180022777  push    rsi
0x180022778  push    rdi
0x180022779  push    r12
0x18002277b  push    r13
0x18002277d  push    r14
0x18002277f  push    r15
0x180022781  lea     rbp, [rsp-1Fh]
0x180022786  sub     rsp, 0C8h
0x18002278d  xor     r15d, r15d
0x180022790  lea     rax, [rbp+57h+var_90]
0x180022794  mov     [rbp+57h+var_88], rax
0x180022798  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Rpc\\RpcProxy\\LBS"...
0x18002279f  lea     rax, [rbp+57h+var_90]
0x1800227a3  mov     [rbp+57h+hKey], r15
0x1800227a7  mov     [rbp+57h+var_90], rax
0x1800227ab  mov     r14, rcx
0x1800227ae  lea     rax, [rbp+57h+hKey]
0x1800227b2  mov     [rbp+57h+hkey], r15
0x1800227b6  mov     r9d, 20019h; samDesired
0x1800227bc  mov     [rsp+100h+phkResult], rax; phkResult
0x1800227c1  xor     r8d, r8d; ulOptions
0x1800227c4  mov     [rbp+57h+pcbData], r15d
0x1800227c8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800227cf  mov     [rbp+57h+pvData], r15d
0x1800227d3  mov     [rbp+57h+cSubKeys], r15d
0x1800227d7  mov     edi, r15d
0x1800227da  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x1800227de  mov     r13d, r15d
0x1800227e1  mov     [rbp+57h+var_80], r15d
0x1800227e5  mov     [rbp+57h+cchName], r15d
0x1800227e9  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r15
0x1800227ed  mov     [rbp+57h+arg_8], r15d
0x1800227f1  mov     [rbp+57h+arg_18], r15d
0x1800227f5  mov     [rbp+57h+var_7C], r15d
0x1800227f9  call    cs:__imp_RegOpenKeyExW
0x1800227ff  lea     ebx, [r15+1]
0x180022803  cmp     eax, 2
0x180022806  jnz     short loc_18002283F
0x180022808  mov     r12d, r15d
0x18002280b  mov     [rbp+57h+hKey], r15
0x18002280f  mov     rsi, [rbp+57h+var_90]
0x180022813  lea     rax, [rbp+57h+var_90]
0x180022817  cmp     rsi, rax
0x18002281a  jz      loc_180022B94
0x180022820  mov     rdi, rsi
0x180022823  mov     rsi, [rsi]
0x180022826  mov     rcx, rdi; this
0x180022829  call    ?ParseConfiguration@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAJXZ; LB_RESOURCE_ID_CONFIG_ENTRY::ParseConfiguration(void)
0x18002282e  mov     ebx, eax
0x180022830  test    eax, eax
0x180022832  jz      short loc_180022813
0x180022834  mov     r13d, 1
0x18002283a  jmp     loc_180022FAD
0x18002283f  test    eax, eax
0x180022841  jz      short loc_18002284D
0x180022843  mov     eax, 0Eh
0x180022848  jmp     loc_180023042
0x18002284d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180022851  jmp     short loc_180022858
0x180022853  mov     ebx, 1
0x180022858  mov     rcx, [rbp+57h+hKey]; hKey
0x18002285c  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180022860  mov     [rsp+100h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180022865  xor     r9d, r9d; lpReserved
0x180022868  mov     [rsp+100h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002286d  xor     r8d, r8d; lpcchClass
0x180022870  mov     [rsp+100h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180022875  xor     edx, edx; lpClass
0x180022877  mov     [rsp+100h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18002287c  mov     [rsp+100h+lpcValues], r15; lpcValues
0x180022881  mov     [rsp+100h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180022886  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; unsigned __int16
0x18002288b  lea     rax, [rbp+57h+cSubKeys]
0x18002288f  mov     [rsp+100h+phkResult], rax; lpcSubKeys
0x180022894  call    cs:__imp_RegQueryInfoKeyW
0x18002289a  test    eax, eax
0x18002289c  jnz     loc_180022FA5
0x1800228a2  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800228a5  add     eax, ebx
0x1800228a7  mov     ecx, eax
0x1800228a9  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x1800228ac  mov     eax, 2
0x1800228b1  mul     rcx
0x1800228b4  cmovb   rax, rsi
0x1800228b8  mov     ecx, eax; Size
0x1800228ba  call    cs:__imp_I_RpcAllocate
0x1800228c0  mov     r12, rax
0x1800228c3  mov     esi, r15d
0x1800228c6  test    rax, rax
0x1800228c9  jz      loc_180022F9B
0x1800228cf  cmp     esi, [rbp+57h+cSubKeys]
0x1800228d2  jnb     loc_18002280F
0x1800228d8  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x1800228db  lea     rax, [rbp+57h+ftLastWriteTime]
0x1800228df  mov     [rsp+100h+lpcValues], rax; lpftLastWriteTime
0x1800228e4  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800228e8  mov     [rsp+100h+lpcbMaxClassLen], r15; lpcchClass
0x1800228ed  mov     r8, r12; lpName
0x1800228f0  mov     [rbp+57h+cchName], ecx
0x1800228f3  mov     edx, esi; dwIndex
0x1800228f5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800228f9  mov     [rsp+100h+lpcbMaxSubKeyLen], r15; lpClass
0x1800228fe  mov     [rsp+100h+phkResult], r15; lpReserved
0x180022903  call    cs:__imp_RegEnumKeyExW
0x180022909  cmp     eax, 103h
0x18002290e  jz      loc_180022B1B
0x180022914  test    eax, eax
0x180022916  jnz     loc_180022FA8
0x18002291c  mov     eax, [rbp+57h+cchName]
0x18002291f  inc     eax
0x180022921  cmp     eax, [rbp+57h+cbMaxSubKeyLen]
0x180022924  ja      loc_180022B1B
0x18002292a  mov     ecx, 98h; Size
0x18002292f  call    cs:__imp_I_RpcAllocate
0x180022935  mov     rdi, rax
0x180022938  test    rax, rax
0x18002293b  jz      loc_180022B8C
0x180022941  lea     rcx, [rax+30h]; CriticalSection
0x180022945  mov     [rax+10h], ebx
0x180022948  mov     edx, 0BB8h; SpinCount
0x18002294d  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180022953  lea     rax, [rdi+18h]
0x180022957  mov     [rdi+70h], r15
0x18002295b  mov     [rdi+20h], rax
0x18002295f  mov     [rax], rax
0x180022962  mov     [rdi+28h], r15d
0x180022966  mov     [rdi+88h], r15
0x18002296d  mov     [rdi], r15
0x180022970  mov     [rdi+8], r15
0x180022974  mov     [rdi+78h], r15
0x180022978  mov     [rdi+80h], r15
0x18002297f  lock add cs:?AllocatedResourceConfigEntries@@3JA, ebx; long AllocatedResourceConfigEntries
0x180022986  lea     rdx, [rdi+58h]; Uuid
0x18002298a  mov     rcx, r12; StringUuid
0x18002298d  call    cs:__imp_UuidFromStringW
0x180022993  mov     ebx, eax
0x180022995  test    eax, eax
0x180022997  jnz     loc_180022B7A
0x18002299d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800229a1  lea     rax, [rbp+57h+hkey]
0x1800229a5  mov     r9d, 20019h; samDesired
0x1800229ab  mov     [rsp+100h+phkResult], rax; phkResult
0x1800229b0  xor     r8d, r8d; ulOptions
0x1800229b3  mov     rdx, r12; lpSubKey
0x1800229b6  call    cs:__imp_RegOpenKeyExW
0x1800229bc  cmp     eax, 2
0x1800229bf  jz      loc_180022B13
0x1800229c5  test    eax, eax
0x1800229c7  jnz     loc_180022B60
0x1800229cd  mov     rcx, [rbp+57h+hkey]; hkey
0x1800229d1  lea     rax, [rbp+57h+pcbData]
0x1800229d5  mov     [rsp+100h+lpcbMaxClassLen], rax; pcbData
0x1800229da  lea     r9d, [rbx+18h]; dwFlags
0x1800229de  lea     rax, [rbp+57h+pvData]
0x1800229e2  mov     [rbp+57h+pcbData], 4
0x1800229e9  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; pvData
0x1800229ee  lea     r8, aConfigurationt; "ConfigurationType"
0x1800229f5  xor     edx, edx; lpSubKey
0x1800229f7  mov     [rsp+100h+phkResult], r15; pdwType
0x1800229fc  call    cs:__imp_RegGetValueW
0x180022a02  cmp     eax, 2
0x180022a05  jnz     short loc_180022A19
0x180022a07  mov     rcx, rdi; this
0x180022a0a  call    ??_GLB_RESOURCE_ID_CONFIG_ENTRY@@QEAAPEAXI@Z; LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(uint)
0x180022a0f  mov     ebx, 1
0x180022a14  jmp     loc_180022B0C
0x180022a19  test    eax, eax
0x180022a1b  jnz     loc_180022B60
0x180022a21  lea     ebx, [rax+1]
0x180022a24  cmp     [rbp+57h+pvData], ebx
0x180022a27  jnz     loc_180022B6D
0x180022a2d  mov     [rdi+68h], ebx
0x180022a30  lea     rax, [rbp+57h+var_80]
0x180022a34  mov     rcx, [rbp+57h+hkey]; hkey
0x180022a38  lea     r9d, [rbx+1]; dwFlags
0x180022a3c  mov     [rsp+100h+lpcbMaxClassLen], rax; pcbData
0x180022a41  lea     r8, aServerfarm; "ServerFarm"
0x180022a48  mov     [rsp+100h+lpcbMaxSubKeyLen], r15; pvData
0x180022a4d  xor     edx, edx; lpSubKey
0x180022a4f  mov     [rsp+100h+phkResult], r15; pdwType
0x180022a54  mov     [rbp+57h+var_80], r15d
0x180022a58  call    cs:__imp_RegGetValueW
0x180022a5e  cmp     eax, 2
0x180022a61  jnz     short loc_180022A70
0x180022a63  mov     rcx, rdi; this
0x180022a66  call    ??_GLB_RESOURCE_ID_CONFIG_ENTRY@@QEAAPEAXI@Z; LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(uint)
0x180022a6b  jmp     loc_180022B0C
0x180022a70  test    eax, eax
0x180022a72  jnz     loc_180022B60
0x180022a78  mov     ecx, [rbp+57h+var_80]
0x180022a7b  mov     eax, 2
0x180022a80  inc     ecx
0x180022a82  mul     rcx
0x180022a85  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022a8c  cmovb   rax, rcx
0x180022a90  mov     ecx, eax; Size
0x180022a92  call    cs:__imp_I_RpcAllocate
0x180022a98  mov     [rdi+70h], rax
0x180022a9c  test    rax, rax
0x180022a9f  jz      loc_180022B60
0x180022aa5  lea     rcx, [rbp+57h+var_80]
0x180022aa9  mov     r9d, 2; dwFlags
0x180022aaf  mov     [rsp+100h+lpcbMaxClassLen], rcx; pcbData
0x180022ab4  lea     r8, aServerfarm; "ServerFarm"
0x180022abb  mov     rcx, [rbp+57h+hkey]; hkey
0x180022abf  xor     edx, edx; lpSubKey
0x180022ac1  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; pvData
0x180022ac6  mov     [rsp+100h+phkResult], r15; pdwType
0x180022acb  call    cs:__imp_RegGetValueW
0x180022ad1  cmp     eax, 2
0x180022ad4  jz      short loc_180022A63
0x180022ad6  test    eax, eax
0x180022ad8  jnz     loc_180022B60
0x180022ade  mov     rax, qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime]
0x180022ae2  lea     rcx, [rbp+57h+var_90]
0x180022ae6  mov     [rdi+90h], rax
0x180022aed  mov     rax, [rbp+57h+var_88]
0x180022af1  cmp     [rax], rcx
0x180022af4  jnz     loc_180022DF2
0x180022afa  mov     [rdi+8], rax
0x180022afe  lea     rcx, [rbp+57h+var_90]
0x180022b02  mov     [rdi], rcx
0x180022b05  mov     [rax], rdi
0x180022b08  mov     [rbp+57h+var_88], rdi
0x180022b0c  add     esi, ebx
0x180022b0e  jmp     loc_1800228CF
0x180022b13  mov     rcx, rdi; this
0x180022b16  call    ??_GLB_RESOURCE_ID_CONFIG_ENTRY@@QEAAPEAXI@Z; LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(uint)
0x180022b1b  mov     rcx, r12; Object
0x180022b1e  call    cs:__imp_I_RpcFree
0x180022b24  mov     rbx, [rbp+57h+var_90]
0x180022b28  lea     rax, [rbp+57h+var_90]
0x180022b2c  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180022b33  cmp     rbx, rax
0x180022b36  jz      loc_180022853
0x180022b3c  mov     rdi, rbx
0x180022b3f  mov     rbx, [rbx]
0x180022b42  test    rdi, rdi
0x180022b45  jz      short loc_180022B4F
0x180022b47  mov     rcx, rdi; this
0x180022b4a  call    ??_GLB_RESOURCE_ID_CONFIG_ENTRY@@QEAAPEAXI@Z; LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(uint)
0x180022b4f  lea     rax, [rbp+57h+var_90]
0x180022b53  cmp     rbx, rax
0x180022b56  jnz     short loc_180022B3C
0x180022b58  or      rsi, rsi
0x180022b5b  jmp     loc_180022853
0x180022b60  mov     rcx, rdi; this
0x180022b63  call    ??_GLB_RESOURCE_ID_CONFIG_ENTRY@@QEAAPEAXI@Z; LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(uint)
0x180022b68  jmp     loc_180022FA8
0x180022b6d  mov     r14d, ebx
0x180022b70  mov     ebx, 6BAh
0x180022b75  jmp     loc_180022FB0
0x180022b7a  mov     rcx, rdi; this
0x180022b7d  call    ??_GLB_RESOURCE_ID_CONFIG_ENTRY@@QEAAPEAXI@Z; LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(uint)
0x180022b82  mov     esi, 1
0x180022b87  jmp     loc_180022FA0
0x180022b8c  mov     rdi, r15
0x180022b8f  jmp     loc_180022FA8
0x180022b94  mov     rcx, r14; CriticalSection
0x180022b97  mov     dword ptr [rbp+57h+Strings], r15d
0x180022b9b  call    cs:__imp_RtlEnterCriticalSection
0x180022ba1  lea     rbx, [r14+30h]
0x180022ba5  mov     rcx, [rbx]
0x180022ba8  jmp     short loc_180022BB4
0x180022baa  lea     rax, [rcx]
0x180022bad  mov     rcx, [rcx]
0x180022bb0  mov     [rax+7Ch], r15d
0x180022bb4  cmp     rcx, rbx
0x180022bb7  jnz     short loc_180022BAA
0x180022bb9  mov     rsi, [rbp+57h+var_90]
0x180022bbd  lea     rax, [rbp+57h+var_90]
0x180022bc1  cmp     rsi, rax
0x180022bc4  jz      loc_180022CC6
0x180022bca  mov     rdi, [rbx]
0x180022bcd  mov     r13, [rsi]
0x180022bd0  cmp     rdi, rbx
0x180022bd3  jz      loc_180022CAC
0x180022bd9  cmp     dword ptr [rdi+78h], 0
0x180022bdd  mov     r15, [rdi]
0x180022be0  jnz     loc_180022CA0
0x180022be6  lea     rdx, [rsi+58h]; Buf2
0x180022bea  mov     r8d, 10h; Size
0x180022bf0  lea     rcx, [rdi+58h]; Buf1
0x180022bf4  call    memcmp_0
0x180022bf9  test    eax, eax
0x180022bfb  jnz     loc_180022CA0
0x180022c01  mov     eax, 1
0x180022c06  lea     rdx, [rsi+90h]; lpFileTime2
0x180022c0d  mov     [rdi+7Ch], eax
0x180022c10  lea     rcx, [rdi+90h]; lpFileTime1
0x180022c17  mov     [rsi+7Ch], eax
0x180022c1a  call    cs:__imp_CompareFileTime
0x180022c20  test    eax, eax
0x180022c22  jns     short loc_180022C98
0x180022c24  mov     rcx, rdi; this
0x180022c27  mov     dword ptr [rdi+78h], 1
0x180022c2e  call    ?RemoveLifetimeReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::RemoveLifetimeReference(void)
  ... truncated ...
```
