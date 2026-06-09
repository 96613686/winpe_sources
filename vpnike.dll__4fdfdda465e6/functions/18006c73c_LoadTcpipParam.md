# LoadTcpipParam

- ea: `0x18006c73c`
- end: `0x18006ca1e`
- name: `LoadTcpipParam`
- size: `738`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18006c42c`

## callees

- `0x18006c73c`
- `0x18006d288`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `msvcrt!_wcslwr` at `0x18006c7eb`
- `msvcrt!_wcslwr` at `0x18006c7eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c9b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c9c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c9b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c9c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006c918`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006c959`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006c918`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006c959`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c814`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c8a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c814`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c8a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c9d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c9e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c9d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c9e7`

## string_xrefs

- `0x18006c844`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006c87f`: `RegOpenKeyEx(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall LoadTcpipParam(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  const WCHAR *v7; // r8
  _WORD *v8; // rsi
  void *v9; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v16[2044]; // [rsp+54h] [rbp-ACh] BYREF

  hKeya = 0;
  phkResult = 0;
  Type = 0;
  v15 = 0;
  cbData = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800AB328 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        xmmword_1800AB328,
        L"LoadTcpipParam");
  }
  else
  {
    TraceHlp("LoadTcpipParam");
  }
  _wcslwr(*(wchar_t **)(a2 + 8));
  v4 = RegOpenKeyExW(hKey, L"Interfaces", 0, 0x20019u, &hKeya);
  v5 = v4;
  if ( v4 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !unk_1800AB320 )
        goto LABEL_23;
      v6 = v4;
      LOWORD(v15) = 0;
      v7 = L"Interfaces";
      goto LABEL_9;
    }
    goto LABEL_10;
  }
  v5 = RegOpenKeyExW(hKeya, *(LPCWSTR *)(a2 + 8), 0, 0x20019u, &phkResult);
  if ( v5 )
  {
    if ( !gIsIphlpEtwTracingAvailable )
    {
LABEL_10:
      TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
      goto LABEL_23;
    }
    if ( unk_1800AB320 )
    {
      v7 = *(const WCHAR **)(a2 + 8);
      LOWORD(v15) = 0;
      v6 = v5;
LABEL_9:
      FormatRRASErrorString(&v15, L"RegOpenKeyEx(%ws) failed and returned %d", v7, v6);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, unk_1800AB320, &v15);
    }
  }
  else
  {
    v8 = (_WORD *)(a2 + 16);
    cbData = 42;
    if ( RegQueryValueExW(phkResult, L"DhcpIPAddress", 0, &Type, (LPBYTE)(a2 + 16), &cbData) || Type != 1 )
      *v8 = 0;
    cbData = 42;
    v5 = RegQueryValueExW(phkResult, L"DhcpSubnetMask", 0, &Type, (LPBYTE)(a2 + 58), &cbData);
    if ( v5 || Type != 1 )
    {
      v5 = 0;
      *(_WORD *)(a2 + 58) = 0;
      *v8 = 0;
    }
    RegQueryValueWithAllocW(phkResult, L"Domain");
    RegQueryValueWithAllocW(phkResult, L"NameServer");
  }
LABEL_23:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
  {
    LocalFree(*(HLOCAL *)(a2 + 120));
    v9 = *(void **)(a2 + 104);
    *(_QWORD *)(a2 + 120) = 0;
    LocalFree(v9);
    *(_QWORD *)(a2 + 104) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18006c73c  mov     [rsp-8+arg_10], rbx
0x18006c741  mov     [rsp-8+arg_18], rsi
0x18006c746  push    rbp
0x18006c747  push    rdi
0x18006c748  push    r14
0x18006c74a  lea     rbp, [rsp-760h]
0x18006c752  sub     rsp, 860h
0x18006c759  mov     rax, cs:__security_cookie
0x18006c760  xor     rax, rsp
0x18006c763  mov     [rbp+770h+var_20], rax
0x18006c76a  mov     rdi, rdx
0x18006c76d  mov     [rsp+870h+hKey], 0
0x18006c776  mov     rbx, rcx
0x18006c779  mov     [rsp+870h+var_838], 0
0x18006c782  xor     eax, eax
0x18006c784  mov     [rsp+870h+Type], 0
0x18006c78c  xor     edx, edx; Val
0x18006c78e  mov     [rsp+870h+var_820], eax
0x18006c792  lea     rcx, [rsp+870h+var_81C]; void *
0x18006c797  mov     [rsp+870h+cbData], 0
0x18006c79f  mov     r8d, 7FCh; Size
0x18006c7a5  call    memset_0
0x18006c7aa  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006c7b1  jz      short loc_18006C7DB
0x18006c7b3  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006c7ba  test    rdx, rdx
0x18006c7bd  jz      short loc_18006C7E7
0x18006c7bf  mov     rcx, cs:gIphlpEtwContext
0x18006c7c6  lea     r8, aLoadtcpipparam; "LoadTcpipParam"
0x18006c7cd  mov     rax, cs:gIphlpTemplateFunc
0x18006c7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7d9  jmp     short loc_18006C7E7
0x18006c7db  lea     rcx, aLoadtcpipparam_0; "LoadTcpipParam"
0x18006c7e2  call    TraceHlp
0x18006c7e7  mov     rcx, [rdi+8]; String
0x18006c7eb  call    cs:__imp__wcslwr
0x18006c7f1  lea     rax, [rsp+870h+hKey]
0x18006c7f6  mov     r14d, 20019h
0x18006c7fc  lea     rsi, aInterfaces; "Interfaces"
0x18006c803  mov     [rsp+870h+phkResult], rax; phkResult
0x18006c808  mov     r9d, r14d; samDesired
0x18006c80b  mov     rdx, rsi; lpSubKey
0x18006c80e  xor     r8d, r8d; ulOptions
0x18006c811  mov     rcx, rbx; hKey
0x18006c814  call    cs:__imp_RegOpenKeyExW
0x18006c81a  mov     ebx, eax
0x18006c81c  test    eax, eax
0x18006c81e  jz      short loc_18006C890
0x18006c820  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006c827  jz      short loc_18006C879
0x18006c829  cmp     qword ptr cs:unk_1800AB320, 0
0x18006c831  jz      loc_18006C9AD
0x18006c837  xor     ecx, ecx
0x18006c839  mov     r9d, eax
0x18006c83c  mov     word ptr [rsp+870h+var_820], cx
0x18006c841  mov     r8, rsi
0x18006c844  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006c84b  lea     rcx, [rsp+870h+var_820]
0x18006c850  call    FormatRRASErrorString
0x18006c855  mov     rdx, qword ptr cs:unk_1800AB320
0x18006c85c  lea     r8, [rsp+870h+var_820]
0x18006c861  mov     rcx, cs:gIphlpEtwContext
0x18006c868  mov     rax, cs:gIphlpTemplateFunc
0x18006c86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c874  jmp     loc_18006C9AD
0x18006c879  mov     r8d, eax
0x18006c87c  mov     rdx, rsi
0x18006c87f  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006c886  call    TraceHlp
0x18006c88b  jmp     loc_18006C9AD
0x18006c890  mov     rdx, [rdi+8]; lpSubKey
0x18006c894  lea     rax, [rsp+870h+var_838]
0x18006c899  mov     rcx, [rsp+870h+hKey]; hKey
0x18006c89e  mov     r9d, r14d; samDesired
0x18006c8a1  xor     r8d, r8d; ulOptions
0x18006c8a4  mov     [rsp+870h+phkResult], rax; phkResult
0x18006c8a9  call    cs:__imp_RegOpenKeyExW
0x18006c8af  mov     ebx, eax
0x18006c8b1  test    eax, eax
0x18006c8b3  jz      short loc_18006C8E8
0x18006c8b5  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006c8bc  jz      short loc_18006C8DF
0x18006c8be  cmp     qword ptr cs:unk_1800AB320, 0
0x18006c8c6  jz      loc_18006C9AD
0x18006c8cc  mov     r8, [rdi+8]
0x18006c8d0  xor     eax, eax
0x18006c8d2  mov     word ptr [rsp+870h+var_820], ax
0x18006c8d7  mov     r9d, ebx
0x18006c8da  jmp     loc_18006C844
0x18006c8df  mov     rdx, [rdi+8]
0x18006c8e3  mov     r8d, ebx
0x18006c8e6  jmp     short loc_18006C87F
0x18006c8e8  mov     rcx, [rsp+870h+var_838]; hKey
0x18006c8ed  lea     rax, [rsp+870h+cbData]
0x18006c8f2  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18006c8f7  lea     rsi, [rdi+10h]
0x18006c8fb  mov     ebx, 2Ah ; '*'
0x18006c900  mov     [rsp+870h+phkResult], rsi; lpData
0x18006c905  lea     r9, [rsp+870h+Type]; lpType
0x18006c90a  mov     [rsp+870h+cbData], ebx
0x18006c90e  xor     r8d, r8d; lpReserved
0x18006c911  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x18006c918  call    cs:__imp_RegQueryValueExW
0x18006c91e  test    eax, eax
0x18006c920  jnz     short loc_18006C929
0x18006c922  cmp     [rsp+870h+Type], 1
0x18006c927  jz      short loc_18006C92E
0x18006c929  xor     eax, eax
0x18006c92b  mov     [rsi], ax
0x18006c92e  mov     rcx, [rsp+870h+var_838]; hKey
0x18006c933  lea     rax, [rsp+870h+cbData]
0x18006c938  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18006c93d  lea     r14, [rdi+3Ah]
0x18006c941  lea     r9, [rsp+870h+Type]; lpType
0x18006c946  mov     [rsp+870h+phkResult], r14; lpData
0x18006c94b  xor     r8d, r8d; lpReserved
0x18006c94e  mov     [rsp+870h+cbData], ebx
0x18006c952  lea     rdx, aDhcpsubnetmask; "DhcpSubnetMask"
0x18006c959  call    cs:__imp_RegQueryValueExW
0x18006c95f  mov     ebx, eax
0x18006c961  test    eax, eax
0x18006c963  jnz     short loc_18006C96C
0x18006c965  cmp     [rsp+870h+Type], 1
0x18006c96a  jz      short loc_18006C977
0x18006c96c  xor     ebx, ebx
0x18006c96e  xor     eax, eax
0x18006c970  mov     [r14], ax
0x18006c974  mov     [rsi], ax
0x18006c977  mov     rcx, [rsp+870h+var_838]; hKey
0x18006c97c  lea     r9, [rdi+78h]
0x18006c980  mov     r8d, 1
0x18006c986  lea     rdx, aDomain; "Domain"
0x18006c98d  call    RegQueryValueWithAllocW
0x18006c992  mov     rcx, [rsp+870h+var_838]; hKey
0x18006c997  lea     r9, [rdi+68h]
0x18006c99b  mov     r8d, 1
0x18006c9a1  lea     rdx, aNameserver; "NameServer"
0x18006c9a8  call    RegQueryValueWithAllocW
0x18006c9ad  mov     rcx, [rsp+870h+hKey]; hKey
0x18006c9b2  test    rcx, rcx
0x18006c9b5  jz      short loc_18006C9BD
0x18006c9b7  call    cs:__imp_RegCloseKey
0x18006c9bd  mov     rcx, [rsp+870h+var_838]; hKey
0x18006c9c2  test    rcx, rcx
0x18006c9c5  jz      short loc_18006C9CD
0x18006c9c7  call    cs:__imp_RegCloseKey
0x18006c9cd  test    ebx, ebx
0x18006c9cf  jz      short loc_18006C9F5
0x18006c9d1  mov     rcx, [rdi+78h]; hMem
0x18006c9d5  call    cs:__imp_LocalFree
0x18006c9db  mov     rcx, [rdi+68h]; hMem
0x18006c9df  mov     qword ptr [rdi+78h], 0
0x18006c9e7  call    cs:__imp_LocalFree
0x18006c9ed  mov     qword ptr [rdi+68h], 0
0x18006c9f5  mov     eax, ebx
0x18006c9f7  mov     rcx, [rbp+770h+var_20]
0x18006c9fe  xor     rcx, rsp; StackCookie
0x18006ca01  call    __security_check_cookie
0x18006ca06  lea     r11, [rsp+870h+var_10]
0x18006ca0e  mov     rbx, [r11+30h]
0x18006ca12  mov     rsi, [r11+38h]
0x18006ca16  mov     rsp, r11
0x18006ca19  pop     r14
0x18006ca1b  pop     rdi
0x18006ca1c  pop     rbp
0x18006ca1d  retn
```
