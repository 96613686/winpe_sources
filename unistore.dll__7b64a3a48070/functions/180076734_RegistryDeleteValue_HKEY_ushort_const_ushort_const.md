# RegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180076734`
- end: `0x180076805`
- name: `?RegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `209`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800188b0`
- `0x180018ab0`

## callees

- `0x1800068f0`
- `0x18001a6c4`
- `0x180076734`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076774`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076774`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800767c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800767db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800767ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800767c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800767db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800767ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180076788`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180076788`

## string_xrefs

- `0x1800767ad`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\registryutil.h`

## pseudocode

```c
__int64 __fastcall RegistryDeleteValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HKEY *phkResult; // rax
  int v5; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v5 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", 0, 2u, phkResult);
  if ( !v5 )
    v5 = RegDeleteValueW(hKey, a3);
  if ( (unsigned int)(v5 - 2) <= 1 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
  else if ( v5 )
  {
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    Log_UnistoreHREvent_0(
      (unsigned int)v5,
      0,
      "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\registryutil.h",
      360);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v5;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x180076734  mov     rax, rsp
0x180076737  mov     [rax+8], rbx
0x18007673b  mov     [rax+10h], rdx
0x18007673f  push    rdi
0x180076740  sub     rsp, 30h
0x180076744  lea     rcx, [rax+10h]
0x180076748  mov     qword ptr [rax+10h], 0
0x180076750  mov     rdi, r8
0x180076753  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x180076758  mov     r9d, 2; samDesired
0x18007675e  mov     [rsp+38h+phkResult], rax; phkResult
0x180076763  xor     r8d, r8d; ulOptions
0x180076766  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x18007676d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180076774  call    cs:__imp_RegOpenKeyExW
0x18007677a  mov     ebx, eax
0x18007677c  test    eax, eax
0x18007677e  jnz     short loc_180076790
0x180076780  mov     rcx, [rsp+38h+hKey]; hKey
0x180076785  mov     rdx, rdi; lpValueName
0x180076788  call    cs:__imp_RegDeleteValueW
0x18007678e  mov     ebx, eax
0x180076790  lea     eax, [rbx-2]
0x180076793  cmp     eax, 1
0x180076796  jbe     short loc_1800767E5
0x180076798  test    ebx, ebx
0x18007679a  jz      short loc_1800767D1
0x18007679c  jle     short loc_1800767A7
0x18007679e  movzx   ebx, bx
0x1800767a1  or      ebx, 80070000h
0x1800767a7  mov     r9d, 168h
0x1800767ad  lea     r8, aOnecoreuapBase_65; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800767b4  xor     edx, edx
0x1800767b6  mov     ecx, ebx
0x1800767b8  call    Log_UnistoreHREvent_0
0x1800767bd  mov     rcx, [rsp+38h+hKey]; hKey
0x1800767c2  test    rcx, rcx
0x1800767c5  jz      short loc_1800767CD
0x1800767c7  call    cs:__imp_RegCloseKey
0x1800767cd  mov     eax, ebx
0x1800767cf  jmp     short loc_1800767FA
0x1800767d1  mov     rcx, [rsp+38h+hKey]; hKey
0x1800767d6  test    rcx, rcx
0x1800767d9  jz      short loc_1800767E1
0x1800767db  call    cs:__imp_RegCloseKey
0x1800767e1  xor     eax, eax
0x1800767e3  jmp     short loc_1800767FA
0x1800767e5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800767ea  test    rcx, rcx
0x1800767ed  jz      short loc_1800767F5
0x1800767ef  call    cs:__imp_RegCloseKey
0x1800767f5  mov     eax, 1
0x1800767fa  mov     rbx, [rsp+38h+arg_0]
0x1800767ff  add     rsp, 30h
0x180076803  pop     rdi
0x180076804  retn
```
