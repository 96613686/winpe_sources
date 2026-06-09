# StorageService::SetStorageCardDisabled(_STORAGE_DEVICE_TYPE,ulong,ulong)

- ea: `0x180029aa8`
- end: `0x180029c55`
- name: `?SetStorageCardDisabled@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, service_task, installer_update`

## callers

- `0x18002a048`

## callees

- `0x180001d84`
- `0x18000d030`
- `0x18001feb8`
- `0x1800200e8`
- `0x1800218d0`
- `0x180025efc`
- `0x180025f5c`
- `0x180029aa8`
- `0x18002a3a0`
- `0x18002c1b4`
- `0x18003f188`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029aeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029aeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029bcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029bcd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180029bae`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180029bae`

## pseudocode

```c
__int64 __fastcall StorageService::SetStorageCardDisabled(__int64 a1, int a2, unsigned int a3, int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  __int64 v5; // rsi
  __int64 v7; // rdi
  int v8; // ebx
  int updated; // eax
  int v10; // r9d
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  int v14; // [rsp+4Ch] [rbp-B4h] BYREF
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v16[3]; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR szVolumeName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 1584);
  v5 = a3;
  v7 = a2;
  *(_DWORD *)Data = a4;
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1584));
  if ( (unsigned int)StorageService::IsVolumeStatusSet(a1, (unsigned int)v7, (unsigned int)v5, 8) != *(_DWORD *)Data )
  {
    v8 = SetStorageRegSetting(L"StorageCardDisabled", 4u, Data, 1);
    if ( v8 >= 0 )
    {
      if ( *(_DWORD *)Data )
      {
        if ( (unsigned int)StorageService::CheckPresenceState(a1, (unsigned int)v7, (unsigned int)v5, 2)
          || (v8 = StorageService::DismountVolume(a1, v7, v5, 1), v8 >= 0) )
        {
          StorageService::SetVolumeStatus(a1, (unsigned int)v7, (unsigned int)v5, 8);
          updated = StorageService::UpdateVolumeStatus(a1, (unsigned int)v7, (unsigned int)v5);
LABEL_9:
          v8 = updated;
        }
      }
      else
      {
        StorageService::ClearVolumeStatus(a1, (unsigned int)v7, (unsigned int)v5, 8);
        if ( GetVolumeNameForVolumeMountPointW(
               (LPCWSTR)(*(_QWORD *)(a1 + 8 * v7 + 40) + 4LL + 1112 * v5),
               szVolumeName,
               0x104u) )
        {
          updated = StorageService::MountVolume(a1, v7, v5, 0);
          goto LABEL_9;
        }
      }
    }
  }
  LeaveCriticalSection(v4);
  if ( v8 < 0 && (unsigned int)dword_1800BF000 > 5 )
  {
    v14 = *(_DWORD *)Data;
    v13 = v8;
    v15 = v5;
    v16[0] = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)byte_1800A69DD,
      0,
      v10,
      (__int64)v16,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v13);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180029aa8  push    rbp
0x180029aaa  push    rbx
0x180029aab  push    rsi
0x180029aac  push    rdi
0x180029aad  push    r14
0x180029aaf  push    r15
0x180029ab1  lea     rbp, [rsp-188h]
0x180029ab9  sub     rsp, 288h
0x180029ac0  mov     rax, cs:__security_cookie
0x180029ac7  xor     rax, rsp
0x180029aca  mov     [rbp+1B0h+var_40], rax
0x180029ad1  lea     r15, [rcx+630h]
0x180029ad8  mov     esi, r8d
0x180029adb  mov     r14, rcx
0x180029ade  movsxd  rdi, edx
0x180029ae1  mov     rcx, r15; lpCriticalSection
0x180029ae4  mov     dword ptr [rsp+2B0h+Data], r9d
0x180029ae9  xor     ebx, ebx
0x180029aeb  call    cs:__imp_EnterCriticalSection
0x180029af1  lea     r9d, [rbx+8]
0x180029af5  mov     r8d, esi
0x180029af8  mov     edx, edi
0x180029afa  mov     rcx, r14
0x180029afd  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180029b02  cmp     eax, dword ptr [rsp+2B0h+Data]
0x180029b06  jz      loc_180029BCA
0x180029b0c  lea     r9d, [rbx+1]; int
0x180029b10  lea     r8, [rsp+2B0h+Data]; lpData
0x180029b15  lea     edx, [rbx+4]; cbData
0x180029b18  lea     rcx, aStoragecarddis; "StorageCardDisabled"
0x180029b1f  call    ?SetStorageRegSetting@@YAJPEBGKPEAXH@Z; SetStorageRegSetting(ushort const *,ulong,void *,int)
0x180029b24  mov     ebx, eax
0x180029b26  test    eax, eax
0x180029b28  js      loc_180029BCA
0x180029b2e  cmp     dword ptr [rsp+2B0h+Data], 0
0x180029b33  mov     r8d, esi
0x180029b36  mov     edx, edi
0x180029b38  mov     rcx, r14
0x180029b3b  jz      short loc_180029B85
0x180029b3d  mov     r9d, 2
0x180029b43  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x180029b48  test    eax, eax
0x180029b4a  jnz     short loc_180029B63
0x180029b4c  lea     r9d, [rax+1]
0x180029b50  mov     r8d, esi
0x180029b53  mov     edx, edi
0x180029b55  mov     rcx, r14
0x180029b58  call    ?DismountVolume@StorageService@@QEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::DismountVolume(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180029b5d  mov     ebx, eax
0x180029b5f  test    eax, eax
0x180029b61  js      short loc_180029BCA
0x180029b63  mov     r9d, 8
0x180029b69  mov     r8d, esi
0x180029b6c  mov     edx, edi
0x180029b6e  mov     rcx, r14
0x180029b71  call    ?SetVolumeStatus@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::SetVolumeStatus(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180029b76  mov     r8d, esi
0x180029b79  mov     edx, edi
0x180029b7b  mov     rcx, r14
0x180029b7e  call    ?UpdateVolumeStatus@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::UpdateVolumeStatus(_STORAGE_DEVICE_TYPE,ulong)
0x180029b83  jmp     short loc_180029BC8
0x180029b85  mov     r9d, 8
0x180029b8b  call    ?ClearVolumeStatus@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::ClearVolumeStatus(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180029b90  mov     rax, [r14+rdi*8+28h]
0x180029b95  lea     rdx, [rsp+2B0h+szVolumeName]; lpszVolumeName
0x180029b9a  add     rax, 4
0x180029b9e  mov     r8d, 104h; cchBufferLength
0x180029ba4  imul    rcx, rsi, 458h
0x180029bab  add     rcx, rax; lpszVolumeMountPoint
0x180029bae  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180029bb4  test    eax, eax
0x180029bb6  jz      short loc_180029BCA
0x180029bb8  xor     r9d, r9d
0x180029bbb  mov     r8d, esi
0x180029bbe  mov     edx, edi
0x180029bc0  mov     rcx, r14
0x180029bc3  call    ?MountVolume@StorageService@@QEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::MountVolume(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180029bc8  mov     ebx, eax
0x180029bca  mov     rcx, r15; lpCriticalSection
0x180029bcd  call    cs:__imp_LeaveCriticalSection
0x180029bd3  test    ebx, ebx
0x180029bd5  jns     short loc_180029C34
0x180029bd7  mov     eax, cs:dword_1800BF000
0x180029bdd  cmp     eax, 5
0x180029be0  jbe     short loc_180029C34
0x180029be2  mov     eax, dword ptr [rsp+2B0h+Data]
0x180029be6  lea     rdx, byte_1800A69DD
0x180029bed  mov     [rsp+2B0h+var_264], eax
0x180029bf1  lea     rcx, dword_1800BF000
0x180029bf8  lea     rax, [rsp+2B0h+var_268]
0x180029bfd  mov     [rsp+2B0h+var_268], ebx
0x180029c01  mov     [rsp+2B0h+var_278], rax
0x180029c06  xor     r8d, r8d
0x180029c09  lea     rax, [rsp+2B0h+var_264]
0x180029c0e  mov     [rsp+2B0h+var_260], esi
0x180029c12  mov     [rsp+2B0h+var_280], rax
0x180029c17  lea     rax, [rsp+2B0h+var_260]
0x180029c1c  mov     [rsp+2B0h+var_288], rax
0x180029c21  lea     rax, [rsp+2B0h+var_25C]
0x180029c26  mov     [rsp+2B0h+var_290], rax
0x180029c2b  mov     [rsp+2B0h+var_25C], edi
0x180029c2f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029c34  mov     eax, ebx
0x180029c36  mov     rcx, [rbp+1B0h+var_40]
0x180029c3d  xor     rcx, rsp; StackCookie
0x180029c40  call    __security_check_cookie
0x180029c45  add     rsp, 288h
0x180029c4c  pop     r15
0x180029c4e  pop     r14
0x180029c50  pop     rdi
0x180029c51  pop     rsi
0x180029c52  pop     rbx
0x180029c53  pop     rbp
0x180029c54  retn
```
