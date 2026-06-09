# _IsValidVirtualFactory(_GUID const &)

- ea: `0x180002dec`
- end: `0x180002f03`
- name: `?_IsValidVirtualFactory@@YAJAEBU_GUID@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180002c00`

## callees

- `0x180002340`
- `0x1800026d4`
- `0x180002dec`
- `0x1800036c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e6e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002e19`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e9c`

## string_xrefs

- `0x180002e2e`: `CLSID\%s\VirtualServerObjects`

## pseudocode

```c
__int64 __fastcall _IsValidVirtualFactory(const struct _GUID *a1)
{
  int v1; // ebx
  int v2; // edi
  LSTATUS v3; // eax
  LPOLESTR lpsz; // [rsp+30h] [rbp-228h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-220h] BYREF
  WCHAR SubKey[256]; // [rsp+40h] [rbp-218h] BYREF

  lpsz = 0;
  v1 = StringFromCLSID(a1, &lpsz);
  if ( v1 < 0 )
    goto LABEL_10;
  v2 = 0;
  v1 = StringCchPrintfW(SubKey, 0x100u, L"CLSID\\%s\\VirtualServerObjects", lpsz);
  if ( v1 >= 0 )
  {
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hKey);
    v1 = v3;
    if ( v3 > 0 )
      v1 = (unsigned __int16)v3 | 0x80070000;
    if ( v1 >= 0 )
    {
      v2 = 1;
      RegCloseKey(hKey);
    }
  }
  CoTaskMemFree(lpsz);
  if ( v1 < 0 )
  {
LABEL_10:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_8681af7930fc3f9ff14ce17035134427_Traceguids,
        (unsigned int)v1);
  }
  else
  {
    return v2 == 0;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180002dec  mov     [rsp+arg_8], rbx
0x180002df1  push    rdi
0x180002df2  sub     rsp, 250h
0x180002df9  mov     rax, cs:__security_cookie
0x180002e00  xor     rax, rsp
0x180002e03  mov     [rsp+258h+var_18], rax
0x180002e0b  lea     rdx, [rsp+258h+lpsz]; lplpsz
0x180002e10  mov     [rsp+258h+lpsz], 0
0x180002e19  call    cs:__imp_StringFromCLSID
0x180002e1f  mov     ebx, eax
0x180002e21  test    eax, eax
0x180002e23  js      loc_180002EAF
0x180002e29  mov     r9, [rsp+258h+lpsz]
0x180002e2e  lea     r8, aClsidSVirtuals; "CLSID\\%s\\VirtualServerObjects"
0x180002e35  mov     edx, 100h; unsigned __int64
0x180002e3a  lea     rcx, [rsp+258h+SubKey]; unsigned __int16 *
0x180002e3f  xor     edi, edi
0x180002e41  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002e46  mov     ebx, eax
0x180002e48  test    eax, eax
0x180002e4a  js      short loc_180002E97
0x180002e4c  lea     rax, [rsp+258h+hKey]
0x180002e51  mov     [rsp+258h+hKey], rdi
0x180002e56  lea     r9d, [rdi+1]; samDesired
0x180002e5a  mov     [rsp+258h+phkResult], rax; phkResult
0x180002e5f  xor     r8d, r8d; ulOptions
0x180002e62  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x180002e67  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002e6e  call    cs:__imp_RegOpenKeyExW
0x180002e74  mov     ebx, eax
0x180002e76  test    eax, eax
0x180002e78  jle     short loc_180002E83
0x180002e7a  movzx   ebx, ax
0x180002e7d  or      ebx, 80070000h
0x180002e83  test    ebx, ebx
0x180002e85  js      short loc_180002E97
0x180002e87  mov     rcx, [rsp+258h+hKey]; hKey
0x180002e8c  mov     edi, 1
0x180002e91  call    cs:__imp_RegCloseKey
0x180002e97  mov     rcx, [rsp+258h+lpsz]; pv
0x180002e9c  call    cs:__imp_CoTaskMemFree
0x180002ea2  test    ebx, ebx
0x180002ea4  js      short loc_180002EAF
0x180002ea6  xor     ebx, ebx
0x180002ea8  test    edi, edi
0x180002eaa  setz    bl
0x180002ead  jmp     short loc_180002EE0
0x180002eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eb6  lea     rax, WPP_GLOBAL_Control
0x180002ebd  cmp     rcx, rax
0x180002ec0  jz      short loc_180002EE0
0x180002ec2  test    byte ptr [rcx+1Ch], 4
0x180002ec6  jz      short loc_180002EE0
0x180002ec8  mov     rcx, [rcx+10h]
0x180002ecc  lea     r8, WPP_8681af7930fc3f9ff14ce17035134427_Traceguids
0x180002ed3  mov     edx, 0Bh
0x180002ed8  mov     r9d, ebx
0x180002edb  call    WPP_SF_d
0x180002ee0  mov     eax, ebx
0x180002ee2  mov     rcx, [rsp+258h+var_18]
0x180002eea  xor     rcx, rsp; StackCookie
0x180002eed  call    __security_check_cookie
0x180002ef2  mov     rbx, [rsp+258h+arg_8]
0x180002efa  add     rsp, 250h
0x180002f01  pop     rdi
0x180002f02  retn
```
