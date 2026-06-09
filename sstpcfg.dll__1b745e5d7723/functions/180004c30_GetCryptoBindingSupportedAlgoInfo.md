# GetCryptoBindingSupportedAlgoInfo

- ea: `0x180004c30`
- end: `0x180004f01`
- name: `GetCryptoBindingSupportedAlgoInfo`
- size: `721`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180005ea0`
- `0x180007450`

## callees

- `0x180004c30`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ed9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ed9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d85`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004e48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d85`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004e48`

## string_xrefs

- `0x180004c9e`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x180004d15`: `Unable to open the parameter store for SSTPSVC: %d`

## pseudocode

```c
unsigned int __fastcall GetCryptoBindingSupportedAlgoInfo(__int64 a1, _BYTE *a2)
{
  unsigned int result; // eax
  __int64 v5; // r8
  unsigned int v6; // esi
  HKEY v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // esi
  unsigned int v11; // eax
  __int64 v12; // r8
  unsigned int v13; // esi
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[2044]; // [rsp+54h] [rbp-ACh] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  v18 = 0;
  *(_DWORD *)Data = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( !a1 )
    a1 = -2147483646;
  result = RegOpenKeyExW((HKEY)a1, L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters", 0, 0x20019u, &hKey);
  v6 = result;
  if ( result )
  {
    *a2 = 2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      result = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, v5, result);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"Unable to open the parameter store for SSTPSVC: %d", v6);
      return ((__int64 (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
               gSstpCfgEtwContext,
               xmmword_1800146E0,
               &v18);
    }
  }
  else
  {
    v7 = hKey;
    *a2 |= 2u;
    cbData = 4;
    v8 = RegQueryValueExW(v7, L"SHA256Enabled", 0, &Type, Data, &cbData);
    v10 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, v9, v8);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"Unable to get SHA256Enabled flag - assuming enabled: %d", v10);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v18);
      }
    }
    else if ( Type == 4 && !*(_DWORD *)Data )
    {
      *a2 &= ~2u;
    }
    cbData = 4;
    v11 = RegQueryValueExW(hKey, L"SHA1Enabled", 0, &Type, Data, &cbData);
    v13 = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, v12, v11);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"Unable to get SHA1Enabled flag - assuming not enabled: %d", v13);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v18);
      }
    }
    else if ( Type == 4 && *(_DWORD *)Data )
    {
      *a2 |= 1u;
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180004c30  mov     [rsp-8+arg_10], rbx
0x180004c35  push    rbp
0x180004c36  push    rsi
0x180004c37  push    rdi
0x180004c38  lea     rbp, [rsp-760h]
0x180004c40  sub     rsp, 860h
0x180004c47  mov     rax, cs:__security_cookie
0x180004c4e  xor     rax, rsp
0x180004c51  mov     [rbp+770h+var_20], rax
0x180004c58  mov     rdi, rdx
0x180004c5b  mov     [rsp+870h+hKey], 0
0x180004c64  mov     rbx, rcx
0x180004c67  mov     [rsp+870h+Type], 0
0x180004c6f  xor     eax, eax
0x180004c71  mov     [rsp+870h+cbData], 0
0x180004c79  xor     edx, edx; Val
0x180004c7b  mov     [rsp+870h+var_820], eax
0x180004c7f  lea     rcx, [rsp+870h+var_81C]; void *
0x180004c84  mov     dword ptr [rsp+870h+Data], 0
0x180004c8c  mov     r8d, 7FCh; Size
0x180004c92  call    memset_0
0x180004c97  mov     rax, 0FFFFFFFF80000002h
0x180004c9e  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x180004ca5  test    rbx, rbx
0x180004ca8  mov     r9d, 20019h; samDesired
0x180004cae  cmovz   rbx, rax
0x180004cb2  lea     rax, [rsp+870h+hKey]
0x180004cb7  mov     rcx, rbx; hKey
0x180004cba  mov     [rsp+870h+phkResult], rax; phkResult
0x180004cbf  xor     r8d, r8d; ulOptions
0x180004cc2  call    cs:__imp_RegOpenKeyExW
0x180004cc8  mov     esi, eax
0x180004cca  test    eax, eax
0x180004ccc  jz      loc_180004D52
0x180004cd2  mov     byte ptr [rdi], 2
0x180004cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cdc  lea     rbx, WPP_GLOBAL_Control
0x180004ce3  cmp     rcx, rbx
0x180004ce6  jz      short loc_180004D05
0x180004ce8  test    byte ptr [rcx+1Ch], 40h
0x180004cec  jz      short loc_180004D05
0x180004cee  cmp     byte ptr [rcx+19h], 1
0x180004cf2  jb      short loc_180004D05
0x180004cf4  mov     rcx, [rcx+10h]
0x180004cf8  mov     edx, 93h
0x180004cfd  mov     r9d, eax
0x180004d00  call    WPP_SF_d
0x180004d05  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180004d0d  jz      loc_180004EDF
0x180004d13  xor     eax, eax
0x180004d15  lea     rdx, aUnableToOpenTh_1; "Unable to open the parameter store for "...
0x180004d1c  mov     r8d, esi
0x180004d1f  mov     word ptr [rsp+870h+var_820], ax
0x180004d24  lea     rcx, [rsp+870h+var_820]
0x180004d29  call    FormatRRASErrorString
0x180004d2e  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180004d35  lea     r8, [rsp+870h+var_820]
0x180004d3a  mov     rcx, cs:gSstpCfgEtwContext
0x180004d41  mov     rax, cs:gSstpCfgTemplateFunc
0x180004d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d4d  jmp     loc_180004EDF
0x180004d52  mov     rcx, [rsp+870h+hKey]; hKey
0x180004d57  lea     rax, [rsp+870h+cbData]
0x180004d5c  or      byte ptr [rdi], 2
0x180004d5f  lea     r9, [rsp+870h+Type]; lpType
0x180004d64  mov     [rsp+870h+lpcbData], rax; lpcbData
0x180004d69  lea     rdx, aSha256enabled; "SHA256Enabled"
0x180004d70  lea     rax, [rsp+870h+Data]
0x180004d75  mov     [rsp+870h+cbData], 4
0x180004d7d  xor     r8d, r8d; lpReserved
0x180004d80  mov     [rsp+870h+phkResult], rax; lpData
0x180004d85  call    cs:__imp_RegQueryValueExW
0x180004d8b  lea     rbx, WPP_GLOBAL_Control
0x180004d92  mov     esi, eax
0x180004d94  test    eax, eax
0x180004d96  jz      short loc_180004E07
0x180004d98  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d9f  cmp     rcx, rbx
0x180004da2  jz      short loc_180004DC1
0x180004da4  test    byte ptr [rcx+1Ch], 40h
0x180004da8  jz      short loc_180004DC1
0x180004daa  cmp     byte ptr [rcx+19h], 1
0x180004dae  jb      short loc_180004DC1
0x180004db0  mov     rcx, [rcx+10h]
0x180004db4  mov     edx, 94h
0x180004db9  mov     r9d, eax
0x180004dbc  call    WPP_SF_d
0x180004dc1  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180004dc9  jz      short loc_180004E18
0x180004dcb  xor     eax, eax
0x180004dcd  lea     rdx, aUnableToGetSha_0; "Unable to get SHA256Enabled flag - assu"...
0x180004dd4  mov     r8d, esi
0x180004dd7  mov     word ptr [rsp+870h+var_820], ax
0x180004ddc  lea     rcx, [rsp+870h+var_820]
0x180004de1  call    FormatRRASErrorString
0x180004de6  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180004ded  lea     r8, [rsp+870h+var_820]
0x180004df2  mov     rcx, cs:gSstpCfgEtwContext
0x180004df9  mov     rax, cs:gSstpCfgTemplateFunc
0x180004e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e05  jmp     short loc_180004E18
0x180004e07  cmp     [rsp+870h+Type], 4
0x180004e0c  jnz     short loc_180004E18
0x180004e0e  cmp     dword ptr [rsp+870h+Data], 0
0x180004e13  jnz     short loc_180004E18
0x180004e15  and     byte ptr [rdi], 0FDh
0x180004e18  mov     rcx, [rsp+870h+hKey]; hKey
0x180004e1d  lea     rax, [rsp+870h+cbData]
0x180004e22  mov     [rsp+870h+lpcbData], rax; lpcbData
0x180004e27  lea     r9, [rsp+870h+Type]; lpType
0x180004e2c  lea     rax, [rsp+870h+Data]
0x180004e31  mov     [rsp+870h+cbData], 4
0x180004e39  xor     r8d, r8d; lpReserved
0x180004e3c  mov     [rsp+870h+phkResult], rax; lpData
0x180004e41  lea     rdx, aSha1enabled; "SHA1Enabled"
0x180004e48  call    cs:__imp_RegQueryValueExW
0x180004e4e  mov     esi, eax
0x180004e50  test    eax, eax
0x180004e52  jz      short loc_180004EC3
0x180004e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e5b  cmp     rcx, rbx
0x180004e5e  jz      short loc_180004E7D
0x180004e60  test    byte ptr [rcx+1Ch], 40h
0x180004e64  jz      short loc_180004E7D
0x180004e66  cmp     byte ptr [rcx+19h], 1
0x180004e6a  jb      short loc_180004E7D
0x180004e6c  mov     rcx, [rcx+10h]
0x180004e70  mov     edx, 95h
0x180004e75  mov     r9d, eax
0x180004e78  call    WPP_SF_d
0x180004e7d  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180004e85  jz      short loc_180004ED4
0x180004e87  xor     eax, eax
0x180004e89  lea     rdx, aUnableToGetSha; "Unable to get SHA1Enabled flag - assumi"...
0x180004e90  mov     r8d, esi
0x180004e93  mov     word ptr [rsp+870h+var_820], ax
0x180004e98  lea     rcx, [rsp+870h+var_820]
0x180004e9d  call    FormatRRASErrorString
0x180004ea2  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180004ea9  lea     r8, [rsp+870h+var_820]
0x180004eae  mov     rcx, cs:gSstpCfgEtwContext
0x180004eb5  mov     rax, cs:gSstpCfgTemplateFunc
0x180004ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec1  jmp     short loc_180004ED4
0x180004ec3  cmp     [rsp+870h+Type], 4
0x180004ec8  jnz     short loc_180004ED4
0x180004eca  cmp     dword ptr [rsp+870h+Data], 0
0x180004ecf  jz      short loc_180004ED4
0x180004ed1  or      byte ptr [rdi], 1
0x180004ed4  mov     rcx, [rsp+870h+hKey]; hKey
0x180004ed9  call    cs:__imp_RegCloseKey
0x180004edf  mov     rcx, [rbp+770h+var_20]
0x180004ee6  xor     rcx, rsp; StackCookie
0x180004ee9  call    __security_check_cookie
0x180004eee  mov     rbx, [rsp+870h+arg_10]
0x180004ef6  add     rsp, 860h
0x180004efd  pop     rdi
0x180004efe  pop     rsi
0x180004eff  pop     rbp
0x180004f00  retn
```
