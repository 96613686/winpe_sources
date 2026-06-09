# LocationDataSource::LocationDataSource(Cache &,ulong,bool,bool)

- ea: `0x180010784`
- end: `0x1800109a0`
- name: `??0LocationDataSource@@QEAA@AEAVCache@@K_N1@Z`
- size: `540`
- prototype: `LocationDataSource *__fastcall(LocationDataSource *this, struct Cache *, int, char, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004018`

## callees

- `0x18000166c`
- `0x1800018fc`
- `0x18000cfec`
- `0x180010784`
- `0x1800116bc`
- `0x180011b0c`
- `0x180011e2c`
- `0x180012738`
- `0x1800127fc`
- `0x1800128c0`
- `0x180012984`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010869`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800108b2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800108fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010869`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800108b2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800108fb`

## string_xrefs

- `0x180010858`: `SYSTEM\CurrentControlSet\Services\tzautoupdate\Config`
- `0x1800108a8`: `SYSTEM\CurrentControlSet\Services\tzautoupdate\Config`
- `0x1800108f1`: `SYSTEM\CurrentControlSet\Services\tzautoupdate\Config`
- `0x1800108ea`: `MinimumMovementThresholdKm`

## pseudocode

```c
LocationDataSource *__fastcall LocationDataSource::LocationDataSource(
        LocationDataSource *this,
        struct Cache *a2,
        int a3,
        char a4,
        int a5)
{
  int v6; // eax
  __int64 v7; // r8
  int v8; // ecx
  int v9; // r9d
  _BYTE v11[48]; // [rsp+40h] [rbp-51h] BYREF
  _BYTE v12[112]; // [rsp+70h] [rbp-21h] BYREF
  __int64 v13; // [rsp+F0h] [rbp+5Fh] BYREF
  DWORD pcbData; // [rsp+108h] [rbp+77h] BYREF

  v13 = (__int64)this;
  *(_QWORD *)this = a2;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = a3;
  *((_BYTE *)this + 76) = a4;
  *((_BYTE *)this + 77) = a5;
  *((_QWORD *)this + 10) = this;
  *((_QWORD *)this + 11) = WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_LFS_SIGNIFICANT_LOCATION_EVENT,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfSubscribe((char *)this + 80);
  *((_QWORD *)this + 12) = this;
  *((_QWORD *)this + 13) = WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_DEVICE_UNLOCKED,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfSubscribe((char *)this + 96);
  *((_QWORD *)this + 14) = this;
  *((_QWORD *)this + 15) = WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfSubscribe((char *)this + 112);
  *((_QWORD *)this + 16) = this;
  *((_QWORD *)this + 17) = WnfSubscription<unsigned long,&_WNF_STATE_NAME const WNF_SHEL_LOCKSCREEN_ACTIVE,LocationDataSource,&private: void LocationDataSource::WnfLockScreenActiveCallback(unsigned long const &)>::WnfSubscribe((char *)this + 128);
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\tzautoupdate\\Config",
         L"ActiveModeThresholdKm",
         0x10u,
         0,
         (char *)this + 8,
         &pcbData) )
  {
    *((_DWORD *)this + 2) = 10;
  }
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\tzautoupdate\\Config",
         L"GeolocatorAccuracy",
         0x10u,
         0,
         (char *)this + 12,
         &pcbData) )
  {
    *((_DWORD *)this + 3) = 0;
  }
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\tzautoupdate\\Config",
         L"MinimumMovementThresholdKm",
         0x10u,
         0,
         (char *)this + 16,
         &pcbData) )
  {
    *((_DWORD *)this + 4) = 1;
  }
  v6 = LocationDataSource::Initialize(this);
  v7 = (unsigned int)v6;
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_180030000 > 5
      && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, (unsigned int)v6) )
    {
      a5 = v7;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)&byte_180028F97,
        v7,
        v9,
        (__int64)&v13,
        (__int64)&a5);
    }
    Cache::Lock(*(_QWORD *)this, v11, v7);
    LOBYTE(a5) = 1;
    Cache::ValueProxy<bool>::SetValue(v12, &a5);
    Cache::Proxy::~Proxy((Cache::Proxy *)v11);
  }
  return this;
}

```

## disassembly

```asm
0x180010784  mov     [rsp-8+arg_8], rbx
0x180010789  mov     [rsp-8+arg_0], rcx
0x18001078e  push    rbp
0x18001078f  push    rdi
0x180010790  push    r13
0x180010792  lea     rbp, [rsp-3Fh]
0x180010797  sub     rsp, 0D0h
0x18001079e  mov     rdi, rcx
0x1800107a1  mov     [rcx], rdx
0x1800107a4  mov     qword ptr [rcx+18h], 0
0x1800107ac  mov     qword ptr [rcx+20h], 0
0x1800107b4  mov     qword ptr [rcx+28h], 0
0x1800107bc  mov     qword ptr [rcx+30h], 0
0x1800107c4  mov     qword ptr [rcx+38h], 0
0x1800107cc  xor     eax, eax
0x1800107ce  mov     [rcx+40h], rax
0x1800107d2  mov     [rcx+48h], r8d
0x1800107d6  mov     [rcx+4Ch], r9b
0x1800107da  mov     al, byte ptr [rbp+4Fh+arg_20]
0x1800107dd  mov     [rcx+4Dh], al
0x1800107e0  mov     [rcx+50h], rcx
0x1800107e4  add     rcx, 50h ; 'P'
0x1800107e8  call    ?WnfSubscribe@?$WnfNoStateSubscription@$1?WNF_LFS_SIGNIFICANT_LOCATION_EVENT@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ; WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_LFS_SIGNIFICANT_LOCATION_EVENT,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfSubscribe(void)
0x1800107ed  mov     [rdi+58h], rax
0x1800107f1  mov     [rdi+60h], rdi
0x1800107f5  lea     rcx, [rdi+60h]
0x1800107f9  call    ?WnfSubscribe@?$WnfNoStateSubscription@$1?WNF_SHEL_DEVICE_UNLOCKED@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ; WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_DEVICE_UNLOCKED,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfSubscribe(void)
0x1800107fe  mov     [rdi+68h], rax
0x180010802  mov     [rdi+70h], rdi
0x180010806  lea     rcx, [rdi+70h]
0x18001080a  call    ?WnfSubscribe@?$WnfNoStateSubscription@$1?WNF_SHEL_LOGON_COMPLETE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ; WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfSubscribe(void)
0x18001080f  mov     [rdi+78h], rax
0x180010813  lea     rbx, [rdi+80h]
0x18001081a  mov     [rbx], rdi
0x18001081d  mov     rcx, rbx
0x180010820  call    ?WnfSubscribe@?$WnfSubscription@K$1?WNF_SHEL_LOCKSCREEN_ACTIVE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfLockScreenActiveCallback@3@AEAAXAEBK@Z@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ; WnfSubscription<ulong,&_WNF_STATE_NAME const WNF_SHEL_LOCKSCREEN_ACTIVE,LocationDataSource,&LocationDataSource::WnfLockScreenActiveCallback(ulong const &)>::WnfSubscribe(void)
0x180010825  mov     [rbx+8], rax
0x180010829  mov     [rbp+4Fh+arg_18], 4
0x180010830  lea     rbx, [rdi+8]
0x180010834  lea     rax, [rbp+4Fh+arg_18]
0x180010838  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18001083d  mov     [rsp+0E0h+pvData], rbx; pvData
0x180010842  mov     [rsp+0E0h+pdwType], 0; pdwType
0x18001084b  mov     r9d, 10h; dwFlags
0x180010851  lea     r8, aActivemodethre; "ActiveModeThresholdKm"
0x180010858  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\tz"...
0x18001085f  mov     r13, 0FFFFFFFF80000002h
0x180010866  mov     rcx, r13; hkey
0x180010869  call    cs:__imp_RegGetValueW
0x18001086f  test    eax, eax
0x180010871  jz      short loc_180010879
0x180010873  mov     dword ptr [rbx], 0Ah
0x180010879  mov     [rbp+4Fh+arg_18], 4
0x180010880  lea     rbx, [rdi+0Ch]
0x180010884  lea     rax, [rbp+4Fh+arg_18]
0x180010888  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18001088d  mov     [rsp+0E0h+pvData], rbx; pvData
0x180010892  mov     [rsp+0E0h+pdwType], 0; pdwType
0x18001089b  mov     r9d, 10h; dwFlags
0x1800108a1  lea     r8, aGeolocatoraccu; "GeolocatorAccuracy"
0x1800108a8  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\tz"...
0x1800108af  mov     rcx, r13; hkey
0x1800108b2  call    cs:__imp_RegGetValueW
0x1800108b8  test    eax, eax
0x1800108ba  jz      short loc_1800108C2
0x1800108bc  mov     dword ptr [rbx], 0
0x1800108c2  mov     [rbp+4Fh+arg_18], 4
0x1800108c9  lea     rbx, [rdi+10h]
0x1800108cd  lea     rax, [rbp+4Fh+arg_18]
0x1800108d1  mov     [rsp+0E0h+pcbData], rax; pcbData
0x1800108d6  mov     [rsp+0E0h+pvData], rbx; pvData
0x1800108db  mov     [rsp+0E0h+pdwType], 0; pdwType
0x1800108e4  mov     r9d, 10h; dwFlags
0x1800108ea  lea     r8, aMinimummovemen; "MinimumMovementThresholdKm"
0x1800108f1  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\tz"...
0x1800108f8  mov     rcx, r13; hkey
0x1800108fb  call    cs:__imp_RegGetValueW
0x180010901  test    eax, eax
0x180010903  jz      short loc_18001090B
0x180010905  mov     dword ptr [rbx], 1
0x18001090b  mov     rcx, rdi; this
0x18001090e  call    ?Initialize@LocationDataSource@@AEAAJXZ; LocationDataSource::Initialize(void)
0x180010913  mov     r8d, eax
0x180010916  test    eax, eax
0x180010918  jns     short loc_180010989
0x18001091a  mov     ecx, cs:dword_180030000
0x180010920  cmp     ecx, 5
0x180010923  jbe     short loc_180010962
0x180010925  mov     rdx, 200000000000h
0x18001092f  call    _tlgKeywordOn
0x180010934  test    al, al
0x180010936  jz      short loc_180010962
0x180010938  mov     [rbp+4Fh+arg_20], r8d
0x18001093c  mov     [rbp+4Fh+arg_0], 1000000h
0x180010944  lea     rax, [rbp+4Fh+arg_20]
0x180010948  mov     [rsp+0E0h+pvData], rax
0x18001094d  lea     rax, [rbp+4Fh+arg_0]
0x180010951  mov     [rsp+0E0h+pdwType], rax
0x180010956  lea     rdx, byte_180028F97
0x18001095d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180010962  lea     rdx, [rbp+4Fh+var_A0]
0x180010966  mov     rcx, [rdi]
0x180010969  call    ?Lock@Cache@@QEAA?AVProxy@1@XZ; Cache::Lock(void)
0x18001096e  mov     byte ptr [rbp+4Fh+arg_20], 1
0x180010972  lea     rdx, [rbp+4Fh+arg_20]
0x180010976  lea     rcx, [rbp+4Fh+var_70]
0x18001097a  call    ?SetValue@?$ValueProxy@_N@Cache@@QEAAXAEB_N@Z; Cache::ValueProxy<bool>::SetValue(bool const &)
0x18001097f  lea     rcx, [rbp+4Fh+var_A0]; this
0x180010983  call    ??1Proxy@Cache@@QEAA@XZ; Cache::Proxy::~Proxy(void)
0x180010988  nop
0x180010989  mov     rax, rdi
0x18001098c  mov     rbx, [rsp+0E0h+arg_8]
0x180010994  add     rsp, 0D0h
0x18001099b  pop     r13
0x18001099d  pop     rdi
0x18001099e  pop     rbp
0x18001099f  retn
```
