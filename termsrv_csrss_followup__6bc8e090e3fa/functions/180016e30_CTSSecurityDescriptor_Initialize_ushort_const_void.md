# CTSSecurityDescriptor::Initialize(ushort const *,void *)

- ea: `0x180016e30`
- end: `0x1800180e8`
- name: `?Initialize@CTSSecurityDescriptor@@QEAAJPEBGPEAX@Z`
- size: `4792`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180016ddc`
- `0x180019854`
- `0x18005289c`

## callees

- `0x180005314`
- `0x180005594`
- `0x1800063dc`
- `0x180009940`
- `0x180012210`
- `0x180014808`
- `0x180016e30`
- `0x180033f44`
- `0x180033f60`
- `0x18003444c`
- `0x180034df8`
- `0x1800bfbb8`
- `0x1800bfcd8`
- `0x1800cae70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800175af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800175c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800175af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800175c9`
- `ntdll!RtlFreeSid` at `0x180017dea`
- `ntdll!RtlFreeSid` at `0x180017dff`
- `ntdll!RtlFreeSid` at `0x180017dea`
- `ntdll!RtlFreeSid` at `0x180017dff`
- `ntdll!RtlDeleteSecurityObject` at `0x1800180b0`
- `ntdll!RtlDeleteSecurityObject` at `0x1800180b0`
- `ntdll!RtlCreateUserSecurityObject` at `0x180017ce7`
- `ntdll!RtlCreateUserSecurityObject` at `0x180017ce7`
- `ntdll!RtlNtStatusToDosError` at `0x180017d23`
- `ntdll!RtlNtStatusToDosError` at `0x180017d7f`
- `ntdll!RtlNtStatusToDosError` at `0x180017d23`
- `ntdll!RtlNtStatusToDosError` at `0x180017d7f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180017c0f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180017c6f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180017c0f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180017c6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017d31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017d8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017d31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017d8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800171fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017380`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800177af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017938`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800171fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017380`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800177af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017938`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001754c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017afe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001754c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017afe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017095`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001766c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017095`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001766c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800171c3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001777c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800171c3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001777c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017e14`

## string_xrefs

- `0x180017ff3`: `StringCchCopy failed: 0x%x in %s`
- `0x180017d6a`: `CUtil::CreateSystemSid failed: 0x%x in %s`
- `0x180017dc6`: `CUtil::CreateAdminSid failed: 0x%x in %s`
- `0x18001757c`: `SecurityDescriptor not found for this listener`
- `0x1800171ef`: `Security`
- `0x1800175f8`: `ConsoleSecurity`
- `0x180017637`: `ConsoleSecurity`
- `0x1800175d9`: `DefaultSecurity`
- `0x180017b2e`: `SecurityDescriptor registry not found`
- `0x180017603`: `Querying Console default security descriptor`
- `0x180017e43`: `CreateDefault`
- `0x180017b62`: `Creating default security descriptor in the registry and using it`
- `0x180017eea`: `Using security descriptor for this listener`
- `0x180017eaa`: `Found security descriptor and using it.`
- `0x18001802d`: `CopySource failed: 0x%x in %s`
- `0x180018023`: `CTSSecurityDescriptor::Initialize`
- `0x180018051`: `CTSSecurityDescriptor::Initialize`
- `0x1800173f6`: `GetSDValueFromRegistry`
- `0x1800179b3`: `GetSDValueFromRegistry`
- `0x180017116`: `Failed to open key`
- `0x1800176d0`: `Failed to open key`
- `0x180017503`: `Invalid security descriptor in registry`
- `0x180017abe`: `Invalid security descriptor in registry`
- `0x180017288`: `Registry entry not found`
- `0x180017846`: `Registry entry not found`
- `0x180017bae`: `CTSSecurityDescriptor::CreateDefault`
- `0x180017d01`: `CTSSecurityDescriptor::CreateDefault`
- `0x180017d60`: `CTSSecurityDescriptor::CreateDefault`
- `0x180017dbc`: `CTSSecurityDescriptor::CreateDefault`
- `0x180017bb8`: `GetCurrentProcessSid failed: 0x%x in %s`
- `0x180017d0b`: `RtlCreateUserSecurityObject failed: 0x%x in %s`
- `0x180017ffa`: `CTSSecurityDescriptor::CopySource`
- `0x1800175bf`: `Services`

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
  int v17; // r8d
  int v18; // r9d
  signed int v19; // esi
  __int64 v20; // rax
  LSTATUS Value; // eax
  DWORD v22; // ecx
  __int64 v23; // rax
  LSTATUS v24; // eax
  __int64 v25; // rax
  int v26; // ecx
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  const WCHAR *v30; // r14
  BYTE *v31; // r13
  LSTATUS v32; // eax
  int v33; // r8d
  int v34; // r9d
  signed int v35; // esi
  LSTATUS v36; // eax
  DWORD v37; // ecx
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
  const WCHAR *v88; // [rsp+120h] [rbp+C0h]
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
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      *(_QWORD *)&EventDescriptor.Id = "Initialize";
      Type[0] = v7;
      v68 = (CTSSecurityDescriptor *)"StringCbLength";
      *(_QWORD *)SubKey = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&dword_18012E170,
        (unsigned int)&byte_18011AE77,
        0,
        0,
        (__int64)SubKey,
        (__int64)&v68,
        (__int64)Type,
        (__int64)&EventDescriptor);
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
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        *(_QWORD *)&EventDescriptor.Id = "Initialize";
        Type[0] = v14;
        v68 = (CTSSecurityDescriptor *)"StringCbPrintf";
        *(_QWORD *)SubKey = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18012E170,
          (unsigned int)byte_18011AF1B,
          0,
          0,
          (__int64)SubKey,
          (__int64)&v68,
          (__int64)Type,
          (__int64)&EventDescriptor);
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
            v26 = *(_DWORD *)SubKey;
            if ( *(_QWORD *)SubKey )
              RegCloseKey(*(HKEY *)SubKey);
            if ( v15 )
              operator delete(v15);
            if ( v19 >= 0 )
            {
              if ( (unsigned int)dword_18012E170 > 5 )
              {
                *(_QWORD *)&EventDescriptor.Id = v4;
                *(_QWORD *)SubKey = "Using security descriptor for this listener";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                  v26,
                  (unsigned int)byte_18011AEE9,
                  v17,
                  v18,
                  (__int64)SubKey,
                  (__int64)&EventDescriptor);
              }
              v5 = v68;
              goto LABEL_134;
            }
            if ( (unsigned int)dword_18012E170 > 5 )
            {
              *(_QWORD *)&EventDescriptor.Id = v4;
              *(_QWORD *)SubKey = "SecurityDescriptor not found for this listener";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                v26,
                (unsigned int)byte_18011AE0D,
                v17,
                v18,
                (__int64)SubKey,
                (__int64)&EventDescriptor);
            }
            if ( (unsigned int)_o__wcsicmp(v4, L"Console") && (unsigned int)_o__wcsicmp(v4, L"Services") )
            {
              v30 = L"DefaultSecurity";
            }
            else if ( (unsigned int)dword_18012E170 <= 5 )
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
                (unsigned int)&byte_18011AE3F,
                v28,
                v29,
                (__int64)&Block,
                (__int64)SubKey,
                (__int64)&EventDescriptor);
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
                    else if ( (unsigned int)dword_18012E170 > 3 )
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
                      v88 = (const WCHAR *)IdentifierAuthority;
                      v89 = 4;
                      v86 = (WCHAR *)"RegQueryValueEx failed after we queried it the 2nd time";
                      v87 = 56;
                      v84 = "Warning HResult failed";
                      v85 = 23;
                      *(_DWORD *)&EventDescriptor.Id = 184549376;
                      *(_DWORD *)&EventDescriptor.Level = 3;
                      EventDescriptor.Keyword = 0;
                      UserData.Ptr = (ULONGLONG)off_18012E178;
                      UserData.Size = *(unsigned __int16 *)off_18012E178;
                      UserData.Reserved = 2;
                      v81 = &byte_18011B00F;
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
                  if ( (unsigned int)dword_18012E170 > 2 )
                  {
                    *(_QWORD *)&EventDescriptor.Id = v30;
                    *(_QWORD *)IdentifierAuthority[0].Value = L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations";
                    v64 = "Invalid security descriptor in registry";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                      v37,
                      (unsigned int)byte_18011ADD5,
                      v33,
                      v34,
                      (__int64)&v64,
                      (__int64)IdentifierAuthority,
                      (__int64)&EventDescriptor);
                  }
                  v35 = -2147023558;
                }
              }
              else if ( (unsigned int)dword_18012E170 > 5 )
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
                UserData.Ptr = (ULONGLONG)off_18012E178;
                UserData.Size = *(unsigned __int16 *)off_18012E178;
                UserData.Reserved = 2;
                v81 = (char *)word_18011AFAA;
                v82 = 49;
                v83 = 1;
                LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
              }
            }
            else if ( (unsigned int)dword_18012E170 > 3 )
            {
              *(_DWORD *)IdentifierAuthority[0].Value = v35;
              v88 = (const WCHAR *)IdentifierAuthority;
              v89 = 4;
              v86 = (WCHAR *)L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations";
              v87 = 122;
              v84 = "Failed to open key";
              v85 = 19;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              *(_DWORD *)&EventDescriptor.Level = 3;
              EventDescriptor.Keyword = 0;
              UserData.Ptr = (ULONGLONG)off_18012E178;
              UserData.Size = *(unsigned __int16 *)off_18012E178;
              UserData.Reserved = 2;
              v81 = byte_18011AD83;
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
              if ( (unsigned int)dword_18012E170 > 5 )
              {
                *(_QWORD *)&EventDescriptor.Id = "Found security descriptor and using it.";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&dword_18012E170,
                  (unsigned int)&dword_18011AFDC,
                  0,
                  0,
                  (__int64)&EventDescriptor);
              }
              v3 = Block;
              v5 = v68;
              goto LABEL_134;
            }
            if ( (unsigned int)dword_18012E170 > 5 )
            {
              *(_QWORD *)&EventDescriptor.Id = v30;
              *(_QWORD *)SubKey = "SecurityDescriptor registry not found";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                (_DWORD)v41,
                (unsigned int)byte_18011AEB9,
                v33,
                v34,
                (__int64)SubKey,
                (__int64)&EventDescriptor);
            }
            if ( (unsigned int)dword_18012E170 > 5 )
            {
              *(_QWORD *)&EventDescriptor.Id = "Creating default security descriptor in the registry and using it";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                (unsigned int)&dword_18012E170,
                (unsigned int)byte_18011ADAD,
                0,
                0,
                (__int64)&EventDescriptor);
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
                if ( (unsigned int)dword_18012E170 > 3 )
                {
                  *(_QWORD *)&EventDescriptor.Id = "Initialize";
                  *(_DWORD *)IdentifierAuthority[0].Value = v43;
                  v68 = (CTSSecurityDescriptor *)"CreateDefault";
                  *(_QWORD *)SubKey = "Warning HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    (unsigned int)&dword_18012E170,
                    (unsigned int)byte_18011AF5D,
                    0,
                    0,
                    (__int64)SubKey,
                    (__int64)&v68,
                    (__int64)IdentifierAuthority,
                    (__int64)&EventDescriptor);
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
          if ( (unsigned int)dword_18012E170 > 3 )
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
            v88 = (const WCHAR *)IdentifierAuthority;
            v89 = 4;
            v86 = (WCHAR *)"RegQueryValueEx failed after we queried it the 2nd time";
            v87 = 56;
            v84 = "Warning HResult failed";
            v85 = 23;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            *(_DWORD *)&EventDescriptor.Level = 3;
            EventDescriptor.Keyword = 0;
            UserData.Ptr = (ULONGLONG)off_18012E178;
            UserData.Size = *(unsigned __int16 *)off_18012E178;
            UserData.Reserved = 2;
            v81 = &byte_18011B00F;
            v82 = 70;
            v83 = 1;
            LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
          }
        }
        else
        {
          if ( (unsigned int)dword_18012E170 > 2 )
          {
            *(_QWORD *)&EventDescriptor.Id = L"Security";
            *(_QWORD *)IdentifierAuthority[0].Value = SubKey;
            v64 = "Invalid security descriptor in registry";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v22,
              (unsigned int)byte_18011ADD5,
              v17,
              v18,
              (__int64)&v64,
              (__int64)IdentifierAuthority,
              (__int64)&EventDescriptor);
          }
          v19 = -2147023558;
        }
      }
      else if ( (unsigned int)dword_18012E170 > 5 )
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
        UserData.Ptr = (ULONGLONG)off_18012E178;
        UserData.Size = *(unsigned __int16 *)off_18012E178;
        UserData.Reserved = 2;
        v81 = (char *)word_18011AFAA;
        v82 = 49;
        v83 = 1;
        LODWORD(v64) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
      }
    }
    else if ( (unsigned int)dword_18012E170 > 3 )
    {
      LODWORD(v64) = v19;
      v88 = (const WCHAR *)&v64;
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
      UserData.Ptr = (ULONGLONG)off_18012E178;
      UserData.Size = *(unsigned __int16 *)off_18012E178;
      UserData.Reserved = 2;
      v81 = byte_18011AD83;
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
0x180016e30  push    rbp
0x180016e32  push    rsi
0x180016e33  push    rdi
0x180016e34  push    r12
0x180016e36  push    r13
0x180016e38  push    r14
0x180016e3a  push    r15
0x180016e3c  sub     rsp, 170h
0x180016e43  lea     rbp, [rsp+60h]
0x180016e48  mov     [rbp+140h+arg_18], rbx
0x180016e4f  mov     rax, cs:__security_cookie
0x180016e56  xor     rax, rbp
0x180016e59  mov     [rbp+140h+var_40], rax
0x180016e60  mov     r14, r8
0x180016e63  mov     r15, rdx
0x180016e66  mov     r13, rcx
0x180016e69  mov     [rbp+140h+var_108], rcx
0x180016e6d  mov     [rbp+140h+var_128], rcx
0x180016e71  mov     qword ptr [rbp+140h+Type], rdx
0x180016e75  xor     ebx, ebx
0x180016e77  mov     r12d, ebx
0x180016e7a  mov     qword ptr [rbp+140h+SubKey], rbx
0x180016e7e  mov     [rbp+140h+ObjectDescriptor], rbx
0x180016e82  mov     [rbp+140h+Block], rbx
0x180016e86  mov     qword ptr [rbp+140h+IdentifierAuthority.Value], rbx
0x180016e8a  test    rdx, rdx
0x180016e8d  jnz     short loc_180016E99
0x180016e8f  mov     edi, 80070057h
0x180016e94  jmp     loc_180018087
0x180016e99  test    r8, r8
0x180016e9c  jnz     loc_180017F19
0x180016ea2  mov     edx, 21h ; '!'
0x180016ea7  mov     eax, edx
0x180016ea9  mov     rcx, r15
0x180016eac  nop     dword ptr [rax+00h]
0x180016eb0  cmp     [rcx], bx
0x180016eb3  jz      short loc_180016EBF
0x180016eb5  add     rcx, 2
0x180016eb9  sub     rax, 1
0x180016ebd  jnz     short loc_180016EB0
0x180016ebf  mov     edi, 80070057h
0x180016ec4  test    rax, rax
0x180016ec7  cmovnz  edi, ebx
0x180016eca  sub     rdx, rax
0x180016ecd  test    rax, rax
0x180016ed0  cmovz   rdx, rbx
0x180016ed4  jz      short loc_180016EDB
0x180016ed6  add     rdx, rdx
0x180016ed9  jmp     short loc_180016EDE
0x180016edb  mov     rdx, rbx
0x180016ede  test    rax, rax
0x180016ee1  jnz     short loc_180016F58
0x180016ee3  mov     eax, cs:dword_18012E170
0x180016ee9  cmp     eax, 3
0x180016eec  jbe     loc_180018083
0x180016ef2  lea     rax, aInitialize; "Initialize"
0x180016ef9  mov     qword ptr [rbp+140h+EventDescriptor.Id], rax
0x180016efd  mov     [rbp+140h+Type], edi
0x180016f00  lea     rax, aStringcblength_0; "StringCbLength"
0x180016f07  mov     [rbp+140h+var_108], rax
0x180016f0b  lea     rax, aWarningHresult; "Warning HResult failed"
0x180016f12  mov     qword ptr [rbp+140h+SubKey], rax
0x180016f16  lea     rax, [rbp+140h+EventDescriptor]
0x180016f1a  mov     qword ptr [rsp+1A0h+SubAuthority5], rax
0x180016f1f  lea     rax, [rbp+140h+Type]
0x180016f23  mov     qword ptr [rsp+1A0h+SubAuthority4], rax
0x180016f28  lea     rax, [rbp+140h+var_108]
0x180016f2c  mov     [rsp+1A0h+UserData], rax
0x180016f31  lea     rax, [rbp+140h+SubKey]
0x180016f35  mov     [rsp+1A0h+phkResult], rax
0x180016f3a  xor     r9d, r9d
0x180016f3d  xor     r8d, r8d
0x180016f40  lea     rdx, byte_18011AE77
0x180016f47  lea     rcx, dword_18012E170
0x180016f4e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180016f53  jmp     loc_180018083
0x180016f58  add     rdx, 7Eh ; '~'
0x180016f5c  mov     qword ptr [rbp+140h+cbData], rdx
0x180016f60  mov     qword ptr [rbp+140h+EventDescriptor.Id], rdx
0x180016f64  lea     rax, [rdx+0Fh]
0x180016f68  cmp     rax, rdx
0x180016f6b  ja      short loc_180016F77
0x180016f6d  mov     rax, 0FFFFFFFFFFFFFF0h
0x180016f77  and     rax, 0FFFFFFFFFFFFFFF0h
0x180016f7b  call    _alloca_probe
0x180016f80  sub     rsp, rax
0x180016f83  lea     r14, [rsp+1A0h+SubKey]
0x180016f88  mov     [rbp+140h+var_D8], r14
0x180016f8c  jmp     short loc_180016FCD
0x180016f8e  call    _o__resetstkoflw_0
0x180016f93  xor     r14d, r14d
0x180016f96  mov     [rbp+140h+var_D8], r14
0x180016f9a  mov     r8, qword ptr [rbp+140h+EventDescriptor.Id]
0x180016f9e  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x180016fa5  mov     ecx, 8; int
0x180016faa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180016faf  xor     ebx, ebx
0x180016fb1  mov     r12, qword ptr [rbp+140h+SubKey]
0x180016fb5  mov     rax, qword ptr [rbp+140h+IdentifierAuthority.Value]
0x180016fb9  mov     [rbp+140h+Block], rax
0x180016fbd  mov     rcx, [rbp+140h+var_128]
0x180016fc1  mov     [rbp+140h+var_108], rcx
0x180016fc5  mov     r15, qword ptr [rbp+140h+Type]
0x180016fc9  mov     rdx, qword ptr [rbp+140h+cbData]; unsigned __int64
0x180016fcd  test    r14, r14
0x180016fd0  jnz     short loc_180016FDC
0x180016fd2  mov     edi, 8007000Eh
0x180016fd7  jmp     loc_180018087
0x180016fdc  mov     [rsp+1A0h+phkResult], r15
0x180016fe1  lea     r9, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180016fe8  lea     r8, aSS_0; "%s\\%s"
0x180016fef  mov     rcx, r14; unsigned __int16 *
0x180016ff2  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016ff7  mov     edi, eax
0x180016ff9  test    eax, eax
0x180016ffb  jns     short loc_180017072
0x180016ffd  mov     ecx, cs:dword_18012E170
0x180017003  cmp     ecx, 3
0x180017006  jbe     loc_180018083
0x18001700c  lea     rax, aInitialize; "Initialize"
0x180017013  mov     qword ptr [rbp+140h+EventDescriptor.Id], rax
0x180017017  mov     [rbp+140h+Type], edi
0x18001701a  lea     rax, aStringcbprintf_0; "StringCbPrintf"
0x180017021  mov     [rbp+140h+var_108], rax
0x180017025  lea     rax, aWarningHresult; "Warning HResult failed"
0x18001702c  mov     qword ptr [rbp+140h+SubKey], rax
0x180017030  lea     rax, [rbp+140h+EventDescriptor]
0x180017034  mov     qword ptr [rsp+1A0h+SubAuthority5], rax
0x180017039  lea     rax, [rbp+140h+Type]
0x18001703d  mov     qword ptr [rsp+1A0h+SubAuthority4], rax
0x180017042  lea     rax, [rbp+140h+var_108]
0x180017046  mov     [rsp+1A0h+UserData], rax
0x18001704b  lea     rax, [rbp+140h+SubKey]
0x18001704f  mov     [rsp+1A0h+phkResult], rax
0x180017054  xor     r9d, r9d
0x180017057  xor     r8d, r8d
0x18001705a  lea     rdx, byte_18011AF1B
0x180017061  lea     rcx, dword_18012E170
0x180017068  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001706d  jmp     loc_180018083
0x180017072  mov     qword ptr [rbp+140h+SubKey], rbx
0x180017076  mov     r13, rbx
0x180017079  lea     rax, [rbp+140h+SubKey]
0x18001707d  mov     [rsp+1A0h+phkResult], rax; phkResult
0x180017082  mov     r9d, 20019h; samDesired
0x180017088  xor     r8d, r8d; ulOptions
0x18001708b  mov     rdx, r14; lpSubKey
0x18001708e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017095  call    cs:__imp_RegOpenKeyExW
0x18001709c  nop     dword ptr [rax+rax+00h]
0x1800170a1  mov     esi, eax
0x1800170a3  test    eax, eax
0x1800170a5  jle     short loc_1800170B0
0x1800170a7  movzx   esi, ax
0x1800170aa  or      esi, 80070000h
0x1800170b0  test    esi, esi
0x1800170b2  jns     loc_1800171D4
0x1800170b8  mov     eax, cs:dword_18012E170
0x1800170be  cmp     eax, 3
0x1800170c1  jbe     loc_18001753A
0x1800170c7  mov     dword ptr [rbp+140h+var_128], esi
0x1800170ca  lea     rax, [rbp+140h+var_128]
0x1800170ce  mov     [rbp+140h+var_80], rax
0x1800170d5  mov     [rbp+140h+var_78], 4
0x1800170e0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800170e7  nop     word ptr [rax+rax+00000000h]
0x1800170f0  lea     rax, [rax+1]
0x1800170f4  cmp     word ptr [r14+rax*2], 0
0x1800170fa  jnz     short loc_1800170F0
0x1800170fc  mov     [rbp+140h+var_90], r14
0x180017103  lea     eax, ds:2[rax*2]
0x18001710a  mov     dword ptr [rbp+140h+var_88], eax
0x180017110  mov     dword ptr [rbp+140h+var_88+4], ebx
0x180017116  lea     r14, aFailedToOpenKe; "Failed to open key"
0x18001711d  mov     [rbp+140h+var_A0], r14
0x180017124  mov     [rbp+140h+var_98], 13h
0x18001712f  mov     dword ptr [rbp+140h+EventDescriptor.Id], 0B000000h
0x180017136  movzx   eax, cs:word_18011AD79
0x18001713d  mov     dword ptr [rbp+140h+EventDescriptor.Level], eax
0x180017140  mov     [rbp+140h+EventDescriptor.Keyword], rbx
0x180017144  mov     rax, cs:off_18012E178
0x18001714b  mov     [rbp+140h+var_C0.Ptr], rax
0x180017152  movzx   eax, word ptr [rax]
0x180017155  mov     [rbp+140h+var_C0.Size], eax
0x18001715b  mov     dword ptr [rbp+140h+var_C0.0Ch], 2
0x180017165  lea     r14, byte_18011AD83
0x18001716c  mov     [rbp+140h+var_B0], r14
0x180017173  mov     [rbp+140h+var_A8], 29h ; ')'
0x18001717d  mov     [rbp+140h+var_A4], 1
0x180017187  lea     rax, _TraceLoggingMetadataEnd
0x18001718e  lea     r14, _TraceLoggingMetadata
0x180017195  sub     eax, r14d
0x180017198  mov     dword ptr [rbp+140h+IdentifierAuthority.Value], eax
0x18001719b  mov     eax, dword ptr [rbp+140h+IdentifierAuthority.Value]
0x18001719e  lea     rax, [rbp+140h+var_C0]
0x1800171a5  mov     [rsp+1A0h+UserData], rax; UserData
0x1800171aa  mov     dword ptr [rsp+1A0h+phkResult], 5; UserDataCount
0x1800171b2  xor     r9d, r9d; RelatedActivityId
0x1800171b5  xor     r8d, r8d; ActivityId
0x1800171b8  lea     rdx, [rbp+140h+EventDescriptor]; EventDescriptor
0x1800171bc  mov     rcx, cs:RegHandle; RegHandle
0x1800171c3  call    cs:__imp_EventWriteTransfer
0x1800171ca  nop     dword ptr [rax+rax+00h]
0x1800171cf  jmp     loc_18001753A
0x1800171d4  mov     [rbp+140h+Type], ebx
0x1800171d7  mov     [rbp+140h+cbData], ebx
0x1800171da  lea     rax, [rbp+140h+cbData]
0x1800171de  mov     [rsp+1A0h+UserData], rax; lpcbData
0x1800171e3  mov     [rsp+1A0h+phkResult], rbx; lpData
0x1800171e8  lea     r9, [rbp+140h+Type]; lpType
0x1800171ec  xor     r8d, r8d; lpReserved
0x1800171ef  lea     rdi, ValueName; "Security"
0x1800171f6  mov     rdx, rdi; lpValueName
0x1800171f9  mov     rcx, qword ptr [rbp+140h+SubKey]; hKey
0x1800171fd  call    cs:__imp_RegQueryValueExW
0x180017204  nop     dword ptr [rax+rax+00h]
0x180017209  mov     esi, eax
0x18001720b  test    eax, eax
0x18001720d  jle     short loc_180017218
0x18001720f  movzx   esi, ax
0x180017212  or      esi, 80070000h
0x180017218  test    esi, esi
0x18001721a  jns     loc_180017329
0x180017220  mov     eax, cs:dword_18012E170
0x180017226  cmp     eax, 5
0x180017229  jbe     loc_18001753A
0x18001722f  mov     dword ptr [rbp+140h+IdentifierAuthority.Value], esi
0x180017232  lea     rax, [rbp+140h+IdentifierAuthority]
0x180017236  mov     [rbp+140h+var_70], rax
0x18001723d  mov     [rbp+140h+var_68], 4
0x180017248  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001724f  nop
0x180017250  lea     rax, [rax+1]
0x180017254  cmp     word ptr [r14+rax*2], 0
0x18001725a  jnz     short loc_180017250
0x18001725c  mov     [rbp+140h+var_80], r14
0x180017263  lea     eax, ds:2[rax*2]
0x18001726a  mov     dword ptr [rbp+140h+var_78], eax
0x180017270  mov     dword ptr [rbp+140h+var_78+4], ebx
0x180017276  mov     [rbp+140h+var_90], rdi
0x18001727d  mov     [rbp+140h+var_88], 12h
0x180017288  lea     r14, aRegistryEntryN; "Registry entry not found"
0x18001728f  mov     [rbp+140h+var_A0], r14
0x180017296  mov     [rbp+140h+var_98], 19h
0x1800172a1  mov     dword ptr [rbp+140h+EventDescriptor.Id], 0B000000h
0x1800172a8  movzx   eax, cs:word_18011AFA0
0x1800172af  mov     dword ptr [rbp+140h+EventDescriptor.Level], eax
0x1800172b2  mov     [rbp+140h+EventDescriptor.Keyword], rbx
0x1800172b6  mov     rax, cs:off_18012E178
0x1800172bd  mov     [rbp+140h+var_C0.Ptr], rax
0x1800172c4  movzx   eax, word ptr [rax]
0x1800172c7  mov     [rbp+140h+var_C0.Size], eax
0x1800172cd  mov     dword ptr [rbp+140h+var_C0.0Ch], 2
0x1800172d7  lea     r14, word_18011AFAA
0x1800172de  mov     [rbp+140h+var_B0], r14
0x1800172e5  mov     [rbp+140h+var_A8], 31h ; '1'
0x1800172ef  mov     [rbp+140h+var_A4], 1
0x1800172f9  lea     rax, _TraceLoggingMetadataEnd
0x180017300  lea     r14, _TraceLoggingMetadata
0x180017307  sub     eax, r14d
0x18001730a  mov     dword ptr [rbp+140h+var_128], eax
0x18001730d  mov     eax, dword ptr [rbp+140h+var_128]
0x180017310  lea     rax, [rbp+140h+var_C0]
0x180017317  mov     [rsp+1A0h+UserData], rax
0x18001731c  mov     dword ptr [rsp+1A0h+phkResult], 6
0x180017324  jmp     loc_1800171B2
0x180017329  cmp     [rbp+140h+Type], 3
0x18001732d  jnz     loc_1800174F0
0x180017333  mov     ecx, [rbp+140h+cbData]; unsigned __int64
0x180017336  lea     eax, [rcx-28h]
0x180017339  cmp     eax, 0FFD7h
0x18001733e  ja      loc_1800174F0
0x180017344  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001734b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017350  mov     r13, rax
0x180017353  test    rax, rax
0x180017356  jnz     short loc_180017364
0x180017358  mov     edi, 8007000Eh
0x18001735d  mov     esi, edi
0x18001735f  jmp     loc_18001753F
0x180017364  lea     rax, [rbp+140h+cbData]
0x180017368  mov     [rsp+1A0h+UserData], rax; lpcbData
0x18001736d  mov     [rsp+1A0h+phkResult], r13; lpData
0x180017372  lea     r9, [rbp+140h+Type]; lpType
0x180017376  xor     r8d, r8d; lpReserved
0x180017379  mov     rdx, rdi; lpValueName
0x18001737c  mov     rcx, qword ptr [rbp+140h+SubKey]; hKey
0x180017380  call    cs:__imp_RegQueryValueExW
0x180017387  nop     dword ptr [rax+rax+00h]
0x18001738c  mov     esi, eax
0x18001738e  test    eax, eax
0x180017390  jle     short loc_18001739B
0x180017392  movzx   esi, ax
0x180017395  or      esi, 80070000h
0x18001739b  test    esi, esi
0x18001739d  jns     loc_1800174DF
0x1800173a3  mov     eax, cs:dword_18012E170
0x1800173a9  cmp     eax, 3
0x1800173ac  jbe     loc_18001753A
0x1800173b2  mov     dword ptr [rbp+140h+IdentifierAuthority.Value], esi
  ... truncated ...
```
