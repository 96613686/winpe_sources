# HttpParseNetworkOptions(ushort *,char *,char * *,char * *,int,char * *,char * *,tagRPCProxyAccessType *,ulong *)

- ea: `0x18001cb10`
- end: `0x18001d1cf`
- name: `?HttpParseNetworkOptions@@YAHPEAGPEADPEAPEAD2H22PEAW4tagRPCProxyAccessType@@PEAK@Z`
- size: `1727`
- prototype: `__int64 __fastcall(unsigned __int16 *, char *, char **, char **, int, char **, char **, enum tagRPCProxyAccessType *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c1a0`

## callees

- `0x180019928`
- `0x180019954`
- `0x18001caa0`
- `0x18001cac0`
- `0x18001cb10`
- `0x18001d7a8`
- `0x18001deb0`
- `0x18001e440`
- `0x18001e524`
- `0x18002461d`
- `0x180024640`

## import_xrefs

- `ntdll!_stricmp` at `0x18001d04c`
- `ntdll!_stricmp` at `0x18001d04c`
- `KERNEL32!GetLastError` at `0x18001cce8`
- `KERNEL32!GetLastError` at `0x18001ce7c`
- `KERNEL32!GetLastError` at `0x18001ced6`
- `KERNEL32!GetLastError` at `0x18001cce8`
- `KERNEL32!GetLastError` at `0x18001ce7c`
- `KERNEL32!GetLastError` at `0x18001ced6`
- `KERNEL32!GlobalFree` at `0x18001d10f`
- `KERNEL32!GlobalFree` at `0x18001d11f`
- `KERNEL32!GlobalFree` at `0x18001d12f`
- `KERNEL32!GlobalFree` at `0x18001d171`
- `KERNEL32!GlobalFree` at `0x18001d181`
- `KERNEL32!GlobalFree` at `0x18001d191`
- `KERNEL32!GlobalFree` at `0x18001d10f`
- `KERNEL32!GlobalFree` at `0x18001d11f`
- `KERNEL32!GlobalFree` at `0x18001d12f`
- `KERNEL32!GlobalFree` at `0x18001d171`
- `KERNEL32!GlobalFree` at `0x18001d181`
- `KERNEL32!GlobalFree` at `0x18001d191`
- `RPCRT4!I_RpcFree` at `0x18001cec7`
- `RPCRT4!I_RpcFree` at `0x18001ced0`
- `RPCRT4!I_RpcFree` at `0x18001cfb2`
- `RPCRT4!I_RpcFree` at `0x18001d0b9`
- `RPCRT4!I_RpcFree` at `0x18001d0d2`
- `RPCRT4!I_RpcFree` at `0x18001d0e9`
- `RPCRT4!I_RpcFree` at `0x18001d0fb`
- `RPCRT4!I_RpcFree` at `0x18001d13d`
- `RPCRT4!I_RpcFree` at `0x18001d14b`
- `RPCRT4!I_RpcFree` at `0x18001cec7`
- `RPCRT4!I_RpcFree` at `0x18001ced0`
- `RPCRT4!I_RpcFree` at `0x18001cfb2`
- `RPCRT4!I_RpcFree` at `0x18001d0b9`
- `RPCRT4!I_RpcFree` at `0x18001d0d2`
- `RPCRT4!I_RpcFree` at `0x18001d0e9`
- `RPCRT4!I_RpcFree` at `0x18001d0fb`
- `RPCRT4!I_RpcFree` at `0x18001d13d`
- `RPCRT4!I_RpcFree` at `0x18001d14b`
- `RPCRT4!I_RpcAllocate` at `0x18001cdab`
- `RPCRT4!I_RpcAllocate` at `0x18001cdca`
- `RPCRT4!I_RpcAllocate` at `0x18001cf3e`
- `RPCRT4!I_RpcAllocate` at `0x18001cdab`
- `RPCRT4!I_RpcAllocate` at `0x18001cdca`
- `RPCRT4!I_RpcAllocate` at `0x18001cf3e`
- `RPCRT4!I_RpcLogEvent` at `0x18001cccd`
- `RPCRT4!I_RpcLogEvent` at `0x18001cea7`
- `RPCRT4!I_RpcLogEvent` at `0x18001cccd`
- `RPCRT4!I_RpcLogEvent` at `0x18001cea7`
- `WINHTTP!WinHttpOpen` at `0x18001ce6b`
- `WINHTTP!WinHttpOpen` at `0x18001ce6b`
- `WINHTTP!WinHttpCloseHandle` at `0x18001cee3`
- `WINHTTP!WinHttpCloseHandle` at `0x18001cee3`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18001ccd8`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18001ccd8`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18001cebc`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18001cebc`

## pseudocode

```c
__int64 __fastcall HttpParseNetworkOptions(
        unsigned __int16 *a1,
        char *a2,
        char **a3,
        char **a4,
        int a5,
        char **a6,
        char **a7,
        enum tagRPCProxyAccessType *a8,
        unsigned int *a9)
{
  void **v9; // r12
  void **v10; // rbx
  const char *v12; // rax
  _QWORD *v13; // r14
  void *v14; // r15
  unsigned __int64 v15; // rdi
  __int64 v16; // rax
  char **v17; // r11
  unsigned int v18; // eax
  char *v19; // rax
  unsigned __int64 v20; // rax
  const char *v21; // rdx
  const char *v22; // rcx
  char *v23; // rax
  DWORD LastError; // eax
  BOOL fAutoDetect; // eax
  unsigned __int16 v26; // r8
  int v27; // ecx
  char *v28; // rcx
  __int64 v29; // r13
  unsigned int v30; // r15d
  unsigned int v31; // eax
  void *v32; // rax
  void *v33; // rdx
  __int64 v34; // rax
  unsigned int v35; // edx
  void *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  BOOL ProxyForUrl; // ebx
  DWORD v40; // r14d
  unsigned __int16 *lpszProxy; // r14
  unsigned __int16 *lpszProxyBypass; // rbx
  unsigned int v43; // r13d
  unsigned int v44; // eax
  unsigned __int16 *v45; // rax
  unsigned __int16 *v46; // r15
  int v47; // r13d
  enum tagRPCProxyAccessType *v48; // rdi
  unsigned int v49; // ebx
  unsigned int v50; // eax
  char *v51; // rax
  int v52; // eax
  void **v53; // rdi
  void **v54; // rdi
  int v56; // [rsp+48h] [rbp-B8h] BYREF
  char **v57; // [rsp+50h] [rbp-B0h]
  void *Src; // [rsp+58h] [rbp-A8h]
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+60h] [rbp-A0h] BYREF
  HINTERNET hSession; // [rsp+80h] [rbp-80h]
  enum tagRPCProxyAccessType *v61; // [rsp+88h] [rbp-78h]
  void **v62; // [rsp+90h] [rbp-70h]
  char *v63; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v64; // [rsp+A0h] [rbp-60h] BYREF
  char *v65; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v66; // [rsp+B0h] [rbp-50h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+B8h] [rbp-48h] BYREF
  void **v68; // [rsp+D8h] [rbp-28h]
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+E0h] [rbp-20h] BYREF
  char v70[304]; // [rsp+100h] [rbp+0h] BYREF

  v9 = (void **)a7;
  v10 = (void **)a6;
  *a4 = 0;
  v12 = a2;
  Src = a2;
  v13 = 0;
  v14 = 0;
  *a3 = 0;
  *a7 = 0;
  *a6 = 0;
  *(_DWORD *)a8 = 0;
  *a9 = 0;
  v68 = (void **)a3;
  v61 = a8;
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  v66 = 0;
  v64 = 0;
  v56 = 0;
  v15 = -1;
  v62 = (void **)a4;
  v57 = a6;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  if ( a1 && *a1 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a1[v16] );
    if ( (unsigned int)(v16 + 1) > 0x12C )
      goto LABEL_76;
    SimpleUnicodeToAnsi(a1, v16 + 1, v70);
    v18 = ParseOptList(v70, a3, v17, a6, a7, (enum tagHttpConnectionOptions *)&v56);
    *a9 = v18;
    if ( v18 )
    {
LABEL_77:
      v53 = v68;
      if ( *v68 )
      {
        I_RpcFree(*v68);
        *v53 = 0;
      }
      v54 = v62;
      if ( *v62 )
      {
        I_RpcFree(*v62);
        *v54 = 0;
      }
      if ( *v10 )
      {
        I_RpcFree(*v10);
        *v10 = 0;
      }
      if ( *v9 )
      {
        I_RpcFree(*v9);
        *v9 = 0;
      }
      if ( pProxyConfig.lpszAutoConfigUrl )
        GlobalFree(pProxyConfig.lpszAutoConfigUrl);
      if ( pProxyConfig.lpszProxy )
        GlobalFree(pProxyConfig.lpszProxy);
      if ( pProxyConfig.lpszProxyBypass )
        GlobalFree(pProxyConfig.lpszProxyBypass);
      if ( v13 )
        I_RpcFree(v13);
      if ( v14 )
        I_RpcFree(v14);
      CNlDelUnicodeAnsi::~CNlDelUnicodeAnsi((CNlDelUnicodeAnsi *)&v63);
      CNlDelUnicodeAnsi::~CNlDelUnicodeAnsi((CNlDelUnicodeAnsi *)&v65);
      return 0;
    }
    v12 = (const char *)Src;
  }
  if ( *a3 )
  {
    v20 = -1;
    do
      ++v20;
    while ( (*a3)[v20] );
    if ( v20 > 0x100 )
      goto LABEL_76;
  }
  else
  {
    v19 = DuplicateStringA(v12);
    *a3 = v19;
    if ( !v19 )
    {
LABEL_10:
      *a9 = 14;
      goto LABEL_77;
    }
  }
  v21 = "80";
  if ( !*v62 )
  {
    v22 = "443";
    if ( !a5 )
      v22 = "80";
    v23 = DuplicateStringA(v22);
    a1 = (unsigned __int16 *)v62;
    *v62 = v23;
    if ( !v23 )
      goto LABEL_10;
    v21 = "80";
  }
  if ( *a6 )
  {
    if ( !*a7 )
    {
      v51 = DuplicateStringA("80");
      *a7 = v51;
      if ( !v51 )
        goto LABEL_10;
    }
    v52 = _stricmp(*a6, "<none>");
    if ( v56 == 1 )
    {
      if ( !v52 )
        goto LABEL_75;
      *(_DWORD *)v61 = 2;
    }
    else if ( !v52 )
    {
      *(_DWORD *)v61 = 1;
      *a6 = 0;
    }
    goto LABEL_71;
  }
  LOBYTE(v21) = 111;
  LOBYTE(a1) = 50;
  I_RpcLogEvent(a1, v21, &pProxyConfig, 26214422, 0, 0, 0);
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
  {
    fAutoDetect = pProxyConfig.fAutoDetect;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      v26 = 3000;
LABEL_24:
      CompRpcpErrorAddRecord(0xDu, 0xEu, v26, LastError);
LABEL_25:
      *a9 = 14;
LABEL_26:
      v9 = (void **)a7;
      goto LABEL_77;
    }
    fAutoDetect = 1;
    pProxyConfig.fAutoDetect = 1;
    memset(&pProxyConfig.lpszAutoConfigUrl, 0, 24);
  }
  v27 = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  if ( fAutoDetect )
  {
    pAutoProxyOptions.dwFlags = 1;
    v27 = 1;
    pAutoProxyOptions.dwAutoDetectFlags = 3;
  }
  if ( pProxyConfig.lpszAutoConfigUrl )
  {
    pAutoProxyOptions.lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
    fAutoDetect = 1;
    pAutoProxyOptions.dwFlags = v27 | 2;
    pProxyConfig.fAutoDetect = 1;
  }
  v28 = *a3;
  v29 = -1;
  Src = v28;
  do
    ++v29;
  while ( v28[v29] );
  if ( !fAutoDetect )
    goto LABEL_47;
  v30 = v29 + (a5 != 0) + 8;
  LODWORD(hSession) = v30;
  v13 = I_RpcAllocate(v30);
  v31 = 2 * v30;
  if ( !is_mul_ok(v30, 2u) )
    v31 = -1;
  v32 = I_RpcAllocate(v31);
  v14 = v32;
  if ( !v13 || !v32 )
    goto LABEL_25;
  v33 = Src;
  if ( a5 )
  {
    *v13 = 0x2F2F3A7370747468LL;
    memcpy_0(v13 + 1, v33, (unsigned int)v29);
    v34 = (unsigned int)(v29 + 8);
  }
  else
  {
    *(_DWORD *)v13 = 1886680168;
    *((_WORD *)v13 + 2) = 12090;
    *((_BYTE *)v13 + 6) = 47;
    memcpy_0((char *)v13 + 7, v33, (unsigned int)v29);
    v34 = (unsigned int)(v29 + 7);
  }
  v35 = (unsigned int)hSession;
  *((_BYTE *)v13 + v34) = 0;
  SimpleAnsiToUnicode((char *)v13, v35, (unsigned __int16 *)v14);
  v36 = WinHttpOpen(L"MSRPC", 1u, 0, 0, 0x10000000u);
  v38 = 0;
  hSession = v36;
  if ( !v36 )
  {
    LastError = GetLastError();
    v26 = 3002;
    goto LABEL_24;
  }
  LOBYTE(v38) = 50;
  LOBYTE(v37) = 111;
  I_RpcLogEvent(v38, v37, v36, 26279958, (_DWORD)v14, 0, 0);
  ProxyForUrl = WinHttpGetProxyForUrl(hSession, (LPCWSTR)v14, &pAutoProxyOptions, &pProxyInfo);
  I_RpcFree(v14);
  I_RpcFree(v13);
  v40 = GetLastError();
  WinHttpCloseHandle(hSession);
  if ( !ProxyForUrl )
  {
    CompRpcpErrorAddRecord(0xDu, 0xEu, 0xBB9u, v40);
    pProxyConfig.fAutoDetect = 0;
LABEL_47:
    lpszProxy = pProxyConfig.lpszProxy;
    lpszProxyBypass = pProxyConfig.lpszProxyBypass;
    goto LABEL_48;
  }
  lpszProxy = pProxyInfo.lpszProxy;
  lpszProxyBypass = pProxyInfo.lpszProxyBypass;
  if ( !pProxyConfig.fAutoDetect )
    goto LABEL_47;
LABEL_48:
  v43 = v29 + 1;
  v44 = 2 * v43;
  if ( !is_mul_ok(v43, 2u) )
    v44 = -1;
  v45 = (unsigned __int16 *)I_RpcAllocate(v44);
  v46 = v45;
  if ( !v45 )
  {
    *a9 = 14;
    v14 = 0;
    v13 = 0;
LABEL_52:
    v10 = (void **)v57;
    goto LABEL_26;
  }
  SimpleAnsiToUnicode((char *)Src, v43, v45);
  v47 = v56;
  v48 = v61;
  if ( v56 == 1 )
    lpszProxyBypass = 0;
  v49 = HttpProcessProxySettings(v46, a5, lpszProxy, lpszProxyBypass, &v66, &v64, v61);
  I_RpcFree(v46);
  v13 = 0;
  if ( v49 )
  {
    v66 = 0;
    v14 = 0;
    v64 = 0;
    *a9 = v49;
    goto LABEL_52;
  }
  if ( *(_DWORD *)v48 != 2 && v47 == 1 )
  {
    v10 = (void **)v57;
    v14 = 0;
LABEL_75:
    v9 = (void **)a7;
LABEL_76:
    *a9 = 1724;
    goto LABEL_77;
  }
  v50 = CNlDelUnicodeAnsi::ConvertOptional(&v65);
  v10 = (void **)v57;
  if ( v50 || (*v57 = v65, (v50 = CNlDelUnicodeAnsi::ConvertOptional(&v63)) != 0) )
  {
    *a9 = v50;
    v14 = 0;
    goto LABEL_26;
  }
  v15 = -1;
  *a7 = v63;
LABEL_71:
  if ( *v10 )
  {
    do
      ++v15;
    while ( *((_BYTE *)*v10 + v15) );
    if ( v15 > 0x100 )
    {
      v14 = 0;
      goto LABEL_75;
    }
  }
  if ( pProxyConfig.lpszAutoConfigUrl )
    GlobalFree(pProxyConfig.lpszAutoConfigUrl);
  if ( pProxyConfig.lpszProxy )
    GlobalFree(pProxyConfig.lpszProxy);
  if ( pProxyConfig.lpszProxyBypass )
    GlobalFree(pProxyConfig.lpszProxyBypass);
  CNlDelUnicodeAnsi::~CNlDelUnicodeAnsi((CNlDelUnicodeAnsi *)&v63);
  CNlDelUnicodeAnsi::~CNlDelUnicodeAnsi((CNlDelUnicodeAnsi *)&v65);
  return 1;
}

```

## disassembly

```asm
0x18001cb10  push    rbp
0x18001cb12  push    rbx
0x18001cb13  push    rsi
0x18001cb14  push    rdi
0x18001cb15  push    r12
0x18001cb17  push    r13
0x18001cb19  push    r14
0x18001cb1b  push    r15
0x18001cb1d  lea     rbp, [rsp-148h]
0x18001cb25  sub     rsp, 248h
0x18001cb2c  mov     rax, cs:__security_cookie
0x18001cb33  xor     rax, rsp
0x18001cb36  mov     [rbp+180h+var_50], rax
0x18001cb3d  mov     r12, [rbp+180h+arg_30]
0x18001cb44  xor     edi, edi
0x18001cb46  mov     rbx, [rbp+180h+arg_28]
0x18001cb4d  xorps   xmm0, xmm0
0x18001cb50  mov     rsi, [rbp+180h+arg_40]
0x18001cb57  mov     r13, r8
0x18001cb5a  mov     [r9], rdi
0x18001cb5d  mov     rax, rdx
0x18001cb60  mov     [rsp+280h+Src], rdx
0x18001cb65  mov     r14d, edi
0x18001cb68  mov     rdx, [rbp+180h+arg_38]
0x18001cb6f  mov     r15d, edi
0x18001cb72  mov     [r13+0], rdi
0x18001cb76  xorps   xmm1, xmm1
0x18001cb79  mov     [r12], rdi
0x18001cb7d  mov     r11, r9
0x18001cb80  mov     [rbx], rdi
0x18001cb83  mov     [rdx], edi
0x18001cb85  mov     [rsi], edi
0x18001cb87  mov     [rbp+180h+var_1A8], r8
0x18001cb8b  xor     r8d, r8d
0x18001cb8e  mov     [rbp+180h+var_1F8], rdx
0x18001cb92  xor     edx, edx
0x18001cb94  mov     qword ptr [rsp+280h+pProxyConfig.fAutoDetect], rdi
0x18001cb99  mov     [rbp+180h+var_1D0], rdi
0x18001cb9d  mov     [rbp+180h+var_1E0], rdi
0x18001cba1  mov     [rsp+280h+var_238], edi
0x18001cba5  mov     [rsp+280h+pProxyConfig.lpszProxyBypass], rdi
0x18001cbaa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001cbae  mov     [rbp+180h+var_1F0], r9
0x18001cbb2  mov     [rsp+280h+var_230], rbx
0x18001cbb7  mov     [rsp+280h+var_240], r12
0x18001cbbc  mov     [rbp+180h+pProxyInfo.lpszProxyBypass], r8
0x18001cbc0  movups  xmmword ptr [rbp+180h+pAutoProxyOptions.dwFlags], xmm0
0x18001cbc4  movups  xmmword ptr [rbp+180h+pAutoProxyOptions.lpvReserved], xmm0
0x18001cbc8  movups  xmmword ptr [rbp+180h+pProxyInfo.dwAccessType], xmm1
0x18001cbcc  movdqu  xmmword ptr [rsp+280h+pProxyConfig.lpszAutoConfigUrl], xmm0
0x18001cbd2  test    rcx, rcx
0x18001cbd5  jz      short loc_18001CC30
0x18001cbd7  cmp     [rcx], dx
0x18001cbda  jz      short loc_18001CC30
0x18001cbdc  mov     rax, rdi
0x18001cbdf  inc     rax
0x18001cbe2  cmp     [rcx+rax*2], dx
0x18001cbe6  jnz     short loc_18001CBDF
0x18001cbe8  lea     edx, [rax+1]; unsigned int
0x18001cbeb  cmp     edx, 12Ch
0x18001cbf1  ja      loc_18001D0A7
0x18001cbf7  lea     r8, [rbp+180h+var_180]; char *
0x18001cbfb  call    ?SimpleUnicodeToAnsi@@YAXPEAGKPEAD@Z; SimpleUnicodeToAnsi(ushort *,ulong,char *)
0x18001cc00  lea     rcx, [rsp+280h+var_238]
0x18001cc05  mov     r9, rbx; char **
0x18001cc08  mov     [rsp+280h+var_258], rcx; enum tagHttpConnectionOptions *
0x18001cc0d  mov     r8, r11; char **
0x18001cc10  lea     rcx, [rbp+180h+var_180]; char *
0x18001cc14  mov     qword ptr [rsp+280h+dwFlags], r12; char **
0x18001cc19  mov     rdx, r13; char **
0x18001cc1c  call    ?ParseOptList@@YAKPEADPEAPEAD111PEAW4tagHttpConnectionOptions@@@Z; ParseOptList(char *,char * *,char * *,char * *,char * *,tagHttpConnectionOptions *)
0x18001cc21  mov     [rsi], eax
0x18001cc23  test    eax, eax
0x18001cc25  jnz     loc_18001D0AD
0x18001cc2b  mov     rax, [rsp+280h+Src]
0x18001cc30  mov     rdx, [r13+0]
0x18001cc34  test    rdx, rdx
0x18001cc37  jnz     short loc_18001CC55
0x18001cc39  mov     rcx, rax; Src
0x18001cc3c  call    ?DuplicateStringA@@YAPEADPEBD@Z; DuplicateStringA(char const *)
0x18001cc41  mov     [r13+0], rax
0x18001cc45  test    rax, rax
0x18001cc48  jnz     short loc_18001CC6D
0x18001cc4a  mov     dword ptr [rsi], 0Eh
0x18001cc50  jmp     loc_18001D0AD
0x18001cc55  mov     rax, rdi
0x18001cc58  inc     rax
0x18001cc5b  cmp     [rdx+rax], r14b
0x18001cc5f  jnz     short loc_18001CC58
0x18001cc61  cmp     rax, 100h
0x18001cc67  ja      loc_18001D0A7
0x18001cc6d  mov     rax, [rbp+180h+var_1F0]
0x18001cc71  lea     rdx, Src; "80"
0x18001cc78  cmp     [rax], r14
0x18001cc7b  jnz     short loc_18001CCA7
0x18001cc7d  cmp     [rbp+180h+arg_20], r14d
0x18001cc84  lea     rcx, a443_0; "443"
0x18001cc8b  cmovz   rcx, rdx; Src
0x18001cc8f  call    ?DuplicateStringA@@YAPEADPEBD@Z; DuplicateStringA(char const *)
0x18001cc94  mov     rcx, [rbp+180h+var_1F0]
0x18001cc98  mov     [rcx], rax
0x18001cc9b  test    rax, rax
0x18001cc9e  jz      short loc_18001CC4A
0x18001cca0  lea     rdx, Src; "80"
0x18001cca7  xor     eax, eax
0x18001cca9  cmp     [rbx], rax
0x18001ccac  jnz     loc_18001D027
0x18001ccb2  mov     dword ptr [rsp+280h+var_250], eax
0x18001ccb6  lea     r8, [rsp+280h+pProxyConfig]
0x18001ccbb  mov     dword ptr [rsp+280h+var_258], eax
0x18001ccbf  mov     r9d, 1900016h
0x18001ccc5  mov     dl, 6Fh ; 'o'
0x18001ccc7  mov     [rsp+280h+dwFlags], eax
0x18001cccb  mov     cl, 32h ; '2'
0x18001cccd  call    cs:__imp_I_RpcLogEvent
0x18001ccd3  lea     rcx, [rsp+280h+pProxyConfig]; pProxyConfig
0x18001ccd8  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18001ccde  mov     r12d, 1
0x18001cce4  test    eax, eax
0x18001cce6  jnz     short loc_18001CD30
0x18001cce8  call    cs:__imp_GetLastError
0x18001ccee  cmp     eax, 2
0x18001ccf1  jnz     short loc_18001CD0A
0x18001ccf3  mov     eax, r12d
0x18001ccf6  mov     [rsp+280h+pProxyConfig.lpszProxyBypass], r15
0x18001ccfb  xorps   xmm0, xmm0
0x18001ccfe  mov     [rsp+280h+pProxyConfig.fAutoDetect], eax
0x18001cd02  movdqu  xmmword ptr [rsp+280h+pProxyConfig.lpszAutoConfigUrl], xmm0
0x18001cd08  jmp     short loc_18001CD34
0x18001cd0a  mov     r8d, 0BB8h; unsigned __int16
0x18001cd10  mov     edi, 0Eh
0x18001cd15  mov     r9d, eax; unsigned int
0x18001cd18  mov     edx, edi; unsigned int
0x18001cd1a  mov     ecx, 0Dh; unsigned int
0x18001cd1f  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x18001cd24  mov     [rsi], edi
0x18001cd26  mov     r12, [rsp+280h+var_240]
0x18001cd2b  jmp     loc_18001D0AD
0x18001cd30  mov     eax, [rsp+280h+pProxyConfig.fAutoDetect]
0x18001cd34  xorps   xmm0, xmm0
0x18001cd37  mov     ecx, r15d
0x18001cd3a  movups  xmmword ptr [rbp+180h+pAutoProxyOptions.dwFlags], xmm0
0x18001cd3e  movups  xmmword ptr [rbp+180h+pAutoProxyOptions.lpvReserved], xmm0
0x18001cd42  test    eax, eax
0x18001cd44  jz      short loc_18001CD54
0x18001cd46  mov     [rbp+180h+pAutoProxyOptions.dwFlags], r12d
0x18001cd4a  mov     ecx, r12d
0x18001cd4d  mov     [rbp+180h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x18001cd54  mov     rdx, [rsp+280h+pProxyConfig.lpszAutoConfigUrl]
0x18001cd59  test    rdx, rdx
0x18001cd5c  jz      short loc_18001CD6F
0x18001cd5e  or      ecx, 2
0x18001cd61  mov     [rbp+180h+pAutoProxyOptions.lpszAutoConfigUrl], rdx
0x18001cd65  mov     eax, r12d
0x18001cd68  mov     [rbp+180h+pAutoProxyOptions.dwFlags], ecx
0x18001cd6b  mov     [rsp+280h+pProxyConfig.fAutoDetect], eax
0x18001cd6f  mov     rcx, [r13+0]
0x18001cd73  mov     r13, rdi
0x18001cd76  mov     [rsp+280h+Src], rcx
0x18001cd7b  inc     r13
0x18001cd7e  cmp     [rcx+r13], r15b
0x18001cd82  jnz     short loc_18001CD7B
0x18001cd84  mov     edi, 0Eh
0x18001cd89  test    eax, eax
0x18001cd8b  jz      loc_18001CF19
0x18001cd91  mov     eax, [rbp+180h+arg_20]
0x18001cd97  neg     eax
0x18001cd99  sbb     ecx, ecx
0x18001cd9b  neg     ecx
0x18001cd9d  lea     r15d, [rcx+8]
0x18001cda1  add     r15d, r13d
0x18001cda4  mov     ecx, r15d; Size
0x18001cda7  mov     dword ptr [rbp+180h+hSession], r15d
0x18001cdab  call    cs:__imp_I_RpcAllocate
0x18001cdb1  mov     r14, rax
0x18001cdb4  mov     ecx, r15d
0x18001cdb7  lea     eax, [rdi-0Ch]
0x18001cdba  mul     rcx
0x18001cdbd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001cdc4  cmovb   rax, rcx
0x18001cdc8  mov     ecx, eax; Size
0x18001cdca  call    cs:__imp_I_RpcAllocate
0x18001cdd0  xor     ecx, ecx
0x18001cdd2  mov     r15, rax
0x18001cdd5  test    r14, r14
0x18001cdd8  jz      loc_18001CD24
0x18001cdde  test    rax, rax
0x18001cde1  jz      loc_18001CD24
0x18001cde7  mov     rdx, [rsp+280h+Src]; Src
0x18001cdec  mov     r8d, r13d; Size
0x18001cdef  cmp     [rbp+180h+arg_20], ecx
0x18001cdf5  jz      short loc_18001CE13
0x18001cdf7  mov     rax, 2F2F3A7370747468h
0x18001ce01  lea     rcx, [r14+8]; void *
0x18001ce05  mov     [r14], rax
0x18001ce08  call    memcpy_0
0x18001ce0d  lea     eax, [r13+8]
0x18001ce11  jmp     short loc_18001CE40
0x18001ce13  mov     rax, cs:qword_180028640
0x18001ce1a  lea     rcx, [r14+7]; void *
0x18001ce1e  mov     [r14], eax
0x18001ce21  movzx   eax, word ptr cs:qword_180028640+4
0x18001ce28  mov     [r14+4], ax
0x18001ce2d  mov     al, byte ptr cs:qword_180028640+6
0x18001ce33  mov     [r14+6], al
0x18001ce37  call    memcpy_0
0x18001ce3c  lea     eax, [r13+7]
0x18001ce40  mov     edx, dword ptr [rbp+180h+hSession]; unsigned int
0x18001ce43  mov     r8, r15; unsigned __int16 *
0x18001ce46  mov     rcx, r14; char *
0x18001ce49  mov     byte ptr [rax+r14], 0
0x18001ce4e  call    ?SimpleAnsiToUnicode@@YAXPEADKPEAG@Z; SimpleAnsiToUnicode(char *,ulong,ushort *)
0x18001ce53  lea     rcx, pszAgentW; "MSRPC"
0x18001ce5a  mov     [rsp+280h+dwFlags], 10000000h; dwFlags
0x18001ce62  xor     r9d, r9d; pszProxyBypassW
0x18001ce65  xor     r8d, r8d; pszProxyW
0x18001ce68  mov     edx, r12d; dwAccessType
0x18001ce6b  call    cs:__imp_WinHttpOpen
0x18001ce71  xor     ecx, ecx
0x18001ce73  mov     [rbp+180h+hSession], rax
0x18001ce77  test    rax, rax
0x18001ce7a  jnz     short loc_18001CE8D
0x18001ce7c  call    cs:__imp_GetLastError
0x18001ce82  mov     r8d, 0BBAh
0x18001ce88  jmp     loc_18001CD15
0x18001ce8d  mov     dword ptr [rsp+280h+var_250], ecx
0x18001ce91  mov     r9d, 1910016h
0x18001ce97  mov     dword ptr [rsp+280h+var_258], ecx
0x18001ce9b  mov     r8, rax
0x18001ce9e  mov     cl, 32h ; '2'
0x18001cea0  mov     [rsp+280h+dwFlags], r15d
0x18001cea5  mov     dl, 6Fh ; 'o'
0x18001cea7  call    cs:__imp_I_RpcLogEvent
0x18001cead  mov     rcx, [rbp+180h+hSession]; hSession
0x18001ceb1  lea     r9, [rbp+180h+pProxyInfo]; pProxyInfo
0x18001ceb5  lea     r8, [rbp+180h+pAutoProxyOptions]; pAutoProxyOptions
0x18001ceb9  mov     rdx, r15; lpcwszUrl
0x18001cebc  call    cs:__imp_WinHttpGetProxyForUrl
0x18001cec2  mov     rcx, r15; Object
0x18001cec5  mov     ebx, eax
0x18001cec7  call    cs:__imp_I_RpcFree
0x18001cecd  mov     rcx, r14; Object
0x18001ced0  call    cs:__imp_I_RpcFree
0x18001ced6  call    cs:__imp_GetLastError
0x18001cedc  mov     rcx, [rbp+180h+hSession]; hInternet
0x18001cee0  mov     r14d, eax
0x18001cee3  call    cs:__imp_WinHttpCloseHandle
0x18001cee9  xor     r15d, r15d
0x18001ceec  test    ebx, ebx
0x18001ceee  jnz     short loc_18001CF0A
0x18001cef0  mov     r8d, 0BB9h; unsigned __int16
0x18001cef6  lea     ecx, [rbx+0Dh]; unsigned int
0x18001cef9  mov     r9d, r14d; unsigned int
0x18001cefc  mov     edx, edi; unsigned int
0x18001cefe  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x18001cf03  mov     [rsp+280h+pProxyConfig.fAutoDetect], r15d
0x18001cf08  jmp     short loc_18001CF19
0x18001cf0a  mov     r14, [rbp+180h+pProxyInfo.lpszProxy]
0x18001cf0e  mov     rbx, [rbp+180h+pProxyInfo.lpszProxyBypass]
0x18001cf12  cmp     [rsp+280h+pProxyConfig.fAutoDetect], r15d
0x18001cf17  jnz     short loc_18001CF23
0x18001cf19  mov     r14, [rsp+280h+pProxyConfig.lpszProxy]
0x18001cf1e  mov     rbx, [rsp+280h+pProxyConfig.lpszProxyBypass]
0x18001cf23  inc     r13d
0x18001cf26  mov     eax, 2
0x18001cf2b  mov     ecx, r13d
0x18001cf2e  mul     rcx
0x18001cf31  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001cf38  cmovb   rax, rcx
0x18001cf3c  mov     ecx, eax; Size
0x18001cf3e  call    cs:__imp_I_RpcAllocate
0x18001cf44  xor     ecx, ecx
0x18001cf46  mov     r15, rax
0x18001cf49  test    rax, rax
0x18001cf4c  jnz     short loc_18001CF60
0x18001cf4e  mov     [rsi], edi
0x18001cf50  mov     r15d, ecx
0x18001cf53  mov     r14d, ecx
0x18001cf56  mov     rbx, [rsp+280h+var_230]
0x18001cf5b  jmp     loc_18001CD26
0x18001cf60  mov     rcx, [rsp+280h+Src]; char *
0x18001cf65  mov     r8, r15; unsigned __int16 *
0x18001cf68  mov     edx, r13d; unsigned int
0x18001cf6b  call    ?SimpleAnsiToUnicode@@YAXPEADKPEAG@Z; SimpleAnsiToUnicode(char *,ulong,ushort *)
0x18001cf70  mov     r13d, [rsp+280h+var_238]
0x18001cf75  xor     eax, eax
0x18001cf77  mov     rdi, [rbp+180h+var_1F8]
0x18001cf7b  cmp     r13d, r12d
0x18001cf7e  mov     edx, [rbp+180h+arg_20]; int
0x18001cf84  mov     r8, r14; unsigned __int16 *
0x18001cf87  cmovz   rbx, rax
0x18001cf8b  mov     [rsp+280h+var_250], rdi; enum tagRPCProxyAccessType *
0x18001cf90  lea     rax, [rbp+180h+var_1E0]
0x18001cf94  mov     r9, rbx; unsigned __int16 *
0x18001cf97  mov     [rsp+280h+var_258], rax; unsigned __int16 **
0x18001cf9c  mov     rcx, r15; unsigned __int16 *
0x18001cf9f  lea     rax, [rbp+180h+var_1D0]
0x18001cfa3  mov     qword ptr [rsp+280h+dwFlags], rax; unsigned __int16 **
0x18001cfa8  call    ?HttpProcessProxySettings@@YAJPEAGH00PEAPEAG1PEAW4tagRPCProxyAccessType@@@Z; HttpProcessProxySettings(ushort *,int,ushort *,ushort *,ushort * *,ushort * *,tagRPCProxyAccessType *)
0x18001cfad  mov     rcx, r15; Object
  ... truncated ...
```
