# CSecretStorage::Store(uchar *,ulong)

- ea: `0x18002bc98`
- end: `0x18002bdee`
- name: `?Store@CSecretStorage@@QEAAJPEAEK@Z`
- size: `342`
- prototype: `__int64 __fastcall(CSecretStorage *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005d644`

## callees

- `0x180009940`
- `0x18002bc98`
- `0x180033854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdb8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bd75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bd75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bdcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bdcd`
- `CRYPT32!CryptProtectData` at `0x18002bcf9`
- `CRYPT32!CryptProtectData` at `0x18002bcf9`

## string_xrefs

- `0x18002bd4c`: `CreateKey failed: 0x%x in %s`
- `0x18002bd97`: `RegSetValueEx failed: 0x%x in %s`

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
0x18002bc98  mov     r11, rsp
0x18002bc9b  mov     [r11+8], rbx
0x18002bc9f  mov     [r11+18h], rdi
0x18002bca3  push    rbp
0x18002bca4  mov     rbp, rsp
0x18002bca7  sub     rsp, 60h
0x18002bcab  lea     rax, [rbp+cbData]
0x18002bcaf  mov     [rbp+pDataIn.pbData], rdx
0x18002bcb3  mov     [r11-38h], rax
0x18002bcb7  mov     rdi, rcx
0x18002bcba  mov     [rbp+pDataIn.cbData], r8d
0x18002bcbe  lea     rcx, [rbp+pDataIn]; pDataIn
0x18002bcc2  mov     [rsp+60h+dwFlags], 1; dwFlags
0x18002bcca  xor     r9d, r9d; pvReserved
0x18002bccd  xor     r8d, r8d; pOptionalEntropy
0x18002bcd0  mov     qword ptr [r11-48h], 0
0x18002bcd8  xor     edx, edx; szDataDescr
0x18002bcda  mov     dword ptr [rbp+pDataIn+4], 0
0x18002bce1  mov     qword ptr [rbp+cbData], 0
0x18002bce9  mov     [rbp+hMem], 0
0x18002bcf1  mov     [rbp+hKey], 0
0x18002bcf9  call    cs:__imp_CryptProtectData
0x18002bd00  nop     dword ptr [rax+rax+00h]
0x18002bd05  test    eax, eax
0x18002bd07  jnz     short loc_18002BD3A
0x18002bd09  call    cs:__imp_GetLastError
0x18002bd10  nop     dword ptr [rax+rax+00h]
0x18002bd15  mov     ebx, eax
0x18002bd17  test    eax, eax
0x18002bd19  jle     short loc_18002BD24
0x18002bd1b  movzx   ebx, ax
0x18002bd1e  or      ebx, 80070000h
0x18002bd24  mov     r8d, ebx
0x18002bd27  lea     rdx, aCryptprotectda_0; "CryptProtectData failed: 0x%x"
0x18002bd2e  mov     ecx, 8; int
0x18002bd33  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002bd38  jmp     short loc_18002BDAF
0x18002bd3a  lea     rcx, [rbp+hKey]; phkResult
0x18002bd3e  call    ?CreateStorageKey@CSecretStorage@@CAJPEAPEAUHKEY__@@@Z; CSecretStorage::CreateStorageKey(HKEY__ * *)
0x18002bd43  mov     ebx, eax
0x18002bd45  test    eax, eax
0x18002bd47  jns     short loc_18002BD55
0x18002bd49  mov     r8d, eax
0x18002bd4c  lea     rdx, aCreatekeyFaile; "CreateKey failed: 0x%x in %s"
0x18002bd53  jmp     short loc_18002BD9E
0x18002bd55  mov     eax, [rbp+cbData]
0x18002bd58  mov     r9d, 3; dwType
0x18002bd5e  mov     rdx, [rdi]; lpValueName
0x18002bd61  xor     r8d, r8d; Reserved
0x18002bd64  mov     rcx, [rbp+hKey]; hKey
0x18002bd68  mov     [rsp+60h+dwFlags], eax; cbData
0x18002bd6c  mov     rax, [rbp+hMem]
0x18002bd70  mov     [rsp+60h+lpData], rax; lpData
0x18002bd75  call    cs:__imp_RegSetValueExW
0x18002bd7c  nop     dword ptr [rax+rax+00h]
0x18002bd81  mov     ebx, eax
0x18002bd83  test    eax, eax
0x18002bd85  jle     short loc_18002BD90
0x18002bd87  movzx   ebx, ax
0x18002bd8a  or      ebx, 80070000h
0x18002bd90  test    ebx, ebx
0x18002bd92  jns     short loc_18002BDAF
0x18002bd94  mov     r8d, ebx
0x18002bd97  lea     rdx, aRegsetvalueexF; "RegSetValueEx failed: 0x%x in %s"
0x18002bd9e  lea     r9, aCsecretstorage_1; "CSecretStorage::Store"
0x18002bda5  mov     ecx, 8; int
0x18002bdaa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002bdaf  mov     rcx, [rbp+hMem]; hMem
0x18002bdb3  test    rcx, rcx
0x18002bdb6  jz      short loc_18002BDC4
0x18002bdb8  call    cs:__imp_LocalFree
0x18002bdbf  nop     dword ptr [rax+rax+00h]
0x18002bdc4  mov     rcx, [rbp+hKey]; hKey
0x18002bdc8  test    rcx, rcx
0x18002bdcb  jz      short loc_18002BDD9
0x18002bdcd  call    cs:__imp_RegCloseKey
0x18002bdd4  nop     dword ptr [rax+rax+00h]
0x18002bdd9  lea     r11, [rsp+60h+var_s0]
0x18002bdde  mov     eax, ebx
0x18002bde0  mov     rbx, [r11+10h]
0x18002bde4  mov     rdi, [r11+20h]
0x18002bde8  mov     rsp, r11
0x18002bdeb  pop     rbp
0x18002bdec  retn
```
