# CInventoryInstance::PersistFileToDisk(wchar_t const *,uint,wchar_t const *)

- ea: `0x1801e0dd0`
- end: `0x1801e1031`
- name: `?PersistFileToDisk@CInventoryInstance@@AEAAXPEB_WI0@Z`
- size: `609`
- prototype: `void(CInventoryInstance *__hidden this, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801df40c`

## callees

- `0x18000c6b4`
- `0x180014964`
- `0x180127fb8`
- `0x180128cf4`
- `0x18012b618`
- `0x18012d944`
- `0x1801e0dd0`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0fbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e100a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e100a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e0e90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e0e90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e0e47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e0e47`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801e0f6c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801e0fb5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801e0f6c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801e0fb5`

## string_xrefs

- `0x1801e0e39`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1801e0f16`: `Inventory: could not create the result file`
- `0x1801e0ebe`: `_result.xml`
- `0x1801e0fdd`: `Inventory: Write file`
- `0x1801e0f94`: `Inventory: Write file failed to write unicode header`

## pseudocode

```c
void __fastcall CInventoryInstance::PersistFileToDisk(
        const wchar_t *this,
        const wchar_t *a2,
        int a3,
        const wchar_t *a4)
{
  int v4; // ebx
  HKEY v9; // rcx
  int v10; // eax
  int v11; // eax
  HANDLE v12; // rcx
  HANDLE v13; // rbx
  signed int v14; // eax
  signed int v15; // ecx
  signed int LastError; // eax
  signed int v17; // ecx
  struct _SECURITY_ATTRIBUTES *v18; // [rsp+28h] [rbp-D8h]
  void *v19; // [rsp+40h] [rbp-C0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-A8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v23[264]; // [rsp+70h] [rbp-90h] BYREF

  v4 = 0;
  hKey = 0;
  NumberOfBytesWritten = 0;
  if ( (unsigned int)AreTestKeysAllowed(1)
    && !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
          0,
          0x20019u,
          &hKey) )
  {
    v9 = hKey;
    LODWORD(hFile) = 0;
    if ( hKey )
    {
      if ( RegQueryDwordValue(hKey, L"PersistInventoryResultFile", (unsigned int *)&hFile) >= 0 )
      {
        v10 = (int)hFile;
      }
      else
      {
        v10 = 0;
        LODWORD(hFile) = 0;
      }
      v9 = hKey;
      if ( v10 == 1 )
        v4 = 1;
    }
    RegCloseKey(v9);
    if ( v4 )
    {
      if ( (int)WUPathCchCombine(v23, 0x104u, this + 40, a4) >= 0
        && (int)StringCchCatW(v23, 0x104u, L"_result.xml") >= 0 )
      {
        hFile = 0;
        v11 = SafeCreateFile(&hFile, 0, v23, 0x40000000u, 0, v18, 2u, 0x80u, v19);
        if ( v11 < 0 )
        {
          WUTrace(0, 0, 0x20000, 5, v11, L"Inventory: could not create the result file");
          v12 = hFile;
          if ( !hFile )
            return;
          goto LABEL_29;
        }
        v13 = hFile;
        if ( WriteFile(hFile, &qword_1802D4490, 2u, &NumberOfBytesWritten, 0) )
        {
          if ( !WriteFile(v13, a2, 2 * a3, &NumberOfBytesWritten, 0) )
          {
            LastError = GetLastError();
            v17 = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              v17 = LastError;
            if ( v17 >= 0 )
              v17 = -2147418113;
            WUTrace(0, 0, 0x20000, 5, v17, L"Inventory: Write file");
          }
        }
        else
        {
          v14 = GetLastError();
          v15 = (unsigned __int16)v14 | 0x80070000;
          if ( v14 <= 0 )
            v15 = v14;
          if ( v15 >= 0 )
            v15 = -2147418113;
          WUTrace(0, 0, 0x20000, 5, v15, L"Inventory: Write file failed to write unicode header");
        }
        if ( v13 )
        {
          v12 = v13;
LABEL_29:
          CloseHandle(v12);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1801e0dd0  push    rbp
0x1801e0dd2  push    rbx
0x1801e0dd3  push    rsi
0x1801e0dd4  push    rdi
0x1801e0dd5  push    r13
0x1801e0dd7  push    r14
0x1801e0dd9  push    r15
0x1801e0ddb  lea     rbp, [rsp-190h]
0x1801e0de3  sub     rsp, 290h
0x1801e0dea  mov     rax, cs:__security_cookie
0x1801e0df1  xor     rax, rsp
0x1801e0df4  mov     [rbp+1C0h+var_40], rax
0x1801e0dfb  xor     ebx, ebx
0x1801e0dfd  mov     rdi, rcx
0x1801e0e00  mov     rsi, r9
0x1801e0e03  mov     [rsp+2C0h+hKey], rbx
0x1801e0e08  mov     r15d, r8d
0x1801e0e0b  mov     [rsp+2C0h+NumberOfBytesWritten], ebx
0x1801e0e0f  mov     r14, rdx
0x1801e0e12  lea     r13d, [rbx+1]
0x1801e0e16  mov     cl, r13b; bool
0x1801e0e19  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1801e0e1e  test    eax, eax
0x1801e0e20  jz      loc_1801E1010
0x1801e0e26  lea     rax, [rsp+2C0h+hKey]
0x1801e0e2b  mov     r9d, 20019h; samDesired
0x1801e0e31  xor     r8d, r8d; ulOptions
0x1801e0e34  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801e0e39  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801e0e40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801e0e47  call    cs:__imp_RegOpenKeyExW
0x1801e0e4d  test    eax, eax
0x1801e0e4f  jnz     loc_1801E1010
0x1801e0e55  mov     rcx, [rsp+2C0h+hKey]; HKEY
0x1801e0e5a  mov     dword ptr [rsp+2C0h+hFile], ebx
0x1801e0e5e  test    rcx, rcx
0x1801e0e61  jz      short loc_1801E0E90
0x1801e0e63  lea     r8, [rsp+2C0h+hFile]; unsigned int *
0x1801e0e68  lea     rdx, aPersistinvento; "PersistInventoryResultFile"
0x1801e0e6f  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x1801e0e74  test    eax, eax
0x1801e0e76  jns     short loc_1801E0E80
0x1801e0e78  xor     eax, eax
0x1801e0e7a  mov     dword ptr [rsp+2C0h+hFile], eax
0x1801e0e7e  jmp     short loc_1801E0E84
0x1801e0e80  mov     eax, dword ptr [rsp+2C0h+hFile]
0x1801e0e84  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1801e0e89  cmp     eax, r13d
0x1801e0e8c  cmovz   ebx, r13d
0x1801e0e90  call    cs:__imp_RegCloseKey
0x1801e0e96  test    ebx, ebx
0x1801e0e98  jz      loc_1801E1010
0x1801e0e9e  mov     ebx, 104h
0x1801e0ea3  lea     r8, [rdi+50h]; wchar_t *
0x1801e0ea7  mov     edx, ebx; unsigned int
0x1801e0ea9  lea     rcx, [rsp+2C0h+var_250]; wchar_t *
0x1801e0eae  mov     r9, rsi; wchar_t *
0x1801e0eb1  call    ?WUPathCchCombine@@YAJPEA_WKPEB_W1@Z; WUPathCchCombine(wchar_t *,ulong,wchar_t const *,wchar_t const *)
0x1801e0eb6  test    eax, eax
0x1801e0eb8  js      loc_1801E1010
0x1801e0ebe  lea     r8, aResultXml; "_result.xml"
0x1801e0ec5  mov     edx, ebx; unsigned __int64
0x1801e0ec7  lea     rcx, [rsp+2C0h+var_250]; wchar_t *
0x1801e0ecc  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1801e0ed1  test    eax, eax
0x1801e0ed3  js      loc_1801E1010
0x1801e0ed9  mov     [rsp+2C0h+var_288], 80h; unsigned int
0x1801e0ee1  lea     r8, [rsp+2C0h+var_250]; wchar_t *
0x1801e0ee6  mov     ebx, 2
0x1801e0eeb  mov     [rsp+2C0h+hFile], 0
0x1801e0ef4  mov     [rsp+2C0h+var_290], ebx; unsigned int
0x1801e0ef8  lea     rcx, [rsp+2C0h+hFile]; void **
0x1801e0efd  mov     r9d, 40000000h; unsigned int
0x1801e0f03  mov     dword ptr [rsp+2C0h+phkResult], 0; unsigned int
0x1801e0f0b  xor     edx, edx; unsigned int
0x1801e0f0d  call    ?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x1801e0f12  test    eax, eax
0x1801e0f14  jns     short loc_1801E0F4C
0x1801e0f16  lea     rcx, aInventoryCould; "Inventory: could not create the result "...
0x1801e0f1d  xor     edx, edx
0x1801e0f1f  mov     [rsp+2C0h+var_298], rcx
0x1801e0f24  lea     r9d, [rbx+3]
0x1801e0f28  xor     ecx, ecx
0x1801e0f2a  mov     dword ptr [rsp+2C0h+phkResult], eax
0x1801e0f2e  mov     r8d, 20000h
0x1801e0f34  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e0f39  mov     rcx, [rsp+2C0h+hFile]
0x1801e0f3e  test    rcx, rcx
0x1801e0f41  jz      loc_1801E1010
0x1801e0f47  jmp     loc_1801E100A
0x1801e0f4c  mov     r8d, ebx; nNumberOfBytesToWrite
0x1801e0f4f  mov     [rsp+2C0h+phkResult], 0; lpOverlapped
0x1801e0f58  mov     rbx, [rsp+2C0h+hFile]
0x1801e0f5d  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801e0f62  mov     rcx, rbx; hFile
0x1801e0f65  lea     rdx, qword_1802D4490; lpBuffer
0x1801e0f6c  call    cs:__imp_WriteFile
0x1801e0f72  test    eax, eax
0x1801e0f74  jnz     short loc_1801E0F9D
0x1801e0f76  call    cs:__imp_GetLastError
0x1801e0f7c  movzx   ecx, ax
0x1801e0f7f  or      ecx, 80070000h
0x1801e0f85  test    eax, eax
0x1801e0f87  cmovle  ecx, eax
0x1801e0f8a  mov     eax, 8000FFFFh
0x1801e0f8f  test    ecx, ecx
0x1801e0f91  cmovns  ecx, eax
0x1801e0f94  lea     rax, aInventoryWrite; "Inventory: Write file failed to write u"...
0x1801e0f9b  jmp     short loc_1801E0FE4
0x1801e0f9d  lea     r8d, [r15+r15]; nNumberOfBytesToWrite
0x1801e0fa1  mov     [rsp+2C0h+phkResult], 0; lpOverlapped
0x1801e0faa  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801e0faf  mov     rdx, r14; lpBuffer
0x1801e0fb2  mov     rcx, rbx; hFile
0x1801e0fb5  call    cs:__imp_WriteFile
0x1801e0fbb  test    eax, eax
0x1801e0fbd  jnz     short loc_1801E1002
0x1801e0fbf  call    cs:__imp_GetLastError
0x1801e0fc5  movzx   ecx, ax
0x1801e0fc8  or      ecx, 80070000h
0x1801e0fce  test    eax, eax
0x1801e0fd0  cmovle  ecx, eax
0x1801e0fd3  mov     eax, 8000FFFFh
0x1801e0fd8  test    ecx, ecx
0x1801e0fda  cmovns  ecx, eax
0x1801e0fdd  lea     rax, aInventoryWrite_0; "Inventory: Write file"
0x1801e0fe4  mov     [rsp+2C0h+var_298], rax
0x1801e0fe9  mov     r9d, 5
0x1801e0fef  mov     dword ptr [rsp+2C0h+phkResult], ecx
0x1801e0ff3  mov     r8d, 20000h
0x1801e0ff9  xor     ecx, ecx
0x1801e0ffb  xor     edx, edx
0x1801e0ffd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e1002  test    rbx, rbx
0x1801e1005  jz      short loc_1801E1010
0x1801e1007  mov     rcx, rbx; hObject
0x1801e100a  call    cs:__imp_CloseHandle
0x1801e1010  mov     rcx, [rbp+1C0h+var_40]
0x1801e1017  xor     rcx, rsp; StackCookie
0x1801e101a  call    __security_check_cookie
0x1801e101f  add     rsp, 290h
0x1801e1026  pop     r15
0x1801e1028  pop     r14
0x1801e102a  pop     r13
0x1801e102c  pop     rdi
0x1801e102d  pop     rsi
0x1801e102e  pop     rbx
0x1801e102f  pop     rbp
0x1801e1030  retn
```
