# PfPrAgentsLoadFromRegistry

- ea: `0x18008c9c4`
- end: `0x18008cc0d`
- name: `PfPrAgentsLoadFromRegistry`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800838e4`

## callees

- `0x18006ea7c`
- `0x1800848a0`
- `0x18008c830`
- `0x18008c9c4`
- `0x18008cc64`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!strchr` at `0x18008ca58`
- `msvcrt!strchr` at `0x18008ca58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008cada`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008cada`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008cab9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008cab9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x18008cb6a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x18008cb6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008caf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008caf5`

## string_xrefs

- `0x18008caac`: `Agents`

## pseudocode

```c
__int64 __fastcall PfPrAgentsLoadFromRegistry(__int64 a1)
{
  char *v1; // rsi
  const char *v3; // rdi
  int v4; // r12d
  __int64 v5; // rax
  const char *v6; // r15
  DWORD i; // r14d
  char *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  LSTATUS v14; // eax
  unsigned int v15; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[40]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[272]; // [rsp+B0h] [rbp-50h] BYREF
  char pszDest[272]; // [rsp+1C0h] [rbp+C0h] BYREF

  v1 = 0;
  cchValueName = 0;
  Type = 0;
  hKey = 0;
  Data[0] = 0;
  cbData = 0;
  v3 = *(const char **)(*(_QWORD *)&PfSvcGlobals + 312LL);
  if ( v3 )
  {
    v4 = 1;
    v5 = -1;
    do
      ++v5;
    while ( v3[v5] );
    v6 = &v3[v5];
    goto LABEL_5;
  }
  v6 = 0;
  v4 = 0;
  v11 = RegOpenKeyExW(*(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL), L"Agents", 0, 0x20019u, &hKey);
  v12 = v11;
  if ( !v11 )
  {
LABEL_5:
    for ( i = 0; ; ++i )
    {
      if ( v4 )
      {
        if ( v3 >= v6 )
          goto LABEL_15;
        v8 = strchr(v3, 44);
        if ( v8 )
          *v8 = 0;
        StringCchCopyA(pszDest, 0x104u, v3);
        v10 = -1;
        do
          ++v10;
        while ( v3[v10] );
        v3 += v10 + 1;
      }
      else
      {
        cchValueName = 260;
        cbData = 260;
        v14 = RegEnumValueA(hKey, i, pszDest, &cchValueName, 0, &Type, Data, &cbData);
        v12 = v14;
        if ( v14 == 259 )
          goto LABEL_15;
        if ( v14 )
          goto LABEL_16;
        if ( Type - 1 > 1 )
          continue;
      }
      if ( !cbData || !Data[0] )
      {
        if ( !v1 )
        {
          if ( (unsigned int)PfPrGetModuleName(v9, WideCharStr) )
            continue;
          v1 = (char *)PfSvUnicodeToAnsi(WideCharStr);
          if ( !v1 )
            continue;
        }
        StringCchCopyA((STRSAFE_LPSTR)Data, 0x104u, v1);
      }
      Data[259] = 0;
      pszDest[259] = 0;
      v15 = PfPrAgentLoad(a1, Data, pszDest);
      v12 = v15;
      if ( v15 && v15 != -536870384 )
        goto LABEL_16;
    }
  }
  if ( v11 == 2 )
LABEL_15:
    v12 = 0;
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v1 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v1);
  return v12;
}

```

## disassembly

```asm
0x18008c9c4  push    rbp
0x18008c9c6  push    rbx
0x18008c9c7  push    rsi
0x18008c9c8  push    rdi
0x18008c9c9  push    r12
0x18008c9cb  push    r13
0x18008c9cd  push    r14
0x18008c9cf  push    r15
0x18008c9d1  lea     rbp, [rsp-1E8h]
0x18008c9d9  sub     rsp, 2E8h
0x18008c9e0  mov     rax, cs:__security_cookie
0x18008c9e7  xor     rax, rsp
0x18008c9ea  mov     [rbp+220h+var_50], rax
0x18008c9f1  xor     esi, esi
0x18008c9f3  mov     [rsp+320h+cchValueName], 0
0x18008c9fb  mov     r13, rcx
0x18008c9fe  mov     [rsp+320h+Type], 0
0x18008ca06  mov     rcx, cs:PfSvcGlobals
0x18008ca0d  mov     [rsp+320h+hKey], 0
0x18008ca16  mov     [rbp+220h+Data], sil
0x18008ca1a  mov     [rsp+320h+cbData], esi
0x18008ca1e  mov     rdi, [rcx+138h]
0x18008ca25  test    rdi, rdi
0x18008ca28  jz      short loc_18008CA92
0x18008ca2a  lea     r12d, [rsi+1]
0x18008ca2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008ca32  inc     rax
0x18008ca35  cmp     [rdi+rax], sil
0x18008ca39  jnz     short loc_18008CA32
0x18008ca3b  lea     r15, [rax+rdi]
0x18008ca3f  xor     r14d, r14d
0x18008ca42  test    r12d, r12d
0x18008ca45  jz      loc_18008CB20
0x18008ca4b  cmp     rdi, r15
0x18008ca4e  jnb     short loc_18008CACE
0x18008ca50  mov     edx, 2Ch ; ','; Val
0x18008ca55  mov     rcx, rdi; Str
0x18008ca58  call    cs:__imp_strchr
0x18008ca5e  test    rax, rax
0x18008ca61  jz      short loc_18008CA66
0x18008ca63  mov     byte ptr [rax], 0
0x18008ca66  mov     r8, rdi; pszSrc
0x18008ca69  lea     rcx, [rbp+220h+pszDest]; pszDest
0x18008ca70  mov     edx, 104h; cchDest
0x18008ca75  call    StringCchCopyA
0x18008ca7a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008ca7e  inc     rax
0x18008ca81  cmp     byte ptr [rdi+rax], 0
0x18008ca85  jnz     short loc_18008CA7E
0x18008ca87  inc     rdi
0x18008ca8a  add     rdi, rax
0x18008ca8d  jmp     loc_18008CB90
0x18008ca92  mov     rcx, [rcx+598h]; hKey
0x18008ca99  lea     rax, [rsp+320h+hKey]
0x18008ca9e  mov     r9d, 20019h; samDesired
0x18008caa4  mov     [rsp+320h+phkResult], rax; phkResult
0x18008caa9  xor     r8d, r8d; ulOptions
0x18008caac  lea     rdx, aAgents; "Agents"
0x18008cab3  xor     r15d, r15d
0x18008cab6  xor     r12d, r12d
0x18008cab9  call    cs:__imp_RegOpenKeyExW
0x18008cabf  mov     ebx, eax
0x18008cac1  test    eax, eax
0x18008cac3  jz      loc_18008CA3F
0x18008cac9  cmp     eax, 2
0x18008cacc  jnz     short loc_18008CAD0
0x18008cace  xor     ebx, ebx
0x18008cad0  mov     rcx, [rsp+320h+hKey]; hKey
0x18008cad5  test    rcx, rcx
0x18008cad8  jz      short loc_18008CAE0
0x18008cada  call    cs:__imp_RegCloseKey
0x18008cae0  test    rsi, rsi
0x18008cae3  jz      short loc_18008CAFB
0x18008cae5  mov     rcx, cs:PfSvcGlobals
0x18008caec  mov     r8, rsi; lpMem
0x18008caef  xor     edx, edx; dwFlags
0x18008caf1  mov     rcx, [rcx+58h]; hHeap
0x18008caf5  call    cs:__imp_HeapFree
0x18008cafb  mov     eax, ebx
0x18008cafd  mov     rcx, [rbp+220h+var_50]
0x18008cb04  xor     rcx, rsp; StackCookie
0x18008cb07  call    __security_check_cookie
0x18008cb0c  add     rsp, 2E8h
0x18008cb13  pop     r15
0x18008cb15  pop     r14
0x18008cb17  pop     r13
0x18008cb19  pop     r12
0x18008cb1b  pop     rdi
0x18008cb1c  pop     rsi
0x18008cb1d  pop     rbx
0x18008cb1e  pop     rbp
0x18008cb1f  retn
0x18008cb20  mov     rcx, [rsp+320h+hKey]; hKey
0x18008cb25  lea     rax, [rsp+320h+cbData]
0x18008cb2a  mov     [rsp+320h+lpcbData], rax; lpcbData
0x18008cb2f  lea     r9, [rsp+320h+cchValueName]; lpcchValueName
0x18008cb34  lea     rax, [rbp+220h+Data]
0x18008cb38  mov     [rsp+320h+cchValueName], 104h
0x18008cb40  mov     [rsp+320h+lpData], rax; lpData
0x18008cb45  lea     r8, [rbp+220h+pszDest]; lpValueName
0x18008cb4c  lea     rax, [rsp+320h+Type]
0x18008cb51  mov     [rsp+320h+cbData], 104h
0x18008cb59  mov     [rsp+320h+lpType], rax; lpType
0x18008cb5e  mov     edx, r14d; dwIndex
0x18008cb61  mov     [rsp+320h+phkResult], 0; lpReserved
0x18008cb6a  call    cs:__imp_RegEnumValueA
0x18008cb70  mov     ebx, eax
0x18008cb72  cmp     eax, 103h
0x18008cb77  jz      loc_18008CACE
0x18008cb7d  test    eax, eax
0x18008cb7f  jnz     loc_18008CAD0
0x18008cb85  mov     eax, [rsp+320h+Type]
0x18008cb89  dec     eax
0x18008cb8b  cmp     eax, 1
0x18008cb8e  ja      short loc_18008CC05
0x18008cb90  cmp     [rsp+320h+cbData], 0
0x18008cb95  jz      short loc_18008CB9D
0x18008cb97  cmp     [rbp+220h+Data], 0
0x18008cb9b  jnz     short loc_18008CBD3
0x18008cb9d  test    rsi, rsi
0x18008cba0  jnz     short loc_18008CBC2
0x18008cba2  lea     rdx, [rsp+320h+WideCharStr]
0x18008cba7  call    PfPrGetModuleName
0x18008cbac  test    eax, eax
0x18008cbae  jnz     short loc_18008CC05
0x18008cbb0  lea     rcx, [rsp+320h+WideCharStr]; lpWideCharStr
0x18008cbb5  call    PfSvUnicodeToAnsi
0x18008cbba  mov     rsi, rax
0x18008cbbd  test    rax, rax
0x18008cbc0  jz      short loc_18008CC05
0x18008cbc2  mov     r8, rsi; pszSrc
0x18008cbc5  lea     rcx, [rbp+220h+Data]; pszDest
0x18008cbc9  mov     edx, 104h; cchDest
0x18008cbce  call    StringCchCopyA
0x18008cbd3  lea     r8, [rbp+220h+pszDest]
0x18008cbda  mov     [rbp+220h+var_16D], 0
0x18008cbe1  lea     rdx, [rbp+220h+Data]
0x18008cbe5  mov     [rbp+220h+var_5D], 0
0x18008cbec  mov     rcx, r13
0x18008cbef  call    PfPrAgentLoad
0x18008cbf4  mov     ebx, eax
0x18008cbf6  test    eax, eax
0x18008cbf8  jz      short loc_18008CC05
0x18008cbfa  cmp     eax, 0E0000210h
0x18008cbff  jnz     loc_18008CAD0
0x18008cc05  inc     r14d
0x18008cc08  jmp     loc_18008CA42
```
