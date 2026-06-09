# RegKeyExists(HKEY__ *,wchar_t const *,RegistryHiveType)

- ea: `0x18002c6dc`
- end: `0x18002c774`
- name: `?RegKeyExists@@YAJPEAUHKEY__@@PEB_WW4RegistryHiveType@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180026f9c`

## callees

- `0x18002bee8`
- `0x18002c6dc`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c735`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c754`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c754`

## pseudocode

```c
__int64 __fastcall RegKeyExists(__int64 a1, const WCHAR *a2)
{
  signed int v3; // ebx
  LSTATUS v4; // eax
  REGSAM samDesired; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  samDesired = 1;
  v3 = SetRegistryType(a1, &samDesired);
  if ( v3 >= 0 )
  {
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey);
    if ( v4 )
    {
      v3 = (unsigned __int16)v4 | 0x80070000;
      if ( v4 <= 0 )
        return (unsigned int)v4;
    }
    else
    {
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002c6dc  mov     [rsp+arg_0], rbx
0x18002c6e1  push    rdi
0x18002c6e2  sub     rsp, 50h
0x18002c6e6  mov     rax, cs:__security_cookie
0x18002c6ed  xor     rax, rsp
0x18002c6f0  mov     [rsp+58h+var_18], rax
0x18002c6f5  mov     rdi, rdx
0x18002c6f8  mov     [rsp+58h+hKey], 0
0x18002c701  lea     rdx, [rsp+58h+samDesired]
0x18002c706  mov     [rsp+58h+samDesired], 1
0x18002c70e  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18002c713  mov     ebx, eax
0x18002c715  test    eax, eax
0x18002c717  js      short loc_18002C75A
0x18002c719  mov     r9d, [rsp+58h+samDesired]; samDesired
0x18002c71e  lea     rax, [rsp+58h+hKey]
0x18002c723  xor     r8d, r8d; ulOptions
0x18002c726  mov     [rsp+58h+phkResult], rax; phkResult
0x18002c72b  mov     rdx, rdi; lpSubKey
0x18002c72e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c735  call    cs:__imp_RegOpenKeyExW
0x18002c73b  test    eax, eax
0x18002c73d  jz      short loc_18002C74F
0x18002c73f  movzx   ebx, ax
0x18002c742  or      ebx, 80070000h
0x18002c748  test    eax, eax
0x18002c74a  cmovle  ebx, eax
0x18002c74d  jmp     short loc_18002C75A
0x18002c74f  mov     rcx, [rsp+58h+hKey]; hKey
0x18002c754  call    cs:__imp_RegCloseKey
0x18002c75a  mov     eax, ebx
0x18002c75c  mov     rcx, [rsp+58h+var_18]
0x18002c761  xor     rcx, rsp; StackCookie
0x18002c764  call    __security_check_cookie
0x18002c769  mov     rbx, [rsp+58h+arg_0]
0x18002c76e  add     rsp, 50h
0x18002c772  pop     rdi
0x18002c773  retn
```
