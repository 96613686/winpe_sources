# CMSSAdmin::DropCatalog(INDEXER_REBUILD_REASON)

- ea: `0x1800044e0`
- end: `0x18000457c`
- name: `?DropCatalog@CMSSAdmin@@QEAAJW4INDEXER_REBUILD_REASON@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aab0`
- `0x1800134b0`

## callees

- `0x1800044e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004554`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004554`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004517`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004517`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000456e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000456e`

## pseudocode

```c
__int64 __fastcall CMSSAdmin::DropCatalog(__int64 a1, int a2)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", 0, 0x40000000u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    v4 = RegSetValueExW(hKey, L"RebuildIndex", 0, 4u, (const BYTE *)&Data, 4u);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    RegCloseKey(hKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800044e0  mov     rax, rsp
0x1800044e3  mov     [rax+10h], edx
0x1800044e6  mov     [rax+8], rcx
0x1800044ea  push    rbx
0x1800044eb  sub     rsp, 30h
0x1800044ef  mov     qword ptr [rax+8], 0
0x1800044f7  lea     rax, [rax+8]
0x1800044fb  mov     r9d, 40000000h; samDesired
0x180004501  mov     [rsp+38h+phkResult], rax; phkResult
0x180004506  xor     r8d, r8d; ulOptions
0x180004509  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Search"
0x180004510  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004517  call    cs:__imp_RegOpenKeyExW
0x18000451d  mov     ebx, eax
0x18000451f  test    eax, eax
0x180004521  jle     short loc_18000452C
0x180004523  movzx   ebx, ax
0x180004526  or      ebx, 80070000h
0x18000452c  test    ebx, ebx
0x18000452e  js      short loc_180004574
0x180004530  mov     rcx, [rsp+38h+hKey]; hKey
0x180004535  lea     rax, [rsp+38h+Data]
0x18000453a  mov     r9d, 4; dwType
0x180004540  lea     rdx, aRebuildindex; "RebuildIndex"
0x180004547  mov     [rsp+38h+cbData], r9d; cbData
0x18000454c  xor     r8d, r8d; Reserved
0x18000454f  mov     [rsp+38h+phkResult], rax; lpData
0x180004554  call    cs:__imp_RegSetValueExW
0x18000455a  mov     ebx, eax
0x18000455c  test    eax, eax
0x18000455e  jle     short loc_180004569
0x180004560  movzx   ebx, ax
0x180004563  or      ebx, 80070000h
0x180004569  mov     rcx, [rsp+38h+hKey]; hKey
0x18000456e  call    cs:__imp_RegCloseKey
0x180004574  mov     eax, ebx
0x180004576  add     rsp, 30h
0x18000457a  pop     rbx
0x18000457b  retn
```
