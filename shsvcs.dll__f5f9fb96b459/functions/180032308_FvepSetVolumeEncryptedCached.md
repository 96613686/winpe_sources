# FvepSetVolumeEncryptedCached

- ea: `0x180032308`
- end: `0x18003245c`
- name: `FvepSetVolumeEncryptedCached`
- size: `340`
- prototype: `int __fastcall(STRSAFE_PCNZWCH pszSrc, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800320fc`

## callees

- `0x18003196c`
- `0x180031f74`
- `0x180032308`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003241b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003241b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032429`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032410`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032410`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032438`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003244f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032438`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003244f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800323a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800323ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800323a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800323ea`

## string_xrefs

- `0x1800323bf`: `Cache`

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
0x180032308  push    rbp
0x18003230a  push    rbx
0x18003230b  mov     rbp, rsp
0x18003230e  sub     rsp, 58h
0x180032312  xor     eax, eax
0x180032314  mov     [rbp+hKey], 0
0x18003231c  test    edx, edx
0x18003231e  mov     [rbp+arg_0], 0
0x180032326  mov     rbx, rcx
0x180032329  mov     [rbp+lpValueName], 0
0x180032331  setnz   al
0x180032334  mov     [rbp+Data], eax
0x180032337  test    rcx, rcx
0x18003233a  jz      loc_180032455
0x180032340  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x180032345  test    eax, eax
0x180032347  jz      loc_18003242F
0x18003234d  lea     rdx, [rbp+lpValueName]
0x180032351  mov     rcx, rbx; pszSrc
0x180032354  call    FvepConvertVolumeNameToCacheValueName
0x180032359  mov     rbx, [rbp+lpValueName]
0x18003235d  test    eax, eax
0x18003235f  js      loc_180032416
0x180032365  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18003236e  lea     rax, [rbp+hKey]
0x180032372  mov     [rsp+58h+phkResult], rax; phkResult
0x180032377  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003237e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180032387  xor     r9d, r9d; lpClass
0x18003238a  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180032392  xor     r8d, r8d; Reserved
0x180032395  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003239c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800323a4  call    cs:__imp_RegCreateKeyExW
0x1800323aa  test    eax, eax
0x1800323ac  jnz     short loc_180032416
0x1800323ae  mov     rcx, [rbp+hKey]; hKey
0x1800323b2  lea     rax, [rbp+arg_0]
0x1800323b6  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800323bf  lea     rdx, aCache; "Cache"
0x1800323c6  mov     [rsp+58h+phkResult], rax; phkResult
0x1800323cb  xor     r9d, r9d; lpClass
0x1800323ce  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800323d7  xor     r8d, r8d; Reserved
0x1800323da  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800323e2  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1800323ea  call    cs:__imp_RegCreateKeyExW
0x1800323f0  test    eax, eax
0x1800323f2  jnz     short loc_180032416
0x1800323f4  mov     rcx, [rbp+arg_0]; hKey
0x1800323f8  lea     r9d, [rax+4]; dwType
0x1800323fc  lea     rax, [rbp+Data]
0x180032400  mov     [rsp+58h+samDesired], r9d; cbData
0x180032405  xor     r8d, r8d; Reserved
0x180032408  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18003240d  mov     rdx, rbx; lpValueName
0x180032410  call    cs:__imp_RegSetValueExW
0x180032416  test    rbx, rbx
0x180032419  jz      short loc_18003242F
0x18003241b  call    cs:__imp_GetProcessHeap
0x180032421  mov     r8, rbx; lpMem
0x180032424  xor     edx, edx; dwFlags
0x180032426  mov     rcx, rax; hHeap
0x180032429  call    cs:__imp_HeapFree
0x18003242f  mov     rcx, [rbp+arg_0]; hKey
0x180032433  test    rcx, rcx
0x180032436  jz      short loc_180032446
0x180032438  call    cs:__imp_RegCloseKey
0x18003243e  mov     [rbp+arg_0], 0
0x180032446  mov     rcx, [rbp+hKey]; hKey
0x18003244a  test    rcx, rcx
0x18003244d  jz      short loc_180032455
0x18003244f  call    cs:__imp_RegCloseKey
0x180032455  add     rsp, 58h
0x180032459  pop     rbx
0x18003245a  pop     rbp
0x18003245b  retn
```
