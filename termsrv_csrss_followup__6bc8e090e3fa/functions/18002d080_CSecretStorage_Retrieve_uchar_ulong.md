# CSecretStorage::Retrieve(uchar *,ulong *)

- ea: `0x18002d080`
- end: `0x18002d2e6`
- name: `?Retrieve@CSecretStorage@@QEAAJPEAEPEAK@Z`
- size: `614`
- prototype: `int(CSecretStorage *__hidden this, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180087950`

## callees

- `0x180009940`
- `0x18002d080`
- `0x1800caedc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d22d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d177`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d177`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d14a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d1b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d14a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d1b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d0e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d0e8`
- `CRYPT32!CryptUnprotectData` at `0x18002d21d`
- `CRYPT32!CryptUnprotectData` at `0x18002d21d`

## string_xrefs

- `0x18002d10a`: `RegOpenKeyEx failed: 0x%x in %s`
- `0x18002d1dc`: `Invalid registry type, expecting REG_BINARY, got: %d`

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
0x18002d080  push    rbp
0x18002d082  push    rbx
0x18002d083  push    rsi
0x18002d084  push    rdi
0x18002d085  push    r12
0x18002d087  push    r14
0x18002d089  mov     rbp, rsp
0x18002d08c  sub     rsp, 78h
0x18002d090  mov     rsi, r8
0x18002d093  mov     qword ptr [rbp+cbData], 0
0x18002d09b  mov     r14, rdx
0x18002d09e  mov     [rbp+lpData], 0
0x18002d0a6  mov     rdi, rcx
0x18002d0a9  mov     qword ptr [rbp+var_20.cbData], 0
0x18002d0b1  lea     rax, [rbp+hKey]
0x18002d0b5  mov     [rbp+var_20.pbData], 0
0x18002d0bd  xor     r8d, r8d; ulOptions
0x18002d0c0  mov     [rsp+78h+phkResult], rax; phkResult
0x18002d0c5  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x18002d0cc  mov     [rbp+hKey], 0
0x18002d0d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d0db  mov     [rbp+Type], 0
0x18002d0e2  mov     r9d, 20019h; samDesired
0x18002d0e8  call    cs:__imp_RegOpenKeyExW
0x18002d0ef  nop     dword ptr [rax+rax+00h]
0x18002d0f4  mov     ebx, eax
0x18002d0f6  mov     r12d, 80070000h
0x18002d0fc  test    eax, eax
0x18002d0fe  jle     short loc_18002D106
0x18002d100  movzx   ebx, ax
0x18002d103  or      ebx, r12d
0x18002d106  test    ebx, ebx
0x18002d108  jns     short loc_18002D12A
0x18002d10a  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed: 0x%x in %s"
0x18002d111  mov     r8d, ebx
0x18002d114  lea     r9, aCsecretstorage; "CSecretStorage::Retrieve"
0x18002d11b  mov     ecx, 8; int
0x18002d120  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d125  jmp     loc_18002D297
0x18002d12a  mov     rdx, [rdi]; lpValueName
0x18002d12d  lea     rax, [rbp+cbData]
0x18002d131  mov     rcx, [rbp+hKey]; hKey
0x18002d135  lea     r9, [rbp+Type]; lpType
0x18002d139  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18002d13e  xor     r8d, r8d; lpReserved
0x18002d141  mov     [rsp+78h+phkResult], 0; lpData
0x18002d14a  call    cs:__imp_RegQueryValueExW
0x18002d151  nop     dword ptr [rax+rax+00h]
0x18002d156  mov     ebx, eax
0x18002d158  test    eax, eax
0x18002d15a  jle     short loc_18002D162
0x18002d15c  movzx   ebx, ax
0x18002d15f  or      ebx, r12d
0x18002d162  test    ebx, ebx
0x18002d164  jns     short loc_18002D16F
0x18002d166  lea     rdx, aRegqueryvaluee_1; "RegQueryValueEx failed: 0x%x in %s"
0x18002d16d  jmp     short loc_18002D111
0x18002d16f  mov     edx, [rbp+cbData]; uBytes
0x18002d172  mov     ecx, 40h ; '@'; uFlags
0x18002d177  call    cs:__imp_LocalAlloc
0x18002d17e  nop     dword ptr [rax+rax+00h]
0x18002d183  mov     [rbp+lpData], rax
0x18002d187  test    rax, rax
0x18002d18a  jnz     short loc_18002D196
0x18002d18c  mov     ebx, 8007000Eh
0x18002d191  jmp     loc_18002D297
0x18002d196  mov     rdx, [rdi]; lpValueName
0x18002d199  lea     rax, [rbp+cbData]
0x18002d19d  mov     rcx, [rbp+hKey]; hKey
0x18002d1a1  lea     r9, [rbp+Type]; lpType
0x18002d1a5  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18002d1aa  xor     r8d, r8d; lpReserved
0x18002d1ad  mov     rax, [rbp+lpData]
0x18002d1b1  mov     [rsp+78h+phkResult], rax; lpData
0x18002d1b6  call    cs:__imp_RegQueryValueExW
0x18002d1bd  nop     dword ptr [rax+rax+00h]
0x18002d1c2  mov     ebx, eax
0x18002d1c4  test    eax, eax
0x18002d1c6  jle     short loc_18002D1CE
0x18002d1c8  movzx   ebx, ax
0x18002d1cb  or      ebx, r12d
0x18002d1ce  test    ebx, ebx
0x18002d1d0  js      short loc_18002D166
0x18002d1d2  mov     r8d, [rbp+Type]
0x18002d1d6  cmp     r8d, 3
0x18002d1da  jz      short loc_18002D1F7
0x18002d1dc  lea     rdx, aInvalidRegistr; "Invalid registry type, expecting REG_BI"...
0x18002d1e3  mov     ecx, 8; int
0x18002d1e8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d1ed  mov     ebx, 8000FFFFh
0x18002d1f2  jmp     loc_18002D297
0x18002d1f7  lea     rax, [rbp+var_20]
0x18002d1fb  xor     r9d, r9d; pvReserved
0x18002d1fe  mov     [rsp+78h+pDataOut], rax; pDataOut
0x18002d203  lea     rcx, [rbp+cbData]; pDataIn
0x18002d207  mov     dword ptr [rsp+78h+lpcbData], 1; dwFlags
0x18002d20f  xor     r8d, r8d; pOptionalEntropy
0x18002d212  xor     edx, edx; ppszDataDescr
0x18002d214  mov     [rsp+78h+phkResult], 0; pPromptStruct
0x18002d21d  call    cs:__imp_CryptUnprotectData
0x18002d224  nop     dword ptr [rax+rax+00h]
0x18002d229  test    eax, eax
0x18002d22b  jnz     short loc_18002D25B
0x18002d22d  call    cs:__imp_GetLastError
0x18002d234  nop     dword ptr [rax+rax+00h]
0x18002d239  mov     ebx, eax
0x18002d23b  test    eax, eax
0x18002d23d  jle     short loc_18002D245
0x18002d23f  movzx   ebx, ax
0x18002d242  or      ebx, r12d
0x18002d245  mov     r8d, ebx
0x18002d248  lea     rdx, aCryptunprotect_2; "CryptUnprotectData failed: 0x%x"
0x18002d24f  mov     ecx, 8; int
0x18002d254  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d259  jmp     short loc_18002D297
0x18002d25b  test    r14, r14
0x18002d25e  jnz     short loc_18002D267
0x18002d260  mov     eax, [rbp+var_20.cbData]
0x18002d263  mov     [rsi], eax
0x18002d265  jmp     short loc_18002D297
0x18002d267  mov     edi, [rbp+var_20.cbData]
0x18002d26a  cmp     [rsi], edi
0x18002d26c  jnb     short loc_18002D286
0x18002d26e  lea     rdx, aInsufficientIn; "Insufficient input buffer"
0x18002d275  mov     ecx, 8; int
0x18002d27a  mov     ebx, 8007007Ah
0x18002d27f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d284  jmp     short loc_18002D260
0x18002d286  mov     rdx, [rbp+var_20.pbData]; Src
0x18002d28a  mov     r8, rdi; Size
0x18002d28d  mov     rcx, r14; void *
0x18002d290  call    memcpy_0
0x18002d295  mov     [rsi], edi
0x18002d297  mov     rcx, [rbp+lpData]; hMem
0x18002d29b  test    rcx, rcx
0x18002d29e  jz      short loc_18002D2AC
0x18002d2a0  call    cs:__imp_LocalFree
0x18002d2a7  nop     dword ptr [rax+rax+00h]
0x18002d2ac  mov     rcx, [rbp+var_20.pbData]; hMem
0x18002d2b0  test    rcx, rcx
0x18002d2b3  jz      short loc_18002D2C1
0x18002d2b5  call    cs:__imp_LocalFree
0x18002d2bc  nop     dword ptr [rax+rax+00h]
0x18002d2c1  mov     rcx, [rbp+hKey]; hKey
0x18002d2c5  test    rcx, rcx
0x18002d2c8  jz      short loc_18002D2D6
0x18002d2ca  call    cs:__imp_RegCloseKey
0x18002d2d1  nop     dword ptr [rax+rax+00h]
0x18002d2d6  mov     eax, ebx
0x18002d2d8  add     rsp, 78h
0x18002d2dc  pop     r14
0x18002d2de  pop     r12
0x18002d2e0  pop     rdi
0x18002d2e1  pop     rsi
0x18002d2e2  pop     rbx
0x18002d2e3  pop     rbp
0x18002d2e4  retn
```
