# IsWallpaperDisabledByTerminalServerClient

- ea: `0x18004f80c`
- end: `0x18004f8d9`
- name: `IsWallpaperDisabledByTerminalServerClient`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180044280`

## callees

- `0x180002280`
- `0x180008110`
- `0x18004f80c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004f855`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004f855`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f842`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f842`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f8aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f8aa`
- `USER32!GetSystemMetrics` at `0x18004f82e`
- `USER32!GetSystemMetrics` at `0x18004f82e`

## pseudocode

```c
__int64 IsWallpaperDisabledByTerminalServerClient()
{
  unsigned int v0; // ebx
  DWORD CurrentProcessId; // eax
  DWORD pSessionId[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF

  v0 = 0;
  if ( GetSystemMetrics(4096) )
  {
    pSessionId[0] = 0;
    CurrentProcessId = GetCurrentProcessId();
    if ( ProcessIdToSessionId(CurrentProcessId, pSessionId) )
    {
      if ( (int)StringCchPrintfW(SubKey, 0x104u, L"Remote\\%d\\Control Panel\\Desktop", pSessionId[0]) >= 0 )
        return RegGetValueW(HKEY_CURRENT_USER, SubKey, L"Wallpaper", 2u, 0, 0, 0) == 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18004f80c  push    rbx
0x18004f80e  sub     rsp, 270h
0x18004f815  mov     rax, cs:__security_cookie
0x18004f81c  xor     rax, rsp
0x18004f81f  mov     [rsp+278h+var_18], rax
0x18004f827  mov     ecx, 1000h; nIndex
0x18004f82c  xor     ebx, ebx
0x18004f82e  call    cs:__imp_GetSystemMetrics
0x18004f835  nop     dword ptr [rax+rax+00h]
0x18004f83a  test    eax, eax
0x18004f83c  jz      short loc_18004F8BD
0x18004f83e  mov     [rsp+278h+pSessionId], ebx
0x18004f842  call    cs:__imp_GetCurrentProcessId
0x18004f849  nop     dword ptr [rax+rax+00h]
0x18004f84e  mov     ecx, eax; dwProcessId
0x18004f850  lea     rdx, [rsp+278h+pSessionId]; pSessionId
0x18004f855  call    cs:__imp_ProcessIdToSessionId
0x18004f85c  nop     dword ptr [rax+rax+00h]
0x18004f861  test    eax, eax
0x18004f863  jz      short loc_18004F8BD
0x18004f865  mov     r9d, [rsp+278h+pSessionId]
0x18004f86a  lea     r8, aRemoteDControl; "Remote\\%d\\Control Panel\\Desktop"
0x18004f871  mov     edx, 104h; unsigned __int64
0x18004f876  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18004f87b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f880  test    eax, eax
0x18004f882  js      short loc_18004F8BD
0x18004f884  mov     [rsp+278h+pcbData], rbx; pcbData
0x18004f889  lea     r9d, [rbx+2]; dwFlags
0x18004f88d  mov     [rsp+278h+pvData], rbx; pvData
0x18004f892  lea     r8, aWallpaper; "Wallpaper"
0x18004f899  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18004f89e  mov     [rsp+278h+pdwType], rbx; pdwType
0x18004f8a3  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18004f8aa  call    cs:__imp_RegGetValueW
0x18004f8b1  nop     dword ptr [rax+rax+00h]
0x18004f8b6  test    eax, eax
0x18004f8b8  jnz     short loc_18004F8BD
0x18004f8ba  lea     ebx, [rax+1]
0x18004f8bd  mov     eax, ebx
0x18004f8bf  mov     rcx, [rsp+278h+var_18]
0x18004f8c7  xor     rcx, rsp; StackCookie
0x18004f8ca  call    __security_check_cookie
0x18004f8cf  add     rsp, 270h
0x18004f8d6  pop     rbx
0x18004f8d7  retn
```
