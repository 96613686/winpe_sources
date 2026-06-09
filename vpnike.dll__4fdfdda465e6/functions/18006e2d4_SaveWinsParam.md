# SaveWinsParam

- ea: `0x18006e2d4`
- end: `0x18006e6b7`
- name: `SaveWinsParam`
- size: `995`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006d494`

## callees

- `0x180020bdc`
- `0x18006cc54`
- `0x18006e2d4`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e3d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e689`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e689`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006e55e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006e55e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e52c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e608`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e52c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e608`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e463`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e463`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e3ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e3ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e679`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e679`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18006e483`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18006e483`

## string_xrefs

- `0x18006e4dc`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006e4eb`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006e4a8`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x18006e4b7`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x18006e54c`: `RegSetValueEx(%ws) failed: %d`
- `0x18006e555`: `RegSetValueEx(%ws) failed: %d`
- `0x18006e57a`: `RegDeleteValue(%ws) failed: %d`
- `0x18006e5b8`: `RegDeleteValue(%ws) failed: %d`
- `0x18006e629`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18006e667`: `RegSetValueEx(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall SaveWinsParam(HKEY hKey, __int64 a2)
{
  int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rax
  size_t v7; // rbx
  wchar_t *v8; // rdi
  DWORD LastError; // eax
  DWORD v10; // ebx
  unsigned int v11; // eax
  const WCHAR *v12; // r8
  const wchar_t *v13; // rdx
  const CHAR *v14; // rcx
  unsigned int v15; // eax
  const wchar_t *v16; // rdx
  const CHAR *v17; // rcx
  int *v18; // r8
  int v19; // eax
  const BYTE *v20; // r8
  HKEY hKeya; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+3Ch] [rbp-C4h] BYREF
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKeya = 0;
  *(_DWORD *)Data = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v4 = gIsIphlpEtwTracingAvailable;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( !*((_QWORD *)&xmmword_1800AB320 + 1) )
      goto LABEL_8;
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      *((_QWORD *)&xmmword_1800AB320 + 1),
      L"SaveWinsParam");
  }
  else
  {
    TraceHlp("SaveWinsParam");
  }
  v4 = gIsIphlpEtwTracingAvailable;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800AB320 + 1) )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800AB320 + 1),
        L"SaveWinsParam");
      goto LABEL_10;
    }
LABEL_8:
    if ( v4 )
      goto LABEL_10;
  }
  TraceHlp("SaveWinsParam");
LABEL_10:
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * v5) );
  v6 = (unsigned int)(v5 + 7);
  v7 = (unsigned int)v6;
  v8 = (wchar_t *)LocalAlloc(0x40u, 2 * v6);
  if ( !v8 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( !gIsIphlpEtwTracingAvailable )
    {
      TraceHlp("LocalAlloc failed and returned %d");
      goto LABEL_51;
    }
    if ( !(_QWORD)xmmword_1800AB320 )
      goto LABEL_51;
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"LocalAlloc failed and returned %d", LastError);
    goto LABEL_48;
  }
  StringCchPrintfW(v8, v7, L"%s%s", L"Tcpip_", *(_QWORD *)(a2 + 8));
  v11 = RegOpenKeyExW(hKey, v8, 0, 0x20006u, &hKeya);
  v10 = v11;
  if ( v11 )
  {
    if ( v11 != 2 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_51;
        v12 = v8;
        v13 = L"RegOpenKeyEx(%ws) failed and returned %d";
        goto LABEL_47;
      }
      v14 = "RegOpenKeyEx(%ws) failed and returned %d";
      goto LABEL_50;
    }
    v11 = RegCreateKeyW(hKey, v8, &hKeya);
    v10 = v11;
    if ( v11 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_51;
        v12 = v8;
        v13 = L"RegCreateKey(%ws) (v4) failed and returned %d";
LABEL_47:
        LOWORD(v25) = 0;
        FormatRRASErrorString(&v25, v13, v12, v11);
LABEL_48:
        ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB320, &v25);
        goto LABEL_51;
      }
      v14 = "RegCreateKey(%ws) (v4) failed and returned %d";
      goto LABEL_50;
    }
  }
  if ( *(_DWORD *)(a2 + 4) )
  {
    *(_DWORD *)Data = 2;
    v15 = RegSetValueExW(hKeya, L"NetbiosOptions", 0, 4u, Data, 4u);
    if ( !v15 )
      goto LABEL_41;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800AB320 )
        goto LABEL_41;
      v16 = L"RegSetValueEx(%ws) failed: %d";
LABEL_38:
      LOWORD(v25) = 0;
      FormatRRASErrorString(&v25, v16, L"NetbiosOptions", v15);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB320, &v25);
      goto LABEL_41;
    }
    v17 = "RegSetValueEx(%ws) failed: %d";
  }
  else
  {
    v15 = RegDeleteValueW(hKeya, L"NetbiosOptions");
    if ( !v15 )
      goto LABEL_41;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800AB320 )
        goto LABEL_41;
      v16 = L"RegDeleteValue(%ws) failed: %d";
      goto LABEL_38;
    }
    v17 = "RegDeleteValue(%ws) failed: %d";
  }
  TraceHlp(v17);
LABEL_41:
  v18 = *(int **)(a2 + 112);
  if ( !v18 )
  {
    v24 = 0;
    v18 = &v24;
  }
  v19 = MwszLength(v18);
  v11 = RegSetValueExW(hKeya, L"NameServerList", 0, 7u, v20, 2 * v19);
  v10 = v11;
  if ( v11 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800AB320 )
        goto LABEL_51;
      v12 = L"NameServerList";
      v13 = L"RegSetValueEx(%ws) failed and returned %d";
      goto LABEL_47;
    }
    v14 = "RegSetValueEx(%ws) failed and returned %d";
LABEL_50:
    TraceHlp(v14);
  }
LABEL_51:
  LocalFree(v8);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v10;
}

```

## disassembly

```asm
0x18006e2d4  mov     [rsp-8+arg_10], rbx
0x18006e2d9  push    rbp
0x18006e2da  push    rsi
0x18006e2db  push    rdi
0x18006e2dc  push    r14
0x18006e2de  push    r15
0x18006e2e0  lea     rbp, [rsp-750h]
0x18006e2e8  sub     rsp, 850h
0x18006e2ef  mov     rax, cs:__security_cookie
0x18006e2f6  xor     rax, rsp
0x18006e2f9  mov     [rbp+770h+var_30], rax
0x18006e300  xor     r15d, r15d
0x18006e303  mov     rsi, rdx
0x18006e306  mov     r14, rcx
0x18006e309  mov     [rsp+870h+hKey], r15
0x18006e30e  xor     edx, edx; Val
0x18006e310  mov     dword ptr [rsp+870h+Data], r15d
0x18006e315  lea     rcx, [rsp+870h+var_82C]; void *
0x18006e31a  mov     [rsp+870h+var_830], r15d
0x18006e31f  mov     r8d, 7FCh; Size
0x18006e325  call    memset_0
0x18006e32a  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006e330  test    eax, eax
0x18006e332  jz      short loc_18006E35C
0x18006e334  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006e33b  test    rdx, rdx
0x18006e33e  jz      short loc_18006E39A
0x18006e340  mov     rcx, cs:gIphlpEtwContext
0x18006e347  lea     r8, aSavewinsparam; "SaveWinsParam"
0x18006e34e  mov     rax, cs:gIphlpTemplateFunc
0x18006e355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e35a  jmp     short loc_18006E368
0x18006e35c  lea     rcx, aSavewinsparam_0; "SaveWinsParam"
0x18006e363  call    TraceHlp
0x18006e368  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006e36e  test    eax, eax
0x18006e370  jz      short loc_18006E39E
0x18006e372  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006e379  test    rdx, rdx
0x18006e37c  jz      short loc_18006E39A
0x18006e37e  mov     rcx, cs:gIphlpEtwContext
0x18006e385  lea     r8, aSavewinsparam; "SaveWinsParam"
0x18006e38c  mov     rax, cs:gIphlpTemplateFunc
0x18006e393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e398  jmp     short loc_18006E3AA
0x18006e39a  test    eax, eax
0x18006e39c  jnz     short loc_18006E3AA
0x18006e39e  lea     rcx, aSavewinsparam_0; "SaveWinsParam"
0x18006e3a5  call    TraceHlp
0x18006e3aa  mov     rcx, [rsi+8]
0x18006e3ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e3b2  inc     rax
0x18006e3b5  cmp     [rcx+rax*2], r15w
0x18006e3ba  jnz     short loc_18006E3B2
0x18006e3bc  add     eax, 7
0x18006e3bf  mov     ecx, 40h ; '@'; uFlags
0x18006e3c4  mov     ebx, eax
0x18006e3c6  lea     rdx, [rax+rax]; uBytes
0x18006e3ca  call    cs:__imp_LocalAlloc
0x18006e3d0  mov     rdi, rax
0x18006e3d3  test    rax, rax
0x18006e3d6  jnz     short loc_18006E428
0x18006e3d8  call    cs:__imp_GetLastError
0x18006e3de  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e3e5  mov     ebx, eax
0x18006e3e7  jz      short loc_18006E415
0x18006e3e9  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e3f0  jz      loc_18006E676
0x18006e3f6  mov     r8d, eax
0x18006e3f9  mov     word ptr [rsp+870h+var_830], r15w
0x18006e3ff  lea     rdx, aLocalallocFail_2; "LocalAlloc failed and returned %d"
0x18006e406  lea     rcx, [rsp+870h+var_830]
0x18006e40b  call    FormatRRASErrorString
0x18006e410  jmp     loc_18006E643
0x18006e415  mov     edx, eax
0x18006e417  lea     rcx, aLocalallocFail_0; "LocalAlloc failed and returned %d"
0x18006e41e  call    TraceHlp
0x18006e423  jmp     loc_18006E676
0x18006e428  mov     rax, [rsi+8]
0x18006e42c  lea     r9, aTcpip; "Tcpip_"
0x18006e433  lea     r8, aSS_0; "%s%s"
0x18006e43a  mov     [rsp+870h+phkResult], rax
0x18006e43f  mov     rdx, rbx; cchDest
0x18006e442  mov     rcx, rdi; pszDest
0x18006e445  call    StringCchPrintfW
0x18006e44a  lea     rax, [rsp+870h+hKey]
0x18006e44f  mov     r9d, 20006h; samDesired
0x18006e455  xor     r8d, r8d; ulOptions
0x18006e458  mov     [rsp+870h+phkResult], rax; phkResult
0x18006e45d  mov     rdx, rdi; lpSubKey
0x18006e460  mov     rcx, r14; hKey
0x18006e463  call    cs:__imp_RegOpenKeyExW
0x18006e469  mov     ebx, eax
0x18006e46b  test    eax, eax
0x18006e46d  jz      loc_18006E4F7
0x18006e473  cmp     eax, 2
0x18006e476  jnz     short loc_18006E4C3
0x18006e478  lea     r8, [rsp+870h+hKey]; phkResult
0x18006e47d  mov     rdx, rdi; lpSubKey
0x18006e480  mov     rcx, r14; hKey
0x18006e483  call    cs:__imp_RegCreateKeyW
0x18006e489  mov     ebx, eax
0x18006e48b  test    eax, eax
0x18006e48d  jz      short loc_18006E4F7
0x18006e48f  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e496  jz      short loc_18006E4B4
0x18006e498  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e49f  jz      loc_18006E676
0x18006e4a5  mov     r8, rdi
0x18006e4a8  lea     rdx, aRegcreatekeyWs_1; "RegCreateKey(%ws) (v4) failed and retur"...
0x18006e4af  jmp     loc_18006E630
0x18006e4b4  mov     rdx, rdi
0x18006e4b7  lea     rcx, aRegcreatekeyWs; "RegCreateKey(%ws) (v4) failed and retur"...
0x18006e4be  jmp     loc_18006E66E
0x18006e4c3  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e4ca  jz      short loc_18006E4E8
0x18006e4cc  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e4d3  jz      loc_18006E676
0x18006e4d9  mov     r8, rdi
0x18006e4dc  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006e4e3  jmp     loc_18006E630
0x18006e4e8  mov     rdx, rdi
0x18006e4eb  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006e4f2  jmp     loc_18006E66E
0x18006e4f7  lea     rbx, aNetbiosoptions; "NetbiosOptions"
0x18006e4fe  mov     rcx, [rsp+870h+hKey]; hKey
0x18006e503  mov     rdx, rbx; lpValueName
0x18006e506  cmp     [rsi+4], r15d
0x18006e50a  jz      short loc_18006E55E
0x18006e50c  mov     r9d, 4; dwType
0x18006e512  mov     dword ptr [rsp+870h+Data], 2
0x18006e51a  lea     rax, [rsp+870h+Data]
0x18006e51f  mov     [rsp+870h+cbData], r9d; cbData
0x18006e524  xor     r8d, r8d; Reserved
0x18006e527  mov     [rsp+870h+phkResult], rax; lpData
0x18006e52c  call    cs:__imp_RegSetValueExW
0x18006e532  test    eax, eax
0x18006e534  jz      loc_18006E5CA
0x18006e53a  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e541  jz      short loc_18006E555
0x18006e543  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e54a  jz      short loc_18006E5CA
0x18006e54c  lea     rdx, aRegsetvalueexW_2; "RegSetValueEx(%ws) failed: %d"
0x18006e553  jmp     short loc_18006E581
0x18006e555  lea     rcx, aRegsetvalueexW_1; "RegSetValueEx(%ws) failed: %d"
0x18006e55c  jmp     short loc_18006E5BF
0x18006e55e  call    cs:__imp_RegDeleteValueW
0x18006e564  test    eax, eax
0x18006e566  jz      short loc_18006E5CA
0x18006e568  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e56f  jz      short loc_18006E5B8
0x18006e571  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e578  jz      short loc_18006E5CA
0x18006e57a  lea     rdx, aRegdeletevalue_1; "RegDeleteValue(%ws) failed: %d"
0x18006e581  mov     r8, rbx
0x18006e584  mov     word ptr [rsp+870h+var_830], r15w
0x18006e58a  mov     r9d, eax
0x18006e58d  lea     rcx, [rsp+870h+var_830]
0x18006e592  call    FormatRRASErrorString
0x18006e597  mov     rdx, qword ptr cs:unk_1800AB320
0x18006e59e  lea     r8, [rsp+870h+var_830]
0x18006e5a3  mov     rcx, cs:gIphlpEtwContext
0x18006e5aa  mov     rax, cs:gIphlpTemplateFunc
0x18006e5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5b6  jmp     short loc_18006E5CA
0x18006e5b8  lea     rcx, aRegdeletevalue_0; "RegDeleteValue(%ws) failed: %d"
0x18006e5bf  mov     r8d, eax
0x18006e5c2  mov     rdx, rbx
0x18006e5c5  call    TraceHlp
0x18006e5ca  mov     r8, [rsi+70h]
0x18006e5ce  test    r8, r8
0x18006e5d1  jnz     short loc_18006E5DD
0x18006e5d3  mov     [rsp+870h+var_834], r15d
0x18006e5d8  lea     r8, [rsp+870h+var_834]
0x18006e5dd  mov     rcx, r8
0x18006e5e0  call    MwszLength
0x18006e5e5  mov     rcx, [rsp+870h+hKey]; hKey
0x18006e5ea  lea     rsi, aNameserverlist; "NameServerList"
0x18006e5f1  add     eax, eax
0x18006e5f3  mov     r9d, 7; dwType
0x18006e5f9  mov     [rsp+870h+cbData], eax; cbData
0x18006e5fd  mov     rdx, rsi; lpValueName
0x18006e600  mov     [rsp+870h+phkResult], r8; lpData
0x18006e605  xor     r8d, r8d; Reserved
0x18006e608  call    cs:__imp_RegSetValueExW
0x18006e60e  mov     ebx, eax
0x18006e610  test    eax, eax
0x18006e612  jz      short loc_18006E676
0x18006e614  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006e61b  jz      short loc_18006E664
0x18006e61d  cmp     qword ptr cs:unk_1800AB320, r15
0x18006e624  jz      short loc_18006E676
0x18006e626  mov     r8, rsi
0x18006e629  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18006e630  mov     r9d, eax
0x18006e633  mov     word ptr [rsp+870h+var_830], r15w
0x18006e639  lea     rcx, [rsp+870h+var_830]
0x18006e63e  call    FormatRRASErrorString
0x18006e643  mov     rdx, qword ptr cs:unk_1800AB320
0x18006e64a  lea     r8, [rsp+870h+var_830]
0x18006e64f  mov     rcx, cs:gIphlpEtwContext
0x18006e656  mov     rax, cs:gIphlpTemplateFunc
0x18006e65d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e662  jmp     short loc_18006E676
0x18006e664  mov     rdx, rsi
0x18006e667  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18006e66e  mov     r8d, eax
0x18006e671  call    TraceHlp
0x18006e676  mov     rcx, rdi; hMem
0x18006e679  call    cs:__imp_LocalFree
0x18006e67f  mov     rcx, [rsp+870h+hKey]; hKey
0x18006e684  test    rcx, rcx
0x18006e687  jz      short loc_18006E68F
0x18006e689  call    cs:__imp_RegCloseKey
0x18006e68f  mov     eax, ebx
0x18006e691  mov     rcx, [rbp+770h+var_30]
0x18006e698  xor     rcx, rsp; StackCookie
0x18006e69b  call    __security_check_cookie
0x18006e6a0  mov     rbx, [rsp+870h+arg_10]
0x18006e6a8  add     rsp, 850h
0x18006e6af  pop     r15
0x18006e6b1  pop     r14
0x18006e6b3  pop     rdi
0x18006e6b4  pop     rsi
0x18006e6b5  pop     rbp
0x18006e6b6  retn
```
