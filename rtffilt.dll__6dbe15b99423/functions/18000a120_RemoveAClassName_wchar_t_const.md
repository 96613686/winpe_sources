# RemoveAClassName(wchar_t const *)

- ea: `0x18000a120`
- end: `0x18000a352`
- name: `?RemoveAClassName@@YAJPEB_W@Z`
- size: `562`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009e20`

## callees

- `0x180001e40`
- `0x18000a120`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a27d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a27d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a265`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a265`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a258`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a258`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a1df`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a2e4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a1df`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a2e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a296`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a2a0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a296`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a2a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a176`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a217`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a176`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a217`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a18e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a307`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a18e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a307`

## pseudocode

```c
LSTATUS __fastcall RemoveAClassName(WCHAR *lpSubKey)
{
  LSTATUS v2; // edi
  HKEY v3; // rcx
  WCHAR *v4; // rdx
  LSTATUS v5; // ebx
  DWORD v6; // esi
  LSTATUS result; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[528]; // [rsp+280h] [rbp+180h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, 0, 0, 0x2001Fu, &hKey);
  if ( v2 )
    return 0;
  v3 = hKey;
  v4 = lpSubKey;
LABEL_3:
  v5 = RegDeleteKeyW(v3, v4);
LABEL_4:
  v6 = 0;
  while ( 1 )
  {
    cchName = 260;
    ftLastWriteTime = 0;
    result = RegEnumKeyExW(hKey, v6, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( result )
      break;
    phkResult = 0;
    ++v6;
    v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Name, 0, 0x2001Fu, &phkResult);
    if ( !v2 )
    {
      Type = 0;
      cchName = 520;
      v2 = RegQueryValueExW(phkResult, 0, 0, &Type, Data, &cchName);
      RegCloseKey(phkResult);
      if ( v2 || (unsigned int)_o__wcsicmp(Data, lpSubKey) )
      {
        v2 = 0;
      }
      else
      {
        if ( v5 )
          RegDeleteValueW(phkResult, 0);
        else
          v5 = RegDeleteValueW(phkResult, 0);
        cchName = 260;
        if ( RegEnumKeyExW(phkResult, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) == 259 )
        {
          v3 = hKey;
          v4 = Name;
          if ( !v5 )
            goto LABEL_3;
          RegDeleteKeyW(hKey, Name);
          goto LABEL_4;
        }
      }
    }
  }
  if ( result == 259 )
    result = v2;
  if ( !result )
    return v5;
  return result;
}

```

## disassembly

```asm
0x18000a120  mov     [rsp-8+arg_8], rbx
0x18000a125  mov     [rsp-8+arg_10], rsi
0x18000a12a  push    rbp
0x18000a12b  push    rdi
0x18000a12c  push    r14
0x18000a12e  lea     rbp, [rsp-3A0h]
0x18000a136  sub     rsp, 4A0h
0x18000a13d  mov     rax, cs:__security_cookie
0x18000a144  xor     rax, rsp
0x18000a147  mov     [rbp+3B0h+var_20], rax
0x18000a14e  mov     r14, rcx
0x18000a151  mov     [rsp+4B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x18000a15a  lea     rax, [rsp+4B0h+hKey]
0x18000a15f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000a166  mov     r9d, 2001Fh; samDesired
0x18000a16c  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000a171  xor     r8d, r8d; ulOptions
0x18000a174  xor     edx, edx; lpSubKey
0x18000a176  call    cs:__imp_RegOpenKeyExW
0x18000a17c  mov     edi, eax
0x18000a17e  test    eax, eax
0x18000a180  jnz     loc_18000A329
0x18000a186  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000a18b  mov     rdx, r14; lpSubKey
0x18000a18e  call    cs:__imp_RegDeleteKeyW
0x18000a194  mov     ebx, eax
0x18000a196  xor     esi, esi
0x18000a198  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000a19d  lea     rax, [rsp+4B0h+ftLastWriteTime]
0x18000a1a2  mov     [rsp+4B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000a1a7  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x18000a1ac  mov     [rsp+4B0h+lpcchClass], 0; lpcchClass
0x18000a1b5  lea     r8, [rsp+4B0h+Name]; lpName
0x18000a1ba  mov     [rsp+4B0h+lpClass], 0; lpClass
0x18000a1c3  mov     edx, esi; dwIndex
0x18000a1c5  mov     [rsp+4B0h+phkResult], 0; lpReserved
0x18000a1ce  mov     [rsp+4B0h+cchName], 104h
0x18000a1d6  mov     qword ptr [rsp+4B0h+ftLastWriteTime.dwLowDateTime], 0
0x18000a1df  call    cs:__imp_RegEnumKeyExW
0x18000a1e5  test    eax, eax
0x18000a1e7  jnz     loc_18000A319
0x18000a1ed  lea     rax, [rsp+4B0h+var_468]
0x18000a1f2  mov     [rsp+4B0h+var_468], 0
0x18000a1fb  mov     r9d, 2001Fh; samDesired
0x18000a201  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000a206  xor     r8d, r8d; ulOptions
0x18000a209  lea     rdx, [rsp+4B0h+Name]; lpSubKey
0x18000a20e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000a215  inc     esi
0x18000a217  call    cs:__imp_RegOpenKeyExW
0x18000a21d  mov     edi, eax
0x18000a21f  test    eax, eax
0x18000a221  jnz     loc_18000A198
0x18000a227  mov     rcx, [rsp+4B0h+var_468]; hKey
0x18000a22c  lea     r9, [rsp+4B0h+Type]; lpType
0x18000a231  mov     [rsp+4B0h+Type], eax
0x18000a235  xor     r8d, r8d; lpReserved
0x18000a238  lea     rax, [rsp+4B0h+cchName]
0x18000a23d  mov     [rsp+4B0h+cchName], 208h
0x18000a245  mov     [rsp+4B0h+lpClass], rax; lpcbData
0x18000a24a  xor     edx, edx; lpValueName
0x18000a24c  lea     rax, [rbp+3B0h+Data]
0x18000a253  mov     [rsp+4B0h+phkResult], rax; lpData
0x18000a258  call    cs:__imp_RegQueryValueExW
0x18000a25e  mov     rcx, [rsp+4B0h+var_468]; hKey
0x18000a263  mov     edi, eax
0x18000a265  call    cs:__imp_RegCloseKey
0x18000a26b  test    edi, edi
0x18000a26d  jnz     loc_18000A312
0x18000a273  mov     rdx, r14
0x18000a276  lea     rcx, [rbp+3B0h+Data]
0x18000a27d  call    cs:__imp__o__wcsicmp
0x18000a283  test    eax, eax
0x18000a285  jnz     loc_18000A312
0x18000a28b  mov     rcx, [rsp+4B0h+var_468]; hKey
0x18000a290  xor     edx, edx; lpValueName
0x18000a292  test    ebx, ebx
0x18000a294  jnz     short loc_18000A2A0
0x18000a296  call    cs:__imp_RegDeleteValueW
0x18000a29c  mov     ebx, eax
0x18000a29e  jmp     short loc_18000A2A6
0x18000a2a0  call    cs:__imp_RegDeleteValueW
0x18000a2a6  mov     rcx, [rsp+4B0h+var_468]; hKey
0x18000a2ab  lea     rax, [rsp+4B0h+ftLastWriteTime]
0x18000a2b0  mov     [rsp+4B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000a2b5  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x18000a2ba  mov     [rsp+4B0h+lpcchClass], 0; lpcchClass
0x18000a2c3  lea     r8, [rsp+4B0h+Name]; lpName
0x18000a2c8  mov     [rsp+4B0h+lpClass], 0; lpClass
0x18000a2d1  xor     edx, edx; dwIndex
0x18000a2d3  mov     [rsp+4B0h+phkResult], 0; lpReserved
0x18000a2dc  mov     [rsp+4B0h+cchName], 104h
0x18000a2e4  call    cs:__imp_RegEnumKeyExW
0x18000a2ea  cmp     eax, 103h
0x18000a2ef  jnz     loc_18000A198
0x18000a2f5  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000a2fa  lea     rdx, [rsp+4B0h+Name]; lpSubKey
0x18000a2ff  test    ebx, ebx
0x18000a301  jz      loc_18000A18E
0x18000a307  call    cs:__imp_RegDeleteKeyW
0x18000a30d  jmp     loc_18000A196
0x18000a312  xor     edi, edi
0x18000a314  jmp     loc_18000A198
0x18000a319  cmp     eax, 103h
0x18000a31e  cmovz   eax, edi
0x18000a321  test    eax, eax
0x18000a323  jnz     short loc_18000A32B
0x18000a325  mov     eax, ebx
0x18000a327  jmp     short loc_18000A32B
0x18000a329  xor     eax, eax
0x18000a32b  mov     rcx, [rbp+3B0h+var_20]
0x18000a332  xor     rcx, rsp; StackCookie
0x18000a335  call    __security_check_cookie
0x18000a33a  lea     r11, [rsp+4B0h+var_10]
0x18000a342  mov     rbx, [r11+28h]
0x18000a346  mov     rsi, [r11+30h]
0x18000a34a  mov     rsp, r11
0x18000a34d  pop     r14
0x18000a34f  pop     rdi
0x18000a350  pop     rbp
0x18000a351  retn
```
