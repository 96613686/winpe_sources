# StorageService::FormatVolume(_STORAGE_DEVICE_TYPE,ulong,ulong)

- ea: `0x180022640`
- end: `0x180022c20`
- name: `?FormatVolume@StorageService@@QEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z`
- size: `1504`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180037530`

## callees

- `0x180001148`
- `0x1800016b8`
- `0x180001a98`
- `0x180001c80`
- `0x18000d030`
- `0x18000d450`
- `0x18000ddb0`
- `0x180014a00`
- `0x18001a5c4`
- `0x18001e9e4`
- `0x18001ea9c`
- `0x18001ec28`
- `0x18001fe50`
- `0x18001feb8`
- `0x180020d2c`
- `0x180022640`
- `0x180024f94`
- `0x180025efc`
- `0x180026bfc`
- `0x1800282b8`
- `0x1800294ec`
- `0x18002a3f8`
- `0x18002bd7c`
- `0x180072900`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800226c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800226c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022a87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227df`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800227d5`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800227d5`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x1800226ab`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x180022892`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x180022a91`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x1800226ab`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x180022892`
- `api-ms-win-core-realtime-l1-1-1!QueryInterruptTime` at `0x180022a91`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800228f1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800228f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StorageService::FormatVolume(__int64 a1, int a2, unsigned int a3, int a4)
{
  char v4; // bl
  __int64 v5; // r15
  __int64 v6; // r14
  int v7; // r13d
  bool v8; // si
  __int64 v9; // rcx
  int updated; // ebx
  __int64 v11; // rdi
  __int64 v12; // r12
  __int64 v13; // rax
  __int64 v14; // rcx
  signed int LastError; // eax
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  const unsigned __int16 *v20; // rdx
  _QWORD *v21; // rax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, struct Windows::Management::Deployment::IPackageVolume **); // rbx
  __int64 v24; // rax
  int v25; // eax
  StorageService *v26; // rcx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // ecx
  int v32; // r9d
  __int64 v33; // rdx
  int v34; // r9d
  bool v36[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+64h] [rbp-9Ch] BYREF
  int v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v39; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int16 *v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41[2]; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Management::Deployment::IPackageVolume *v42; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 InterruptTime; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v45; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v46; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v47; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER string; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-30h]
  OLECHAR sz[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v52[76]; // [rsp+E4h] [rbp-1Ch] BYREF
  WCHAR szVolumeName[264]; // [rsp+130h] [rbp+30h] BYREF

  v4 = a4;
  v38 = a4;
  v5 = a3;
  v6 = a2;
  v7 = 0;
  v39 = 0;
  v8 = 0;
  *(_DWORD *)sz = 0;
  memset_0(v52, 0, 0x4Au);
  InterruptTime = 0;
  v45 = 0;
  v47 = 0;
  QueryInterruptTime(&InterruptTime);
  v45 = InterruptTime;
  EnterCriticalSection(&stru_1800C10D0);
  if ( (v4 & 4) != 0
    || (updated = StorageService::GetStorageSettings(v9, (unsigned int)v6, (unsigned int)v5, 2, &v39), updated >= 0) )
  {
    updated = StorageService::CheckDeviceParameters(v9, (unsigned int)v6, (unsigned int)v5, 1);
    if ( updated >= 0 )
    {
      if ( (unsigned int)StorageService::IsVolumeStatusSet(&g_StorageService, (unsigned int)v6, (unsigned int)v5, 8)
        || (unsigned int)StorageService::IsVolumeStatusSet(&g_StorageService, (unsigned int)v6, (unsigned int)v5, 16) )
      {
        updated = -2147018887;
        goto LABEL_37;
      }
      v11 = v6;
      v12 = 1112 * v5;
      v13 = *((_QWORD *)&g_StorageService + v6 + 5);
      if ( !*(_WORD *)(1112 * v5 + v13 + 4) )
      {
        updated = -2147418113;
        goto LABEL_37;
      }
      v37 = *(_DWORD *)(v12 + v13 + 564);
      v8 = v37 == 2;
      if ( (unsigned int)StorageService::CheckPresenceState(&g_StorageService, (unsigned int)v6, (unsigned int)v5, 2) )
      {
        StorageService::SetDismountReason(v14, (unsigned int)v6, (unsigned int)v5);
      }
      else
      {
        updated = StorageService::UpdateDismountState(&g_StorageService, (unsigned int)v6, (unsigned int)v5, 4);
        if ( updated < 0 )
          goto LABEL_37;
      }
      if ( GetVolumeNameForVolumeMountPointW((LPCWSTR)((char *)*(&P + 1) + v12 + 4), szVolumeName, 0x104u) )
      {
        v16 = -1;
        do
          ++v16;
        while ( szVolumeName[v16] );
        v17 = 2 * v16 - 2;
        if ( v17 >= 0x208 )
          _report_rangecheckfailure();
        *(WCHAR *)((char *)szVolumeName + v17) = 0;
        v40 = 0;
        v41[0] = 0;
        if ( (v38 & 1) != 0 )
        {
          v18 = L"NTFS";
          v19 = 4096;
        }
        else
        {
          updated = GetFileSystemFormatAndClusterSize(szVolumeName, (const unsigned __int16 **)&v40, v41);
          if ( updated < 0 )
            goto LABEL_37;
          v18 = v40;
          v19 = v41[0];
        }
        v7 = FormatPartitionWithPath(v12 + *((_QWORD *)&g_StorageService + v6 + 5) + 4LL, v18, v19);
        QueryInterruptTime(&v45);
        if ( v7 >= 0 && v37 == 2 )
        {
          v44 = 0;
          v42 = 0;
          v21 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                            (HSTRING *)&string,
                            (const unsigned __int16 (*)[62])v20);
          if ( (int)Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
                      *v21,
                      &v44) >= 0
            && StringFromGUID2((const GUID *const)(v12 + *((_QWORD *)&g_StorageService + v6 + 5) + 548LL), sz, 39) )
          {
            v22 = v44;
            v23 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Management::Deployment::IPackageVolume **))(*(_QWORD *)v44 + 232LL);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
            v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, sz);
            v25 = v23(v22, *(_QWORD *)(v24 + 24), &v42);
            v50 = 0;
            if ( v25 >= 0
              && (StorageService::RemoveAppxPackagesAndVolume(v26, v42), (unsigned int)dword_1800BF000 > 5)
              && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
            {
              v37 = v27;
              v11 = v6;
              v29 = *((_QWORD *)&g_StorageService + v6 + 5);
              v38 = *(_DWORD *)(v12 + v29 + 1100);
              v41[0] = *(_DWORD *)(v12 + v29 + 1096);
              LODWORD(v40) = v6;
              v46 = v12 + v29 + 548;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v29,
                (unsigned int)&dword_1800A6CCC,
                v27,
                v28,
                (__int64)&v46,
                (__int64)&v40,
                (__int64)v41,
                (__int64)&v38,
                (__int64)&v37);
            }
            else
            {
              v11 = v6;
            }
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
        }
        updated = StorageService::DetermineFormatState(&g_StorageService, (unsigned int)v6, (unsigned int)v5);
        if ( updated >= 0 )
        {
          updated = StorageService::ProcessNewStorageCard(
                      (__int64)&g_StorageService,
                      (const unsigned __int16 *)(v12 + 4 + *((_QWORD *)&g_StorageService + v11 + 5)),
                      szVolumeName,
                      v6,
                      v5);
          if ( updated >= 0 && v7 >= 0 )
            updated = StorageService::SetWriteAccess((__int64)&g_StorageService, v6, v5, v39);
        }
      }
      else
      {
        LastError = GetLastError();
        updated = LastError;
        if ( LastError > 0 )
          updated = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
LABEL_37:
  LeaveCriticalSection(&stru_1800C10D0);
  QueryInterruptTime(&v47);
  if ( v7 >= 0 )
    v7 = updated;
  if ( (int)StorageService::CheckDeviceParameters(v30, (unsigned int)v6, (unsigned int)v5, 1) < 0 )
  {
    if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
    {
      LODWORD(v40) = v5;
      v37 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BF000,
        (unsigned int)&word_1800A699E,
        0,
        v34,
        (__int64)&v37,
        (__int64)&v40);
    }
  }
  else if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    LODWORD(v40) = v7;
    v36[0] = v8;
    v46 = v47 - InterruptTime;
    *(_QWORD *)v41 = v45 - InterruptTime;
    v33 = *((_QWORD *)&g_StorageService + v6 + 5);
    v37 = *(_DWORD *)(v33 + 1112 * v5 + 1100);
    v38 = *(_DWORD *)(v33 + 1112 * v5 + 1096);
    v39 = v6;
    v48 = v33 + 1112 * v5 + 548;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      v31,
      (unsigned int)&word_1800A65FE,
      1112 * v5,
      v32,
      (__int64)&v48,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)v41,
      (__int64)&v46,
      (__int64)v36,
      (__int64)&v40);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180022640  mov     [rsp-8+arg_0], rbx
0x180022645  push    rbp
0x180022646  push    rsi
0x180022647  push    rdi
0x180022648  push    r12
0x18002264a  push    r13
0x18002264c  push    r14
0x18002264e  push    r15
0x180022650  lea     rbp, [rsp-250h]
0x180022658  sub     rsp, 350h
0x18002265f  mov     rax, cs:__security_cookie
0x180022666  xor     rax, rsp
0x180022669  mov     [rbp+280h+var_40], rax
0x180022670  mov     ebx, r9d
0x180022673  mov     [rsp+380h+var_318], ebx
0x180022677  mov     r15d, r8d
0x18002267a  movsxd  r14, edx
0x18002267d  xor     edi, edi
0x18002267f  mov     r13d, edi
0x180022682  mov     [rsp+380h+var_314], edi
0x180022686  mov     sil, dil
0x180022689  mov     dword ptr [rbp+280h+sz], edi
0x18002268c  xor     edx, edx; Val
0x18002268e  lea     r8d, [rdi+4Ah]; Size
0x180022692  lea     rcx, [rbp+280h+var_29C]; void *
0x180022696  call    memset_0
0x18002269b  mov     [rbp+280h+InterruptTime], rdi
0x18002269f  mov     [rbp+280h+var_2E8], rdi
0x1800226a3  mov     [rbp+280h+var_2D8], rdi
0x1800226a7  lea     rcx, [rbp+280h+InterruptTime]; lpInterruptTime
0x1800226ab  call    cs:__imp_QueryInterruptTime
0x1800226b1  mov     rax, [rbp+280h+InterruptTime]
0x1800226b5  mov     [rbp+280h+var_2E8], rax
0x1800226b9  lea     rcx, stru_1800C10D0; lpCriticalSection
0x1800226c0  call    cs:__imp_EnterCriticalSection
0x1800226c6  lea     r12, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x1800226cd  test    bl, 4
0x1800226d0  jnz     short loc_1800226F5
0x1800226d2  lea     rax, [rsp+380h+var_314]
0x1800226d7  mov     [rsp+380h+var_360], rax
0x1800226dc  lea     r9d, [rdi+2]
0x1800226e0  mov     r8d, r15d
0x1800226e3  mov     edx, r14d
0x1800226e6  call    ?GetStorageSettings@StorageService@@QEAAJW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_SETTING@@PEAK@Z; StorageService::GetStorageSettings(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_SETTING,ulong *)
0x1800226eb  mov     ebx, eax
0x1800226ed  test    eax, eax
0x1800226ef  js      loc_180022A80
0x1800226f5  mov     r9d, 1
0x1800226fb  mov     r8d, r15d
0x1800226fe  mov     edx, r14d
0x180022701  call    ?CheckDeviceParameters@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::CheckDeviceParameters(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180022706  mov     ebx, eax
0x180022708  test    eax, eax
0x18002270a  js      loc_180022A80
0x180022710  mov     r9d, 8
0x180022716  mov     r8d, r15d
0x180022719  mov     edx, r14d
0x18002271c  mov     rcx, r12
0x18002271f  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180022724  xor     ebx, ebx
0x180022726  test    eax, eax
0x180022728  jnz     loc_180022A7B
0x18002272e  lea     r9d, [rbx+10h]
0x180022732  mov     r8d, r15d
0x180022735  mov     edx, r14d
0x180022738  mov     rcx, r12
0x18002273b  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180022740  test    eax, eax
0x180022742  jnz     loc_180022A7B
0x180022748  mov     rdi, r14
0x18002274b  imul    r12, r15, 458h
0x180022752  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x180022759  mov     rax, [rcx+r14*8+28h]
0x18002275e  cmp     [r12+rax+4], bx
0x180022764  jnz     short loc_180022777
0x180022766  mov     ebx, 8000FFFFh
0x18002276b  lea     r12, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x180022772  jmp     loc_180022A80
0x180022777  mov     eax, [r12+rax+234h]
0x18002277f  mov     [rsp+380h+var_31C], eax
0x180022783  cmp     eax, 2
0x180022786  setz    sil
0x18002278a  mov     r9d, 2
0x180022790  mov     r8d, r15d
0x180022793  mov     edx, r14d
0x180022796  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x18002279b  mov     r8d, r15d
0x18002279e  mov     edx, r14d
0x1800227a1  test    eax, eax
0x1800227a3  jnz     short loc_1800227F9
0x1800227a5  lea     r9d, [rax+4]
0x1800227a9  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x1800227b0  call    ?UpdateDismountState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_DISMOUNT_REASON@@@Z; StorageService::UpdateDismountState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DISMOUNT_REASON)
0x1800227b5  mov     ebx, eax
0x1800227b7  test    eax, eax
0x1800227b9  js      short loc_18002276B
0x1800227bb  xor     ebx, ebx
0x1800227bd  mov     rcx, qword ptr cs:P+8
0x1800227c4  add     rcx, 4
0x1800227c8  add     rcx, r12; lpszVolumeMountPoint
0x1800227cb  mov     r8d, 104h; cchBufferLength
0x1800227d1  lea     rdx, [rbp+280h+szVolumeName]; lpszVolumeName
0x1800227d5  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800227db  test    eax, eax
0x1800227dd  jnz     short loc_180022800
0x1800227df  call    cs:__imp_GetLastError
0x1800227e5  mov     ebx, eax
0x1800227e7  test    eax, eax
0x1800227e9  jle     short loc_18002276B
0x1800227eb  movzx   ebx, ax
0x1800227ee  or      ebx, 80070000h
0x1800227f4  jmp     loc_18002276B
0x1800227f9  call    ?SetDismountReason@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_DISMOUNT_REASON@@@Z; StorageService::SetDismountReason(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DISMOUNT_REASON)
0x1800227fe  jmp     short loc_1800227BD
0x180022800  lea     rcx, [rbp+280h+szVolumeName]
0x180022804  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022808  inc     rax
0x18002280b  cmp     [rcx+rax*2], bx
0x18002280f  jnz     short loc_180022808
0x180022811  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180022819  cmp     rcx, 208h
0x180022820  jnb     loc_180022C1A
0x180022826  mov     [rbp+rcx+280h+szVolumeName], bx
0x18002282b  mov     [rsp+380h+var_310], rbx
0x180022830  mov     [rsp+380h+var_308], ebx
0x180022834  test    byte ptr [rsp+380h+var_318], 1
0x180022839  jz      short loc_18002284A
0x18002283b  lea     rdx, aNtfs; "NTFS"
0x180022842  mov     r8d, 1000h
0x180022848  jmp     short loc_180022873
0x18002284a  lea     r8, [rsp+380h+var_308]; unsigned int *
0x18002284f  lea     rdx, [rsp+380h+var_310]; unsigned __int16 **
0x180022854  lea     rcx, [rbp+280h+szVolumeName]; unsigned __int16 *
0x180022858  call    ?GetFileSystemFormatAndClusterSize@@YAJPEBGPEAPEBGPEAK@Z; GetFileSystemFormatAndClusterSize(ushort const *,ushort const * *,ulong *)
0x18002285d  mov     ebx, eax
0x18002285f  test    eax, eax
0x180022861  js      loc_18002276B
0x180022867  mov     rdx, [rsp+380h+var_310]
0x18002286c  mov     r8d, [rsp+380h+var_308]
0x180022871  xor     ebx, ebx
0x180022873  lea     rax, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x18002287a  mov     rcx, [rax+r14*8+28h]
0x18002287f  add     rcx, 4
0x180022883  add     rcx, r12
0x180022886  call    FormatPartitionWithPath
0x18002288b  mov     r13d, eax
0x18002288e  lea     rcx, [rbp+280h+var_2E8]; lpInterruptTime
0x180022892  call    cs:__imp_QueryInterruptTime
0x180022898  test    r13d, r13d
0x18002289b  js      loc_180022A0F
0x1800228a1  cmp     [rsp+380h+var_31C], 2
0x1800228a6  jnz     loc_180022A0F
0x1800228ac  mov     [rbp+280h+var_2F0], rbx
0x1800228b0  mov     [rbp+280h+var_300], rbx
0x1800228b4  lea     rcx, [rbp+280h+string]; string
0x1800228b8  call    ??$?0$0DO@@StringReference@Internal@Windows@@QEAA@AEAY0DO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[62])
0x1800228bd  lea     rdx, [rbp+280h+var_2F0]
0x1800228c1  mov     rcx, [rax]
0x1800228c4  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x1800228c9  test    eax, eax
0x1800228cb  js      loc_1800229FC
0x1800228d1  lea     rax, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x1800228d8  mov     rcx, [rax+r14*8+28h]
0x1800228dd  add     rcx, 224h
0x1800228e4  add     rcx, r12; rguid
0x1800228e7  mov     r8d, 27h ; '''; cchMax
0x1800228ed  lea     rdx, [rbp+280h+sz]; lpsz
0x1800228f1  call    cs:__imp_StringFromGUID2
0x1800228f7  test    eax, eax
0x1800228f9  jz      loc_1800229FC
0x1800228ff  mov     rdi, [rbp+280h+var_2F0]
0x180022903  mov     rax, [rdi]
0x180022906  mov     rbx, [rax+0E8h]
0x18002290d  lea     rcx, [rbp+280h+var_300]
0x180022911  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022916  lea     rdx, [rbp+280h+sz]; sourceString
0x18002291a  lea     rcx, [rbp+280h+string]; hstringHeader
0x18002291e  call    ??$?0$0CH@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CH@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[39])
0x180022923  nop
0x180022924  lea     r8, [rbp+280h+var_300]
0x180022928  mov     rdx, [rax+18h]
0x18002292c  mov     rcx, rdi
0x18002292f  mov     rax, rbx
0x180022932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022937  nop
0x180022938  xor     ebx, ebx
0x18002293a  mov     [rbp+280h+var_2B0], rbx
0x18002293e  test    eax, eax
0x180022940  js      loc_1800229F9
0x180022946  mov     rdx, [rbp+280h+var_300]; struct Windows::Management::Deployment::IPackageVolume *
0x18002294a  call    ?RemoveAppxPackagesAndVolume@StorageService@@IEAAJPEAUIPackageVolume@Deployment@Management@Windows@@@Z; StorageService::RemoveAppxPackagesAndVolume(Windows::Management::Deployment::IPackageVolume *)
0x18002294f  mov     r8d, eax
0x180022952  mov     ecx, cs:dword_1800BF000
0x180022958  cmp     ecx, 5
0x18002295b  jbe     loc_1800229F9
0x180022961  mov     rdx, 400000000000h
0x18002296b  lea     rcx, dword_1800BF000
0x180022972  call    _tlgKeywordOn
0x180022977  test    al, al
0x180022979  jz      short loc_1800229F9
0x18002297b  mov     [rsp+380h+var_31C], r8d
0x180022980  mov     rdi, r14
0x180022983  lea     rax, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x18002298a  mov     rcx, [rax+r14*8+28h]
0x18002298f  mov     eax, [r12+rcx+44Ch]
0x180022997  mov     [rsp+380h+var_318], eax
0x18002299b  mov     eax, [r12+rcx+448h]
0x1800229a3  mov     [rsp+380h+var_308], eax
0x1800229a7  mov     dword ptr [rsp+380h+var_310], r14d
0x1800229ac  lea     rax, [rcx+224h]
0x1800229b3  add     rax, r12
0x1800229b6  mov     [rbp+280h+var_2E0], rax
0x1800229ba  lea     rax, [rsp+380h+var_31C]
0x1800229bf  mov     [rsp+380h+var_340], rax
0x1800229c4  lea     rax, [rsp+380h+var_318]
0x1800229c9  mov     [rsp+380h+var_348], rax
0x1800229ce  lea     rax, [rsp+380h+var_308]
0x1800229d3  mov     [rsp+380h+var_350], rax
0x1800229d8  lea     rax, [rsp+380h+var_310]
0x1800229dd  mov     [rsp+380h+var_358], rax
0x1800229e2  lea     rax, [rbp+280h+var_2E0]
0x1800229e6  mov     [rsp+380h+var_360], rax
0x1800229eb  lea     rdx, dword_1800A6CCC
0x1800229f2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800229f7  jmp     short loc_1800229FC
0x1800229f9  mov     rdi, r14
0x1800229fc  lea     rcx, [rbp+280h+var_300]
0x180022a00  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022a05  nop
0x180022a06  lea     rcx, [rbp+280h+var_2F0]
0x180022a0a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022a0f  mov     r8d, r15d
0x180022a12  mov     edx, r14d
0x180022a15  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x180022a1c  call    ?DetermineFormatState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::DetermineFormatState(_STORAGE_DEVICE_TYPE,ulong)
0x180022a21  mov     ebx, eax
0x180022a23  test    eax, eax
0x180022a25  js      loc_18002276B
0x180022a2b  lea     rax, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x180022a32  mov     rdx, [rax+rdi*8+28h]
0x180022a37  add     r12, 4
0x180022a3b  add     rdx, r12
0x180022a3e  mov     dword ptr [rsp+380h+var_360], r15d
0x180022a43  mov     r9d, r14d
0x180022a46  lea     r8, [rbp+280h+szVolumeName]
0x180022a4a  lea     r12, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x180022a51  mov     rcx, r12
0x180022a54  call    ?ProcessNewStorageCard@StorageService@@IEAAJPEBG0W4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::ProcessNewStorageCard(ushort const *,ushort const *,_STORAGE_DEVICE_TYPE,ulong)
0x180022a59  mov     ebx, eax
0x180022a5b  test    eax, eax
0x180022a5d  js      short loc_180022A80
0x180022a5f  test    r13d, r13d
0x180022a62  js      short loc_180022A80
0x180022a64  mov     r9d, [rsp+380h+var_314]
0x180022a69  mov     r8d, r15d
0x180022a6c  mov     edx, r14d
0x180022a6f  mov     rcx, r12
0x180022a72  call    ?SetWriteAccess@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::SetWriteAccess(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180022a77  mov     ebx, eax
0x180022a79  jmp     short loc_180022A80
0x180022a7b  mov     ebx, 80071779h
0x180022a80  lea     rcx, stru_1800C10D0; lpCriticalSection
0x180022a87  call    cs:__imp_LeaveCriticalSection
0x180022a8d  lea     rcx, [rbp+280h+var_2D8]; lpInterruptTime
0x180022a91  call    cs:__imp_QueryInterruptTime
0x180022a97  test    r13d, r13d
0x180022a9a  cmovns  r13d, ebx
0x180022a9e  mov     r9d, 1
0x180022aa4  mov     r8d, r15d
0x180022aa7  mov     edx, r14d
0x180022aaa  call    ?CheckDeviceParameters@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::CheckDeviceParameters(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180022aaf  test    eax, eax
0x180022ab1  mov     eax, cs:dword_1800BF000
0x180022ab7  js      loc_180022B9A
0x180022abd  cmp     eax, 5
0x180022ac0  jbe     loc_180022BED
0x180022ac6  mov     rdx, 400000000000h
0x180022ad0  lea     rcx, dword_1800BF000
0x180022ad7  call    _tlgKeywordOn
0x180022adc  test    al, al
0x180022ade  jz      loc_180022BED
0x180022ae4  mov     dword ptr [rsp+380h+var_310], r13d
0x180022ae9  mov     [rsp+380h+var_320], sil
0x180022aee  mov     rax, [rbp+280h+var_2D8]
0x180022af2  sub     rax, [rbp+280h+InterruptTime]
0x180022af6  mov     [rbp+280h+var_2E0], rax
0x180022afa  mov     rax, [rbp+280h+var_2E8]
0x180022afe  sub     rax, [rbp+280h+InterruptTime]
0x180022b02  mov     qword ptr [rsp+380h+var_308], rax
0x180022b07  imul    r8, r15, 458h
0x180022b0e  mov     rdx, [r12+r14*8+28h]
0x180022b13  mov     eax, [rdx+r8+44Ch]
0x180022b1b  mov     [rsp+380h+var_31C], eax
0x180022b1f  mov     eax, [rdx+r8+448h]
0x180022b27  mov     [rsp+380h+var_318], eax
0x180022b2b  mov     [rsp+380h+var_314], r14d
0x180022b30  lea     rax, [r8+224h]
0x180022b37  add     rax, rdx
0x180022b3a  mov     [rbp+280h+var_2D0], rax
0x180022b3e  lea     rax, [rsp+380h+var_310]
  ... truncated ...
```
