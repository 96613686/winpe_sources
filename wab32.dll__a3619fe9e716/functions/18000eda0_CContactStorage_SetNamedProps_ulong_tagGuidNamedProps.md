# CContactStorage::SetNamedProps(ulong,_tagGuidNamedProps *)

- ea: `0x18000eda0`
- end: `0x18000eee7`
- name: `?SetNamedProps@CContactStorage@@UEAAJKPEAU_tagGuidNamedProps@@@Z`
- size: `327`
- prototype: `int(CContactStorage *__hidden this, unsigned int, struct _tagGuidNamedProps *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000eda0`
- `0x180033608`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000eed7`
- `ADVAPI32!RegCloseKey` at `0x18000eed7`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ee02`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ee02`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee21`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee32`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee21`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee32`
- `ADVAPI32!RegSetValueExW` at `0x18000ee7a`
- `ADVAPI32!RegSetValueExW` at `0x18000eea4`
- `ADVAPI32!RegSetValueExW` at `0x18000ee7a`
- `ADVAPI32!RegSetValueExW` at `0x18000eea4`
- `KERNEL32!LocalFree` at `0x18000eec8`
- `KERNEL32!LocalFree` at `0x18000eec8`

## pseudocode

```c
__int64 __fastcall CContactStorage::SetNamedProps(
        CContactStorage *this,
        unsigned int a2,
        struct _tagGuidNamedProps *a3)
{
  BYTE *v3; // rdi
  unsigned int v5; // ebx
  int v6; // eax
  BYTE *lpData; // [rsp+50h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+88h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  Data = a2;
  v3 = 0;
  lpData = 0;
  cbData = 0;
  hKey = 0;
  if ( a3 && a2 )
  {
    if ( RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\WAB", 0, 0, 0, 0x20006u, 0, &hKey, 0) )
    {
      v5 = -2147467259;
      goto LABEL_12;
    }
    RegDeleteValueW(hKey, L"NamedProps");
    RegDeleteValueW(hKey, L"NamedPropCount");
    v6 = SetNamedPropsToBuffer(Data, a3, &cbData, &lpData);
    v3 = lpData;
    if ( !v6 || RegSetValueExW(hKey, L"NamedProps", 0, 3u, lpData, cbData) )
      v5 = -2147467259;
    else
      v5 = RegSetValueExW(hKey, L"NamedPropCount", 0, 4u, (const BYTE *)&Data, 4u) != 0 ? 0x80004005 : 0;
  }
  else
  {
    v5 = -2147024809;
  }
  if ( v3 )
    LocalFree(v3);
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18000eda0  mov     [rsp-18h+Data], edx
0x18000eda4  push    rbp
0x18000eda5  push    rbx
0x18000eda6  push    rdi
0x18000eda7  mov     rbp, rsp
0x18000edaa  sub     rsp, 60h
0x18000edae  xor     edi, edi
0x18000edb0  mov     rbx, r8
0x18000edb3  mov     [rbp+lpData], rdi
0x18000edb7  mov     [rbp+cbData], edi
0x18000edba  mov     [rbp+hKey], rdi
0x18000edbe  test    r8, r8
0x18000edc1  jz      loc_18000EEBB
0x18000edc7  test    edx, edx
0x18000edc9  jz      loc_18000EEBB
0x18000edcf  mov     [rsp+60h+lpdwDisposition], rdi; lpdwDisposition
0x18000edd4  lea     rax, [rbp+hKey]
0x18000edd8  mov     [rsp+60h+phkResult], rax; phkResult
0x18000eddd  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\WAB"
0x18000ede4  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000ede9  xor     r9d, r9d; lpClass
0x18000edec  mov     [rsp+60h+samDesired], 20006h; samDesired
0x18000edf4  xor     r8d, r8d; Reserved
0x18000edf7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000edfe  mov     [rsp+60h+dwOptions], edi; dwOptions
0x18000ee02  call    cs:__imp_RegCreateKeyExW
0x18000ee08  test    eax, eax
0x18000ee0a  jz      short loc_18000EE16
0x18000ee0c  mov     ebx, 80004005h
0x18000ee11  jmp     loc_18000EECE
0x18000ee16  mov     rcx, [rbp+hKey]; hKey
0x18000ee1a  lea     rdx, ValueName; "NamedProps"
0x18000ee21  call    cs:__imp_RegDeleteValueW
0x18000ee27  mov     rcx, [rbp+hKey]; hKey
0x18000ee2b  lea     rdx, Value; "NamedPropCount"
0x18000ee32  call    cs:__imp_RegDeleteValueW
0x18000ee38  mov     ecx, [rbp+Data]; unsigned int
0x18000ee3b  lea     r9, [rbp+lpData]; unsigned __int8 **
0x18000ee3f  lea     r8, [rbp+cbData]; unsigned int *
0x18000ee43  mov     rdx, rbx; struct _tagGuidNamedProps *
0x18000ee46  call    ?SetNamedPropsToBuffer@@YAHKPEAU_tagGuidNamedProps@@PEAKPEAPEAE@Z; SetNamedPropsToBuffer(ulong,_tagGuidNamedProps *,ulong *,uchar * *)
0x18000ee4b  mov     rdi, [rbp+lpData]
0x18000ee4f  test    eax, eax
0x18000ee51  jnz     short loc_18000EE5A
0x18000ee53  mov     ebx, 80004005h
0x18000ee58  jmp     short loc_18000EEC0
0x18000ee5a  mov     eax, [rbp+cbData]
0x18000ee5d  lea     rdx, ValueName; "NamedProps"
0x18000ee64  mov     rcx, [rbp+hKey]; hKey
0x18000ee68  mov     r9d, 3; dwType
0x18000ee6e  mov     [rsp+60h+samDesired], eax; cbData
0x18000ee72  xor     r8d, r8d; Reserved
0x18000ee75  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x18000ee7a  call    cs:__imp_RegSetValueExW
0x18000ee80  test    eax, eax
0x18000ee82  jnz     short loc_18000EE53
0x18000ee84  mov     rcx, [rbp+hKey]; hKey
0x18000ee88  lea     r9d, [rax+4]; dwType
0x18000ee8c  lea     rax, [rbp+Data]
0x18000ee90  mov     [rsp+60h+samDesired], r9d; cbData
0x18000ee95  xor     r8d, r8d; Reserved
0x18000ee98  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18000ee9d  lea     rdx, Value; "NamedPropCount"
0x18000eea4  call    cs:__imp_RegSetValueExW
0x18000eeaa  xor     ecx, ecx
0x18000eeac  mov     ebx, 80004005h
0x18000eeb1  sub     ecx, eax
0x18000eeb3  neg     ecx
0x18000eeb5  sbb     eax, eax
0x18000eeb7  and     ebx, eax
0x18000eeb9  jmp     short loc_18000EEC0
0x18000eebb  mov     ebx, 80070057h
0x18000eec0  test    rdi, rdi
0x18000eec3  jz      short loc_18000EECE
0x18000eec5  mov     rcx, rdi; hMem
0x18000eec8  call    cs:__imp_LocalFree
0x18000eece  mov     rcx, [rbp+hKey]; hKey
0x18000eed2  test    rcx, rcx
0x18000eed5  jz      short loc_18000EEDD
0x18000eed7  call    cs:__imp_RegCloseKey
0x18000eedd  mov     eax, ebx
0x18000eedf  add     rsp, 60h
0x18000eee3  pop     rdi
0x18000eee4  pop     rbx
0x18000eee5  pop     rbp
0x18000eee6  retn
```
