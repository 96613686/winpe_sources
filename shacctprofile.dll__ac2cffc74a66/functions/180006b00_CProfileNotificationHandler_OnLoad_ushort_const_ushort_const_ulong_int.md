# CProfileNotificationHandler::OnLoad(ushort const *,ushort const *,ulong,int)

- ea: `0x180006b00`
- end: `0x180006bf0`
- name: `?OnLoad@CProfileNotificationHandler@@UEAAJPEBG0KH@Z`
- size: `240`
- prototype: `__int64 __fastcall(CProfileNotificationHandler *this, const unsigned __int16 *, const unsigned __int16 *, __int64, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006180`
- `0x180006b00`
- `0x180008f80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006be2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006be2`
- `SHELL32!SHGetKnownFolderPath` at `0x180006b6e`
- `SHELL32!SHGetKnownFolderPath` at `0x180006bb2`
- `SHELL32!SHGetKnownFolderPath` at `0x180006b6e`
- `SHELL32!SHGetKnownFolderPath` at `0x180006bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006bd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006bd8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006b25`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006b25`

## pseudocode

```c
__int64 __fastcall CProfileNotificationHandler::OnLoad(
        CProfileNotificationHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  PSID Sid; // [rsp+20h] [rbp-20h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-18h] BYREF
  PWSTR pObjectName; // [rsp+30h] [rbp-10h] BYREF

  if ( a5 )
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(a2, &Sid) )
    {
      if ( (int)CSIsUserInAdministratorGroup(Sid) >= 0 )
      {
        ppszPath = 0;
        if ( SHGetKnownFolderPath(&FOLDERID_PublicDesktop, 0, 0, &ppszPath) >= 0 )
        {
          AddRemoveDeleteAceOnFolder(ppszPath, Sid, 1);
          CoTaskMemFree(ppszPath);
        }
        pObjectName = 0;
        if ( SHGetKnownFolderPath(&FOLDERID_CommonStartMenu, 0, 0, &pObjectName) >= 0 )
        {
          AddRemoveDeleteAceOnFolder(pObjectName, Sid, 1);
          CoTaskMemFree(pObjectName);
        }
      }
      LocalFree(Sid);
    }
    else
    {
      GetLastError();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006b00  push    rbp
0x180006b02  mov     rbp, rsp
0x180006b05  sub     rsp, 40h
0x180006b09  cmp     [rbp+arg_20], 0
0x180006b0d  mov     rax, rdx
0x180006b10  jz      loc_180006BE8
0x180006b16  lea     rdx, [rbp+Sid]; Sid
0x180006b1a  mov     [rbp+Sid], 0
0x180006b22  mov     rcx, rax; StringSid
0x180006b25  call    cs:__imp_ConvertStringSidToSidW
0x180006b2b  test    eax, eax
0x180006b2d  jnz     short loc_180006B3A
0x180006b2f  call    cs:__imp_GetLastError
0x180006b35  jmp     loc_180006BE8
0x180006b3a  mov     rcx, [rbp+Sid]; pSid2
0x180006b3e  lea     rdx, [rbp+arg_20]
0x180006b42  mov     [rbp+arg_20], 0
0x180006b49  call    CSIsUserInAdministratorGroup
0x180006b4e  test    eax, eax
0x180006b50  js      loc_180006BDE
0x180006b56  lea     r9, [rbp+ppszPath]; ppszPath
0x180006b5a  mov     [rbp+ppszPath], 0
0x180006b62  xor     r8d, r8d; hToken
0x180006b65  lea     rcx, FOLDERID_PublicDesktop; rfid
0x180006b6c  xor     edx, edx; dwFlags
0x180006b6e  call    cs:__imp_SHGetKnownFolderPath
0x180006b74  test    eax, eax
0x180006b76  js      short loc_180006B9A
0x180006b78  mov     rdx, [rbp+Sid]; void *
0x180006b7c  xor     r8d, r8d
0x180006b7f  cmp     [rbp+arg_20], r8d
0x180006b83  mov     rcx, [rbp+ppszPath]; pObjectName
0x180006b87  setz    r8b; int
0x180006b8b  call    ?AddRemoveDeleteAceOnFolder@@YAJPEBGPEAXH@Z; AddRemoveDeleteAceOnFolder(ushort const *,void *,int)
0x180006b90  mov     rcx, [rbp+ppszPath]; pv
0x180006b94  call    cs:__imp_CoTaskMemFree
0x180006b9a  lea     r9, [rbp+pObjectName]; ppszPath
0x180006b9e  mov     [rbp+pObjectName], 0
0x180006ba6  xor     r8d, r8d; hToken
0x180006ba9  lea     rcx, FOLDERID_CommonStartMenu; rfid
0x180006bb0  xor     edx, edx; dwFlags
0x180006bb2  call    cs:__imp_SHGetKnownFolderPath
0x180006bb8  test    eax, eax
0x180006bba  js      short loc_180006BDE
0x180006bbc  mov     rdx, [rbp+Sid]; void *
0x180006bc0  xor     r8d, r8d
0x180006bc3  cmp     [rbp+arg_20], r8d
0x180006bc7  mov     rcx, [rbp+pObjectName]; pObjectName
0x180006bcb  setz    r8b; int
0x180006bcf  call    ?AddRemoveDeleteAceOnFolder@@YAJPEBGPEAXH@Z; AddRemoveDeleteAceOnFolder(ushort const *,void *,int)
0x180006bd4  mov     rcx, [rbp+pObjectName]; pv
0x180006bd8  call    cs:__imp_CoTaskMemFree
0x180006bde  mov     rcx, [rbp+Sid]; hMem
0x180006be2  call    cs:__imp_LocalFree
0x180006be8  xor     eax, eax
0x180006bea  add     rsp, 40h
0x180006bee  pop     rbp
0x180006bef  retn
```
