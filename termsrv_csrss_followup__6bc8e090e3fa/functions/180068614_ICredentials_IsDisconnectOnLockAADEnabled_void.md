# ICredentials::IsDisconnectOnLockAADEnabled(void)

- ea: `0x180068614`
- end: `0x180068799`
- name: `?IsDisconnectOnLockAADEnabled@ICredentials@@QEAAHXZ`
- size: `389`
- prototype: `__int64 __fastcall(ICredentials *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800675d0`
- `0x180067650`

## callees

- `0x180001294`
- `0x180015310`
- `0x180068614`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800686bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800686bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068783`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068664`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068664`

## string_xrefs

- `0x180068643`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18006871a`: `RegQueryValueEx for fDisconnectOnLockMicrosoftIdentity failed, policy is not configured so disconnect on lock is enabled by default`
- `0x18006874e`: `ICredentials::IsDisconnectOnLockAADEnabled() completed`
- `0x180068688`: `RegOpenKeyEx failed`

## pseudocode

```c
__int64 __fastcall ICredentials::IsDisconnectOnLockAADEnabled(ICredentials *this)
{
  unsigned int v1; // ebx
  LSTATUS v2; // ecx
  int v3; // r8d
  int v4; // r9d
  const char *v5; // rax
  __int16 *v6; // rdx
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v10[2]; // [rsp+38h] [rbp-10h] BYREF
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
  v1 = 1;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0,
         0x20019u,
         &hKey);
  if ( v2 )
  {
    if ( (unsigned int)dword_18012E170 <= 5 )
      goto LABEL_13;
    LODWORD(v13) = v2;
    v5 = "RegOpenKeyEx failed";
    v6 = (__int16 *)byte_18010F839;
    goto LABEL_12;
  }
  v7 = RegQueryValueExW(hKey, L"fDisconnectOnLockMicrosoftIdentity", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v7 )
  {
    if ( v7 == 2 && (unsigned int)dword_18012E170 > 5 )
    {
      LODWORD(v13) = 2;
      v5 = "RegQueryValueEx for fDisconnectOnLockMicrosoftIdentity failed, policy is not configured so disconnect on lock"
           " is enabled by default";
      v6 = &word_18010F89E;
LABEL_12:
      v10[0] = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v2,
        (_DWORD)v6,
        v3,
        v4,
        (__int64)v10,
        (__int64)&v13);
    }
  }
  else if ( !Data )
  {
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v13 = "Disconnect on Lock for AAD is disabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v2,
        (unsigned int)word_18010F872,
        v3,
        v4,
        (__int64)&v13);
    }
    v1 = 0;
  }
LABEL_13:
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    LODWORD(v13) = v1;
    v10[0] = "ICredentials::IsDisconnectOnLockAADEnabled() completed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)&byte_18010F8D7,
      v3,
      v4,
      (__int64)v10,
      (__int64)&v13);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180068614  mov     qword ptr [rsp-10h+Data], rcx
0x180068619  push    rbp
0x18006861a  push    rbx
0x18006861b  mov     rbp, rsp
0x18006861e  sub     rsp, 48h
0x180068622  lea     rax, [rbp+hKey]
0x180068626  mov     [rbp+hKey], 0
0x18006862e  mov     r9d, 20019h; samDesired
0x180068634  mov     [rsp+48h+phkResult], rax; phkResult
0x180068639  xor     r8d, r8d; ulOptions
0x18006863c  mov     [rbp+Data], 0
0x180068643  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18006864a  mov     [rbp+Type], 0
0x180068651  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068658  mov     [rbp+cbData], 4
0x18006865f  mov     ebx, 1
0x180068664  call    cs:__imp_RegOpenKeyExW
0x18006866b  nop     dword ptr [rax+rax+00h]
0x180068670  mov     ecx, eax
0x180068672  test    eax, eax
0x180068674  jz      short loc_18006869B
0x180068676  mov     eax, cs:dword_18012E170
0x18006867c  cmp     eax, 5
0x18006867f  jbe     loc_180068743
0x180068685  mov     dword ptr [rbp+arg_8], ecx
0x180068688  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x18006868f  lea     rdx, byte_18010F839
0x180068696  jmp     loc_180068728
0x18006869b  mov     rcx, [rbp+hKey]; hKey
0x18006869f  lea     rax, [rbp+cbData]
0x1800686a3  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800686a8  lea     r9, [rbp+Type]; lpType
0x1800686ac  lea     rax, [rbp+Data]
0x1800686b0  xor     r8d, r8d; lpReserved
0x1800686b3  lea     rdx, aFdisconnectonl_2; "fDisconnectOnLockMicrosoftIdentity"
0x1800686ba  mov     [rsp+48h+phkResult], rax; lpData
0x1800686bf  call    cs:__imp_RegQueryValueExW
0x1800686c6  nop     dword ptr [rax+rax+00h]
0x1800686cb  test    eax, eax
0x1800686cd  jnz     short loc_180068703
0x1800686cf  cmp     [rbp+Data], eax
0x1800686d2  jnz     short loc_180068743
0x1800686d4  mov     eax, cs:dword_18012E170
0x1800686da  cmp     eax, 5
0x1800686dd  jbe     short loc_1800686FF
0x1800686df  lea     rax, aDisconnectOnLo; "Disconnect on Lock for AAD is disabled"
0x1800686e6  mov     [rbp+arg_8], rax
0x1800686ea  lea     rdx, word_18010F872
0x1800686f1  lea     rax, [rbp+arg_8]
0x1800686f5  mov     [rsp+48h+phkResult], rax
0x1800686fa  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800686ff  xor     ebx, ebx
0x180068701  jmp     short loc_180068743
0x180068703  cmp     eax, 2
0x180068706  jnz     short loc_180068743
0x180068708  mov     eax, cs:dword_18012E170
0x18006870e  cmp     eax, 5
0x180068711  jbe     short loc_180068743
0x180068713  mov     dword ptr [rbp+arg_8], 2
0x18006871a  lea     rax, aRegqueryvaluee_4; "RegQueryValueEx for fDisconnectOnLockMi"...
0x180068721  lea     rdx, word_18010F89E
0x180068728  mov     [rbp+var_10], rax
0x18006872c  lea     rax, [rbp+arg_8]
0x180068730  mov     [rsp+48h+lpcbData], rax
0x180068735  lea     rax, [rbp+var_10]
0x180068739  mov     [rsp+48h+phkResult], rax
0x18006873e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180068743  mov     eax, cs:dword_18012E170
0x180068749  cmp     eax, 5
0x18006874c  jbe     short loc_18006877A
0x18006874e  lea     rax, aIcredentialsIs; "ICredentials::IsDisconnectOnLockAADEnab"...
0x180068755  mov     dword ptr [rbp+arg_8], ebx
0x180068758  mov     [rbp+var_10], rax
0x18006875c  lea     rdx, byte_18010F8D7
0x180068763  lea     rax, [rbp+arg_8]
0x180068767  mov     [rsp+48h+lpcbData], rax
0x18006876c  lea     rax, [rbp+var_10]
0x180068770  mov     [rsp+48h+phkResult], rax
0x180068775  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006877a  mov     rcx, [rbp+hKey]; hKey
0x18006877e  test    rcx, rcx
0x180068781  jz      short loc_18006878F
0x180068783  call    cs:__imp_RegCloseKey
0x18006878a  nop     dword ptr [rax+rax+00h]
0x18006878f  mov     eax, ebx
0x180068791  add     rsp, 48h
0x180068795  pop     rbx
0x180068796  pop     rbp
0x180068797  retn
```
