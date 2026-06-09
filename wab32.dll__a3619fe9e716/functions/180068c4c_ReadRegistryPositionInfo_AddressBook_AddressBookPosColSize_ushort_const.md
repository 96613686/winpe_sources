# ReadRegistryPositionInfo(AddressBook *,_AddressBookPosColSize *,ushort const *)

- ea: `0x180068c4c`
- end: `0x180068d4d`
- name: `?ReadRegistryPositionInfo@@YAHPEAVAddressBook@@PEAU_AddressBookPosColSize@@PEBG@Z`
- size: `257`
- prototype: `int(struct AddressBook *, struct _AddressBookPosColSize *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ff70`

## callees

- `0x180068c4c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180068d1d`
- `ADVAPI32!RegCloseKey` at `0x180068d3a`
- `ADVAPI32!RegCloseKey` at `0x180068d1d`
- `ADVAPI32!RegCloseKey` at `0x180068d3a`
- `ADVAPI32!RegCreateKeyExW` at `0x180068cc7`
- `ADVAPI32!RegCreateKeyExW` at `0x180068cc7`
- `ADVAPI32!RegQueryValueExW` at `0x180068cfe`
- `ADVAPI32!RegQueryValueExW` at `0x180068cfe`

## pseudocode

```c
__int64 __fastcall ReadRegistryPositionInfo(struct AddressBook *a1, BYTE *a2, const unsigned __int16 *a3)
{
  unsigned int v3; // edi
  __int64 v5; // rbx
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF
  const unsigned __int16 *dwDisposition; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  dwDisposition = a3;
  v3 = 0;
  hKey = 0;
  if ( !a1 || (v5 = *((_QWORD *)a1 + 132)) == 0 )
    v5 = -2147483647;
  cbData = 0;
  LODWORD(dwDisposition) = 0;
  Type = 0;
  if ( a2 )
  {
    while ( !RegCreateKeyExW(
               (HKEY)v5,
               L"Software\\Microsoft\\WAB\\WAB Sort State",
               0,
               0,
               0,
               0x20019u,
               0,
               &hKey,
               (LPDWORD)&dwDisposition)
         && (_DWORD)dwDisposition != 1 )
    {
      cbData = 76;
      if ( !RegQueryValueExW(hKey, L"FindPosition", 0, &Type, a2, &cbData) )
      {
        v3 = 1;
        break;
      }
      if ( v5 == -2147483647 )
        break;
      v5 = -2147483647;
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x180068c4c  mov     [rsp-28h+dwDisposition], r8
0x180068c51  push    rbp
0x180068c52  push    rbx
0x180068c53  push    rsi
0x180068c54  push    rdi
0x180068c55  push    r15
0x180068c57  mov     rbp, rsp
0x180068c5a  sub     rsp, 50h
0x180068c5e  xor     edi, edi
0x180068c60  mov     rsi, rdx
0x180068c63  mov     [rbp+hKey], rdi
0x180068c67  mov     r15, 0FFFFFFFF80000001h
0x180068c6e  test    rcx, rcx
0x180068c71  jz      short loc_180068C7F
0x180068c73  mov     rbx, [rcx+420h]
0x180068c7a  test    rbx, rbx
0x180068c7d  jnz     short loc_180068C82
0x180068c7f  mov     rbx, r15
0x180068c82  mov     [rbp+cbData], edi
0x180068c85  mov     dword ptr [rbp+dwDisposition], edi
0x180068c88  mov     [rbp+Type], edi
0x180068c8b  test    rsi, rsi
0x180068c8e  jz      loc_180068D40
0x180068c94  lea     rax, [rbp+dwDisposition]
0x180068c98  xor     r9d, r9d; lpClass
0x180068c9b  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180068ca0  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WAB\\WAB Sort Stat"...
0x180068ca7  lea     rax, [rbp+hKey]
0x180068cab  xor     r8d, r8d; Reserved
0x180068cae  mov     [rsp+50h+phkResult], rax; phkResult
0x180068cb3  mov     rcx, rbx; hKey
0x180068cb6  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180068cbb  mov     [rsp+50h+samDesired], 20019h; samDesired
0x180068cc3  mov     [rsp+50h+dwOptions], edi; dwOptions
0x180068cc7  call    cs:__imp_RegCreateKeyExW
0x180068ccd  test    eax, eax
0x180068ccf  jnz     short loc_180068D31
0x180068cd1  cmp     dword ptr [rbp+dwDisposition], 1
0x180068cd5  jz      short loc_180068D31
0x180068cd7  mov     rcx, [rbp+hKey]; hKey
0x180068cdb  lea     rax, [rbp+cbData]
0x180068cdf  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x180068ce4  lea     r9, [rbp+Type]; lpType
0x180068ce8  xor     r8d, r8d; lpReserved
0x180068ceb  mov     qword ptr [rsp+50h+dwOptions], rsi; lpData
0x180068cf0  lea     rdx, aFindposition; "FindPosition"
0x180068cf7  mov     [rbp+cbData], 4Ch ; 'L'
0x180068cfe  call    cs:__imp_RegQueryValueExW
0x180068d04  test    eax, eax
0x180068d06  jz      short loc_180068D2C
0x180068d08  cmp     rbx, r15
0x180068d0b  jz      short loc_180068D31
0x180068d0d  mov     rcx, [rbp+hKey]; hKey
0x180068d11  mov     rbx, r15
0x180068d14  test    rcx, rcx
0x180068d17  jz      loc_180068C94
0x180068d1d  call    cs:__imp_RegCloseKey
0x180068d23  mov     [rbp+hKey], rdi
0x180068d27  jmp     loc_180068C94
0x180068d2c  mov     edi, 1
0x180068d31  mov     rcx, [rbp+hKey]; hKey
0x180068d35  test    rcx, rcx
0x180068d38  jz      short loc_180068D40
0x180068d3a  call    cs:__imp_RegCloseKey
0x180068d40  mov     eax, edi
0x180068d42  add     rsp, 50h
0x180068d46  pop     r15
0x180068d48  pop     rdi
0x180068d49  pop     rsi
0x180068d4a  pop     rbx
0x180068d4b  pop     rbp
0x180068d4c  retn
```
