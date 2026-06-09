# StorageService::UpdateAppPairingState(_STORAGE_DEVICE_TYPE,ulong,ulong)

- ea: `0x18002b474`
- end: `0x18002bd74`
- name: `?UpdateAppPairingState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z`
- size: `2304`
- prototype: ``
- caller_count: `5`
- callee_count: `28`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x180020140`
- `0x18002675c`
- `0x180027080`
- `0x18002bd7c`
- `0x18002bebc`

## callees

- `0x180001148`
- `0x180001174`
- `0x180001248`
- `0x1800013c4`
- `0x1800016b8`
- `0x180001d84`
- `0x18000d030`
- `0x18000d450`
- `0x18000ddb0`
- `0x180012ce0`
- `0x180014a00`
- `0x18001dc9c`
- `0x18001e8d4`
- `0x18001e9e4`
- `0x18001ea50`
- `0x18001ea9c`
- `0x18001eae8`
- `0x18001ec28`
- `0x18001f884`
- `0x180022eec`
- `0x1800282b8`
- `0x18002b0ac`
- `0x18002b474`
- `0x18002c460`
- `0x18002c834`
- `0x18002cb2c`
- `0x18002cebc`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b583`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bab7`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002b650`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002baad`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002b650`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002baad`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b719`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b719`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall StorageService::UpdateAppPairingState(__int64 a1, signed int a2, unsigned int a3, int a4)
{
  unsigned int v6; // edi
  int AppPairingStatus; // ebx
  const unsigned __int16 *v9; // rdx
  int *v10; // r9
  bool IsZero; // al
  struct _GUID *v12; // r9
  void *v13; // rcx
  signed int v14; // esi
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // r15
  signed int LastError; // eax
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // rdi
  unsigned int (__fastcall *v22)(__int64, PVOID, struct Windows::Management::Deployment::IPackageVolume **); // rbx
  StorageService *v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rdi
  unsigned int (__fastcall *v27)(__int64, _QWORD, struct Windows::Management::Deployment::IPackageVolume **); // rbx
  __int64 v28; // rax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, PVOID, __int64 *); // rbx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rcx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, struct Windows::Management::Deployment::IPackageVolume *, __int64 *); // rbx
  int v37; // ecx
  int v38; // r8d
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, struct Windows::Management::Deployment::IPackageVolume *, __int64 *); // rbx
  int v41; // ecx
  int v42; // r8d
  signed int v43; // eax
  unsigned __int64 v44; // rcx
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, PVOID, __int64 *); // rbx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rdi
  __int64 (__fastcall *v50)(__int64, struct Windows::Management::Deployment::IPackageVolume *, __int64 *); // rbx
  int v51; // ecx
  int v52; // r8d
  StorageNotify *v53; // rcx
  __int64 v54; // [rsp+20h] [rbp-E0h]
  char v57[8]; // [rsp+58h] [rbp-A8h] BYREF
  struct Windows::Management::Deployment::IPackageVolume *v58; // [rsp+60h] [rbp-A0h] BYREF
  int v59; // [rsp+68h] [rbp-98h] BYREF
  __int64 v60; // [rsp+70h] [rbp-90h] BYREF
  __int64 v61; // [rsp+78h] [rbp-88h] BYREF
  __int64 v62; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v63; // [rsp+88h] [rbp-78h] BYREF
  WCHAR *v64; // [rsp+90h] [rbp-70h] BYREF
  __int64 v65; // [rsp+98h] [rbp-68h] BYREF
  __int64 v66; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v68; // [rsp+B0h] [rbp-50h] BYREF
  int v69; // [rsp+B8h] [rbp-48h] BYREF
  char v70; // [rsp+BCh] [rbp-44h]
  _BYTE v71[16]; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v72; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER string; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v74; // [rsp+F8h] [rbp-8h]
  OLECHAR sz[2]; // [rsp+100h] [rbp+0h] BYREF
  char v76[76]; // [rsp+104h] [rbp+4h] BYREF
  WCHAR szVolumeName[2]; // [rsp+150h] [rbp+50h] BYREF
  char v78[620]; // [rsp+154h] [rbp+54h] BYREF
  WCHAR sourceString[2]; // [rsp+3C0h] [rbp+2C0h] BYREF
  char v80[524]; // [rsp+3C4h] [rbp+2C4h] BYREF

  v6 = a2;
  v69 = 0;
  v70 = 0;
  *(_DWORD *)sz = 0;
  memset_0(v76, 0, 0x4Au);
  *(_DWORD *)szVolumeName = 0;
  memset_0(v78, 0, 0x260u);
  *(_DWORD *)sourceString = 0;
  memset_0(v80, 0, 0x204u);
  AppPairingStatus = StorageService::GetAppPairingStatus(a1, v6, a3);
  v62 = 0;
  v67 = 0;
  v58 = 0;
  v66 = 0;
  v60 = 0;
  v65 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v69);
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    if ( !v70 || (IsZero = _tlgGuidIsZero(&v72), v12 = &v72, IsZero) )
      v12 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1800BF000,
      &dword_1800A5A74,
      v71,
      v12);
  }
  v13 = *(void **)(a1 + 1672);
  if ( v13 )
    WaitForSingleObject(v13, 0xFFFFFFFF);
  if ( (a4 & 2) != 0 && !(unsigned int)StorageService::SupportsAppXInstall(a1, v6, a3) )
  {
    v14 = -2147024846;
LABEL_40:
    v32 = a3;
    goto LABEL_41;
  }
  v59 = a4 & 0x10;
  if ( (a4 & 0x10) != 0 && (!a2 && !a3 || a4 != 16) )
  {
    v14 = -2147024809;
LABEL_39:
    v6 = a2;
    goto LABEL_40;
  }
  v15 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                    (HSTRING *)&string,
                    (const unsigned __int16 (*)[62])v9);
  v14 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
          *v15,
          &v67);
  if ( v14 < 0 )
    goto LABEL_39;
  v16 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                    (HSTRING *)&string,
                    (const unsigned __int16 (*)[45])v9);
  v14 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>(
          *v16,
          &v62);
  if ( v14 < 0 )
    goto LABEL_39;
  if ( AppPairingStatus != 2 && (a4 & 0x10) == 0 )
    goto LABEL_82;
  v17 = -1;
  v6 = a2;
  if ( a2 || a3 )
  {
    v61 = a3;
    v63 = (const unsigned __int16 *)a2;
    if ( !StringFromGUID2((const GUID *const)(*(_QWORD *)(a1 + 8LL * a2 + 40) + 548LL + 1112LL * a3), sz, 39) )
    {
      v14 = -2147024809;
      goto LABEL_40;
    }
    v26 = v67;
    v27 = *(unsigned int (__fastcall **)(__int64, _QWORD, struct Windows::Management::Deployment::IPackageVolume **))(*(_QWORD *)v67 + 232LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, sz);
    v23 = (StorageService *)v27(v26, *(_QWORD *)(v28 + 24), &v58);
    v74 = 0;
    v25 = v61;
    v9 = v63;
  }
  else
  {
    if ( !GetVolumeNameForVolumeMountPointW((LPCWSTR)(*(_QWORD *)(a1 + 40) + 4LL), szVolumeName, 0x104u) )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_40;
    }
    v19 = -1;
    do
      ++v19;
    while ( szVolumeName[v19] );
    v20 = 2 * v19 - 2;
    if ( v20 >= 0x264 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v20) = 0;
    v21 = v62;
    v22 = *(unsigned int (__fastcall **)(__int64, PVOID, struct Windows::Management::Deployment::IPackageVolume **))(*(_QWORD *)v62 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
    Windows::Internal::StringReference::_ConstructorHelper((HSTRING *)&string, szVolumeName);
    v23 = (StorageService *)v22(v21, string.Reserved.Reserved1, &v58);
    v25 = 0;
    v61 = 0;
    v9 = 0;
    v63 = 0;
  }
  if ( (_DWORD)v23 != -2147023728 )
  {
    if ( (int)v23 >= 0 )
      goto LABEL_47;
LABEL_84:
    if ( v58 )
      goto LABEL_86;
    goto LABEL_85;
  }
  if ( (a4 & 1) == 0 )
    goto LABEL_84;
  v14 = StringCchPrintfW(
          sourceString,
          0x104u,
          L"%sWindowsApps",
          *(_QWORD *)(a1 + 8LL * (_QWORD)v9 + 40) + 4LL + 1112 * v25);
  if ( v14 < 0 )
    goto LABEL_39;
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    v64 = sourceString;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)&dword_1800A65BC,
      (unsigned int)v71,
      0,
      (__int64)&v64);
  }
  v29 = v62;
  v30 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v62 + 48LL);
  Windows::Internal::StringReference::_ConstructorHelper((HSTRING *)&string, sourceString);
  v14 = v30(v29, string.Reserved.Reserved1, &v65);
  if ( v14 < 0 )
    goto LABEL_39;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
  v14 = Windows::Management::Deployment::WaitForPackageVolumeOperation(v65, v31, &v58);
  if ( v14 < 0 )
    goto LABEL_39;
LABEL_47:
  if ( !v58 )
  {
LABEL_85:
    LODWORD(v23) = -2147023728;
LABEL_86:
    if ( (unsigned int)dword_1800BF000 > 5 )
    {
      LODWORD(v61) = (_DWORD)v23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BF000,
        (unsigned int)&word_1800A5C46,
        (unsigned int)v71,
        (_DWORD)v10,
        (__int64)&v61);
    }
    goto LABEL_39;
  }
  if ( (a4 & 2) != 0 )
  {
    if ( (unsigned int)dword_1800BF000 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1800BF000,
        qword_1800A6D28,
        v71,
        0);
    v35 = v62;
    v36 = *(__int64 (__fastcall **)(__int64, struct Windows::Management::Deployment::IPackageVolume *, __int64 *))(*(_QWORD *)v62 + 144LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    v14 = v36(v35, v58, &v60);
    if ( v14 < 0 )
      goto LABEL_39;
    v14 = Windows::Management::Deployment::WaitForDeploymentOperation(v37, v60, v38, (_DWORD)v10, v54);
    if ( v14 < 0 )
      goto LABEL_39;
  }
  if ( (a4 & 4) != 0 )
  {
    if ( (unsigned int)dword_1800BF000 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1800BF000,
        byte_1800A727B,
        v71,
        0);
    v57[0] = 0;
    v14 = (*(__int64 (__fastcall **)(struct Windows::Management::Deployment::IPackageVolume *, char *))(*(_QWORD *)v58 + 48LL))(
            v58,
            v57);
    if ( v14 < 0 )
      goto LABEL_39;
    if ( !v57[0] )
    {
      v39 = v62;
      v40 = *(__int64 (__fastcall **)(__int64, struct Windows::Management::Deployment::IPackageVolume *, __int64 *))(*(_QWORD *)v62 + 136LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
      v14 = v40(v39, v58, &v60);
      if ( v14 < 0 )
        goto LABEL_39;
      v14 = Windows::Management::Deployment::WaitForDeploymentOperation(v41, v60, v42, (_DWORD)v10, v54);
      if ( v14 < 0 )
        goto LABEL_39;
    }
    if ( (unsigned int)dword_1800BF000 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1800BF000,
        &byte_1800A5CB7,
        v71,
        0);
    if ( !GetVolumeNameForVolumeMountPointW((LPCWSTR)(*(_QWORD *)(a1 + 40) + 4LL), szVolumeName, 0x104u) )
    {
      v43 = GetLastError();
      v14 = v43;
      if ( v43 > 0 )
        v14 = (unsigned __int16)v43 | 0x80070000;
      goto LABEL_39;
    }
    do
      ++v17;
    while ( szVolumeName[v17] );
    v44 = 2 * v17 - 2;
    if ( v44 >= 0x264 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v44) = 0;
    v45 = v62;
    v46 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v62 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
    Windows::Internal::StringReference::_ConstructorHelper((HSTRING *)&string, szVolumeName);
    v14 = v46(v45, string.Reserved.Reserved1, &v66);
    if ( v14 < 0 )
      goto LABEL_39;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 120LL))(v62, v66);
    if ( v14 < 0 )
      goto LABEL_39;
  }
  if ( v59 )
  {
    v24 = (unsigned int)StorageService::RemoveAppxPackagesAndVolume(v23, v58);
    if ( (unsigned int)dword_1800BF000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
      {
        v59 = v24;
        v47 = 1112 * v61;
        v48 = *(_QWORD *)(a1 + 8LL * (_QWORD)v63 + 40);
        LODWORD(v64) = *(_DWORD *)(v48 + 1112 * v61 + 1100);
        LODWORD(v63) = *(_DWORD *)(v48 + 1112 * v61 + 1096);
        LODWORD(v61) = a2;
        v68 = v48 + v47 + 548;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v48,
          (unsigned int)word_1800A7002,
          v24,
          (_DWORD)v10,
          (__int64)&v68,
          (__int64)&v61,
          (__int64)&v63,
          (__int64)&v64,
          (__int64)&v59);
      }
    }
  }
  if ( (a4 & 8) != 0 )
  {
    if ( (unsigned int)dword_1800BF000 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1800BF000,
        byte_1800A5B8B,
        v71,
        0);
    v14 = (*(__int64 (__fastcall **)(__int64, struct Windows::Management::Deployment::IPackageVolume *, __int64))(*(_QWORD *)v62 + 120LL))(
            v62,
            v58,
            v24);
    if ( v14 < 0 )
      goto LABEL_39;
  }
  if ( (a4 & 0x20) != 0 )
  {
    if ( (unsigned int)dword_1800BF000 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1800BF000,
        &byte_1800A7487,
        v71,
        0);
    v49 = v67;
    v50 = *(__int64 (__fastcall **)(__int64, struct Windows::Management::Deployment::IPackageVolume *, __int64 *))(*(_QWORD *)v67 + 496LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    v14 = v50(v49, v58, &v60);
    if ( v14 < 0 )
      goto LABEL_39;
    v14 = Windows::Management::Deployment::WaitForDeploymentOperation(v51, v60, v52, (_DWORD)v10, v54);
    if ( v14 < 0 )
      goto LABEL_39;
  }
LABEL_82:
  v6 = a2;
  v32 = a3;
  v53 = (StorageNotify *)(1112LL * a3);
  if ( *(_DWORD *)((char *)v53 + *(_QWORD *)(a1 + 8LL * a2 + 40) + 564) == 2 )
  {
    StorageNotify::PublishState(v53, WNF_OSWN_STORAGE_APP_PAIRING_CHANGE, *(_DWORD *)(a1 + 16), v10);
    goto LABEL_40;
  }
LABEL_41:
  v69 = 2;
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    LODWORD(v61) = v14;
    LODWORD(v63) = a4;
    LODWORD(v64) = v32;
    v59 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)&unk_1800A6EC0,
      (unsigned int)v71,
      (_DWORD)v10,
      (__int64)&v59,
      (__int64)&v64,
      (__int64)&v63,
      (__int64)&v61);
  }
  v33 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v33 + 16LL))(v33, v9, v32);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v69);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002b474  mov     [rsp-8+arg_18], rbx
0x18002b479  push    rbp
0x18002b47a  push    rsi
0x18002b47b  push    rdi
0x18002b47c  push    r12
0x18002b47e  push    r13
0x18002b480  push    r14
0x18002b482  push    r15
0x18002b484  lea     rbp, [rsp-4E0h]
0x18002b48c  sub     rsp, 5E0h
0x18002b493  mov     rax, cs:__security_cookie
0x18002b49a  xor     rax, rsp
0x18002b49d  mov     [rbp+510h+var_40], rax
0x18002b4a4  mov     r12d, r9d
0x18002b4a7  mov     esi, r8d
0x18002b4aa  mov     [rsp+610h+var_5C0], r8d
0x18002b4af  mov     edi, edx
0x18002b4b1  mov     [rsp+610h+var_5BC], edx
0x18002b4b5  mov     r14, rcx
0x18002b4b8  xor     r15d, r15d
0x18002b4bb  mov     [rbp+510h+var_558], r15d
0x18002b4bf  mov     [rbp+510h+var_554], r15b
0x18002b4c3  mov     dword ptr [rbp+510h+sz], r15d
0x18002b4c7  xor     edx, edx; Val
0x18002b4c9  lea     r8d, [r15+4Ah]; Size
0x18002b4cd  lea     rcx, [rbp+510h+var_50C]; void *
0x18002b4d1  call    memset_0
0x18002b4d6  mov     dword ptr [rbp+510h+szVolumeName], r15d
0x18002b4da  xor     edx, edx; Val
0x18002b4dc  mov     r8d, 260h; Size
0x18002b4e2  lea     rcx, [rbp+510h+var_4BC]; void *
0x18002b4e6  call    memset_0
0x18002b4eb  mov     dword ptr [rbp+510h+sourceString], r15d
0x18002b4f2  xor     edx, edx; Val
0x18002b4f4  mov     r8d, 204h; Size
0x18002b4fa  lea     rcx, [rbp+510h+var_24C]; void *
0x18002b501  call    memset_0
0x18002b506  mov     r8d, esi
0x18002b509  mov     edx, edi
0x18002b50b  mov     rcx, r14
0x18002b50e  call    ?GetAppPairingStatus@StorageService@@IEAAKW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::GetAppPairingStatus(_STORAGE_DEVICE_TYPE,ulong)
0x18002b513  mov     ebx, eax
0x18002b515  mov     [rbp+510h+var_590], r15
0x18002b519  mov     [rbp+510h+var_568], r15
0x18002b51d  mov     [rsp+610h+var_5B0], r15
0x18002b522  mov     [rbp+510h+var_570], r15
0x18002b526  mov     [rsp+610h+var_5A0], r15
0x18002b52b  mov     [rbp+510h+var_578], r15
0x18002b52f  lea     rcx, [rbp+510h+var_558]
0x18002b533  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18002b538  mov     eax, cs:dword_1800BF000
0x18002b53e  cmp     eax, 5
0x18002b541  jbe     short loc_18002B574
0x18002b543  cmp     [rbp+510h+var_554], r15b
0x18002b547  jz      short loc_18002B55A
0x18002b549  lea     rcx, [rbp+510h+var_540]; struct _GUID *
0x18002b54d  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18002b552  test    al, al
0x18002b554  lea     r9, [rbp+510h+var_540]
0x18002b558  jz      short loc_18002B55D
0x18002b55a  mov     r9, r15
0x18002b55d  lea     r8, [rbp+510h+var_550]
0x18002b561  lea     rdx, dword_1800A5A74
0x18002b568  lea     rcx, dword_1800BF000
0x18002b56f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002b574  mov     rcx, [r14+688h]; hHandle
0x18002b57b  test    rcx, rcx
0x18002b57e  jz      short loc_18002B589
0x18002b580  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b583  call    cs:__imp_WaitForSingleObject
0x18002b589  mov     r13d, r12d
0x18002b58c  and     r13d, 2
0x18002b590  jz      short loc_18002B5AD
0x18002b592  mov     r8d, esi
0x18002b595  mov     edx, edi
0x18002b597  mov     rcx, r14
0x18002b59a  call    ?SupportsAppXInstall@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::SupportsAppXInstall(_STORAGE_DEVICE_TYPE,ulong)
0x18002b59f  test    eax, eax
0x18002b5a1  jnz     short loc_18002B5AD
0x18002b5a3  mov     esi, 80070032h
0x18002b5a8  jmp     loc_18002B85E
0x18002b5ad  mov     edi, r12d
0x18002b5b0  and     edi, 10h
0x18002b5b3  mov     [rsp+610h+var_5A8], edi
0x18002b5b7  jz      short loc_18002B5D4
0x18002b5b9  cmp     [rsp+610h+var_5BC], 0
0x18002b5be  jnz     short loc_18002B5CE
0x18002b5c0  test    esi, esi
0x18002b5c2  jnz     short loc_18002B5CE
0x18002b5c4  mov     esi, 80070057h
0x18002b5c9  jmp     loc_18002B85A
0x18002b5ce  cmp     r12d, 10h
0x18002b5d2  jnz     short loc_18002B5C4
0x18002b5d4  lea     rcx, [rbp+510h+string]; string
0x18002b5d8  call    ??$?0$0DO@@StringReference@Internal@Windows@@QEAA@AEAY0DO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[62])
0x18002b5dd  lea     rdx, [rbp+510h+var_568]
0x18002b5e1  mov     rcx, [rax]
0x18002b5e4  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x18002b5e9  mov     esi, eax
0x18002b5eb  test    eax, eax
0x18002b5ed  js      loc_18002B85A
0x18002b5f3  lea     rcx, [rbp+510h+string]; string
0x18002b5f7  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x18002b5fc  lea     rdx, [rbp+510h+var_590]
0x18002b600  mov     rcx, [rax]
0x18002b603  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager3@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager3@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>)
0x18002b608  mov     esi, eax
0x18002b60a  test    eax, eax
0x18002b60c  js      loc_18002B85A
0x18002b612  cmp     ebx, 2
0x18002b615  jz      short loc_18002B61F
0x18002b617  test    edi, edi
0x18002b619  jz      loc_18002BCE2
0x18002b61f  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002b623  movsxd  rdi, [rsp+610h+var_5BC]
0x18002b628  xor     ebx, ebx
0x18002b62a  mov     eax, [rsp+610h+var_5C0]
0x18002b62e  test    edi, edi
0x18002b630  jnz     loc_18002B6F1
0x18002b636  test    eax, eax
0x18002b638  jnz     loc_18002B6F1
0x18002b63e  mov     rcx, [r14+28h]
0x18002b642  add     rcx, 4; lpszVolumeMountPoint
0x18002b646  mov     r8d, 104h; cchBufferLength
0x18002b64c  lea     rdx, [rbp+510h+szVolumeName]; lpszVolumeName
0x18002b650  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002b656  test    eax, eax
0x18002b658  jnz     short loc_18002B67B
0x18002b65a  call    cs:__imp_GetLastError
0x18002b660  mov     esi, eax
0x18002b662  xor     r15d, r15d
0x18002b665  test    eax, eax
0x18002b667  jle     loc_18002B85E
0x18002b66d  movzx   esi, ax
0x18002b670  or      esi, 80070000h
0x18002b676  jmp     loc_18002B85E
0x18002b67b  lea     rcx, [rbp+510h+szVolumeName]
0x18002b67f  mov     rax, r15
0x18002b682  inc     rax
0x18002b685  cmp     [rcx+rax*2], bx
0x18002b689  jnz     short loc_18002B682
0x18002b68b  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18002b693  cmp     rcx, 264h
0x18002b69a  jnb     loc_18002BD6E
0x18002b6a0  mov     [rbp+rcx+510h+szVolumeName], bx
0x18002b6a5  mov     rdi, [rbp+510h+var_590]
0x18002b6a9  mov     rax, [rdi]
0x18002b6ac  mov     rbx, [rax+50h]
0x18002b6b0  lea     rcx, [rsp+610h+var_5B0]
0x18002b6b5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b6ba  lea     rdx, [rbp+510h+szVolumeName]; sourceString
0x18002b6be  lea     rcx, [rbp+510h+string]; string
0x18002b6c2  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18002b6c7  lea     r8, [rsp+610h+var_5B0]
0x18002b6cc  mov     rdx, qword ptr [rbp+510h+string]
0x18002b6d0  mov     rcx, rdi
0x18002b6d3  mov     rax, rbx
0x18002b6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6db  mov     ecx, eax
0x18002b6dd  xor     ebx, ebx
0x18002b6df  mov     eax, ebx
0x18002b6e1  mov     [rsp+610h+var_598], rbx
0x18002b6e6  mov     edx, ebx
0x18002b6e8  mov     [rbp+510h+var_588], rbx
0x18002b6ec  jmp     loc_18002B77B
0x18002b6f1  mov     [rsp+610h+var_598], rax
0x18002b6f6  mov     [rbp+510h+var_588], rdi
0x18002b6fa  imul    rcx, rax, 458h
0x18002b701  mov     rax, [r14+rdi*8+28h]
0x18002b706  add     rax, 224h
0x18002b70c  add     rcx, rax; rguid
0x18002b70f  mov     r8d, 27h ; '''; cchMax
0x18002b715  lea     rdx, [rbp+510h+sz]; lpsz
0x18002b719  call    cs:__imp_StringFromGUID2
0x18002b71f  test    eax, eax
0x18002b721  jnz     short loc_18002B730
0x18002b723  mov     esi, 80070057h
0x18002b728  xor     r15d, r15d
0x18002b72b  jmp     loc_18002B85E
0x18002b730  mov     rdi, [rbp+510h+var_568]
0x18002b734  mov     rax, [rdi]
0x18002b737  mov     rbx, [rax+0E8h]
0x18002b73e  lea     rcx, [rsp+610h+var_5B0]
0x18002b743  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b748  lea     rdx, [rbp+510h+sz]; sourceString
0x18002b74c  lea     rcx, [rbp+510h+string]; hstringHeader
0x18002b750  call    ??$?0$0CH@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CH@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[39])
0x18002b755  nop
0x18002b756  lea     r8, [rsp+610h+var_5B0]
0x18002b75b  mov     rdx, [rax+18h]
0x18002b75f  mov     rcx, rdi
0x18002b762  mov     rax, rbx
0x18002b765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b76a  mov     ecx, eax
0x18002b76c  xor     ebx, ebx
0x18002b76e  mov     [rbp+510h+var_518], rbx
0x18002b772  mov     rax, [rsp+610h+var_598]
0x18002b777  mov     rdx, [rbp+510h+var_588]
0x18002b77b  cmp     ecx, 80070490h
0x18002b781  jnz     loc_18002B946
0x18002b787  test    r12b, 1
0x18002b78b  jz      loc_18002BD1B
0x18002b791  imul    r9, rax, 458h
0x18002b798  mov     rax, [r14+rdx*8+28h]
0x18002b79d  add     rax, 4
0x18002b7a1  add     r9, rax
0x18002b7a4  lea     r8, aSwindowsapps; "%sWindowsApps"
0x18002b7ab  mov     edx, 104h; unsigned __int64
0x18002b7b0  lea     rcx, [rbp+510h+sourceString]; unsigned __int16 *
0x18002b7b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b7bc  mov     esi, eax
0x18002b7be  test    eax, eax
0x18002b7c0  js      loc_18002B857
0x18002b7c6  mov     eax, cs:dword_1800BF000
0x18002b7cc  cmp     eax, 5
0x18002b7cf  jbe     short loc_18002B7FF
0x18002b7d1  lea     rax, [rbp+510h+sourceString]
0x18002b7d8  mov     [rbp+510h+var_580], rax
0x18002b7dc  lea     rax, [rbp+510h+var_580]
0x18002b7e0  mov     [rsp+610h+var_5F0], rax
0x18002b7e5  xor     r9d, r9d
0x18002b7e8  lea     r8, [rbp+510h+var_550]
0x18002b7ec  lea     rdx, dword_1800A65BC
0x18002b7f3  lea     rcx, dword_1800BF000
0x18002b7fa  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002b7ff  mov     rdi, [rbp+510h+var_590]
0x18002b803  mov     rax, [rdi]
0x18002b806  mov     rbx, [rax+30h]
0x18002b80a  lea     rdx, [rbp+510h+sourceString]; sourceString
0x18002b811  lea     rcx, [rbp+510h+string]; string
0x18002b815  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18002b81a  lea     r8, [rbp+510h+var_578]
0x18002b81e  mov     rdx, qword ptr [rbp+510h+string]
0x18002b822  mov     rcx, rdi
0x18002b825  mov     rax, rbx
0x18002b828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b82d  mov     esi, eax
0x18002b82f  xor     ebx, ebx
0x18002b831  test    eax, eax
0x18002b833  js      short loc_18002B857
0x18002b835  lea     rcx, [rsp+610h+var_5B0]
0x18002b83a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b83f  lea     r8, [rsp+610h+var_5B0]
0x18002b844  mov     rcx, [rbp+510h+var_578]
0x18002b848  call    ?WaitForPackageVolumeOperation@Deployment@Management@Windows@@YAJPEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@3@PEAU?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@53@PEAPEAUIPackageVolume@123@@Z; Windows::Management::Deployment::WaitForPackageVolumeOperation(Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *> *,Windows::Management::Deployment::IPackageVolume * *)
0x18002b84d  mov     esi, eax
0x18002b84f  test    eax, eax
0x18002b851  jns     loc_18002B94E
0x18002b857  xor     r15d, r15d
0x18002b85a  mov     edi, [rsp+610h+var_5BC]
0x18002b85e  mov     r8d, [rsp+610h+var_5C0]
0x18002b863  mov     [rbp+510h+var_558], 2
0x18002b86a  mov     eax, cs:dword_1800BF000
0x18002b870  cmp     eax, 5
0x18002b873  jbe     short loc_18002B8C3
0x18002b875  mov     dword ptr [rsp+610h+var_598], esi
0x18002b879  mov     dword ptr [rbp+510h+var_588], r12d
0x18002b87d  mov     dword ptr [rbp+510h+var_580], r8d
0x18002b881  mov     [rsp+610h+var_5A8], edi
0x18002b885  lea     rax, [rsp+610h+var_598]
0x18002b88a  mov     [rsp+610h+var_5D8], rax
0x18002b88f  lea     rax, [rbp+510h+var_588]
0x18002b893  mov     [rsp+610h+var_5E0], rax
0x18002b898  lea     rax, [rbp+510h+var_580]
0x18002b89c  mov     [rsp+610h+var_5E8], rax
0x18002b8a1  lea     rax, [rsp+610h+var_5A8]
0x18002b8a6  mov     [rsp+610h+var_5F0], rax
0x18002b8ab  lea     r8, [rbp+510h+var_550]
0x18002b8af  lea     rdx, unk_1800A6EC0
0x18002b8b6  lea     rcx, dword_1800BF000
0x18002b8bd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002b8c2  nop
0x18002b8c3  mov     rcx, [rbp+510h+var_578]
0x18002b8c7  test    rcx, rcx
0x18002b8ca  jz      short loc_18002B8DD
0x18002b8cc  mov     [rbp+510h+var_578], r15
0x18002b8d0  mov     rax, [rcx]
0x18002b8d3  mov     rax, [rax+10h]
0x18002b8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8dc  nop
0x18002b8dd  lea     rcx, [rsp+610h+var_5A0]
0x18002b8e2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b8e7  nop
0x18002b8e8  lea     rcx, [rbp+510h+var_570]
0x18002b8ec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b8f1  nop
0x18002b8f2  lea     rcx, [rsp+610h+var_5B0]
0x18002b8f7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b8fc  nop
0x18002b8fd  lea     rcx, [rbp+510h+var_568]
0x18002b901  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b906  nop
0x18002b907  lea     rcx, [rbp+510h+var_590]
0x18002b90b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b910  nop
0x18002b911  lea     rcx, [rbp+510h+var_558]
0x18002b915  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18002b91a  mov     eax, esi
0x18002b91c  mov     rcx, [rbp+510h+var_40]
0x18002b923  xor     rcx, rsp; StackCookie
  ... truncated ...
```
