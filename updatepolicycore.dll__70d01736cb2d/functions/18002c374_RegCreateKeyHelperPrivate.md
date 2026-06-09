# RegCreateKeyHelperPrivate

- ea: `0x18002c374`
- end: `0x18002c465`
- name: `RegCreateKeyHelperPrivate`
- size: `241`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002c46c`

## callees

- `0x18002bee8`
- `0x18002c374`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c400`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c400`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c43e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c43e`

## pseudocode

```c
__int64 __fastcall RegCreateKeyHelperPrivate(__int64 a1, const WCHAR *a2, __int64 a3, HKEY *a4)
{
  signed int v6; // ebx
  LSTATUS v7; // eax
  REGSAM samDesired; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF

  hKey = 0;
  samDesired = 131078;
  *a4 = 0;
  v6 = SetRegistryType(a1, &samDesired);
  if ( v6 >= 0 )
  {
    if ( a2 )
    {
      v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, samDesired, 0, &hKey, 0);
      if ( v7 )
      {
        v6 = (unsigned __int16)v7 | 0x80070000;
        if ( v7 <= 0 )
          v6 = v7;
      }
      else
      {
        *a4 = hKey;
        hKey = 0;
      }
    }
    else
    {
      *a4 = HKEY_LOCAL_MACHINE;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c374  mov     r11, rsp
0x18002c377  mov     [r11+8], rbx
0x18002c37b  mov     [r11+18h], rsi
0x18002c37f  push    rdi
0x18002c380  sub     rsp, 70h
0x18002c384  mov     rax, cs:__security_cookie
0x18002c38b  xor     rax, rsp
0x18002c38e  mov     [rsp+78h+var_18], rax
0x18002c393  mov     rsi, rdx
0x18002c396  mov     qword ptr [r11-20h], 0
0x18002c39e  lea     rdx, [r11-28h]
0x18002c3a2  mov     [rsp+78h+var_28], 20006h
0x18002c3aa  mov     rdi, r9
0x18002c3ad  mov     qword ptr [r9], 0
0x18002c3b4  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18002c3b9  mov     ebx, eax
0x18002c3bb  test    eax, eax
0x18002c3bd  js      short loc_18002C434
0x18002c3bf  test    rsi, rsi
0x18002c3c2  jz      short loc_18002C42D
0x18002c3c4  mov     ecx, [rsp+78h+var_28]
0x18002c3c8  lea     rax, [rsp+78h+hKey]
0x18002c3cd  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18002c3d6  xor     r9d, r9d; lpClass
0x18002c3d9  mov     [rsp+78h+phkResult], rax; phkResult
0x18002c3de  xor     r8d, r8d; Reserved
0x18002c3e1  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002c3ea  mov     rdx, rsi; lpSubKey
0x18002c3ed  mov     [rsp+78h+samDesired], ecx; samDesired
0x18002c3f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c3f8  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18002c400  call    cs:__imp_RegCreateKeyExW
0x18002c406  test    eax, eax
0x18002c408  jz      short loc_18002C41A
0x18002c40a  movzx   ebx, ax
0x18002c40d  or      ebx, 80070000h
0x18002c413  test    eax, eax
0x18002c415  cmovle  ebx, eax
0x18002c418  jmp     short loc_18002C434
0x18002c41a  mov     rax, [rsp+78h+hKey]
0x18002c41f  mov     [rdi], rax
0x18002c422  mov     [rsp+78h+hKey], 0
0x18002c42b  jmp     short loc_18002C434
0x18002c42d  mov     qword ptr [rdi], 0FFFFFFFF80000002h
0x18002c434  mov     rcx, [rsp+78h+hKey]; hKey
0x18002c439  test    rcx, rcx
0x18002c43c  jz      short loc_18002C444
0x18002c43e  call    cs:__imp_RegCloseKey
0x18002c444  mov     eax, ebx
0x18002c446  mov     rcx, [rsp+78h+var_18]
0x18002c44b  xor     rcx, rsp; StackCookie
0x18002c44e  call    __security_check_cookie
0x18002c453  lea     r11, [rsp+78h+var_8]
0x18002c458  mov     rbx, [r11+10h]
0x18002c45c  mov     rsi, [r11+20h]
0x18002c460  mov     rsp, r11
0x18002c463  pop     rdi
0x18002c464  retn
```
