# StorageService::MountVolume(_STORAGE_DEVICE_TYPE,ulong,ulong)

- ea: `0x180025f5c`
- end: `0x1800261c0`
- name: `?MountVolume@StorageService@@QEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z`
- size: `612`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, service_task`

## callers

- `0x180029aa8`
- `0x1800377b0`

## callees

- `0x180001248`
- `0x180001d84`
- `0x18000d030`
- `0x18000d450`
- `0x18001a70c`
- `0x18001b7d4`
- `0x18001fe50`
- `0x18001feb8`
- `0x180025efc`
- `0x180025f5c`
- `0x180027080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025fa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025fa2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025fe5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800260bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800260bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261af`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026147`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026147`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800260b3`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800260b3`

## pseudocode

```c
__int64 __fastcall StorageService::MountVolume(__int64 a1, int a2, unsigned int a3, int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r12
  __int64 v5; // r15
  __int64 v7; // r14
  __int64 v9; // rcx
  signed int LastHr; // ebx
  int v11; // r9d
  __int64 v13; // rax
  unsigned __int64 v14; // rcx
  void *v15; // rax
  void *v16; // rdi
  signed int v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+44h] [rbp-BCh] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR szVolumeName[264]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 1584);
  v5 = a3;
  v7 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1584));
  LastHr = StorageService::CheckDeviceParameters(v9, (unsigned int)v7, (unsigned int)v5, 1);
  if ( LastHr < 0 )
    goto LABEL_4;
  if ( !(unsigned int)StorageService::CheckPresenceState(a1, (unsigned int)v7, (unsigned int)v5, 2) )
  {
    LastHr = -2147418113;
    goto LABEL_4;
  }
  if ( (unsigned int)StorageService::IsVolumeStatusSet(a1, (unsigned int)v7, (unsigned int)v5, 8) )
  {
    LastHr = -2147024891;
    goto LABEL_4;
  }
  if ( GetVolumeNameForVolumeMountPointW(
         (LPCWSTR)(*(_QWORD *)(a1 + 8 * v7 + 40) + 4LL + 1112 * v5),
         szVolumeName,
         0x104u) )
  {
    v13 = -1;
    do
      ++v13;
    while ( szVolumeName[v13] );
    v14 = 2 * v13 - 2;
    if ( v14 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v14) = 0;
    v15 = OpenVolumeHandle(szVolumeName);
    v16 = v15;
    if ( v15 == (void *)-1LL )
      goto LABEL_16;
    if ( DeviceIoControl(v15, 0x56C008u, 0, 0, 0, 0, 0, 0) || (LastHr = GetLastHr(), LastHr >= 0) )
    {
      CloseHandle(v16);
      v16 = OpenVolumeHandle(szVolumeName);
      if ( v16 == (void *)-1LL )
      {
LABEL_16:
        LastHr = GetLastHr();
        goto LABEL_4;
      }
      LastHr = StorageService::ProcessVolumeChange((StorageService *)a1);
    }
    else if ( (unsigned int)dword_1800BF000 > 5 )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1800BF000,
        byte_1800A5C19,
        0,
        0);
    }
    CloseHandle(v16);
    goto LABEL_4;
  }
  LastHr = GetLastError();
  if ( LastHr > 0 )
    LastHr = (unsigned __int16)LastHr | 0x80070000;
LABEL_4:
  LeaveCriticalSection(v4);
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    v17 = LastHr;
    v18 = a4;
    v19 = v5;
    v20 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)&unk_1800A6950,
      0,
      v11,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v17);
  }
  return (unsigned int)LastHr;
}

```

## disassembly

```asm
0x180025f5c  mov     [rsp-8+arg_18], rbx
0x180025f61  push    rbp
0x180025f62  push    rsi
0x180025f63  push    rdi
0x180025f64  push    r12
0x180025f66  push    r13
0x180025f68  push    r14
0x180025f6a  push    r15
0x180025f6c  lea     rbp, [rsp-170h]
0x180025f74  sub     rsp, 270h
0x180025f7b  mov     rax, cs:__security_cookie
0x180025f82  xor     rax, rsp
0x180025f85  mov     [rbp+1A0h+var_40], rax
0x180025f8c  lea     r12, [rcx+630h]
0x180025f93  mov     r15d, r8d
0x180025f96  mov     rsi, rcx
0x180025f99  movsxd  r14, edx
0x180025f9c  mov     rcx, r12; lpCriticalSection
0x180025f9f  mov     r13d, r9d
0x180025fa2  call    cs:__imp_EnterCriticalSection
0x180025fa8  mov     r9d, 1
0x180025fae  mov     r8d, r15d
0x180025fb1  mov     edx, r14d
0x180025fb4  call    ?CheckDeviceParameters@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::CheckDeviceParameters(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180025fb9  mov     ebx, eax
0x180025fbb  test    eax, eax
0x180025fbd  js      short loc_180025FE2
0x180025fbf  mov     r9d, 2
0x180025fc5  mov     r8d, r15d
0x180025fc8  mov     edx, r14d
0x180025fcb  mov     rcx, rsi
0x180025fce  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x180025fd3  xor     ebx, ebx
0x180025fd5  test    eax, eax
0x180025fd7  jnz     loc_180026073
0x180025fdd  mov     ebx, 8000FFFFh
0x180025fe2  mov     rcx, r12; lpCriticalSection
0x180025fe5  call    cs:__imp_LeaveCriticalSection
0x180025feb  mov     eax, cs:dword_1800BF000
0x180025ff1  cmp     eax, 5
0x180025ff4  jbe     short loc_180026047
0x180025ff6  lea     rax, [rsp+2A0h+var_260]
0x180025ffb  mov     [rsp+2A0h+var_260], ebx
0x180025fff  mov     [rsp+2A0h+lpOverlapped], rax
0x180026004  lea     rdx, unk_1800A6950
0x18002600b  lea     rax, [rsp+2A0h+var_25C]
0x180026010  mov     [rsp+2A0h+var_25C], r13d
0x180026015  mov     [rsp+2A0h+lpBytesReturned], rax
0x18002601a  lea     rcx, dword_1800BF000
0x180026021  lea     rax, [rsp+2A0h+var_258]
0x180026026  mov     [rsp+2A0h+var_258], r15d
0x18002602b  mov     qword ptr [rsp+2A0h+nOutBufferSize], rax
0x180026030  xor     r8d, r8d
0x180026033  lea     rax, [rsp+2A0h+var_254]
0x180026038  mov     [rsp+2A0h+var_254], r14d
0x18002603d  mov     [rsp+2A0h+lpOutBuffer], rax
0x180026042  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180026047  mov     eax, ebx
0x180026049  mov     rcx, [rbp+1A0h+var_40]
0x180026050  xor     rcx, rsp; StackCookie
0x180026053  call    __security_check_cookie
0x180026058  mov     rbx, [rsp+2A0h+arg_18]
0x180026060  add     rsp, 270h
0x180026067  pop     r15
0x180026069  pop     r14
0x18002606b  pop     r13
0x18002606d  pop     r12
0x18002606f  pop     rdi
0x180026070  pop     rsi
0x180026071  pop     rbp
0x180026072  retn
0x180026073  mov     r9d, 8
0x180026079  mov     r8d, r15d
0x18002607c  mov     edx, r14d
0x18002607f  mov     rcx, rsi
0x180026082  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180026087  test    eax, eax
0x180026089  jz      short loc_180026095
0x18002608b  mov     ebx, 80070005h
0x180026090  jmp     loc_180025FE2
0x180026095  mov     rax, [rsi+r14*8+28h]
0x18002609a  lea     rdx, [rsp+2A0h+szVolumeName]; lpszVolumeName
0x18002609f  add     rax, 4
0x1800260a3  mov     r8d, 104h; cchBufferLength
0x1800260a9  imul    rcx, r15, 458h
0x1800260b0  add     rcx, rax; lpszVolumeMountPoint
0x1800260b3  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800260b9  test    eax, eax
0x1800260bb  jnz     short loc_1800260DB
0x1800260bd  call    cs:__imp_GetLastError
0x1800260c3  mov     ebx, eax
0x1800260c5  test    eax, eax
0x1800260c7  jle     loc_180025FE2
0x1800260cd  movzx   ebx, bx
0x1800260d0  or      ebx, 80070000h
0x1800260d6  jmp     loc_180025FE2
0x1800260db  lea     rcx, [rsp+2A0h+szVolumeName]
0x1800260e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800260e4  inc     rax
0x1800260e7  cmp     [rcx+rax*2], bx
0x1800260eb  jnz     short loc_1800260E4
0x1800260ed  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1800260f5  cmp     rcx, 208h
0x1800260fc  jnb     loc_1800261BA
0x180026102  mov     [rsp+rcx+2A0h+szVolumeName], bx
0x180026107  lea     rcx, [rsp+2A0h+szVolumeName]; unsigned __int16 *
0x18002610c  call    ?OpenVolumeHandle@@YAPEAXPEBG@Z; OpenVolumeHandle(ushort const *)
0x180026111  mov     rdi, rax
0x180026114  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026118  jnz     short loc_180026126
0x18002611a  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x18002611f  mov     ebx, eax
0x180026121  jmp     loc_180025FE2
0x180026126  mov     [rsp+2A0h+lpOverlapped], rbx; lpOverlapped
0x18002612b  xor     r9d, r9d; nInBufferSize
0x18002612e  mov     [rsp+2A0h+lpBytesReturned], rbx; lpBytesReturned
0x180026133  xor     r8d, r8d; lpInBuffer
0x180026136  mov     [rsp+2A0h+nOutBufferSize], ebx; nOutBufferSize
0x18002613a  mov     edx, 56C008h; dwIoControlCode
0x18002613f  mov     rcx, rdi; hDevice
0x180026142  mov     [rsp+2A0h+lpOutBuffer], rbx; lpOutBuffer
0x180026147  call    cs:__imp_DeviceIoControl
0x18002614d  test    eax, eax
0x18002614f  jnz     short loc_180026182
0x180026151  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x180026156  mov     ebx, eax
0x180026158  test    eax, eax
0x18002615a  jns     short loc_180026182
0x18002615c  mov     eax, cs:dword_1800BF000
0x180026162  cmp     eax, 5
0x180026165  jbe     short loc_1800261AC
0x180026167  xor     r9d, r9d
0x18002616a  lea     rdx, byte_1800A5C19
0x180026171  xor     r8d, r8d
0x180026174  lea     rcx, dword_1800BF000
0x18002617b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180026180  jmp     short loc_1800261AC
0x180026182  mov     rcx, rdi; hObject
0x180026185  call    cs:__imp_CloseHandle
0x18002618b  lea     rcx, [rsp+2A0h+szVolumeName]; unsigned __int16 *
0x180026190  call    ?OpenVolumeHandle@@YAPEAXPEBG@Z; OpenVolumeHandle(ushort const *)
0x180026195  mov     rdi, rax
0x180026198  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002619c  jz      loc_18002611A
0x1800261a2  mov     rcx, rsi; this
0x1800261a5  call    ?ProcessVolumeChange@StorageService@@QEAAJXZ; StorageService::ProcessVolumeChange(void)
0x1800261aa  mov     ebx, eax
0x1800261ac  mov     rcx, rdi; hObject
0x1800261af  call    cs:__imp_CloseHandle
0x1800261b5  jmp     loc_180025FE2
0x1800261ba  call    __report_rangecheckfailure
```
