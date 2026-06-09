# CUtils::GetAllowFastReconnect(int *)

- ea: `0x18009d0c0`
- end: `0x18009d1c8`
- name: `?GetAllowFastReconnect@CUtils@@SAJPEAH@Z`
- size: `264`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004aeb0`

## callees

- `0x180005918`
- `0x18009d0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d13d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d13d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d15a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d15a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d103`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d103`

## string_xrefs

- `0x18009d187`: `RegistryRead`

## pseudocode

```c
__int64 __fastcall CUtils::GetAllowFastReconnect(DWORD *a1)
{
  int v2; // ecx
  LSTATUS v3; // edi
  int v4; // r8d
  int v5; // r9d
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  const char *v8; // [rsp+48h] [rbp-8h] BYREF
  int Data; // [rsp+70h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  int v12; // [rsp+88h] [rbp+38h] BYREF

  *a1 = 1;
  hKey = 0;
  Data = 1;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  if ( !v3 )
  {
    Type = 0;
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"bAllowFastReconnect", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v3 || Type != 4 )
      Data = 1;
    RegCloseKey(hKey);
  }
  *a1 = Data != 0;
  if ( (unsigned int)dword_180128170 > 5 )
  {
    Type = *a1;
    v12 = Data;
    v8 = "RegistryRead";
    cbData = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)&dword_180113AF4,
      v4,
      v5,
      (__int64)&v8,
      (__int64)&v12,
      (__int64)&cbData,
      (__int64)&Type);
  }
  return 0;
}

```

## disassembly

```asm
0x18009d0c0  push    rbp
0x18009d0c2  push    rbx
0x18009d0c3  push    rdi
0x18009d0c4  mov     rbp, rsp
0x18009d0c7  sub     rsp, 50h
0x18009d0cb  mov     rbx, rcx
0x18009d0ce  mov     dword ptr [rcx], 1
0x18009d0d4  lea     rax, [rbp+hKey]
0x18009d0d8  mov     [rbp+hKey], 0
0x18009d0e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009d0e7  mov     [rsp+50h+phkResult], rax; phkResult
0x18009d0ec  mov     r9d, 20019h; samDesired
0x18009d0f2  mov     [rbp+Data], 1
0x18009d0f9  xor     r8d, r8d; ulOptions
0x18009d0fc  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18009d103  call    cs:__imp_RegOpenKeyExW
0x18009d109  mov     edi, eax
0x18009d10b  test    eax, eax
0x18009d10d  jnz     short loc_18009D160
0x18009d10f  mov     rcx, [rbp+hKey]; hKey
0x18009d113  lea     r9, [rbp+Type]; lpType
0x18009d117  mov     [rbp+Type], eax
0x18009d11a  lea     rdx, aBallowfastreco; "bAllowFastReconnect"
0x18009d121  lea     rax, [rbp+cbData]
0x18009d125  mov     [rbp+cbData], 4
0x18009d12c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18009d131  xor     r8d, r8d; lpReserved
0x18009d134  lea     rax, [rbp+Data]
0x18009d138  mov     [rsp+50h+phkResult], rax; lpData
0x18009d13d  call    cs:__imp_RegQueryValueExW
0x18009d143  mov     edi, eax
0x18009d145  test    eax, eax
0x18009d147  jnz     short loc_18009D14F
0x18009d149  cmp     [rbp+Type], 4
0x18009d14d  jz      short loc_18009D156
0x18009d14f  mov     [rbp+Data], 1
0x18009d156  mov     rcx, [rbp+hKey]; hKey
0x18009d15a  call    cs:__imp_RegCloseKey
0x18009d160  xor     eax, eax
0x18009d162  cmp     [rbp+Data], eax
0x18009d165  setnz   al
0x18009d168  mov     [rbx], eax
0x18009d16a  mov     eax, cs:dword_180128170
0x18009d170  cmp     eax, 5
0x18009d173  jbe     short loc_18009D1BE
0x18009d175  mov     eax, [rbx]
0x18009d177  lea     rdx, dword_180113AF4
0x18009d17e  mov     [rbp+Type], eax
0x18009d181  mov     eax, [rbp+Data]
0x18009d184  mov     [rbp+arg_18], eax
0x18009d187  lea     rax, aRegistryread; "RegistryRead"
0x18009d18e  mov     [rbp+var_8], rax
0x18009d192  lea     rax, [rbp+Type]
0x18009d196  mov     [rsp+50h+var_18], rax
0x18009d19b  lea     rax, [rbp+cbData]
0x18009d19f  mov     [rsp+50h+var_20], rax
0x18009d1a4  lea     rax, [rbp+arg_18]
0x18009d1a8  mov     [rsp+50h+lpcbData], rax
0x18009d1ad  lea     rax, [rbp+var_8]
0x18009d1b1  mov     [rsp+50h+phkResult], rax
0x18009d1b6  mov     [rbp+cbData], edi
0x18009d1b9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009d1be  xor     eax, eax
0x18009d1c0  add     rsp, 50h
0x18009d1c4  pop     rdi
0x18009d1c5  pop     rbx
0x18009d1c6  pop     rbp
0x18009d1c7  retn
```
