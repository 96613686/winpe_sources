# IsIndexerSupportedDriveType(ushort const *)

- ea: `0x180024714`
- end: `0x1800247ad`
- name: `?IsIndexerSupportedDriveType@@YAHPEBG@Z`
- size: `153`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180025270`
- `0x18002c980`

## callees

- `0x180005cc0`
- `0x180024714`

## import_xrefs

- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180024773`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180024773`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002474f`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180024784`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002474f`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180024784`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180024740`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180024740`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18002475c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18002475c`

## pseudocode

```c
__int64 __fastcall IsIndexerSupportedDriveType(const unsigned __int16 *a1)
{
  unsigned int v1; // edi
  UINT v2; // ebx
  UINT DriveTypeW; // eax
  const CHAR *v4; // rdx
  WCHAR szVolumePathName[264]; // [rsp+20h] [rbp-228h] BYREF

  v1 = 0;
  if ( GetVolumePathNameW(a1, szVolumePathName, 0x104u) )
  {
    v2 = SetErrorMode(0x8001u);
    DriveTypeW = GetDriveTypeW(szVolumePathName);
    if ( DriveTypeW == 3 || DriveTypeW == 2 && !SHWindowsPolicy(&POLID_DisableRemovableDriveIndexing, v4) )
      v1 = 1;
    SetErrorMode(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x180024714  mov     [rsp+arg_8], rbx
0x180024719  push    rdi
0x18002471a  sub     rsp, 240h
0x180024721  mov     rax, cs:__security_cookie
0x180024728  xor     rax, rsp
0x18002472b  mov     [rsp+248h+var_18], rax
0x180024733  mov     r8d, 104h; cchBufferLength
0x180024739  lea     rdx, [rsp+248h+szVolumePathName]; lpszVolumePathName
0x18002473e  xor     edi, edi
0x180024740  call    cs:__imp_GetVolumePathNameW
0x180024746  test    eax, eax
0x180024748  jz      short loc_18002478A
0x18002474a  mov     ecx, 8001h; uMode
0x18002474f  call    cs:__imp_SetErrorMode
0x180024755  lea     rcx, [rsp+248h+szVolumePathName]; lpRootPathName
0x18002475a  mov     ebx, eax
0x18002475c  call    cs:__imp_GetDriveTypeW
0x180024762  cmp     eax, 3
0x180024765  jz      short loc_18002477D
0x180024767  cmp     eax, 2
0x18002476a  jnz     short loc_180024782
0x18002476c  lea     rcx, POLID_DisableRemovableDriveIndexing; pszPath
0x180024773  call    cs:__imp_SHWindowsPolicy
0x180024779  test    eax, eax
0x18002477b  jnz     short loc_180024782
0x18002477d  mov     edi, 1
0x180024782  mov     ecx, ebx; uMode
0x180024784  call    cs:__imp_SetErrorMode
0x18002478a  mov     eax, edi
0x18002478c  mov     rcx, [rsp+248h+var_18]
0x180024794  xor     rcx, rsp; StackCookie
0x180024797  call    __security_check_cookie
0x18002479c  mov     rbx, [rsp+248h+arg_8]
0x1800247a4  add     rsp, 240h
0x1800247ab  pop     rdi
0x1800247ac  retn
```
