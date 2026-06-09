# ICredentials::IsAADTestRegKeyEnabled(void)

- ea: `0x1800684a4`
- end: `0x18006860b`
- name: `?IsAADTestRegKeyEnabled@ICredentials@@QEAAHXZ`
- size: `359`
- prototype: `__int64 __fastcall(ICredentials *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800675d0`

## callees

- `0x180001294`
- `0x180015310`
- `0x1800684a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006856b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006856b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800685f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800685f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800684ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800684ef`

## string_xrefs

- `0x180068514`: `RegOpenKeyEx failed`

## pseudocode

```c
__int64 __fastcall ICredentials::IsAADTestRegKeyEnabled(ICredentials *this)
{
  LSTATUS v1; // eax
  __int64 v2; // r8
  __int64 v3; // r9
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  const unsigned __int16 *v10[2]; // [rsp+38h] [rbp-10h] BYREF
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
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  if ( v1 && (unsigned int)dword_18012E170 > 5 )
  {
    LODWORD(v13) = v1;
    v10[0] = (const unsigned __int16 *)"RegOpenKeyEx failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_18012E170,
      (unsigned __int8 *)&word_18010F90E,
      v2,
      v3,
      v10,
      (__int64)&v13);
    v4 = 0;
  }
  else
  {
    v4 = 0;
    if ( !v1 )
    {
      v5 = RegQueryValueExW(hKey, L"DisconnectOnLockTestAAD", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( v5 )
      {
        if ( (unsigned int)dword_18012E170 > 5 )
        {
          LODWORD(v13) = v5;
          v10[0] = (const unsigned __int16 *)"RegQueryValueEx for DisconnectOnLockTestAAD failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v5,
            (unsigned __int8 *)byte_18010F973,
            v6,
            v7,
            v10,
            (__int64)&v13);
        }
      }
      else if ( Data == 1 )
      {
        if ( (unsigned int)dword_18012E170 > 5 )
        {
          v13 = "DisconnectOnLockTestAAD reg key is enabled, IsAADCred is true";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v5,
            (unsigned __int8 *)byte_18010F947,
            v6,
            v7,
            (const unsigned __int16 **)&v13);
        }
        v4 = 1;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1800684a4  mov     qword ptr [rsp-10h+Data], rcx
0x1800684a9  push    rbp
0x1800684aa  push    rbx
0x1800684ab  mov     rbp, rsp
0x1800684ae  sub     rsp, 48h
0x1800684b2  lea     rax, [rbp+hKey]
0x1800684b6  mov     [rbp+hKey], 0
0x1800684be  mov     r9d, 20019h; samDesired
0x1800684c4  mov     [rsp+48h+phkResult], rax; phkResult
0x1800684c9  xor     r8d, r8d; ulOptions
0x1800684cc  mov     [rbp+Data], 0
0x1800684d3  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800684da  mov     [rbp+Type], 0
0x1800684e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800684e8  mov     [rbp+cbData], 4
0x1800684ef  call    cs:__imp_RegOpenKeyExW
0x1800684f6  nop     dword ptr [rax+rax+00h]
0x1800684fb  test    eax, eax
0x1800684fd  jz      short loc_18006853D
0x1800684ff  mov     ecx, cs:dword_18012E170
0x180068505  cmp     ecx, 5
0x180068508  jbe     short loc_18006853D
0x18006850a  mov     dword ptr [rbp+arg_8], eax
0x18006850d  lea     rdx, word_18010F90E
0x180068514  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x18006851b  mov     [rbp+var_10], rax
0x18006851f  lea     rax, [rbp+arg_8]
0x180068523  mov     [rsp+48h+lpcbData], rax
0x180068528  lea     rax, [rbp+var_10]
0x18006852c  mov     [rsp+48h+phkResult], rax
0x180068531  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180068536  xor     ebx, ebx
0x180068538  jmp     loc_1800685EC
0x18006853d  xor     ebx, ebx
0x18006853f  test    eax, eax
0x180068541  jnz     loc_1800685EC
0x180068547  mov     rcx, [rbp+hKey]; hKey
0x18006854b  lea     rax, [rbp+cbData]
0x18006854f  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180068554  lea     r9, [rbp+Type]; lpType
0x180068558  lea     rax, [rbp+Data]
0x18006855c  xor     r8d, r8d; lpReserved
0x18006855f  lea     rdx, aDisconnectonlo_0; "DisconnectOnLockTestAAD"
0x180068566  mov     [rsp+48h+phkResult], rax; lpData
0x18006856b  call    cs:__imp_RegQueryValueExW
0x180068572  nop     dword ptr [rax+rax+00h]
0x180068577  mov     ecx, eax
0x180068579  test    eax, eax
0x18006857b  jnz     short loc_1800685B5
0x18006857d  cmp     [rbp+Data], 1
0x180068581  jnz     short loc_1800685EC
0x180068583  mov     eax, cs:dword_18012E170
0x180068589  cmp     eax, 5
0x18006858c  jbe     short loc_1800685AE
0x18006858e  lea     rax, aDisconnectonlo; "DisconnectOnLockTestAAD reg key is enab"...
0x180068595  mov     [rbp+arg_8], rax
0x180068599  lea     rdx, byte_18010F947
0x1800685a0  lea     rax, [rbp+arg_8]
0x1800685a4  mov     [rsp+48h+phkResult], rax
0x1800685a9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800685ae  mov     ebx, 1
0x1800685b3  jmp     short loc_1800685EC
0x1800685b5  mov     eax, cs:dword_18012E170
0x1800685bb  cmp     eax, 5
0x1800685be  jbe     short loc_1800685EC
0x1800685c0  lea     rax, aRegqueryvaluee_2; "RegQueryValueEx for DisconnectOnLockTes"...
0x1800685c7  mov     dword ptr [rbp+arg_8], ecx
0x1800685ca  mov     [rbp+var_10], rax
0x1800685ce  lea     rdx, byte_18010F973
0x1800685d5  lea     rax, [rbp+arg_8]
0x1800685d9  mov     [rsp+48h+lpcbData], rax
0x1800685de  lea     rax, [rbp+var_10]
0x1800685e2  mov     [rsp+48h+phkResult], rax
0x1800685e7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800685ec  mov     rcx, [rbp+hKey]; hKey
0x1800685f0  test    rcx, rcx
0x1800685f3  jz      short loc_180068601
0x1800685f5  call    cs:__imp_RegCloseKey
0x1800685fc  nop     dword ptr [rax+rax+00h]
0x180068601  mov     eax, ebx
0x180068603  add     rsp, 48h
0x180068607  pop     rbx
0x180068608  pop     rbp
0x180068609  retn
```
