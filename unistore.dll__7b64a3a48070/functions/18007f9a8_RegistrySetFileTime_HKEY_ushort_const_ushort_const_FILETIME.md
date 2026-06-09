# RegistrySetFileTime(HKEY__ *,ushort const *,ushort const *,_FILETIME)

- ea: `0x18007f9a8`
- end: `0x18007fa62`
- name: `?RegistrySetFileTime@@YAJPEAUHKEY__@@PEBG1U_FILETIME@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18007df9c`

## callees

- `0x18001a6c4`
- `0x18007f9a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007fa35`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007fa35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007fa54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007fa54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007fa04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007fa04`

## pseudocode

```c
__int64 __fastcall RegistrySetFileTime(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _FILETIME a4)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  unsigned int v6; // ebx
  bool v7; // cc
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  struct _FILETIME Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", 0, 0, 0, 0x20006u, 0, phkResult, 0);
  v6 = Key;
  v7 = Key <= 0;
  if ( !Key )
  {
    Key = RegSetValueExW(hKey, L"Refreshed", 0, 0xBu, (const BYTE *)&Data, 8u);
    v6 = Key;
    v7 = Key <= 0;
  }
  if ( !v7 )
    v6 = (unsigned __int16)Key | 0x80070000;
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18007f9a8  mov     rax, rsp
0x18007f9ab  mov     [rax+20h], r9
0x18007f9af  mov     [rax+18h], r8
0x18007f9b3  push    rbx
0x18007f9b4  sub     rsp, 50h
0x18007f9b8  lea     rcx, [rax+18h]
0x18007f9bc  mov     qword ptr [rax+18h], 0
0x18007f9c4  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18007f9c9  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18007f9d2  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x18007f9d9  mov     [rsp+58h+phkResult], rax; phkResult
0x18007f9de  xor     r9d, r9d; lpClass
0x18007f9e1  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007f9ea  xor     r8d, r8d; Reserved
0x18007f9ed  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18007f9f5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007f9fc  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18007fa04  call    cs:__imp_RegCreateKeyExW
0x18007fa0a  mov     ebx, eax
0x18007fa0c  test    eax, eax
0x18007fa0e  jnz     short loc_18007FA3F
0x18007fa10  mov     rcx, [rsp+58h+hKey]; hKey
0x18007fa15  lea     rax, [rsp+58h+Data]
0x18007fa1a  mov     [rsp+58h+samDesired], 8; cbData
0x18007fa22  lea     r9d, [rbx+0Bh]; dwType
0x18007fa26  xor     r8d, r8d; Reserved
0x18007fa29  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007fa2e  lea     rdx, ?c_wszUnistoreRegistryStoreRefreshed@@3QBGB; "Refreshed"
0x18007fa35  call    cs:__imp_RegSetValueExW
0x18007fa3b  mov     ebx, eax
0x18007fa3d  test    eax, eax
0x18007fa3f  jle     short loc_18007FA4A
0x18007fa41  movzx   ebx, ax
0x18007fa44  or      ebx, 80070000h
0x18007fa4a  mov     rcx, [rsp+58h+hKey]; hKey
0x18007fa4f  test    rcx, rcx
0x18007fa52  jz      short loc_18007FA5A
0x18007fa54  call    cs:__imp_RegCloseKey
0x18007fa5a  mov     eax, ebx
0x18007fa5c  add     rsp, 50h
0x18007fa60  pop     rbx
0x18007fa61  retn
```
