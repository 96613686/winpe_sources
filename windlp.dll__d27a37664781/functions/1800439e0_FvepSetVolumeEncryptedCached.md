# FvepSetVolumeEncryptedCached

- ea: `0x1800439e0`
- end: `0x180043b34`
- name: `FvepSetVolumeEncryptedCached`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800437d4`

## callees

- `0x180042fc8`
- `0x18004364c`
- `0x1800439e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043af3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043af3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043b01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043b01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180043a7c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180043ac2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180043a7c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180043ac2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043ae8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043ae8`

## string_xrefs

- `0x180043a97`: `Cache`

## pseudocode

```c
int __fastcall FvepSetVolumeEncryptedCached(__int64 a1, int a2)
{
  int result; // eax
  WCHAR *v4; // rbx
  HANDLE ProcessHeap; // rax
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+28h] BYREF
  LPCWSTR lpValueName; // [rsp+88h] [rbp+30h] BYREF

  hKey = 0;
  phkResult = 0;
  lpValueName = 0;
  result = a2 != 0;
  Data = result;
  if ( a1 )
  {
    result = FvepIsNonDriverEncryptionStatusCachingAllowed();
    if ( result )
    {
      result = FvepConvertVolumeNameToCacheValueName(a1, &lpValueName);
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
0x1800439e0  push    rbp
0x1800439e2  push    rbx
0x1800439e3  mov     rbp, rsp
0x1800439e6  sub     rsp, 58h
0x1800439ea  xor     eax, eax
0x1800439ec  mov     [rbp+hKey], 0
0x1800439f4  test    edx, edx
0x1800439f6  mov     [rbp+arg_0], 0
0x1800439fe  mov     rbx, rcx
0x180043a01  mov     [rbp+lpValueName], 0
0x180043a09  setnz   al
0x180043a0c  mov     [rbp+Data], eax
0x180043a0f  test    rcx, rcx
0x180043a12  jz      loc_180043B2D
0x180043a18  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x180043a1d  test    eax, eax
0x180043a1f  jz      loc_180043B07
0x180043a25  lea     rdx, [rbp+lpValueName]
0x180043a29  mov     rcx, rbx
0x180043a2c  call    FvepConvertVolumeNameToCacheValueName
0x180043a31  mov     rbx, [rbp+lpValueName]
0x180043a35  test    eax, eax
0x180043a37  js      loc_180043AEE
0x180043a3d  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180043a46  lea     rax, [rbp+hKey]
0x180043a4a  mov     [rsp+58h+phkResult], rax; phkResult
0x180043a4f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180043a56  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180043a5f  xor     r9d, r9d; lpClass
0x180043a62  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180043a6a  xor     r8d, r8d; Reserved
0x180043a6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043a74  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180043a7c  call    cs:__imp_RegCreateKeyExW
0x180043a82  test    eax, eax
0x180043a84  jnz     short loc_180043AEE
0x180043a86  mov     rcx, [rbp+hKey]; hKey
0x180043a8a  lea     rax, [rbp+arg_0]
0x180043a8e  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180043a97  lea     rdx, aCache; "Cache"
0x180043a9e  mov     [rsp+58h+phkResult], rax; phkResult
0x180043aa3  xor     r9d, r9d; lpClass
0x180043aa6  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180043aaf  xor     r8d, r8d; Reserved
0x180043ab2  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180043aba  mov     [rsp+58h+dwOptions], 1; dwOptions
0x180043ac2  call    cs:__imp_RegCreateKeyExW
0x180043ac8  test    eax, eax
0x180043aca  jnz     short loc_180043AEE
0x180043acc  mov     rcx, [rbp+arg_0]; hKey
0x180043ad0  lea     r9d, [rax+4]; dwType
0x180043ad4  lea     rax, [rbp+Data]
0x180043ad8  mov     [rsp+58h+samDesired], r9d; cbData
0x180043add  xor     r8d, r8d; Reserved
0x180043ae0  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180043ae5  mov     rdx, rbx; lpValueName
0x180043ae8  call    cs:__imp_RegSetValueExW
0x180043aee  test    rbx, rbx
0x180043af1  jz      short loc_180043B07
0x180043af3  call    cs:__imp_GetProcessHeap
0x180043af9  mov     r8, rbx; lpMem
0x180043afc  xor     edx, edx; dwFlags
0x180043afe  mov     rcx, rax; hHeap
0x180043b01  call    cs:__imp_HeapFree
0x180043b07  mov     rcx, [rbp+arg_0]; hKey
0x180043b0b  test    rcx, rcx
0x180043b0e  jz      short loc_180043B1E
0x180043b10  call    cs:__imp_RegCloseKey
0x180043b16  mov     [rbp+arg_0], 0
0x180043b1e  mov     rcx, [rbp+hKey]; hKey
0x180043b22  test    rcx, rcx
0x180043b25  jz      short loc_180043B2D
0x180043b27  call    cs:__imp_RegCloseKey
0x180043b2d  add     rsp, 58h
0x180043b31  pop     rbx
0x180043b32  pop     rbp
0x180043b33  retn
```
