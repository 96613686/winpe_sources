# StorageService::ProcessVolumeChange(void)

- ea: `0x180027080`
- end: `0x18002784f`
- name: `?ProcessVolumeChange@StorageService@@QEAAJXZ`
- size: `1999`
- prototype: `__int64 __fastcall(StorageService *__hidden this)`
- caller_count: `8`
- callee_count: `36`
- tags: `reparse_path, service_task, installer_update`

## callers

- `0x18001e9b0`
- `0x180020140`
- `0x1800218d0`
- `0x180025f5c`
- `0x18002901c`
- `0x18002ab70`
- `0x18002c440`
- `0x180037890`

## callees

- `0x1800010a8`
- `0x180001148`
- `0x180001174`
- `0x180001248`
- `0x1800020c4`
- `0x18000d030`
- `0x18000d450`
- `0x18000ddb0`
- `0x180012c9c`
- `0x18001768c`
- `0x180018fb8`
- `0x180019234`
- `0x18001b660`
- `0x18001c130`
- `0x18001c208`
- `0x18001dc9c`
- `0x18001f634`
- `0x18001f884`
- `0x18001fdd8`
- `0x18001feb8`
- `0x180020088`
- `0x1800200e8`
- `0x180020d2c`
- `0x180023a64`
- `0x180024480`
- `0x180025bf8`
- `0x180025e40`
- `0x180025efc`
- `0x18002629c`
- `0x180026bfc`
- `0x180027080`
- `0x180029e68`
- `0x18002b474`
- `0x18002bd7c`
- `0x18002c080`
- `0x18002cebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800270da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800270da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800276fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800276fe`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800271d4`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800275a9`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800271d4`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800275a9`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1800270b7`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1800270b7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800272cb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800272cb`

## string_xrefs

- `0x1800276ae`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall StorageService::ProcessVolumeChange(StorageService *this)
{
  unsigned int v2; // edi
  DWORD v3; // r14d
  bool IsZero; // al
  struct _GUID *v5; // r9
  _DWORD *v6; // r13
  _DWORD *v7; // r15
  unsigned __int128 v8; // kr00_16
  __int64 v9; // rdi
  __int64 v10; // rsi
  int v11; // r12d
  int v12; // eax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // r8
  __int64 v15; // rax
  int v16; // r13d
  __int64 v17; // r15
  __int64 v18; // rax
  int v19; // r9d
  int v20; // r9d
  __int64 v21; // rcx
  unsigned int v22; // r12d
  char v23; // r15
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // r8
  StorageService *v26; // rcx
  int v27; // r9d
  unsigned int v28; // esi
  __int64 v29; // rcx
  int v30; // eax
  int v31; // r9d
  int v33; // r9d
  int v34; // [rsp+20h] [rbp-E0h]
  int v35[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+4Ch] [rbp-B4h] BYREF
  int v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v39; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42; // [rsp+68h] [rbp-98h] BYREF
  WCHAR *v43; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v44; // [rsp+78h] [rbp-88h]
  __int128 v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+90h] [rbp-70h]
  __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  __int128 v48; // [rsp+A0h] [rbp-60h]
  int v49; // [rsp+B0h] [rbp-50h] BYREF
  char v50; // [rsp+B4h] [rbp-4Ch]
  _BYTE v51[16]; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v52; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v53[40]; // [rsp+D8h] [rbp-28h] BYREF
  char v54[32]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h]
  unsigned int *v57; // [rsp+130h] [rbp+30h]
  __int64 v58; // [rsp+138h] [rbp+38h]
  int *v59; // [rsp+140h] [rbp+40h]
  __int64 v60; // [rsp+148h] [rbp+48h]
  int *v61; // [rsp+150h] [rbp+50h]
  __int64 v62; // [rsp+158h] [rbp+58h]
  wchar_t v63[264]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR szVolumeMountPoint[4]; // [rsp+370h] [rbp+270h] BYREF
  char v65[520]; // [rsp+378h] [rbp+278h] BYREF
  WCHAR szVolumeName[264]; // [rsp+580h] [rbp+480h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7E8h] [rbp+6E8h]

  v2 = 0;
  v41 = 0;
  v3 = GetLogicalDrives() & ~*((_DWORD *)this + 6);
  v36 = v3;
  v49 = 0;
  v50 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v49);
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    if ( !v50 || (IsZero = _tlgGuidIsZero(&v52), v5 = &v52, IsZero) )
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1800BF000,
      byte_1800A7325,
      v51,
      v5);
  }
  StorageService::GetCurrentTrackedDeviceList(this, &v45);
  __SET_PAIR__((unsigned __int64)v6, (unsigned __int64)v7, v45);
  v8 = v45;
  v44 = (_DWORD *)(v8 >> 64);
  *(_QWORD *)v35 = v8;
  if ( (_QWORD)v45 != *((_QWORD *)&v45 + 1) )
  {
    do
    {
      v9 = (int)v7[1];
      v10 = (unsigned int)v7[2];
      v11 = 1 << *v7;
      v12 = StorageService::CheckPresenceState(this, (unsigned int)v7[1], v10, 2);
      if ( (v11 & v3) != 0 )
      {
        if ( !v12
          && (int)StorageService::CheckDeviceId(this, (unsigned int)v9, (unsigned int)v10) >= 0
          && (int)StorageService::GetStorageCardMetadata(this, (unsigned int)v9, (unsigned int)v10) < 0 )
        {
          v40 = 1112 * v10;
          GetVolumeNameForVolumeMountPointW(
            (LPCWSTR)(1112 * v10 + *((_QWORD *)this + v9 + 5) + 4LL),
            szVolumeName,
            0x104u);
          StringCchCopyW(v63, 0x104u, szVolumeName);
          StringCchLengthW(v63, v13, &v41);
          if ( v41 && v63[v41 - 1] == 92 )
          {
            v14 = 2 * v41 - 2;
            if ( v14 >= 0x208 )
LABEL_67:
              _report_rangecheckfailure();
            *(wchar_t *)((char *)v63 + v14) = 0;
          }
          if ( (unsigned int)IsVolumeMounted(v63) )
          {
            std::wstring::wstring(v53, 1112 * v10 + *((_QWORD *)this + v9 + 5) + 4LL);
            StorageService::UpdateAppPairingState(this, (unsigned int)v9, (unsigned int)v10, 16);
            StorageService::ClearStorageCardPaths(this, (unsigned int)v9, (unsigned int)v10);
            v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53);
            StorageService::SetStorageCardPaths(this, v15, (unsigned int)v9, (unsigned int)v10);
            v16 = 0;
            v17 = v40;
            do
            {
              StorageService::ClearVolumeStatus(this, (unsigned int)v9, (unsigned int)v10, 2);
              StorageService::DetermineFormatState(this, (unsigned int)v9, (unsigned int)v10);
              if ( (*(_BYTE *)(v17 + *((_QWORD *)this + v9 + 5) + 536) & 2) == 0 )
                break;
              Sleep(0x1F4u);
              ++v16;
            }
            while ( v16 < 10 );
            v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53);
            v34 = v10;
            StorageService::ProcessNewStorageCard(this, v18, szVolumeName, (unsigned int)v9);
            v3 = v36;
            v7 = *(_DWORD **)v35;
            if ( (unsigned int)dword_1800BF000 > 5 )
            {
              *(_QWORD *)v35 = szVolumeName;
              v36 = v10;
              v37 = v9;
              LODWORD(v40) = 3;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                (unsigned int)&dword_1800BF000,
                (unsigned int)&dword_1800A5F54,
                (unsigned int)v51,
                v19,
                (__int64)&v40,
                (__int64)&v37,
                (__int64)&v36,
                (__int64)v35);
            }
            std::wstring::_Tidy_deallocate(v53);
          }
          v6 = v44;
        }
        v3 &= ~v11;
        v36 = v3;
      }
      else if ( !v12 || (unsigned int)StorageService::IsVolumeStatusSet(this, (unsigned int)v9, (unsigned int)v10, 10) )
      {
        if ( !(_DWORD)v9 )
          StorageService::UpdateSystemReservedSize(
            this,
            (const unsigned __int16 *)(1112 * v10 + *((_QWORD *)this + 5) + 4LL));
        --*((_DWORD *)this + v9 + 7);
        StorageService::UpdateDismountState(this, (unsigned int)v9, (unsigned int)v10, 2);
        if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
        {
          v21 = *((_QWORD *)this + v9 + 5);
          v42 = *(_DWORD *)(v21 + 1112 * v10 + 532);
          v38 = *(_DWORD *)(v21 + 1112 * v10 + 1096);
          v39 = v9;
          v61 = &v42;
          v62 = 4;
          v59 = &v38;
          v60 = 4;
          v57 = &v39;
          v58 = 4;
          v55 = v21 + 1112 * v10 + 548;
          v56 = 16;
          tlgWriteTransfer_EventWriteTransfer(&dword_1800BF000, &unk_1800A7348, 0, 0, 6, v54);
        }
        if ( (unsigned int)dword_1800BF000 > 5 )
        {
          v43 = (WCHAR *)(*((_QWORD *)this + v9 + 5) + 4LL + 1112 * v10);
          LODWORD(v40) = v10;
          v37 = v9;
          v35[0] = 2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_1800BF000,
            (unsigned int)byte_1800A6D5B,
            (unsigned int)v51,
            v20,
            (__int64)v35,
            (__int64)&v37,
            (__int64)&v40,
            (__int64)&v43);
        }
        StorageService::ClearStorageCardPaths(this, (unsigned int)v9, (unsigned int)v10);
      }
      v7 += 7;
      *(_QWORD *)v35 = v7;
    }
    while ( v7 != v6 );
    v2 = 0;
  }
  v22 = 0;
  v23 = 65;
  wcscpy(szVolumeMountPoint, L"A:\\");
  memset_0(v65, 0, 0x200u);
  if ( !v3 )
    goto LABEL_51;
  while ( 1 )
  {
    if ( (v3 & 1) != 0 )
    {
      szVolumeMountPoint[0] = v23;
      if ( GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x104u) )
      {
        StringCchCopyW(v63, 0x104u, szVolumeName);
        StringCchLengthW(v63, v24, &v41);
        if ( v41 && v63[v41 - 1] == 92 )
        {
          v25 = 2 * v41 - 2;
          if ( v25 >= 0x208 )
            goto LABEL_67;
          *(wchar_t *)((char *)v63 + v25) = 0;
        }
        if ( (unsigned int)IsVolumeMounted(v63) && StorageService::IsValidStorageSenseDrive(v26, v63) )
        {
          if ( (unsigned int)StorageService::IsRemovable(this, szVolumeName, szVolumeMountPoint, v27) )
          {
            v28 = 1;
          }
          else
          {
            v28 = 0;
            StorageService::UpdateSystemReservedSize(this, szVolumeMountPoint);
          }
          while ( *(_WORD *)(1112LL * v2 + *((_QWORD *)this + v28 + 5) + 4) )
          {
            if ( ++v2 >= 0x1F )
            {
              v22 = -2147024812;
              goto LABEL_51;
            }
          }
          ++*((_DWORD *)this + v28 + 7);
          if ( (unsigned int)StorageService::CheckPresenceState(this, v28, v2, 2) )
          {
            v34 = v2;
            StorageService::ProcessNewStorageCard(this, szVolumeMountPoint, szVolumeName, v28);
          }
          if ( (unsigned int)dword_1800BF000 > 5 )
          {
            v43 = szVolumeName;
            v35[0] = v2;
            v39 = v28;
            v38 = 1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              (unsigned int)&dword_1800BF000,
              (unsigned int)&word_1800A71F6,
              (unsigned int)v51,
              v33,
              (__int64)&v38,
              (__int64)&v39,
              (__int64)v35,
              (__int64)&v43);
          }
          v2 = 0;
        }
      }
    }
    v3 >>= 1;
    if ( !v3 )
      break;
    ++v23;
  }
LABEL_51:
  StorageService::GetCurrentTrackedDeviceList(this, &v47);
  v30 = StorageService::OfflineAppxVolumesIfMissing(v29, (__int64)&v47);
  if ( v30 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8FD,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)v30,
      v34);
  v49 = 2;
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    v35[0] = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)&dword_1800A5E54,
      (unsigned int)v51,
      v31,
      (__int64)v35);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
  if ( v47 )
  {
    std::_Deallocate<16>(v47, 4 * ((*((_QWORD *)&v48 + 1) - v47) >> 2));
    v47 = 0;
    v48 = 0;
  }
  if ( (_QWORD)v45 )
  {
    std::_Deallocate<16>(v45, 4 * ((v46 - (__int64)v45) >> 2));
    v45 = 0;
    v46 = 0;
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v49);
  return v22;
}

```

## disassembly

```asm
0x180027080  push    rbp
0x180027082  push    rbx
0x180027083  push    rsi
0x180027084  push    rdi
0x180027085  push    r12
0x180027087  push    r13
0x180027089  push    r14
0x18002708b  push    r15
0x18002708d  lea     rbp, [rsp-6A8h]
0x180027095  sub     rsp, 7A8h
0x18002709c  mov     rax, cs:__security_cookie
0x1800270a3  xor     rax, rsp
0x1800270a6  mov     [rbp+6E0h+var_50], rax
0x1800270ad  mov     rbx, rcx
0x1800270b0  xor     edi, edi
0x1800270b2  mov     [rsp+7E0h+var_780], rdi
0x1800270b7  call    cs:__imp_GetLogicalDrives
0x1800270bd  mov     r14d, [rbx+18h]
0x1800270c1  not     r14d
0x1800270c4  and     r14d, eax
0x1800270c7  mov     [rsp+7E0h+var_798], r14d
0x1800270cc  mov     [rbp+6E0h+var_730], edi
0x1800270cf  mov     [rbp+6E0h+var_72C], dil
0x1800270d3  lea     rcx, [rbx+630h]; lpCriticalSection
0x1800270da  call    cs:__imp_EnterCriticalSection
0x1800270e0  lea     rcx, [rbp+6E0h+var_730]
0x1800270e4  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800270e9  mov     eax, cs:dword_1800BF000
0x1800270ef  cmp     eax, 5
0x1800270f2  jbe     short loc_180027125
0x1800270f4  cmp     [rbp+6E0h+var_72C], dil
0x1800270f8  jz      short loc_18002710B
0x1800270fa  lea     rcx, [rbp+6E0h+var_718]; struct _GUID *
0x1800270fe  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180027103  test    al, al
0x180027105  lea     r9, [rbp+6E0h+var_718]
0x180027109  jz      short loc_18002710E
0x18002710b  mov     r9, rdi
0x18002710e  lea     r8, [rbp+6E0h+var_728]
0x180027112  lea     rdx, byte_1800A7325
0x180027119  lea     rcx, dword_1800BF000
0x180027120  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180027125  lea     rdx, [rbp+6E0h+var_760]
0x180027129  mov     rcx, rbx
0x18002712c  call    ?GetCurrentTrackedDeviceList@StorageService@@AEAA?AV?$vector@UTrackedDevice@@V?$allocator@UTrackedDevice@@@std@@@std@@XZ; StorageService::GetCurrentTrackedDeviceList(void)
0x180027131  nop
0x180027132  mov     r15, qword ptr [rbp+6E0h+var_760]
0x180027136  mov     qword ptr [rsp+7E0h+var_7A0], r15
0x18002713b  mov     r13, qword ptr [rbp+6E0h+var_760+8]
0x18002713f  mov     [rsp+7E0h+var_768], r13
0x180027144  cmp     r15, r13
0x180027147  jz      loc_180027538
0x18002714d  movsxd  rdi, dword ptr [r15+4]
0x180027151  mov     esi, [r15+8]
0x180027155  mov     ecx, [r15]
0x180027158  mov     r12d, 1
0x18002715e  shl     r12d, cl
0x180027161  mov     r9d, 2
0x180027167  mov     r8d, esi
0x18002716a  mov     edx, edi
0x18002716c  mov     rcx, rbx
0x18002716f  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x180027174  test    r14d, r12d
0x180027177  jz      loc_18002738B
0x18002717d  test    eax, eax
0x18002717f  jnz     loc_18002737B
0x180027185  mov     r8d, esi
0x180027188  mov     edx, edi
0x18002718a  mov     rcx, rbx
0x18002718d  call    ?CheckDeviceId@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::CheckDeviceId(_STORAGE_DEVICE_TYPE,ulong)
0x180027192  test    eax, eax
0x180027194  js      loc_18002737B
0x18002719a  mov     r8d, esi
0x18002719d  mov     edx, edi
0x18002719f  mov     rcx, rbx
0x1800271a2  call    ?GetStorageCardMetadata@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::GetStorageCardMetadata(_STORAGE_DEVICE_TYPE,ulong)
0x1800271a7  test    eax, eax
0x1800271a9  jns     loc_18002737B
0x1800271af  imul    r13, rsi, 458h
0x1800271b6  mov     [rsp+7E0h+var_788], r13
0x1800271bb  mov     rcx, [rbx+rdi*8+28h]
0x1800271c0  add     rcx, 4
0x1800271c4  add     rcx, r13; lpszVolumeMountPoint
0x1800271c7  mov     r8d, 104h; cchBufferLength
0x1800271cd  lea     rdx, [rbp+6E0h+szVolumeName]; lpszVolumeName
0x1800271d4  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800271da  lea     r8, [rbp+6E0h+szVolumeName]; wchar_t *
0x1800271e1  mov     edx, 104h; unsigned __int64
0x1800271e6  lea     rcx, [rbp+6E0h+var_680]; wchar_t *
0x1800271ea  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800271ef  lea     r8, [rsp+7E0h+var_780]; unsigned __int64 *
0x1800271f4  lea     rcx, [rbp+6E0h+var_680]; unsigned __int16 *
0x1800271f8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800271fd  mov     r8, [rsp+7E0h+var_780]
0x180027202  xor     eax, eax
0x180027204  test    r8, r8
0x180027207  jz      short loc_18002722D
0x180027209  cmp     [rbp+r8*2+6E0h+var_682], 5Ch ; '\'
0x180027210  jnz     short loc_18002722D
0x180027212  lea     r8, ds:0FFFFFFFFFFFFFFFEh[r8*2]
0x18002721a  cmp     r8, 208h
0x180027221  jnb     loc_180027849
0x180027227  mov     [rbp+r8+6E0h+var_680], ax
0x18002722d  lea     rcx, [rbp+6E0h+var_680]; unsigned __int16 *
0x180027231  call    ?IsVolumeMounted@@YAHPEBG@Z; IsVolumeMounted(ushort const *)
0x180027236  test    eax, eax
0x180027238  jz      loc_180027376
0x18002723e  mov     rdx, [rbx+rdi*8+28h]
0x180027243  add     rdx, 4
0x180027247  add     rdx, r13
0x18002724a  lea     rcx, [rbp+6E0h+var_708]
0x18002724e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027253  nop
0x180027254  mov     r9d, 10h
0x18002725a  mov     r8d, esi
0x18002725d  mov     edx, edi
0x18002725f  mov     rcx, rbx
0x180027262  call    ?UpdateAppPairingState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::UpdateAppPairingState(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180027267  mov     r8d, esi
0x18002726a  mov     edx, edi
0x18002726c  mov     rcx, rbx
0x18002726f  call    ?ClearStorageCardPaths@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::ClearStorageCardPaths(_STORAGE_DEVICE_TYPE,ulong)
0x180027274  lea     rcx, [rbp+6E0h+var_708]
0x180027278  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002727d  mov     rdx, rax
0x180027280  mov     r9d, esi
0x180027283  mov     r8d, edi
0x180027286  mov     rcx, rbx
0x180027289  call    ?SetStorageCardPaths@StorageService@@IEAAJPEBGW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::SetStorageCardPaths(ushort const *,_STORAGE_DEVICE_TYPE,ulong)
0x18002728e  xor     r13d, r13d
0x180027291  mov     r15, [rsp+7E0h+var_788]
0x180027296  mov     r9d, 2
0x18002729c  mov     r8d, esi
0x18002729f  mov     edx, edi
0x1800272a1  mov     rcx, rbx
0x1800272a4  call    ?ClearVolumeStatus@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::ClearVolumeStatus(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x1800272a9  mov     r8d, esi
0x1800272ac  mov     edx, edi
0x1800272ae  mov     rcx, rbx
0x1800272b1  call    ?DetermineFormatState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::DetermineFormatState(_STORAGE_DEVICE_TYPE,ulong)
0x1800272b6  mov     rax, [rbx+rdi*8+28h]
0x1800272bb  test    byte ptr [r15+rax+218h], 2
0x1800272c4  jz      short loc_1800272DA
0x1800272c6  mov     ecx, 1F4h; dwMilliseconds
0x1800272cb  call    cs:__imp_Sleep
0x1800272d1  inc     r13d
0x1800272d4  cmp     r13d, 0Ah
0x1800272d8  jl      short loc_180027296
0x1800272da  lea     rcx, [rbp+6E0h+var_708]
0x1800272de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800272e3  mov     rdx, rax
0x1800272e6  mov     [rsp+7E0h+var_7C0], esi
0x1800272ea  mov     r9d, edi
0x1800272ed  lea     r8, [rbp+6E0h+szVolumeName]
0x1800272f4  mov     rcx, rbx
0x1800272f7  call    ?ProcessNewStorageCard@StorageService@@IEAAJPEBG0W4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::ProcessNewStorageCard(ushort const *,ushort const *,_STORAGE_DEVICE_TYPE,ulong)
0x1800272fc  mov     eax, cs:dword_1800BF000
0x180027302  cmp     eax, 5
0x180027305  mov     r14d, [rsp+7E0h+var_798]
0x18002730a  mov     r15, qword ptr [rsp+7E0h+var_7A0]
0x18002730f  jbe     short loc_18002736D
0x180027311  lea     rax, [rbp+6E0h+szVolumeName]
0x180027318  mov     qword ptr [rsp+7E0h+var_7A0], rax
0x18002731d  mov     [rsp+7E0h+var_798], esi
0x180027321  mov     [rsp+7E0h+var_794], edi
0x180027325  mov     dword ptr [rsp+7E0h+var_788], 3
0x18002732d  lea     rax, [rsp+7E0h+var_7A0]
0x180027332  mov     [rsp+7E0h+var_7A8], rax
0x180027337  lea     rax, [rsp+7E0h+var_798]
0x18002733c  mov     [rsp+7E0h+var_7B0], rax
0x180027341  lea     rax, [rsp+7E0h+var_794]
0x180027346  mov     [rsp+7E0h+var_7B8], rax
0x18002734b  lea     rax, [rsp+7E0h+var_788]
0x180027350  mov     qword ptr [rsp+7E0h+var_7C0], rax
0x180027355  lea     r8, [rbp+6E0h+var_728]
0x180027359  lea     rdx, dword_1800A5F54
0x180027360  lea     rcx, dword_1800BF000
0x180027367  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002736c  nop
0x18002736d  lea     rcx, [rbp+6E0h+var_708]
0x180027371  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027376  mov     r13, [rsp+7E0h+var_768]
0x18002737b  not     r12d
0x18002737e  and     r14d, r12d
0x180027381  mov     [rsp+7E0h+var_798], r14d
0x180027386  jmp     loc_180027524
0x18002738b  test    eax, eax
0x18002738d  jz      short loc_1800273AA
0x18002738f  mov     r9d, 0Ah
0x180027395  mov     r8d, esi
0x180027398  mov     edx, edi
0x18002739a  mov     rcx, rbx
0x18002739d  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x1800273a2  test    eax, eax
0x1800273a4  jz      loc_180027524
0x1800273aa  test    edi, edi
0x1800273ac  jnz     short loc_1800273C8
0x1800273ae  imul    rcx, rsi, 458h
0x1800273b5  mov     rdx, [rbx+28h]
0x1800273b9  add     rdx, 4
0x1800273bd  add     rdx, rcx; unsigned __int16 *
0x1800273c0  mov     rcx, rbx; this
0x1800273c3  call    ?UpdateSystemReservedSize@StorageService@@QEAAXPEBG@Z; StorageService::UpdateSystemReservedSize(ushort const *)
0x1800273c8  dec     dword ptr [rbx+rdi*4+1Ch]
0x1800273cc  mov     r9d, 2
0x1800273d2  mov     r8d, esi
0x1800273d5  mov     edx, edi
0x1800273d7  mov     rcx, rbx
0x1800273da  call    ?UpdateDismountState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_DISMOUNT_REASON@@@Z; StorageService::UpdateDismountState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DISMOUNT_REASON)
0x1800273df  mov     eax, cs:dword_1800BF000
0x1800273e5  cmp     eax, 5
0x1800273e8  jbe     loc_1800274A5
0x1800273ee  mov     rdx, 400000000000h
0x1800273f8  lea     rcx, dword_1800BF000
0x1800273ff  call    _tlgKeywordOn
0x180027404  test    al, al
0x180027406  jz      loc_1800274A5
0x18002740c  imul    rdx, rsi, 458h
0x180027413  mov     rcx, [rbx+rdi*8+28h]
0x180027418  mov     eax, [rcx+rdx+214h]
0x18002741f  mov     [rsp+7E0h+var_778], eax
0x180027423  mov     eax, [rcx+rdx+448h]
0x18002742a  mov     [rsp+7E0h+var_790], eax
0x18002742e  mov     [rsp+7E0h+var_78C], edi
0x180027432  lea     rax, [rsp+7E0h+var_778]
0x180027437  mov     [rbp+6E0h+var_690], rax
0x18002743b  mov     qword ptr [rbp+58h], 4
0x180027443  lea     rax, [rsp+7E0h+var_790]
0x180027448  mov     [rbp+6E0h+var_6A0], rax
0x18002744c  mov     [rbp+6E0h+var_698], 4
0x180027454  lea     rax, [rsp+7E0h+var_78C]
0x180027459  mov     [rbp+6E0h+var_6B0], rax
0x18002745d  mov     [rbp+6E0h+var_6A8], 4
0x180027465  lea     rax, [rdx+224h]
0x18002746c  add     rax, rcx
0x18002746f  mov     [rbp+6E0h+var_6C0], rax
0x180027473  mov     [rbp+6E0h+var_6B8], 10h
0x18002747b  lea     rax, [rbp+6E0h+var_6E0]
0x18002747f  mov     [rsp+7E0h+var_7B8], rax
0x180027484  mov     [rsp+7E0h+var_7C0], 6
0x18002748c  xor     r9d, r9d
0x18002748f  xor     r8d, r8d
0x180027492  lea     rdx, unk_1800A7348
0x180027499  lea     rcx, dword_1800BF000
0x1800274a0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800274a5  mov     eax, cs:dword_1800BF000
0x1800274ab  cmp     eax, 5
0x1800274ae  jbe     short loc_180027517
0x1800274b0  imul    rcx, rsi, 458h
0x1800274b7  mov     rax, [rbx+rdi*8+28h]
0x1800274bc  add     rax, 4
0x1800274c0  add     rcx, rax
0x1800274c3  mov     [rsp+7E0h+var_770], rcx
0x1800274c8  mov     dword ptr [rsp+7E0h+var_788], esi
0x1800274cc  mov     [rsp+7E0h+var_794], edi
0x1800274d0  mov     [rsp+7E0h+var_7A0], 2
0x1800274d8  lea     rax, [rsp+7E0h+var_770]
0x1800274dd  mov     [rsp+7E0h+var_7A8], rax
0x1800274e2  lea     rax, [rsp+7E0h+var_788]
0x1800274e7  mov     [rsp+7E0h+var_7B0], rax
0x1800274ec  lea     rax, [rsp+7E0h+var_794]
0x1800274f1  mov     [rsp+7E0h+var_7B8], rax
0x1800274f6  lea     rax, [rsp+7E0h+var_7A0]
0x1800274fb  mov     qword ptr [rsp+7E0h+var_7C0], rax; int
0x180027500  lea     r8, [rbp+6E0h+var_728]
0x180027504  lea     rdx, byte_1800A6D5B
0x18002750b  lea     rcx, dword_1800BF000
0x180027512  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180027517  mov     r8d, esi
0x18002751a  mov     edx, edi
0x18002751c  mov     rcx, rbx
0x18002751f  call    ?ClearStorageCardPaths@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::ClearStorageCardPaths(_STORAGE_DEVICE_TYPE,ulong)
0x180027524  add     r15, 1Ch
0x180027528  mov     qword ptr [rsp+7E0h+var_7A0], r15
0x18002752d  cmp     r15, r13
0x180027530  jnz     loc_18002714D
0x180027536  xor     edi, edi
0x180027538  mov     r12d, edi
0x18002753b  mov     r15d, 41h ; 'A'
0x180027541  mov     [rbp+6E0h+szVolumeMountPoint], r15w
0x180027549  mov     eax, dword ptr cs:aA+2; ":\\"
0x18002754f  mov     [rbp+6E0h+var_46E], eax
0x180027555  movzx   eax, word ptr cs:aA+6; ""
0x18002755c  mov     [rbp+6E0h+var_46A], ax
0x180027563  xor     edx, edx; Val
0x180027565  mov     r8d, 200h; Size
0x18002756b  lea     rcx, [rbp+6E0h+var_468]; void *
0x180027572  call    memset_0
0x180027577  test    r14d, r14d
0x18002757a  jz      loc_180027688
0x180027580  test    r14b, 1
0x180027584  jz      loc_180027838
0x18002758a  movsx   eax, r15b
0x18002758e  mov     [rbp+6E0h+szVolumeMountPoint], ax
0x180027595  mov     r8d, 104h; cchBufferLength
0x18002759b  lea     rdx, [rbp+6E0h+szVolumeName]; lpszVolumeName
0x1800275a2  lea     rcx, [rbp+6E0h+szVolumeMountPoint]; lpszVolumeMountPoint
0x1800275a9  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800275af  test    eax, eax
0x1800275b1  jz      loc_180027838
  ... truncated ...
```
