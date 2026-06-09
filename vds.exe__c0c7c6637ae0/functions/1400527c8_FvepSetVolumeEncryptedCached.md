# FvepSetVolumeEncryptedCached

- ea: `0x1400527c8`
- end: `0x14005291c`
- name: `FvepSetVolumeEncryptedCached`
- size: `340`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400525bc`

## callees

- `0x140051e2c`
- `0x140052434`
- `0x1400527c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400528db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400528db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400528e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400528e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400528f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005290f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400528f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005290f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400528d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400528d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140052864`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400528aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140052864`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400528aa`

## string_xrefs

- `0x14005287f`: `Cache`

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
0x1400527c8  push    rbp
0x1400527ca  push    rbx
0x1400527cb  mov     rbp, rsp
0x1400527ce  sub     rsp, 58h
0x1400527d2  xor     eax, eax
0x1400527d4  mov     [rbp+hKey], 0
0x1400527dc  test    edx, edx
0x1400527de  mov     [rbp+arg_0], 0
0x1400527e6  mov     rbx, rcx
0x1400527e9  mov     [rbp+lpValueName], 0
0x1400527f1  setnz   al
0x1400527f4  mov     [rbp+Data], eax
0x1400527f7  test    rcx, rcx
0x1400527fa  jz      loc_140052915
0x140052800  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x140052805  test    eax, eax
0x140052807  jz      loc_1400528EF
0x14005280d  lea     rdx, [rbp+lpValueName]
0x140052811  mov     rcx, rbx; pszSrc
0x140052814  call    FvepConvertVolumeNameToCacheValueName
0x140052819  mov     rbx, [rbp+lpValueName]
0x14005281d  test    eax, eax
0x14005281f  js      loc_1400528D6
0x140052825  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x14005282e  lea     rax, [rbp+hKey]
0x140052832  mov     [rsp+58h+phkResult], rax; phkResult
0x140052837  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14005283e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140052847  xor     r9d, r9d; lpClass
0x14005284a  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x140052852  xor     r8d, r8d; Reserved
0x140052855  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005285c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140052864  call    cs:__imp_RegCreateKeyExW
0x14005286a  test    eax, eax
0x14005286c  jnz     short loc_1400528D6
0x14005286e  mov     rcx, [rbp+hKey]; hKey
0x140052872  lea     rax, [rbp+arg_0]
0x140052876  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x14005287f  lea     rdx, aCache; "Cache"
0x140052886  mov     [rsp+58h+phkResult], rax; phkResult
0x14005288b  xor     r9d, r9d; lpClass
0x14005288e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140052897  xor     r8d, r8d; Reserved
0x14005289a  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1400528a2  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1400528aa  call    cs:__imp_RegCreateKeyExW
0x1400528b0  test    eax, eax
0x1400528b2  jnz     short loc_1400528D6
0x1400528b4  mov     rcx, [rbp+arg_0]; hKey
0x1400528b8  lea     r9d, [rax+4]; dwType
0x1400528bc  lea     rax, [rbp+Data]
0x1400528c0  mov     [rsp+58h+samDesired], r9d; cbData
0x1400528c5  xor     r8d, r8d; Reserved
0x1400528c8  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1400528cd  mov     rdx, rbx; lpValueName
0x1400528d0  call    cs:__imp_RegSetValueExW
0x1400528d6  test    rbx, rbx
0x1400528d9  jz      short loc_1400528EF
0x1400528db  call    cs:__imp_GetProcessHeap
0x1400528e1  mov     r8, rbx; lpMem
0x1400528e4  xor     edx, edx; dwFlags
0x1400528e6  mov     rcx, rax; hHeap
0x1400528e9  call    cs:__imp_HeapFree
0x1400528ef  mov     rcx, [rbp+arg_0]; hKey
0x1400528f3  test    rcx, rcx
0x1400528f6  jz      short loc_140052906
0x1400528f8  call    cs:__imp_RegCloseKey
0x1400528fe  mov     [rbp+arg_0], 0
0x140052906  mov     rcx, [rbp+hKey]; hKey
0x14005290a  test    rcx, rcx
0x14005290d  jz      short loc_140052915
0x14005290f  call    cs:__imp_RegCloseKey
0x140052915  add     rsp, 58h
0x140052919  pop     rbx
0x14005291a  pop     rbp
0x14005291b  retn
```
