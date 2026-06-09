# _CheckForControlledUsers(void *,int *)

- ea: `0x18006b164`
- end: `0x18006b2d2`
- name: `?_CheckForControlledUsers@@YAJPEAXPEAH@Z`
- size: `366`
- prototype: `__int64 __fastcall(HKEY, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011988`

## callees

- `0x18006a608`
- `0x18006b164`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006b267`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006b267`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b1ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b1ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b2bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b2bc`

## string_xrefs

- `0x18006b1dd`: `RegOpenKeyEx`
- `0x18006b1f1`: `onecore\ds\security\eas\policyengine\common.cpp`

## pseudocode

```c
__int64 __fastcall _CheckForControlledUsers(HKEY a1, int *a2)
{
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-48h]
  PHKEY phkResulta; // [rsp+20h] [rbp-48h]
  DWORD cSubKeys; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  cSubKeys = 0;
  hKey = 0;
  *a2 = 0;
  if ( !a1 )
    return 0;
  v3 = RegOpenKeyExW(a1, L"ControlledUsers", 0, 0x20019u, &hKey);
  if ( v3 - 2 > 1 )
  {
    if ( v3 )
    {
      if ( (int)v3 > 0 )
        v3 = (unsigned __int16)v3 | 0xC0070000;
      LODWORD(phkResult) = 241;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v3,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        phkResult,
        L"RegOpenKeyEx",
        &Class);
      goto LABEL_16;
    }
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0xC0070000;
      LODWORD(phkResulta) = 260;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v3,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        phkResulta,
        L"RegQueryInfoKey",
        &Class);
      goto LABEL_16;
    }
    if ( cSubKeys )
      *a2 = 1;
  }
  v3 = 0;
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18006b164  mov     [rsp+arg_10], rbx
0x18006b169  push    rdi
0x18006b16a  sub     rsp, 60h
0x18006b16e  mov     [rsp+68h+cSubKeys], 0
0x18006b176  mov     rdi, rdx
0x18006b179  mov     [rsp+68h+hKey], 0
0x18006b182  mov     dword ptr [rdx], 0
0x18006b188  test    rcx, rcx
0x18006b18b  jnz     short loc_18006B194
0x18006b18d  xor     ebx, ebx
0x18006b18f  jmp     loc_18006B2C2
0x18006b194  lea     rax, [rsp+68h+hKey]
0x18006b199  mov     r9d, 20019h; samDesired
0x18006b19f  xor     r8d, r8d; ulOptions
0x18006b1a2  mov     [rsp+68h+phkResult], rax; phkResult
0x18006b1a7  lea     rdx, aControlleduser; "ControlledUsers"
0x18006b1ae  call    cs:__imp_RegOpenKeyExW
0x18006b1b4  mov     ebx, eax
0x18006b1b6  add     eax, 0FFFFFFFEh
0x18006b1b9  cmp     eax, 1
0x18006b1bc  jbe     loc_18006B2B0
0x18006b1c2  test    ebx, ebx
0x18006b1c4  jz      short loc_18006B211
0x18006b1c6  jle     short loc_18006B1D1
0x18006b1c8  movzx   ebx, bx
0x18006b1cb  or      ebx, 0C0070000h
0x18006b1d1  lea     rax, Class
0x18006b1d8  mov     [rsp+68h+lpcbMaxClassLen], rax
0x18006b1dd  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x18006b1e4  mov     [rsp+68h+lpcbMaxSubKeyLen], rax
0x18006b1e9  mov     dword ptr [rsp+68h+phkResult], 0F1h
0x18006b1f1  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006b1f8  mov     r8d, ebx
0x18006b1fb  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006b202  mov     ecx, 1; unsigned int
0x18006b207  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006b20c  jmp     loc_18006B2B2
0x18006b211  mov     rcx, [rsp+68h+hKey]; hKey
0x18006b216  lea     rax, [rsp+68h+cSubKeys]
0x18006b21b  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18006b224  xor     r9d, r9d; lpReserved
0x18006b227  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18006b230  xor     r8d, r8d; lpcchClass
0x18006b233  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18006b23c  xor     edx, edx; lpClass
0x18006b23e  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18006b247  mov     [rsp+68h+lpcValues], 0; lpcValues
0x18006b250  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18006b259  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18006b262  mov     [rsp+68h+phkResult], rax; lpcSubKeys
0x18006b267  call    cs:__imp_RegQueryInfoKeyW
0x18006b26d  mov     ebx, eax
0x18006b26f  test    eax, eax
0x18006b271  jz      short loc_18006B2A3
0x18006b273  jle     short loc_18006B27E
0x18006b275  movzx   ebx, ax
0x18006b278  or      ebx, 0C0070000h
0x18006b27e  lea     rax, Class
0x18006b285  mov     [rsp+68h+lpcbMaxClassLen], rax
0x18006b28a  lea     rax, aRegqueryinfoke; "RegQueryInfoKey"
0x18006b291  mov     [rsp+68h+lpcbMaxSubKeyLen], rax
0x18006b296  mov     dword ptr [rsp+68h+phkResult], 104h
0x18006b29e  jmp     loc_18006B1F1
0x18006b2a3  cmp     [rsp+68h+cSubKeys], 0
0x18006b2a8  jz      short loc_18006B2B0
0x18006b2aa  mov     dword ptr [rdi], 1
0x18006b2b0  xor     ebx, ebx
0x18006b2b2  mov     rcx, [rsp+68h+hKey]; hKey
0x18006b2b7  test    rcx, rcx
0x18006b2ba  jz      short loc_18006B2C2
0x18006b2bc  call    cs:__imp_RegCloseKey
0x18006b2c2  mov     eax, ebx
0x18006b2c4  mov     rbx, [rsp+68h+arg_10]
0x18006b2cc  add     rsp, 60h
0x18006b2d0  pop     rdi
0x18006b2d1  retn
```
