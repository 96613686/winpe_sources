# FvepSetVolumeEncryptedCached

- ea: `0x180032d34`
- end: `0x180032e88`
- name: `FvepSetVolumeEncryptedCached`
- size: `340`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032b28`

## callees

- `0x180032398`
- `0x1800329a0`
- `0x180032d34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032dd0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032e16`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032dd0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032e16`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e3c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032e47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032e47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032e55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032e55`

## string_xrefs

- `0x180032deb`: `Cache`

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
0x180032d34  push    rbp
0x180032d36  push    rbx
0x180032d37  mov     rbp, rsp
0x180032d3a  sub     rsp, 58h
0x180032d3e  xor     eax, eax
0x180032d40  mov     [rbp+hKey], 0
0x180032d48  test    edx, edx
0x180032d4a  mov     [rbp+arg_0], 0
0x180032d52  mov     rbx, rcx
0x180032d55  mov     [rbp+lpValueName], 0
0x180032d5d  setnz   al
0x180032d60  mov     [rbp+Data], eax
0x180032d63  test    rcx, rcx
0x180032d66  jz      loc_180032E81
0x180032d6c  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x180032d71  test    eax, eax
0x180032d73  jz      loc_180032E5B
0x180032d79  lea     rdx, [rbp+lpValueName]
0x180032d7d  mov     rcx, rbx; pszSrc
0x180032d80  call    FvepConvertVolumeNameToCacheValueName
0x180032d85  mov     rbx, [rbp+lpValueName]
0x180032d89  test    eax, eax
0x180032d8b  js      loc_180032E42
0x180032d91  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180032d9a  lea     rax, [rbp+hKey]
0x180032d9e  mov     [rsp+58h+phkResult], rax; phkResult
0x180032da3  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180032daa  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180032db3  xor     r9d, r9d; lpClass
0x180032db6  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180032dbe  xor     r8d, r8d; Reserved
0x180032dc1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032dc8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180032dd0  call    cs:__imp_RegCreateKeyExW
0x180032dd6  test    eax, eax
0x180032dd8  jnz     short loc_180032E42
0x180032dda  mov     rcx, [rbp+hKey]; hKey
0x180032dde  lea     rax, [rbp+arg_0]
0x180032de2  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180032deb  lea     rdx, aCache; "Cache"
0x180032df2  mov     [rsp+58h+phkResult], rax; phkResult
0x180032df7  xor     r9d, r9d; lpClass
0x180032dfa  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180032e03  xor     r8d, r8d; Reserved
0x180032e06  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180032e0e  mov     [rsp+58h+dwOptions], 1; dwOptions
0x180032e16  call    cs:__imp_RegCreateKeyExW
0x180032e1c  test    eax, eax
0x180032e1e  jnz     short loc_180032E42
0x180032e20  mov     rcx, [rbp+arg_0]; hKey
0x180032e24  lea     r9d, [rax+4]; dwType
0x180032e28  lea     rax, [rbp+Data]
0x180032e2c  mov     [rsp+58h+samDesired], r9d; cbData
0x180032e31  xor     r8d, r8d; Reserved
0x180032e34  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180032e39  mov     rdx, rbx; lpValueName
0x180032e3c  call    cs:__imp_RegSetValueExW
0x180032e42  test    rbx, rbx
0x180032e45  jz      short loc_180032E5B
0x180032e47  call    cs:__imp_GetProcessHeap
0x180032e4d  mov     r8, rbx; lpMem
0x180032e50  xor     edx, edx; dwFlags
0x180032e52  mov     rcx, rax; hHeap
0x180032e55  call    cs:__imp_HeapFree
0x180032e5b  mov     rcx, [rbp+arg_0]; hKey
0x180032e5f  test    rcx, rcx
0x180032e62  jz      short loc_180032E72
0x180032e64  call    cs:__imp_RegCloseKey
0x180032e6a  mov     [rbp+arg_0], 0
0x180032e72  mov     rcx, [rbp+hKey]; hKey
0x180032e76  test    rcx, rcx
0x180032e79  jz      short loc_180032E81
0x180032e7b  call    cs:__imp_RegCloseKey
0x180032e81  add     rsp, 58h
0x180032e85  pop     rbx
0x180032e86  pop     rbp
0x180032e87  retn
```
