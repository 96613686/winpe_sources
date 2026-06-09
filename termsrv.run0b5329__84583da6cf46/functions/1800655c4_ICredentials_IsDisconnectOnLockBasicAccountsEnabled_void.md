# ICredentials::IsDisconnectOnLockBasicAccountsEnabled(void)

- ea: `0x1800655c4`
- end: `0x180065717`
- name: `?IsDisconnectOnLockBasicAccountsEnabled@ICredentials@@QEAAHXZ`
- size: `339`
- prototype: `__int64 __fastcall(ICredentials *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180064410`
- `0x180064490`
- `0x180064520`

## callees

- `0x180001284`
- `0x1800148f0`
- `0x1800655c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065662`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065662`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065708`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065708`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006560f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006560f`

## string_xrefs

- `0x1800655f3`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x180065632`: `RegOpenKeyEx failed`

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
    v4 = dword_180128170;
    if ( (unsigned int)dword_180128170 > 5 )
    {
      LODWORD(v13) = v1;
      v5 = &byte_1801096EF;
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
    if ( (unsigned int)dword_180128170 > 5 )
    {
      LODWORD(v13) = v4;
      v6 = "RegQueryValueEx for fDisconnectOnLockLegacy failed";
      v5 = (char *)&unk_180109780;
      goto LABEL_12;
    }
LABEL_13:
    v7 = 0;
    goto LABEL_14;
  }
  v7 = 1;
  if ( Data != 1 )
  {
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v13 = "fDisconnectOnLockLegacy is disabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        0,
        (unsigned int)&dword_180109754,
        v2,
        v3,
        (__int64)&v13);
    }
    goto LABEL_13;
  }
  if ( (unsigned int)dword_180128170 > 5 )
  {
    v13 = "fDisconnectOnLockLegacy is enabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      0,
      (unsigned int)&unk_180109728,
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
0x1800655c4  mov     qword ptr [rsp-10h+Data], rcx
0x1800655c9  push    rbp
0x1800655ca  push    rbx
0x1800655cb  mov     rbp, rsp
0x1800655ce  sub     rsp, 48h
0x1800655d2  lea     rax, [rbp+hKey]
0x1800655d6  mov     [rbp+hKey], 0
0x1800655de  mov     r9d, 20019h; samDesired
0x1800655e4  mov     [rsp+48h+phkResult], rax; phkResult
0x1800655e9  xor     r8d, r8d; ulOptions
0x1800655ec  mov     [rbp+Data], 0
0x1800655f3  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x1800655fa  mov     [rbp+Type], 0
0x180065601  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065608  mov     [rbp+cbData], 4
0x18006560f  call    cs:__imp_RegOpenKeyExW
0x180065615  test    eax, eax
0x180065617  jz      short loc_18006563E
0x180065619  mov     ecx, cs:dword_180128170
0x18006561f  cmp     ecx, 5
0x180065622  jbe     loc_1800656FD
0x180065628  mov     dword ptr [rbp+arg_8], eax
0x18006562b  lea     rdx, byte_1801096EF
0x180065632  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x180065639  jmp     loc_1800656E2
0x18006563e  mov     rcx, [rbp+hKey]; hKey
0x180065642  lea     rax, [rbp+cbData]
0x180065646  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18006564b  lea     r9, [rbp+Type]; lpType
0x18006564f  lea     rax, [rbp+Data]
0x180065653  xor     r8d, r8d; lpReserved
0x180065656  lea     rdx, aFdisconnectonl; "fDisconnectOnLockLegacy"
0x18006565d  mov     [rsp+48h+phkResult], rax; lpData
0x180065662  call    cs:__imp_RegQueryValueExW
0x180065668  mov     ecx, eax
0x18006566a  test    eax, eax
0x18006566c  mov     eax, cs:dword_180128170
0x180065672  jnz     short loc_1800656CC
0x180065674  mov     ebx, 1
0x180065679  cmp     [rbp+Data], ebx
0x18006567c  jnz     short loc_1800656A5
0x18006567e  cmp     eax, 5
0x180065681  jbe     short loc_1800656FF
0x180065683  lea     rax, aFdisconnectonl_1; "fDisconnectOnLockLegacy is enabled"
0x18006568a  mov     [rbp+arg_8], rax
0x18006568e  lea     rdx, unk_180109728
0x180065695  lea     rax, [rbp+arg_8]
0x180065699  mov     [rsp+48h+phkResult], rax
0x18006569e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800656a3  jmp     short loc_1800656FF
0x1800656a5  cmp     eax, 5
0x1800656a8  jbe     short loc_1800656FD
0x1800656aa  lea     rax, aFdisconnectonl_0; "fDisconnectOnLockLegacy is disabled"
0x1800656b1  mov     [rbp+arg_8], rax
0x1800656b5  lea     rdx, dword_180109754
0x1800656bc  lea     rax, [rbp+arg_8]
0x1800656c0  mov     [rsp+48h+phkResult], rax
0x1800656c5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800656ca  jmp     short loc_1800656FD
0x1800656cc  cmp     eax, 5
0x1800656cf  jbe     short loc_1800656FD
0x1800656d1  mov     dword ptr [rbp+arg_8], ecx
0x1800656d4  lea     rax, aRegqueryvaluee_6; "RegQueryValueEx for fDisconnectOnLockLe"...
0x1800656db  lea     rdx, unk_180109780
0x1800656e2  mov     [rbp+var_10], rax
0x1800656e6  lea     rax, [rbp+arg_8]
0x1800656ea  mov     [rsp+48h+lpcbData], rax
0x1800656ef  lea     rax, [rbp+var_10]
0x1800656f3  mov     [rsp+48h+phkResult], rax
0x1800656f8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800656fd  xor     ebx, ebx
0x1800656ff  mov     rcx, [rbp+hKey]; hKey
0x180065703  test    rcx, rcx
0x180065706  jz      short loc_18006570E
0x180065708  call    cs:__imp_RegCloseKey
0x18006570e  mov     eax, ebx
0x180065710  add     rsp, 48h
0x180065714  pop     rbx
0x180065715  pop     rbp
0x180065716  retn
```
