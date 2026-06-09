# CUtils::GetAllowFastReconnect(int *)

- ea: `0x1800a14c8`
- end: `0x1800a15e3`
- name: `?GetAllowFastReconnect@CUtils@@SAJPEAH@Z`
- size: `283`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004d4d0`

## callees

- `0x180005964`
- `0x1800a14c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a154b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a154b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a156e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a156e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a150b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a150b`

## string_xrefs

- `0x1800a15a1`: `RegistryRead`

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
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    Type = *a1;
    v12 = Data;
    v8 = "RegistryRead";
    cbData = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)&dword_180119B74,
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
0x1800a14c8  push    rbp
0x1800a14ca  push    rbx
0x1800a14cb  push    rdi
0x1800a14cc  mov     rbp, rsp
0x1800a14cf  sub     rsp, 50h
0x1800a14d3  mov     rbx, rcx
0x1800a14d6  mov     dword ptr [rcx], 1
0x1800a14dc  lea     rax, [rbp+hKey]
0x1800a14e0  mov     [rbp+hKey], 0
0x1800a14e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a14ef  mov     [rsp+50h+phkResult], rax; phkResult
0x1800a14f4  mov     r9d, 20019h; samDesired
0x1800a14fa  mov     [rbp+Data], 1
0x1800a1501  xor     r8d, r8d; ulOptions
0x1800a1504  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800a150b  call    cs:__imp_RegOpenKeyExW
0x1800a1512  nop     dword ptr [rax+rax+00h]
0x1800a1517  mov     edi, eax
0x1800a1519  test    eax, eax
0x1800a151b  jnz     short loc_1800A157A
0x1800a151d  mov     rcx, [rbp+hKey]; hKey
0x1800a1521  lea     r9, [rbp+Type]; lpType
0x1800a1525  mov     [rbp+Type], eax
0x1800a1528  lea     rdx, aBallowfastreco; "bAllowFastReconnect"
0x1800a152f  lea     rax, [rbp+cbData]
0x1800a1533  mov     [rbp+cbData], 4
0x1800a153a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800a153f  xor     r8d, r8d; lpReserved
0x1800a1542  lea     rax, [rbp+Data]
0x1800a1546  mov     [rsp+50h+phkResult], rax; lpData
0x1800a154b  call    cs:__imp_RegQueryValueExW
0x1800a1552  nop     dword ptr [rax+rax+00h]
0x1800a1557  mov     edi, eax
0x1800a1559  test    eax, eax
0x1800a155b  jnz     short loc_1800A1563
0x1800a155d  cmp     [rbp+Type], 4
0x1800a1561  jz      short loc_1800A156A
0x1800a1563  mov     [rbp+Data], 1
0x1800a156a  mov     rcx, [rbp+hKey]; hKey
0x1800a156e  call    cs:__imp_RegCloseKey
0x1800a1575  nop     dword ptr [rax+rax+00h]
0x1800a157a  xor     eax, eax
0x1800a157c  cmp     [rbp+Data], eax
0x1800a157f  setnz   al
0x1800a1582  mov     [rbx], eax
0x1800a1584  mov     eax, cs:dword_18012E170
0x1800a158a  cmp     eax, 5
0x1800a158d  jbe     short loc_1800A15D8
0x1800a158f  mov     eax, [rbx]
0x1800a1591  lea     rdx, dword_180119B74
0x1800a1598  mov     [rbp+Type], eax
0x1800a159b  mov     eax, [rbp+Data]
0x1800a159e  mov     [rbp+arg_18], eax
0x1800a15a1  lea     rax, aRegistryread; "RegistryRead"
0x1800a15a8  mov     [rbp+var_8], rax
0x1800a15ac  lea     rax, [rbp+Type]
0x1800a15b0  mov     [rsp+50h+var_18], rax
0x1800a15b5  lea     rax, [rbp+cbData]
0x1800a15b9  mov     [rsp+50h+var_20], rax
0x1800a15be  lea     rax, [rbp+arg_18]
0x1800a15c2  mov     [rsp+50h+lpcbData], rax
0x1800a15c7  lea     rax, [rbp+var_8]
0x1800a15cb  mov     [rsp+50h+phkResult], rax
0x1800a15d0  mov     [rbp+cbData], edi
0x1800a15d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a15d8  xor     eax, eax
0x1800a15da  add     rsp, 50h
0x1800a15de  pop     rdi
0x1800a15df  pop     rbx
0x1800a15e0  pop     rbp
0x1800a15e1  retn
```
