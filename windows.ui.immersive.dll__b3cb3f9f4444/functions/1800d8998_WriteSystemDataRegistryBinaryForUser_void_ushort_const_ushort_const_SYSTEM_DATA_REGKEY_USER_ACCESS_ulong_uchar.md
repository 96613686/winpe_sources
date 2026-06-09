# WriteSystemDataRegistryBinaryForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,uchar *)

- ea: `0x1800d8998`
- end: `0x1800d8ad1`
- name: `?WriteSystemDataRegistryBinaryForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@KPEAE@Z`
- size: `313`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180031890`

## callees

- `0x18000da00`
- `0x18003d244`
- `0x180054130`
- `0x1800d8998`
- `0x1800d8ad8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8a9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8a9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d8a8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d8a8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d8a7b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d8a7b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d89d5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d89d5`

## string_xrefs

- `0x1800d89f9`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall WriteSystemDataRegistryBinaryForUser(
        void *a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        DWORD cbData,
        BYTE *lpData)
{
  int Error; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r9
  HKEY hKey; // [rsp+40h] [rbp-248h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-240h] BYREF
  unsigned __int16 v15[264]; // [rsp+50h] [rbp-238h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = StringCchPrintfW(
              v15,
              0x104u,
              L"%s\\%s\\%s\\%s",
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
              StringSid,
              L"AnyoneRead",
              a2);
    if ( Error >= 0 )
    {
      hKey = 0;
      Error = _CreateRegKeyWithSDDL(v10, v9, v15, v11, 0, &hKey);
      if ( Error >= 0 )
      {
        Error = RegSetValueExW(hKey, a3, 0, 3u, lpData, cbData);
        RegCloseKey(hKey);
      }
    }
    LocalFree(StringSid);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d8998  mov     [rsp+arg_18], rbx
0x1800d899d  push    rbp
0x1800d899e  push    rsi
0x1800d899f  push    rdi
0x1800d89a0  sub     rsp, 270h
0x1800d89a7  mov     rax, cs:__security_cookie
0x1800d89ae  xor     rax, rsp
0x1800d89b1  mov     [rsp+288h+var_28], rax
0x1800d89b9  mov     rbp, [rsp+288h+arg_28]
0x1800d89c1  mov     rdi, rdx
0x1800d89c4  lea     rdx, [rsp+288h+StringSid]; StringSid
0x1800d89c9  mov     [rsp+288h+StringSid], 0
0x1800d89d2  mov     rsi, r8
0x1800d89d5  call    cs:__imp_ConvertSidToStringSidW
0x1800d89dc  nop     dword ptr [rax+rax+00h]
0x1800d89e1  test    eax, eax
0x1800d89e3  jnz     short loc_1800D89F4
0x1800d89e5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d89ea  mov     ebx, eax
0x1800d89ec  test    eax, eax
0x1800d89ee  js      loc_1800D8AAB
0x1800d89f4  mov     rcx, [rsp+288h+StringSid]
0x1800d89f9  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800d8a00  mov     rax, cs:off_1800EE7D8; "AnyoneRead"
0x1800d8a07  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800d8a0e  mov     [rsp+288h+var_258], rdi
0x1800d8a13  mov     edx, 104h; unsigned __int64
0x1800d8a18  mov     qword ptr [rsp+288h+cbData], rax
0x1800d8a1d  mov     [rsp+288h+lpData], rcx
0x1800d8a22  lea     rcx, [rsp+288h+var_238]; unsigned __int16 *
0x1800d8a27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d8a2c  mov     ebx, eax
0x1800d8a2e  test    eax, eax
0x1800d8a30  js      short loc_1800D8A9A
0x1800d8a32  lea     rax, [rsp+288h+hKey]
0x1800d8a37  mov     [rsp+288h+hKey], 0
0x1800d8a40  mov     qword ptr [rsp+288h+cbData], rax
0x1800d8a45  lea     r8, [rsp+288h+var_238]
0x1800d8a4a  mov     byte ptr [rsp+288h+lpData], 0
0x1800d8a4f  call    ?_CreateRegKeyWithSDDL@@YAJPEAUHKEY__@@PEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@_NPEAPEAU1@@Z; _CreateRegKeyWithSDDL(HKEY__ *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,bool,HKEY__ * *)
0x1800d8a54  mov     ebx, eax
0x1800d8a56  test    eax, eax
0x1800d8a58  js      short loc_1800D8A9A
0x1800d8a5a  mov     eax, [rsp+288h+arg_20]
0x1800d8a61  mov     r9d, 3; dwType
0x1800d8a67  mov     rcx, [rsp+288h+hKey]; hKey
0x1800d8a6c  xor     r8d, r8d; Reserved
0x1800d8a6f  mov     [rsp+288h+cbData], eax; cbData
0x1800d8a73  mov     rdx, rsi; lpValueName
0x1800d8a76  mov     [rsp+288h+lpData], rbp; lpData
0x1800d8a7b  call    cs:__imp_RegSetValueExW
0x1800d8a82  nop     dword ptr [rax+rax+00h]
0x1800d8a87  mov     rcx, [rsp+288h+hKey]; hKey
0x1800d8a8c  mov     ebx, eax
0x1800d8a8e  call    cs:__imp_RegCloseKey
0x1800d8a95  nop     dword ptr [rax+rax+00h]
0x1800d8a9a  mov     rcx, [rsp+288h+StringSid]; hMem
0x1800d8a9f  call    cs:__imp_LocalFree
0x1800d8aa6  nop     dword ptr [rax+rax+00h]
0x1800d8aab  mov     eax, ebx
0x1800d8aad  mov     rcx, [rsp+288h+var_28]
0x1800d8ab5  xor     rcx, rsp; StackCookie
0x1800d8ab8  call    __security_check_cookie
0x1800d8abd  mov     rbx, [rsp+288h+arg_18]
0x1800d8ac5  add     rsp, 270h
0x1800d8acc  pop     rdi
0x1800d8acd  pop     rsi
0x1800d8ace  pop     rbp
0x1800d8acf  retn
```
