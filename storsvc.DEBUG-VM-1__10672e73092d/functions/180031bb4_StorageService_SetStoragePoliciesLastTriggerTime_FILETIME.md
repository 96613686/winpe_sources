# StorageService::SetStoragePoliciesLastTriggerTime(_FILETIME)

- ea: `0x180031bb4`
- end: `0x180031ce6`
- name: `?SetStoragePoliciesLastTriggerTime@StorageService@@QEAAJU_FILETIME@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(StorageService *__hidden this, struct _FILETIME)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800379b0`

## callees

- `0x180001148`
- `0x1800011d0`
- `0x1800108f4`
- `0x180010d24`
- `0x180012734`
- `0x180019db4`
- `0x180031bb4`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031c61`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031be9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031be9`

## string_xrefs

- `0x180031c25`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StorageService::SetStoragePoliciesLastTriggerTime(StorageService *this, struct _FILETIME a2)
{
  int v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  int v5; // r8d
  int v6; // r9d
  int lpData; // [rsp+20h] [rbp-20h]
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  StorageService *v11; // [rsp+50h] [rbp+10h] BYREF
  struct _FILETIME Data; // [rsp+58h] [rbp+18h] BYREF
  __int64 v13; // [rsp+60h] [rbp+20h] BYREF

  Data = a2;
  v11 = this;
  hKey[0] = 0;
  v2 = OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"StoragePolicy", hKey);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = RegSetValueExW(hKey[0], L"StoragePoliciesLastTrigger", 0, 3u, (const BYTE *)&Data, 8u);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 < 0
      && (unsigned int)dword_1800BF000 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
    {
      v13 = 0x1000000;
      LODWORD(v11) = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800BF000,
        (unsigned int)word_1800A7D72,
        v5,
        v6,
        (__int64)&v11,
        (__int64)&v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DC,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v2,
      lpData);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180031bb4  mov     [rsp-8+arg_18], rbx
0x180031bb9  mov     [rsp-8+Data], rdx
0x180031bbe  mov     [rsp-8+arg_0], rcx
0x180031bc3  push    rbp
0x180031bc4  mov     rbp, rsp
0x180031bc7  sub     rsp, 40h
0x180031bcb  mov     [rbp+hKey], 0
0x180031bd3  mov     rbx, [rbp+hKey]
0x180031bd7  test    rbx, rbx
0x180031bda  jz      short loc_180031BF9
0x180031bdc  lea     rcx, [rbp+arg_0]; this
0x180031be0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180031be5  nop
0x180031be6  mov     rcx, rbx; hKey
0x180031be9  call    cs:__imp_RegCloseKey
0x180031bef  nop
0x180031bf0  lea     rcx, [rbp+arg_0]; this
0x180031bf4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180031bf9  mov     [rbp+hKey], 0
0x180031c01  lea     r8, [rbp+hKey]; phkResult
0x180031c05  lea     rdx, aStoragepolicy; "StoragePolicy"
0x180031c0c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180031c13  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180031c18  mov     ebx, eax
0x180031c1a  test    eax, eax
0x180031c1c  jns     short loc_180031C3C
0x180031c1e  mov     rcx, [rbp+8]; this
0x180031c22  mov     r9d, eax; char *
0x180031c25  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031c2c  mov     edx, 2DCh; void *
0x180031c31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c36  nop
0x180031c37  jmp     loc_180031CD0
0x180031c3c  mov     [rsp+40h+cbData], 8; cbData
0x180031c44  lea     rax, [rbp+Data]
0x180031c48  mov     [rsp+40h+lpData], rax; lpData
0x180031c4d  mov     r9d, 3; dwType
0x180031c53  xor     r8d, r8d; Reserved
0x180031c56  lea     rdx, aStoragepolicie; "StoragePoliciesLastTrigger"
0x180031c5d  mov     rcx, [rbp+hKey]; hKey
0x180031c61  call    cs:__imp_RegSetValueExW
0x180031c67  mov     ebx, eax
0x180031c69  test    eax, eax
0x180031c6b  jle     short loc_180031C76
0x180031c6d  movzx   ebx, ax
0x180031c70  or      ebx, 80070000h
0x180031c76  test    ebx, ebx
0x180031c78  jns     short loc_180031CD0
0x180031c7a  mov     eax, cs:dword_1800BF000
0x180031c80  cmp     eax, 5
0x180031c83  jbe     short loc_180031CD0
0x180031c85  mov     rdx, 400000000000h
0x180031c8f  lea     rcx, dword_1800BF000
0x180031c96  call    _tlgKeywordOn
0x180031c9b  test    al, al
0x180031c9d  jz      short loc_180031CD0
0x180031c9f  mov     [rbp+arg_10], 1000000h
0x180031ca7  mov     dword ptr [rbp+arg_0], ebx
0x180031caa  lea     rax, [rbp+arg_10]
0x180031cae  mov     qword ptr [rsp+40h+cbData], rax
0x180031cb3  lea     rax, [rbp+arg_0]
0x180031cb7  mov     [rsp+40h+lpData], rax
0x180031cbc  lea     rdx, word_1800A7D72
0x180031cc3  lea     rcx, dword_1800BF000
0x180031cca  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180031ccf  nop
0x180031cd0  lea     rcx, [rbp+hKey]
0x180031cd4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031cd9  mov     eax, ebx
0x180031cdb  mov     rbx, [rsp+40h+arg_18]
0x180031ce0  add     rsp, 40h
0x180031ce4  pop     rbp
0x180031ce5  retn
```
