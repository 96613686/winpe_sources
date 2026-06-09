# WscMigrationComplete(_SECURITY_PRODUCT_TYPE)

- ea: `0x18003e88c`
- end: `0x18003ea1c`
- name: `?WscMigrationComplete@@YAJW4_SECURITY_PRODUCT_TYPE@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(enum _SECURITY_PRODUCT_TYPE)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036adc`
- `0x180037460`

## callees

- `0x180001008`
- `0x18001f9f4`
- `0x1800202e8`
- `0x180023dec`
- `0x180027b94`
- `0x1800287b0`
- `0x18003e88c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e90c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e90c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e95a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e95a`

## pseudocode

```c
__int64 __fastcall WscMigrationComplete(enum _SECURITY_PRODUCT_TYPE a1)
{
  const WCHAR *DatastoreRegKey; // rbx
  HKEY *phkResult; // rax
  int v5; // ebx
  CThirdPartyManager *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // eax
  enum _SECURITY_PRODUCT_TYPE v12; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  int Data; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v15; // [rsp+80h] [rbp+30h] BYREF
  int v16; // [rsp+88h] [rbp+38h] BYREF

  DatastoreRegKey = WscGetDatastoreRegKey(a1);
  if ( !DatastoreRegKey )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids);
    }
    return 2147942487LL;
  }
  Data = 1;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, DatastoreRegKey, 0, 0x2001Fu, phkResult);
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_15;
    }
    v7 = 21;
  }
  else
  {
    v5 = RegSetValueExW(hKey, L"DataMigrated", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v5 )
      goto LABEL_15;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_15;
    }
    v7 = 22;
  }
  WPP_SF_(*((_QWORD *)v6 + 2), v7, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids);
LABEL_15:
  if ( (unsigned int)dword_180053218 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180053218, 0x400000000000LL) )
  {
    if ( v5 > 0 )
      v11 = (unsigned __int16)v5 | 0x80070000;
    else
      v11 = v5;
    v15 = v11;
    v16 = Data;
    v12 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned __int8 *)&dword_18004C74C,
      v9,
      v10,
      (__int64)&v12,
      (__int64)&v16,
      (__int64)&v15);
  }
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003e88c  push    rbp
0x18003e88e  push    rbx
0x18003e88f  push    rdi
0x18003e890  mov     rbp, rsp
0x18003e893  sub     rsp, 50h
0x18003e897  mov     edi, ecx
0x18003e899  call    ?WscGetDatastoreRegKey@@YAPEBGW4_SECURITY_PRODUCT_TYPE@@@Z; WscGetDatastoreRegKey(_SECURITY_PRODUCT_TYPE)
0x18003e89e  mov     rbx, rax
0x18003e8a1  test    rax, rax
0x18003e8a4  jnz     short loc_18003E8DC
0x18003e8a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e8ad  lea     rax, WPP_GLOBAL_Control
0x18003e8b4  cmp     rcx, rax
0x18003e8b7  jz      short loc_18003E8D2
0x18003e8b9  test    byte ptr [rcx+1Ch], 1
0x18003e8bd  jz      short loc_18003E8D2
0x18003e8bf  mov     rcx, [rcx+10h]
0x18003e8c3  lea     edx, [rbx+14h]
0x18003e8c6  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x18003e8cd  call    WPP_SF_
0x18003e8d2  mov     eax, 80070057h
0x18003e8d7  jmp     loc_18003EA14
0x18003e8dc  lea     rcx, [rbp+hKey]
0x18003e8e0  mov     [rbp+Data], 1
0x18003e8e7  mov     [rbp+hKey], 0
0x18003e8ef  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18003e8f4  mov     r9d, 2001Fh; samDesired
0x18003e8fa  mov     [rsp+50h+phkResult], rax; phkResult
0x18003e8ff  xor     r8d, r8d; ulOptions
0x18003e902  mov     rdx, rbx; lpSubKey
0x18003e905  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e90c  call    cs:__imp_RegOpenKeyExW
0x18003e912  mov     ebx, eax
0x18003e914  test    eax, eax
0x18003e916  jz      short loc_18003E938
0x18003e918  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e91f  lea     rax, WPP_GLOBAL_Control
0x18003e926  cmp     rcx, rax
0x18003e929  jz      short loc_18003E994
0x18003e92b  test    byte ptr [rcx+1Ch], 1
0x18003e92f  jz      short loc_18003E994
0x18003e931  mov     edx, 15h
0x18003e936  jmp     short loc_18003E984
0x18003e938  mov     rcx, [rbp+hKey]; hKey
0x18003e93c  lea     rax, [rbp+Data]
0x18003e940  mov     r9d, 4; dwType
0x18003e946  lea     rdx, aDatamigrated; "DataMigrated"
0x18003e94d  mov     [rsp+50h+cbData], r9d; cbData
0x18003e952  xor     r8d, r8d; Reserved
0x18003e955  mov     [rsp+50h+phkResult], rax; lpData
0x18003e95a  call    cs:__imp_RegSetValueExW
0x18003e960  mov     ebx, eax
0x18003e962  test    eax, eax
0x18003e964  jz      short loc_18003E994
0x18003e966  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e96d  lea     rax, WPP_GLOBAL_Control
0x18003e974  cmp     rcx, rax
0x18003e977  jz      short loc_18003E994
0x18003e979  test    byte ptr [rcx+1Ch], 1
0x18003e97d  jz      short loc_18003E994
0x18003e97f  mov     edx, 16h
0x18003e984  mov     rcx, [rcx+10h]
0x18003e988  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x18003e98f  call    WPP_SF_
0x18003e994  mov     eax, cs:dword_180053218
0x18003e99a  cmp     eax, 5
0x18003e99d  jbe     short loc_18003E9FC
0x18003e99f  mov     rdx, 400000000000h
0x18003e9a9  lea     rcx, dword_180053218
0x18003e9b0  call    _tlgKeywordOn
0x18003e9b5  test    al, al
0x18003e9b7  jz      short loc_18003E9FC
0x18003e9b9  test    ebx, ebx
0x18003e9bb  jg      short loc_18003E9C1
0x18003e9bd  mov     eax, ebx
0x18003e9bf  jmp     short loc_18003E9C9
0x18003e9c1  movzx   eax, bx
0x18003e9c4  or      eax, 80070000h
0x18003e9c9  mov     [rbp+arg_10], eax
0x18003e9cc  lea     rdx, dword_18004C74C
0x18003e9d3  mov     eax, [rbp+Data]
0x18003e9d6  mov     [rbp+arg_18], eax
0x18003e9d9  lea     rax, [rbp+arg_10]
0x18003e9dd  mov     [rsp+50h+var_20], rax
0x18003e9e2  lea     rax, [rbp+arg_18]
0x18003e9e6  mov     qword ptr [rsp+50h+cbData], rax
0x18003e9eb  lea     rax, [rbp+var_10]
0x18003e9ef  mov     [rsp+50h+phkResult], rax
0x18003e9f4  mov     [rbp+var_10], edi
0x18003e9f7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003e9fc  test    ebx, ebx
0x18003e9fe  jle     short loc_18003EA09
0x18003ea00  movzx   ebx, bx
0x18003ea03  or      ebx, 80070000h
0x18003ea09  lea     rcx, [rbp+hKey]
0x18003ea0d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ea12  mov     eax, ebx
0x18003ea14  add     rsp, 50h
0x18003ea18  pop     rdi
0x18003ea19  pop     rbx
0x18003ea1a  pop     rbp
0x18003ea1b  retn
```
