# UmpopCacheRegistryPowerRequestOverride

- ea: `0x180016b40`
- end: `0x180016e1e`
- name: `UmpopCacheRegistryPowerRequestOverride`
- size: `734`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000c534`

## callees

- `0x180002214`
- `0x180016b40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180016cb3`
- `ntdll!RtlAllocateHeap` at `0x180016d17`
- `ntdll!RtlAllocateHeap` at `0x180016d9c`
- `ntdll!RtlAllocateHeap` at `0x180016cb3`
- `ntdll!RtlAllocateHeap` at `0x180016d17`
- `ntdll!RtlAllocateHeap` at `0x180016d9c`
- `ntdll!RtlFreeHeap` at `0x180016be0`
- `ntdll!RtlFreeHeap` at `0x180016ce1`
- `ntdll!RtlFreeHeap` at `0x180016cfc`
- `ntdll!RtlFreeHeap` at `0x180016be0`
- `ntdll!RtlFreeHeap` at `0x180016ce1`
- `ntdll!RtlFreeHeap` at `0x180016cfc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180016d67`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180016d67`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016c89`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016c89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016de6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016e02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016de6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016e02`

## string_xrefs

- `0x180016b97`: `Service`

## pseudocode

```c
__int64 __fastcall UmpopCacheRegistryPowerRequestOverride(int a1)
{
  int v1; // ecx
  unsigned int v2; // ebx
  const WCHAR *v3; // r14
  __int64 *v4; // rdi
  __int64 i; // rsi
  void *v6; // r8
  PVOID Heap; // r15
  _DWORD *v8; // rsi
  DWORD v9; // r14d
  wchar_t *v10; // rax
  DWORD cValues; // [rsp+60h] [rbp-9h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+7h] BYREF
  DWORD cchValueName; // [rsp+D0h] [rbp+67h] BYREF
  DWORD cbMaxValueLen; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD cbMaxValueNameLen; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+E8h] [rbp+7Fh] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cValues = 0;
  cbData = 0;
  cchValueName = 0;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( a1 )
  {
    v1 = a1 - 1;
    if ( v1 )
    {
      if ( v1 != 1 )
        return 87;
      v3 = L"Service";
      v4 = &UmpoServiceOverrideCacheArray;
    }
    else
    {
      v3 = L"Process";
      v4 = UmpoProcessOverrideCacheArray;
    }
  }
  else
  {
    v3 = L"Driver";
    v4 = UmpoDriverOverrideCacheArray;
  }
  for ( i = 0; i != 10; ++i )
  {
    v6 = (void *)v4[2 * i];
    if ( v6 )
    {
      RtlFreeHeap(UmpoHeapHandle, 0, v6);
      v4[2 * i] = 0;
      LODWORD(v4[2 * i + 1]) = 0;
    }
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Power\\PowerRequestOverride",
         0,
         1u,
         &hKey)
    || RegOpenKeyExW(hKey, v3, 0, 3u, &phkResult) )
  {
    v2 = 0;
    goto LABEL_34;
  }
  v2 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( !v2 )
  {
    cchValueName = 2 * cbMaxValueNameLen + 2;
    Heap = RtlAllocateHeap(UmpoHeapHandle, 8u, cchValueName);
    if ( !Heap )
    {
      v2 = 14;
      goto LABEL_34;
    }
    if ( cbMaxValueLen >= 4 )
    {
      v8 = RtlAllocateHeap(UmpoHeapHandle, 8u, cbMaxValueLen);
      if ( !v8 )
      {
LABEL_23:
        v2 = 14;
LABEL_20:
        RtlFreeHeap(UmpoHeapHandle, 0, Heap);
        if ( v8 )
          RtlFreeHeap(UmpoHeapHandle, 0, v8);
        goto LABEL_34;
      }
      v9 = 0;
      while ( !v2 )
      {
        cbData = cbMaxValueLen;
        cchValueName = cbMaxValueNameLen + 1;
        v2 = RegEnumValueW(phkResult, v9, (LPWSTR)Heap, &cchValueName, 0, 0, (LPBYTE)v8, &cbData);
        if ( !v2 && cbData == 4 )
        {
          if ( v9 >= 0xA )
            break;
          if ( *v8 )
          {
            v10 = (wchar_t *)RtlAllocateHeap(UmpoHeapHandle, 8u, 2LL * (cchValueName + 1));
            v4[2 * v9] = (__int64)v10;
            if ( !v10 )
              goto LABEL_23;
            StringCchCopyW(v10, cchValueName + 1, (STRSAFE_LPCWSTR)Heap);
            LODWORD(v4[2 * v9 + 1]) = *v8;
          }
        }
        ++v9;
      }
    }
    else
    {
      v8 = 0;
    }
    v2 = 0;
    goto LABEL_20;
  }
LABEL_34:
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180016b40  push    rbp
0x180016b42  push    rbx
0x180016b43  push    rsi
0x180016b44  push    rdi
0x180016b45  push    r12
0x180016b47  push    r13
0x180016b49  push    r14
0x180016b4b  push    r15
0x180016b4d  lea     rbp, [rsp-1Fh]
0x180016b52  sub     rsp, 88h
0x180016b59  xor     r13d, r13d
0x180016b5c  mov     [rbp+57h+hKey], 0FFFFFFFFFFFFFFFFh
0x180016b64  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x180016b68  mov     [rbp+57h+cbMaxValueLen], r13d
0x180016b6c  mov     [rbp+57h+cValues], r13d
0x180016b70  mov     [rbp+57h+cbData], r13d
0x180016b74  mov     [rbp+57h+cchValueName], r13d
0x180016b78  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x180016b80  test    ecx, ecx
0x180016b82  jz      short loc_180016BB7
0x180016b84  sub     ecx, 1
0x180016b87  jz      short loc_180016BA7
0x180016b89  cmp     ecx, 1
0x180016b8c  jz      short loc_180016B97
0x180016b8e  lea     ebx, [r13+57h]
0x180016b92  jmp     loc_180016E08
0x180016b97  lea     r14, aService_0; "Service"
0x180016b9e  lea     rdi, UmpoServiceOverrideCacheArray
0x180016ba5  jmp     short loc_180016BC5
0x180016ba7  lea     r14, aProcess; "Process"
0x180016bae  lea     rdi, UmpoProcessOverrideCacheArray
0x180016bb5  jmp     short loc_180016BC5
0x180016bb7  lea     r14, aDriver; "Driver"
0x180016bbe  lea     rdi, UmpoDriverOverrideCacheArray
0x180016bc5  mov     rsi, r13
0x180016bc8  mov     rbx, rsi
0x180016bcb  add     rbx, rbx
0x180016bce  mov     r8, [rdi+rbx*8]; P
0x180016bd2  test    r8, r8
0x180016bd5  jz      short loc_180016BEF
0x180016bd7  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016bde  xor     edx, edx; Flags
0x180016be0  call    cs:__imp_RtlFreeHeap
0x180016be6  mov     [rdi+rbx*8], r13
0x180016bea  mov     [rdi+rbx*8+8], r13d
0x180016bef  inc     rsi
0x180016bf2  cmp     rsi, 0Ah
0x180016bf6  jnz     short loc_180016BC8
0x180016bf8  lea     rax, [rbp+57h+hKey]
0x180016bfc  xor     r8d, r8d; ulOptions
0x180016bff  lea     r9d, [rsi-9]; samDesired
0x180016c03  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180016c08  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Pow"...
0x180016c0f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016c16  call    cs:__imp_RegOpenKeyExW
0x180016c1c  test    eax, eax
0x180016c1e  jnz     loc_180016DD5
0x180016c24  mov     rcx, [rbp+57h+hKey]; hKey
0x180016c28  lea     rax, [rbp+57h+var_58]
0x180016c2c  lea     r9d, [rsi-7]; samDesired
0x180016c30  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180016c35  xor     r8d, r8d; ulOptions
0x180016c38  mov     rdx, r14; lpSubKey
0x180016c3b  call    cs:__imp_RegOpenKeyExW
0x180016c41  test    eax, eax
0x180016c43  jnz     loc_180016DD5
0x180016c49  mov     rcx, [rbp+57h+var_58]; hKey
0x180016c4d  lea     rax, [rbp+57h+cbMaxValueLen]
0x180016c51  mov     [rsp+0C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180016c56  xor     r9d, r9d; lpReserved
0x180016c59  mov     [rsp+0C0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180016c5e  xor     r8d, r8d; lpcchClass
0x180016c61  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180016c66  xor     edx, edx; lpClass
0x180016c68  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180016c6c  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180016c71  lea     rax, [rbp+57h+cValues]
0x180016c75  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x180016c7a  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180016c7f  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180016c84  mov     [rsp+0C0h+phkResult], r13; lpcSubKeys
0x180016c89  call    cs:__imp_RegQueryInfoKeyW
0x180016c8f  mov     ebx, eax
0x180016c91  test    eax, eax
0x180016c93  jnz     loc_180016DD8
0x180016c99  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180016c9c  lea     edx, [rsi-2]; Flags
0x180016c9f  lea     ecx, ds:2[rcx*2]
0x180016ca6  mov     [rbp+57h+cchValueName], ecx
0x180016ca9  mov     r8d, ecx; Size
0x180016cac  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016cb3  call    cs:__imp_RtlAllocateHeap
0x180016cb9  mov     r15, rax
0x180016cbc  test    rax, rax
0x180016cbf  jnz     short loc_180016CC9
0x180016cc1  lea     ebx, [rsi+4]
0x180016cc4  jmp     loc_180016DD8
0x180016cc9  cmp     [rbp+57h+cbMaxValueLen], 4
0x180016ccd  jnb     short loc_180016D07
0x180016ccf  mov     rsi, r13
0x180016cd2  mov     ebx, r13d
0x180016cd5  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016cdc  mov     r8, r15; P
0x180016cdf  xor     edx, edx; Flags
0x180016ce1  call    cs:__imp_RtlFreeHeap
0x180016ce7  test    rsi, rsi
0x180016cea  jz      loc_180016DD8
0x180016cf0  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016cf7  mov     r8, rsi; P
0x180016cfa  xor     edx, edx; Flags
0x180016cfc  call    cs:__imp_RtlFreeHeap
0x180016d02  jmp     loc_180016DD8
0x180016d07  mov     r8d, [rbp+57h+cbMaxValueLen]; Size
0x180016d0b  mov     edx, 8; Flags
0x180016d10  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016d17  call    cs:__imp_RtlAllocateHeap
0x180016d1d  mov     rsi, rax
0x180016d20  test    rax, rax
0x180016d23  jnz     short loc_180016D2C
0x180016d25  mov     ebx, 0Eh
0x180016d2a  jmp     short loc_180016CD5
0x180016d2c  mov     r14d, r13d
0x180016d2f  test    ebx, ebx
0x180016d31  jnz     short loc_180016CD2
0x180016d33  mov     eax, [rbp+57h+cbMaxValueLen]
0x180016d36  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180016d3a  mov     rcx, [rbp+57h+var_58]; hKey
0x180016d3e  mov     r8, r15; lpValueName
0x180016d41  mov     [rbp+57h+cbData], eax
0x180016d44  mov     edx, r14d; dwIndex
0x180016d47  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180016d4a  inc     eax
0x180016d4c  mov     [rbp+57h+cchValueName], eax
0x180016d4f  lea     rax, [rbp+57h+cbData]
0x180016d53  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x180016d58  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpData
0x180016d5d  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r13; lpType
0x180016d62  mov     [rsp+0C0h+phkResult], r13; lpReserved
0x180016d67  call    cs:__imp_RegEnumValueW
0x180016d6d  mov     ebx, eax
0x180016d6f  test    eax, eax
0x180016d71  jnz     short loc_180016DCD
0x180016d73  cmp     [rbp+57h+cbData], 4
0x180016d77  jnz     short loc_180016DCD
0x180016d79  cmp     r14d, 0Ah
0x180016d7d  jnb     loc_180016CD2
0x180016d83  cmp     [rsi], r13d
0x180016d86  jz      short loc_180016DCD
0x180016d88  mov     r8d, [rbp+57h+cchValueName]
0x180016d8c  lea     edx, [rax+8]; Flags
0x180016d8f  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016d96  inc     r8d
0x180016d99  add     r8, r8; Size
0x180016d9c  call    cs:__imp_RtlAllocateHeap
0x180016da2  mov     r12d, r14d
0x180016da5  add     r12, r12
0x180016da8  mov     [rdi+r12*8], rax
0x180016dac  test    rax, rax
0x180016daf  jz      loc_180016D25
0x180016db5  mov     edx, [rbp+57h+cchValueName]
0x180016db8  mov     r8, r15; pszSrc
0x180016dbb  inc     edx; cchDest
0x180016dbd  mov     rcx, rax; pszDest
0x180016dc0  call    StringCchCopyW
0x180016dc5  mov     r11d, [rsi]
0x180016dc8  mov     [rdi+r12*8+8], r11d
0x180016dcd  inc     r14d
0x180016dd0  jmp     loc_180016D2F
0x180016dd5  mov     ebx, r13d
0x180016dd8  mov     rcx, [rbp+57h+var_58]; hKey
0x180016ddc  lea     rax, [rcx-1]
0x180016de0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016de4  ja      short loc_180016DF4
0x180016de6  call    cs:__imp_RegCloseKey
0x180016dec  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x180016df4  mov     rcx, [rbp+57h+hKey]; hKey
0x180016df8  lea     rax, [rcx-1]
0x180016dfc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016e00  ja      short loc_180016E08
0x180016e02  call    cs:__imp_RegCloseKey
0x180016e08  mov     eax, ebx
0x180016e0a  add     rsp, 88h
0x180016e11  pop     r15
0x180016e13  pop     r14
0x180016e15  pop     r13
0x180016e17  pop     r12
0x180016e19  pop     rdi
0x180016e1a  pop     rsi
0x180016e1b  pop     rbx
0x180016e1c  pop     rbp
0x180016e1d  retn
```
