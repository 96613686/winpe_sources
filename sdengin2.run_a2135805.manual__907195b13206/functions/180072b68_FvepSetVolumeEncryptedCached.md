# FvepSetVolumeEncryptedCached

- ea: `0x180072b68`
- end: `0x180072ce7`
- name: `FvepSetVolumeEncryptedCached`
- size: `383`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180072924`

## callees

- `0x1800720d4`
- `0x180072784`
- `0x180072b68`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180072c8d`
- `KERNEL32!GetProcessHeap` at `0x180072c8d`
- `KERNEL32!HeapFree` at `0x180072ca1`
- `KERNEL32!HeapFree` at `0x180072ca1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072c7c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180072c7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072cb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072cd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072cb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072cd3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072c04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072c50`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072c04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072c50`

## string_xrefs

- `0x180072c25`: `Cache`

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
0x180072b68  push    rbp
0x180072b6a  push    rbx
0x180072b6b  mov     rbp, rsp
0x180072b6e  sub     rsp, 58h
0x180072b72  xor     eax, eax
0x180072b74  mov     [rbp+hKey], 0
0x180072b7c  test    edx, edx
0x180072b7e  mov     [rbp+arg_0], 0
0x180072b86  mov     rbx, rcx
0x180072b89  mov     [rbp+lpValueName], 0
0x180072b91  setnz   al
0x180072b94  mov     [rbp+Data], eax
0x180072b97  test    rcx, rcx
0x180072b9a  jz      loc_180072CDF
0x180072ba0  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x180072ba5  test    eax, eax
0x180072ba7  jz      loc_180072CAD
0x180072bad  lea     rdx, [rbp+lpValueName]
0x180072bb1  mov     rcx, rbx; pszSrc
0x180072bb4  call    FvepConvertVolumeNameToCacheValueName
0x180072bb9  mov     rbx, [rbp+lpValueName]
0x180072bbd  test    eax, eax
0x180072bbf  js      loc_180072C88
0x180072bc5  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180072bce  lea     rax, [rbp+hKey]
0x180072bd2  mov     [rsp+58h+phkResult], rax; phkResult
0x180072bd7  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180072bde  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180072be7  xor     r9d, r9d; lpClass
0x180072bea  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180072bf2  xor     r8d, r8d; Reserved
0x180072bf5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072bfc  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180072c04  call    cs:__imp_RegCreateKeyExW
0x180072c0b  nop     dword ptr [rax+rax+00h]
0x180072c10  test    eax, eax
0x180072c12  jnz     short loc_180072C88
0x180072c14  mov     rcx, [rbp+hKey]; hKey
0x180072c18  lea     rax, [rbp+arg_0]
0x180072c1c  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180072c25  lea     rdx, aCache_0; "Cache"
0x180072c2c  mov     [rsp+58h+phkResult], rax; phkResult
0x180072c31  xor     r9d, r9d; lpClass
0x180072c34  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180072c3d  xor     r8d, r8d; Reserved
0x180072c40  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180072c48  mov     [rsp+58h+dwOptions], 1; dwOptions
0x180072c50  call    cs:__imp_RegCreateKeyExW
0x180072c57  nop     dword ptr [rax+rax+00h]
0x180072c5c  test    eax, eax
0x180072c5e  jnz     short loc_180072C88
0x180072c60  mov     rcx, [rbp+arg_0]; hKey
0x180072c64  lea     r9d, [rax+4]; dwType
0x180072c68  lea     rax, [rbp+Data]
0x180072c6c  mov     [rsp+58h+samDesired], r9d; cbData
0x180072c71  xor     r8d, r8d; Reserved
0x180072c74  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180072c79  mov     rdx, rbx; lpValueName
0x180072c7c  call    cs:__imp_RegSetValueExW
0x180072c83  nop     dword ptr [rax+rax+00h]
0x180072c88  test    rbx, rbx
0x180072c8b  jz      short loc_180072CAD
0x180072c8d  call    cs:__imp_GetProcessHeap
0x180072c94  nop     dword ptr [rax+rax+00h]
0x180072c99  mov     r8, rbx; lpMem
0x180072c9c  xor     edx, edx; dwFlags
0x180072c9e  mov     rcx, rax; hHeap
0x180072ca1  call    cs:__imp_HeapFree
0x180072ca8  nop     dword ptr [rax+rax+00h]
0x180072cad  mov     rcx, [rbp+arg_0]; hKey
0x180072cb1  test    rcx, rcx
0x180072cb4  jz      short loc_180072CCA
0x180072cb6  call    cs:__imp_RegCloseKey
0x180072cbd  nop     dword ptr [rax+rax+00h]
0x180072cc2  mov     [rbp+arg_0], 0
0x180072cca  mov     rcx, [rbp+hKey]; hKey
0x180072cce  test    rcx, rcx
0x180072cd1  jz      short loc_180072CDF
0x180072cd3  call    cs:__imp_RegCloseKey
0x180072cda  nop     dword ptr [rax+rax+00h]
0x180072cdf  add     rsp, 58h
0x180072ce3  pop     rbx
0x180072ce4  pop     rbp
0x180072ce5  retn
```
