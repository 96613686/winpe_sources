# GetSubscriptionFolderPath(ushort *,ulong)

- ea: `0x18001bc9c`
- end: `0x18001bda9`
- name: `?GetSubscriptionFolderPath@@YAHPEAGK@Z`
- size: `269`
- prototype: `__int64 __fastcall(PWSTR pszPathOut, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18001d420`

## callees

- `0x18001bc9c`
- `0x180027384`
- `0x180029280`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x18001bd5c`
- `KERNEL32!GetWindowsDirectoryW` at `0x18001bd5c`
- `SHLWAPI!SHRegGetValueW` at `0x18001bd48`
- `SHLWAPI!SHRegGetValueW` at `0x18001bd48`
- `ADVAPI32!RegCloseKey` at `0x18001bd7b`
- `ADVAPI32!RegCloseKey` at `0x18001bd7b`
- `ADVAPI32!RegCreateKeyExW` at `0x18001bd0e`
- `ADVAPI32!RegCreateKeyExW` at `0x18001bd0e`

## string_xrefs

- `0x18001bd27`: `Directory`

## pseudocode

```c
__int64 __fastcall GetSubscriptionFolderPath(PWSTR pszPathOut)
{
  unsigned int v1; // ebx
  size_t v3; // rdx
  ULONG dwOptions; // [rsp+20h] [rbp-268h]
  DWORD dwDisposition; // [rsp+50h] [rbp-238h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-234h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-230h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-228h] BYREF

  dwDisposition = 0;
  hkey = 0;
  v1 = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\windows\\CurrentVersion\\Internet Settings\\Subscription Folder",
          0,
          (LPWSTR)&Default,
          0,
          0x2001Fu,
          0,
          &hkey,
          &dwDisposition) )
  {
    pcbData = 520;
    if ( SHRegGetValueW(hkey, 0, L"Directory", 268435462, 0, pszPathOut, &pcbData) )
    {
      GetWindowsDirectoryW(Buffer, 0x104u);
      PathCchCombineEx(pszPathOut, v3, Buffer, L"Offline Web Pages", dwOptions);
    }
    RegCloseKey(hkey);
    return 1;
  }
  return v1;
}

```

## disassembly

```asm
0x18001bc9c  mov     [rsp+arg_8], rbx
0x18001bca1  push    rdi
0x18001bca2  sub     rsp, 280h
0x18001bca9  mov     rax, cs:__security_cookie
0x18001bcb0  xor     rax, rsp
0x18001bcb3  mov     [rsp+288h+var_18], rax
0x18001bcbb  lea     rax, [rsp+288h+dwDisposition]
0x18001bcc0  mov     [rsp+288h+dwDisposition], 0
0x18001bcc8  mov     [rsp+288h+lpdwDisposition], rax; lpdwDisposition
0x18001bccd  lea     r9, Default; lpClass
0x18001bcd4  lea     rax, [rsp+288h+hkey]
0x18001bcd9  mov     [rsp+288h+hkey], 0
0x18001bce2  mov     [rsp+288h+phkResult], rax; phkResult
0x18001bce7  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\windows\\CurrentVe"...
0x18001bcee  xor     ebx, ebx
0x18001bcf0  mov     rdi, rcx
0x18001bcf3  mov     [rsp+288h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18001bcf8  xor     r8d, r8d; Reserved
0x18001bcfb  mov     [rsp+288h+samDesired], 2001Fh; samDesired
0x18001bd03  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bd0a  mov     [rsp+288h+dwOptions], ebx; dwOptions
0x18001bd0e  call    cs:__imp_RegCreateKeyExW
0x18001bd14  test    eax, eax
0x18001bd16  jnz     short loc_18001BD86
0x18001bd18  mov     rcx, [rsp+288h+hkey]; hkey
0x18001bd1d  lea     rax, [rsp+288h+pcbData]
0x18001bd22  mov     [rsp+288h+lpSecurityAttributes], rax; pcbData
0x18001bd27  lea     r8, aDirectory; "Directory"
0x18001bd2e  mov     qword ptr [rsp+288h+samDesired], rdi; pvData
0x18001bd33  mov     r9d, 10000006h; srrfFlags
0x18001bd39  xor     edx, edx; pszSubKey
0x18001bd3b  mov     qword ptr [rsp+288h+dwOptions], rbx; dwFlags
0x18001bd40  mov     [rsp+288h+pcbData], 208h
0x18001bd48  call    cs:__imp_SHRegGetValueW
0x18001bd4e  test    eax, eax
0x18001bd50  jz      short loc_18001BD76
0x18001bd52  mov     edx, 104h; uSize
0x18001bd57  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x18001bd5c  call    cs:__imp_GetWindowsDirectoryW
0x18001bd62  lea     r9, aOfflineWebPage; "Offline Web Pages"
0x18001bd69  mov     rcx, rdi; pszPathOut
0x18001bd6c  lea     r8, [rsp+288h+Buffer]; pszPathIn
0x18001bd71  call    PathCchCombineEx
0x18001bd76  mov     rcx, [rsp+288h+hkey]; hKey
0x18001bd7b  call    cs:__imp_RegCloseKey
0x18001bd81  mov     ebx, 1
0x18001bd86  mov     eax, ebx
0x18001bd88  mov     rcx, [rsp+288h+var_18]
0x18001bd90  xor     rcx, rsp; StackCookie
0x18001bd93  call    __security_check_cookie
0x18001bd98  mov     rbx, [rsp+288h+arg_8]
0x18001bda0  add     rsp, 280h
0x18001bda7  pop     rdi
0x18001bda8  retn
```
