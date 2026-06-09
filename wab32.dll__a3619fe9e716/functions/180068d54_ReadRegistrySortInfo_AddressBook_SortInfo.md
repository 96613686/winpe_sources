# ReadRegistrySortInfo(AddressBook *,_SortInfo *)

- ea: `0x180068d54`
- end: `0x180068e45`
- name: `?ReadRegistrySortInfo@@YAHPEAVAddressBook@@PEAU_SortInfo@@@Z`
- size: `241`
- prototype: `int(struct AddressBook *, struct _SortInfo *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800464e4`
- `0x18005ecd8`
- `0x180060850`

## callees

- `0x180068d54`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180068e35`
- `ADVAPI32!RegCloseKey` at `0x180068e35`
- `ADVAPI32!RegCreateKeyExW` at `0x180068de4`
- `ADVAPI32!RegCreateKeyExW` at `0x180068de4`
- `ADVAPI32!RegQueryValueExW` at `0x180068e1d`
- `ADVAPI32!RegQueryValueExW` at `0x180068e1d`

## pseudocode

```c
__int64 __fastcall ReadRegistrySortInfo(struct AddressBook *a1, struct _SortInfo *a2)
{
  unsigned int v2; // edi
  __int64 v4; // rcx
  DWORD dwDisposition; // [rsp+70h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+10h] BYREF
  DWORD Type; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  v2 = 0;
  hKey = 0;
  if ( !a1 || (v4 = *((_QWORD *)a1 + 132)) == 0 )
    v4 = -2147483647;
  cbData = 16;
  dwDisposition = 0;
  Type = 0;
  if ( a2 )
  {
    *((_DWORD *)a2 + 3) = bDNisByLN;
    *(_QWORD *)a2 = 0;
    *((_DWORD *)a2 + 2) = 1;
    if ( !RegCreateKeyExW(
            (HKEY)v4,
            L"Software\\Microsoft\\WAB\\WAB Sort State",
            0,
            0,
            0,
            0x20019u,
            0,
            &hKey,
            &dwDisposition)
      && dwDisposition != 1
      && !RegQueryValueExW(hKey, L"State", 0, &Type, (LPBYTE)a2, &cbData) )
    {
      v2 = 1;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180068d54  mov     rax, rsp
0x180068d57  push    rbx
0x180068d58  push    rbp
0x180068d59  push    rdi
0x180068d5a  sub     rsp, 50h
0x180068d5e  xor     edi, edi
0x180068d60  mov     rbx, rdx
0x180068d63  mov     [rax+20h], rdi
0x180068d67  test    rcx, rcx
0x180068d6a  jz      short loc_180068D78
0x180068d6c  mov     rcx, [rcx+420h]
0x180068d73  test    rcx, rcx
0x180068d76  jnz     short loc_180068D7F
0x180068d78  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180068d7f  mov     [rsp+68h+cbData], 10h
0x180068d87  mov     [rsp+68h+dwDisposition], edi
0x180068d8b  mov     [rsp+68h+Type], edi
0x180068d92  test    rbx, rbx
0x180068d95  jz      loc_180068E3B
0x180068d9b  mov     eax, cs:bDNisByLN
0x180068da1  mov     ebp, 1
0x180068da6  mov     [rdx+0Ch], eax
0x180068da9  xor     r9d, r9d; lpClass
0x180068dac  lea     rax, [rsp+68h+dwDisposition]
0x180068db1  mov     [rdx], rdi
0x180068db4  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180068db9  xor     r8d, r8d; Reserved
0x180068dbc  lea     rax, [rsp+68h+hKey]
0x180068dc4  mov     [rdx+8], ebp
0x180068dc7  mov     [rsp+68h+phkResult], rax; phkResult
0x180068dcc  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WAB\\WAB Sort Stat"...
0x180068dd3  mov     [rsp+68h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180068dd8  mov     [rsp+68h+samDesired], 20019h; samDesired
0x180068de0  mov     [rsp+68h+dwOptions], edi; dwOptions
0x180068de4  call    cs:__imp_RegCreateKeyExW
0x180068dea  test    eax, eax
0x180068dec  jnz     short loc_180068E28
0x180068dee  cmp     [rsp+68h+dwDisposition], ebp
0x180068df2  jz      short loc_180068E28
0x180068df4  mov     rcx, [rsp+68h+hKey]; hKey
0x180068dfc  lea     rax, [rsp+68h+cbData]
0x180068e01  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180068e06  lea     r9, [rsp+68h+Type]; lpType
0x180068e0e  xor     r8d, r8d; lpReserved
0x180068e11  mov     qword ptr [rsp+68h+dwOptions], rbx; lpData
0x180068e16  lea     rdx, aState; "State"
0x180068e1d  call    cs:__imp_RegQueryValueExW
0x180068e23  test    eax, eax
0x180068e25  cmovz   edi, ebp
0x180068e28  mov     rcx, [rsp+68h+hKey]; hKey
0x180068e30  test    rcx, rcx
0x180068e33  jz      short loc_180068E3B
0x180068e35  call    cs:__imp_RegCloseKey
0x180068e3b  mov     eax, edi
0x180068e3d  add     rsp, 50h
0x180068e41  pop     rdi
0x180068e42  pop     rbp
0x180068e43  pop     rbx
0x180068e44  retn
```
