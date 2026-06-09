# LoadTcpipInfo

- ea: `0x18006c42c`
- end: `0x18006c734`
- name: `LoadTcpipInfo`
- size: `776`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18004971c`
- `0x18004baa8`
- `0x18004c488`

## callees

- `0x180020ba4`
- `0x18006bc18`
- `0x18006c42c`
- `0x18006c73c`
- `0x18006ca24`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c535`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c6e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c6f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c6e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c6f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c625`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c6b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c625`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c6b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c527`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c5bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c527`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c5bf`

## string_xrefs

- `0x18006c658`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006c671`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006c606`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18006c69d`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall LoadTcpipInfo(__int64 *a1, const wchar_t *a2, int a3)
{
  unsigned int TcpipParam; // ebx
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  HLOCAL v9; // rax
  DWORD LastError; // eax
  __int64 v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rbx
  wchar_t *v14; // rcx
  const WCHAR *v15; // rdi
  unsigned int v16; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  phkResult = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800AB328 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        xmmword_1800AB328,
        L"LoadTcpipInfo");
  }
  else
  {
    TraceHlp("LoadTcpipInfo");
  }
  if ( a2 )
  {
    *a1 = 0;
    v9 = LocalAlloc(0x40u, 0x80u);
    *a1 = (__int64)v9;
    if ( !v9 )
      goto LABEL_12;
    memset_0(v9, 0, 0x80u);
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v13 = *a1;
    *(_QWORD *)(v13 + 8) = LocalAlloc(0x40u, 2 * v12 + 2);
    v14 = *(wchar_t **)(*a1 + 8);
    if ( !v14 )
    {
LABEL_12:
      LastError = GetLastError();
      TcpipParam = LastError;
      if ( !gIsIphlpEtwTracingAvailable )
      {
        TraceHlp("LocalAlloc failed and returned %d");
        goto LABEL_34;
      }
      if ( !unk_1800AB320 )
        goto LABEL_34;
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"LocalAlloc failed and returned %d", LastError);
      goto LABEL_15;
    }
    TcpipParam = 0;
    do
      ++v11;
    while ( a2[v11] );
    StringCchCopyW(v14, v11 + 1, a2);
    if ( a3 )
      goto LABEL_34;
    v15 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
    v16 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
            0,
            0x20019u,
            &hKey);
    TcpipParam = v16;
    if ( v16 )
    {
      if ( v16 != 2 )
      {
LABEL_25:
        if ( !gIsIphlpEtwTracingAvailable )
        {
          TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
          goto LABEL_34;
        }
        if ( !unk_1800AB320 )
          goto LABEL_34;
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RegOpenKeyEx(%ws) failed and returned %d", v15, v16);
LABEL_15:
        v7 = unk_1800AB320;
        v8 = (const wchar_t *)&v20;
LABEL_9:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(gIphlpEtwContext, v7, v8);
        goto LABEL_34;
      }
    }
    else
    {
      TcpipParam = LoadTcpipParam(hKey);
      if ( TcpipParam )
        goto LABEL_34;
    }
    v15 = L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces";
    v16 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces",
            0,
            0x20019u,
            &phkResult);
    TcpipParam = v16;
    if ( !v16 )
    {
      TcpipParam = LoadWinsParam(phkResult);
      goto LABEL_34;
    }
    if ( v16 == 2 )
    {
      TcpipParam = 0;
      goto LABEL_34;
    }
    goto LABEL_25;
  }
  TcpipParam = 87;
  if ( gIsIphlpEtwTracingAvailable )
  {
    v7 = unk_1800AB320;
    if ( !unk_1800AB320 )
      goto LABEL_34;
    v8 = L"wszAdapterName is NULL";
    goto LABEL_9;
  }
  TraceHlp("wszAdapterName is NULL");
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( TcpipParam )
    FreeTcpipInfo(a1);
  return TcpipParam;
}

```

## disassembly

```asm
0x18006c42c  mov     [rsp-8+arg_10], rbx
0x18006c431  mov     [rsp-8+arg_18], rsi
0x18006c436  push    rbp
0x18006c437  push    rdi
0x18006c438  push    r12
0x18006c43a  push    r14
0x18006c43c  push    r15
0x18006c43e  lea     rbp, [rsp-750h]
0x18006c446  sub     rsp, 850h
0x18006c44d  mov     rax, cs:__security_cookie
0x18006c454  xor     rax, rsp
0x18006c457  mov     [rbp+770h+var_30], rax
0x18006c45e  xor     r12d, r12d
0x18006c461  mov     r15d, r8d
0x18006c464  mov     r14, rdx
0x18006c467  mov     [rsp+870h+hKey], r12
0x18006c46c  mov     rsi, rcx
0x18006c46f  mov     [rsp+870h+var_838], r12
0x18006c474  xor     edx, edx; Val
0x18006c476  mov     [rsp+870h+var_830], r12d
0x18006c47b  mov     r8d, 7FCh; Size
0x18006c481  lea     rcx, [rsp+870h+var_82C]; void *
0x18006c486  call    memset_0
0x18006c48b  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006c492  jz      short loc_18006C4BC
0x18006c494  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006c49b  test    rdx, rdx
0x18006c49e  jz      short loc_18006C4C8
0x18006c4a0  mov     rcx, cs:gIphlpEtwContext
0x18006c4a7  lea     r8, aLoadtcpipinfo; "LoadTcpipInfo"
0x18006c4ae  mov     rax, cs:gIphlpTemplateFunc
0x18006c4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c4ba  jmp     short loc_18006C4C8
0x18006c4bc  lea     rcx, aLoadtcpipinfo_0; "LoadTcpipInfo"
0x18006c4c3  call    TraceHlp
0x18006c4c8  test    r14, r14
0x18006c4cb  jnz     short loc_18006C51A
0x18006c4cd  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006c4d4  lea     ebx, [r14+57h]
0x18006c4d8  jz      short loc_18006C509
0x18006c4da  mov     rdx, qword ptr cs:unk_1800AB320
0x18006c4e1  test    rdx, rdx
0x18006c4e4  jz      loc_18006C6DB
0x18006c4ea  lea     r8, aWszadaptername; "wszAdapterName is NULL"
0x18006c4f1  mov     rcx, cs:gIphlpEtwContext
0x18006c4f8  mov     rax, cs:gIphlpTemplateFunc
0x18006c4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c504  jmp     loc_18006C6DB
0x18006c509  lea     rcx, aWszadaptername_0; "wszAdapterName is NULL"
0x18006c510  call    TraceHlp
0x18006c515  jmp     loc_18006C6DB
0x18006c51a  mov     ebx, 80h
0x18006c51f  mov     [rsi], r12
0x18006c522  mov     edx, ebx; uBytes
0x18006c524  lea     ecx, [rbx-40h]; uFlags
0x18006c527  call    cs:__imp_LocalAlloc
0x18006c52d  mov     [rsi], rax
0x18006c530  test    rax, rax
0x18006c533  jnz     short loc_18006C591
0x18006c535  call    cs:__imp_GetLastError
0x18006c53b  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006c542  mov     ebx, eax
0x18006c544  jz      short loc_18006C57E
0x18006c546  cmp     qword ptr cs:unk_1800AB320, r12
0x18006c54d  jz      loc_18006C6DB
0x18006c553  mov     r8d, eax
0x18006c556  mov     word ptr [rsp+870h+var_830], r12w
0x18006c55c  lea     rdx, aLocalallocFail_2; "LocalAlloc failed and returned %d"
0x18006c563  lea     rcx, [rsp+870h+var_830]
0x18006c568  call    FormatRRASErrorString
0x18006c56d  mov     rdx, qword ptr cs:unk_1800AB320
0x18006c574  lea     r8, [rsp+870h+var_830]
0x18006c579  jmp     loc_18006C4F1
0x18006c57e  mov     edx, eax
0x18006c580  lea     rcx, aLocalallocFail_0; "LocalAlloc failed and returned %d"
0x18006c587  call    TraceHlp
0x18006c58c  jmp     loc_18006C6DB
0x18006c591  mov     r8, rbx; Size
0x18006c594  xor     edx, edx; Val
0x18006c596  mov     rcx, rax; void *
0x18006c599  call    memset_0
0x18006c59e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006c5a2  mov     rdx, rdi
0x18006c5a5  inc     rdx
0x18006c5a8  cmp     [r14+rdx*2], r12w
0x18006c5ad  jnz     short loc_18006C5A5
0x18006c5af  mov     rbx, [rsi]
0x18006c5b2  lea     rdx, ds:2[rdx*2]; uBytes
0x18006c5ba  mov     ecx, 40h ; '@'; uFlags
0x18006c5bf  call    cs:__imp_LocalAlloc
0x18006c5c5  mov     [rbx+8], rax
0x18006c5c9  mov     rax, [rsi]
0x18006c5cc  mov     rcx, [rax+8]; pszDest
0x18006c5d0  test    rcx, rcx
0x18006c5d3  jz      loc_18006C535
0x18006c5d9  mov     ebx, r12d
0x18006c5dc  inc     rdi
0x18006c5df  cmp     [r14+rdi*2], r12w
0x18006c5e4  jnz     short loc_18006C5DC
0x18006c5e6  lea     rdx, [rdi+1]; cchDest
0x18006c5ea  mov     r8, r14; pszSrc
0x18006c5ed  call    StringCchCopyW
0x18006c5f2  test    r15d, r15d
0x18006c5f5  jnz     loc_18006C6DB
0x18006c5fb  lea     rax, [rsp+870h+hKey]
0x18006c600  mov     r14d, 20019h
0x18006c606  lea     rdi, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x18006c60d  mov     [rsp+870h+phkResult], rax; phkResult
0x18006c612  mov     r15, 0FFFFFFFF80000002h
0x18006c619  mov     r9d, r14d; samDesired
0x18006c61c  mov     rdx, rdi; lpSubKey
0x18006c61f  mov     rcx, r15; hKey
0x18006c622  xor     r8d, r8d; ulOptions
0x18006c625  call    cs:__imp_RegOpenKeyExW
0x18006c62b  mov     ebx, eax
0x18006c62d  test    eax, eax
0x18006c62f  jz      short loc_18006C682
0x18006c631  cmp     eax, 2
0x18006c634  jz      short loc_18006C695
0x18006c636  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006c63d  jz      short loc_18006C66E
0x18006c63f  cmp     qword ptr cs:unk_1800AB320, r12
0x18006c646  jz      loc_18006C6DB
0x18006c64c  mov     r9d, eax
0x18006c64f  mov     word ptr [rsp+870h+var_830], r12w
0x18006c655  mov     r8, rdi
0x18006c658  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006c65f  lea     rcx, [rsp+870h+var_830]
0x18006c664  call    FormatRRASErrorString
0x18006c669  jmp     loc_18006C56D
0x18006c66e  mov     r8d, eax
0x18006c671  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006c678  mov     rdx, rdi
0x18006c67b  call    TraceHlp
0x18006c680  jmp     short loc_18006C6DB
0x18006c682  mov     rdx, [rsi]
0x18006c685  mov     rcx, [rsp+870h+hKey]; hKey
0x18006c68a  call    LoadTcpipParam
0x18006c68f  mov     ebx, eax
0x18006c691  test    eax, eax
0x18006c693  jnz     short loc_18006C6DB
0x18006c695  lea     rax, [rsp+870h+var_838]
0x18006c69a  mov     r9d, r14d; samDesired
0x18006c69d  lea     rdi, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Ne"...
0x18006c6a4  mov     [rsp+870h+phkResult], rax; phkResult
0x18006c6a9  mov     rdx, rdi; lpSubKey
0x18006c6ac  xor     r8d, r8d; ulOptions
0x18006c6af  mov     rcx, r15; hKey
0x18006c6b2  call    cs:__imp_RegOpenKeyExW
0x18006c6b8  mov     ebx, eax
0x18006c6ba  test    eax, eax
0x18006c6bc  jz      short loc_18006C6CC
0x18006c6be  cmp     eax, 2
0x18006c6c1  jnz     loc_18006C636
0x18006c6c7  mov     ebx, r12d
0x18006c6ca  jmp     short loc_18006C6DB
0x18006c6cc  mov     rdx, [rsi]
0x18006c6cf  mov     rcx, [rsp+870h+var_838]; hKey
0x18006c6d4  call    LoadWinsParam
0x18006c6d9  mov     ebx, eax
0x18006c6db  mov     rcx, [rsp+870h+hKey]; hKey
0x18006c6e0  test    rcx, rcx
0x18006c6e3  jz      short loc_18006C6EB
0x18006c6e5  call    cs:__imp_RegCloseKey
0x18006c6eb  mov     rcx, [rsp+870h+var_838]; hKey
0x18006c6f0  test    rcx, rcx
0x18006c6f3  jz      short loc_18006C6FB
0x18006c6f5  call    cs:__imp_RegCloseKey
0x18006c6fb  test    ebx, ebx
0x18006c6fd  jz      short loc_18006C707
0x18006c6ff  mov     rcx, rsi
0x18006c702  call    FreeTcpipInfo
0x18006c707  mov     eax, ebx
0x18006c709  mov     rcx, [rbp+770h+var_30]
0x18006c710  xor     rcx, rsp; StackCookie
0x18006c713  call    __security_check_cookie
0x18006c718  lea     r11, [rsp+870h+var_20]
0x18006c720  mov     rbx, [r11+40h]
0x18006c724  mov     rsi, [r11+48h]
0x18006c728  mov     rsp, r11
0x18006c72b  pop     r15
0x18006c72d  pop     r14
0x18006c72f  pop     r12
0x18006c731  pop     rdi
0x18006c732  pop     rbp
0x18006c733  retn
```
