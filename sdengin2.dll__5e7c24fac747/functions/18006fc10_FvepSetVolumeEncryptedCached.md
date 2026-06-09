# FvepSetVolumeEncryptedCached

- ea: `0x18006fc10`
- end: `0x18006fd64`
- name: `FvepSetVolumeEncryptedCached`
- size: `340`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006fa04`

## callees

- `0x18006f274`
- `0x18006f87c`
- `0x18006fc10`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18006fd23`
- `KERNEL32!GetProcessHeap` at `0x18006fd23`
- `KERNEL32!HeapFree` at `0x18006fd31`
- `KERNEL32!HeapFree` at `0x18006fd31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006fd18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006fd18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fd40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fd57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fd40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fd57`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006fcac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006fcf2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006fcac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006fcf2`

## string_xrefs

- `0x18006fcc7`: `Cache`

## pseudocode

```c
int __fastcall FvepSetVolumeEncryptedCached(STRSAFE_PCNZWCH pszSrc, int a2)
{
  int result; // eax
  WCHAR *v4; // rbx
  HANDLE ProcessHeap; // rax
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+28h] BYREF
  LPCWSTR lpValueName; // [rsp+88h] [rbp+30h]

  hKey = 0;
  phkResult = 0;
  lpValueName = 0;
  result = a2 != 0;
  Data = result;
  if ( pszSrc )
  {
    result = FvepIsNonDriverEncryptionStatusCachingAllowed();
    if ( result )
    {
      result = FvepConvertVolumeNameToCacheValueName(pszSrc);
      v4 = (WCHAR *)lpValueName;
      if ( result >= 0 )
      {
        result = RegCreateKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FveDetect",
                   0,
                   0,
                   0,
                   0xF003Fu,
                   0,
                   &hKey,
                   0);
        if ( !result )
        {
          result = RegCreateKeyExW(hKey, L"Cache", 0, 0, 1u, 0xF003Fu, 0, &phkResult, 0);
          if ( !result )
            result = RegSetValueExW(phkResult, v4, 0, 4u, (const BYTE *)&Data, 4u);
        }
      }
      if ( v4 )
      {
        ProcessHeap = GetProcessHeap();
        result = HeapFree(ProcessHeap, 0, v4);
      }
    }
    if ( phkResult )
    {
      result = RegCloseKey(phkResult);
      phkResult = 0;
    }
    if ( hKey )
      return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18006fc10  push    rbp
0x18006fc12  push    rbx
0x18006fc13  mov     rbp, rsp
0x18006fc16  sub     rsp, 58h
0x18006fc1a  xor     eax, eax
0x18006fc1c  mov     [rbp+hKey], 0
0x18006fc24  test    edx, edx
0x18006fc26  mov     [rbp+arg_0], 0
0x18006fc2e  mov     rbx, rcx
0x18006fc31  mov     [rbp+lpValueName], 0
0x18006fc39  setnz   al
0x18006fc3c  mov     [rbp+Data], eax
0x18006fc3f  test    rcx, rcx
0x18006fc42  jz      loc_18006FD5D
0x18006fc48  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x18006fc4d  test    eax, eax
0x18006fc4f  jz      loc_18006FD37
0x18006fc55  lea     rdx, [rbp+lpValueName]
0x18006fc59  mov     rcx, rbx; pszSrc
0x18006fc5c  call    FvepConvertVolumeNameToCacheValueName
0x18006fc61  mov     rbx, [rbp+lpValueName]
0x18006fc65  test    eax, eax
0x18006fc67  js      loc_18006FD1E
0x18006fc6d  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18006fc76  lea     rax, [rbp+hKey]
0x18006fc7a  mov     [rsp+58h+phkResult], rax; phkResult
0x18006fc7f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18006fc86  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006fc8f  xor     r9d, r9d; lpClass
0x18006fc92  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18006fc9a  xor     r8d, r8d; Reserved
0x18006fc9d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006fca4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18006fcac  call    cs:__imp_RegCreateKeyExW
0x18006fcb2  test    eax, eax
0x18006fcb4  jnz     short loc_18006FD1E
0x18006fcb6  mov     rcx, [rbp+hKey]; hKey
0x18006fcba  lea     rax, [rbp+arg_0]
0x18006fcbe  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18006fcc7  lea     rdx, aCache_0; "Cache"
0x18006fcce  mov     [rsp+58h+phkResult], rax; phkResult
0x18006fcd3  xor     r9d, r9d; lpClass
0x18006fcd6  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006fcdf  xor     r8d, r8d; Reserved
0x18006fce2  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18006fcea  mov     [rsp+58h+dwOptions], 1; dwOptions
0x18006fcf2  call    cs:__imp_RegCreateKeyExW
0x18006fcf8  test    eax, eax
0x18006fcfa  jnz     short loc_18006FD1E
0x18006fcfc  mov     rcx, [rbp+arg_0]; hKey
0x18006fd00  lea     r9d, [rax+4]; dwType
0x18006fd04  lea     rax, [rbp+Data]
0x18006fd08  mov     [rsp+58h+samDesired], r9d; cbData
0x18006fd0d  xor     r8d, r8d; Reserved
0x18006fd10  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18006fd15  mov     rdx, rbx; lpValueName
0x18006fd18  call    cs:__imp_RegSetValueExW
0x18006fd1e  test    rbx, rbx
0x18006fd21  jz      short loc_18006FD37
0x18006fd23  call    cs:__imp_GetProcessHeap
0x18006fd29  mov     r8, rbx; lpMem
0x18006fd2c  xor     edx, edx; dwFlags
0x18006fd2e  mov     rcx, rax; hHeap
0x18006fd31  call    cs:__imp_HeapFree
0x18006fd37  mov     rcx, [rbp+arg_0]; hKey
0x18006fd3b  test    rcx, rcx
0x18006fd3e  jz      short loc_18006FD4E
0x18006fd40  call    cs:__imp_RegCloseKey
0x18006fd46  mov     [rbp+arg_0], 0
0x18006fd4e  mov     rcx, [rbp+hKey]; hKey
0x18006fd52  test    rcx, rcx
0x18006fd55  jz      short loc_18006FD5D
0x18006fd57  call    cs:__imp_RegCloseKey
0x18006fd5d  add     rsp, 58h
0x18006fd61  pop     rbx
0x18006fd62  pop     rbp
0x18006fd63  retn
```
