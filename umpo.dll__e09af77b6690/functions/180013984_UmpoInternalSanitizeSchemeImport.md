# UmpoInternalSanitizeSchemeImport

- ea: `0x180013984`
- end: `0x180013daf`
- name: `UmpoInternalSanitizeSchemeImport`
- size: `1067`
- prototype: `__int64 __fastcall(HKEY, HKEY, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180012254`
- `0x180013984`

## callees

- `0x180010070`
- `0x180010946`
- `0x180013984`
- `0x180013db8`
- `0x1800188a4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180013a63`
- `ntdll!RtlAllocateHeap` at `0x180013a91`
- `ntdll!RtlAllocateHeap` at `0x180013ab7`
- `ntdll!RtlAllocateHeap` at `0x180013a63`
- `ntdll!RtlAllocateHeap` at `0x180013a91`
- `ntdll!RtlAllocateHeap` at `0x180013ab7`
- `ntdll!RtlFreeHeap` at `0x180013d57`
- `ntdll!RtlFreeHeap` at `0x180013d69`
- `ntdll!RtlFreeHeap` at `0x180013d80`
- `ntdll!RtlFreeHeap` at `0x180013d57`
- `ntdll!RtlFreeHeap` at `0x180013d69`
- `ntdll!RtlFreeHeap` at `0x180013d80`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013bd5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013bd5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013ce9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013ce9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013b24`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013b24`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013a37`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013a37`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013c4d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013c4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013c75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013c75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d32`
- `RPCRT4!UuidFromStringW` at `0x180013ca0`
- `RPCRT4!UuidFromStringW` at `0x180013ca0`

## pseudocode

```c
__int64 __fastcall UmpoInternalSanitizeSchemeImport(HKEY a1, HKEY a2, unsigned int a3)
{
  DWORD v3; // edi
  HKEY v5; // r13
  unsigned int v6; // ebx
  PVOID Heap; // rsi
  SIZE_T v8; // r8
  PVOID v9; // r14
  PVOID v10; // r12
  DWORD v11; // r13d
  const wchar_t *v12; // rdx
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-39h] BYREF
  size_t Size; // [rsp+64h] [rbp-35h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-2Dh] BYREF
  DWORD cValues; // [rsp+70h] [rbp-29h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-25h] BYREF
  DWORD Type; // [rsp+78h] [rbp-21h] BYREF
  DWORD cSubKeys; // [rsp+7Ch] [rbp-1Dh] BYREF
  DWORD cchName; // [rsp+80h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-9h] BYREF
  HKEY v24; // [rsp+98h] [rbp-1h]
  UUID Uuid; // [rsp+A0h] [rbp+7h] BYREF

  v3 = 0;
  v24 = a2;
  *(_QWORD *)&Uuid.Data1 = a1;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  cbMaxValueLen = 0;
  v5 = a1;
  cbMaxValueNameLen = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  cchName = 0;
  cSubKeys = 0;
  Size = 0;
  cchValueName = 0;
  cValues = 0;
  Type = 0;
  if ( a3 >= 3 )
    return 13;
  v6 = RegQueryInfoKeyW(
         a1,
         0,
         0,
         0,
         &cSubKeys,
         (LPDWORD)&Size + 1,
         0,
         &cValues,
         &cbMaxValueNameLen,
         &cbMaxValueLen,
         0,
         0);
  if ( v6 )
    return v6;
  Heap = RtlAllocateHeap(UmpoHeapHandle, 8u, 2LL * ++cbMaxValueNameLen);
  if ( !Heap )
    return 14;
  v8 = 2LL * (unsigned int)++HIDWORD(Size);
  v9 = RtlAllocateHeap(UmpoHeapHandle, 8u, v8);
  if ( v9 )
  {
    v10 = RtlAllocateHeap(UmpoHeapHandle, 8u, cbMaxValueLen);
    if ( v10 )
    {
      while ( 1 )
      {
        if ( v3 >= cValues )
        {
          v3 = 0;
          goto LABEL_25;
        }
        cchValueName = cbMaxValueNameLen;
        LODWORD(Size) = cbMaxValueLen;
        memset_0(Heap, 0, 2LL * cbMaxValueNameLen);
        memset_0(v10, 0, (unsigned int)Size);
        v6 = RegEnumValueW(v5, v3, (LPWSTR)Heap, &cchValueName, 0, &Type, (LPBYTE)v10, (LPDWORD)&Size);
        if ( v6 || (v11 = Size, !a3) && (v6 = UmpoInternalSanitizeSchemeWrite(v10, (unsigned int)Size)) != 0 )
        {
LABEL_39:
          RtlFreeHeap(UmpoHeapHandle, 0, v10);
          goto LABEL_40;
        }
        if ( !a3 )
          break;
        if ( a3 - 1 > 1 )
          goto LABEL_23;
        if ( wcscmp_0((const wchar_t *)Heap, L"ACSettingIndex") )
        {
          v12 = L"DCSettingIndex";
LABEL_20:
          if ( wcscmp_0((const wchar_t *)Heap, v12) )
          {
LABEL_23:
            v5 = *(HKEY *)&Uuid.Data1;
            v6 = 13;
            while ( 1 )
            {
              if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                RegCloseKey(hKey);
                hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
              }
              if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                RegCloseKey(phkResult);
                phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
              }
              if ( v6 )
                break;
              ++v3;
LABEL_25:
              if ( v3 >= cSubKeys )
                break;
              hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
              phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
              cchName = HIDWORD(Size);
              memset_0(v9, 0, 2LL * HIDWORD(Size));
              v6 = RegEnumKeyExW(v5, v3, (LPWSTR)v9, &cchName, 0, 0, 0, 0);
              if ( !v6 )
              {
                v6 = RegOpenKeyExW(v5, (LPCWSTR)v9, 0, 0x20019u, &hKey);
                if ( !v6 )
                {
                  if ( a3 > 1 || (Uuid = 0, UuidFromStringW((RPC_WSTR)v9, &Uuid)) )
                  {
                    v6 = 13;
                  }
                  else
                  {
                    v6 = RegCreateKeyExW(v24, (LPCWSTR)v9, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
                    if ( !v6 )
                      v6 = UmpoInternalSanitizeSchemeImport(hKey, phkResult, a3 + 1);
                  }
                }
              }
            }
            goto LABEL_39;
          }
        }
LABEL_21:
        v6 = RegSetValueExW(v24, (LPCWSTR)Heap, 0, Type, (const BYTE *)v10, v11);
        if ( v6 )
          goto LABEL_39;
        v5 = *(HKEY *)&Uuid.Data1;
        ++v3;
      }
      if ( !wcscmp_0((const wchar_t *)Heap, L"Description") || !wcscmp_0((const wchar_t *)Heap, L"FriendlyName") )
        goto LABEL_21;
      v12 = L"IconResource";
      goto LABEL_20;
    }
  }
  v6 = 14;
LABEL_40:
  RtlFreeHeap(UmpoHeapHandle, 0, Heap);
  if ( v9 )
    RtlFreeHeap(UmpoHeapHandle, 0, v9);
  return v6;
}

```

## disassembly

```asm
0x180013984  mov     [rsp-8+arg_18], rbx
0x180013989  push    rbp
0x18001398a  push    rsi
0x18001398b  push    rdi
0x18001398c  push    r12
0x18001398e  push    r13
0x180013990  push    r14
0x180013992  push    r15
0x180013994  lea     rbp, [rsp-27h]
0x180013999  sub     rsp, 0C0h
0x1800139a0  mov     rax, cs:__security_cookie
0x1800139a7  xor     rax, rsp
0x1800139aa  mov     [rbp+57h+var_40], rax
0x1800139ae  xor     edi, edi
0x1800139b0  mov     [rbp+57h+var_58], rdx
0x1800139b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800139b8  mov     qword ptr [rbp+57h+Uuid.Data1], rcx
0x1800139bc  mov     [rbp+57h+phkResult], rax
0x1800139c0  mov     r15d, r8d
0x1800139c3  mov     [rbp+57h+cbMaxValueLen], edi
0x1800139c6  mov     r13, rcx
0x1800139c9  mov     [rbp+57h+cbMaxValueNameLen], edi
0x1800139cc  mov     [rbp+57h+hKey], rax
0x1800139d0  mov     [rbp+57h+cchName], edi
0x1800139d3  mov     [rbp+57h+cSubKeys], edi
0x1800139d6  mov     dword ptr [rbp+57h+Size], edi
0x1800139d9  mov     [rbp+57h+cchValueName], edi
0x1800139dc  mov     [rbp+57h+cValues], edi
0x1800139df  mov     [rbp+57h+Type], edi
0x1800139e2  mov     dword ptr [rbp+57h+Size+4], edi
0x1800139e5  cmp     r8d, 3
0x1800139e9  jb      short loc_1800139F3
0x1800139eb  lea     ebx, [rax+0Eh]
0x1800139ee  jmp     loc_180013D86
0x1800139f3  mov     [rsp+0F0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800139f8  lea     rax, [rbp+57h+cbMaxValueLen]
0x1800139fc  mov     [rsp+0F0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180013a01  xor     r9d, r9d; lpReserved
0x180013a04  mov     [rsp+0F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180013a09  xor     r8d, r8d; lpcchClass
0x180013a0c  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180013a10  xor     edx, edx; lpClass
0x180013a12  mov     [rsp+0F0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180013a17  lea     rax, [rbp+57h+cValues]
0x180013a1b  mov     [rsp+0F0h+lpcValues], rax; lpcValues
0x180013a20  lea     rax, [rbp+57h+Size+4]
0x180013a24  mov     [rsp+0F0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180013a29  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180013a2e  lea     rax, [rbp+57h+cSubKeys]
0x180013a32  mov     [rsp+0F0h+lpcSubKeys], rax; lpcSubKeys
0x180013a37  call    cs:__imp_RegQueryInfoKeyW
0x180013a3d  mov     ebx, eax
0x180013a3f  test    eax, eax
0x180013a41  jnz     loc_180013D86
0x180013a47  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180013a4a  lea     r12d, [rax+8]
0x180013a4e  inc     ecx
0x180013a50  mov     edx, r12d; Flags
0x180013a53  mov     r8d, ecx
0x180013a56  mov     [rbp+57h+cbMaxValueNameLen], ecx
0x180013a59  add     r8, r8; Size
0x180013a5c  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180013a63  call    cs:__imp_RtlAllocateHeap
0x180013a69  mov     rsi, rax
0x180013a6c  test    rax, rax
0x180013a6f  jnz     short loc_180013A79
0x180013a71  lea     ebx, [rax+0Eh]
0x180013a74  jmp     loc_180013D86
0x180013a79  mov     eax, dword ptr [rbp+57h+Size+4]
0x180013a7c  mov     edx, r12d; Flags
0x180013a7f  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180013a86  inc     eax
0x180013a88  mov     r8d, eax
0x180013a8b  add     r8, r8; Size
0x180013a8e  mov     dword ptr [rbp+57h+Size+4], eax
0x180013a91  call    cs:__imp_RtlAllocateHeap
0x180013a97  mov     r14, rax
0x180013a9a  test    rax, rax
0x180013a9d  jnz     short loc_180013AA9
0x180013a9f  mov     ebx, 0Eh
0x180013aa4  jmp     loc_180013D5D
0x180013aa9  mov     r8d, [rbp+57h+cbMaxValueLen]; Size
0x180013aad  mov     edx, r12d; Flags
0x180013ab0  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180013ab7  call    cs:__imp_RtlAllocateHeap
0x180013abd  mov     r12, rax
0x180013ac0  test    rax, rax
0x180013ac3  jz      short loc_180013A9F
0x180013ac5  cmp     edi, [rbp+57h+cValues]
0x180013ac8  jnb     loc_180013BFE
0x180013ace  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180013ad1  xor     edx, edx; Val
0x180013ad3  mov     eax, [rbp+57h+cbMaxValueLen]
0x180013ad6  mov     r8d, ecx
0x180013ad9  mov     [rbp+57h+cchValueName], ecx
0x180013adc  add     r8, r8; Size
0x180013adf  mov     rcx, rsi; void *
0x180013ae2  mov     dword ptr [rbp+57h+Size], eax
0x180013ae5  call    memset_0
0x180013aea  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180013aee  xor     edx, edx; Val
0x180013af0  mov     rcx, r12; void *
0x180013af3  call    memset_0
0x180013af8  lea     rax, [rbp+57h+Size]
0x180013afc  mov     r8, rsi; lpValueName
0x180013aff  mov     [rsp+0F0h+lpcValues], rax; lpcbData
0x180013b04  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180013b08  lea     rax, [rbp+57h+Type]
0x180013b0c  mov     [rsp+0F0h+lpcbMaxClassLen], r12; lpData
0x180013b11  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpType
0x180013b16  mov     edx, edi; dwIndex
0x180013b18  mov     rcx, r13; hKey
0x180013b1b  mov     [rsp+0F0h+lpcSubKeys], 0; lpReserved
0x180013b24  call    cs:__imp_RegEnumValueW
0x180013b2a  mov     ebx, eax
0x180013b2c  test    eax, eax
0x180013b2e  jnz     loc_180013D4B
0x180013b34  mov     r13d, dword ptr [rbp+57h+Size]
0x180013b38  test    r15d, r15d
0x180013b3b  jnz     short loc_180013B52
0x180013b3d  mov     edx, r13d
0x180013b40  mov     rcx, r12
0x180013b43  call    UmpoInternalSanitizeSchemeWrite
0x180013b48  mov     ebx, eax
0x180013b4a  test    eax, eax
0x180013b4c  jnz     loc_180013D4B
0x180013b52  mov     eax, r15d
0x180013b55  test    r15d, r15d
0x180013b58  jz      short loc_180013B84
0x180013b5a  sub     eax, 1
0x180013b5d  jz      short loc_180013B68
0x180013b5f  cmp     eax, 1
0x180013b62  jnz     loc_180013BF0
0x180013b68  lea     rdx, aAcsettingindex; "ACSettingIndex"
0x180013b6f  mov     rcx, rsi; String1
0x180013b72  call    wcscmp_0
0x180013b77  test    eax, eax
0x180013b79  jz      short loc_180013BBD
0x180013b7b  lea     rdx, aDcsettingindex; "DCSettingIndex"
0x180013b82  jmp     short loc_180013BB1
0x180013b84  lea     rdx, aDescription; "Description"
0x180013b8b  mov     rcx, rsi; String1
0x180013b8e  call    wcscmp_0
0x180013b93  test    eax, eax
0x180013b95  jz      short loc_180013BBD
0x180013b97  lea     rdx, aFriendlyname; "FriendlyName"
0x180013b9e  mov     rcx, rsi; String1
0x180013ba1  call    wcscmp_0
0x180013ba6  test    eax, eax
0x180013ba8  jz      short loc_180013BBD
0x180013baa  lea     rdx, aIconresource; "IconResource"
0x180013bb1  mov     rcx, rsi; String1
0x180013bb4  call    wcscmp_0
0x180013bb9  test    eax, eax
0x180013bbb  jnz     short loc_180013BF0
0x180013bbd  mov     r9d, [rbp+57h+Type]; dwType
0x180013bc1  xor     r8d, r8d; Reserved
0x180013bc4  mov     rcx, [rbp+57h+var_58]; hKey
0x180013bc8  mov     rdx, rsi; lpValueName
0x180013bcb  mov     dword ptr [rsp+0F0h+lpcbMaxSubKeyLen], r13d; cbData
0x180013bd0  mov     [rsp+0F0h+lpcSubKeys], r12; lpData
0x180013bd5  call    cs:__imp_RegSetValueExW
0x180013bdb  mov     ebx, eax
0x180013bdd  test    eax, eax
0x180013bdf  jnz     loc_180013D4B
0x180013be5  mov     r13, qword ptr [rbp+57h+Uuid.Data1]
0x180013be9  inc     edi
0x180013beb  jmp     loc_180013AC5
0x180013bf0  mov     r13, qword ptr [rbp+57h+Uuid.Data1]
0x180013bf4  mov     ebx, 0Dh
0x180013bf9  jmp     loc_180013D08
0x180013bfe  xor     edi, edi
0x180013c00  cmp     edi, [rbp+57h+cSubKeys]
0x180013c03  jnb     loc_180013D4B
0x180013c09  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013c0d  xor     edx, edx; Val
0x180013c0f  mov     [rbp+57h+hKey], rax
0x180013c13  mov     rcx, r14; void *
0x180013c16  mov     [rbp+57h+phkResult], rax
0x180013c1a  mov     eax, dword ptr [rbp+57h+Size+4]
0x180013c1d  mov     r8d, eax
0x180013c20  mov     [rbp+57h+cchName], eax
0x180013c23  add     r8, r8; Size
0x180013c26  call    memset_0
0x180013c2b  xor     eax, eax
0x180013c2d  lea     r9, [rbp+57h+cchName]; lpcchName
0x180013c31  mov     [rsp+0F0h+lpcValues], rax; lpftLastWriteTime
0x180013c36  mov     r8, r14; lpName
0x180013c39  mov     [rsp+0F0h+lpcbMaxClassLen], rax; lpcchClass
0x180013c3e  mov     edx, edi; dwIndex
0x180013c40  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpClass
0x180013c45  mov     rcx, r13; hKey
0x180013c48  mov     [rsp+0F0h+lpcSubKeys], rax; lpReserved
0x180013c4d  call    cs:__imp_RegEnumKeyExW
0x180013c53  mov     ebx, eax
0x180013c55  test    eax, eax
0x180013c57  jnz     loc_180013D08
0x180013c5d  lea     rax, [rbp+57h+hKey]
0x180013c61  mov     r9d, 20019h; samDesired
0x180013c67  xor     r8d, r8d; ulOptions
0x180013c6a  mov     [rsp+0F0h+lpcSubKeys], rax; phkResult
0x180013c6f  mov     rdx, r14; lpSubKey
0x180013c72  mov     rcx, r13; hKey
0x180013c75  call    cs:__imp_RegOpenKeyExW
0x180013c7b  mov     ebx, eax
0x180013c7d  test    eax, eax
0x180013c7f  jnz     loc_180013D08
0x180013c85  mov     eax, r15d
0x180013c88  test    r15d, r15d
0x180013c8b  jz      short loc_180013C92
0x180013c8d  cmp     eax, 1
0x180013c90  jnz     short loc_180013CAA
0x180013c92  xorps   xmm0, xmm0
0x180013c95  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180013c99  lea     rdx, [rbp+57h+Uuid]; Uuid
0x180013c9d  mov     rcx, r14; StringUuid
0x180013ca0  call    cs:__imp_UuidFromStringW
0x180013ca6  test    eax, eax
0x180013ca8  jz      short loc_180013CB1
0x180013caa  mov     ebx, 0Dh
0x180013caf  jmp     short loc_180013D08
0x180013cb1  mov     rcx, [rbp+57h+var_58]; hKey
0x180013cb5  lea     rax, [rbp+57h+phkResult]
0x180013cb9  mov     [rsp+0F0h+lpcbMaxValueNameLen], 0; lpdwDisposition
0x180013cc2  xor     r9d, r9d; lpClass
0x180013cc5  mov     [rsp+0F0h+lpcValues], rax; phkResult
0x180013cca  xor     r8d, r8d; Reserved
0x180013ccd  mov     [rsp+0F0h+lpcbMaxClassLen], 0; lpSecurityAttributes
0x180013cd6  mov     rdx, r14; lpSubKey
0x180013cd9  mov     dword ptr [rsp+0F0h+lpcbMaxSubKeyLen], 2001Fh; samDesired
0x180013ce1  mov     dword ptr [rsp+0F0h+lpcSubKeys], 0; dwOptions
0x180013ce9  call    cs:__imp_RegCreateKeyExW
0x180013cef  mov     ebx, eax
0x180013cf1  test    eax, eax
0x180013cf3  jnz     short loc_180013D08
0x180013cf5  mov     rdx, [rbp+57h+phkResult]
0x180013cf9  lea     r8d, [r15+1]
0x180013cfd  mov     rcx, [rbp+57h+hKey]
0x180013d01  call    UmpoInternalSanitizeSchemeImport
0x180013d06  mov     ebx, eax
0x180013d08  mov     rcx, [rbp+57h+hKey]; hKey
0x180013d0c  lea     rax, [rcx-1]
0x180013d10  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013d14  ja      short loc_180013D24
0x180013d16  call    cs:__imp_RegCloseKey
0x180013d1c  mov     [rbp+57h+hKey], 0FFFFFFFFFFFFFFFFh
0x180013d24  mov     rcx, [rbp+57h+phkResult]; hKey
0x180013d28  lea     rax, [rcx-1]
0x180013d2c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013d30  ja      short loc_180013D40
0x180013d32  call    cs:__imp_RegCloseKey
0x180013d38  mov     [rbp+57h+phkResult], 0FFFFFFFFFFFFFFFFh
0x180013d40  test    ebx, ebx
0x180013d42  jnz     short loc_180013D4B
0x180013d44  inc     edi
0x180013d46  jmp     loc_180013C00
0x180013d4b  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180013d52  mov     r8, r12; P
0x180013d55  xor     edx, edx; Flags
0x180013d57  call    cs:__imp_RtlFreeHeap
0x180013d5d  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180013d64  mov     r8, rsi; P
0x180013d67  xor     edx, edx; Flags
0x180013d69  call    cs:__imp_RtlFreeHeap
0x180013d6f  test    r14, r14
0x180013d72  jz      short loc_180013D86
0x180013d74  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180013d7b  mov     r8, r14; P
0x180013d7e  xor     edx, edx; Flags
0x180013d80  call    cs:__imp_RtlFreeHeap
0x180013d86  mov     eax, ebx
0x180013d88  mov     rcx, [rbp+57h+var_40]
0x180013d8c  xor     rcx, rsp; StackCookie
0x180013d8f  call    __security_check_cookie
0x180013d94  mov     rbx, [rsp+0F0h+arg_18]
0x180013d9c  add     rsp, 0C0h
0x180013da3  pop     r15
0x180013da5  pop     r14
0x180013da7  pop     r13
0x180013da9  pop     r12
0x180013dab  pop     rdi
0x180013dac  pop     rsi
0x180013dad  pop     rbp
0x180013dae  retn
```
