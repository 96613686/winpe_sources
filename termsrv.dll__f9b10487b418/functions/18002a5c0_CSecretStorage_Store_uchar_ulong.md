# CSecretStorage::Store(uchar *,ulong)

- ea: `0x18002a5c0`
- end: `0x18002a6f7`
- name: `?Store@CSecretStorage@@QEAAJPEAEK@Z`
- size: `311`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int8 *, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005a968`

## callees

- `0x18000a210`
- `0x18002a5c0`
- `0x180031b3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a62b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a62b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a691`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a691`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a6dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a6dd`
- `CRYPT32!CryptProtectData` at `0x18002a621`
- `CRYPT32!CryptProtectData` at `0x18002a621`

## string_xrefs

- `0x18002a668`: `CreateKey failed: 0x%x in %s`
- `0x18002a6ad`: `RegSetValueEx failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSecretStorage::Store(LPCWSTR *this, unsigned __int8 *a2, DWORD a3)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  int v6; // eax
  LSTATUS v7; // eax
  DATA_BLOB cbData; // [rsp+40h] [rbp-20h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+18h] BYREF

  pDataIn.pbData = a2;
  pDataIn.cbData = a3;
  *(&pDataIn.cbData + 1) = 0;
  *(_QWORD *)&cbData.cbData = 0;
  cbData.pbData = 0;
  hKey = 0;
  if ( CryptProtectData(&pDataIn, 0, 0, 0, 0, 1u, &cbData) )
  {
    v6 = CSecretStorage::CreateStorageKey(&hKey);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = RegSetValueExW(hKey, *this, 0, 3u, cbData.pbData, cbData.cbData);
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
        _DbgPrintMessage(8, "RegSetValueEx failed: 0x%x in %s", v5, "CSecretStorage::Store");
    }
    else
    {
      _DbgPrintMessage(8, "CreateKey failed: 0x%x in %s", (unsigned int)v6, "CSecretStorage::Store");
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "CryptProtectData failed: 0x%x", v5);
  }
  if ( cbData.pbData )
    LocalFree(cbData.pbData);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18002a5c0  mov     r11, rsp
0x18002a5c3  mov     [r11+8], rbx
0x18002a5c7  mov     [r11+18h], rdi
0x18002a5cb  push    rbp
0x18002a5cc  mov     rbp, rsp
0x18002a5cf  sub     rsp, 60h
0x18002a5d3  lea     rax, [rbp+cbData]
0x18002a5d7  mov     [rbp+pDataIn.pbData], rdx
0x18002a5db  mov     [r11-38h], rax
0x18002a5df  mov     rdi, rcx
0x18002a5e2  mov     [rbp+pDataIn.cbData], r8d
0x18002a5e6  lea     rcx, [rbp+pDataIn]; pDataIn
0x18002a5ea  mov     [rsp+60h+dwFlags], 1; dwFlags
0x18002a5f2  xor     r9d, r9d; pvReserved
0x18002a5f5  xor     r8d, r8d; pOptionalEntropy
0x18002a5f8  mov     qword ptr [r11-48h], 0
0x18002a600  xor     edx, edx; szDataDescr
0x18002a602  mov     dword ptr [rbp+pDataIn+4], 0
0x18002a609  mov     qword ptr [rbp+cbData], 0
0x18002a611  mov     [rbp+hMem], 0
0x18002a619  mov     [rbp+hKey], 0
0x18002a621  call    cs:__imp_CryptProtectData
0x18002a627  test    eax, eax
0x18002a629  jnz     short loc_18002A656
0x18002a62b  call    cs:__imp_GetLastError
0x18002a631  mov     ebx, eax
0x18002a633  test    eax, eax
0x18002a635  jle     short loc_18002A640
0x18002a637  movzx   ebx, ax
0x18002a63a  or      ebx, 80070000h
0x18002a640  mov     r8d, ebx
0x18002a643  lea     rdx, aCryptprotectda_0; "CryptProtectData failed: 0x%x"
0x18002a64a  mov     ecx, 8; int
0x18002a64f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a654  jmp     short loc_18002A6C5
0x18002a656  lea     rcx, [rbp+hKey]; phkResult
0x18002a65a  call    ?CreateStorageKey@CSecretStorage@@CAJPEAPEAUHKEY__@@@Z; CSecretStorage::CreateStorageKey(HKEY__ * *)
0x18002a65f  mov     ebx, eax
0x18002a661  test    eax, eax
0x18002a663  jns     short loc_18002A671
0x18002a665  mov     r8d, eax
0x18002a668  lea     rdx, aCreatekeyFaile; "CreateKey failed: 0x%x in %s"
0x18002a66f  jmp     short loc_18002A6B4
0x18002a671  mov     eax, [rbp+cbData]
0x18002a674  mov     r9d, 3; dwType
0x18002a67a  mov     rdx, [rdi]; lpValueName
0x18002a67d  xor     r8d, r8d; Reserved
0x18002a680  mov     rcx, [rbp+hKey]; hKey
0x18002a684  mov     [rsp+60h+dwFlags], eax; cbData
0x18002a688  mov     rax, [rbp+hMem]
0x18002a68c  mov     [rsp+60h+lpData], rax; lpData
0x18002a691  call    cs:__imp_RegSetValueExW
0x18002a697  mov     ebx, eax
0x18002a699  test    eax, eax
0x18002a69b  jle     short loc_18002A6A6
0x18002a69d  movzx   ebx, ax
0x18002a6a0  or      ebx, 80070000h
0x18002a6a6  test    ebx, ebx
0x18002a6a8  jns     short loc_18002A6C5
0x18002a6aa  mov     r8d, ebx
0x18002a6ad  lea     rdx, aRegsetvalueexF; "RegSetValueEx failed: 0x%x in %s"
0x18002a6b4  lea     r9, aCsecretstorage_1; "CSecretStorage::Store"
0x18002a6bb  mov     ecx, 8; int
0x18002a6c0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a6c5  mov     rcx, [rbp+hMem]; hMem
0x18002a6c9  test    rcx, rcx
0x18002a6cc  jz      short loc_18002A6D4
0x18002a6ce  call    cs:__imp_LocalFree
0x18002a6d4  mov     rcx, [rbp+hKey]; hKey
0x18002a6d8  test    rcx, rcx
0x18002a6db  jz      short loc_18002A6E3
0x18002a6dd  call    cs:__imp_RegCloseKey
0x18002a6e3  lea     r11, [rsp+60h+var_s0]
0x18002a6e8  mov     eax, ebx
0x18002a6ea  mov     rbx, [r11+10h]
0x18002a6ee  mov     rdi, [r11+20h]
0x18002a6f2  mov     rsp, r11
0x18002a6f5  pop     rbp
0x18002a6f6  retn
```
