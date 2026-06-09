# StorageService::DismountVolume(_STORAGE_DEVICE_TYPE,ulong,ulong)

- ea: `0x1800218d0`
- end: `0x180021cbd`
- name: `?DismountVolume@StorageService@@QEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z`
- size: `1005`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `reparse_path, service_task, installer_update`

## callers

- `0x180020c3c`
- `0x180029aa8`
- `0x1800373c0`

## callees

- `0x180001148`
- `0x180001248`
- `0x180001768`
- `0x180001c80`
- `0x18000d030`
- `0x18000d450`
- `0x18001a0b8`
- `0x18001a70c`
- `0x18001b7d4`
- `0x18001fe50`
- `0x18001feb8`
- `0x180020088`
- `0x1800218d0`
- `0x180027080`
- `0x18002bd7c`
- `0x18002bfdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021920`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021994`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021bf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021bf8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021b23`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021bb4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021b23`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021bb4`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180021a84`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180021a84`

## pseudocode

```c
__int64 __fastcall StorageService::DismountVolume(__int64 a1, int a2, unsigned int a3, char a4)
{
  __int64 v5; // r14
  __int64 v6; // rsi
  __int64 v8; // rcx
  signed int LastHr; // ebx
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // r9d
  __int64 v13; // rdx
  signed int LastError; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  void *v17; // r15
  int v18; // eax
  int v19; // eax
  int v20; // r9d
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+54h] [rbp-ACh] BYREF
  signed int v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+5Ch] [rbp-A4h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  GUID *v27; // [rsp+68h] [rbp-98h] BYREF
  GUID v28; // [rsp+70h] [rbp-90h] BYREF
  WCHAR szVolumeName[264]; // [rsp+80h] [rbp-80h] BYREF

  v5 = a3;
  v6 = a2;
  v28 = GUID_NULL;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1584));
  LastHr = StorageService::CheckDeviceParameters(v8, (unsigned int)v6, (unsigned int)v5, 1);
  if ( LastHr < 0 )
    goto LABEL_5;
  v28 = *(GUID *)(*(_QWORD *)(a1 + 8 * v6 + 40) + 1112 * v5 + 548);
  if ( !(unsigned int)StorageService::CheckPresenceState(a1, (unsigned int)v6, (unsigned int)v5, 0)
    && !(unsigned int)StorageService::CheckPresenceState(a1, (unsigned int)v6, (unsigned int)v5, 1) )
  {
    LastHr = -2147418113;
    goto LABEL_5;
  }
  if ( GetVolumeNameForVolumeMountPointW((LPCWSTR)(1112 * v5 + 4 + *(_QWORD *)(a1 + 8 * v6 + 40)), szVolumeName, 0x104u) )
  {
    v15 = -1;
    do
      ++v15;
    while ( szVolumeName[v15] );
    v16 = 2 * v15 - 2;
    if ( v16 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v16) = 0;
    v17 = OpenVolumeHandle(szVolumeName);
    if ( v17 == (void *)-1LL )
    {
      LastHr = GetLastHr();
      goto LABEL_5;
    }
    if ( (a4 & 1) != 0 || DeviceIoControl(v17, 0x90018u, 0, 0, 0, 0, 0, 0) || (int)GetLastHr() >= 0 )
    {
      v18 = DismountVolume(v17);
      if ( v18 < 0 )
      {
        LastHr = v18;
        if ( (unsigned int)dword_1800BF000 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1800BF000,
            byte_1800A5F2B,
            0,
            0);
      }
      if ( DeviceIoControl(v17, 0x56C00Cu, 0, 0, 0, 0, 0, 0) || (v19 = GetLastHr(), v19 >= 0) )
      {
        if ( LastHr >= 0 )
        {
          LastHr = StorageService::UpdateDismountState(a1, (unsigned int)v6, (unsigned int)v5, 1);
          if ( LastHr >= 0 )
          {
            if ( (a4 & 2) != 0 )
            {
              --*(_DWORD *)(a1 + 4 * v6 + 28);
              StorageService::ClearStorageCardPaths(a1, (unsigned int)v6, (unsigned int)v5);
            }
            goto LABEL_30;
          }
        }
      }
      else
      {
        LastHr = v19;
        if ( (unsigned int)dword_1800BF000 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1800BF000,
            &word_1800A724E,
            0,
            0);
      }
      StorageService::ProcessVolumeChange((StorageService *)a1);
    }
    else
    {
      LastHr = StorageService::UpdatePresenceState(a1, (unsigned int)v6, (unsigned int)v5, 1);
      if ( LastHr >= 0 )
        LastHr = -2147483638;
    }
LABEL_30:
    CloseHandle(v17);
    goto LABEL_5;
  }
  LastError = GetLastError();
  LastHr = LastError;
  if ( LastError > 0 )
    LastHr = (unsigned __int16)LastError | 0x80070000;
LABEL_5:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1584));
  if ( (int)StorageService::CheckDeviceParameters(v10, (unsigned int)v6, (unsigned int)v5, 1) < 0 )
  {
    if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
    {
      v23 = v5;
      v22 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BF000,
        (unsigned int)&dword_1800A78B4,
        0,
        v20,
        (__int64)&v22,
        (__int64)&v23);
    }
  }
  else if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    v13 = *(_QWORD *)(a1 + 8 * v6 + 40);
    v24 = LastHr;
    v25 = *(_DWORD *)(v13 + 1112 * v5 + 536);
    v26 = *(_DWORD *)(v13 + 1112 * v5 + 532);
    v22 = *(_DWORD *)(v13 + 1112 * v5 + 1096);
    v27 = &v28;
    v23 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)byte_1800A7653,
      1112 * v5,
      v12,
      (__int64)&v27,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24);
  }
  return (unsigned int)LastHr;
}

```

## disassembly

```asm
0x1800218d0  mov     [rsp-8+arg_18], rbx
0x1800218d5  push    rbp
0x1800218d6  push    rsi
0x1800218d7  push    rdi
0x1800218d8  push    r12
0x1800218da  push    r13
0x1800218dc  push    r14
0x1800218de  push    r15
0x1800218e0  lea     rbp, [rsp-1A0h]
0x1800218e8  sub     rsp, 2A0h
0x1800218ef  mov     rax, cs:__security_cookie
0x1800218f6  xor     rax, rsp
0x1800218f9  mov     [rbp+1D0h+var_40], rax
0x180021900  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180021907  mov     rdi, rcx
0x18002190a  mov     r14d, r8d
0x18002190d  add     rcx, 630h; lpCriticalSection
0x180021914  movsxd  rsi, edx
0x180021917  movdqu  [rsp+2D0h+var_260], xmm0
0x18002191d  mov     r13d, r9d
0x180021920  call    cs:__imp_EnterCriticalSection
0x180021926  mov     r9d, 1
0x18002192c  mov     r8d, r14d
0x18002192f  mov     edx, esi
0x180021931  call    ?CheckDeviceParameters@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::CheckDeviceParameters(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180021936  mov     ebx, eax
0x180021938  test    eax, eax
0x18002193a  js      short loc_18002198D
0x18002193c  mov     rcx, [rdi+rsi*8+28h]
0x180021941  xor     r9d, r9d
0x180021944  imul    r15, r14, 458h
0x18002194b  mov     r8d, r14d
0x18002194e  mov     edx, esi
0x180021950  movups  xmm0, xmmword ptr [rcx+r15+224h]
0x180021959  mov     rcx, rdi
0x18002195c  movdqu  [rsp+2D0h+var_260], xmm0
0x180021962  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x180021967  test    eax, eax
0x180021969  jnz     loc_180021A6E
0x18002196f  lea     r9d, [rax+1]
0x180021973  mov     r8d, r14d
0x180021976  mov     edx, esi
0x180021978  mov     rcx, rdi
0x18002197b  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x180021980  test    eax, eax
0x180021982  jnz     loc_180021A6E
0x180021988  mov     ebx, 8000FFFFh
0x18002198d  lea     rcx, [rdi+630h]; lpCriticalSection
0x180021994  call    cs:__imp_LeaveCriticalSection
0x18002199a  mov     r9d, 1
0x1800219a0  mov     r8d, r14d
0x1800219a3  mov     edx, esi
0x1800219a5  call    ?CheckDeviceParameters@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::CheckDeviceParameters(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x1800219aa  test    eax, eax
0x1800219ac  mov     eax, cs:dword_1800BF000
0x1800219b2  js      loc_180021C39
0x1800219b8  cmp     eax, 5
0x1800219bb  jbe     loc_180021C8B
0x1800219c1  mov     rdx, 400000000000h
0x1800219cb  lea     rcx, dword_1800BF000
0x1800219d2  call    _tlgKeywordOn
0x1800219d7  test    al, al
0x1800219d9  jz      loc_180021C8B
0x1800219df  mov     rdx, [rdi+rsi*8+28h]
0x1800219e4  imul    r8, r14, 458h
0x1800219eb  mov     [rsp+2D0h+var_278], ebx
0x1800219ef  mov     eax, [rdx+r8+218h]
0x1800219f7  mov     [rsp+2D0h+var_274], eax
0x1800219fb  mov     eax, [rdx+r8+214h]
0x180021a03  mov     [rsp+2D0h+var_270], eax
0x180021a07  mov     eax, [rdx+r8+448h]
0x180021a0f  lea     rdx, byte_1800A7653
0x180021a16  mov     [rsp+2D0h+var_280], eax
0x180021a1a  lea     rax, [rsp+2D0h+var_260]
0x180021a1f  mov     [rsp+2D0h+var_268], rax
0x180021a24  lea     rax, [rsp+2D0h+var_278]
0x180021a29  mov     [rsp+2D0h+var_288], rax
0x180021a2e  lea     rax, [rsp+2D0h+var_274]
0x180021a33  mov     [rsp+2D0h+var_290], rax
0x180021a38  lea     rax, [rsp+2D0h+var_270]
0x180021a3d  mov     [rsp+2D0h+lpOverlapped], rax
0x180021a42  lea     rax, [rsp+2D0h+var_280]
0x180021a47  mov     [rsp+2D0h+lpBytesReturned], rax
0x180021a4c  lea     rax, [rsp+2D0h+var_27C]
0x180021a51  mov     qword ptr [rsp+2D0h+nOutBufferSize], rax
0x180021a56  lea     rax, [rsp+2D0h+var_268]
0x180021a5b  mov     [rsp+2D0h+lpOutBuffer], rax
0x180021a60  mov     [rsp+2D0h+var_27C], esi
0x180021a64  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180021a69  jmp     loc_180021C8B
0x180021a6e  mov     rcx, [rdi+rsi*8+28h]
0x180021a73  lea     rdx, [rbp+1D0h+szVolumeName]; lpszVolumeName
0x180021a77  add     r15, 4
0x180021a7b  mov     r8d, 104h; cchBufferLength
0x180021a81  add     rcx, r15; lpszVolumeMountPoint
0x180021a84  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180021a8a  xor     r15d, r15d
0x180021a8d  test    eax, eax
0x180021a8f  jnz     short loc_180021AAF
0x180021a91  call    cs:__imp_GetLastError
0x180021a97  mov     ebx, eax
0x180021a99  test    eax, eax
0x180021a9b  jle     loc_18002198D
0x180021aa1  movzx   ebx, ax
0x180021aa4  or      ebx, 80070000h
0x180021aaa  jmp     loc_18002198D
0x180021aaf  lea     rcx, [rbp+1D0h+szVolumeName]
0x180021ab3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021ab7  inc     rax
0x180021aba  cmp     [rcx+rax*2], r15w
0x180021abf  jnz     short loc_180021AB7
0x180021ac1  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180021ac9  cmp     rcx, 208h
0x180021ad0  jnb     loc_180021CB7
0x180021ad6  mov     [rbp+rcx+1D0h+szVolumeName], r15w
0x180021adc  lea     rcx, [rbp+1D0h+szVolumeName]; unsigned __int16 *
0x180021ae0  call    ?OpenVolumeHandle@@YAPEAXPEBG@Z; OpenVolumeHandle(ushort const *)
0x180021ae5  mov     r15, rax
0x180021ae8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021aec  jnz     short loc_180021AFA
0x180021aee  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x180021af3  mov     ebx, eax
0x180021af5  jmp     loc_18002198D
0x180021afa  test    r13b, 1
0x180021afe  jnz     short loc_180021B5D
0x180021b00  xor     eax, eax
0x180021b02  xor     r9d, r9d; nInBufferSize
0x180021b05  mov     [rsp+2D0h+lpOverlapped], rax; lpOverlapped
0x180021b0a  xor     r8d, r8d; lpInBuffer
0x180021b0d  mov     [rsp+2D0h+lpBytesReturned], rax; lpBytesReturned
0x180021b12  mov     edx, 90018h; dwIoControlCode
0x180021b17  mov     [rsp+2D0h+nOutBufferSize], eax; nOutBufferSize
0x180021b1b  mov     rcx, r15; hDevice
0x180021b1e  mov     [rsp+2D0h+lpOutBuffer], rax; lpOutBuffer
0x180021b23  call    cs:__imp_DeviceIoControl
0x180021b29  test    eax, eax
0x180021b2b  jnz     short loc_180021B5D
0x180021b2d  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x180021b32  test    eax, eax
0x180021b34  jns     short loc_180021B5D
0x180021b36  mov     r9d, 1
0x180021b3c  mov     r8d, r14d
0x180021b3f  mov     edx, esi
0x180021b41  mov     rcx, rdi
0x180021b44  call    ?UpdatePresenceState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::UpdatePresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x180021b49  mov     ebx, eax
0x180021b4b  test    eax, eax
0x180021b4d  js      loc_180021BF5
0x180021b53  mov     ebx, 8000000Ah
0x180021b58  jmp     loc_180021BF5
0x180021b5d  mov     rcx, r15; void *
0x180021b60  call    ?DismountVolume@@YAJPEAX@Z; DismountVolume(void *)
0x180021b65  xor     ecx, ecx
0x180021b67  test    eax, eax
0x180021b69  jns     short loc_180021B93
0x180021b6b  mov     ebx, eax
0x180021b6d  mov     eax, cs:dword_1800BF000
0x180021b73  cmp     eax, 5
0x180021b76  jbe     short loc_180021B93
0x180021b78  xor     r9d, r9d
0x180021b7b  lea     rdx, byte_1800A5F2B
0x180021b82  xor     r8d, r8d
0x180021b85  lea     rcx, dword_1800BF000
0x180021b8c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180021b91  xor     ecx, ecx
0x180021b93  mov     [rsp+2D0h+lpOverlapped], rcx; lpOverlapped
0x180021b98  xor     r9d, r9d; nInBufferSize
0x180021b9b  mov     [rsp+2D0h+lpBytesReturned], rcx; lpBytesReturned
0x180021ba0  xor     r8d, r8d; lpInBuffer
0x180021ba3  mov     [rsp+2D0h+nOutBufferSize], ecx; nOutBufferSize
0x180021ba7  mov     edx, 56C00Ch; dwIoControlCode
0x180021bac  mov     [rsp+2D0h+lpOutBuffer], rcx; lpOutBuffer
0x180021bb1  mov     rcx, r15; hDevice
0x180021bb4  call    cs:__imp_DeviceIoControl
0x180021bba  test    eax, eax
0x180021bbc  jnz     short loc_180021C03
0x180021bbe  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x180021bc3  test    eax, eax
0x180021bc5  jns     short loc_180021C03
0x180021bc7  mov     ebx, eax
0x180021bc9  mov     eax, cs:dword_1800BF000
0x180021bcf  cmp     eax, 5
0x180021bd2  jbe     short loc_180021BED
0x180021bd4  xor     r9d, r9d
0x180021bd7  lea     rdx, word_1800A724E
0x180021bde  xor     r8d, r8d
0x180021be1  lea     rcx, dword_1800BF000
0x180021be8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180021bed  mov     rcx, rdi; this
0x180021bf0  call    ?ProcessVolumeChange@StorageService@@QEAAJXZ; StorageService::ProcessVolumeChange(void)
0x180021bf5  mov     rcx, r15; hObject
0x180021bf8  call    cs:__imp_CloseHandle
0x180021bfe  jmp     loc_18002198D
0x180021c03  test    ebx, ebx
0x180021c05  js      short loc_180021BED
0x180021c07  mov     r9d, 1
0x180021c0d  mov     r8d, r14d
0x180021c10  mov     edx, esi
0x180021c12  mov     rcx, rdi
0x180021c15  call    ?UpdateDismountState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_DISMOUNT_REASON@@@Z; StorageService::UpdateDismountState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DISMOUNT_REASON)
0x180021c1a  mov     ebx, eax
0x180021c1c  test    eax, eax
0x180021c1e  js      short loc_180021BED
0x180021c20  test    r13b, 2
0x180021c24  jz      short loc_180021BF5
0x180021c26  dec     dword ptr [rdi+rsi*4+1Ch]
0x180021c2a  mov     r8d, r14d
0x180021c2d  mov     edx, esi
0x180021c2f  mov     rcx, rdi
0x180021c32  call    ?ClearStorageCardPaths@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::ClearStorageCardPaths(_STORAGE_DEVICE_TYPE,ulong)
0x180021c37  jmp     short loc_180021BF5
0x180021c39  cmp     eax, 5
0x180021c3c  jbe     short loc_180021C8B
0x180021c3e  mov     rdx, 400000000000h
0x180021c48  lea     rcx, dword_1800BF000
0x180021c4f  call    _tlgKeywordOn
0x180021c54  test    al, al
0x180021c56  jz      short loc_180021C8B
0x180021c58  lea     rax, [rsp+2D0h+var_27C]
0x180021c5d  mov     [rsp+2D0h+var_27C], r14d
0x180021c62  mov     qword ptr [rsp+2D0h+nOutBufferSize], rax
0x180021c67  lea     rdx, dword_1800A78B4
0x180021c6e  lea     rax, [rsp+2D0h+var_280]
0x180021c73  mov     [rsp+2D0h+var_280], esi
0x180021c77  xor     r8d, r8d
0x180021c7a  mov     [rsp+2D0h+lpOutBuffer], rax
0x180021c7f  lea     rcx, dword_1800BF000
0x180021c86  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180021c8b  mov     eax, ebx
0x180021c8d  mov     rcx, [rbp+1D0h+var_40]
0x180021c94  xor     rcx, rsp; StackCookie
0x180021c97  call    __security_check_cookie
0x180021c9c  mov     rbx, [rsp+2D0h+arg_18]
0x180021ca4  add     rsp, 2A0h
0x180021cab  pop     r15
0x180021cad  pop     r14
0x180021caf  pop     r13
0x180021cb1  pop     r12
0x180021cb3  pop     rdi
0x180021cb4  pop     rsi
0x180021cb5  pop     rbp
0x180021cb6  retn
0x180021cb7  call    __report_rangecheckfailure
```
