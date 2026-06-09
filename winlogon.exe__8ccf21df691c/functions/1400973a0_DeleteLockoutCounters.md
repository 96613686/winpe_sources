# DeleteLockoutCounters

- ea: `0x1400973a0`
- end: `0x1400974aa`
- name: `DeleteLockoutCounters`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004d020`

## callees

- `0x140038250`
- `0x1400973a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14009742c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14009742c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14009745f`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14009745f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400973d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400973d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009749c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009749c`

## string_xrefs

- `0x1400973f4`: `RegOpenKeyEx`
- `0x140097408`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140097444`: `RegDeleteTree`

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
        &pPassword);
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
        &pPassword);
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
    &pPassword);
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x1400973a0  push    rbx
0x1400973a2  sub     rsp, 40h
0x1400973a6  lea     rax, [rsp+48h+hKey]
0x1400973ab  mov     [rsp+48h+hKey], 0
0x1400973b4  mov     r9d, 0F003Fh; samDesired
0x1400973ba  mov     [rsp+48h+phkResult], rax; phkResult
0x1400973bf  xor     r8d, r8d; ulOptions
0x1400973c2  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400973c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400973d0  call    cs:__imp_RegOpenKeyExW
0x1400973d6  mov     ebx, eax
0x1400973d8  lea     ecx, [rax-2]
0x1400973db  cmp     ecx, 1
0x1400973de  jbe     loc_140097490
0x1400973e4  test    eax, eax
0x1400973e6  jz      short loc_140097425
0x1400973e8  lea     rax, pPassword
0x1400973ef  mov     [rsp+48h+var_18], rax
0x1400973f4  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x1400973fb  mov     [rsp+48h+var_20], rax
0x140097400  mov     dword ptr [rsp+48h+phkResult], 260h
0x140097408  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x14009740f  mov     r8d, ebx
0x140097412  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140097419  mov     ecx, 1; unsigned int
0x14009741e  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097423  jmp     short loc_140097492
0x140097425  mov     rcx, [rsp+48h+hKey]; hKey
0x14009742a  xor     edx, edx; lpSubKey
0x14009742c  call    cs:__imp_RegDeleteTreeW
0x140097432  mov     ebx, eax
0x140097434  test    eax, eax
0x140097436  jz      short loc_14009745A
0x140097438  lea     rax, pPassword
0x14009743f  mov     [rsp+48h+var_18], rax
0x140097444  lea     rax, aRegdeletetree; "RegDeleteTree"
0x14009744b  mov     [rsp+48h+var_20], rax
0x140097450  mov     dword ptr [rsp+48h+phkResult], 265h
0x140097458  jmp     short loc_140097408
0x14009745a  mov     rcx, [rsp+48h+hKey]; hKey
0x14009745f  call    cs:__imp_RegFlushKey
0x140097465  mov     ebx, eax
0x140097467  test    eax, eax
0x140097469  jz      short loc_140097490
0x14009746b  lea     rax, pPassword
0x140097472  mov     [rsp+48h+var_18], rax
0x140097477  lea     rax, aRegflushkey; "RegFlushKey"
0x14009747e  mov     [rsp+48h+var_20], rax
0x140097483  mov     dword ptr [rsp+48h+phkResult], 268h
0x14009748b  jmp     loc_140097408
0x140097490  xor     ebx, ebx
0x140097492  mov     rcx, [rsp+48h+hKey]; hKey
0x140097497  test    rcx, rcx
0x14009749a  jz      short loc_1400974A2
0x14009749c  call    cs:__imp_RegCloseKey
0x1400974a2  mov     eax, ebx
0x1400974a4  add     rsp, 40h
0x1400974a8  pop     rbx
0x1400974a9  retn
```
