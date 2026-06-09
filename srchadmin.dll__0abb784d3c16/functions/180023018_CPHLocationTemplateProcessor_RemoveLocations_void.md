# CPHLocationTemplateProcessor::RemoveLocations(void)

- ea: `0x180023018`
- end: `0x180023096`
- name: `?RemoveLocations@CPHLocationTemplateProcessor@@QEAAXXZ`
- size: `126`
- prototype: `void __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800230a0`

## callees

- `0x180023018`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180023071`
- `SHLWAPI!PathFindFileNameW` at `0x180023071`
- `SHLWAPI!SHDeleteKeyW` at `0x18002307f`
- `SHLWAPI!SHDeleteKeyW` at `0x18002307f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180023034`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180023034`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023064`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023064`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002308a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002308a`

## pseudocode

```c
void __fastcall CPHLocationTemplateProcessor::RemoveLocations(const WCHAR *pszPath)
{
  __int64 v2; // rcx
  const WCHAR *FileNameW; // rax
  HKEY hkey; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)pszPath + 68);
  if ( v2 )
    DeleteFileW((LPCWSTR)(v2 + 540));
  hkey = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\Windows Search\\ProcessedSearchRoots",
          0,
          0x1000Bu,
          &hkey) )
  {
    FileNameW = PathFindFileNameW(pszPath);
    SHDeleteKeyW(hkey, FileNameW);
    RegCloseKey(hkey);
  }
}

```

## disassembly

```asm
0x180023018  push    rbx
0x18002301a  sub     rsp, 30h
0x18002301e  mov     rbx, rcx
0x180023021  mov     rcx, [rcx+220h]
0x180023028  test    rcx, rcx
0x18002302b  jz      short loc_18002303A
0x18002302d  add     rcx, 21Ch; lpFileName
0x180023034  call    cs:__imp_DeleteFileW
0x18002303a  lea     rax, [rsp+38h+hkey]
0x18002303f  mov     [rsp+38h+hkey], 0
0x180023048  mov     r9d, 1000Bh; samDesired
0x18002304e  mov     [rsp+38h+phkResult], rax; phkResult
0x180023053  xor     r8d, r8d; ulOptions
0x180023056  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows Search\\Pr"...
0x18002305d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180023064  call    cs:__imp_RegOpenKeyExW
0x18002306a  test    eax, eax
0x18002306c  jnz     short loc_180023090
0x18002306e  mov     rcx, rbx; pszPath
0x180023071  call    cs:__imp_PathFindFileNameW
0x180023077  mov     rcx, [rsp+38h+hkey]; hkey
0x18002307c  mov     rdx, rax; pszSubKey
0x18002307f  call    cs:__imp_SHDeleteKeyW
0x180023085  mov     rcx, [rsp+38h+hkey]; hKey
0x18002308a  call    cs:__imp_RegCloseKey
0x180023090  add     rsp, 30h
0x180023094  pop     rbx
0x180023095  retn
```
