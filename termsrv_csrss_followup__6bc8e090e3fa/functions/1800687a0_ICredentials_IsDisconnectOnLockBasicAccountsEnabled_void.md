# ICredentials::IsDisconnectOnLockBasicAccountsEnabled(void)

- ea: `0x1800687a0`
- end: `0x180068906`
- name: `?IsDisconnectOnLockBasicAccountsEnabled@ICredentials@@QEAAHXZ`
- size: `358`
- prototype: `__int64 __fastcall(ICredentials *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800675d0`
- `0x180067650`
- `0x1800676e0`

## callees

- `0x180001294`
- `0x180015310`
- `0x1800687a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180068844`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180068844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800688f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800688f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800687eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800687eb`

## string_xrefs

- `0x1800687cf`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x180068814`: `RegOpenKeyEx failed`

## pseudocode

```c
__int64 __fastcall ICredentials::IsDisconnectOnLockBasicAccountsEnabled(ICredentials *this)
{
  LSTATUS v1; // eax
  int v2; // r8d
  int v3; // r9d
  LSTATUS v4; // ecx
  char *v5; // rdx
  const char *v6; // rax
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  const char *v10; // [rsp+38h] [rbp-10h] BYREF
  int Data; // [rsp+60h] [rbp+18h] BYREF
  int v12; // [rsp+64h] [rbp+1Ch]
  const char *v13; // [rsp+68h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+28h] BYREF
  DWORD Type; // [rsp+78h] [rbp+30h] BYREF

  v12 = HIDWORD(this);
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0,
         0x20019u,
         &hKey);
  if ( v1 )
  {
    v4 = dword_18012E170;
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      LODWORD(v13) = v1;
      v5 = &byte_18010F76F;
      v6 = "RegOpenKeyEx failed";
LABEL_12:
      v10 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v4,
        (_DWORD)v5,
        v2,
        v3,
        (__int64)&v10,
        (__int64)&v13);
      goto LABEL_13;
    }
    goto LABEL_13;
  }
  v4 = RegQueryValueExW(hKey, L"fDisconnectOnLockLegacy", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v4 )
  {
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      LODWORD(v13) = v4;
      v6 = "RegQueryValueEx for fDisconnectOnLockLegacy failed";
      v5 = (char *)&unk_18010F800;
      goto LABEL_12;
    }
LABEL_13:
    v7 = 0;
    goto LABEL_14;
  }
  v7 = 1;
  if ( Data != 1 )
  {
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v13 = "fDisconnectOnLockLegacy is disabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        0,
        (unsigned int)&dword_18010F7D4,
        v2,
        v3,
        (__int64)&v13);
    }
    goto LABEL_13;
  }
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    v13 = "fDisconnectOnLockLegacy is enabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      0,
      (unsigned int)&unk_18010F7A8,
      v2,
      v3,
      (__int64)&v13);
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x1800687a0  mov     qword ptr [rsp-10h+Data], rcx
0x1800687a5  push    rbp
0x1800687a6  push    rbx
0x1800687a7  mov     rbp, rsp
0x1800687aa  sub     rsp, 48h
0x1800687ae  lea     rax, [rbp+hKey]
0x1800687b2  mov     [rbp+hKey], 0
0x1800687ba  mov     r9d, 20019h; samDesired
0x1800687c0  mov     [rsp+48h+phkResult], rax; phkResult
0x1800687c5  xor     r8d, r8d; ulOptions
0x1800687c8  mov     [rbp+Data], 0
0x1800687cf  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x1800687d6  mov     [rbp+Type], 0
0x1800687dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800687e4  mov     [rbp+cbData], 4
0x1800687eb  call    cs:__imp_RegOpenKeyExW
0x1800687f2  nop     dword ptr [rax+rax+00h]
0x1800687f7  test    eax, eax
0x1800687f9  jz      short loc_180068820
0x1800687fb  mov     ecx, cs:dword_18012E170
0x180068801  cmp     ecx, 5
0x180068804  jbe     loc_1800688E5
0x18006880a  mov     dword ptr [rbp+arg_8], eax
0x18006880d  lea     rdx, byte_18010F76F
0x180068814  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x18006881b  jmp     loc_1800688CA
0x180068820  mov     rcx, [rbp+hKey]; hKey
0x180068824  lea     rax, [rbp+cbData]
0x180068828  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18006882d  lea     r9, [rbp+Type]; lpType
0x180068831  lea     rax, [rbp+Data]
0x180068835  xor     r8d, r8d; lpReserved
0x180068838  lea     rdx, aFdisconnectonl; "fDisconnectOnLockLegacy"
0x18006883f  mov     [rsp+48h+phkResult], rax; lpData
0x180068844  call    cs:__imp_RegQueryValueExW
0x18006884b  nop     dword ptr [rax+rax+00h]
0x180068850  mov     ecx, eax
0x180068852  test    eax, eax
0x180068854  mov     eax, cs:dword_18012E170
0x18006885a  jnz     short loc_1800688B4
0x18006885c  mov     ebx, 1
0x180068861  cmp     [rbp+Data], ebx
0x180068864  jnz     short loc_18006888D
0x180068866  cmp     eax, 5
0x180068869  jbe     short loc_1800688E7
0x18006886b  lea     rax, aFdisconnectonl_1; "fDisconnectOnLockLegacy is enabled"
0x180068872  mov     [rbp+arg_8], rax
0x180068876  lea     rdx, unk_18010F7A8
0x18006887d  lea     rax, [rbp+arg_8]
0x180068881  mov     [rsp+48h+phkResult], rax
0x180068886  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006888b  jmp     short loc_1800688E7
0x18006888d  cmp     eax, 5
0x180068890  jbe     short loc_1800688E5
0x180068892  lea     rax, aFdisconnectonl_0; "fDisconnectOnLockLegacy is disabled"
0x180068899  mov     [rbp+arg_8], rax
0x18006889d  lea     rdx, dword_18010F7D4
0x1800688a4  lea     rax, [rbp+arg_8]
0x1800688a8  mov     [rsp+48h+phkResult], rax
0x1800688ad  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800688b2  jmp     short loc_1800688E5
0x1800688b4  cmp     eax, 5
0x1800688b7  jbe     short loc_1800688E5
0x1800688b9  mov     dword ptr [rbp+arg_8], ecx
0x1800688bc  lea     rax, aRegqueryvaluee_6; "RegQueryValueEx for fDisconnectOnLockLe"...
0x1800688c3  lea     rdx, unk_18010F800
0x1800688ca  mov     [rbp+var_10], rax
0x1800688ce  lea     rax, [rbp+arg_8]
0x1800688d2  mov     [rsp+48h+lpcbData], rax
0x1800688d7  lea     rax, [rbp+var_10]
0x1800688db  mov     [rsp+48h+phkResult], rax
0x1800688e0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800688e5  xor     ebx, ebx
0x1800688e7  mov     rcx, [rbp+hKey]; hKey
0x1800688eb  test    rcx, rcx
0x1800688ee  jz      short loc_1800688FC
0x1800688f0  call    cs:__imp_RegCloseKey
0x1800688f7  nop     dword ptr [rax+rax+00h]
0x1800688fc  mov     eax, ebx
0x1800688fe  add     rsp, 48h
0x180068902  pop     rbx
0x180068903  pop     rbp
0x180068904  retn
```
