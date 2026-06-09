# DllUnregisterServer

- ea: `0x18000cee0`
- end: `0x18000cfeb`
- name: `DllUnregisterServer`
- size: `267`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180005ae4`
- `0x18000ba74`
- `0x18000cee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cfd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cfd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cfae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cfae`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000cf77`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000cfc3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000cf77`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000cfc3`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const struct SHandlerEntry *v0; // rcx
  int v1; // ebx
  wchar_t *v4[4]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+10h] BYREF

  v1 = UnRegisterAHandler(v0);
  v4[0] = L"{e2403e98-663b-4df6-b234-687789db8560}";
  v4[1] = L"rtf filter";
  v4[2] = L"InprocServer32";
  v4[3] = L"RtfFilt.dll";
  if ( v1 )
  {
    DestroyKeyValues((LPCWSTR *)v4, 4);
  }
  else
  {
    v1 = DestroyKeyValues((LPCWSTR *)v4, 4);
    if ( !v1 )
    {
      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      v1 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L".rtf", 0, 0x2001Fu, &hKey);
      if ( !v1 )
        v1 = RegDeleteKeyW(hKey, L"PersistentHandler");
      goto LABEL_8;
    }
  }
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L".rtf", 0, 0x2001Fu, &hKey) )
    RegDeleteKeyW(hKey, L"PersistentHandler");
LABEL_8:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return v1 != 0;
}

```

## disassembly

```asm
0x18000cee0  mov     [rsp-8+arg_8], rbx
0x18000cee5  push    rbp
0x18000cee6  mov     rbp, rsp
0x18000cee9  sub     rsp, 50h
0x18000ceed  call    ?UnRegisterAHandler@@YAJAEBUSHandlerEntry@@@Z; UnRegisterAHandler(SHandlerEntry const &)
0x18000cef2  mov     ebx, eax
0x18000cef4  lea     rcx, [rbp+var_20]; wchar_t **
0x18000cef8  test    eax, eax
0x18000cefa  mov     edx, 4; int
0x18000ceff  mov     rax, cs:off_18001C478; "{e2403e98-663b-4df6-b234-687789db8560}"
0x18000cf06  mov     [rbp+var_20], rax
0x18000cf0a  mov     rax, cs:off_18001C480; "rtf filter"
0x18000cf11  mov     [rbp+var_18], rax
0x18000cf15  lea     rax, aInprocserver32; "InprocServer32"
0x18000cf1c  mov     [rbp+var_10], rax
0x18000cf20  mov     rax, cs:off_18001C488; "RtfFilt.dll"
0x18000cf27  mov     [rbp+var_8], rax
0x18000cf2b  jnz     short loc_18000CF81
0x18000cf2d  call    ?DestroyKeyValues@@YAJPEBQEB_WH@Z; DestroyKeyValues(wchar_t const * const *,int)
0x18000cf32  mov     ebx, eax
0x18000cf34  test    eax, eax
0x18000cf36  jnz     short loc_18000CF86
0x18000cf38  mov     rdx, cs:lpSubKey; lpSubKey
0x18000cf3f  lea     rax, [rbp+hKey]
0x18000cf43  mov     r9d, 2001Fh; samDesired
0x18000cf49  mov     [rsp+50h+phkResult], rax; phkResult
0x18000cf4e  xor     r8d, r8d; ulOptions
0x18000cf51  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x18000cf59  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000cf60  call    cs:__imp_RegOpenKeyExW
0x18000cf66  mov     ebx, eax
0x18000cf68  test    eax, eax
0x18000cf6a  jnz     short loc_18000CFC9
0x18000cf6c  mov     rcx, [rbp+hKey]; hKey
0x18000cf70  lea     rdx, SubKey; "PersistentHandler"
0x18000cf77  call    cs:__imp_RegDeleteKeyW
0x18000cf7d  mov     ebx, eax
0x18000cf7f  jmp     short loc_18000CFC9
0x18000cf81  call    ?DestroyKeyValues@@YAJPEBQEB_WH@Z; DestroyKeyValues(wchar_t const * const *,int)
0x18000cf86  mov     rdx, cs:lpSubKey; lpSubKey
0x18000cf8d  lea     rax, [rbp+hKey]
0x18000cf91  mov     r9d, 2001Fh; samDesired
0x18000cf97  mov     [rsp+50h+phkResult], rax; phkResult
0x18000cf9c  xor     r8d, r8d; ulOptions
0x18000cf9f  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x18000cfa7  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000cfae  call    cs:__imp_RegOpenKeyExW
0x18000cfb4  test    eax, eax
0x18000cfb6  jnz     short loc_18000CFC9
0x18000cfb8  mov     rcx, [rbp+hKey]; hKey
0x18000cfbc  lea     rdx, SubKey; "PersistentHandler"
0x18000cfc3  call    cs:__imp_RegDeleteKeyW
0x18000cfc9  mov     rcx, [rbp+hKey]; hKey
0x18000cfcd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cfd1  jz      short loc_18000CFD9
0x18000cfd3  call    cs:__imp_RegCloseKey
0x18000cfd9  xor     eax, eax
0x18000cfdb  test    ebx, ebx
0x18000cfdd  mov     rbx, [rsp+50h+arg_8]
0x18000cfe2  setnz   al
0x18000cfe5  add     rsp, 50h
0x18000cfe9  pop     rbp
0x18000cfea  retn
```
