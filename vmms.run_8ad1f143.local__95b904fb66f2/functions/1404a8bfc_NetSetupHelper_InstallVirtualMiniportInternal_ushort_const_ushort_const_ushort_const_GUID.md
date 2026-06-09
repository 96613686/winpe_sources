# NetSetupHelper::InstallVirtualMiniportInternal(ushort const *,ushort const *,ushort const *,_GUID *)

- ea: `0x1404a8bfc`
- end: `0x1404a93cb`
- name: `?InstallVirtualMiniportInternal@NetSetupHelper@@AEAAJPEBG00PEAU_GUID@@@Z`
- size: `1999`
- prototype: `int(NetSetupHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1404a8b0c`

## callees

- `0x140001da8`
- `0x140002078`
- `0x14004f3c4`
- `0x14005c630`
- `0x1400a2bb0`
- `0x1400a83b8`
- `0x1400a8824`
- `0x14015fd30`
- `0x14015fdb8`
- `0x14042bd48`
- `0x1404828e0`
- `0x1404835a0`
- `0x1404a6510`
- `0x1404a6d14`
- `0x1404a8bfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404a8d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404a8e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404a8ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404a9378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404a8d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404a8e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404a8ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404a9378`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1404a8edd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1404a8edd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1404a8f27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1404a8f27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1404a928f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1404a92a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1404a928f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1404a92a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1404a911c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1404a911c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1404a9160`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1404a9160`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1404a9190`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1404a9190`
- `DEVOBJ!DevObjChangeState` at `0x1404a8fa7`
- `DEVOBJ!DevObjChangeState` at `0x1404a8fa7`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1404a8e30`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1404a8e30`
- `DEVOBJ!DevObjDeleteDevice` at `0x1404a9368`
- `DEVOBJ!DevObjDeleteDevice` at `0x1404a9368`
- `DEVOBJ!DevObjSetDeviceRegistryProperty` at `0x1404a8dd8`
- `DEVOBJ!DevObjSetDeviceRegistryProperty` at `0x1404a8dd8`
- `DEVOBJ!DevObjRegisterDeviceInfo` at `0x1404a8e03`
- `DEVOBJ!DevObjRegisterDeviceInfo` at `0x1404a8e03`
- `DEVOBJ!DevObjCreateDevRegKey` at `0x1404a8e85`
- `DEVOBJ!DevObjCreateDevRegKey` at `0x1404a8e85`
- `DEVOBJ!DevObjCreateDeviceInfo` at `0x1404a8d65`
- `DEVOBJ!DevObjCreateDeviceInfo` at `0x1404a8d65`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1404a92bc`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1404a92bc`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1404a8d01`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1404a8d01`
- `NetSetupApi!NetSetupSynchronizeDevices` at `0x1404a9022`
- `NetSetupApi!NetSetupSynchronizeDevices` at `0x1404a9022`
- `NetSetupApi!NetSetupClose` at `0x1404a9044`
- `NetSetupApi!NetSetupClose` at `0x1404a9044`
- `NetSetupApi!NetSetupInitialize` at `0x1404a9064`
- `NetSetupApi!NetSetupInitialize` at `0x1404a9064`
- `NetSetupApi!NetSetupGetObjects` at `0x1404a90b6`
- `NetSetupApi!NetSetupGetObjects` at `0x1404a90b6`
- `NetSetupApi!NetSetupFreeObjects` at `0x1404a91aa`
- `NetSetupApi!NetSetupFreeObjects` at `0x1404a91e8`
- `NetSetupApi!NetSetupFreeObjects` at `0x1404a921c`
- `NetSetupApi!NetSetupFreeObjects` at `0x1404a91aa`
- `NetSetupApi!NetSetupFreeObjects` at `0x1404a91e8`
- `NetSetupApi!NetSetupFreeObjects` at `0x1404a921c`

## string_xrefs

- `0x1404a8f5e`: `*CompartmentGuid`
- `0x1404a8ca4`: `InstallVirtualMiniportInternal call started`
- `0x1404a92d2`: `InstallVirtualMiniportInternal call ended`

## pseudocode

```c
__int64 __fastcall NetSetupHelper::InstallVirtualMiniportInternal(
        NetSetupHelper *this,
        const unsigned __int16 *a2,
        const BYTE *a3,
        unsigned __int16 *a4,
        struct _GUID *a5)
{
  struct _GUID *v5; // r12
  HKEY DevRegKey; // r13
  __int64 v11; // rcx
  void *v12; // r15
  signed int LastError; // eax
  signed int v14; // ebx
  __int64 v15; // rax
  signed int v16; // eax
  __int64 v17; // rax
  NetSetupHelper *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // r12d
  __int64 v22; // rax
  void *v23; // rbx
  int Objects; // eax
  unsigned int v25; // r14d
  __int64 v26; // rsi
  bool v27; // sf
  NetSetupHelper *v28; // rdi
  _DWORD *v29; // rcx
  signed int v31; // eax
  unsigned int v32; // esi
  __int64 v33; // r9
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  NetSetupHelper *v35; // [rsp+58h] [rbp-A8h]
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  void *DeviceInfoList; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbData; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v43; // [rsp+94h] [rbp-6Ch]
  DWORD Type; // [rsp+98h] [rbp-68h] BYREF
  int v45; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+A4h] [rbp-5Ch]
  GUID pclsid; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v48[3]; // [rsp+C0h] [rbp-40h] BYREF
  int v49; // [rsp+F0h] [rbp-10h]
  __int128 v50; // [rsp+F8h] [rbp-8h]
  int v51; // [rsp+108h] [rbp+8h]
  __int64 v52; // [rsp+10Ch] [rbp+Ch]
  int v53; // [rsp+114h] [rbp+14h]
  int v54; // [rsp+118h] [rbp+18h]
  int v55; // [rsp+11Ch] [rbp+1Ch]
  unsigned __int16 *v56; // [rsp+120h] [rbp+20h]
  OLECHAR Data[40]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v58[200]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v59[264]; // [rsp+310h] [rbp+210h] BYREF

  v5 = a5;
  v38 = (__int64)a3;
  v35 = this;
  v34 = (__int64)a5;
  memset(v48, 0, sizeof(v48));
  memset_0(v59, 0, 0x20Au);
  v45 = 3;
  hKey = 0;
  v46 = 1;
  DevRegKey = 0;
  memset_0(v58, 0, sizeof(v58));
  v11 = *(_QWORD *)this;
  if ( **(_DWORD **)this > 4u )
  {
    v39 = (__int64)a3;
    v36 = (__int64)"InstallVirtualMiniportInternal call started";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v11,
      (int)&unk_140B77B20,
      (__int64)&v39,
      (__int64)&v36);
  }
  v36 = 0;
  wil::AcquireSRWLockExclusive(&v36, &NetSetupHelper::gm_PnpLock);
  DeviceInfoList = (void *)DevObjCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0, 0, 0, 0);
  v12 = DeviceInfoList;
  if ( DeviceInfoList == (void *)-1LL )
    goto LABEL_4;
  LODWORD(v48[0]) = 48;
  if ( !(unsigned int)DevObjCreateDeviceInfo(DeviceInfoList, a2, &GUID_DEVCLASS_NET, 0, 1, v48) )
    goto LABEL_4;
  memset_0(v59, 0, 0x20Au);
  if ( (int)StringCchCopyW(v59, 0x105u, a2) < 0 )
    goto LABEL_4;
  v15 = -1;
  do
    ++v15;
  while ( v59[v15] );
  if ( !(unsigned int)DevObjSetDeviceRegistryProperty(v12, v48, 1, v59, 2 * (int)v15 + 4)
    || !(unsigned int)DevObjRegisterDeviceInfo(v12, v48, 0, 0, 0, 0) )
  {
LABEL_4:
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_82;
  }
  if ( !(unsigned int)DevObjGetDeviceInstanceId(v12, v48, v58, 200, 0) )
    goto LABEL_14;
  DevRegKey = (HKEY)DevObjCreateDevRegKey(v12, v48, 1);
  if ( DevRegKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    DevRegKey = 0;
    goto LABEL_14;
  }
  v14 = RegCreateKeyExW(DevRegKey, L"NetSetupProperties", 0, 0, 0, 2u, 0, &hKey, 0);
  if ( v14 < 0 )
    goto LABEL_77;
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)&a3[2 * v17] );
  v14 = RegSetValueExW(hKey, L"NETSETUPPKEY_Interface_IfAliasBase", 0, 1u, a3, 2 * v17 + 2);
  if ( v14 < 0 )
  {
LABEL_77:
    cbData = 0;
    if ( !(unsigned int)DevObjDeleteDevice(v12, v48, 0, &cbData) )
    {
      v31 = GetLastError();
      v32 = v31;
      if ( v31 > 0 )
        v32 = (unsigned __int16)v31 | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTraceEx(0x4000, &off_140901BE0, v32, v33);
    }
LABEL_82:
    v28 = v35;
    if ( v14 < 0 )
      *v5 = 0;
    goto LABEL_68;
  }
  if ( a4 )
  {
    v19 = -1;
    do
      ++v19;
    while ( a4[v19] );
    v20 = NetSetupHelper::SetAdvancedParameterInPnpSoftwareKey(
            v18,
            &DeviceInfoList,
            (struct _DO_DEVINFO_DATA *)v48,
            L"*CompartmentGuid",
            1u,
            a4,
            2 * v19 + 2);
    v14 = v20;
    if ( v20 )
    {
      if ( v20 > 0 )
        v14 = (unsigned __int16)v20 | 0x80070000;
      v12 = DeviceInfoList;
LABEL_66:
      if ( v14 >= 0 )
      {
        v28 = v35;
        goto LABEL_68;
      }
      goto LABEL_77;
    }
    v12 = DeviceInfoList;
  }
  if ( !(unsigned int)DevObjChangeState(v12, v48, &v45, 0) )
  {
LABEL_14:
    v16 = GetLastError();
    v14 = v16;
    if ( v16 > 0 )
      v14 = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_66;
  }
  v51 = 50;
  v21 = 0;
  v49 = 131074;
  v52 = 0;
  v53 = 0;
  v22 = -1;
  v50 = NETSETUPPKEY_Interface_PnpInstance;
  v54 = 18;
  do
    ++v22;
  while ( v58[v22] );
  v55 = 2 * v22 + 2;
  v56 = v58;
  while ( 1 )
  {
    v43 = 0;
    DeviceInfoList = 0;
    v39 = 0;
    NetSetupSynchronizeDevices(0);
    v23 = DeviceInfoList;
    if ( DeviceInfoList )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v37);
      NetSetupClose(v23);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v37);
    }
    DeviceInfoList = 0;
    v14 = NetSetupInitialize(0, &DeviceInfoList);
    if ( v14 < 0 )
      goto LABEL_62;
    Objects = NetSetupGetObjects(DeviceInfoList, 2, 0);
    v25 = v43;
    v14 = Objects;
    v26 = v39;
    if ( Objects >= 0 )
    {
      if ( v43 )
      {
        memset_0(Data, 0, sizeof(Data));
        cbData = 80;
        Type = 0;
        v14 = RegQueryValueExW(DevRegKey, L"NetCfgInstanceId", 0, &Type, (LPBYTE)Data, &cbData);
        v27 = v14 < 0;
        if ( v14 > 0 )
        {
          v14 = (unsigned __int16)v14 | 0x80070000;
          v27 = v14 < 0;
        }
        if ( !v27 && Type != 1 )
        {
          v14 = -2147023267;
LABEL_56:
          if ( v26 )
            NetSetupFreeObjects(v25, v26);
LABEL_62:
          wil::details::unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&void NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&void NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>(&DeviceInfoList);
LABEL_63:
          if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
            VmlDebugTraceEx(0x4000, &off_140901BC8, v58, (unsigned int)v14);
          v5 = (struct _GUID *)v34;
          goto LABEL_66;
        }
        if ( v14 != -2147024894 )
        {
          if ( v14 < 0 )
            goto LABEL_56;
          pclsid = 0;
          v14 = CLSIDFromString(Data, &pclsid);
          if ( v14 < 0 )
            goto LABEL_56;
          if ( *(_QWORD *)(v39 + 4) == *(_QWORD *)&pclsid.Data1 && *(_QWORD *)(v39 + 12) == *(_QWORD *)pclsid.Data4 )
            break;
        }
      }
    }
    Sleep(0x32u);
    ++v21;
    if ( v26 )
      NetSetupFreeObjects(v25, v26);
    wil::details::unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&void NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&void NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>(&DeviceInfoList);
    if ( v21 > 0x14 )
    {
      if ( v14 >= 0 )
        v14 = -2147217406;
      goto LABEL_63;
    }
  }
  v5 = (struct _GUID *)v34;
  *(GUID *)v34 = pclsid;
  if ( v26 )
    NetSetupFreeObjects(v25, v26);
  wil::details::unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&void NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&void NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>(&DeviceInfoList);
  v28 = v35;
  NetSetupHelper::AbandonNetSetupTransaction(v35);
LABEL_68:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( DevRegKey )
    RegCloseKey(DevRegKey);
  if ( v12 != (void *)-1LL )
    DevObjDestroyDeviceInfoList(v12);
  v29 = *(_DWORD **)v28;
  if ( **(_DWORD **)v28 > 4u )
  {
    cbData = v14;
    v37 = (__int64)"InstallVirtualMiniportInternal call ended";
    v34 = (__int64)v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (int)v29,
      (int)&word_140B77AB2,
      (__int64)&v38,
      (__int64)&v34,
      (__int64)&cbData,
      (__int64)&v37);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v36);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1404a8bfc  push    rbp
0x1404a8bfe  push    rbx
0x1404a8bff  push    rsi
0x1404a8c00  push    rdi
0x1404a8c01  push    r12
0x1404a8c03  push    r13
0x1404a8c05  push    r14
0x1404a8c07  push    r15
0x1404a8c09  lea     rbp, [rsp-438h]
0x1404a8c11  sub     rsp, 538h
0x1404a8c18  mov     rax, cs:__security_cookie
0x1404a8c1f  xor     rax, rsp
0x1404a8c22  mov     [rbp+470h+var_50], rax
0x1404a8c29  mov     r12, [rbp+470h+arg_20]
0x1404a8c30  xorps   xmm0, xmm0
0x1404a8c33  mov     r14, r8
0x1404a8c36  mov     [rsp+570h+var_500], r8
0x1404a8c3b  mov     rbx, rdx
0x1404a8c3e  mov     [rsp+570h+var_518], rcx
0x1404a8c43  mov     rdi, rcx
0x1404a8c46  mov     [rsp+570h+var_520], r12
0x1404a8c4b  xor     edx, edx; Val
0x1404a8c4d  lea     rcx, [rbp+470h+var_260]; void *
0x1404a8c54  mov     r8d, 20Ah; Size
0x1404a8c5a  mov     rsi, r9
0x1404a8c5d  movups  [rbp+470h+var_4B0], xmm0
0x1404a8c61  movups  [rbp+470h+var_4A0], xmm0
0x1404a8c65  movups  [rbp+470h+var_490], xmm0
0x1404a8c69  call    memset_0
0x1404a8c6e  xor     eax, eax
0x1404a8c70  mov     [rbp+470h+var_4D0], 3
0x1404a8c77  xor     edx, edx; Val
0x1404a8c79  mov     [rbp+470h+hKey], rax
0x1404a8c7d  mov     r8d, 190h; Size
0x1404a8c83  mov     [rbp+470h+var_4CC], 1
0x1404a8c8b  lea     rcx, [rbp+470h+var_3F0]; void *
0x1404a8c92  mov     r13d, eax
0x1404a8c95  call    memset_0
0x1404a8c9a  mov     rcx, [rdi]; int
0x1404a8c9d  mov     eax, [rcx]
0x1404a8c9f  cmp     eax, 4
0x1404a8ca2  jbe     short loc_1404A8CD5
0x1404a8ca4  lea     rax, aInstallvirtual_1; "InstallVirtualMiniportInternal call sta"...
0x1404a8cab  mov     [rsp+570h+var_4F8], r14
0x1404a8cb0  mov     [rsp+570h+var_510], rax
0x1404a8cb5  lea     rdx, unk_140B77B20; int
0x1404a8cbc  lea     rax, [rsp+570h+var_510]
0x1404a8cc1  mov     qword ptr [rsp+570h+samDesired], rax; __int64
0x1404a8cc6  lea     rax, [rsp+570h+var_4F8]
0x1404a8ccb  mov     qword ptr [rsp+570h+dwOptions], rax; __int64
0x1404a8cd0  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x1404a8cd5  xor     edi, edi
0x1404a8cd7  lea     rdx, ?gm_PnpLock@NetSetupHelper@@0Vsrwlock@wil@@A; wil::srwlock NetSetupHelper::gm_PnpLock
0x1404a8cde  lea     rcx, [rsp+570h+var_510]
0x1404a8ce3  mov     [rsp+570h+var_510], rdi
0x1404a8ce8  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1404a8ced  xor     r9d, r9d
0x1404a8cf0  mov     qword ptr [rsp+570h+dwOptions], rdi
0x1404a8cf5  xor     r8d, r8d
0x1404a8cf8  lea     rcx, GUID_DEVCLASS_NET
0x1404a8cff  xor     edx, edx
0x1404a8d01  call    cs:__imp_DevObjCreateDeviceInfoList
0x1404a8d08  nop     dword ptr [rax+rax+00h]
0x1404a8d0d  mov     [rbp+470h+var_4E8], rax
0x1404a8d11  mov     r15, rax
0x1404a8d14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1404a8d18  jnz     short loc_1404A8D3D
0x1404a8d1a  call    cs:__imp_GetLastError
0x1404a8d21  nop     dword ptr [rax+rax+00h]
0x1404a8d26  mov     ebx, eax
0x1404a8d28  test    eax, eax
0x1404a8d2a  jle     short loc_1404A8D35
0x1404a8d2c  movzx   ebx, ax
0x1404a8d2f  or      ebx, 80070000h
0x1404a8d35  xor     r14d, r14d
0x1404a8d38  jmp     loc_1404A93B0
0x1404a8d3d  lea     rax, [rbp+470h+var_4B0]
0x1404a8d41  mov     dword ptr [rbp+470h+var_4B0], 30h ; '0'
0x1404a8d48  mov     qword ptr [rsp+570h+samDesired], rax
0x1404a8d4d  lea     r8, GUID_DEVCLASS_NET
0x1404a8d54  xor     r9d, r9d
0x1404a8d57  mov     [rsp+570h+dwOptions], 1
0x1404a8d5f  mov     rdx, rbx
0x1404a8d62  mov     rcx, r15
0x1404a8d65  call    cs:__imp_DevObjCreateDeviceInfo
0x1404a8d6c  nop     dword ptr [rax+rax+00h]
0x1404a8d71  test    eax, eax
0x1404a8d73  jz      short loc_1404A8D1A
0x1404a8d75  xor     edx, edx; Val
0x1404a8d77  lea     rcx, [rbp+470h+var_260]; void *
0x1404a8d7e  mov     r8d, 20Ah; Size
0x1404a8d84  call    memset_0
0x1404a8d89  mov     r8, rbx; unsigned __int16 *
0x1404a8d8c  lea     rcx, [rbp+470h+var_260]; unsigned __int16 *
0x1404a8d93  mov     edx, 105h; unsigned __int64
0x1404a8d98  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1404a8d9d  test    eax, eax
0x1404a8d9f  js      loc_1404A8D1A
0x1404a8da5  lea     rcx, [rbp+470h+var_260]
0x1404a8dac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1404a8db0  inc     rax
0x1404a8db3  cmp     [rcx+rax*2], di
0x1404a8db7  jnz     short loc_1404A8DB0
0x1404a8db9  lea     eax, ds:4[rax*2]
0x1404a8dc0  mov     r8d, 1
0x1404a8dc6  lea     r9, [rbp+470h+var_260]
0x1404a8dcd  mov     [rsp+570h+dwOptions], eax
0x1404a8dd1  lea     rdx, [rbp+470h+var_4B0]
0x1404a8dd5  mov     rcx, r15
0x1404a8dd8  call    cs:__imp_DevObjSetDeviceRegistryProperty
0x1404a8ddf  nop     dword ptr [rax+rax+00h]
0x1404a8de4  test    eax, eax
0x1404a8de6  jz      loc_1404A8D1A
0x1404a8dec  mov     qword ptr [rsp+570h+samDesired], rdi
0x1404a8df1  lea     rdx, [rbp+470h+var_4B0]
0x1404a8df5  xor     r9d, r9d
0x1404a8df8  mov     qword ptr [rsp+570h+dwOptions], rdi
0x1404a8dfd  xor     r8d, r8d
0x1404a8e00  mov     rcx, r15
0x1404a8e03  call    cs:__imp_DevObjRegisterDeviceInfo
0x1404a8e0a  nop     dword ptr [rax+rax+00h]
0x1404a8e0f  test    eax, eax
0x1404a8e11  jz      loc_1404A8D1A
0x1404a8e17  mov     r9d, 0C8h
0x1404a8e1d  mov     qword ptr [rsp+570h+dwOptions], rdi
0x1404a8e22  lea     r8, [rbp+470h+var_3F0]
0x1404a8e29  mov     rcx, r15
0x1404a8e2c  lea     rdx, [rbp+470h+var_4B0]
0x1404a8e30  call    cs:__imp_DevObjGetDeviceInstanceId
0x1404a8e37  nop     dword ptr [rax+rax+00h]
0x1404a8e3c  xor     ebx, ebx
0x1404a8e3e  mov     edi, 80070000h
0x1404a8e43  test    eax, eax
0x1404a8e45  jnz     short loc_1404A8E6A
0x1404a8e47  call    cs:__imp_GetLastError
0x1404a8e4e  nop     dword ptr [rax+rax+00h]
0x1404a8e53  xor     r14d, r14d
0x1404a8e56  mov     ebx, eax
0x1404a8e58  test    eax, eax
0x1404a8e5a  jle     loc_1404A9279
0x1404a8e60  movzx   ebx, ax
0x1404a8e63  or      ebx, edi
0x1404a8e65  jmp     loc_1404A9279
0x1404a8e6a  xor     r9d, r9d
0x1404a8e6d  mov     qword ptr [rsp+570h+samDesired], rbx
0x1404a8e72  lea     rdx, [rbp+470h+var_4B0]
0x1404a8e76  mov     [rsp+570h+dwOptions], 2
0x1404a8e7e  mov     rcx, r15
0x1404a8e81  lea     r8d, [r9+1]
0x1404a8e85  call    cs:__imp_DevObjCreateDevRegKey
0x1404a8e8c  nop     dword ptr [rax+rax+00h]
0x1404a8e91  mov     r13, rax
0x1404a8e94  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1404a8e98  jnz     short loc_1404A8EAE
0x1404a8e9a  xor     r14d, r14d
0x1404a8e9d  mov     r13d, r14d
0x1404a8ea0  call    cs:__imp_GetLastError
0x1404a8ea7  nop     dword ptr [rax+rax+00h]
0x1404a8eac  jmp     short loc_1404A8E56
0x1404a8eae  mov     [rsp+570h+lpdwDisposition], rbx; lpdwDisposition
0x1404a8eb3  lea     rax, [rbp+470h+hKey]
0x1404a8eb7  mov     [rsp+570h+phkResult], rax; phkResult
0x1404a8ebc  lea     rdx, aNetsetupproper; "NetSetupProperties"
0x1404a8ec3  mov     [rsp+570h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1404a8ec8  xor     r9d, r9d; lpClass
0x1404a8ecb  mov     [rsp+570h+samDesired], 2; samDesired
0x1404a8ed3  xor     r8d, r8d; Reserved
0x1404a8ed6  mov     rcx, r13; hKey
0x1404a8ed9  mov     [rsp+570h+dwOptions], ebx; dwOptions
0x1404a8edd  call    cs:__imp_RegCreateKeyExW
0x1404a8ee4  nop     dword ptr [rax+rax+00h]
0x1404a8ee9  xor     ecx, ecx
0x1404a8eeb  mov     ebx, eax
0x1404a8eed  test    eax, eax
0x1404a8eef  js      loc_1404A9353
0x1404a8ef5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1404a8ef9  inc     rax
0x1404a8efc  cmp     [r14+rax*2], cx
0x1404a8f01  jnz     short loc_1404A8EF9
0x1404a8f03  mov     rcx, [rbp+470h+hKey]; hKey
0x1404a8f07  lea     eax, ds:2[rax*2]
0x1404a8f0e  mov     [rsp+570h+samDesired], eax; cbData
0x1404a8f12  lea     rdx, aNetsetuppkeyIn; "NETSETUPPKEY_Interface_IfAliasBase"
0x1404a8f19  mov     r9d, 1; dwType
0x1404a8f1f  mov     qword ptr [rsp+570h+dwOptions], r14; lpData
0x1404a8f24  xor     r8d, r8d; Reserved
0x1404a8f27  call    cs:__imp_RegSetValueExW
0x1404a8f2e  nop     dword ptr [rax+rax+00h]
0x1404a8f33  xor     r14d, r14d
0x1404a8f36  mov     ebx, eax
0x1404a8f38  test    eax, eax
0x1404a8f3a  js      loc_1404A9356
0x1404a8f40  test    rsi, rsi
0x1404a8f43  jz      short loc_1404A8F99
0x1404a8f45  or      rax, 0FFFFFFFFFFFFFFFFh
0x1404a8f49  inc     rax
0x1404a8f4c  cmp     [rsi+rax*2], r14w
0x1404a8f51  jnz     short loc_1404A8F49
0x1404a8f53  lea     eax, ds:2[rax*2]
0x1404a8f5a  mov     dword ptr [rsp+570h+lpSecurityAttributes], eax; unsigned int
0x1404a8f5e  lea     r9, ?NvspWmiPvtCompartmentGuidKeyword@@3QBGB; "*CompartmentGuid"
0x1404a8f65  mov     qword ptr [rsp+570h+samDesired], rsi; void *
0x1404a8f6a  lea     r8, [rbp+470h+var_4B0]; struct _DO_DEVINFO_DATA *
0x1404a8f6e  lea     rdx, [rbp+470h+var_4E8]; void **
0x1404a8f72  mov     [rsp+570h+dwOptions], 1; unsigned int
0x1404a8f7a  call    ?SetAdvancedParameterInPnpSoftwareKey@NetSetupHelper@@QEAAKPEAPEAXPEAU_DO_DEVINFO_DATA@@PEBGKPEAXK@Z; NetSetupHelper::SetAdvancedParameterInPnpSoftwareKey(void * *,_DO_DEVINFO_DATA *,ushort const *,ulong,void *,ulong)
0x1404a8f7f  mov     ebx, eax
0x1404a8f81  test    eax, eax
0x1404a8f83  jz      short loc_1404A8F95
0x1404a8f85  jle     short loc_1404A8F8C
0x1404a8f87  movzx   ebx, ax
0x1404a8f8a  or      ebx, edi
0x1404a8f8c  mov     r15, [rbp+470h+var_4E8]
0x1404a8f90  jmp     loc_1404A9279
0x1404a8f95  mov     r15, [rbp+470h+var_4E8]
0x1404a8f99  xor     r9d, r9d
0x1404a8f9c  lea     r8, [rbp+470h+var_4D0]
0x1404a8fa0  lea     rdx, [rbp+470h+var_4B0]
0x1404a8fa4  mov     rcx, r15
0x1404a8fa7  call    cs:__imp_DevObjChangeState
0x1404a8fae  nop     dword ptr [rax+rax+00h]
0x1404a8fb3  test    eax, eax
0x1404a8fb5  jz      loc_1404A8EA0
0x1404a8fbb  mov     eax, cs:dword_140962E78
0x1404a8fc1  lea     rcx, [rbp+470h+var_3F0]
0x1404a8fc8  movups  xmm0, cs:NETSETUPPKEY_Interface_PnpInstance
0x1404a8fcf  mov     [rbp+470h+var_468], eax
0x1404a8fd2  mov     r12d, r14d
0x1404a8fd5  xor     eax, eax
0x1404a8fd7  mov     [rbp+470h+var_480], 20002h
0x1404a8fde  mov     [rbp+470h+var_464], rax
0x1404a8fe2  mov     [rbp+470h+var_45C], eax
0x1404a8fe5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1404a8fe9  movups  [rbp+470h+var_478], xmm0
0x1404a8fed  mov     [rbp+470h+var_458], 12h
0x1404a8ff4  inc     rax
0x1404a8ff7  cmp     [rcx+rax*2], r14w
0x1404a8ffc  jnz     short loc_1404A8FF4
0x1404a8ffe  lea     eax, ds:2[rax*2]
0x1404a9005  mov     [rbp+470h+var_454], eax
0x1404a9008  lea     rax, [rbp+470h+var_3F0]
0x1404a900f  mov     [rbp+470h+var_450], rax
0x1404a9013  xor     ecx, ecx
0x1404a9015  mov     [rbp+470h+var_4DC], r14d
0x1404a9019  mov     [rbp+470h+var_4E8], r14
0x1404a901d  mov     [rsp+570h+var_4F8], r14
0x1404a9022  call    cs:__imp_NetSetupSynchronizeDevices
0x1404a9029  nop     dword ptr [rax+rax+00h]
0x1404a902e  mov     rbx, [rbp+470h+var_4E8]
0x1404a9032  test    rbx, rbx
0x1404a9035  jz      short loc_1404A905A
0x1404a9037  lea     rcx, [rsp+570h+var_508]; this
0x1404a903c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1404a9041  mov     rcx, rbx
0x1404a9044  call    cs:__imp_NetSetupClose
0x1404a904b  nop     dword ptr [rax+rax+00h]
0x1404a9050  lea     rcx, [rsp+570h+var_508]; this
0x1404a9055  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1404a905a  lea     rdx, [rbp+470h+var_4E8]
0x1404a905e  mov     [rbp+470h+var_4E8], r14
0x1404a9062  xor     ecx, ecx
0x1404a9064  call    cs:__imp_NetSetupInitialize
0x1404a906b  nop     dword ptr [rax+rax+00h]
0x1404a9070  mov     ebx, eax
0x1404a9072  test    eax, eax
0x1404a9074  js      loc_1404A9243
0x1404a907a  mov     rcx, [rbp+470h+var_4E8]
0x1404a907e  lea     rax, [rsp+570h+var_4F8]
0x1404a9083  mov     [rsp+570h+var_528], rax
0x1404a9088  xor     r9d, r9d
0x1404a908b  lea     rax, [rbp+470h+var_4DC]
0x1404a908f  xor     r8d, r8d
0x1404a9092  mov     [rsp+570h+lpdwDisposition], rax
0x1404a9097  lea     rax, [rbp+470h+var_480]
0x1404a909b  mov     [rsp+570h+phkResult], rax
0x1404a90a0  mov     dword ptr [rsp+570h+lpSecurityAttributes], 1
0x1404a90a8  lea     edx, [r9+2]
0x1404a90ac  mov     qword ptr [rsp+570h+samDesired], r14
0x1404a90b1  mov     [rsp+570h+dwOptions], r14d
0x1404a90b6  call    cs:__imp_NetSetupGetObjects
0x1404a90bd  nop     dword ptr [rax+rax+00h]
0x1404a90c2  mov     r14d, [rbp+470h+var_4DC]
0x1404a90c6  mov     ebx, eax
0x1404a90c8  mov     rsi, [rsp+570h+var_4F8]
0x1404a90cd  test    eax, eax
0x1404a90cf  js      loc_1404A918B
0x1404a90d5  test    r14d, r14d
0x1404a90d8  jz      loc_1404A918B
0x1404a90de  mov     ebx, 50h ; 'P'
0x1404a90e3  lea     rcx, [rbp+470h+Data]; void *
0x1404a90e7  mov     r8d, ebx; Size
0x1404a90ea  xor     edx, edx; Val
0x1404a90ec  call    memset_0
0x1404a90f1  xor     ecx, ecx
0x1404a90f3  mov     [rbp+470h+cbData], ebx
0x1404a90f6  lea     rax, [rbp+470h+cbData]
0x1404a90fa  mov     [rbp+470h+Type], ecx
0x1404a90fd  mov     qword ptr [rsp+570h+samDesired], rax; lpcbData
0x1404a9102  lea     r9, [rbp+470h+Type]; lpType
0x1404a9106  lea     rax, [rbp+470h+Data]
  ... truncated ...
```
