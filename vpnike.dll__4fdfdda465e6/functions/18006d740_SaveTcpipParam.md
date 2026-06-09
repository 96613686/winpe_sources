# SaveTcpipParam

- ea: `0x18006d740`
- end: `0x18006db81`
- name: `SaveTcpipParam`
- size: `1089`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18006d494`

## callees

- `0x18006d740`
- `0x18006e6c0`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `msvcrt!_wcslwr` at `0x18006d7d7`
- `msvcrt!_wcslwr` at `0x18006d7d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006db43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006db53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006db43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006db53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006dacb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006dacb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006d944`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006d9bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006da30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006da84`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006d944`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006d9bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006da30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006da84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d800`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d859`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d800`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d859`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18006d878`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18006d878`

## string_xrefs

- `0x18006d825`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006d834`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006d89e`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x18006d8ae`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x18006d96d`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18006daaa`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18006d980`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18006dab3`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18006dae9`: `RegDeleteValue(%ws) failed and returned %d`
- `0x18006db27`: `RegDeleteValue(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall SaveTcpipParam(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  const WCHAR *v6; // r8
  const wchar_t *v7; // rdx
  const CHAR *v8; // rcx
  size_t v9; // rdx
  const wchar_t *v10; // r8
  __int64 v11; // rsi
  const BYTE *v12; // r11
  const BYTE *v13; // r14
  size_t v14; // rdx
  STRSAFE_LPCWSTR v15; // r8
  __int64 v16; // rax
  __int64 v17; // rax
  const WCHAR *v18; // r14
  bool v19; // zf
  const BYTE *v20; // rcx
  __int64 v21; // rax
  const BYTE *v22; // rcx
  const BYTE *phkResult; // [rsp+20h] [rbp-E0h]
  HKEY v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[2044]; // [rsp+54h] [rbp-ACh] BYREF

  hKeya = 0;
  v25 = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800AB320 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800AB320 + 1),
        L"SaveTcpipParam");
  }
  else
  {
    TraceHlp("SaveTcpipParam");
  }
  _wcslwr(*(wchar_t **)(a2 + 8));
  v4 = RegOpenKeyExW(hKey, L"Interfaces", 0, 0x20006u, &hKeya);
  v5 = v4;
  if ( v4 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800AB320 )
        goto LABEL_62;
      v6 = L"Interfaces";
LABEL_9:
      v7 = L"RegOpenKeyEx(%ws) failed and returned %d";
LABEL_59:
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, v7, v6, v4);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB320, &v28);
      goto LABEL_62;
    }
LABEL_10:
    v8 = "RegOpenKeyEx(%ws) failed and returned %d";
LABEL_61:
    TraceHlp(v8);
    goto LABEL_62;
  }
  v4 = RegOpenKeyExW(hKeya, *(LPCWSTR *)(a2 + 8), 0, 0x20006u, &v25);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 != 2 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_62;
        v6 = *(const WCHAR **)(a2 + 8);
        goto LABEL_9;
      }
      goto LABEL_10;
    }
    v4 = RegCreateKeyW(hKeya, *(LPCWSTR *)(a2 + 8), &v25);
    v5 = v4;
    if ( v4 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_62;
        v6 = *(const WCHAR **)(a2 + 8);
        v7 = L"RegCreateKey(%ws) (v4) failed and returned %d";
        goto LABEL_59;
      }
      v8 = "RegCreateKey(%ws) (v4) failed and returned %d";
      goto LABEL_61;
    }
  }
  v11 = -1;
  if ( *(_DWORD *)a2 == 1 )
  {
    v12 = (const BYTE *)(a2 + 16);
    if ( !*(_WORD *)(a2 + 16) || (v13 = (const BYTE *)(a2 + 58), !*(_WORD *)(a2 + 58)) )
    {
      StringCbCopyW((STRSAFE_LPWSTR)(a2 + 16), v9, v10);
      v13 = (const BYTE *)(a2 + 58);
      StringCbCopyW((STRSAFE_LPWSTR)(a2 + 58), v14, v15);
    }
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)&v12[2 * v16] );
    v4 = RegSetValueExW(v25, L"DhcpIPAddress", 0, 1u, v12, 2 * v16);
    v5 = v4;
    if ( v4 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_62;
        v6 = L"DhcpIPAddress";
LABEL_32:
        v7 = L"RegSetValueEx(%ws) failed and returned %d";
        goto LABEL_59;
      }
      goto LABEL_33;
    }
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)&v13[2 * v17] );
    phkResult = v13;
    v18 = L"DhcpSubnetMask";
    v4 = RegSetValueExW(v25, L"DhcpSubnetMask", 0, 1u, phkResult, 2 * v17);
    v5 = v4;
    if ( v4 )
      goto LABEL_37;
  }
  v19 = *(_QWORD *)(a2 + 120) == 0;
  v20 = (const BYTE *)&v26;
  v26 = 0;
  v21 = -1;
  if ( !v19 )
    v20 = *(const BYTE **)(a2 + 120);
  do
    ++v21;
  while ( *(_WORD *)&v20[2 * v21] );
  v18 = L"Domain";
  v4 = RegSetValueExW(v25, L"Domain", 0, 1u, v20, 2 * v21 + 2);
  v5 = v4;
  if ( v4 )
  {
LABEL_37:
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800AB320 )
        goto LABEL_62;
      v6 = v18;
      goto LABEL_32;
    }
LABEL_33:
    v8 = "RegSetValueEx(%ws) failed and returned %d";
    goto LABEL_61;
  }
  v22 = (const BYTE *)&v26;
  if ( *(_QWORD *)(a2 + 104) )
    v22 = *(const BYTE **)(a2 + 104);
  if ( *(_WORD *)v22 == 32 )
  {
    v4 = RegDeleteValueW(v25, L"NameServer");
    v5 = v4;
    if ( !v4 )
      goto LABEL_62;
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v8 = "RegDeleteValue(%ws) failed and returned %d";
      goto LABEL_61;
    }
    if ( !(_QWORD)xmmword_1800AB320 )
      goto LABEL_62;
    v7 = L"RegDeleteValue(%ws) failed and returned %d";
    goto LABEL_58;
  }
  do
    ++v11;
  while ( *(_WORD *)&v22[2 * v11] );
  v4 = RegSetValueExW(v25, L"NameServer", 0, 1u, v22, 2 * v11 + 2);
  v5 = v4;
  if ( v4 )
  {
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v8 = "RegSetValueEx(%ws) failed and returned %d";
      goto LABEL_61;
    }
    if ( !(_QWORD)xmmword_1800AB320 )
      goto LABEL_62;
    v7 = L"RegSetValueEx(%ws) failed and returned %d";
LABEL_58:
    v6 = L"NameServer";
    goto LABEL_59;
  }
LABEL_62:
  if ( v25 )
    RegCloseKey(v25);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v5;
}

```

## disassembly

```asm
0x18006d740  mov     [rsp-8+arg_10], rbx
0x18006d745  push    rbp
0x18006d746  push    rsi
0x18006d747  push    rdi
0x18006d748  push    r14
0x18006d74a  push    r15
0x18006d74c  lea     rbp, [rsp-760h]
0x18006d754  sub     rsp, 860h
0x18006d75b  mov     rax, cs:__security_cookie
0x18006d762  xor     rax, rsp
0x18006d765  mov     [rbp+780h+var_30], rax
0x18006d76c  xor     r15d, r15d
0x18006d76f  mov     rdi, rdx
0x18006d772  mov     rbx, rcx
0x18006d775  mov     [rsp+880h+hKey], r15
0x18006d77a  xor     edx, edx; Val
0x18006d77c  mov     [rsp+880h+var_850], r15
0x18006d781  lea     rcx, [rsp+880h+var_82C]; void *
0x18006d786  mov     [rsp+880h+var_830], r15d
0x18006d78b  mov     r8d, 7FCh; Size
0x18006d791  call    memset_0
0x18006d796  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006d79d  jz      short loc_18006D7C7
0x18006d79f  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006d7a6  test    rdx, rdx
0x18006d7a9  jz      short loc_18006D7D3
0x18006d7ab  mov     rcx, cs:gIphlpEtwContext
0x18006d7b2  lea     r8, aSavetcpipparam; "SaveTcpipParam"
0x18006d7b9  mov     rax, cs:gIphlpTemplateFunc
0x18006d7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d7c5  jmp     short loc_18006D7D3
0x18006d7c7  lea     rcx, aSavetcpipparam_0; "SaveTcpipParam"
0x18006d7ce  call    TraceHlp
0x18006d7d3  mov     rcx, [rdi+8]; String
0x18006d7d7  call    cs:__imp__wcslwr
0x18006d7dd  lea     rax, [rsp+880h+hKey]
0x18006d7e2  mov     r14d, 20006h
0x18006d7e8  lea     rsi, aInterfaces; "Interfaces"
0x18006d7ef  mov     [rsp+880h+phkResult], rax; phkResult
0x18006d7f4  mov     r9d, r14d; samDesired
0x18006d7f7  mov     rdx, rsi; lpSubKey
0x18006d7fa  xor     r8d, r8d; ulOptions
0x18006d7fd  mov     rcx, rbx; hKey
0x18006d800  call    cs:__imp_RegOpenKeyExW
0x18006d806  mov     ebx, eax
0x18006d808  test    eax, eax
0x18006d80a  jz      short loc_18006D840
0x18006d80c  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006d813  jz      short loc_18006D831
0x18006d815  cmp     qword ptr cs:unk_1800AB320, r15
0x18006d81c  jz      loc_18006DB39
0x18006d822  mov     r8, rsi
0x18006d825  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006d82c  jmp     loc_18006DAF3
0x18006d831  mov     rdx, rsi
0x18006d834  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006d83b  jmp     loc_18006DB31
0x18006d840  mov     rdx, [rdi+8]; lpSubKey
0x18006d844  lea     rax, [rsp+880h+var_850]
0x18006d849  mov     rcx, [rsp+880h+hKey]; hKey
0x18006d84e  mov     r9d, r14d; samDesired
0x18006d851  xor     r8d, r8d; ulOptions
0x18006d854  mov     [rsp+880h+phkResult], rax; phkResult
0x18006d859  call    cs:__imp_RegOpenKeyExW
0x18006d85f  mov     ebx, eax
0x18006d861  test    eax, eax
0x18006d863  jz      short loc_18006D8E2
0x18006d865  cmp     eax, 2
0x18006d868  jnz     short loc_18006D8BA
0x18006d86a  mov     rdx, [rdi+8]; lpSubKey
0x18006d86e  lea     r8, [rsp+880h+var_850]; phkResult
0x18006d873  mov     rcx, [rsp+880h+hKey]; hKey
0x18006d878  call    cs:__imp_RegCreateKeyW
0x18006d87e  mov     ebx, eax
0x18006d880  test    eax, eax
0x18006d882  jz      short loc_18006D8E2
0x18006d884  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006d88b  jz      short loc_18006D8AA
0x18006d88d  cmp     qword ptr cs:unk_1800AB320, r15
0x18006d894  jz      loc_18006DB39
0x18006d89a  mov     r8, [rdi+8]
0x18006d89e  lea     rdx, aRegcreatekeyWs_1; "RegCreateKey(%ws) (v4) failed and retur"...
0x18006d8a5  jmp     loc_18006DAF3
0x18006d8aa  mov     rdx, [rdi+8]
0x18006d8ae  lea     rcx, aRegcreatekeyWs; "RegCreateKey(%ws) (v4) failed and retur"...
0x18006d8b5  jmp     loc_18006DB31
0x18006d8ba  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006d8c1  jz      short loc_18006D8D9
0x18006d8c3  cmp     qword ptr cs:unk_1800AB320, r15
0x18006d8ca  jz      loc_18006DB39
0x18006d8d0  mov     r8, [rdi+8]
0x18006d8d4  jmp     loc_18006D825
0x18006d8d9  mov     rdx, [rdi+8]
0x18006d8dd  jmp     loc_18006D834
0x18006d8e2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006d8e6  cmp     dword ptr [rdi], 1
0x18006d8e9  jnz     loc_18006D9E8
0x18006d8ef  lea     r11, [rdi+10h]
0x18006d8f3  cmp     r15w, [r11]
0x18006d8f7  jz      short loc_18006D903
0x18006d8f9  lea     r14, [rdi+3Ah]
0x18006d8fd  cmp     r15w, [r14]
0x18006d901  jnz     short loc_18006D917
0x18006d903  mov     rcx, r11; pszDest
0x18006d906  call    StringCbCopyW
0x18006d90b  lea     r14, [rdi+3Ah]
0x18006d90f  mov     rcx, r14; pszDest
0x18006d912  call    StringCbCopyW
0x18006d917  mov     rax, rsi
0x18006d91a  inc     rax
0x18006d91d  cmp     [r11+rax*2], r15w
0x18006d922  jnz     short loc_18006D91A
0x18006d924  mov     rcx, [rsp+880h+var_850]; hKey
0x18006d929  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x18006d930  add     eax, eax
0x18006d932  mov     r9d, 1; dwType
0x18006d938  mov     [rsp+880h+cbData], eax; cbData
0x18006d93c  xor     r8d, r8d; Reserved
0x18006d93f  mov     [rsp+880h+phkResult], r11; lpData
0x18006d944  call    cs:__imp_RegSetValueExW
0x18006d94a  mov     ebx, eax
0x18006d94c  test    eax, eax
0x18006d94e  jz      short loc_18006D98C
0x18006d950  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006d957  jz      short loc_18006D979
0x18006d959  cmp     qword ptr cs:unk_1800AB320, r15
0x18006d960  jz      loc_18006DB39
0x18006d966  lea     r8, aDhcpipaddress; "DhcpIPAddress"
0x18006d96d  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18006d974  jmp     loc_18006DAF3
0x18006d979  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x18006d980  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18006d987  jmp     loc_18006DB31
0x18006d98c  mov     rax, rsi
0x18006d98f  inc     rax
0x18006d992  cmp     [r14+rax*2], r15w
0x18006d997  jnz     short loc_18006D98F
0x18006d999  mov     rcx, [rsp+880h+var_850]; hKey
0x18006d99e  add     eax, eax
0x18006d9a0  mov     [rsp+880h+cbData], eax; cbData
0x18006d9a4  mov     r9d, 1; dwType
0x18006d9aa  mov     [rsp+880h+phkResult], r14; lpData
0x18006d9af  xor     r8d, r8d; Reserved
0x18006d9b2  lea     r14, aDhcpsubnetmask; "DhcpSubnetMask"
0x18006d9b9  mov     rdx, r14; lpValueName
0x18006d9bc  call    cs:__imp_RegSetValueExW
0x18006d9c2  mov     ebx, eax
0x18006d9c4  test    eax, eax
0x18006d9c6  jz      short loc_18006D9E8
0x18006d9c8  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006d9cf  jz      short loc_18006D9E3
0x18006d9d1  cmp     qword ptr cs:unk_1800AB320, r15
0x18006d9d8  jz      loc_18006DB39
0x18006d9de  mov     r8, r14
0x18006d9e1  jmp     short loc_18006D96D
0x18006d9e3  mov     rdx, r14
0x18006d9e6  jmp     short loc_18006D980
0x18006d9e8  cmp     [rdi+78h], r15
0x18006d9ec  lea     rcx, [rsp+880h+var_848]
0x18006d9f1  mov     [rsp+880h+var_848], r15d
0x18006d9f6  mov     rax, rsi
0x18006d9f9  cmovnz  rcx, [rdi+78h]
0x18006d9fe  inc     rax
0x18006da01  cmp     [rcx+rax*2], r15w
0x18006da06  jnz     short loc_18006D9FE
0x18006da08  lea     eax, ds:2[rax*2]
0x18006da0f  mov     r9d, 1; dwType
0x18006da15  mov     [rsp+880h+cbData], eax; cbData
0x18006da19  lea     r14, aDomain; "Domain"
0x18006da20  mov     [rsp+880h+phkResult], rcx; lpData
0x18006da25  xor     r8d, r8d; Reserved
0x18006da28  mov     rcx, [rsp+880h+var_850]; hKey
0x18006da2d  mov     rdx, r14; lpValueName
0x18006da30  call    cs:__imp_RegSetValueExW
0x18006da36  mov     ebx, eax
0x18006da38  test    eax, eax
0x18006da3a  jnz     short loc_18006D9C8
0x18006da3c  cmp     [rdi+68h], r15
0x18006da40  lea     rcx, [rsp+880h+var_848]
0x18006da45  lea     eax, [rbx+20h]
0x18006da48  cmovnz  rcx, [rdi+68h]
0x18006da4d  cmp     ax, [rcx]
0x18006da50  jz      short loc_18006DABC
0x18006da52  inc     rsi
0x18006da55  cmp     [rcx+rsi*2], r15w
0x18006da5a  jnz     short loc_18006DA52
0x18006da5c  lea     eax, ds:2[rsi*2]
0x18006da63  mov     r9d, 1; dwType
0x18006da69  mov     [rsp+880h+cbData], eax; cbData
0x18006da6d  lea     rdi, aNameserver; "NameServer"
0x18006da74  mov     [rsp+880h+phkResult], rcx; lpData
0x18006da79  xor     r8d, r8d; Reserved
0x18006da7c  mov     rcx, [rsp+880h+var_850]; hKey
0x18006da81  mov     rdx, rdi; lpValueName
0x18006da84  call    cs:__imp_RegSetValueExW
0x18006da8a  mov     ebx, eax
0x18006da8c  test    eax, eax
0x18006da8e  jz      loc_18006DB39
0x18006da94  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006da9b  jz      short loc_18006DAB3
0x18006da9d  cmp     qword ptr cs:unk_1800AB320, r15
0x18006daa4  jz      loc_18006DB39
0x18006daaa  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18006dab1  jmp     short loc_18006DAF0
0x18006dab3  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18006daba  jmp     short loc_18006DB2E
0x18006dabc  mov     rcx, [rsp+880h+var_850]; hKey
0x18006dac1  lea     rdi, aNameserver; "NameServer"
0x18006dac8  mov     rdx, rdi; lpValueName
0x18006dacb  call    cs:__imp_RegDeleteValueW
0x18006dad1  mov     ebx, eax
0x18006dad3  test    eax, eax
0x18006dad5  jz      short loc_18006DB39
0x18006dad7  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006dade  jz      short loc_18006DB27
0x18006dae0  cmp     qword ptr cs:unk_1800AB320, r15
0x18006dae7  jz      short loc_18006DB39
0x18006dae9  lea     rdx, aRegdeletevalue; "RegDeleteValue(%ws) failed and returned"...
0x18006daf0  mov     r8, rdi
0x18006daf3  mov     r9d, eax
0x18006daf6  mov     word ptr [rsp+880h+var_830], r15w
0x18006dafc  lea     rcx, [rsp+880h+var_830]
0x18006db01  call    FormatRRASErrorString
0x18006db06  mov     rdx, qword ptr cs:unk_1800AB320
0x18006db0d  lea     r8, [rsp+880h+var_830]
0x18006db12  mov     rcx, cs:gIphlpEtwContext
0x18006db19  mov     rax, cs:gIphlpTemplateFunc
0x18006db20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db25  jmp     short loc_18006DB39
0x18006db27  lea     rcx, aRegdeletevalue_2; "RegDeleteValue(%ws) failed and returned"...
0x18006db2e  mov     rdx, rdi
0x18006db31  mov     r8d, eax
0x18006db34  call    TraceHlp
0x18006db39  mov     rcx, [rsp+880h+var_850]; hKey
0x18006db3e  test    rcx, rcx
0x18006db41  jz      short loc_18006DB49
0x18006db43  call    cs:__imp_RegCloseKey
0x18006db49  mov     rcx, [rsp+880h+hKey]; hKey
0x18006db4e  test    rcx, rcx
0x18006db51  jz      short loc_18006DB59
0x18006db53  call    cs:__imp_RegCloseKey
0x18006db59  mov     eax, ebx
0x18006db5b  mov     rcx, [rbp+780h+var_30]
0x18006db62  xor     rcx, rsp; StackCookie
0x18006db65  call    __security_check_cookie
0x18006db6a  mov     rbx, [rsp+880h+arg_10]
0x18006db72  add     rsp, 860h
0x18006db79  pop     r15
0x18006db7b  pop     r14
0x18006db7d  pop     rdi
0x18006db7e  pop     rsi
0x18006db7f  pop     rbp
0x18006db80  retn
```
