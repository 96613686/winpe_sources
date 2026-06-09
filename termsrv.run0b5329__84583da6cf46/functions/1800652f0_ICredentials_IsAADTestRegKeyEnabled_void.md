# ICredentials::IsAADTestRegKeyEnabled(void)

- ea: `0x1800652f0`
- end: `0x180065444`
- name: `?IsAADTestRegKeyEnabled@ICredentials@@QEAAHXZ`
- size: `340`
- prototype: `__int64 __fastcall(ICredentials *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180064410`

## callees

- `0x180001284`
- `0x1800148f0`
- `0x1800652f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800653b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800653b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065435`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065435`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006533b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006533b`

## string_xrefs

- `0x18006535a`: `RegOpenKeyEx failed`

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
  if ( v1 && (unsigned int)dword_180128170 > 5 )
  {
    LODWORD(v13) = v1;
    v10[0] = (const unsigned __int16 *)"RegOpenKeyEx failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_180128170,
      (unsigned __int8 *)&word_18010988E,
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
        if ( (unsigned int)dword_180128170 > 5 )
        {
          LODWORD(v13) = v5;
          v10[0] = (const unsigned __int16 *)"RegQueryValueEx for DisconnectOnLockTestAAD failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v5,
            (unsigned __int8 *)byte_1801098F3,
            v6,
            v7,
            v10,
            (__int64)&v13);
        }
      }
      else if ( Data == 1 )
      {
        if ( (unsigned int)dword_180128170 > 5 )
        {
          v13 = "DisconnectOnLockTestAAD reg key is enabled, IsAADCred is true";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v5,
            (unsigned __int8 *)byte_1801098C7,
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
0x1800652f0  mov     qword ptr [rsp-10h+Data], rcx
0x1800652f5  push    rbp
0x1800652f6  push    rbx
0x1800652f7  mov     rbp, rsp
0x1800652fa  sub     rsp, 48h
0x1800652fe  lea     rax, [rbp+hKey]
0x180065302  mov     [rbp+hKey], 0
0x18006530a  mov     r9d, 20019h; samDesired
0x180065310  mov     [rsp+48h+phkResult], rax; phkResult
0x180065315  xor     r8d, r8d; ulOptions
0x180065318  mov     [rbp+Data], 0
0x18006531f  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x180065326  mov     [rbp+Type], 0
0x18006532d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065334  mov     [rbp+cbData], 4
0x18006533b  call    cs:__imp_RegOpenKeyExW
0x180065341  test    eax, eax
0x180065343  jz      short loc_180065383
0x180065345  mov     ecx, cs:dword_180128170
0x18006534b  cmp     ecx, 5
0x18006534e  jbe     short loc_180065383
0x180065350  mov     dword ptr [rbp+arg_8], eax
0x180065353  lea     rdx, word_18010988E
0x18006535a  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x180065361  mov     [rbp+var_10], rax
0x180065365  lea     rax, [rbp+arg_8]
0x180065369  mov     [rsp+48h+lpcbData], rax
0x18006536e  lea     rax, [rbp+var_10]
0x180065372  mov     [rsp+48h+phkResult], rax
0x180065377  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006537c  xor     ebx, ebx
0x18006537e  jmp     loc_18006542C
0x180065383  xor     ebx, ebx
0x180065385  test    eax, eax
0x180065387  jnz     loc_18006542C
0x18006538d  mov     rcx, [rbp+hKey]; hKey
0x180065391  lea     rax, [rbp+cbData]
0x180065395  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18006539a  lea     r9, [rbp+Type]; lpType
0x18006539e  lea     rax, [rbp+Data]
0x1800653a2  xor     r8d, r8d; lpReserved
0x1800653a5  lea     rdx, aDisconnectonlo_0; "DisconnectOnLockTestAAD"
0x1800653ac  mov     [rsp+48h+phkResult], rax; lpData
0x1800653b1  call    cs:__imp_RegQueryValueExW
0x1800653b7  mov     ecx, eax
0x1800653b9  test    eax, eax
0x1800653bb  jnz     short loc_1800653F5
0x1800653bd  cmp     [rbp+Data], 1
0x1800653c1  jnz     short loc_18006542C
0x1800653c3  mov     eax, cs:dword_180128170
0x1800653c9  cmp     eax, 5
0x1800653cc  jbe     short loc_1800653EE
0x1800653ce  lea     rax, aDisconnectonlo; "DisconnectOnLockTestAAD reg key is enab"...
0x1800653d5  mov     [rbp+arg_8], rax
0x1800653d9  lea     rdx, byte_1801098C7
0x1800653e0  lea     rax, [rbp+arg_8]
0x1800653e4  mov     [rsp+48h+phkResult], rax
0x1800653e9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800653ee  mov     ebx, 1
0x1800653f3  jmp     short loc_18006542C
0x1800653f5  mov     eax, cs:dword_180128170
0x1800653fb  cmp     eax, 5
0x1800653fe  jbe     short loc_18006542C
0x180065400  lea     rax, aRegqueryvaluee_2; "RegQueryValueEx for DisconnectOnLockTes"...
0x180065407  mov     dword ptr [rbp+arg_8], ecx
0x18006540a  mov     [rbp+var_10], rax
0x18006540e  lea     rdx, byte_1801098F3
0x180065415  lea     rax, [rbp+arg_8]
0x180065419  mov     [rsp+48h+lpcbData], rax
0x18006541e  lea     rax, [rbp+var_10]
0x180065422  mov     [rsp+48h+phkResult], rax
0x180065427  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006542c  mov     rcx, [rbp+hKey]; hKey
0x180065430  test    rcx, rcx
0x180065433  jz      short loc_18006543B
0x180065435  call    cs:__imp_RegCloseKey
0x18006543b  mov     eax, ebx
0x18006543d  add     rsp, 48h
0x180065441  pop     rbx
0x180065442  pop     rbp
0x180065443  retn
```
