# DeleteLockoutCounters

- ea: `0x18006c1fc`
- end: `0x18006c306`
- name: `DeleteLockoutCounters`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006c070`

## callees

- `0x18006a608`
- `0x18006c1fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c22c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c22c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c2f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c2f8`
- `ADVAPI32!RegFlushKey` at `0x18006c2bb`
- `ADVAPI32!RegFlushKey` at `0x18006c2bb`
- `ADVAPI32!RegDeleteTreeW` at `0x18006c288`
- `ADVAPI32!RegDeleteTreeW` at `0x18006c288`

## string_xrefs

- `0x18006c250`: `RegOpenKeyEx`
- `0x18006c264`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x18006c2a0`: `RegDeleteTree`

## pseudocode

```c
__int64 DeleteLockoutCounters()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-28h]
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\EAS\\UserState",
         0,
         0xF003Fu,
         &hKey);
  v1 = v0;
  if ( v0 - 2 <= 1 )
  {
LABEL_9:
    v1 = 0;
    goto LABEL_10;
  }
  if ( !v0 )
  {
    v1 = RegDeleteTreeW(hKey, 0);
    if ( v1 )
    {
      LODWORD(phkResult) = 613;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v1,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
        phkResult,
        L"RegDeleteTree",
        &Class);
      goto LABEL_10;
    }
    v1 = RegFlushKey(hKey);
    if ( v1 )
    {
      LODWORD(phkResult) = 616;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v1,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
        phkResult,
        L"RegFlushKey",
        &Class);
      goto LABEL_10;
    }
    goto LABEL_9;
  }
  LODWORD(phkResult) = 608;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v0,
    L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
    phkResult,
    L"RegOpenKeyEx",
    &Class);
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x18006c1fc  push    rbx
0x18006c1fe  sub     rsp, 40h
0x18006c202  lea     rax, [rsp+48h+hKey]
0x18006c207  mov     [rsp+48h+hKey], 0
0x18006c210  mov     r9d, 0F003Fh; samDesired
0x18006c216  mov     [rsp+48h+phkResult], rax; phkResult
0x18006c21b  xor     r8d, r8d; ulOptions
0x18006c21e  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006c225  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006c22c  call    cs:__imp_RegOpenKeyExW
0x18006c232  mov     ebx, eax
0x18006c234  lea     ecx, [rax-2]
0x18006c237  cmp     ecx, 1
0x18006c23a  jbe     loc_18006C2EC
0x18006c240  test    eax, eax
0x18006c242  jz      short loc_18006C281
0x18006c244  lea     rax, Class
0x18006c24b  mov     [rsp+48h+var_18], rax
0x18006c250  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x18006c257  mov     [rsp+48h+var_20], rax
0x18006c25c  mov     dword ptr [rsp+48h+phkResult], 260h
0x18006c264  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x18006c26b  mov     r8d, ebx
0x18006c26e  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006c275  mov     ecx, 1; unsigned int
0x18006c27a  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006c27f  jmp     short loc_18006C2EE
0x18006c281  mov     rcx, [rsp+48h+hKey]; hKey
0x18006c286  xor     edx, edx; lpSubKey
0x18006c288  call    cs:__imp_RegDeleteTreeW
0x18006c28e  mov     ebx, eax
0x18006c290  test    eax, eax
0x18006c292  jz      short loc_18006C2B6
0x18006c294  lea     rax, Class
0x18006c29b  mov     [rsp+48h+var_18], rax
0x18006c2a0  lea     rax, aRegdeletetree; "RegDeleteTree"
0x18006c2a7  mov     [rsp+48h+var_20], rax
0x18006c2ac  mov     dword ptr [rsp+48h+phkResult], 265h
0x18006c2b4  jmp     short loc_18006C264
0x18006c2b6  mov     rcx, [rsp+48h+hKey]; hKey
0x18006c2bb  call    cs:__imp_RegFlushKey
0x18006c2c1  mov     ebx, eax
0x18006c2c3  test    eax, eax
0x18006c2c5  jz      short loc_18006C2EC
0x18006c2c7  lea     rax, Class
0x18006c2ce  mov     [rsp+48h+var_18], rax
0x18006c2d3  lea     rax, aRegflushkey; "RegFlushKey"
0x18006c2da  mov     [rsp+48h+var_20], rax
0x18006c2df  mov     dword ptr [rsp+48h+phkResult], 268h
0x18006c2e7  jmp     loc_18006C264
0x18006c2ec  xor     ebx, ebx
0x18006c2ee  mov     rcx, [rsp+48h+hKey]; hKey
0x18006c2f3  test    rcx, rcx
0x18006c2f6  jz      short loc_18006C2FE
0x18006c2f8  call    cs:__imp_RegCloseKey
0x18006c2fe  mov     eax, ebx
0x18006c300  add     rsp, 40h
0x18006c304  pop     rbx
0x18006c305  retn
```
