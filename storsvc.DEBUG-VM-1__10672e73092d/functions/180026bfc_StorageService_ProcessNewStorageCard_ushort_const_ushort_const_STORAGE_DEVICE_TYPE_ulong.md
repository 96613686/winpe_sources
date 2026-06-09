# StorageService::ProcessNewStorageCard(ushort const *,ushort const *,_STORAGE_DEVICE_TYPE,ulong)

- ea: `0x180026bfc`
- end: `0x18002707a`
- name: `?ProcessNewStorageCard@StorageService@@IEAAJPEBG0W4_STORAGE_DEVICE_TYPE@@K@Z`
- size: `1150`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, enum _STORAGE_DEVICE_TYPE, unsigned int)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180022640`
- `0x180027080`

## callees

- `0x180001148`
- `0x180001908`
- `0x18000231c`
- `0x18000d030`
- `0x180012734`
- `0x180012ce0`
- `0x180019ee8`
- `0x1800209d4`
- `0x180020be0`
- `0x180020c3c`
- `0x180020d2c`
- `0x180020f10`
- `0x180020fe8`
- `0x180022eec`
- `0x180025efc`
- `0x180026bfc`
- `0x180029e68`
- `0x18002bd7c`
- `0x18002bebc`
- `0x18002c1b4`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026ca0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026ca0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026cc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026cc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027000`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027000`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002703a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002703a`

## string_xrefs

- `0x180026f94`: `AccessFlags`
- `0x180026c72`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`

## pseudocode

```c
__int64 __fastcall StorageService::ProcessNewStorageCard(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        DWORD a5)
{
  const unsigned __int16 *v5; // rbx
  __int64 v6; // rsi
  StorageService *v9; // rcx
  int v10; // eax
  signed int updated; // edi
  __int64 v12; // r13
  int v13; // ecx
  int v14; // r9d
  __int64 v15; // r8
  __int64 v16; // rcx
  signed int v18; // eax
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // r8
  int lpData; // [rsp+20h] [rbp-A1h]
  char v23; // [rsp+80h] [rbp-41h] BYREF
  char v24; // [rsp+81h] [rbp-40h] BYREF
  char v25; // [rsp+82h] [rbp-3Fh] BYREF
  char v26; // [rsp+83h] [rbp-3Eh] BYREF
  _BYTE v27[4]; // [rsp+84h] [rbp-3Dh] BYREF
  DWORD cbData; // [rsp+88h] [rbp-39h] BYREF
  unsigned int v29; // [rsp+8Ch] [rbp-35h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-31h] BYREF
  const unsigned __int16 *v31; // [rsp+98h] [rbp-29h] BYREF
  const unsigned __int16 *v32; // [rsp+A0h] [rbp-21h] BYREF
  BYTE Data[16]; // [rsp+A8h] [rbp-19h] BYREF
  WCHAR ValueName[4]; // [rsp+B8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v5 = a3;
  v6 = (int)a4;
  v31 = a3;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  StorageService::DetermineBusType(a1, a3, a4, a5);
  v29 = 0;
  v10 = StorageService::DeterminePersistentVolumeState(v9, v5, &v29);
  updated = v10;
  if ( v10 >= 0 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 8 * v6 + 40) + 1112LL * a5 + 1104) = v29;
    updated = StorageService::SetStorageCardPaths(a1, a2, (unsigned int)v6, a5);
    if ( updated >= 0 )
    {
      v18 = CheckCrashDumpSettings(a2);
      if ( v18 < 0 && (unsigned int)dword_1800BF000 > 5 )
      {
        v29 = v18;
        *(_QWORD *)ValueName = v5;
        v32 = a2;
        LODWORD(hKey) = a5;
        cbData = v6;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          dword_1800BF000,
          (unsigned int)byte_1800A6BEB,
          v19,
          v20,
          (__int64)&cbData,
          (__int64)&hKey,
          (__int64)&v32,
          (__int64)ValueName,
          (__int64)&v29);
      }
      updated = StorageService::DetermineDisabledState(a1, (unsigned int)v6, a5);
      if ( updated < 0 || (unsigned int)StorageService::IsVolumeStatusSet(a1, (unsigned int)v6, a5, 8) )
      {
        v25 = 1;
      }
      else
      {
        updated = StorageService::DetermineFormatState(a1, (unsigned int)v6, a5);
        if ( updated < 0 || (unsigned int)StorageService::IsVolumeStatusSet(a1, (unsigned int)v6, a5, 2) )
        {
          v24 = 1;
        }
        else
        {
          updated = StorageService::DetermineNewCardState(a1, (unsigned int)v6, a5);
          if ( updated < 0 )
            goto LABEL_3;
          updated = StorageService::DetermineAppPairingState(a1, (unsigned int)v6, a5);
          if ( updated < 0 )
            goto LABEL_3;
          if ( (unsigned int)StorageService::GetAppPairingStatus(a1, (unsigned int)v6, a5) == 1 )
          {
            v23 = 1;
            hKey = 0;
            wcscpy(ValueName, L"123");
            cbData = 16;
            *(_OWORD *)Data = 0;
            updated = OpenStorageRegKey(HKEY_LOCAL_MACHINE, (wchar_t *)L"AccessFlags", &hKey);
            if ( updated < 0 )
              goto LABEL_3;
            updated = StringCchPrintfW(ValueName, 4u, L"%02d");
            if ( updated < 0 )
              goto LABEL_3;
            if ( !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
            {
              v21 = *(_QWORD *)(a1 + 8 * v6 + 40);
              if ( *(_QWORD *)Data == *(_QWORD *)(v21 + 1112LL * a5 + 548)
                && *(_QWORD *)&Data[8] == *(_QWORD *)(v21 + 1112LL * a5 + 556) )
              {
                RegDeleteValueW(hKey, ValueName);
              }
            }
          }
          updated = StorageService::UpdateMountState(a1, (unsigned int)v6, a5);
        }
      }
      if ( updated >= 0 )
      {
        updated = StorageService::UpdateVolumeStatus(a1, (unsigned int)v6, a5);
        v12 = v6;
        goto LABEL_4;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9C,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)v10,
      lpData);
  }
LABEL_3:
  StorageService::UpdateDismountState(a1, (unsigned int)v6, a5, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1624));
  v12 = v6;
  *(_OWORD *)(*(_QWORD *)(a1 + 8 * v6 + 40) + 1112LL * a5 + 548) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1624));
  v5 = v31;
LABEL_4:
  LODWORD(v15) = a5;
  if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    v16 = *(_QWORD *)(a1 + 8 * v12 + 40);
    cbData = updated;
    v26 = 0;
    v27[0] = 0;
    v31 = v5;
    LODWORD(hKey) = *(_DWORD *)(v16 + 1112 * v15 + 1096);
    v32 = a2;
    *(_QWORD *)Data = v16 + 1112 * v15 + 548;
    v29 = v6;
    *(_DWORD *)ValueName = a5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)byte_1800A66EB,
      v15,
      v14,
      (__int64)Data,
      (__int64)ValueName,
      (__int64)&v29,
      (__int64)&hKey,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)v27,
      (__int64)&v26,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&cbData);
  }
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    *(_DWORD *)ValueName = updated;
    *(_QWORD *)Data = v5;
    v31 = a2;
    cbData = a5;
    LODWORD(hKey) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)byte_1800A7561,
      v15,
      v14,
      (__int64)&hKey,
      (__int64)&cbData,
      (__int64)&v31,
      (__int64)Data,
      (__int64)ValueName);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180026bfc  push    rbp
0x180026bfe  push    rbx
0x180026bff  push    rsi
0x180026c00  push    rdi
0x180026c01  push    r12
0x180026c03  push    r13
0x180026c05  push    r14
0x180026c07  push    r15
0x180026c09  lea     rbp, [rsp-17h]
0x180026c0e  sub     rsp, 0D8h
0x180026c15  mov     rax, cs:__security_cookie
0x180026c1c  xor     rax, rsp
0x180026c1f  mov     [rbp+4Fh+var_50], rax
0x180026c23  mov     r14d, [rbp+4Fh+arg_20]
0x180026c27  mov     rbx, r8
0x180026c2a  movsxd  rsi, r9d
0x180026c2d  xor     r13d, r13d
0x180026c30  mov     r12, rdx
0x180026c33  mov     [rbp+4Fh+var_78], rbx
0x180026c37  mov     r9d, r14d
0x180026c3a  mov     [rbp+4Fh+var_8E], r13b
0x180026c3e  mov     r8d, esi
0x180026c41  mov     [rbp+4Fh+var_8F], r13b
0x180026c45  mov     rdx, rbx
0x180026c48  mov     [rbp+4Fh+var_90], r13b
0x180026c4c  mov     r15, rcx
0x180026c4f  call    ?DetermineBusType@StorageService@@IEAAJPEBGW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::DetermineBusType(ushort const *,_STORAGE_DEVICE_TYPE,ulong)
0x180026c54  lea     r8, [rbp+4Fh+var_84]; unsigned int *
0x180026c58  mov     [rbp+4Fh+var_84], r13d
0x180026c5c  mov     rdx, rbx; unsigned __int16 *
0x180026c5f  call    ?DeterminePersistentVolumeState@StorageService@@IEAAJPEBGPEAK@Z; StorageService::DeterminePersistentVolumeState(ushort const *,ulong *)
0x180026c64  mov     edi, eax
0x180026c66  test    eax, eax
0x180026c68  jns     loc_180026E3D
0x180026c6e  mov     rcx, [rbp+57h]; this
0x180026c72  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180026c79  mov     r9d, eax; char *
0x180026c7c  mov     edx, 0C9Ch; void *
0x180026c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c86  xor     r9d, r9d
0x180026c89  mov     r8d, r14d
0x180026c8c  mov     edx, esi
0x180026c8e  mov     rcx, r15
0x180026c91  call    ?UpdateDismountState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_DISMOUNT_REASON@@@Z; StorageService::UpdateDismountState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DISMOUNT_REASON)
0x180026c96  lea     rbx, [r15+658h]
0x180026c9d  mov     rcx, rbx; lpCriticalSection
0x180026ca0  call    cs:__imp_EnterCriticalSection
0x180026ca6  mov     rax, [r15+rsi*8+28h]
0x180026cab  xorps   xmm0, xmm0
0x180026cae  imul    rdx, r14, 458h
0x180026cb5  mov     rcx, rbx; lpCriticalSection
0x180026cb8  mov     r13, rsi
0x180026cbb  movups  xmmword ptr [rax+rdx+224h], xmm0
0x180026cc3  call    cs:__imp_LeaveCriticalSection
0x180026cc9  mov     rbx, [rbp+4Fh+var_78]
0x180026ccd  mov     eax, cs:dword_1800BF000
0x180026cd3  mov     r8, r14
0x180026cd6  cmp     eax, 5
0x180026cd9  jbe     loc_180026DC5
0x180026cdf  mov     rdx, 400000000000h
0x180026ce9  lea     rcx, dword_1800BF000
0x180026cf0  call    _tlgKeywordOn
0x180026cf5  test    al, al
0x180026cf7  jz      loc_180026DC5
0x180026cfd  mov     al, [rbp+4Fh+var_90]
0x180026d00  mov     rcx, [r15+r13*8+28h]
0x180026d05  mov     [rbp+4Fh+var_90], al
0x180026d08  mov     al, [rbp+4Fh+var_8F]
0x180026d0b  mov     [rbp+4Fh+var_8F], al
0x180026d0e  mov     al, [rbp+4Fh+var_8E]
0x180026d11  mov     [rbp+4Fh+var_8E], al
0x180026d14  imul    rdx, r8, 458h
0x180026d1b  mov     [rbp+4Fh+cbData], edi
0x180026d1e  mov     [rbp+4Fh+var_8D], 0
0x180026d22  mov     [rbp+4Fh+var_8C], 0
0x180026d26  mov     [rbp+4Fh+var_78], rbx
0x180026d2a  mov     eax, [rcx+rdx+448h]
0x180026d31  mov     dword ptr [rbp+4Fh+hKey], eax
0x180026d34  lea     rax, [rdx+224h]
0x180026d3b  add     rax, rcx
0x180026d3e  mov     [rbp+4Fh+var_70], r12
0x180026d42  mov     qword ptr [rbp+4Fh+Data], rax
0x180026d46  lea     rdx, byte_1800A66EB
0x180026d4d  lea     rax, [rbp+4Fh+cbData]
0x180026d51  mov     [rbp+4Fh+var_84], esi
0x180026d54  mov     [rsp+110h+var_98], rax
0x180026d59  lea     rax, [rbp+4Fh+var_78]
0x180026d5d  mov     [rsp+110h+var_A0], rax
0x180026d62  lea     rax, [rbp+4Fh+var_70]
0x180026d66  mov     [rsp+110h+var_A8], rax
0x180026d6b  lea     rax, [rbp+4Fh+var_8D]
0x180026d6f  mov     [rsp+110h+var_B0], rax
0x180026d74  lea     rax, [rbp+4Fh+var_8C]
0x180026d78  mov     [rsp+110h+var_B8], rax
0x180026d7d  lea     rax, [rbp+4Fh+var_90]
0x180026d81  mov     [rsp+110h+var_C0], rax
0x180026d86  lea     rax, [rbp+4Fh+var_8F]
0x180026d8a  mov     [rsp+110h+var_C8], rax
0x180026d8f  lea     rax, [rbp+4Fh+var_8E]
0x180026d93  mov     [rsp+110h+var_D0], rax
0x180026d98  lea     rax, [rbp+4Fh+hKey]
0x180026d9c  mov     [rsp+110h+var_D8], rax
0x180026da1  lea     rax, [rbp+4Fh+var_84]
0x180026da5  mov     [rsp+110h+var_E0], rax
0x180026daa  lea     rax, [rbp+4Fh+ValueName]
0x180026dae  mov     [rsp+110h+lpcbData], rax
0x180026db3  lea     rax, [rbp+4Fh+Data]
0x180026db7  mov     [rsp+110h+lpData], rax
0x180026dbc  mov     dword ptr [rbp+4Fh+ValueName], r14d
0x180026dc0  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByVal@$00@@U3@U3@U3@U3@U?$_tlgWrapSz@G@@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByVal@$00@@5555AEBU?$_tlgWrapSz@G@@64@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180026dc5  mov     eax, cs:dword_1800BF000
0x180026dcb  cmp     eax, 5
0x180026dce  jbe     short loc_180026E1B
0x180026dd0  lea     rax, [rbp+4Fh+ValueName]
0x180026dd4  mov     dword ptr [rbp+4Fh+ValueName], edi
0x180026dd7  mov     [rsp+110h+var_D0], rax
0x180026ddc  lea     rdx, byte_1800A7561
0x180026de3  lea     rax, [rbp+4Fh+Data]
0x180026de7  mov     qword ptr [rbp+4Fh+Data], rbx
0x180026deb  mov     [rsp+110h+var_D8], rax
0x180026df0  lea     rax, [rbp+4Fh+var_78]
0x180026df4  mov     [rsp+110h+var_E0], rax
0x180026df9  lea     rax, [rbp+4Fh+cbData]
0x180026dfd  mov     [rsp+110h+lpcbData], rax
0x180026e02  lea     rax, [rbp+4Fh+hKey]
0x180026e06  mov     [rsp+110h+lpData], rax
0x180026e0b  mov     [rbp+4Fh+var_78], r12
0x180026e0f  mov     [rbp+4Fh+cbData], r14d
0x180026e13  mov     dword ptr [rbp+4Fh+hKey], esi
0x180026e16  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180026e1b  mov     eax, edi
0x180026e1d  mov     rcx, [rbp+4Fh+var_50]
0x180026e21  xor     rcx, rsp; StackCookie
0x180026e24  call    __security_check_cookie
0x180026e29  add     rsp, 0D8h
0x180026e30  pop     r15
0x180026e32  pop     r14
0x180026e34  pop     r13
0x180026e36  pop     r12
0x180026e38  pop     rdi
0x180026e39  pop     rsi
0x180026e3a  pop     rbx
0x180026e3b  pop     rbp
0x180026e3c  retn
0x180026e3d  mov     rcx, [r15+rsi*8+28h]
0x180026e42  mov     r9d, r14d
0x180026e45  mov     eax, [rbp+4Fh+var_84]
0x180026e48  mov     r8d, esi
0x180026e4b  imul    rdx, r14, 458h
0x180026e52  mov     [rcx+rdx+450h], eax
0x180026e59  mov     rdx, r12
0x180026e5c  mov     rcx, r15
0x180026e5f  call    ?SetStorageCardPaths@StorageService@@IEAAJPEBGW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::SetStorageCardPaths(ushort const *,_STORAGE_DEVICE_TYPE,ulong)
0x180026e64  mov     edi, eax
0x180026e66  test    eax, eax
0x180026e68  js      loc_180026C86
0x180026e6e  mov     rcx, r12; unsigned __int16 *
0x180026e71  call    ?CheckCrashDumpSettings@@YAJPEBG@Z; CheckCrashDumpSettings(ushort const *)
0x180026e76  test    eax, eax
0x180026e78  jns     short loc_180026ED0
0x180026e7a  mov     ecx, cs:dword_1800BF000
0x180026e80  cmp     ecx, 5
0x180026e83  jbe     short loc_180026ED0
0x180026e85  mov     [rbp+4Fh+var_84], eax
0x180026e88  lea     rdx, byte_1800A6BEB
0x180026e8f  lea     rax, [rbp+4Fh+var_84]
0x180026e93  mov     qword ptr [rbp+4Fh+ValueName], rbx
0x180026e97  mov     [rsp+110h+var_D0], rax
0x180026e9c  lea     rax, [rbp+4Fh+ValueName]
0x180026ea0  mov     [rsp+110h+var_D8], rax
0x180026ea5  lea     rax, [rbp+4Fh+var_70]
0x180026ea9  mov     [rsp+110h+var_E0], rax
0x180026eae  lea     rax, [rbp+4Fh+hKey]
0x180026eb2  mov     [rsp+110h+lpcbData], rax
0x180026eb7  lea     rax, [rbp+4Fh+cbData]
0x180026ebb  mov     [rsp+110h+lpData], rax
0x180026ec0  mov     [rbp+4Fh+var_70], r12
0x180026ec4  mov     dword ptr [rbp+4Fh+hKey], r14d
0x180026ec8  mov     [rbp+4Fh+cbData], esi
0x180026ecb  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180026ed0  mov     r8d, r14d
0x180026ed3  mov     edx, esi
0x180026ed5  mov     rcx, r15
0x180026ed8  call    ?DetermineDisabledState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::DetermineDisabledState(_STORAGE_DEVICE_TYPE,ulong)
0x180026edd  mov     edi, eax
0x180026edf  test    eax, eax
0x180026ee1  js      loc_180027057
0x180026ee7  mov     r9d, 8
0x180026eed  mov     r8d, r14d
0x180026ef0  mov     edx, esi
0x180026ef2  mov     rcx, r15
0x180026ef5  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180026efa  test    eax, eax
0x180026efc  jnz     loc_180027057
0x180026f02  mov     r8d, r14d
0x180026f05  mov     edx, esi
0x180026f07  mov     rcx, r15
0x180026f0a  call    ?DetermineFormatState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::DetermineFormatState(_STORAGE_DEVICE_TYPE,ulong)
0x180026f0f  mov     edi, eax
0x180026f11  test    eax, eax
0x180026f13  js      loc_180027051
0x180026f19  mov     r9d, 2
0x180026f1f  mov     r8d, r14d
0x180026f22  mov     edx, esi
0x180026f24  mov     rcx, r15
0x180026f27  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180026f2c  test    eax, eax
0x180026f2e  jnz     loc_180027051
0x180026f34  mov     r8d, r14d
0x180026f37  mov     edx, esi
0x180026f39  mov     rcx, r15
0x180026f3c  call    ?DetermineNewCardState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::DetermineNewCardState(_STORAGE_DEVICE_TYPE,ulong)
0x180026f41  mov     edi, eax
0x180026f43  test    eax, eax
0x180026f45  js      loc_180026C86
0x180026f4b  mov     r8d, r14d
0x180026f4e  mov     edx, esi
0x180026f50  mov     rcx, r15
0x180026f53  call    ?DetermineAppPairingState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::DetermineAppPairingState(_STORAGE_DEVICE_TYPE,ulong)
0x180026f58  mov     edi, eax
0x180026f5a  test    eax, eax
0x180026f5c  js      loc_180026C86
0x180026f62  mov     r8d, r14d
0x180026f65  mov     edx, esi
0x180026f67  mov     rcx, r15
0x180026f6a  call    ?GetAppPairingStatus@StorageService@@IEAAKW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::GetAppPairingStatus(_STORAGE_DEVICE_TYPE,ulong)
0x180026f6f  cmp     eax, 1
0x180026f72  jnz     loc_180027040
0x180026f78  mov     [rbp+4Fh+var_90], al
0x180026f7b  lea     r8, [rbp+4Fh+hKey]; phkResult
0x180026f7f  mov     rax, 3300320031h
0x180026f89  mov     [rbp+4Fh+hKey], r13
0x180026f8d  xorps   xmm0, xmm0
0x180026f90  mov     qword ptr [rbp+4Fh+ValueName], rax
0x180026f94  lea     rdx, aAccessflags; "AccessFlags"
0x180026f9b  mov     [rbp+4Fh+cbData], 10h
0x180026fa2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026fa9  movups  xmmword ptr [rbp+4Fh+Data], xmm0
0x180026fad  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180026fb2  mov     edi, eax
0x180026fb4  test    eax, eax
0x180026fb6  js      loc_180026C86
0x180026fbc  mov     r9d, 10h
0x180026fc2  lea     r8, a02d; "%02d"
0x180026fc9  lea     rcx, [rbp+4Fh+ValueName]; unsigned __int16 *
0x180026fcd  lea     edx, [r9-0Ch]; unsigned __int64
0x180026fd1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026fd6  mov     edi, eax
0x180026fd8  test    eax, eax
0x180026fda  js      loc_180026C86
0x180026fe0  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180026fe4  lea     rax, [rbp+4Fh+cbData]
0x180026fe8  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180026fed  lea     rdx, [rbp+4Fh+ValueName]; lpValueName
0x180026ff1  lea     rax, [rbp+4Fh+Data]
0x180026ff5  xor     r9d, r9d; lpType
0x180026ff8  xor     r8d, r8d; lpReserved
0x180026ffb  mov     [rsp+110h+lpData], rax; lpData
0x180027000  call    cs:__imp_RegQueryValueExW
0x180027006  test    eax, eax
0x180027008  jnz     short loc_180027040
0x18002700a  mov     r8, [r15+rsi*8+28h]
0x18002700f  mov     rax, qword ptr [rbp+4Fh+Data]
0x180027013  imul    rdx, r14, 458h
0x18002701a  cmp     rax, [r8+rdx+224h]
0x180027022  jnz     short loc_180027040
0x180027024  mov     rax, qword ptr [rbp+4Fh+Data+8]
0x180027028  cmp     rax, [r8+rdx+22Ch]
0x180027030  jnz     short loc_180027040
0x180027032  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180027036  lea     rdx, [rbp+4Fh+ValueName]; lpValueName
0x18002703a  call    cs:__imp_RegDeleteValueW
0x180027040  mov     r8d, r14d
0x180027043  mov     edx, esi
0x180027045  mov     rcx, r15
0x180027048  call    ?UpdateMountState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::UpdateMountState(_STORAGE_DEVICE_TYPE,ulong)
0x18002704d  mov     edi, eax
0x18002704f  jmp     short loc_18002705B
0x180027051  mov     [rbp+4Fh+var_8F], 1
0x180027055  jmp     short loc_18002705B
0x180027057  mov     [rbp+4Fh+var_8E], 1
0x18002705b  test    edi, edi
0x18002705d  js      loc_180026C86
0x180027063  mov     r8d, r14d
0x180027066  mov     edx, esi
0x180027068  mov     rcx, r15
0x18002706b  call    ?UpdateVolumeStatus@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::UpdateVolumeStatus(_STORAGE_DEVICE_TYPE,ulong)
0x180027070  mov     edi, eax
0x180027072  mov     r13, rsi
0x180027075  jmp     loc_180026CCD
```
