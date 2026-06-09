# StoreADialingRuleInReg

- ea: `0x18001c490`
- end: `0x18001c73a`
- name: `StoreADialingRuleInReg`
- size: `682`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800030a4`

## callees

- `0x180001600`
- `0x18001c490`
- `0x18001c8a4`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c706`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c706`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c5b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c5b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c606`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c62d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c653`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c68c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c6c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c6fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c606`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c62d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c653`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c68c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c6c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c6fb`
- `KERNEL32!FreeLibrary` at `0x18001c569`
- `KERNEL32!FreeLibrary` at `0x18001c569`
- `KERNEL32!LoadLibraryW` at `0x18001c4e5`
- `KERNEL32!LoadLibraryW` at `0x18001c4e5`
- `KERNEL32!GetLastError` at `0x18001c539`
- `KERNEL32!GetLastError` at `0x18001c539`
- `USER32!LoadStringW` at `0x18001c52d`
- `USER32!LoadStringW` at `0x18001c52d`

## string_xrefs

- `0x18001c4f7`: `Failed to load ResDll=%ls for ResId=%ld!`
- `0x18001c542`: `LoadString failed for ResId=%ld with GetLastError %ld`

## pseudocode

```c
__int64 __fastcall StoreADialingRuleInReg(HKEY hKey, unsigned int *a2)
{
  __int64 v4; // rsi
  HMODULE LibraryW; // rbx
  unsigned int v7; // ebx
  DWORD LastError; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  const BYTE *v11; // rcx
  __int64 v12; // rax
  const BYTE *v13; // rcx
  __int64 v14; // rax
  const BYTE *v15; // rdx
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[20]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[256]; // [rsp+80h] [rbp-80h] BYREF

  hKeya = 0;
  if ( a2[3] )
  {
    v4 = (int)a2[3];
    LibraryW = LoadLibraryW((LPCWSTR)gaTapiNameResDlls[v4]);
    if ( !LibraryW )
    {
      TRACELogPrint(65538, "Failed to load ResDll=%ls for ResId=%ld!", (const wchar_t *)gaTapiNameResDlls[v4], a2[2]);
      return 0;
    }
  }
  else
  {
    LibraryW = ghInstance;
  }
  if ( LoadStringW(LibraryW, a2[2], Buffer, 256) <= 0 )
  {
    v7 = a2[2];
    LastError = GetLastError();
    TRACELogPrint(65538, "LoadString failed for ResId=%ld with GetLastError %ld", v7, LastError);
    return 0;
  }
  if ( LibraryW && LibraryW != ghInstance )
    FreeLibrary(LibraryW);
  StringCbPrintfW(pszDest, 0x28u, L"%ld", *a2);
  if ( RegCreateKeyExW(hKey, pszDest, 0, 0, 0, 0x20006u, 0, &hKeya, 0) )
    return 0;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( Buffer[v10] );
  RegSetValueExW(hKeya, L"Name", 0, 1u, (const BYTE *)Buffer, 2 * v10 + 2);
  RegSetValueExW(hKeya, L"NameResourceId", 0, 4u, (const BYTE *)a2 + 8, 4u);
  RegSetValueExW(hKeya, L"CountryCode", 0, 4u, (const BYTE *)a2 + 4, 4u);
  v11 = (const BYTE *)*((_QWORD *)a2 + 2);
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)&v11[2 * v12] );
  RegSetValueExW(hKeya, L"SameAreaRule", 0, 1u, v11, 2 * v12 + 2);
  v13 = (const BYTE *)*((_QWORD *)a2 + 3);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)&v13[2 * v14] );
  RegSetValueExW(hKeya, L"LongDistanceRule", 0, 1u, v13, 2 * v14 + 2);
  v15 = (const BYTE *)*((_QWORD *)a2 + 4);
  do
    ++v9;
  while ( *(_WORD *)&v15[2 * v9] );
  RegSetValueExW(hKeya, L"InternationalRule", 0, 1u, v15, 2 * v9 + 2);
  RegCloseKey(hKeya);
  return 1;
}

```

## disassembly

```asm
0x18001c490  mov     [rsp-8+arg_10], rbx
0x18001c495  mov     [rsp-8+arg_18], rsi
0x18001c49a  push    rbp
0x18001c49b  push    rdi
0x18001c49c  push    r12
0x18001c49e  push    r14
0x18001c4a0  push    r15
0x18001c4a2  lea     rbp, [rsp-190h]
0x18001c4aa  sub     rsp, 290h
0x18001c4b1  mov     rax, cs:__security_cookie
0x18001c4b8  xor     rax, rsp
0x18001c4bb  mov     [rbp+1B0h+var_30], rax
0x18001c4c2  xor     r15d, r15d
0x18001c4c5  mov     rdi, rdx
0x18001c4c8  mov     r14, rcx
0x18001c4cb  mov     [rsp+2B0h+hKey], r15
0x18001c4d0  cmp     [rdx+0Ch], r15d
0x18001c4d4  jz      short loc_18001C513
0x18001c4d6  movsxd  rsi, dword ptr [rdx+0Ch]
0x18001c4da  lea     r12, gaTapiNameResDlls
0x18001c4e1  mov     rcx, [r12+rsi*8]; lpLibFileName
0x18001c4e5  call    cs:__imp_LoadLibraryW
0x18001c4eb  mov     rbx, rax
0x18001c4ee  test    rax, rax
0x18001c4f1  jnz     short loc_18001C51A
0x18001c4f3  mov     r9d, [rdi+8]
0x18001c4f7  lea     rdx, aFailedToLoadRe; "Failed to load ResDll=%ls for ResId=%ld"...
0x18001c4fe  mov     r8, [r12+rsi*8]
0x18001c502  mov     ecx, 10002h
0x18001c507  call    TRACELogPrint
0x18001c50c  xor     eax, eax
0x18001c50e  jmp     loc_18001C70F
0x18001c513  mov     rbx, cs:ghInstance
0x18001c51a  lea     rsi, [rdi+8]
0x18001c51e  mov     r9d, 100h; cchBufferMax
0x18001c524  mov     edx, [rsi]; uID
0x18001c526  lea     r8, [rbp+1B0h+Buffer]; lpBuffer
0x18001c52a  mov     rcx, rbx; hInstance
0x18001c52d  call    cs:__imp_LoadStringW
0x18001c533  test    eax, eax
0x18001c535  jg      short loc_18001C558
0x18001c537  mov     ebx, [rsi]
0x18001c539  call    cs:__imp_GetLastError
0x18001c53f  mov     r8d, ebx
0x18001c542  lea     rdx, aLoadstringFail; "LoadString failed for ResId=%ld with Ge"...
0x18001c549  mov     r9d, eax
0x18001c54c  mov     ecx, 10002h
0x18001c551  call    TRACELogPrint
0x18001c556  jmp     short loc_18001C50C
0x18001c558  test    rbx, rbx
0x18001c55b  jz      short loc_18001C56F
0x18001c55d  cmp     rbx, cs:ghInstance
0x18001c564  jz      short loc_18001C56F
0x18001c566  mov     rcx, rbx; hLibModule
0x18001c569  call    cs:__imp_FreeLibrary
0x18001c56f  mov     r9d, [rdi]
0x18001c572  lea     r8, aLd; "%ld"
0x18001c579  mov     edx, 28h ; '('; cbDest
0x18001c57e  lea     rcx, [rsp+2B0h+pszDest]; pszDest
0x18001c583  call    StringCbPrintfW
0x18001c588  mov     [rsp+2B0h+lpdwDisposition], r15; lpdwDisposition
0x18001c58d  lea     rax, [rsp+2B0h+hKey]
0x18001c592  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001c597  lea     rdx, [rsp+2B0h+pszDest]; lpSubKey
0x18001c59c  mov     [rsp+2B0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18001c5a1  xor     r9d, r9d; lpClass
0x18001c5a4  mov     [rsp+2B0h+samDesired], 20006h; samDesired
0x18001c5ac  xor     r8d, r8d; Reserved
0x18001c5af  mov     rcx, r14; hKey
0x18001c5b2  mov     [rsp+2B0h+dwOptions], r15d; dwOptions
0x18001c5b7  call    cs:__imp_RegCreateKeyExW
0x18001c5bd  test    eax, eax
0x18001c5bf  jnz     loc_18001C50C
0x18001c5c5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c5c9  lea     rcx, [rbp+1B0h+Buffer]
0x18001c5cd  mov     rax, rbx
0x18001c5d0  inc     rax
0x18001c5d3  cmp     [rcx+rax*2], r15w
0x18001c5d8  jnz     short loc_18001C5D0
0x18001c5da  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001c5df  lea     eax, ds:2[rax*2]
0x18001c5e6  mov     [rsp+2B0h+samDesired], eax; cbData
0x18001c5ea  lea     rdx, gszNameW; "Name"
0x18001c5f1  lea     rax, [rbp+1B0h+Buffer]
0x18001c5f5  mov     r12d, 1
0x18001c5fb  mov     r9d, r12d; dwType
0x18001c5fe  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x18001c603  xor     r8d, r8d; Reserved
0x18001c606  call    cs:__imp_RegSetValueExW
0x18001c60c  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001c611  lea     r14d, [r12+3]
0x18001c616  mov     [rsp+2B0h+samDesired], r14d; cbData
0x18001c61b  lea     rdx, gszNameResW; "NameResourceId"
0x18001c622  mov     r9d, r14d; dwType
0x18001c625  mov     qword ptr [rsp+2B0h+dwOptions], rsi; lpData
0x18001c62a  xor     r8d, r8d; Reserved
0x18001c62d  call    cs:__imp_RegSetValueExW
0x18001c633  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001c638  lea     rax, [rdi+4]
0x18001c63c  mov     [rsp+2B0h+samDesired], r14d; cbData
0x18001c641  lea     rdx, ValueName; "CountryCode"
0x18001c648  mov     r9d, r14d; dwType
0x18001c64b  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x18001c650  xor     r8d, r8d; Reserved
0x18001c653  call    cs:__imp_RegSetValueExW
0x18001c659  mov     rcx, [rdi+10h]
0x18001c65d  mov     rax, rbx
0x18001c660  inc     rax
0x18001c663  cmp     [rcx+rax*2], r15w
0x18001c668  jnz     short loc_18001C660
0x18001c66a  lea     eax, ds:2[rax*2]
0x18001c671  mov     r9d, r12d; dwType
0x18001c674  mov     [rsp+2B0h+samDesired], eax; cbData
0x18001c678  lea     rdx, gszSameAreaRuleW; "SameAreaRule"
0x18001c67f  mov     qword ptr [rsp+2B0h+dwOptions], rcx; lpData
0x18001c684  xor     r8d, r8d; Reserved
0x18001c687  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001c68c  call    cs:__imp_RegSetValueExW
0x18001c692  mov     rcx, [rdi+18h]
0x18001c696  mov     rax, rbx
0x18001c699  inc     rax
0x18001c69c  cmp     [rcx+rax*2], r15w
0x18001c6a1  jnz     short loc_18001C699
0x18001c6a3  lea     eax, ds:2[rax*2]
0x18001c6aa  mov     r9d, r12d; dwType
0x18001c6ad  mov     [rsp+2B0h+samDesired], eax; cbData
0x18001c6b1  lea     rdx, gszLongDistanceRuleW; "LongDistanceRule"
0x18001c6b8  mov     qword ptr [rsp+2B0h+dwOptions], rcx; lpData
0x18001c6bd  xor     r8d, r8d; Reserved
0x18001c6c0  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001c6c5  call    cs:__imp_RegSetValueExW
0x18001c6cb  mov     rdx, [rdi+20h]
0x18001c6cf  inc     rbx
0x18001c6d2  cmp     [rdx+rbx*2], r15w
0x18001c6d7  jnz     short loc_18001C6CF
0x18001c6d9  lea     ecx, ds:2[rbx*2]
0x18001c6e0  mov     r9d, r12d; dwType
0x18001c6e3  mov     [rsp+2B0h+samDesired], ecx; cbData
0x18001c6e7  xor     r8d, r8d; Reserved
0x18001c6ea  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001c6ef  mov     qword ptr [rsp+2B0h+dwOptions], rdx; lpData
0x18001c6f4  lea     rdx, gszInternationalRuleW; "InternationalRule"
0x18001c6fb  call    cs:__imp_RegSetValueExW
0x18001c701  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001c706  call    cs:__imp_RegCloseKey
0x18001c70c  mov     eax, r12d
0x18001c70f  mov     rcx, [rbp+1B0h+var_30]
0x18001c716  xor     rcx, rsp; StackCookie
0x18001c719  call    __security_check_cookie
0x18001c71e  lea     r11, [rsp+2B0h+var_20]
0x18001c726  mov     rbx, [r11+40h]
0x18001c72a  mov     rsi, [r11+48h]
0x18001c72e  mov     rsp, r11
0x18001c731  pop     r15
0x18001c733  pop     r14
0x18001c735  pop     r12
0x18001c737  pop     rdi
0x18001c738  pop     rbp
0x18001c739  retn
```
