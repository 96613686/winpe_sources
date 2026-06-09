# SaveTcpipV6Param

- ea: `0x18006de0c`
- end: `0x18006e2ce`
- name: `SaveTcpipV6Param`
- size: `1218`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18006db88`

## callees

- `0x18006de0c`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `msvcrt!_wcslwr` at `0x18006deae`
- `msvcrt!_wcslwr` at `0x18006deae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e275`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e285`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e295`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e2a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e275`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e285`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e295`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e2a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006e1fd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006e1fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e12c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e1b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e12c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e1b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006df11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006df72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dffc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e057`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006df11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006df72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dffc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e057`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18006e075`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18006e075`

## string_xrefs

- `0x18006e151`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18006e1dc`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18006e160`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18006e1e5`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18006e21b`: `RegDeleteValue(%ws) failed and returned %d`
- `0x18006e259`: `RegDeleteValue(%ws) failed and returned %d`
- `0x18006df36`: `RegOpenKeyEx(%ws) (v4) failed and returned %d`
- `0x18006df45`: `RegOpenKeyEx(%ws) (v4) failed and returned %d`
- `0x18006e021`: `RegOpenKeyEx(%ws) (v6) failed and returned %d`
- `0x18006e030`: `RegOpenKeyEx(%ws) (v6) failed and returned %d`
- `0x18006e09a`: `RegCreateKey(%ws) (v6) failed and returned %d`
- `0x18006e0a9`: `RegCreateKey(%ws) (v6) failed and returned %d`

## pseudocode

```c
__int64 __fastcall SaveTcpipV6Param(HKEY hKey, HKEY a2, __int64 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  const WCHAR *v8; // r8
  const wchar_t *v9; // rdx
  const CHAR *v10; // rcx
  int v11; // r14d
  bool v12; // zf
  const BYTE *v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rax
  const BYTE *v16; // rcx
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v19; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v20; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  hKeya = 0;
  phkResult = 0;
  v20 = 0;
  v19 = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800AB320 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800AB320 + 1),
        L"SaveTcpipV6Param");
  }
  else
  {
    TraceHlp("SaveTcpipV6Param");
  }
  _wcslwr(*(wchar_t **)a3);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800AB320 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800AB320 + 1),
        L"SaveTcpipV6Param");
  }
  else
  {
    TraceHlp("SaveTcpipV6Param");
  }
  v6 = RegOpenKeyExW(hKey, L"Interfaces", 0, 0x20006u, &hKeya);
  v7 = v6;
  if ( v6 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800AB320 )
        goto LABEL_70;
      v8 = L"Interfaces";
LABEL_13:
      v9 = L"RegOpenKeyEx(%ws) (v4) failed and returned %d";
LABEL_67:
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, v9, v8, v6);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB320, &v23);
      goto LABEL_70;
    }
LABEL_14:
    v10 = "RegOpenKeyEx(%ws) (v4) failed and returned %d";
LABEL_69:
    TraceHlp(v10);
    goto LABEL_70;
  }
  v11 = 1;
  v6 = RegOpenKeyExW(hKeya, *(LPCWSTR *)a3, 0, 0x20006u, &phkResult);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 != 2 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_70;
        v8 = *(const WCHAR **)a3;
        goto LABEL_13;
      }
      goto LABEL_14;
    }
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800AB320 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800AB320 + 1),
          L"TcpIp V4 Interface sub-key not found continuing without it");
    }
    else
    {
      TraceHlp("TcpIp V4 Interface sub-key not found continuing without it");
    }
    v11 = 0;
  }
  v6 = RegOpenKeyExW(a2, L"Interfaces", 0, 0x20006u, &v20);
  v7 = v6;
  if ( v6 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800AB320 )
        goto LABEL_70;
      v8 = L"Interfaces";
LABEL_30:
      v9 = L"RegOpenKeyEx(%ws) (v6) failed and returned %d";
      goto LABEL_67;
    }
    goto LABEL_31;
  }
  v6 = RegOpenKeyExW(v20, *(LPCWSTR *)a3, 0, 0x20006u, &v19);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 != 2 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_70;
        v8 = *(const WCHAR **)a3;
        goto LABEL_30;
      }
LABEL_31:
      v10 = "RegOpenKeyEx(%ws) (v6) failed and returned %d";
      goto LABEL_69;
    }
    v6 = RegCreateKeyW(v20, *(LPCWSTR *)a3, &v19);
    v7 = v6;
    if ( v6 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_70;
        v8 = *(const WCHAR **)a3;
        v9 = L"RegCreateKey(%ws) (v6) failed and returned %d";
        goto LABEL_67;
      }
      v10 = "RegCreateKey(%ws) (v6) failed and returned %d";
      goto LABEL_69;
    }
  }
  v12 = *(_QWORD *)(a3 + 16) == 0;
  v13 = (const BYTE *)&v18;
  v18 = 0;
  if ( !v12 )
    v13 = *(const BYTE **)(a3 + 16);
  v14 = -1;
  if ( v11 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&v13[2 * v15] );
    v6 = RegSetValueExW(phkResult, L"Domain", 0, 1u, v13, 2 * v15 + 2);
    v7 = v6;
    if ( v6 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_70;
        v8 = L"Domain";
        v9 = L"RegSetValueEx(%ws) failed and returned %d";
        goto LABEL_67;
      }
      v10 = "RegSetValueEx(%ws) failed and returned %d";
      goto LABEL_69;
    }
  }
  v16 = (const BYTE *)&v18;
  if ( *(_QWORD *)(a3 + 8) )
    v16 = *(const BYTE **)(a3 + 8);
  if ( *(_WORD *)v16 == 32 )
  {
    v6 = RegDeleteValueW(v19, L"NameServer");
    v7 = v6;
    if ( !v6 )
      goto LABEL_70;
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v10 = "RegDeleteValue(%ws) failed and returned %d";
      goto LABEL_69;
    }
    if ( !(_QWORD)xmmword_1800AB320 )
      goto LABEL_70;
    v9 = L"RegDeleteValue(%ws) failed and returned %d";
    goto LABEL_66;
  }
  do
    ++v14;
  while ( *(_WORD *)&v16[2 * v14] );
  v6 = RegSetValueExW(v19, L"NameServer", 0, 1u, v16, 2 * v14 + 2);
  v7 = v6;
  if ( v6 )
  {
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v10 = "RegSetValueEx(%ws) failed and returned %d";
      goto LABEL_69;
    }
    if ( !(_QWORD)xmmword_1800AB320 )
      goto LABEL_70;
    v9 = L"RegSetValueEx(%ws) failed and returned %d";
LABEL_66:
    v8 = L"NameServer";
    goto LABEL_67;
  }
LABEL_70:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v19 )
    RegCloseKey(v19);
  if ( v20 )
    RegCloseKey(v20);
  return v7;
}

```

## disassembly

```asm
0x18006de0c  push    rbp
0x18006de0e  push    rbx
0x18006de0f  push    rsi
0x18006de10  push    rdi
0x18006de11  push    r12
0x18006de13  push    r14
0x18006de15  push    r15
0x18006de17  lea     rbp, [rsp-770h]
0x18006de1f  sub     rsp, 870h
0x18006de26  mov     rax, cs:__security_cookie
0x18006de2d  xor     rax, rsp
0x18006de30  mov     [rbp+7A0h+var_40], rax
0x18006de37  xor     r15d, r15d
0x18006de3a  mov     rdi, r8
0x18006de3d  mov     rsi, rdx
0x18006de40  mov     [rsp+8A0h+hKey], r15
0x18006de45  mov     rbx, rcx
0x18006de48  mov     [rsp+8A0h+var_858], r15
0x18006de4d  xor     edx, edx; Val
0x18006de4f  mov     [rsp+8A0h+var_860], r15
0x18006de54  mov     r8d, 7FCh; Size
0x18006de5a  mov     [rsp+8A0h+var_868], r15
0x18006de5f  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18006de64  mov     [rsp+8A0h+var_840], r15d
0x18006de69  call    memset_0
0x18006de6e  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006de75  jz      short loc_18006DE9F
0x18006de77  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006de7e  test    rdx, rdx
0x18006de81  jz      short loc_18006DEAB
0x18006de83  mov     rcx, cs:gIphlpEtwContext
0x18006de8a  lea     r8, aSavetcpipv6par; "SaveTcpipV6Param"
0x18006de91  mov     rax, cs:gIphlpTemplateFunc
0x18006de98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de9d  jmp     short loc_18006DEAB
0x18006de9f  lea     rcx, aSavetcpipv6par_0; "SaveTcpipV6Param"
0x18006dea6  call    TraceHlp
0x18006deab  mov     rcx, [rdi]; String
0x18006deae  call    cs:__imp__wcslwr
0x18006deb4  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006debb  jz      short loc_18006DEE5
0x18006debd  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006dec4  test    rdx, rdx
0x18006dec7  jz      short loc_18006DEF1
0x18006dec9  mov     rcx, cs:gIphlpEtwContext
0x18006ded0  lea     r8, aSavetcpipv6par; "SaveTcpipV6Param"
0x18006ded7  mov     rax, cs:gIphlpTemplateFunc
0x18006dede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dee3  jmp     short loc_18006DEF1
0x18006dee5  lea     rcx, aSavetcpipv6par_0; "SaveTcpipV6Param"
0x18006deec  call    TraceHlp
0x18006def1  lea     rax, [rsp+8A0h+hKey]
0x18006def6  mov     r9d, 20006h; samDesired
0x18006defc  lea     r12, aInterfaces; "Interfaces"
0x18006df03  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18006df08  mov     rdx, r12; lpSubKey
0x18006df0b  xor     r8d, r8d; ulOptions
0x18006df0e  mov     rcx, rbx; hKey
0x18006df11  call    cs:__imp_RegOpenKeyExW
0x18006df17  mov     ebx, eax
0x18006df19  test    eax, eax
0x18006df1b  jz      short loc_18006DF51
0x18006df1d  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006df24  jz      short loc_18006DF42
0x18006df26  cmp     qword ptr cs:unk_1800AB320, r15
0x18006df2d  jz      loc_18006E26B
0x18006df33  mov     r8, r12
0x18006df36  lea     rdx, aRegopenkeyexWs_1; "RegOpenKeyEx(%ws) (v4) failed and retur"...
0x18006df3d  jmp     loc_18006E225
0x18006df42  mov     rdx, r12
0x18006df45  lea     rcx, aRegopenkeyexWs_4; "RegOpenKeyEx(%ws) (v4) failed and retur"...
0x18006df4c  jmp     loc_18006E263
0x18006df51  mov     rdx, [rdi]; lpSubKey
0x18006df54  lea     rax, [rsp+8A0h+var_858]
0x18006df59  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18006df5e  mov     r9d, 20006h; samDesired
0x18006df64  xor     r8d, r8d; ulOptions
0x18006df67  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18006df6c  mov     r14d, 1
0x18006df72  call    cs:__imp_RegOpenKeyExW
0x18006df78  mov     ebx, eax
0x18006df7a  test    eax, eax
0x18006df7c  jz      short loc_18006DFE3
0x18006df7e  cmp     eax, 2
0x18006df81  jz      short loc_18006DFA3
0x18006df83  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006df8a  jz      short loc_18006DF9E
0x18006df8c  cmp     qword ptr cs:unk_1800AB320, r15
0x18006df93  jz      loc_18006E26B
0x18006df99  mov     r8, [rdi]
0x18006df9c  jmp     short loc_18006DF36
0x18006df9e  mov     rdx, [rdi]
0x18006dfa1  jmp     short loc_18006DF45
0x18006dfa3  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006dfaa  jz      short loc_18006DFD4
0x18006dfac  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006dfb3  test    rdx, rdx
0x18006dfb6  jz      short loc_18006DFE0
0x18006dfb8  mov     rcx, cs:gIphlpEtwContext
0x18006dfbf  lea     r8, aTcpipV4Interfa; "TcpIp V4 Interface sub-key not found co"...
0x18006dfc6  mov     rax, cs:gIphlpTemplateFunc
0x18006dfcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfd2  jmp     short loc_18006DFE0
0x18006dfd4  lea     rcx, aTcpipV4Interfa_0; "TcpIp V4 Interface sub-key not found co"...
0x18006dfdb  call    TraceHlp
0x18006dfe0  mov     r14d, r15d
0x18006dfe3  lea     rax, [rsp+8A0h+var_860]
0x18006dfe8  mov     r9d, 20006h; samDesired
0x18006dfee  xor     r8d, r8d; ulOptions
0x18006dff1  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18006dff6  mov     rdx, r12; lpSubKey
0x18006dff9  mov     rcx, rsi; hKey
0x18006dffc  call    cs:__imp_RegOpenKeyExW
0x18006e002  mov     ebx, eax
0x18006e004  test    eax, eax
0x18006e006  jz      short loc_18006E03C
0x18006e008  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e00f  jz      short loc_18006E02D
0x18006e011  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e018  jz      loc_18006E26B
0x18006e01e  mov     r8, r12
0x18006e021  lea     rdx, aRegopenkeyexWs_0; "RegOpenKeyEx(%ws) (v6) failed and retur"...
0x18006e028  jmp     loc_18006E225
0x18006e02d  mov     rdx, r12
0x18006e030  lea     rcx, aRegopenkeyexWs_3; "RegOpenKeyEx(%ws) (v6) failed and retur"...
0x18006e037  jmp     loc_18006E263
0x18006e03c  mov     rdx, [rdi]; lpSubKey
0x18006e03f  lea     rax, [rsp+8A0h+var_868]
0x18006e044  mov     rcx, [rsp+8A0h+var_860]; hKey
0x18006e049  mov     r9d, 20006h; samDesired
0x18006e04f  xor     r8d, r8d; ulOptions
0x18006e052  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18006e057  call    cs:__imp_RegOpenKeyExW
0x18006e05d  mov     ebx, eax
0x18006e05f  test    eax, eax
0x18006e061  jz      short loc_18006E0DB
0x18006e063  cmp     eax, 2
0x18006e066  jnz     short loc_18006E0B5
0x18006e068  mov     rdx, [rdi]; lpSubKey
0x18006e06b  lea     r8, [rsp+8A0h+var_868]; phkResult
0x18006e070  mov     rcx, [rsp+8A0h+var_860]; hKey
0x18006e075  call    cs:__imp_RegCreateKeyW
0x18006e07b  mov     ebx, eax
0x18006e07d  test    eax, eax
0x18006e07f  jz      short loc_18006E0DB
0x18006e081  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e088  jz      short loc_18006E0A6
0x18006e08a  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e091  jz      loc_18006E26B
0x18006e097  mov     r8, [rdi]
0x18006e09a  lea     rdx, aRegcreatekeyWs_2; "RegCreateKey(%ws) (v6) failed and retur"...
0x18006e0a1  jmp     loc_18006E225
0x18006e0a6  mov     rdx, [rdi]
0x18006e0a9  lea     rcx, aRegcreatekeyWs_0; "RegCreateKey(%ws) (v6) failed and retur"...
0x18006e0b0  jmp     loc_18006E263
0x18006e0b5  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e0bc  jz      short loc_18006E0D3
0x18006e0be  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e0c5  jz      loc_18006E26B
0x18006e0cb  mov     r8, [rdi]
0x18006e0ce  jmp     loc_18006E021
0x18006e0d3  mov     rdx, [rdi]
0x18006e0d6  jmp     loc_18006E030
0x18006e0db  cmp     [rdi+10h], r15
0x18006e0df  lea     rcx, [rsp+8A0h+var_870]
0x18006e0e4  mov     [rsp+8A0h+var_870], r15d
0x18006e0e9  cmovnz  rcx, [rdi+10h]
0x18006e0ee  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006e0f2  test    r14d, r14d
0x18006e0f5  jz      short loc_18006E16C
0x18006e0f7  mov     rax, rsi
0x18006e0fa  inc     rax
0x18006e0fd  cmp     [rcx+rax*2], r15w
0x18006e102  jnz     short loc_18006E0FA
0x18006e104  lea     eax, ds:2[rax*2]
0x18006e10b  mov     r9d, 1; dwType
0x18006e111  mov     [rsp+8A0h+cbData], eax; cbData
0x18006e115  lea     r14, aDomain; "Domain"
0x18006e11c  mov     [rsp+8A0h+phkResult], rcx; lpData
0x18006e121  xor     r8d, r8d; Reserved
0x18006e124  mov     rcx, [rsp+8A0h+var_858]; hKey
0x18006e129  mov     rdx, r14; lpValueName
0x18006e12c  call    cs:__imp_RegSetValueExW
0x18006e132  mov     ebx, eax
0x18006e134  test    eax, eax
0x18006e136  jz      short loc_18006E16C
0x18006e138  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e13f  jz      short loc_18006E15D
0x18006e141  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e148  jz      loc_18006E26B
0x18006e14e  mov     r8, r14
0x18006e151  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18006e158  jmp     loc_18006E225
0x18006e15d  mov     rdx, r14
0x18006e160  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18006e167  jmp     loc_18006E263
0x18006e16c  cmp     [rdi+8], r15
0x18006e170  lea     rcx, [rsp+8A0h+var_870]
0x18006e175  mov     eax, 20h ; ' '
0x18006e17a  cmovnz  rcx, [rdi+8]
0x18006e17f  cmp     ax, [rcx]
0x18006e182  jz      short loc_18006E1EE
0x18006e184  inc     rsi
0x18006e187  cmp     [rcx+rsi*2], r15w
0x18006e18c  jnz     short loc_18006E184
0x18006e18e  lea     eax, ds:2[rsi*2]
0x18006e195  mov     r9d, 1; dwType
0x18006e19b  mov     [rsp+8A0h+cbData], eax; cbData
0x18006e19f  lea     rdi, aNameserver; "NameServer"
0x18006e1a6  mov     [rsp+8A0h+phkResult], rcx; lpData
0x18006e1ab  xor     r8d, r8d; Reserved
0x18006e1ae  mov     rcx, [rsp+8A0h+var_868]; hKey
0x18006e1b3  mov     rdx, rdi; lpValueName
0x18006e1b6  call    cs:__imp_RegSetValueExW
0x18006e1bc  mov     ebx, eax
0x18006e1be  test    eax, eax
0x18006e1c0  jz      loc_18006E26B
0x18006e1c6  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e1cd  jz      short loc_18006E1E5
0x18006e1cf  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e1d6  jz      loc_18006E26B
0x18006e1dc  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18006e1e3  jmp     short loc_18006E222
0x18006e1e5  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18006e1ec  jmp     short loc_18006E260
0x18006e1ee  mov     rcx, [rsp+8A0h+var_868]; hKey
0x18006e1f3  lea     rdi, aNameserver; "NameServer"
0x18006e1fa  mov     rdx, rdi; lpValueName
0x18006e1fd  call    cs:__imp_RegDeleteValueW
0x18006e203  mov     ebx, eax
0x18006e205  test    eax, eax
0x18006e207  jz      short loc_18006E26B
0x18006e209  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e210  jz      short loc_18006E259
0x18006e212  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e219  jz      short loc_18006E26B
0x18006e21b  lea     rdx, aRegdeletevalue; "RegDeleteValue(%ws) failed and returned"...
0x18006e222  mov     r8, rdi
0x18006e225  mov     r9d, eax
0x18006e228  mov     word ptr [rsp+8A0h+var_840], r15w
0x18006e22e  lea     rcx, [rsp+8A0h+var_840]
0x18006e233  call    FormatRRASErrorString
0x18006e238  mov     rdx, qword ptr cs:unk_1800AB320
0x18006e23f  lea     r8, [rsp+8A0h+var_840]
0x18006e244  mov     rcx, cs:gIphlpEtwContext
0x18006e24b  mov     rax, cs:gIphlpTemplateFunc
0x18006e252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e257  jmp     short loc_18006E26B
0x18006e259  lea     rcx, aRegdeletevalue_2; "RegDeleteValue(%ws) failed and returned"...
0x18006e260  mov     rdx, rdi
0x18006e263  mov     r8d, eax
0x18006e266  call    TraceHlp
0x18006e26b  mov     rcx, [rsp+8A0h+var_858]; hKey
0x18006e270  test    rcx, rcx
0x18006e273  jz      short loc_18006E27B
0x18006e275  call    cs:__imp_RegCloseKey
0x18006e27b  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18006e280  test    rcx, rcx
0x18006e283  jz      short loc_18006E28B
0x18006e285  call    cs:__imp_RegCloseKey
0x18006e28b  mov     rcx, [rsp+8A0h+var_868]; hKey
0x18006e290  test    rcx, rcx
0x18006e293  jz      short loc_18006E29B
0x18006e295  call    cs:__imp_RegCloseKey
0x18006e29b  mov     rcx, [rsp+8A0h+var_860]; hKey
0x18006e2a0  test    rcx, rcx
0x18006e2a3  jz      short loc_18006E2AB
0x18006e2a5  call    cs:__imp_RegCloseKey
0x18006e2ab  mov     eax, ebx
0x18006e2ad  mov     rcx, [rbp+7A0h+var_40]
0x18006e2b4  xor     rcx, rsp; StackCookie
0x18006e2b7  call    __security_check_cookie
0x18006e2bc  add     rsp, 870h
0x18006e2c3  pop     r15
0x18006e2c5  pop     r14
0x18006e2c7  pop     r12
0x18006e2c9  pop     rdi
0x18006e2ca  pop     rsi
0x18006e2cb  pop     rbx
0x18006e2cc  pop     rbp
0x18006e2cd  retn
```
