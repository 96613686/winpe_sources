# LocationDataSource::PositionChangedCallback(Windows::Devices::Geolocation::IGeolocator *,Windows::Devices::Geolocation::IPositionChangedEventArgs *)

- ea: `0x180011b60`
- end: `0x180011c4f`
- name: `?PositionChangedCallback@LocationDataSource@@AEAAJPEAUIGeolocator@Geolocation@Devices@Windows@@PEAUIPositionChangedEventArgs@345@@Z`
- size: `239`
- prototype: `__int64 __fastcall(LocationDataSource *__hidden this, struct Windows::Devices::Geolocation::IGeolocator *, struct Windows::Devices::Geolocation::IPositionChangedEventArgs *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010c50`

## callees

- `0x18000166c`
- `0x1800018fc`
- `0x180006844`
- `0x18000885c`
- `0x180010afc`
- `0x18001126c`
- `0x180011b60`
- `0x18001d010`

## string_xrefs

- `0x180011bb9`: `onecore\base\win32\winnls\tzautoupdate\locationdatasource.cpp`

## pseudocode

```c
__int64 __fastcall LocationDataSource::PositionChangedCallback(
        LocationDataSource *this,
        struct Windows::Devices::Geolocation::IGeolocator *a2,
        struct Windows::Devices::Geolocation::IPositionChangedEventArgs *a3)
{
  __int64 (__fastcall *v5)(struct Windows::Devices::Geolocation::IPositionChangedEventArgs *, struct Windows::Devices::Geolocation::IGeoposition **); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  int v15; // [rsp+20h] [rbp-20h]
  __int64 v16; // [rsp+30h] [rbp-10h] BYREF
  char v17; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  struct Windows::Devices::Geolocation::IGeoposition *v19; // [rsp+60h] [rbp+20h] BYREF
  struct Windows::Devices::Geolocation::IGeolocator *v20; // [rsp+68h] [rbp+28h] BYREF
  __int64 v21; // [rsp+70h] [rbp+30h] BYREF

  v20 = a2;
  v16 = *(_QWORD *)this;
  v17 = 0;
  v19 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Devices::Geolocation::IPositionChangedEventArgs *, struct Windows::Devices::Geolocation::IGeoposition **))(*(_QWORD *)a3 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((__int64 *)&v19);
  v6 = v5(a3, &v19);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = LocationDataSource::HandleNewGeoposition(this, v19, (struct LocationDataSource::CacheManager *)&v16);
    if ( v8 < 0
      && (unsigned int)dword_180030000 > 5
      && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, (unsigned int)v8) )
    {
      LODWORD(v20) = v10;
      v21 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)byte_1800292BD,
        v10,
        v11,
        (__int64)&v21,
        (__int64)&v20);
    }
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\locationdatasource.cpp",
      (const char *)(unsigned int)v6,
      v15);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((__int64 *)&v19);
  LocationDataSource::CacheManager::~CacheManager((LocationDataSource::CacheManager *)&v16, v12, v13);
  return v7;
}

```

## disassembly

```asm
0x180011b60  mov     [rsp-18h+arg_18], rbx
0x180011b65  mov     [rsp-18h+arg_8], rdx
0x180011b6a  push    rbp
0x180011b6b  push    rsi
0x180011b6c  push    rdi
0x180011b6d  mov     rbp, rsp
0x180011b70  sub     rsp, 40h
0x180011b74  mov     rdi, r8
0x180011b77  mov     rsi, rcx
0x180011b7a  mov     rax, [rcx]
0x180011b7d  mov     [rbp+var_10], rax
0x180011b81  mov     [rbp+var_8], 0
0x180011b85  mov     [rbp+arg_0], 0
0x180011b8d  mov     rax, [r8]
0x180011b90  mov     rbx, [rax+30h]
0x180011b94  lea     rcx, [rbp+arg_0]
0x180011b98  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011b9d  lea     rdx, [rbp+arg_0]
0x180011ba1  mov     rcx, rdi
0x180011ba4  mov     rax, rbx
0x180011ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bac  mov     ebx, eax
0x180011bae  test    eax, eax
0x180011bb0  jns     short loc_180011BCC
0x180011bb2  mov     rcx, [rbp+18h]; this
0x180011bb6  mov     r9d, eax; char *
0x180011bb9  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180011bc0  mov     edx, 126h; void *
0x180011bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bca  jmp     short loc_180011C2D
0x180011bcc  lea     r8, [rbp+var_10]; struct LocationDataSource::CacheManager *
0x180011bd0  mov     rdx, [rbp+arg_0]; struct Windows::Devices::Geolocation::IGeoposition *
0x180011bd4  mov     rcx, rsi; this
0x180011bd7  call    ?HandleNewGeoposition@LocationDataSource@@AEAAJPEAUIGeoposition@Geolocation@Devices@Windows@@AEAVCacheManager@1@@Z; LocationDataSource::HandleNewGeoposition(Windows::Devices::Geolocation::IGeoposition *,LocationDataSource::CacheManager &)
0x180011bdc  mov     r8d, eax
0x180011bdf  test    eax, eax
0x180011be1  jns     short loc_180011C2B
0x180011be3  mov     ecx, cs:dword_180030000
0x180011be9  cmp     ecx, 5
0x180011bec  jbe     short loc_180011C2B
0x180011bee  mov     rdx, 200000000000h
0x180011bf8  call    _tlgKeywordOn
0x180011bfd  test    al, al
0x180011bff  jz      short loc_180011C2B
0x180011c01  mov     dword ptr [rbp+arg_8], r8d
0x180011c05  mov     [rbp+arg_10], 1000000h
0x180011c0d  lea     rax, [rbp+arg_8]
0x180011c11  mov     [rsp+40h+var_18], rax
0x180011c16  lea     rax, [rbp+arg_10]
0x180011c1a  mov     [rsp+40h+var_20], rax
0x180011c1f  lea     rdx, byte_1800292BD
0x180011c26  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180011c2b  xor     ebx, ebx
0x180011c2d  lea     rcx, [rbp+arg_0]
0x180011c31  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011c36  nop
0x180011c37  lea     rcx, [rbp+var_10]; this
0x180011c3b  call    ??1CacheManager@LocationDataSource@@QEAA@XZ; LocationDataSource::CacheManager::~CacheManager(void)
0x180011c40  mov     eax, ebx
0x180011c42  mov     rbx, [rsp+40h+arg_18]
0x180011c47  add     rsp, 40h
0x180011c4b  pop     rdi
0x180011c4c  pop     rsi
0x180011c4d  pop     rbp
0x180011c4e  retn
```
