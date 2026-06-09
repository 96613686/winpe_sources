# GetTetheringProfileNameOrConnectInternetProfile(_GUID const *,ushort * *,ulong *,bool *)

- ea: `0x1800229b8`
- end: `0x180023475`
- name: `?GetTetheringProfileNameOrConnectInternetProfile@@YAJPEBU_GUID@@PEAPEAGPEAKPEA_N@Z`
- size: `2749`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 **, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ffe4`

## callees

- `0x180002590`
- `0x1800035a8`
- `0x180005e98`
- `0x18000a21c`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000ea08`
- `0x1800222d0`
- `0x1800225bc`
- `0x1800226c8`
- `0x1800229b8`
- `0x18002347c`
- `0x180023678`
- `0x180023974`
- `0x180023eb4`
- `0x180023f7c`
- `0x180029c10`
- `0x18002a3c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800231dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800231dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180023086`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180023086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022b17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022c06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022f18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022f8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800230c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022b17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022c06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022f18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022f8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800230c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800230b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800233cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800230b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800233cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022b0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022f84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800233e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800233f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022b0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022f84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800233e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800233f6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180022bfe`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18002341e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180022bfe`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18002341e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180022d2b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180022e7d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180022ee2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180023042`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002305f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002340a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180022d2b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180022e7d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180022ee2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180023042`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002305f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002340a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180022c2a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180022c2a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x1800230f8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x1800233aa`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x1800230f8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x1800233aa`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180022d97`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180022d97`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180022d04`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180022d04`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x180022e53`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x180022e53`
- `ext-ms-win-wwan-wwapi-l1-1-2!WwanConnect` at `0x18002316a`
- `ext-ms-win-wwan-wwapi-l1-1-2!WwanConnect` at `0x18002316a`

## pseudocode

```c
__int64 __fastcall GetTetheringProfileNameOrConnectInternetProfile(
        const struct _GUID *a1,
        unsigned __int16 **a2,
        unsigned int *a3,
        bool *a4)
{
  bool *v4; // r15
  unsigned __int16 **v5; // rdi
  unsigned __int16 *v7; // rbx
  signed int SimIccidForInterfaceGuidInternal; // esi
  int DedicatedConnectionNameFromDedicatedConnections; // eax
  TetheringServiceTelemetry *v10; // rcx
  unsigned __int16 *v11; // r12
  _QWORD *v12; // r14
  void *v13; // r15
  DWORD LastError; // edi
  unsigned int ProfileList; // r14d
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  void *v19; // rsi
  DWORD v20; // edi
  int WwanConnectionStatus; // eax
  bool v22; // al
  bool v23; // r15
  int WwanConnectionProfileName; // eax
  TetheringServiceTelemetry *v25; // rcx
  __int64 v26; // rdx
  void *v27; // rdx
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // edi
  _DWORD *v32; // r12
  void *v33; // rdx
  __int64 v34; // r8
  const char *v35; // r9
  unsigned __int16 *v36; // rcx
  bool v37; // zf
  HLOCAL v38; // r15
  DWORD v39; // edi
  __int64 v40; // rax
  HLOCAL *v41; // rsi
  HLOCAL v42; // r12
  HLOCAL v43; // r15
  DWORD v44; // edi
  unsigned __int16 *v45; // rcx
  unsigned __int16 *v46; // rcx
  void *v47; // rdx
  unsigned int v48; // r8d
  const char *v49; // r9
  HANDLE Event; // r14
  HANDLE v51; // rdi
  DWORD v52; // r15d
  __int64 v53; // r8
  const char *v54; // r9
  TetheringServiceTelemetry *v55; // rcx
  __int64 v56; // rdx
  DWORD v57; // eax
  __int64 v58; // r8
  const char *v59; // r9
  unsigned __int16 *v60; // rcx
  unsigned __int16 **v61; // rax
  TetheringServiceTelemetry *v62; // rcx
  __int64 v63; // rdx
  unsigned __int16 *v64; // r9
  __int64 v65; // r8
  const char *v66; // r9
  _DWORD *v67; // rcx
  bool *v69; // [rsp+20h] [rbp-E0h]
  bool v70[8]; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  void *v72; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v73; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v74; // [rsp+60h] [rbp-A0h] BYREF
  int v75; // [rsp+68h] [rbp-98h] BYREF
  void **p_hMem; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v77; // [rsp+78h] [rbp-88h] BYREF
  char v78; // [rsp+80h] [rbp-80h]
  _DWORD *v79; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-70h] BYREF
  __int64 v81; // [rsp+98h] [rbp-68h]
  int v82; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 **v83; // [rsp+A8h] [rbp-58h]
  bool *v84; // [rsp+B0h] [rbp-50h]
  HLOCAL v85[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v86; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v87[24]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v4 = a4;
  v84 = a4;
  v86 = a3;
  v5 = a2;
  v83 = a2;
  v82 = 0;
  v72 = (void *)-1LL;
  v79 = 0;
  hMem = 0;
  v7 = 0;
  v74 = 0;
  v70[0] = 0;
  v75 = 0;
  hObject = 0;
  v81 = 0;
  *a3 = 0;
  *a4 = 0;
  p_hMem = &hMem;
  v77 = 0;
  v78 = 1;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids);
  }
  *(struct _GUID *)v85 = *a1;
  SimIccidForInterfaceGuidInternal = TetheringGetSimIccidForInterfaceGuidInternal((struct _GUID *)v85, v87);
  if ( SimIccidForInterfaceGuidInternal >= 0 )
  {
    DedicatedConnectionNameFromDedicatedConnections = GetDedicatedConnectionNameFromDedicatedConnections(v87, &v77);
    SimIccidForInterfaceGuidInternal = DedicatedConnectionNameFromDedicatedConnections;
    if ( DedicatedConnectionNameFromDedicatedConnections == -2147024637
      || DedicatedConnectionNameFromDedicatedConnections == -2147024894 )
    {
      SimIccidForInterfaceGuidInternal = GetDedicatedConnectionNameFromNAIConnection(v87, &v77);
    }
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids,
      (unsigned int)SimIccidForInterfaceGuidInternal);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v78 )
  {
    v11 = v77;
    v12 = p_hMem;
    v13 = *p_hMem;
    if ( *p_hMem )
    {
      LastError = GetLastError();
      LocalFree(v13);
      SetLastError(LastError);
      v5 = v83;
    }
    *v12 = v11;
    v10 = WPP_GLOBAL_Control;
    v4 = v84;
  }
  if ( SimIccidForInterfaceGuidInternal != -2147024894 && SimIccidForInterfaceGuidInternal != -2147024637 )
  {
    ProfileList = 0;
    if ( SimIccidForInterfaceGuidInternal >= 0 )
    {
      if ( v10 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)v10 + 2), 11, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, hMem);
      v16 = (unsigned __int16 *)hMem;
      hMem = 0;
      *v5 = v16;
      *v4 = 1;
      goto LABEL_149;
    }
    if ( v10 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
      goto LABEL_149;
    v17 = 12;
LABEL_25:
    v18 = (unsigned int)SimIccidForInterfaceGuidInternal;
    goto LABEL_148;
  }
  if ( v10 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)v10 + 2), 10, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids);
  if ( !(unsigned __int8)IsWwanOpenHandlePresent() )
  {
    ProfileList = 50;
LABEL_144:
    SimIccidForInterfaceGuidInternal = 0;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_149;
    }
    v17 = 13;
    goto LABEL_147;
  }
  v19 = v72;
  if ( v72 != (void *)-1LL )
  {
    v20 = GetLastError();
    WwanCloseHandle(v19, 0);
    SetLastError(v20);
  }
  v72 = (void *)-1LL;
  ProfileList = WwanOpenHandle(1, 0, &v82, &v72);
  if ( ProfileList )
    goto LABEL_144;
  WwanConnectionStatus = GetWwanConnectionStatus(v72, a1, v70);
  SimIccidForInterfaceGuidInternal = WwanConnectionStatus;
  if ( WwanConnectionStatus < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_149;
    }
    v17 = ProfileList + 14;
    v18 = (unsigned int)WwanConnectionStatus;
LABEL_148:
    WPP_SF_d(*((_QWORD *)v10 + 2), v17, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, v18);
    goto LABEL_149;
  }
  v22 = IsMobile();
  v23 = v22;
  if ( v70[0] )
  {
    v74 = 0;
    WwanConnectionProfileName = GetWwanConnectionProfileName(v72, a1, &v74);
    SimIccidForInterfaceGuidInternal = WwanConnectionProfileName;
    if ( WwanConnectionProfileName < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_43;
      }
      v26 = 15;
LABEL_42:
      WPP_SF_d(
        *((_QWORD *)v25 + 2),
        v26,
        &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids,
        (unsigned int)WwanConnectionProfileName);
LABEL_43:
      v7 = v74;
      goto LABEL_149;
    }
    v7 = v74;
  }
  else if ( v22 )
  {
    *(_DWORD *)v70 = 0;
    v69 = v70;
    v28 = WwanSetInterface(v72, a1, 45);
    ProfileList = v28;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LODWORD(v69) = v28;
      WPP_SF__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, v30, a1, v69);
      v10 = WPP_GLOBAL_Control;
    }
    SimIccidForInterfaceGuidInternal = -2095972331;
    if ( v10 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
      goto LABEL_149;
    v17 = 17;
    goto LABEL_25;
  }
  p_hMem = (void **)&v79;
  v77 = 0;
  v78 = 1;
  ProfileList = WwanGetProfileList(v72, a1, 0, &v77);
  if ( v78 )
  {
    v27 = *p_hMem;
    *p_hMem = v77;
    if ( v27 )
      WwanFreeMemory(v27);
  }
  if ( ProfileList )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_149;
    }
    v17 = 18;
LABEL_147:
    v18 = ProfileList;
    goto LABEL_148;
  }
  v31 = 0;
  if ( !*v79 )
  {
LABEL_98:
    if ( !hMem )
    {
      if ( v7 )
        goto LABEL_135;
      Event = CreateEventExW(0, 0, 0, 0x1F0003u);
      if ( !Event )
        wil::details::in1diag3::Throw_GetLastError(retaddr, v47, v48, v49);
      GetLastError();
      v51 = hObject;
      if ( hObject )
      {
        v52 = GetLastError();
        if ( !CloseHandle(v51) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v53, v54);
        SetLastError(v52);
      }
      hObject = Event;
      ProfileList = WwanRegisterNotification(v72, 2, WwanCallback, &hObject, 0, &v75);
      if ( ProfileList )
      {
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_149;
        }
        v56 = 22;
        goto LABEL_108;
      }
      *(_WORD *)v70 = 0;
      ProfileList = WwanConnect(v72, a1, 2, v70, v86, 0, 0);
      if ( ProfileList )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_149;
        }
        v17 = 23;
        goto LABEL_147;
      }
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids);
      }
      v57 = WaitForSingleObjectEx(hObject, 0x2BF20u, 0);
      if ( v57 == 258 )
      {
        ProfileList = 1460;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_149;
        }
        v17 = 25;
        goto LABEL_147;
      }
      if ( v57 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v58, v59);
      if ( !(_BYTE)v81 )
      {
        ProfileList = HIDWORD(v81);
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_149;
        }
        v56 = 27;
LABEL_108:
        WPP_SF_d(*((_QWORD *)v55 + 2), v56, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, ProfileList);
        goto LABEL_149;
      }
      v74 = 0;
      WwanConnectionProfileName = GetWwanConnectionProfileName(v72, a1, &v74);
      SimIccidForInterfaceGuidInternal = WwanConnectionProfileName;
      if ( WwanConnectionProfileName < 0 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_43;
        }
        v26 = 26;
        goto LABEL_42;
      }
      v7 = v74;
    }
    v60 = (unsigned __int16 *)hMem;
    if ( hMem )
    {
      hMem = 0;
      v61 = v83;
      *v83 = v60;
      *v84 = 1;
      v62 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_149;
      }
      v63 = 28;
      v64 = *v61;
      goto LABEL_138;
    }
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids);
      }
      SimIccidForInterfaceGuidInternal = -2147024894;
      goto LABEL_149;
    }
LABEL_135:
    v64 = v7;
    v7 = 0;
    *v83 = v64;
    v62 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_149;
    }
    v63 = 29;
LABEL_138:
    WPP_SF_S(*((_QWORD *)v62 + 2), v63, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, v64);
    goto LABEL_149;
  }
  while ( 1 )
  {
    v32 = &v79[129 * v31];
    v73 = 0;
    *(_DWORD *)v70 = 0;
    p_hMem = (void **)&v73;
    v77 = 0;
    v78 = 1;
    ProfileList = WwanGetProfile(v72, &GUID_NULL, v32 + 1, 0, &v77, v70, 0);
    if ( v78 )
    {
      v33 = *p_hMem;
      *p_hMem = v77;
      if ( v33 )
        WwanFreeMemory(v33);
    }
    if ( ProfileList )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, ProfileList);
      }
      goto LABEL_69;
    }
    if ( !v23 && (unsigned int)IsTetheringProfile(v73) )
      break;
LABEL_69:
    v36 = v73;
    v37 = v73 == 0;
    v73 = 0;
    if ( !v37 )
      WwanFreeMemory(v36);
    if ( (unsigned int)++v31 >= *v79 )
      goto LABEL_98;
  }
  v38 = hMem;
  if ( hMem )
  {
    v39 = GetLastError();
    LocalFree(v38);
    SetLastError(v39);
  }
  hMem = 0;
  v40 = -1;
  do
    ++v40;
  while ( *((_WORD *)v32 + v40 + 2) );
  if ( !v40 )
  {
LABEL_96:
    v46 = v73;
    v73 = 0;
    if ( v46 )
      WwanFreeMemory(v46);
    goto LABEL_98;
  }
  if ( 2 * (unsigned __int64)(unsigned int)(v40 + 1) > 0xFFFFFFFF )
  {
    SimIccidForInterfaceGuidInternal = -2147024362;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, 2147942934LL);
    }
  }
  else
  {
    v41 = (HLOCAL *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      v85,
                      (char *)v32 + 4,
                      v34,
                      v35);
    if ( &hMem != v41 )
    {
      v42 = *v41;
      v43 = hMem;
      if ( hMem )
      {
        v44 = GetLastError();
        LocalFree(v43);
        SetLastError(v44);
      }
      hMem = v42;
      *v41 = 0;
    }
    if ( v85[0] )
      LocalFree(v85[0]);
    if ( hMem )
    {
      SimIccidForInterfaceGuidInternal = 0;
      goto LABEL_96;
    }
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids);
    }
    SimIccidForInterfaceGuidInternal = -2147024882;
  }
  v45 = v73;
  v73 = 0;
  if ( v45 )
    WwanFreeMemory(v45);
LABEL_149:
  if ( v75 )
    WwanRegisterNotification(v72, 0, 0, 0, 0, &v75);
  if ( ProfileList )
  {
    if ( (int)ProfileList > 0 )
      SimIccidForInterfaceGuidInternal = (unsigned __int16)ProfileList | 0x80070000;
    else
      SimIccidForInterfaceGuidInternal = ProfileList;
  }
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v65, v66);
  if ( v7 )
    LocalFree(v7);
  if ( hMem )
    LocalFree(hMem);
  v67 = v79;
  v79 = 0;
  if ( v67 )
    WwanFreeMemory(v67);
  if ( v72 != (void *)-1LL )
    WwanCloseHandle(v72, 0);
  return (unsigned int)SimIccidForInterfaceGuidInternal;
}

```

## disassembly

```asm
0x1800229b8  push    rbp
0x1800229ba  push    rbx
0x1800229bb  push    rsi
0x1800229bc  push    rdi
0x1800229bd  push    r12
0x1800229bf  push    r13
0x1800229c1  push    r14
0x1800229c3  push    r15
0x1800229c5  lea     rbp, [rsp-18h]
0x1800229ca  sub     rsp, 118h
0x1800229d1  mov     rax, cs:__security_cookie
0x1800229d8  xor     rax, rsp
0x1800229db  mov     [rbp+50h+var_48], rax
0x1800229df  mov     r15, r9
0x1800229e2  mov     [rbp+50h+var_A0], r9
0x1800229e6  mov     [rbp+50h+var_80], r8
0x1800229ea  mov     rdi, rdx
0x1800229ed  mov     [rbp+50h+var_A8], rdx
0x1800229f1  mov     r13, rcx
0x1800229f4  xor     r12d, r12d
0x1800229f7  mov     [rbp+50h+var_B0], r12d
0x1800229fb  mov     [rsp+150h+var_100], 0FFFFFFFFFFFFFFFFh
0x180022a04  mov     [rbp+50h+var_C8], r12
0x180022a08  mov     [rsp+150h+hMem], r12
0x180022a0d  mov     ebx, r12d
0x180022a10  mov     [rsp+150h+var_F0], rbx
0x180022a15  mov     [rsp+150h+var_110], r12b
0x180022a1a  mov     [rsp+150h+var_E8], r12d
0x180022a1f  mov     [rbp+50h+hObject], r12
0x180022a23  xor     ecx, ecx
0x180022a25  mov     [rbp+50h+var_B8], rcx
0x180022a29  mov     [r8], r12d
0x180022a2c  mov     [r9], r12b
0x180022a2f  lea     rax, [rsp+150h+hMem]
0x180022a34  mov     [rsp+150h+var_E0], rax
0x180022a39  mov     [rsp+150h+var_D8], r12
0x180022a3e  mov     [rbp+50h+var_D0], 1
0x180022a42  lea     r14, WPP_GLOBAL_Control
0x180022a49  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a50  cmp     rcx, r14
0x180022a53  jz      short loc_180022A70
0x180022a55  test    byte ptr [rcx+1Ch], 8
0x180022a59  jz      short loc_180022A70
0x180022a5b  lea     edx, [r12+24h]
0x180022a60  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x180022a67  mov     rcx, [rcx+10h]
0x180022a6b  call    WPP_SF_
0x180022a70  movups  xmm0, xmmword ptr [r13+0]
0x180022a75  movdqu  xmmword ptr [rbp+50h+var_90], xmm0
0x180022a7a  lea     rdx, [rbp+50h+var_78]; unsigned __int16 *
0x180022a7e  lea     rcx, [rbp+50h+var_90]; struct _GUID
0x180022a82  call    ?TetheringGetSimIccidForInterfaceGuidInternal@@YAJU_GUID@@PEAG@Z; TetheringGetSimIccidForInterfaceGuidInternal(_GUID,ushort *)
0x180022a87  mov     esi, eax
0x180022a89  test    eax, eax
0x180022a8b  js      short loc_180022ABB
0x180022a8d  lea     rdx, [rsp+150h+var_D8]; unsigned __int16 **
0x180022a92  lea     rcx, [rbp+50h+var_78]; unsigned __int16 *
0x180022a96  call    ?GetDedicatedConnectionNameFromDedicatedConnections@@YAJPEBGPEAPEAG@Z; GetDedicatedConnectionNameFromDedicatedConnections(ushort const *,ushort * *)
0x180022a9b  mov     esi, eax
0x180022a9d  cmp     eax, 80070103h
0x180022aa2  jz      short loc_180022AAB
0x180022aa4  cmp     eax, 80070002h
0x180022aa9  jnz     short loc_180022ABB
0x180022aab  lea     rdx, [rsp+150h+var_D8]; unsigned __int16 **
0x180022ab0  lea     rcx, [rbp+50h+var_78]; unsigned __int16 *
0x180022ab4  call    ?GetDedicatedConnectionNameFromNAIConnection@@YAJPEBGPEAPEAG@Z; GetDedicatedConnectionNameFromNAIConnection(ushort const *,ushort * *)
0x180022ab9  mov     esi, eax
0x180022abb  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ac2  cmp     rcx, r14
0x180022ac5  jz      short loc_180022AEC
0x180022ac7  test    byte ptr [rcx+1Ch], 8
0x180022acb  jz      short loc_180022AEC
0x180022acd  mov     edx, 25h ; '%'
0x180022ad2  mov     r9d, esi
0x180022ad5  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x180022adc  mov     rcx, [rcx+10h]
0x180022ae0  call    WPP_SF_d
0x180022ae5  mov     rcx, cs:WPP_GLOBAL_Control
0x180022aec  cmp     [rbp+50h+var_D0], r12b
0x180022af0  jz      short loc_180022B32
0x180022af2  mov     r12, [rsp+150h+var_D8]
0x180022af7  mov     r14, [rsp+150h+var_E0]
0x180022afc  mov     r15, [r14]
0x180022aff  test    r15, r15
0x180022b02  jz      short loc_180022B21
0x180022b04  call    cs:__imp_GetLastError
0x180022b0a  mov     edi, eax
0x180022b0c  mov     rcx, r15; hMem
0x180022b0f  call    cs:__imp_LocalFree
0x180022b15  mov     ecx, edi; dwErrCode
0x180022b17  call    cs:__imp_SetLastError
0x180022b1d  mov     rdi, [rbp+50h+var_A8]
0x180022b21  mov     [r14], r12
0x180022b24  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b2b  mov     r15, [rbp+50h+var_A0]
0x180022b2f  xor     r12d, r12d
0x180022b32  cmp     esi, 80070002h
0x180022b38  jz      short loc_180022BB2
0x180022b3a  cmp     esi, 80070103h
0x180022b40  jz      short loc_180022BB2
0x180022b42  mov     r14d, r12d
0x180022b45  test    esi, esi
0x180022b47  js      short loc_180022B8B
0x180022b49  lea     rax, WPP_GLOBAL_Control
0x180022b50  cmp     rcx, rax
0x180022b53  jz      short loc_180022B75
0x180022b55  test    byte ptr [rcx+1Ch], 4
0x180022b59  jz      short loc_180022B75
0x180022b5b  mov     edx, 0Bh
0x180022b60  mov     r9, [rsp+150h+hMem]
0x180022b65  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x180022b6c  mov     rcx, [rcx+10h]
0x180022b70  call    WPP_SF_S
0x180022b75  mov     rax, [rsp+150h+hMem]
0x180022b7a  mov     [rsp+150h+hMem], r12
0x180022b7f  mov     [rdi], rax
0x180022b82  mov     byte ptr [r15], 1
0x180022b86  jmp     loc_180023387
0x180022b8b  lea     rax, WPP_GLOBAL_Control
0x180022b92  cmp     rcx, rax
0x180022b95  jz      loc_180023387
0x180022b9b  test    byte ptr [rcx+1Ch], 1
0x180022b9f  jz      loc_180023387
0x180022ba5  mov     edx, 0Ch
0x180022baa  mov     r9d, esi
0x180022bad  jmp     loc_180023377
0x180022bb2  lea     rdi, WPP_GLOBAL_Control
0x180022bb9  cmp     rcx, rdi
0x180022bbc  jz      short loc_180022BD9
0x180022bbe  test    byte ptr [rcx+1Ch], 4
0x180022bc2  jz      short loc_180022BD9
0x180022bc4  mov     edx, 0Ah
0x180022bc9  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x180022bd0  mov     rcx, [rcx+10h]
0x180022bd4  call    WPP_SF_
0x180022bd9  call    IsWwanOpenHandlePresent
0x180022bde  test    al, al
0x180022be0  jz      loc_180023354
0x180022be6  mov     rsi, [rsp+150h+var_100]
0x180022beb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180022bef  jz      short loc_180022C13
0x180022bf1  call    cs:__imp_GetLastError
0x180022bf7  mov     edi, eax
0x180022bf9  xor     edx, edx
0x180022bfb  mov     rcx, rsi
0x180022bfe  call    cs:__imp_WwanCloseHandle
0x180022c04  mov     ecx, edi; dwErrCode
0x180022c06  call    cs:__imp_SetLastError
0x180022c0c  lea     rdi, WPP_GLOBAL_Control
0x180022c13  mov     [rsp+150h+var_100], 0FFFFFFFFFFFFFFFFh
0x180022c1c  lea     r9, [rsp+150h+var_100]
0x180022c21  lea     r8, [rbp+50h+var_B0]
0x180022c25  xor     edx, edx
0x180022c27  lea     ecx, [rdx+1]
0x180022c2a  call    cs:__imp_WwanOpenHandle
0x180022c30  mov     r14d, eax
0x180022c33  test    eax, eax
0x180022c35  jnz     loc_18002335A
0x180022c3b  lea     r8, [rsp+150h+var_110]; bool *
0x180022c40  mov     rdx, r13; struct _GUID *
0x180022c43  mov     rcx, [rsp+150h+var_100]; void *
0x180022c48  call    ?GetWwanConnectionStatus@@YAJPEAXPEBU_GUID@@PEA_N@Z; GetWwanConnectionStatus(void *,_GUID const *,bool *)
0x180022c4d  mov     esi, eax
0x180022c4f  test    eax, eax
0x180022c51  jns     short loc_180022C79
0x180022c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c5a  cmp     rcx, rdi
0x180022c5d  jz      loc_180023387
0x180022c63  test    byte ptr [rcx+1Ch], 1
0x180022c67  jz      loc_180023387
0x180022c6d  lea     edx, [r14+0Eh]
0x180022c71  mov     r9d, eax
0x180022c74  jmp     loc_180023377
0x180022c79  call    ?IsMobile@@YA_NXZ; IsMobile(void)
0x180022c7e  mov     r15b, al
0x180022c81  cmp     [rsp+150h+var_110], r12b
0x180022c86  jz      loc_180022D5E
0x180022c8c  mov     [rsp+150h+var_F0], r12
0x180022c91  lea     r8, [rsp+150h+var_F0]; unsigned __int16 **
0x180022c96  mov     rdx, r13; struct _GUID *
0x180022c99  mov     rcx, [rsp+150h+var_100]; void *
0x180022c9e  call    ?GetWwanConnectionProfileName@@YAJPEAXPEBU_GUID@@PEAPEAG@Z; GetWwanConnectionProfileName(void *,_GUID const *,ushort * *)
0x180022ca3  mov     esi, eax
0x180022ca5  test    eax, eax
0x180022ca7  jns     short loc_180022CDD
0x180022ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cb0  cmp     rcx, rdi
0x180022cb3  jz      short loc_180022CD3
0x180022cb5  test    byte ptr [rcx+1Ch], 1
0x180022cb9  jz      short loc_180022CD3
0x180022cbb  mov     edx, 0Fh
0x180022cc0  mov     r9d, eax
0x180022cc3  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x180022cca  mov     rcx, [rcx+10h]
0x180022cce  call    WPP_SF_d
0x180022cd3  mov     rbx, [rsp+150h+var_F0]
0x180022cd8  jmp     loc_180023387
0x180022cdd  mov     rbx, [rsp+150h+var_F0]
0x180022ce2  lea     rax, [rbp+50h+var_C8]
0x180022ce6  mov     [rsp+150h+var_E0], rax
0x180022ceb  mov     [rsp+150h+var_D8], r12
0x180022cf0  mov     [rbp+50h+var_D0], 1
0x180022cf4  lea     r9, [rsp+150h+var_D8]
0x180022cf9  xor     r8d, r8d
0x180022cfc  mov     rdx, r13
0x180022cff  mov     rcx, [rsp+150h+var_100]
0x180022d04  call    cs:__imp_WwanGetProfileList
0x180022d0a  mov     r14d, eax
0x180022d0d  cmp     [rbp+50h+var_D0], r12b
0x180022d11  jz      short loc_180022D31
0x180022d13  mov     rcx, [rsp+150h+var_E0]
0x180022d18  mov     rdx, [rcx]
0x180022d1b  mov     rax, [rsp+150h+var_D8]
0x180022d20  mov     [rcx], rax
0x180022d23  test    rdx, rdx
0x180022d26  jz      short loc_180022D31
0x180022d28  mov     rcx, rdx
0x180022d2b  call    cs:__imp_WwanFreeMemory
0x180022d31  test    r14d, r14d
0x180022d34  jz      loc_180022DEB
0x180022d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d41  cmp     rcx, rdi
0x180022d44  jz      loc_180023387
0x180022d4a  test    byte ptr [rcx+1Ch], 1
0x180022d4e  jz      loc_180023387
0x180022d54  mov     edx, 12h
0x180022d59  jmp     loc_180023374
0x180022d5e  test    r15b, r15b
0x180022d61  jz      loc_180022CE2
0x180022d67  mov     dword ptr [rsp+150h+var_110], r12d
0x180022d6c  mov     [rsp+150h+var_118], r12
0x180022d71  mov     [rsp+150h+var_120], r12
0x180022d76  mov     [rsp+150h+var_128], r12
0x180022d7b  lea     rax, [rsp+150h+var_110]
0x180022d80  mov     [rsp+150h+var_130], rax
0x180022d85  mov     r9d, 4
0x180022d8b  lea     r8d, [r9+29h]
0x180022d8f  mov     rdx, r13
0x180022d92  mov     rcx, [rsp+150h+var_100]
0x180022d97  call    cs:__imp_WwanSetInterface
0x180022d9d  mov     r14d, eax
0x180022da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022da7  cmp     rcx, rdi
0x180022daa  jz      short loc_180022DC9
0x180022dac  test    byte ptr [rcx+1Ch], 1
0x180022db0  jz      short loc_180022DC9
0x180022db2  mov     dword ptr [rsp+150h+var_130], eax
0x180022db6  mov     r9, r13
0x180022db9  mov     rcx, [rcx+10h]
0x180022dbd  call    WPP_SF__guid_D
0x180022dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dc9  mov     esi, 83120015h
0x180022dce  cmp     rcx, rdi
0x180022dd1  jz      loc_180023387
0x180022dd7  test    byte ptr [rcx+1Ch], 1
0x180022ddb  jz      loc_180023387
0x180022de1  mov     edx, 11h
0x180022de6  jmp     loc_180022BAA
0x180022deb  mov     edi, r12d
0x180022dee  mov     rax, [rbp+50h+var_C8]
0x180022df2  cmp     [rax], r12d
0x180022df5  jbe     loc_180023065
0x180022dfb  mov     eax, edi
0x180022dfd  imul    r12, rax, 204h
0x180022e04  add     r12, [rbp+50h+var_C8]
0x180022e08  xor     ecx, ecx
0x180022e0a  mov     [rsp+150h+var_F8], rcx
0x180022e0f  mov     dword ptr [rsp+150h+var_110], ecx
0x180022e13  lea     rax, [rsp+150h+var_F8]
0x180022e18  mov     [rsp+150h+var_E0], rax
0x180022e1d  mov     [rsp+150h+var_D8], rcx
0x180022e22  mov     [rbp+50h+var_D0], 1
0x180022e26  mov     [rsp+150h+var_120], rcx
0x180022e2b  lea     rax, [rsp+150h+var_110]
0x180022e30  mov     [rsp+150h+var_128], rax
0x180022e35  lea     rax, [rsp+150h+var_D8]
0x180022e3a  mov     [rsp+150h+var_130], rax
0x180022e3f  xor     r9d, r9d
0x180022e42  lea     r8, [r12+4]
0x180022e47  lea     rdx, GUID_NULL
0x180022e4e  mov     rcx, [rsp+150h+var_100]
0x180022e53  call    cs:__imp_WwanGetProfile
0x180022e59  mov     r14d, eax
0x180022e5c  xor     r8d, r8d
0x180022e5f  cmp     [rbp+50h+var_D0], r8b
0x180022e63  jz      short loc_180022E83
0x180022e65  mov     rcx, [rsp+150h+var_E0]
0x180022e6a  mov     rdx, [rcx]
0x180022e6d  mov     rax, [rsp+150h+var_D8]
0x180022e72  mov     [rcx], rax
0x180022e75  test    rdx, rdx
0x180022e78  jz      short loc_180022E83
0x180022e7a  mov     rcx, rdx
0x180022e7d  call    cs:__imp_WwanFreeMemory
0x180022e83  test    r14d, r14d
0x180022e86  jz      short loc_180022EBB
0x180022e88  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e8f  lea     rax, WPP_GLOBAL_Control
0x180022e96  cmp     rcx, rax
0x180022e99  jz      short loc_180022ED0
  ... truncated ...
```
