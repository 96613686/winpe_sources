# UnregisterCoClass(_GUID const &,ushort const *,ushort const *)

- ea: `0x18002ce6c`
- end: `0x18002d00c`
- name: `?UnregisterCoClass@@YAXAEBU_GUID@@PEBG1@Z`
- size: `416`
- prototype: `void __fastcall(GUID *rguid, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002d480`

## callees

- `0x18000d2c0`
- `0x180018460`
- `0x18002ce14`
- `0x18002ce6c`
- `0x18002d014`
- `0x180034090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cf9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cfd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cf9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cfd3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ceaa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ceaa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002cfdd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002cfdd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002cec9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002cec9`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002cf24`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002cfb4`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002cf24`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002cfb4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf3a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf4c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf5e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf70`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf82`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf94`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cfc8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf3a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf4c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf5e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf70`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf82`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cf94`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cfc8`

## string_xrefs

- `0x18002ceea`: `SOFTWARE\CLASSES\CLSID\`
- `0x18002cfaa`: `SOFTWARE\CLASSES\CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UnregisterCoClass(GUID *rguid, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned __int16 *v6; // rbx
  size_t *v7; // r8
  unsigned int v8; // r11d
  size_t v9; // [rsp+20h] [rbp-E0h]
  HKEY phkResult[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[128]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[128]; // [rsp+140h] [rbp+40h] BYREF

  phkResult[0] = 0;
  v6 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x130u);
  if ( v6 )
  {
    if ( StringFromGUID2(rguid, sz, 128) )
    {
      StringCopyWorkerW(pszDest, 0x80u, v7, sz, v9);
      StringCchCopyW(v6, 0x98u, L"SOFTWARE\\CLASSES\\CLSID\\");
      StringCchCatW(v6, v8, pszDest);
      if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, v6, phkResult) )
      {
        RegDeleteKeyW(phkResult[0], L"InProcServer32");
        RegDeleteKeyW(phkResult[0], L"TypeLib");
        RegDeleteKeyW(phkResult[0], L"ProgID");
        RegDeleteKeyW(phkResult[0], L"VersionIndependentProgID");
        RegDeleteKeyW(phkResult[0], L"Version");
        RegDeleteKeyW(phkResult[0], L"Programmable");
        RegCloseKey(phkResult[0]);
      }
      if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\CLASSES\\CLSID\\", phkResult) )
      {
        RegDeleteKeyW(phkResult[0], pszDest);
        RegCloseKey(phkResult[0]);
      }
    }
    CWin32DefaultArena::WbemMemFree(v6);
  }
  UnregisterProgID(a2, a3);
}

```

## disassembly

```asm
0x18002ce6c  push    rbp
0x18002ce6e  push    rbx
0x18002ce6f  push    rsi
0x18002ce70  push    rdi
0x18002ce71  push    r14
0x18002ce73  lea     rbp, [rsp-150h]
0x18002ce7b  sub     rsp, 250h
0x18002ce82  mov     rax, cs:__security_cookie
0x18002ce89  xor     rax, rsp
0x18002ce8c  mov     [rbp+170h+var_30], rax
0x18002ce93  mov     r14, r8
0x18002ce96  mov     rsi, rdx
0x18002ce99  mov     rdi, rcx
0x18002ce9c  mov     [rsp+270h+phkResult], 0
0x18002cea5  mov     ecx, 130h
0x18002ceaa  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002ceb0  mov     rbx, rax
0x18002ceb3  test    rax, rax
0x18002ceb6  jz      loc_18002CFE4
0x18002cebc  mov     r8d, 80h; cchMax
0x18002cec2  lea     rdx, [rbp+170h+sz]; lpsz
0x18002cec6  mov     rcx, rdi; rguid
0x18002cec9  call    cs:__imp_StringFromGUID2
0x18002cecf  test    eax, eax
0x18002ced1  jz      loc_18002CFDA
0x18002ced7  lea     r9, [rbp+170h+sz]; pszSrc
0x18002cedb  mov     edx, 80h; cchDest
0x18002cee0  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18002cee5  call    StringCopyWorkerW
0x18002ceea  lea     r8, aSoftwareClasse; "SOFTWARE\\CLASSES\\CLSID\\"
0x18002cef1  mov     r11d, 98h
0x18002cef7  mov     edx, r11d; unsigned __int64
0x18002cefa  mov     rcx, rbx; unsigned __int16 *
0x18002cefd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cf02  lea     r8, [rsp+270h+pszDest]; unsigned __int16 *
0x18002cf07  mov     edx, r11d; unsigned __int64
0x18002cf0a  mov     rcx, rbx; unsigned __int16 *
0x18002cf0d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002cf12  lea     r8, [rsp+270h+phkResult]; phkResult
0x18002cf17  mov     rdx, rbx; lpSubKey
0x18002cf1a  mov     rdi, 0FFFFFFFF80000002h
0x18002cf21  mov     rcx, rdi; hKey
0x18002cf24  call    cs:__imp_RegOpenKeyW
0x18002cf2a  test    eax, eax
0x18002cf2c  jnz     short loc_18002CFA5
0x18002cf2e  lea     rdx, aInprocserver32; "InProcServer32"
0x18002cf35  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002cf3a  call    cs:__imp_RegDeleteKeyW
0x18002cf40  lea     rdx, aTypelib; "TypeLib"
0x18002cf47  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002cf4c  call    cs:__imp_RegDeleteKeyW
0x18002cf52  lea     rdx, aProgid; "ProgID"
0x18002cf59  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002cf5e  call    cs:__imp_RegDeleteKeyW
0x18002cf64  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x18002cf6b  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002cf70  call    cs:__imp_RegDeleteKeyW
0x18002cf76  lea     rdx, aVersion; "Version"
0x18002cf7d  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002cf82  call    cs:__imp_RegDeleteKeyW
0x18002cf88  lea     rdx, aProgrammable; "Programmable"
0x18002cf8f  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002cf94  call    cs:__imp_RegDeleteKeyW
0x18002cf9a  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002cf9f  call    cs:__imp_RegCloseKey
0x18002cfa5  lea     r8, [rsp+270h+phkResult]; phkResult
0x18002cfaa  lea     rdx, aSoftwareClasse; "SOFTWARE\\CLASSES\\CLSID\\"
0x18002cfb1  mov     rcx, rdi; hKey
0x18002cfb4  call    cs:__imp_RegOpenKeyW
0x18002cfba  test    eax, eax
0x18002cfbc  jnz     short loc_18002CFDA
0x18002cfbe  lea     rdx, [rsp+270h+pszDest]; lpSubKey
0x18002cfc3  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002cfc8  call    cs:__imp_RegDeleteKeyW
0x18002cfce  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002cfd3  call    cs:__imp_RegCloseKey
0x18002cfd9  nop
0x18002cfda  mov     rcx, rbx
0x18002cfdd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002cfe3  nop
0x18002cfe4  mov     rdx, r14; unsigned __int16 *
0x18002cfe7  mov     rcx, rsi; unsigned __int16 *
0x18002cfea  call    ?UnregisterProgID@@YAXPEBG0@Z; UnregisterProgID(ushort const *,ushort const *)
0x18002cfef  mov     rcx, [rbp+170h+var_30]
0x18002cff6  xor     rcx, rsp; StackCookie
0x18002cff9  call    __security_check_cookie
0x18002cffe  add     rsp, 250h
0x18002d005  pop     r14
0x18002d007  pop     rdi
0x18002d008  pop     rsi
0x18002d009  pop     rbx
0x18002d00a  pop     rbp
0x18002d00b  retn
```
