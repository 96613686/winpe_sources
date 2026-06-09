# CSecretStorage::Retrieve(uchar *,ulong *)

- ea: `0x18002b8ac`
- end: `0x18002badb`
- name: `?Retrieve@CSecretStorage@@QEAAJPEAEPEAK@Z`
- size: `559`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800840d0`

## callees

- `0x18000a210`
- `0x18002b8ac`
- `0x1800c4e0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b997`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b997`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002baa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002baa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bab7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b970`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b9d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b970`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b9d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bac6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bac6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b914`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b914`
- `CRYPT32!CryptUnprotectData` at `0x18002ba31`
- `CRYPT32!CryptUnprotectData` at `0x18002ba31`

## string_xrefs

- `0x18002b930`: `RegOpenKeyEx failed: 0x%x in %s`
- `0x18002b9f0`: `Invalid registry type, expecting REG_BINARY, got: %d`

## pseudocode

```c
__int64 __fastcall CSecretStorage::Retrieve(LPCWSTR *this, unsigned __int8 *a2, unsigned int *a3)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  signed int LastError; // eax
  DWORD v11; // edi
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF
  DATA_BLOB cbData; // [rsp+48h] [rbp-30h] BYREF
  DATA_BLOB pDataOut; // [rsp+58h] [rbp-20h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+50h] BYREF

  *(_QWORD *)&cbData.cbData = 0;
  cbData.pbData = 0;
  *(_QWORD *)&pDataOut.cbData = 0;
  pDataOut.pbData = 0;
  hKey = 0;
  Type = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\RCM\\Secrets",
         0,
         0x20019u,
         &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    v8 = RegQueryValueExW(hKey, *this, 0, &Type, 0, &cbData.cbData);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_9;
    cbData.pbData = (BYTE *)LocalAlloc(0x40u, cbData.cbData);
    if ( !cbData.pbData )
    {
      v7 = -2147024882;
      goto LABEL_26;
    }
    v9 = RegQueryValueExW(hKey, *this, 0, &Type, cbData.pbData, &cbData.cbData);
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    if ( v7 < 0 )
    {
LABEL_9:
      _DbgPrintMessage(8, "RegQueryValueEx failed: 0x%x in %s", (unsigned int)v7, "CSecretStorage::Retrieve");
      goto LABEL_26;
    }
    if ( Type != 3 )
    {
      _DbgPrintMessage(8, "Invalid registry type, expecting REG_BINARY, got: %d", Type);
      v7 = -2147418113;
      goto LABEL_26;
    }
    if ( CryptUnprotectData(&cbData, 0, 0, 0, 0, 1u, &pDataOut) )
    {
      if ( a2 )
      {
        v11 = pDataOut.cbData;
        if ( *a3 >= pDataOut.cbData )
        {
          memcpy_0(a2, pDataOut.pbData, pDataOut.cbData);
          *a3 = v11;
          goto LABEL_26;
        }
        v7 = -2147024774;
        _DbgPrintMessage(8, "Insufficient input buffer");
      }
      *a3 = pDataOut.cbData;
      goto LABEL_26;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "CryptUnprotectData failed: 0x%x", v7);
  }
  else
  {
    _DbgPrintMessage(8, "RegOpenKeyEx failed: 0x%x in %s", (unsigned int)v7, "CSecretStorage::Retrieve");
  }
LABEL_26:
  if ( cbData.pbData )
    LocalFree(cbData.pbData);
  if ( pDataOut.pbData )
    LocalFree(pDataOut.pbData);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002b8ac  push    rbp
0x18002b8ae  push    rbx
0x18002b8af  push    rsi
0x18002b8b0  push    rdi
0x18002b8b1  push    r12
0x18002b8b3  push    r14
0x18002b8b5  mov     rbp, rsp
0x18002b8b8  sub     rsp, 78h
0x18002b8bc  mov     rsi, r8
0x18002b8bf  mov     qword ptr [rbp+cbData], 0
0x18002b8c7  mov     r14, rdx
0x18002b8ca  mov     [rbp+lpData], 0
0x18002b8d2  mov     rdi, rcx
0x18002b8d5  mov     qword ptr [rbp+var_20.cbData], 0
0x18002b8dd  lea     rax, [rbp+hKey]
0x18002b8e1  mov     [rbp+var_20.pbData], 0
0x18002b8e9  xor     r8d, r8d; ulOptions
0x18002b8ec  mov     [rsp+78h+phkResult], rax; phkResult
0x18002b8f1  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x18002b8f8  mov     [rbp+hKey], 0
0x18002b900  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b907  mov     [rbp+Type], 0
0x18002b90e  mov     r9d, 20019h; samDesired
0x18002b914  call    cs:__imp_RegOpenKeyExW
0x18002b91a  mov     ebx, eax
0x18002b91c  mov     r12d, 80070000h
0x18002b922  test    eax, eax
0x18002b924  jle     short loc_18002B92C
0x18002b926  movzx   ebx, ax
0x18002b929  or      ebx, r12d
0x18002b92c  test    ebx, ebx
0x18002b92e  jns     short loc_18002B950
0x18002b930  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed: 0x%x in %s"
0x18002b937  mov     r8d, ebx
0x18002b93a  lea     r9, aCsecretstorage; "CSecretStorage::Retrieve"
0x18002b941  mov     ecx, 8; int
0x18002b946  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b94b  jmp     loc_18002BA9F
0x18002b950  mov     rdx, [rdi]; lpValueName
0x18002b953  lea     rax, [rbp+cbData]
0x18002b957  mov     rcx, [rbp+hKey]; hKey
0x18002b95b  lea     r9, [rbp+Type]; lpType
0x18002b95f  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18002b964  xor     r8d, r8d; lpReserved
0x18002b967  mov     [rsp+78h+phkResult], 0; lpData
0x18002b970  call    cs:__imp_RegQueryValueExW
0x18002b976  mov     ebx, eax
0x18002b978  test    eax, eax
0x18002b97a  jle     short loc_18002B982
0x18002b97c  movzx   ebx, ax
0x18002b97f  or      ebx, r12d
0x18002b982  test    ebx, ebx
0x18002b984  jns     short loc_18002B98F
0x18002b986  lea     rdx, aRegqueryvaluee_1; "RegQueryValueEx failed: 0x%x in %s"
0x18002b98d  jmp     short loc_18002B937
0x18002b98f  mov     edx, [rbp+cbData]; uBytes
0x18002b992  mov     ecx, 40h ; '@'; uFlags
0x18002b997  call    cs:__imp_LocalAlloc
0x18002b99d  mov     [rbp+lpData], rax
0x18002b9a1  test    rax, rax
0x18002b9a4  jnz     short loc_18002B9B0
0x18002b9a6  mov     ebx, 8007000Eh
0x18002b9ab  jmp     loc_18002BA9F
0x18002b9b0  mov     rdx, [rdi]; lpValueName
0x18002b9b3  lea     rax, [rbp+cbData]
0x18002b9b7  mov     rcx, [rbp+hKey]; hKey
0x18002b9bb  lea     r9, [rbp+Type]; lpType
0x18002b9bf  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18002b9c4  xor     r8d, r8d; lpReserved
0x18002b9c7  mov     rax, [rbp+lpData]
0x18002b9cb  mov     [rsp+78h+phkResult], rax; lpData
0x18002b9d0  call    cs:__imp_RegQueryValueExW
0x18002b9d6  mov     ebx, eax
0x18002b9d8  test    eax, eax
0x18002b9da  jle     short loc_18002B9E2
0x18002b9dc  movzx   ebx, ax
0x18002b9df  or      ebx, r12d
0x18002b9e2  test    ebx, ebx
0x18002b9e4  js      short loc_18002B986
0x18002b9e6  mov     r8d, [rbp+Type]
0x18002b9ea  cmp     r8d, 3
0x18002b9ee  jz      short loc_18002BA0B
0x18002b9f0  lea     rdx, aInvalidRegistr; "Invalid registry type, expecting REG_BI"...
0x18002b9f7  mov     ecx, 8; int
0x18002b9fc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ba01  mov     ebx, 8000FFFFh
0x18002ba06  jmp     loc_18002BA9F
0x18002ba0b  lea     rax, [rbp+var_20]
0x18002ba0f  xor     r9d, r9d; pvReserved
0x18002ba12  mov     [rsp+78h+pDataOut], rax; pDataOut
0x18002ba17  lea     rcx, [rbp+cbData]; pDataIn
0x18002ba1b  mov     dword ptr [rsp+78h+lpcbData], 1; dwFlags
0x18002ba23  xor     r8d, r8d; pOptionalEntropy
0x18002ba26  xor     edx, edx; ppszDataDescr
0x18002ba28  mov     [rsp+78h+phkResult], 0; pPromptStruct
0x18002ba31  call    cs:__imp_CryptUnprotectData
0x18002ba37  test    eax, eax
0x18002ba39  jnz     short loc_18002BA63
0x18002ba3b  call    cs:__imp_GetLastError
0x18002ba41  mov     ebx, eax
0x18002ba43  test    eax, eax
0x18002ba45  jle     short loc_18002BA4D
0x18002ba47  movzx   ebx, ax
0x18002ba4a  or      ebx, r12d
0x18002ba4d  mov     r8d, ebx
0x18002ba50  lea     rdx, aCryptunprotect_2; "CryptUnprotectData failed: 0x%x"
0x18002ba57  mov     ecx, 8; int
0x18002ba5c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ba61  jmp     short loc_18002BA9F
0x18002ba63  test    r14, r14
0x18002ba66  jnz     short loc_18002BA6F
0x18002ba68  mov     eax, [rbp+var_20.cbData]
0x18002ba6b  mov     [rsi], eax
0x18002ba6d  jmp     short loc_18002BA9F
0x18002ba6f  mov     edi, [rbp+var_20.cbData]
0x18002ba72  cmp     [rsi], edi
0x18002ba74  jnb     short loc_18002BA8E
0x18002ba76  lea     rdx, aInsufficientIn; "Insufficient input buffer"
0x18002ba7d  mov     ecx, 8; int
0x18002ba82  mov     ebx, 8007007Ah
0x18002ba87  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ba8c  jmp     short loc_18002BA68
0x18002ba8e  mov     rdx, [rbp+var_20.pbData]; Src
0x18002ba92  mov     r8, rdi; Size
0x18002ba95  mov     rcx, r14; void *
0x18002ba98  call    memcpy_0
0x18002ba9d  mov     [rsi], edi
0x18002ba9f  mov     rcx, [rbp+lpData]; hMem
0x18002baa3  test    rcx, rcx
0x18002baa6  jz      short loc_18002BAAE
0x18002baa8  call    cs:__imp_LocalFree
0x18002baae  mov     rcx, [rbp+var_20.pbData]; hMem
0x18002bab2  test    rcx, rcx
0x18002bab5  jz      short loc_18002BABD
0x18002bab7  call    cs:__imp_LocalFree
0x18002babd  mov     rcx, [rbp+hKey]; hKey
0x18002bac1  test    rcx, rcx
0x18002bac4  jz      short loc_18002BACC
0x18002bac6  call    cs:__imp_RegCloseKey
0x18002bacc  mov     eax, ebx
0x18002bace  add     rsp, 78h
0x18002bad2  pop     r14
0x18002bad4  pop     r12
0x18002bad6  pop     rdi
0x18002bad7  pop     rsi
0x18002bad8  pop     rbx
0x18002bad9  pop     rbp
0x18002bada  retn
```
