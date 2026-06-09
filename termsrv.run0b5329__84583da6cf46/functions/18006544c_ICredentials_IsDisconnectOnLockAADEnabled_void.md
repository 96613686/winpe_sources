# ICredentials::IsDisconnectOnLockAADEnabled(void)

- ea: `0x18006544c`
- end: `0x1800655be`
- name: `?IsDisconnectOnLockAADEnabled@ICredentials@@QEAAHXZ`
- size: `370`
- prototype: `__int64 __fastcall(ICredentials *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180064410`
- `0x180064490`

## callees

- `0x180001284`
- `0x1800148f0`
- `0x18006544c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800654f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800654f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800655af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800655af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006549c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006549c`

## string_xrefs

- `0x18006547b`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x180065546`: `RegQueryValueEx for fDisconnectOnLockMicrosoftIdentity failed, policy is not configured so disconnect on lock is enabled by default`
- `0x18006557a`: `ICredentials::IsDisconnectOnLockAADEnabled() completed`
- `0x1800654ba`: `RegOpenKeyEx failed`

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
    if ( (unsigned int)dword_180128170 <= 5 )
      goto LABEL_13;
    LODWORD(v13) = v2;
    v5 = "RegOpenKeyEx failed";
    v6 = (__int16 *)byte_1801097B9;
    goto LABEL_12;
  }
  v7 = RegQueryValueExW(hKey, L"fDisconnectOnLockMicrosoftIdentity", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v7 )
  {
    if ( v7 == 2 && (unsigned int)dword_180128170 > 5 )
    {
      LODWORD(v13) = 2;
      v5 = "RegQueryValueEx for fDisconnectOnLockMicrosoftIdentity failed, policy is not configured so disconnect on lock"
           " is enabled by default";
      v6 = &word_18010981E;
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
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v13 = "Disconnect on Lock for AAD is disabled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v2,
        (unsigned int)word_1801097F2,
        v3,
        v4,
        (__int64)&v13);
    }
    v1 = 0;
  }
LABEL_13:
  if ( (unsigned int)dword_180128170 > 5 )
  {
    LODWORD(v13) = v1;
    v10[0] = "ICredentials::IsDisconnectOnLockAADEnabled() completed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)&byte_180109857,
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
0x18006544c  mov     qword ptr [rsp-10h+Data], rcx
0x180065451  push    rbp
0x180065452  push    rbx
0x180065453  mov     rbp, rsp
0x180065456  sub     rsp, 48h
0x18006545a  lea     rax, [rbp+hKey]
0x18006545e  mov     [rbp+hKey], 0
0x180065466  mov     r9d, 20019h; samDesired
0x18006546c  mov     [rsp+48h+phkResult], rax; phkResult
0x180065471  xor     r8d, r8d; ulOptions
0x180065474  mov     [rbp+Data], 0
0x18006547b  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180065482  mov     [rbp+Type], 0
0x180065489  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065490  mov     [rbp+cbData], 4
0x180065497  mov     ebx, 1
0x18006549c  call    cs:__imp_RegOpenKeyExW
0x1800654a2  mov     ecx, eax
0x1800654a4  test    eax, eax
0x1800654a6  jz      short loc_1800654CD
0x1800654a8  mov     eax, cs:dword_180128170
0x1800654ae  cmp     eax, 5
0x1800654b1  jbe     loc_18006556F
0x1800654b7  mov     dword ptr [rbp+arg_8], ecx
0x1800654ba  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x1800654c1  lea     rdx, byte_1801097B9
0x1800654c8  jmp     loc_180065554
0x1800654cd  mov     rcx, [rbp+hKey]; hKey
0x1800654d1  lea     rax, [rbp+cbData]
0x1800654d5  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800654da  lea     r9, [rbp+Type]; lpType
0x1800654de  lea     rax, [rbp+Data]
0x1800654e2  xor     r8d, r8d; lpReserved
0x1800654e5  lea     rdx, aFdisconnectonl_2; "fDisconnectOnLockMicrosoftIdentity"
0x1800654ec  mov     [rsp+48h+phkResult], rax; lpData
0x1800654f1  call    cs:__imp_RegQueryValueExW
0x1800654f7  test    eax, eax
0x1800654f9  jnz     short loc_18006552F
0x1800654fb  cmp     [rbp+Data], eax
0x1800654fe  jnz     short loc_18006556F
0x180065500  mov     eax, cs:dword_180128170
0x180065506  cmp     eax, 5
0x180065509  jbe     short loc_18006552B
0x18006550b  lea     rax, aDisconnectOnLo; "Disconnect on Lock for AAD is disabled"
0x180065512  mov     [rbp+arg_8], rax
0x180065516  lea     rdx, word_1801097F2
0x18006551d  lea     rax, [rbp+arg_8]
0x180065521  mov     [rsp+48h+phkResult], rax
0x180065526  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006552b  xor     ebx, ebx
0x18006552d  jmp     short loc_18006556F
0x18006552f  cmp     eax, 2
0x180065532  jnz     short loc_18006556F
0x180065534  mov     eax, cs:dword_180128170
0x18006553a  cmp     eax, 5
0x18006553d  jbe     short loc_18006556F
0x18006553f  mov     dword ptr [rbp+arg_8], 2
0x180065546  lea     rax, aRegqueryvaluee_4; "RegQueryValueEx for fDisconnectOnLockMi"...
0x18006554d  lea     rdx, word_18010981E
0x180065554  mov     [rbp+var_10], rax
0x180065558  lea     rax, [rbp+arg_8]
0x18006555c  mov     [rsp+48h+lpcbData], rax
0x180065561  lea     rax, [rbp+var_10]
0x180065565  mov     [rsp+48h+phkResult], rax
0x18006556a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006556f  mov     eax, cs:dword_180128170
0x180065575  cmp     eax, 5
0x180065578  jbe     short loc_1800655A6
0x18006557a  lea     rax, aIcredentialsIs; "ICredentials::IsDisconnectOnLockAADEnab"...
0x180065581  mov     dword ptr [rbp+arg_8], ebx
0x180065584  mov     [rbp+var_10], rax
0x180065588  lea     rdx, byte_180109857
0x18006558f  lea     rax, [rbp+arg_8]
0x180065593  mov     [rsp+48h+lpcbData], rax
0x180065598  lea     rax, [rbp+var_10]
0x18006559c  mov     [rsp+48h+phkResult], rax
0x1800655a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800655a6  mov     rcx, [rbp+hKey]; hKey
0x1800655aa  test    rcx, rcx
0x1800655ad  jz      short loc_1800655B5
0x1800655af  call    cs:__imp_RegCloseKey
0x1800655b5  mov     eax, ebx
0x1800655b7  add     rsp, 48h
0x1800655bb  pop     rbx
0x1800655bc  pop     rbp
0x1800655bd  retn
```
