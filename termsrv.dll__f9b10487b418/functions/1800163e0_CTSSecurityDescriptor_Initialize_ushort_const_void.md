# CTSSecurityDescriptor::Initialize(ushort const *,void *)

- ea: `0x1800163e0`
- end: `0x180017601`
- name: `?Initialize@CTSSecurityDescriptor@@QEAAJPEBGPEAX@Z`
- size: `4641`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180016388`
- `0x180018bd0`
- `0x1800501dc`

## callees

- `0x1800052d0`
- `0x18000554c`
- `0x180006380`
- `0x18000a210`
- `0x180011a80`
- `0x180013e38`
- `0x1800163e0`
- `0x1800321d4`
- `0x1800321f0`
- `0x1800326dc`
- `0x180033058`
- `0x1800b9264`
- `0x1800b9370`
- `0x1800c4da0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b39`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b4d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b39`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b4d`
- `ntdll!RtlFreeSid` at `0x18001731a`
- `ntdll!RtlFreeSid` at `0x180017329`
- `ntdll!RtlFreeSid` at `0x18001731a`
- `ntdll!RtlFreeSid` at `0x180017329`
- `ntdll!RtlDeleteSecurityObject` at `0x1800175d0`
- `ntdll!RtlDeleteSecurityObject` at `0x1800175d0`
- `ntdll!RtlCreateUserSecurityObject` at `0x180017241`
- `ntdll!RtlCreateUserSecurityObject` at `0x180017241`
- `ntdll!RtlNtStatusToDosError` at `0x180017277`
- `ntdll!RtlNtStatusToDosError` at `0x1800172c1`
- `ntdll!RtlNtStatusToDosError` at `0x180017277`
- `ntdll!RtlNtStatusToDosError` at `0x1800172c1`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180017175`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800171cf`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180017175`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800171cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001727f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800172c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001727f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800172c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800172cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800172cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016798`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016914`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016d21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ea8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016798`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016914`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016d21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ea8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016adc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001706a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016adc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001706a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016645`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016bea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016645`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016bea`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016764`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016cf4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016764`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017338`

## string_xrefs

- `0x180017513`: `StringCchCopy failed: 0x%x in %s`
- `0x1800172ac`: `CUtil::CreateSystemSid failed: 0x%x in %s`
- `0x1800172f6`: `CUtil::CreateAdminSid failed: 0x%x in %s`
- `0x180016b06`: `SecurityDescriptor not found for this listener`
- `0x18001678a`: `Security`
- `0x180016b76`: `ConsoleSecurity`
- `0x180016bb5`: `ConsoleSecurity`
- `0x180016b57`: `DefaultSecurity`
- `0x180017094`: `SecurityDescriptor registry not found`
- `0x180016b81`: `Querying Console default security descriptor`
- `0x180017361`: `CreateDefault`
- `0x1800170c8`: `Creating default security descriptor in the registry and using it`
- `0x180017408`: `Using security descriptor for this listener`
- `0x1800173c8`: `Found security descriptor and using it.`
- `0x18001754d`: `CopySource failed: 0x%x in %s`
- `0x180017543`: `CTSSecurityDescriptor::Initialize`
- `0x180017571`: `CTSSecurityDescriptor::Initialize`
- `0x180016986`: `GetSDValueFromRegistry`
- `0x180016f1f`: `GetSDValueFromRegistry`
- `0x1800166b7`: `Failed to open key`
- `0x180016c48`: `Failed to open key`
- `0x180016a93`: `Invalid security descriptor in registry`
- `0x18001702a`: `Invalid security descriptor in registry`
- `0x18001681c`: `Registry entry not found`
- `0x180016db6`: `Registry entry not found`
- `0x180017114`: `CTSSecurityDescriptor::CreateDefault`
- `0x180017255`: `CTSSecurityDescriptor::CreateDefault`
- `0x1800172a2`: `CTSSecurityDescriptor::CreateDefault`
- `0x1800172ec`: `CTSSecurityDescriptor::CreateDefault`
- `0x18001711e`: `GetCurrentProcessSid failed: 0x%x in %s`
- `0x18001725f`: `RtlCreateUserSecurityObject failed: 0x%x in %s`
- `0x18001751a`: `CTSSecurityDescriptor::CopySource`
- `0x180016b43`: `Services`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::Initialize(CTSSecurityDescriptor *this, const unsigned __int16 *a2, void *a3)
{
  void *v3; // r14
  const unsigned __int16 *v4; // r15
  CTSSecurityDescriptor *v5; // r13
  unsigned __int16 *v6; // r12
  int v7; // edi
  __int64 v8; // rax
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  void *v13; // rsp
  int v14; // eax
  void *v15; // r13
  LSTATUS v16; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  signed int v19; // esi
  __int64 v20; // rax
  LSTATUS Value; // eax
  __int64 v22; // rcx
  __int64 v23; // rax
  LSTATUS v24; // eax
  __int64 v25; // rax
  HKEY v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  const WCHAR *v30; // r14
  BYTE *v31; // r13
  LSTATUS v32; // eax
  __int64 v33; // r8
  __int64 v34; // r9
  signed int v35; // esi
  LSTATUS v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rax
  LSTATUS v39; // eax
  __int64 v40; // rax
  HKEY v41; // rcx
  int CurrentProcessSid; // eax
  int v43; // esi
  int v44; // eax
  int v45; // eax
  NTSTATUS v46; // eax
  DWORD v47; // eax
  signed int LastError; // eax
  DWORD v49; // eax
  signed int v50; // eax
  __int64 v51; // rcx
  const unsigned __int16 *v52; // rax
  unsigned __int64 v53; // rsi
  unsigned __int64 v54; // rax
  __int64 v55; // rdx
  unsigned __int16 *v56; // rcx
  unsigned __int16 v57; // ax
  unsigned __int16 *v58; // rax
  int v59; // eax
  void *v60; // rcx
  WCHAR SubKey[4]; // [rsp+60h] [rbp+0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp+8h] BYREF
  PSID v64; // [rsp+78h] [rbp+18h] BYREF
  DWORD Type[2]; // [rsp+80h] [rbp+20h] BYREF
  DWORD cbData[2]; // [rsp+88h] [rbp+28h] BYREF
  void *Block; // [rsp+90h] [rbp+30h] BYREF
  CTSSecurityDescriptor *v68; // [rsp+98h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+A0h] [rbp+40h] BYREF
  __int16 AceData; // [rsp+A8h] [rbp+48h] BYREF
  char v71; // [rsp+AAh] [rbp+4Ah]
  int v72; // [rsp+ACh] [rbp+4Ch]
  WCHAR *v73; // [rsp+B0h] [rbp+50h]
  __int16 v74; // [rsp+B8h] [rbp+58h]
  char v75; // [rsp+BAh] [rbp+5Ah]
  int v76; // [rsp+BCh] [rbp+5Ch]
  PSID *v77; // [rsp+C0h] [rbp+60h]
  WCHAR *v78; // [rsp+C8h] [rbp+68h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority[2]; // [rsp+D0h] [rbp+70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp+80h] BYREF
  char *v81; // [rsp+F0h] [rbp+90h]
  int v82; // [rsp+F8h] [rbp+98h]
  int v83; // [rsp+FCh] [rbp+9Ch]
  const char *v84; // [rsp+100h] [rbp+A0h]
  __int64 v85; // [rsp+108h] [rbp+A8h]
  WCHAR *v86; // [rsp+110h] [rbp+B0h]
  __int64 v87; // [rsp+118h] [rbp+B8h]
  const wchar_t *v88; // [rsp+120h] [rbp+C0h]
  __int64 v89; // [rsp+128h] [rbp+C8h]
  _SID_IDENTIFIER_AUTHORITY *v90; // [rsp+130h] [rbp+D0h]
  __int64 v91; // [rsp+138h] [rbp+D8h]
  WCHAR *v92; // [rsp+140h] [rbp+E0h]
  __int64 v93; // [rsp+148h] [rbp+E8h]
  const WCHAR *v94; // [rsp+150h] [rbp+F0h]
  __int64 v95; // [rsp+158h] [rbp+F8h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  v68 = this;
  v64 = this;
  *(_QWORD *)Type = a2;
  v6 = 0;
  *(_QWORD *)SubKey = 0;
  ObjectDescriptor = 0;
  Block = 0;
  *(_QWORD *)IdentifierAuthority[0].Value = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    goto LABEL_165;
  }
  if ( a3 )
  {
    v7 = -2147024882;
    goto LABEL_134;
  }
  v8 = 33;
  v9 = a2;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v7 = -2147024809;
  if ( v8 )
  {
    v7 = 0;
    v10 = 2 * (33 - v8);
  }
  else
  {
    v10 = 0;
  }
  if ( !v8 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      *(_QWORD *)&EventDescriptor.Id = "Initialize";
      Type[0] = v7;
      v68 = (CTSSecurityDescriptor *)"StringCbLength";
      *(_QWORD *)SubKey = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)&dword_180128170,
        (__int64)&byte_180114DF7,
        0,
        0,
        (const unsigned __int16 **)SubKey,
        (const unsigned __int16 **)&v68,
        (__int64)Type,
        (const unsigned __int16 **)&EventDescriptor);
    }
    goto LABEL_164;
  }
  v11 = v10 + 126;
  *(_QWORD *)cbData = v11;
  *(_QWORD *)&EventDescriptor.Id = v11;
  v12 = v11 + 15;
  if ( v11 + 15 < v11 )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = alloca(v12 & 0xFFFFFFFFFFFFFFF0uLL);
  v78 = SubKey;
  if ( SubKey )
  {
    v14 = StringCbPrintfW(
            SubKey,
            v11,
            L"%s\\%s",
            L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
            v4);
    v7 = v14;
    if ( v14 < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        *(_QWORD *)&EventDescriptor.Id = "Initialize";
        Type[0] = v14;
        v68 = (CTSSecurityDescriptor *)"StringCbPrintf";
        *(_QWORD *)SubKey = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)&dword_180128170,
          (__int64)byte_180114E69,
          0,
          0,
          (const unsigned __int16 **)SubKey,
          (const unsigned __int16 **)&v68,
          (__int64)Type,
          (const unsigned __int16 **)&EventDescriptor);
      }
      goto LABEL_164;
    }
    *(_QWORD *)SubKey = 0;
    v15 = 0;
    v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)SubKey);
    v19 = v16;
    if ( v16 > 0 )
      v19 = (unsigned __int16)v16 | 0x80070000;
    if ( v19 >= 0 )
    {
      Type[0] = 0;
      cbData[0] = 0;
      Value = RegQueryValueExW(*(HKEY *)SubKey, L"Security", 0, Type, 0, cbData);
      v19 = Value;
      if ( Value > 0 )
        v19 = (unsigned __int16)Value | 0x80070000;
      if ( v19 >= 0 )
      {
        if ( Type[0] == 3 && (v22 = cbData[0], cbData[0] - 40 <= 0xFFD7) )
        {
          v15 = operator new(cbData[0], (const struct std::nothrow_t *)std::nothrow);
          if ( !v15 )
          {
            v7 = -2147024882;
            v19 = -2147024882;
LABEL_50:
            v3 = Block;
LABEL_51:
            v26 = *(HKEY *)SubKey;
            if ( *(_QWORD *)SubKey )
              RegCloseKey(*(HKEY *)SubKey);
            if ( v15 )
              operator delete(v15);
            if ( v19 >= 0 )
            {
              if ( (unsigned int)dword_180128170 > 5 )
              {
                *(_QWORD *)&EventDescriptor.Id = v4;
                *(_QWORD *)SubKey = "Using security descriptor for this listener";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                  (__int64)v26,
                  (__int64)byte_180114EAB,
                  v17,
                  v18,
                  (const unsigned __int16 **)SubKey,
                  (const unsigned __int16 **)&EventDescriptor);
              }
              v5 = v68;
              goto LABEL_134;
            }
            if ( (unsigned int)dword_180128170 > 5 )
            {
              *(_QWORD *)&EventDescriptor.Id = v4;
              *(_QWORD *)SubKey = "SecurityDescriptor not found for this listener";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                (__int64)v26,
                (__int64)byte_180114D8D,
                v17,
                v18,
                (const unsigned __int16 **)SubKey,
                (const unsigned __int16 **)&EventDescriptor);
            }
            if ( (unsigned int)_o__wcsicmp(v4, L"Console") && (unsigned int)_o__wcsicmp(v4, L"Services") )
            {
              v30 = L"DefaultSecurity";
            }
            else if ( (unsigned int)dword_180128170 <= 5 )
            {
              v30 = L"ConsoleSecurity";
            }
            else
            {
              *(_QWORD *)&EventDescriptor.Id = L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations";
              v30 = L"ConsoleSecurity";
              *(_QWORD *)SubKey = L"ConsoleSecurity";
              Block = "Querying Console default security descriptor";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                v27,
                (__int64)&byte_180114DBF,
                v28,
                v29,
                (const unsigned __int16 **)&Block,
                (const unsigned __int16 **)SubKey,
                (const unsigned __int16 **)&EventDescriptor);
            }
            *(_QWORD *)SubKey = 0;
            v31 = 0;
            Block = 0;
            v32 = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
                    0,
                    0x20019u,
                    (PHKEY)SubKey);
            v35 = v32;
            if ( v32 > 0 )
              v35 = (unsigned __int16)v32 | 0x80070000;
            if ( v35 >= 0 )
            {
              cbData[0] = 0;
              Type[0] = 0;
              v36 = RegQueryValueExW(*(HKEY *)SubKey, v30, 0, cbData, 0, Type);
              v35 = v36;
              if ( v36 > 0 )
                v35 = (unsigned __int16)v36 | 0x80070000;
              if ( v35 >= 0 )
              {
                if ( cbData[0] == 3 && (v37 = Type[0], Type[0] - 40 <= 0xFFD7) )
                {
                  v31 = (BYTE *)operator new(Type[0], (const struct std::nothrow_t *)std::nothrow);
                  if ( v31 )
                  {
                    v39 = RegQueryValueExW(*(HKEY *)SubKey, v30, 0, cbData, v31, Type);
                    v35 = v39;
                    if ( v39 > 0 )
                      v35 = (unsigned __int16)v39 | 0x80070000;
                    if ( v35 >= 0 )
                    {
                      Block = v31;
                      v31 = 0;
                    }
                    else if ( (unsigned int)dword_180128170 > 3 )
                    {
                      *(_DWORD *)IdentifierAuthority[0].Value = v35;
                      v40 = -1;
                      do
                        ++v40;
                      while ( v30[v40] );
                      v94 = v30;
                      v95 = (unsigned int)(2 * v40 + 2);
                      v92 = (WCHAR *)L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations";
                      v93 = 122;
                      v90 = (_SID_IDENTIFIER_AUTHORITY *)"GetSDValueFromRegistry";
                      v91 = 23;
                      v88 = (const wchar_t *)IdentifierAuthority;
                      v89 = 4;
                      v86 = (WCHAR *)"RegQueryValueEx failed after we queried it the 2nd time";
                      v87 = 56;
                      v84 = "Warning HResult failed";
                      v85 = 23;
                      *(_DWORD *)&EventDescriptor.Id = 184549376;
                      *(_DWORD *)&EventDescriptor.Level = 3;
                      EventDescriptor.Keyword = 0;
                      UserData.Ptr = (ULONGLONG)off_180128178;
                      UserData.Size = *(unsigned __int16 *)off_180128178;
                      UserData.Reserved = 2;
                      v81 = &byte_180114F8F;
                      v82 = 70;
                      v83 = 1;
                      LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
                    }
                  }
                  else
                  {
                    v35 = -2147024882;
                  }
                }
                else
                {
                  if ( (unsigned int)dword_180128170 > 2 )
                  {
                    *(_QWORD *)&EventDescriptor.Id = v30;
                    *(_QWORD *)IdentifierAuthority[0].Value = L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations";
                    v64 = "Invalid security descriptor in registry";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                      v37,
                      (__int64)byte_180114D55,
                      v33,
                      v34,
                      (const unsigned __int16 **)&v64,
                      (const unsigned __int16 **)IdentifierAuthority,
                      (const unsigned __int16 **)&EventDescriptor);
                  }
                  v35 = -2147023558;
                }
              }
              else if ( (unsigned int)dword_180128170 > 5 )
              {
                *(_DWORD *)IdentifierAuthority[0].Value = v35;
                v90 = IdentifierAuthority;
                v91 = 4;
                v88 = L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations";
                v89 = 122;
                v38 = -1;
                do
                  ++v38;
                while ( v30[v38] );
                v86 = (WCHAR *)v30;
                v87 = (unsigned int)(2 * v38 + 2);
                v84 = "Registry entry not found";
                v85 = 25;
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                *(_DWORD *)&EventDescriptor.Level = 5;
                EventDescriptor.Keyword = 0;
                UserData.Ptr = (ULONGLONG)off_180128178;
                UserData.Size = *(unsigned __int16 *)off_180128178;
                UserData.Reserved = 2;
                v81 = (char *)word_180114F2A;
                v82 = 49;
                v83 = 1;
                LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
              }
            }
            else if ( (unsigned int)dword_180128170 > 3 )
            {
              *(_DWORD *)IdentifierAuthority[0].Value = v35;
              v88 = (const wchar_t *)IdentifierAuthority;
              v89 = 4;
              v86 = (WCHAR *)L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations";
              v87 = 122;
              v84 = "Failed to open key";
              v85 = 19;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              *(_DWORD *)&EventDescriptor.Level = 3;
              EventDescriptor.Keyword = 0;
              UserData.Ptr = (ULONGLONG)off_180128178;
              UserData.Size = *(unsigned __int16 *)off_180128178;
              UserData.Reserved = 2;
              v81 = byte_180114D03;
              v82 = 41;
              v83 = 1;
              LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
            }
            v41 = *(HKEY *)SubKey;
            if ( *(_QWORD *)SubKey )
              RegCloseKey(*(HKEY *)SubKey);
            if ( v31 )
              operator delete(v31);
            if ( v35 >= 0 )
            {
              if ( (unsigned int)dword_180128170 > 5 )
              {
                *(_QWORD *)&EventDescriptor.Id = "Found security descriptor and using it.";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (__int64)&dword_180128170,
                  (unsigned __int8 *)&dword_180114F5C,
                  0,
                  0,
                  (const unsigned __int16 **)&EventDescriptor);
              }
              v3 = Block;
              v5 = v68;
              goto LABEL_134;
            }
            if ( (unsigned int)dword_180128170 > 5 )
            {
              *(_QWORD *)&EventDescriptor.Id = v30;
              *(_QWORD *)SubKey = "SecurityDescriptor registry not found";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                (__int64)v41,
                (__int64)byte_180114E39,
                v33,
                v34,
                (const unsigned __int16 **)SubKey,
                (const unsigned __int16 **)&EventDescriptor);
            }
            if ( (unsigned int)dword_180128170 > 5 )
            {
              *(_QWORD *)&EventDescriptor.Id = "Creating default security descriptor in the registry and using it";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                (__int64)&dword_180128170,
                (unsigned __int8 *)byte_180114D2D,
                0,
                0,
                (const unsigned __int16 **)&EventDescriptor);
            }
            *(_QWORD *)&EventDescriptor.Id = 0;
            *(_QWORD *)Type = 0;
            *(_QWORD *)SubKey = 0;
            v64 = 0;
            CurrentProcessSid = CTSSecurityDescriptor::GetCurrentProcessSid((CTSSecurityDescriptor *)v41, (void **)Type);
            v43 = CurrentProcessSid;
            if ( CurrentProcessSid < 0 )
            {
              _DbgPrintMessage(
                8,
                "GetCurrentProcessSid failed: 0x%x in %s",
                CurrentProcessSid,
                "CTSSecurityDescriptor::CreateDefault");
LABEL_117:
              if ( *(_QWORD *)SubKey )
                RtlFreeSid(*(PSID *)SubKey);
              if ( v64 )
                RtlFreeSid(v64);
              if ( *(_QWORD *)Type )
                CoTaskMemFree(*(LPVOID *)Type);
              if ( v43 < 0 )
              {
                v7 = v43;
                if ( (unsigned int)dword_180128170 > 3 )
                {
                  *(_QWORD *)&EventDescriptor.Id = "Initialize";
                  *(_DWORD *)IdentifierAuthority[0].Value = v43;
                  v68 = (CTSSecurityDescriptor *)"CreateDefault";
                  *(_QWORD *)SubKey = "Warning HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    (__int64)&dword_180128170,
                    (__int64)byte_180114EDD,
                    0,
                    0,
                    (const unsigned __int16 **)SubKey,
                    (const unsigned __int16 **)&v68,
                    (__int64)IdentifierAuthority,
                    (const unsigned __int16 **)&EventDescriptor);
                }
                goto LABEL_164;
              }
              v3 = ObjectDescriptor;
              v5 = v68;
LABEL_134:
              v51 = 0x7FFFFFFF;
              v52 = v4;
              do
              {
                if ( !*v52 )
                  break;
                ++v52;
                --v51;
              }
              while ( v51 );
              if ( v51 )
              {
                v53 = 0x7FFFFFFF - v51 + 1;
                v54 = 2 * v53;
                if ( !is_mul_ok(v53, 2u) )
                  v54 = -1;
                v6 = (unsigned __int16 *)operator new(v54, (const struct std::nothrow_t *)std::nothrow);
                if ( v6 )
                {
                  v55 = 2147483646;
                  if ( v53 - 1 > 0x7FFFFFFE )
                  {
                    v7 = -2147024809;
                    if ( v53 )
                      *v6 = 0;
                  }
                  else
                  {
                    v56 = v6;
                    do
                    {
                      if ( !v55 )
                        break;
                      v57 = *v4;
                      if ( !*v4 )
                        break;
                      ++v4;
                      *v56++ = v57;
                      --v55;
                      --v53;
                    }
                    while ( v53 );
                    v58 = v56 - 1;
                    if ( v53 )
                      v58 = v56;
                    *v58 = 0;
                    v7 = -2147024774;
                    if ( v53 )
                      v7 = 0;
                  }
                  if ( v7 >= 0 )
                  {
                    v59 = CTSSecurityDescriptor::InitializeFromBlob(v5, v3);
                    v7 = v59;
                    if ( v59 >= 0 )
                    {
                      v60 = (void *)*((_QWORD *)v5 + 2);
                      if ( v60 )
                        operator delete(v60);
                      *((_QWORD *)v5 + 2) = v6;
                      v6 = 0;
                    }
                    else
                    {
                      _DbgPrintMessage(
                        8,
                        "InitializeFromBlob failed: 0x%x in %s",
                        v59,
                        "CTSSecurityDescriptor::Initialize");
                    }
LABEL_164:
                    if ( v7 >= 0 )
                      goto LABEL_167;
                    goto LABEL_165;
                  }
                  _DbgPrintMessage(
                    8,
                    "StringCchCopy failed: 0x%x in %s",
                    (unsigned int)v7,
                    "CTSSecurityDescriptor::CopySource");
                }
              }
              else
              {
                v7 = -2147024809;
                _DbgPrintMessage(
                  8,
                  "StringCchLength failed: 0x%x in %s",
                  2147942487LL,
                  "CTSSecurityDescriptor::CopySource");
              }
              if ( v6 )
              {
                operator delete(v6);
                v6 = 0;
              }
              _DbgPrintMessage(8, "CopySource failed: 0x%x in %s", v7, "CTSSecurityDescriptor::Initialize");
              goto LABEL_164;
            }
            *(_QWORD *)cbData = 0;
            *(_DWORD *)IdentifierAuthority[0].Value = 0;
            *(_WORD *)&IdentifierAuthority[0].Value[4] = 1280;
            v44 = RtlAllocateAndInitializeSid(IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, (PSID *)cbData);
            if ( v44 < 0 )
            {
              v47 = RtlNtStatusToDosError(v44);
              SetLastError(v47);
              LastError = GetLastError();
              v43 = LastError;
              if ( LastError > 0 )
                v43 = (unsigned __int16)LastError | 0x80070000;
              if ( v43 < 0 )
              {
                _DbgPrintMessage(
                  8,
                  "CUtil::CreateSystemSid failed: 0x%x in %s",
                  v43,
                  "CTSSecurityDescriptor::CreateDefault");
                goto LABEL_117;
              }
            }
            else
            {
              *(_QWORD *)SubKey = *(_QWORD *)cbData;
            }
            *(_QWORD *)cbData = 0;
            *(_DWORD *)IdentifierAuthority[0].Value = 0;
            *(_WORD *)&IdentifierAuthority[0].Value[4] = 1280;
            v45 = RtlAllocateAndInitializeSid(IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, (PSID *)cbData);
            if ( v45 < 0 )
            {
              v49 = RtlNtStatusToDosError(v45);
              SetLastError(v49);
              v50 = GetLastError();
              v43 = v50;
              if ( v50 > 0 )
                v43 = (unsigned __int16)v50 | 0x80070000;
              if ( v43 < 0 )
              {
                _DbgPrintMessage(
                  8,
                  "CUtil::CreateAdminSid failed: 0x%x in %s",
                  v43,
                  "CTSSecurityDescriptor::CreateDefault");
                goto LABEL_117;
              }
            }
            else
            {
              v64 = *(PSID *)cbData;
            }
            AceData = 0;
            v71 = 0;
            v72 = 983999;
            v73 = SubKey;
            v74 = 0;
            v75 = 0;
            v76 = 983999;
            v77 = &v64;
            v46 = RtlCreateUserSecurityObject(
                    &AceData,
                    2u,
                    *(PSID *)Type,
                    *(PSID *)Type,
                    0,
                    (PGENERIC_MAPPING)&GenericMapping,
                    (PSECURITY_DESCRIPTOR *)&EventDescriptor);
            v43 = v46 | 0x10000000;
            if ( v46 >= 0 )
              ObjectDescriptor = *(PSECURITY_DESCRIPTOR *)&EventDescriptor.Id;
            else
              _DbgPrintMessage(
                8,
                "RtlCreateUserSecurityObject failed: 0x%x in %s",
                v43,
                "CTSSecurityDescriptor::CreateDefault");
            goto LABEL_117;
          }
          v24 = RegQueryValueExW(*(HKEY *)SubKey, L"Security", 0, Type, (LPBYTE)v15, cbData);
          v19 = v24;
          if ( v24 > 0 )
            v19 = (unsigned __int16)v24 | 0x80070000;
          if ( v19 >= 0 )
          {
            v3 = v15;
            Block = v15;
            v15 = 0;
            v7 = -2147024882;
            goto LABEL_51;
          }
          if ( (unsigned int)dword_180128170 > 3 )
          {
            *(_DWORD *)IdentifierAuthority[0].Value = v19;
            v94 = L"Security";
            v95 = 18;
            v25 = -1;
            do
              ++v25;
            while ( SubKey[v25] );
            v92 = SubKey;
            v93 = (unsigned int)(2 * v25 + 2);
            v90 = (_SID_IDENTIFIER_AUTHORITY *)"GetSDValueFromRegistry";
            v91 = 23;
            v88 = (const wchar_t *)IdentifierAuthority;
            v89 = 4;
            v86 = (WCHAR *)"RegQueryValueEx failed after we queried it the 2nd time";
            v87 = 56;
            v84 = "Warning HResult failed";
            v85 = 23;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            *(_DWORD *)&EventDescriptor.Level = 3;
            EventDescriptor.Keyword = 0;
            UserData.Ptr = (ULONGLONG)off_180128178;
            UserData.Size = *(unsigned __int16 *)off_180128178;
            UserData.Reserved = 2;
            v81 = &byte_180114F8F;
            v82 = 70;
            v83 = 1;
            LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
          }
        }
        else
        {
          if ( (unsigned int)dword_180128170 > 2 )
          {
            *(_QWORD *)&EventDescriptor.Id = L"Security";
            *(_QWORD *)IdentifierAuthority[0].Value = SubKey;
            v64 = "Invalid security descriptor in registry";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v22,
              (__int64)byte_180114D55,
              v17,
              v18,
              (const unsigned __int16 **)&v64,
              (const unsigned __int16 **)IdentifierAuthority,
              (const unsigned __int16 **)&EventDescriptor);
          }
          v19 = -2147023558;
        }
      }
      else if ( (unsigned int)dword_180128170 > 5 )
      {
        *(_DWORD *)IdentifierAuthority[0].Value = v19;
        v90 = IdentifierAuthority;
        v91 = 4;
        v23 = -1;
        do
          ++v23;
        while ( SubKey[v23] );
        v88 = SubKey;
        v89 = (unsigned int)(2 * v23 + 2);
        v86 = (WCHAR *)L"Security";
        v87 = 18;
        v84 = "Registry entry not found";
        v85 = 25;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 5;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_180128178;
        UserData.Size = *(unsigned __int16 *)off_180128178;
        UserData.Reserved = 2;
        v81 = (char *)word_180114F2A;
        v82 = 49;
        v83 = 1;
        LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
      }
    }
    else if ( (unsigned int)dword_180128170 > 3 )
    {
      LODWORD(v64) = v19;
      v88 = (const wchar_t *)&v64;
      v89 = 4;
      v20 = -1;
      do
        ++v20;
      while ( SubKey[v20] );
      v86 = SubKey;
      v87 = (unsigned int)(2 * v20 + 2);
      v84 = "Failed to open key";
      v85 = 19;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 3;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180128178;
      UserData.Size = *(unsigned __int16 *)off_180128178;
      UserData.Reserved = 2;
      v81 = byte_180114D03;
      v82 = 41;
      v83 = 1;
      *(_DWORD *)IdentifierAuthority[0].Value = (unsigned int)&TraceLoggingMetadataEnd
                                              - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
    v7 = -2147024882;
    goto LABEL_50;
  }
  v7 = -2147024882;
LABEL_165:
  if ( v6 )
    operator delete(v6);
LABEL_167:
  if ( Block )
    operator delete(Block);
  if ( ObjectDescriptor )
    RtlDeleteSecurityObject(&ObjectDescriptor);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800163e0  push    rbp
0x1800163e2  push    rsi
0x1800163e3  push    rdi
0x1800163e4  push    r12
0x1800163e6  push    r13
0x1800163e8  push    r14
0x1800163ea  push    r15
0x1800163ec  sub     rsp, 170h
0x1800163f3  lea     rbp, [rsp+60h]
0x1800163f8  mov     [rbp+140h+arg_18], rbx
0x1800163ff  mov     rax, cs:__security_cookie
0x180016406  xor     rax, rbp
0x180016409  mov     [rbp+140h+var_40], rax
0x180016410  mov     r14, r8
0x180016413  mov     r15, rdx
0x180016416  mov     r13, rcx
0x180016419  mov     [rbp+140h+var_108], rcx
0x18001641d  mov     [rbp+140h+var_128], rcx
0x180016421  mov     qword ptr [rbp+140h+Type], rdx
0x180016425  xor     ebx, ebx
0x180016427  mov     r12d, ebx
0x18001642a  mov     qword ptr [rbp+140h+SubKey], rbx
0x18001642e  mov     [rbp+140h+ObjectDescriptor], rbx
0x180016432  mov     [rbp+140h+Block], rbx
0x180016436  mov     qword ptr [rbp+140h+IdentifierAuthority.Value], rbx
0x18001643a  test    rdx, rdx
0x18001643d  jnz     short loc_180016449
0x18001643f  mov     edi, 80070057h
0x180016444  jmp     loc_1800175A7
0x180016449  test    r8, r8
0x18001644c  jnz     loc_180017437
0x180016452  mov     edx, 21h ; '!'
0x180016457  mov     eax, edx
0x180016459  mov     rcx, r15
0x18001645c  nop     dword ptr [rax+00h]
0x180016460  cmp     [rcx], bx
0x180016463  jz      short loc_18001646F
0x180016465  add     rcx, 2
0x180016469  sub     rax, 1
0x18001646d  jnz     short loc_180016460
0x18001646f  mov     edi, 80070057h
0x180016474  test    rax, rax
0x180016477  cmovnz  edi, ebx
0x18001647a  sub     rdx, rax
0x18001647d  test    rax, rax
0x180016480  cmovz   rdx, rbx
0x180016484  jz      short loc_18001648B
0x180016486  add     rdx, rdx
0x180016489  jmp     short loc_18001648E
0x18001648b  mov     rdx, rbx
0x18001648e  test    rax, rax
0x180016491  jnz     short loc_180016508
0x180016493  mov     eax, cs:dword_180128170
0x180016499  cmp     eax, 3
0x18001649c  jbe     loc_1800175A3
0x1800164a2  lea     rax, aInitialize; "Initialize"
0x1800164a9  mov     qword ptr [rbp+140h+EventDescriptor.Id], rax
0x1800164ad  mov     [rbp+140h+Type], edi
0x1800164b0  lea     rax, aStringcblength_0; "StringCbLength"
0x1800164b7  mov     [rbp+140h+var_108], rax
0x1800164bb  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800164c2  mov     qword ptr [rbp+140h+SubKey], rax
0x1800164c6  lea     rax, [rbp+140h+EventDescriptor]
0x1800164ca  mov     qword ptr [rsp+1A0h+SubAuthority5], rax
0x1800164cf  lea     rax, [rbp+140h+Type]
0x1800164d3  mov     qword ptr [rsp+1A0h+SubAuthority4], rax
0x1800164d8  lea     rax, [rbp+140h+var_108]
0x1800164dc  mov     [rsp+1A0h+UserData], rax
0x1800164e1  lea     rax, [rbp+140h+SubKey]
0x1800164e5  mov     [rsp+1A0h+phkResult], rax
0x1800164ea  xor     r9d, r9d
0x1800164ed  xor     r8d, r8d
0x1800164f0  lea     rdx, byte_180114DF7
0x1800164f7  lea     rcx, dword_180128170
0x1800164fe  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180016503  jmp     loc_1800175A3
0x180016508  add     rdx, 7Eh ; '~'
0x18001650c  mov     qword ptr [rbp+140h+cbData], rdx
0x180016510  mov     qword ptr [rbp+140h+EventDescriptor.Id], rdx
0x180016514  lea     rax, [rdx+0Fh]
0x180016518  cmp     rax, rdx
0x18001651b  ja      short loc_180016527
0x18001651d  mov     rax, 0FFFFFFFFFFFFFF0h
0x180016527  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001652b  call    _alloca_probe
0x180016530  sub     rsp, rax
0x180016533  lea     r14, [rsp+1A0h+SubKey]
0x180016538  mov     [rbp+140h+var_D8], r14
0x18001653c  jmp     short loc_18001657D
0x18001653e  call    _o__resetstkoflw_0
0x180016543  xor     r14d, r14d
0x180016546  mov     [rbp+140h+var_D8], r14
0x18001654a  mov     r8, qword ptr [rbp+140h+EventDescriptor.Id]
0x18001654e  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x180016555  mov     ecx, 8; int
0x18001655a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001655f  xor     ebx, ebx
0x180016561  mov     r12, qword ptr [rbp+140h+SubKey]
0x180016565  mov     rax, qword ptr [rbp+140h+IdentifierAuthority.Value]
0x180016569  mov     [rbp+140h+Block], rax
0x18001656d  mov     rcx, [rbp+140h+var_128]
0x180016571  mov     [rbp+140h+var_108], rcx
0x180016575  mov     r15, qword ptr [rbp+140h+Type]
0x180016579  mov     rdx, qword ptr [rbp+140h+cbData]; unsigned __int64
0x18001657d  test    r14, r14
0x180016580  jnz     short loc_18001658C
0x180016582  mov     edi, 8007000Eh
0x180016587  jmp     loc_1800175A7
0x18001658c  mov     [rsp+1A0h+phkResult], r15
0x180016591  lea     r9, aSystemCurrentc_10; "System\\CurrentControlSet\\Control\\Ter"...
0x180016598  lea     r8, aSS_0; "%s\\%s"
0x18001659f  mov     rcx, r14; unsigned __int16 *
0x1800165a2  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800165a7  mov     edi, eax
0x1800165a9  test    eax, eax
0x1800165ab  jns     short loc_180016622
0x1800165ad  mov     ecx, cs:dword_180128170
0x1800165b3  cmp     ecx, 3
0x1800165b6  jbe     loc_1800175A3
0x1800165bc  lea     rax, aInitialize; "Initialize"
0x1800165c3  mov     qword ptr [rbp+140h+EventDescriptor.Id], rax
0x1800165c7  mov     [rbp+140h+Type], edi
0x1800165ca  lea     rax, aStringcbprintf_0; "StringCbPrintf"
0x1800165d1  mov     [rbp+140h+var_108], rax
0x1800165d5  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800165dc  mov     qword ptr [rbp+140h+SubKey], rax
0x1800165e0  lea     rax, [rbp+140h+EventDescriptor]
0x1800165e4  mov     qword ptr [rsp+1A0h+SubAuthority5], rax
0x1800165e9  lea     rax, [rbp+140h+Type]
0x1800165ed  mov     qword ptr [rsp+1A0h+SubAuthority4], rax
0x1800165f2  lea     rax, [rbp+140h+var_108]
0x1800165f6  mov     [rsp+1A0h+UserData], rax
0x1800165fb  lea     rax, [rbp+140h+SubKey]
0x1800165ff  mov     [rsp+1A0h+phkResult], rax
0x180016604  xor     r9d, r9d
0x180016607  xor     r8d, r8d
0x18001660a  lea     rdx, byte_180114E69
0x180016611  lea     rcx, dword_180128170
0x180016618  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001661d  jmp     loc_1800175A3
0x180016622  mov     qword ptr [rbp+140h+SubKey], rbx
0x180016626  mov     r13, rbx
0x180016629  lea     rax, [rbp+140h+SubKey]
0x18001662d  mov     [rsp+1A0h+phkResult], rax; phkResult
0x180016632  mov     r9d, 20019h; samDesired
0x180016638  xor     r8d, r8d; ulOptions
0x18001663b  mov     rdx, r14; lpSubKey
0x18001663e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016645  call    cs:__imp_RegOpenKeyExW
0x18001664b  mov     esi, eax
0x18001664d  test    eax, eax
0x18001664f  jle     short loc_18001665A
0x180016651  movzx   esi, ax
0x180016654  or      esi, 80070000h
0x18001665a  test    esi, esi
0x18001665c  jns     loc_18001676F
0x180016662  mov     eax, cs:dword_180128170
0x180016668  cmp     eax, 3
0x18001666b  jbe     loc_180016ACA
0x180016671  mov     dword ptr [rbp+140h+var_128], esi
0x180016674  lea     rax, [rbp+140h+var_128]
0x180016678  mov     [rbp+140h+var_80], rax
0x18001667f  mov     [rbp+140h+var_78], 4
0x18001668a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016691  lea     rax, [rax+1]
0x180016695  cmp     word ptr [r14+rax*2], 0
0x18001669b  jnz     short loc_180016691
0x18001669d  mov     [rbp+140h+var_90], r14
0x1800166a4  lea     eax, ds:2[rax*2]
0x1800166ab  mov     dword ptr [rbp+140h+var_88], eax
0x1800166b1  mov     dword ptr [rbp+140h+var_88+4], ebx
0x1800166b7  lea     r14, aFailedToOpenKe; "Failed to open key"
0x1800166be  mov     [rbp+140h+var_A0], r14
0x1800166c5  mov     [rbp+140h+var_98], 13h
0x1800166d0  mov     dword ptr [rbp+140h+EventDescriptor.Id], 0B000000h
0x1800166d7  movzx   eax, cs:word_180114CF9
0x1800166de  mov     dword ptr [rbp+140h+EventDescriptor.Level], eax
0x1800166e1  mov     [rbp+140h+EventDescriptor.Keyword], rbx
0x1800166e5  mov     rax, cs:off_180128178
0x1800166ec  mov     [rbp+140h+var_C0.Ptr], rax
0x1800166f3  movzx   eax, word ptr [rax]
0x1800166f6  mov     [rbp+140h+var_C0.Size], eax
0x1800166fc  mov     dword ptr [rbp+140h+var_C0.0Ch], 2
0x180016706  lea     r14, byte_180114D03
0x18001670d  mov     [rbp+140h+var_B0], r14
0x180016714  mov     [rbp+140h+var_A8], 29h ; ')'
0x18001671e  mov     [rbp+140h+var_A4], 1
0x180016728  lea     rax, _TraceLoggingMetadataEnd
0x18001672f  lea     r14, _TraceLoggingMetadata
0x180016736  sub     eax, r14d
0x180016739  mov     dword ptr [rbp+140h+IdentifierAuthority.Value], eax
0x18001673c  mov     eax, dword ptr [rbp+140h+IdentifierAuthority.Value]
0x18001673f  lea     rax, [rbp+140h+var_C0]
0x180016746  mov     [rsp+1A0h+UserData], rax; UserData
0x18001674b  mov     dword ptr [rsp+1A0h+phkResult], 5; UserDataCount
0x180016753  xor     r9d, r9d; RelatedActivityId
0x180016756  xor     r8d, r8d; ActivityId
0x180016759  lea     rdx, [rbp+140h+EventDescriptor]; EventDescriptor
0x18001675d  mov     rcx, cs:RegHandle; RegHandle
0x180016764  call    cs:__imp_EventWriteTransfer
0x18001676a  jmp     loc_180016ACA
0x18001676f  mov     [rbp+140h+Type], ebx
0x180016772  mov     [rbp+140h+cbData], ebx
0x180016775  lea     rax, [rbp+140h+cbData]
0x180016779  mov     [rsp+1A0h+UserData], rax; lpcbData
0x18001677e  mov     [rsp+1A0h+phkResult], rbx; lpData
0x180016783  lea     r9, [rbp+140h+Type]; lpType
0x180016787  xor     r8d, r8d; lpReserved
0x18001678a  lea     rdi, ValueName; "Security"
0x180016791  mov     rdx, rdi; lpValueName
0x180016794  mov     rcx, qword ptr [rbp+140h+SubKey]; hKey
0x180016798  call    cs:__imp_RegQueryValueExW
0x18001679e  mov     esi, eax
0x1800167a0  test    eax, eax
0x1800167a2  jle     short loc_1800167AD
0x1800167a4  movzx   esi, ax
0x1800167a7  or      esi, 80070000h
0x1800167ad  test    esi, esi
0x1800167af  jns     loc_1800168BD
0x1800167b5  mov     eax, cs:dword_180128170
0x1800167bb  cmp     eax, 5
0x1800167be  jbe     loc_180016ACA
0x1800167c4  mov     dword ptr [rbp+140h+IdentifierAuthority.Value], esi
0x1800167c7  lea     rax, [rbp+140h+IdentifierAuthority]
0x1800167cb  mov     [rbp+140h+var_70], rax
0x1800167d2  mov     [rbp+140h+var_68], 4
0x1800167dd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800167e4  lea     rax, [rax+1]
0x1800167e8  cmp     word ptr [r14+rax*2], 0
0x1800167ee  jnz     short loc_1800167E4
0x1800167f0  mov     [rbp+140h+var_80], r14
0x1800167f7  lea     eax, ds:2[rax*2]
0x1800167fe  mov     dword ptr [rbp+140h+var_78], eax
0x180016804  mov     dword ptr [rbp+140h+var_78+4], ebx
0x18001680a  mov     [rbp+140h+var_90], rdi
0x180016811  mov     [rbp+140h+var_88], 12h
0x18001681c  lea     r14, aRegistryEntryN; "Registry entry not found"
0x180016823  mov     [rbp+140h+var_A0], r14
0x18001682a  mov     [rbp+140h+var_98], 19h
0x180016835  mov     dword ptr [rbp+140h+EventDescriptor.Id], 0B000000h
0x18001683c  movzx   eax, cs:word_180114F20
0x180016843  mov     dword ptr [rbp+140h+EventDescriptor.Level], eax
0x180016846  mov     [rbp+140h+EventDescriptor.Keyword], rbx
0x18001684a  mov     rax, cs:off_180128178
0x180016851  mov     [rbp+140h+var_C0.Ptr], rax
0x180016858  movzx   eax, word ptr [rax]
0x18001685b  mov     [rbp+140h+var_C0.Size], eax
0x180016861  mov     dword ptr [rbp+140h+var_C0.0Ch], 2
0x18001686b  lea     r14, word_180114F2A
0x180016872  mov     [rbp+140h+var_B0], r14
0x180016879  mov     [rbp+140h+var_A8], 31h ; '1'
0x180016883  mov     [rbp+140h+var_A4], 1
0x18001688d  lea     rax, _TraceLoggingMetadataEnd
0x180016894  lea     r14, _TraceLoggingMetadata
0x18001689b  sub     eax, r14d
0x18001689e  mov     dword ptr [rbp+140h+var_128], eax
0x1800168a1  mov     eax, dword ptr [rbp+140h+var_128]
0x1800168a4  lea     rax, [rbp+140h+var_C0]
0x1800168ab  mov     [rsp+1A0h+UserData], rax
0x1800168b0  mov     dword ptr [rsp+1A0h+phkResult], 6
0x1800168b8  jmp     loc_180016753
0x1800168bd  cmp     [rbp+140h+Type], 3
0x1800168c1  jnz     loc_180016A80
0x1800168c7  mov     ecx, [rbp+140h+cbData]; unsigned __int64
0x1800168ca  lea     eax, [rcx-28h]
0x1800168cd  cmp     eax, 0FFD7h
0x1800168d2  ja      loc_180016A80
0x1800168d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800168df  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800168e4  mov     r13, rax
0x1800168e7  test    rax, rax
0x1800168ea  jnz     short loc_1800168F8
0x1800168ec  mov     edi, 8007000Eh
0x1800168f1  mov     esi, edi
0x1800168f3  jmp     loc_180016ACF
0x1800168f8  lea     rax, [rbp+140h+cbData]
0x1800168fc  mov     [rsp+1A0h+UserData], rax; lpcbData
0x180016901  mov     [rsp+1A0h+phkResult], r13; lpData
0x180016906  lea     r9, [rbp+140h+Type]; lpType
0x18001690a  xor     r8d, r8d; lpReserved
0x18001690d  mov     rdx, rdi; lpValueName
0x180016910  mov     rcx, qword ptr [rbp+140h+SubKey]; hKey
0x180016914  call    cs:__imp_RegQueryValueExW
0x18001691a  mov     esi, eax
0x18001691c  test    eax, eax
0x18001691e  jle     short loc_180016929
0x180016920  movzx   esi, ax
0x180016923  or      esi, 80070000h
0x180016929  test    esi, esi
0x18001692b  jns     loc_180016A6F
0x180016931  mov     eax, cs:dword_180128170
0x180016937  cmp     eax, 3
0x18001693a  jbe     loc_180016ACA
0x180016940  mov     dword ptr [rbp+140h+IdentifierAuthority.Value], esi
0x180016943  mov     [rbp+140h+var_50], rdi
0x18001694a  mov     [rbp+140h+var_48], 12h
0x180016955  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001695c  nop     dword ptr [rax+00h]
0x180016960  lea     rax, [rax+1]
0x180016964  cmp     word ptr [r14+rax*2], 0
  ... truncated ...
```
