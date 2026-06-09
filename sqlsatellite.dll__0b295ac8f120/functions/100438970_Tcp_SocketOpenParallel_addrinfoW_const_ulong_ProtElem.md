# Tcp::SocketOpenParallel(addrinfoW const *,ulong,ProtElem *)

- ea: `0x100438970`
- end: `0x100438ef8`
- name: `?SocketOpenParallel@Tcp@@QEAAKPEBUaddrinfoW@@KPEAVProtElem@@@Z`
- size: `1416`
- prototype: `unsigned int __fastcall(Tcp *__hidden this, const struct addrinfoW *, unsigned int, struct ProtElem *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100439390`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100435d20`
- `0x100435f90`
- `0x100436140`
- `0x100436280`
- `0x100436430`
- `0x1004368f0`
- `0x100436bd0`
- `0x100438970`
- `0x100486b14`
- `0x100487684`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x100438bbc`
- `KERNEL32!WaitForMultipleObjects` at `0x100438d83`
- `KERNEL32!WaitForMultipleObjects` at `0x100438bbc`
- `KERNEL32!WaitForMultipleObjects` at `0x100438d83`
- `KERNEL32!GetTickCount` at `0x1004389f8`
- `KERNEL32!GetTickCount` at `0x100438cc5`
- `KERNEL32!GetTickCount` at `0x1004389f8`
- `KERNEL32!GetTickCount` at `0x100438cc5`
- `KERNEL32!GetLastError` at `0x100438c49`
- `KERNEL32!GetLastError` at `0x100438db8`
- `KERNEL32!GetLastError` at `0x100438c49`
- `KERNEL32!GetLastError` at `0x100438db8`
- `sqldk!??_V@YAXPEAX@Z` at `0x100438e61`
- `sqldk!??_V@YAXPEAX@Z` at `0x100438e73`
- `sqldk!??_V@YAXPEAX@Z` at `0x100438e61`
- `sqldk!??_V@YAXPEAX@Z` at `0x100438e73`

## string_xrefs

- `0x1004389a5`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100438ddf`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100438e11`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100438e46`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100438ed6`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004389b0`: `Tcp::SocketOpenParallel`
- `0x100438e3f`: `Tcp::SocketOpenParallel`
- `0x100438ecf`: `Tcp::SocketOpenParallel`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Tcp::SocketOpenParallel(Tcp *this, const struct addrinfoW *a2, DWORD a3, struct ProtElem *a4)
{
  unsigned int v6; // edx
  const struct addrinfoW *i; // rcx
  int ai_family; // eax
  unsigned int v9; // esi
  const wchar_t *v10; // r9
  HANDLE *v11; // r15
  DWORD v12; // ebx
  struct addrinfoW *v13; // rdi
  DWORD v14; // r12d
  HANDLE *v15; // r14
  DWORD v16; // esi
  struct addrinfoW *v17; // r13
  int v18; // eax
  struct addrinfoW *v19; // rsi
  unsigned int v20; // eax
  __int64 v21; // rcx
  Tcp *v22; // r12
  PWSTR ai_canonname; // rax
  DWORD v24; // ecx
  DWORD v25; // eax
  _BYTE *v26; // rdi
  __int64 v27; // r8
  unsigned int j; // ebx
  __int64 v29; // rcx
  __int64 v30; // rax
  struct addrinfoW *v31; // rdi
  DWORD v32; // r12d
  DWORD LastError; // eax
  unsigned int v34; // eax
  __int64 v35; // r9
  DWORD v36; // eax
  TcpConnection **v37; // rdi
  __int64 v38; // r12
  __int64 v39; // r13
  signed __int64 v40; // r14
  DWORD v41; // eax
  HANDLE *v42; // rcx
  DWORD v43; // eax
  _QWORD *p_ai_next; // rbx
  __int64 v46; // [rsp+20h] [rbp-69h]
  __int64 v47; // [rsp+28h] [rbp-61h]
  __int64 v48; // [rsp+30h] [rbp-59h]
  DWORD TickCount; // [rsp+40h] [rbp-49h]
  struct addrinfoW *v50[2]; // [rsp+70h] [rbp-19h] BYREF
  HANDLE *lpHandles[2]; // [rsp+80h] [rbp-9h]
  DWORD nCount[20]; // [rsp+90h] [rbp+7h]
  DWORD dwMilliseconds; // [rsp+F8h] [rbp+6Fh]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "Tcp::SocketOpenParallel",
      6724,
      L"API|SNI%u#, AI: %p{ADDRINFO*}, ai_family: %d, timeout: %d\n",
      *((_DWORD *)this + 11),
      a2,
      a2->ai_family,
      a3);
  TickCount = GetTickCount();
  dwMilliseconds = a3;
  *(_OWORD *)v50 = 0;
  *(_OWORD *)lpHandles = 0;
  *(_QWORD *)nCount = 0;
  v6 = 0;
  for ( i = a2; i; i = i->ai_next )
  {
    ai_family = i->ai_family;
    if ( (ai_family == 2 || ai_family == 23) && ++v6 > 0x40 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v48) = -1;
        LODWORD(v47) = 47;
        LODWORD(v46) = 7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "ParallelConnectWaitSet::Initialize",
          4046,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v46,
          v47,
          v48);
      }
      SNISetLastError(7u, 0xFFFFFFFF, 0xC3E3u);
      v9 = -1;
      goto LABEL_65;
    }
  }
  v50[0] = (struct addrinfoW *)a2;
  v9 = ParallelConnectWaitSet::SetSize((ParallelConnectWaitSet *)v50, v6);
  v11 = lpHandles[1];
  v12 = nCount[0];
  if ( v9 )
  {
    v15 = lpHandles[0];
    goto LABEL_53;
  }
  v13 = v50[0];
  v14 = 0;
  v15 = lpHandles[0];
  v16 = nCount[1];
  v17 = v50[1];
  if ( !nCount[1] )
  {
LABEL_22:
    v22 = this;
    *((_QWORD *)this + 8) = -1;
    goto LABEL_26;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v18 = v13->ai_family;
      if ( v18 == 2 || v18 == 23 )
        break;
      v13 = v13->ai_next;
    }
    v19 = &v17[v14];
    if ( !TcpConnection::FInit((TcpConnection *)v19, this, v13, a4)
      && !(unsigned int)TcpConnection::FInitForAsync((TcpConnection *)v19) )
    {
      break;
    }
LABEL_21:
    v13 = v13->ai_next;
    ++v14;
    v16 = nCount[1];
    if ( v14 >= nCount[1] )
      goto LABEL_22;
  }
  v20 = TcpConnection::AsyncOpen((TcpConnection *)v19);
  if ( v20 )
  {
    if ( v20 == 997 )
    {
      v21 = v12;
      v15[v21] = v19;
      v11[v21] = (HANDLE)v19->ai_addrlen;
      nCount[0] = ++v12;
    }
    goto LABEL_21;
  }
  ai_canonname = v17[v14].ai_canonname;
  v17[v14].ai_canonname = (PWSTR)-1LL;
  v22 = this;
  *((_QWORD *)this + 8) = ai_canonname;
  if ( ai_canonname != (PWSTR)-1LL )
  {
LABEL_24:
    v9 = 0;
    goto LABEL_53;
  }
  v16 = nCount[1];
LABEL_26:
  if ( v12 )
  {
    v24 = dwMilliseconds;
    while ( 1 )
    {
      v25 = WaitForMultipleObjects(v12, v11, 0, v24);
      if ( v25 >= v12 )
      {
        if ( v25 == -1 )
        {
          LastError = GetLastError();
          v34 = TcpConnection::CalculateReturnCode(v17, v16, LastError, 4);
          v31 = v50[1];
          v32 = nCount[1];
        }
        else
        {
          _mm_lfence();
          v35 = 4;
          if ( v25 == 258 )
            v35 = 1;
          v32 = nCount[1];
          v31 = v50[1];
          v34 = TcpConnection::CalculateReturnCode(v50[1], nCount[1], v25, v35);
          v12 = nCount[0];
          v11 = lpHandles[1];
          v15 = lpHandles[0];
        }
        v9 = v34;
        if ( v34 )
          goto LABEL_53;
      }
      else
      {
        _mm_lfence();
        v15 = lpHandles[0];
        v26 = lpHandles[0][v25];
        v27 = v25 + 1;
        v11 = lpHandles[1];
        for ( j = nCount[0]; (unsigned int)v27 < j; v27 = (unsigned int)(v27 + 1) )
        {
          v29 = (unsigned int)(v27 - 1);
          v15[v29] = v15[v27];
          v11[v29] = v11[v27];
        }
        v12 = j - 1;
        nCount[0] = v12;
        v26[32] = 0;
        if ( !TcpConnection::CheckCompletedAsyncConnect((TcpConnection *)v26) )
        {
          v30 = *((_QWORD *)v26 + 3);
          *((_QWORD *)v26 + 3) = -1;
          *((_QWORD *)v22 + 8) = v30;
        }
        v31 = v50[1];
        v32 = nCount[1];
      }
      if ( *((_QWORD *)this + 8) != -1 )
        goto LABEL_24;
      if ( a3 == -1 )
      {
        v24 = dwMilliseconds;
      }
      else
      {
        v36 = GetTickCount() - TickCount;
        if ( a3 < v36 )
        {
          v9 = TcpConnection::CalculateReturnCode(v31, v32, 258, 1);
          goto LABEL_53;
        }
        v24 = a3 - v36;
        if ( a3 - v36 < 0x5DC )
          v24 = 1500;
        dwMilliseconds = v24;
      }
      if ( !v12 )
        goto LABEL_51;
      v17 = v50[1];
      v16 = nCount[1];
      v22 = this;
    }
  }
  v31 = v50[1];
  v32 = nCount[1];
LABEL_51:
  v9 = TcpConnection::CalculateReturnCode(v31, v32, 0xFFFFFFFFLL, 0);
LABEL_53:
  if ( v12 )
  {
    v37 = (TcpConnection **)v15;
    v38 = v12;
    v39 = v12;
    v40 = (char *)v11 - (char *)v15;
    do
    {
      TcpConnection::CloseOutstandingSocket(*v37);
      *(TcpConnection **)((char *)v37 + v40) = (TcpConnection *)*((_QWORD *)*v37 + 2);
      ++v37;
      --v39;
    }
    while ( v39 );
    v41 = WaitForMultipleObjects(v12, v11, 1, 0xFFFFFFFF);
    v15 = lpHandles[0];
    if ( v41 < v12 )
    {
      v42 = lpHandles[0];
      do
      {
        *((_BYTE *)*v42++ + 32) = 0;
        --v38;
      }
      while ( v38 );
      goto LABEL_66;
    }
    if ( v41 == -1 )
    {
      v43 = GetLastError();
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v46) = v43;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "ParallelConnectWaitSet::CloseConnections",
          4217,
          L"ERR|SNIWaitForMultipleObjects() extended error: %d{WINERR}\n",
          v46);
      }
      goto LABEL_66;
    }
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_66;
    _mm_lfence();
    LODWORD(v46) = v41;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "ParallelConnectWaitSet::CloseConnections",
      4221,
      L"ERR|SNIWaitForMultipleObjects(): %d{WINERR}\n",
      v46);
LABEL_65:
    v15 = lpHandles[0];
    v11 = lpHandles[1];
  }
LABEL_66:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v46) = v9;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "Tcp::SocketOpenParallel",
      6789,
      L"RET|SNI%d{WINERR}\n",
      v46);
  }
  *(_QWORD *)nCount = 0;
  if ( v11 )
  {
    operator delete[](v11);
    lpHandles[1] = 0;
  }
  if ( v15 )
  {
    operator delete[](v15);
    lpHandles[0] = 0;
  }
  if ( v50[1] )
  {
    p_ai_next = &v50[1][-1].ai_next;
    `eh vector destructor iterator'(
      v50[1],
      0x30u,
      (unsigned __int64)v50[1][-1].ai_next,
      (void (*)(void *))TcpConnection::~TcpConnection);
    operator delete[](p_ai_next, 48LL * *p_ai_next + 8);
    v50[1] = 0;
  }
  v50[0] = 0;
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::SocketOpenParallel", 6724, v10);
  return v9;
}

```

## disassembly

```asm
0x100438970  mov     [rsp-8+arg_18], r9
0x100438975  mov     [rsp-8+arg_10], r8d
0x10043897a  mov     [rsp-8+arg_0], rcx
0x10043897f  push    rbp
0x100438980  push    rbx
0x100438981  push    rsi
0x100438982  push    rdi
0x100438983  push    r12
0x100438985  push    r13
0x100438987  push    r14
0x100438989  push    r15
0x10043898b  lea     rbp, [rsp-1Fh]
0x100438990  sub     rsp, 0A8h
0x100438997  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x10043899f  mov     edi, r8d
0x1004389a2  mov     rbx, rdx
0x1004389a5  lea     rsi, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x1004389ac  mov     [rbp+57h+var_88], rsi
0x1004389b0  lea     rdx, aTcpSocketopenp; "Tcp::SocketOpenParallel"
0x1004389b7  mov     [rbp+57h+var_80], rdx
0x1004389bb  mov     [rbp+57h+var_78], 1A44h
0x1004389c2  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004389c9  jz      short loc_1004389F8
0x1004389cb  mov     [rsp+0E0h+var_A8], r8d
0x1004389d0  mov     eax, [rbx+4]
0x1004389d3  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1004389d7  mov     [rsp+0E0h+var_B8], rbx
0x1004389dc  mov     eax, [rcx+2Ch]
0x1004389df  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1004389e3  lea     r9, aApiSniUAiPAddr; "API|SNI%u#, AI: %p{ADDRINFO*}, ai_famil"...
0x1004389ea  mov     r8d, 1A44h; int
0x1004389f0  mov     rcx, rsi; char *
0x1004389f3  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004389f8  call    cs:__imp_GetTickCount
0x1004389fe  mov     [rbp+57h+var_A0], eax
0x100438a01  mov     [rbp+57h+dwMilliseconds], edi
0x100438a04  xorps   xmm0, xmm0
0x100438a07  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x100438a0c  xorps   xmm1, xmm1
0x100438a0f  movdqu  xmmword ptr [rbp+57h+lpHandles], xmm1
0x100438a14  xor     r14d, r14d
0x100438a17  mov     qword ptr [rbp+57h+nCount], r14
0x100438a1b  mov     edx, r14d
0x100438a1e  mov     rcx, rbx
0x100438a21  test    rbx, rbx
0x100438a24  jz      short loc_100438A43
0x100438a26  mov     eax, [rcx+4]
0x100438a29  cmp     eax, 2
0x100438a2c  jz      short loc_100438A33
0x100438a2e  cmp     eax, 17h
0x100438a31  jnz     short loc_100438A3A
0x100438a33  inc     edx; unsigned int
0x100438a35  cmp     edx, 40h ; '@'
0x100438a38  ja      short loc_100438A93
0x100438a3a  mov     rcx, [rcx+28h]
0x100438a3e  test    rcx, rcx
0x100438a41  jnz     short loc_100438A26
0x100438a43  mov     [rbp+57h+var_70], rbx
0x100438a47  lea     rcx, [rbp+57h+var_70]; this
0x100438a4b  call    ?SetSize@ParallelConnectWaitSet@@AEAAKK@Z; ParallelConnectWaitSet::SetSize(ulong)
0x100438a50  mov     esi, eax
0x100438a52  mov     r15, [rbp+57h+lpHandles+8]
0x100438a56  mov     ebx, [rbp+57h+nCount]
0x100438a59  test    eax, eax
0x100438a5b  jnz     loc_100438D39
0x100438a61  mov     rdi, [rbp+57h+var_70]
0x100438a65  mov     r12d, r14d
0x100438a68  mov     r14, [rbp+57h+lpHandles]
0x100438a6c  mov     esi, [rbp+57h+nCount+4]
0x100438a6f  mov     r13, [rbp+57h+var_70+8]
0x100438a73  test    esi, esi
0x100438a75  jz      loc_100438B65
0x100438a7b  nop     dword ptr [rax+rax+00h]
0x100438a80  mov     eax, [rdi+4]
0x100438a83  cmp     eax, 2
0x100438a86  jz      short loc_100438AEF
0x100438a88  cmp     eax, 17h
0x100438a8b  jz      short loc_100438AEF
0x100438a8d  mov     rdi, [rdi+28h]
0x100438a91  jmp     short loc_100438A80
0x100438a93  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100438a9a  jz      short loc_100438AD0
0x100438a9c  mov     dword ptr [rsp+0E0h+var_B0], 0FFFFFFFFh
0x100438aa4  mov     dword ptr [rsp+0E0h+var_B8], 2Fh ; '/'
0x100438aac  mov     dword ptr [rsp+0E0h+var_C0], 7
0x100438ab4  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100438abb  mov     r8d, 0FCEh; int
0x100438ac1  lea     rdx, aParallelconnec; "ParallelConnectWaitSet::Initialize"
0x100438ac8  mov     rcx, rsi; char *
0x100438acb  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100438ad0  mov     edx, 0FFFFFFFFh
0x100438ad5  mov     ecx, 7
0x100438ada  mov     r8d, 0C3E3h
0x100438ae0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100438ae5  mov     esi, 0FFFFFFFFh
0x100438aea  jmp     loc_100438E1D
0x100438aef  mov     eax, r12d
0x100438af2  mov     [rbp+57h+var_98], rax
0x100438af6  lea     rsi, [rax+rax*2]
0x100438afa  shl     rsi, 4
0x100438afe  add     rsi, r13
0x100438b01  mov     r9, [rbp+57h+arg_18]; struct ProtElem *
0x100438b05  mov     r8, rdi; struct addrinfoW *
0x100438b08  mov     rdx, [rbp+57h+arg_0]; struct Tcp *
0x100438b0c  mov     rcx, rsi; this
0x100438b0f  call    ?FInit@TcpConnection@@QEAAKPEBVTcp@@PEBUaddrinfoW@@PEBVProtElem@@@Z; TcpConnection::FInit(Tcp const *,addrinfoW const *,ProtElem const *)
0x100438b14  test    eax, eax
0x100438b16  jnz     short loc_100438B52
0x100438b18  mov     rcx, rsi; this
0x100438b1b  call    ?FInitForAsync@TcpConnection@@QEAAKXZ; TcpConnection::FInitForAsync(void)
0x100438b20  test    eax, eax
0x100438b22  jnz     short loc_100438B52
0x100438b24  mov     rcx, rsi; this
0x100438b27  call    ?AsyncOpen@TcpConnection@@QEAAKXZ; TcpConnection::AsyncOpen(void)
0x100438b2c  test    eax, eax
0x100438b2e  jz      short loc_100438B74
0x100438b30  cmp     eax, 3E5h
0x100438b35  jnz     short loc_100438B52
0x100438b37  mov     eax, ebx
0x100438b39  lea     rcx, ds:0[rax*8]
0x100438b41  mov     [rcx+r14], rsi
0x100438b45  mov     rax, [rsi+10h]
0x100438b49  mov     [rcx+r15], rax
0x100438b4d  inc     ebx
0x100438b4f  mov     [rbp+57h+nCount], ebx
0x100438b52  mov     rdi, [rdi+28h]
0x100438b56  inc     r12d
0x100438b59  mov     esi, [rbp+57h+nCount+4]
0x100438b5c  cmp     r12d, esi
0x100438b5f  jb      loc_100438A80
0x100438b65  mov     r12, [rbp+57h+arg_0]
0x100438b69  mov     qword ptr [r12+40h], 0FFFFFFFFFFFFFFFFh
0x100438b72  jmp     short loc_100438BA6
0x100438b74  mov     rax, [rbp+57h+var_98]
0x100438b78  lea     rcx, [rax+rax*2]
0x100438b7c  add     rcx, rcx
0x100438b7f  mov     rax, [r13+rcx*8+18h]
0x100438b84  mov     qword ptr [r13+rcx*8+18h], 0FFFFFFFFFFFFFFFFh
0x100438b8d  mov     r12, [rbp+57h+arg_0]
0x100438b91  mov     [r12+40h], rax
0x100438b96  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100438b9a  jz      short loc_100438BA3
0x100438b9c  xor     esi, esi
0x100438b9e  jmp     loc_100438D3D
0x100438ba3  mov     esi, [rbp+57h+nCount+4]
0x100438ba6  test    ebx, ebx
0x100438ba8  jz      loc_100438D19
0x100438bae  mov     ecx, [rbp+57h+dwMilliseconds]
0x100438bb1  mov     r9d, ecx; dwMilliseconds
0x100438bb4  xor     r8d, r8d; bWaitAll
0x100438bb7  mov     rdx, r15; lpHandles
0x100438bba  mov     ecx, ebx; nCount
0x100438bbc  call    cs:__imp_WaitForMultipleObjects
0x100438bc2  cmp     eax, ebx
0x100438bc4  jnb     loc_100438C44
0x100438bca  lfence
0x100438bcd  mov     ecx, eax
0x100438bcf  mov     r14, [rbp+57h+lpHandles]
0x100438bd3  mov     rdi, [r14+rcx*8]
0x100438bd7  lea     r8d, [rax+1]
0x100438bdb  mov     r15, [rbp+57h+lpHandles+8]
0x100438bdf  mov     ebx, [rbp+57h+nCount]
0x100438be2  cmp     r8d, ebx
0x100438be5  jnb     short loc_100438C14
0x100438be7  nop     word ptr [rax+rax+00000000h]
0x100438bf0  lea     rdx, ds:0[r8*8]
0x100438bf8  lea     ecx, [r8-1]
0x100438bfc  mov     rax, [r14+rdx]
0x100438c00  mov     [r14+rcx*8], rax
0x100438c04  mov     rax, [r15+rdx]
0x100438c08  mov     [r15+rcx*8], rax
0x100438c0c  inc     r8d
0x100438c0f  cmp     r8d, ebx
0x100438c12  jb      short loc_100438BF0
0x100438c14  dec     ebx
0x100438c16  mov     [rbp+57h+nCount], ebx
0x100438c19  mov     byte ptr [rdi+20h], 0
0x100438c1d  mov     rcx, rdi; this
0x100438c20  call    ?CheckCompletedAsyncConnect@TcpConnection@@QEAAKXZ; TcpConnection::CheckCompletedAsyncConnect(void)
0x100438c25  test    eax, eax
0x100438c27  jnz     short loc_100438C3A
0x100438c29  mov     rax, [rdi+18h]
0x100438c2d  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x100438c35  mov     [r12+40h], rax
0x100438c3a  mov     rdi, [rbp+57h+var_70+8]
0x100438c3e  mov     r12d, [rbp+57h+nCount+4]
0x100438c42  jmp     short loc_100438CAE
0x100438c44  cmp     eax, 0FFFFFFFFh
0x100438c47  jnz     short loc_100438C6C
0x100438c49  call    cs:__imp_GetLastError
0x100438c4f  mov     r9d, 4
0x100438c55  mov     r8d, eax
0x100438c58  mov     edx, esi
0x100438c5a  mov     rcx, r13
0x100438c5d  call    ?CalculateReturnCode@TcpConnection@@SAKPEAV1@KKW4TcpConnectionErrorLevel@@@Z; TcpConnection::CalculateReturnCode(TcpConnection *,ulong,ulong,TcpConnectionErrorLevel)
0x100438c62  mov     rdi, [rbp+57h+var_70+8]
0x100438c66  mov     r12d, [rbp+57h+nCount+4]
0x100438c6a  jmp     short loc_100438CA4
0x100438c6c  lfence
0x100438c6f  mov     r9d, 4
0x100438c75  cmp     eax, 102h
0x100438c7a  mov     ecx, 1
0x100438c7f  cmovz   r9d, ecx
0x100438c83  mov     r8d, eax
0x100438c86  mov     r12d, [rbp+57h+nCount+4]
0x100438c8a  mov     edx, r12d
0x100438c8d  mov     rdi, [rbp+57h+var_70+8]
0x100438c91  mov     rcx, rdi
0x100438c94  call    ?CalculateReturnCode@TcpConnection@@SAKPEAV1@KKW4TcpConnectionErrorLevel@@@Z; TcpConnection::CalculateReturnCode(TcpConnection *,ulong,ulong,TcpConnectionErrorLevel)
0x100438c99  mov     ebx, [rbp+57h+nCount]
0x100438c9c  mov     r15, [rbp+57h+lpHandles+8]
0x100438ca0  mov     r14, [rbp+57h+lpHandles]
0x100438ca4  mov     esi, eax
0x100438ca6  test    eax, eax
0x100438ca8  jnz     loc_100438D3D
0x100438cae  mov     rax, [rbp+57h+arg_0]
0x100438cb2  cmp     qword ptr [rax+40h], 0FFFFFFFFFFFFFFFFh
0x100438cb7  jnz     loc_100438B9C
0x100438cbd  mov     esi, [rbp+57h+arg_10]
0x100438cc0  cmp     esi, 0FFFFFFFFh
0x100438cc3  jz      short loc_100438D02
0x100438cc5  call    cs:__imp_GetTickCount
0x100438ccb  sub     eax, [rbp+57h+var_A0]
0x100438cce  cmp     esi, eax
0x100438cd0  jb      short loc_100438CE7
0x100438cd2  mov     ecx, esi
0x100438cd4  sub     ecx, eax
0x100438cd6  mov     eax, 5DCh
0x100438cdb  cmp     ecx, eax
0x100438cdd  cmovb   ecx, eax
0x100438ce0  mov     [rbp+57h+dwMilliseconds], ecx
0x100438ce3  test    ecx, ecx
0x100438ce5  jnz     short loc_100438D05
0x100438ce7  mov     r9d, 1
0x100438ced  mov     r8d, 102h
0x100438cf3  mov     edx, r12d
0x100438cf6  mov     rcx, rdi
0x100438cf9  call    ?CalculateReturnCode@TcpConnection@@SAKPEAV1@KKW4TcpConnectionErrorLevel@@@Z; TcpConnection::CalculateReturnCode(TcpConnection *,ulong,ulong,TcpConnectionErrorLevel)
0x100438cfe  mov     esi, eax
0x100438d00  jmp     short loc_100438D3D
0x100438d02  mov     ecx, [rbp+57h+dwMilliseconds]
0x100438d05  test    ebx, ebx
0x100438d07  jz      short loc_100438D21
0x100438d09  mov     r13, [rbp+57h+var_70+8]
0x100438d0d  mov     esi, [rbp+57h+nCount+4]
0x100438d10  mov     r12, [rbp+57h+arg_0]
0x100438d14  jmp     loc_100438BB1
0x100438d19  mov     rdi, [rbp+57h+var_70+8]
0x100438d1d  mov     r12d, [rbp+57h+nCount+4]
0x100438d21  xor     r9d, r9d
0x100438d24  mov     r8d, 0FFFFFFFFh
0x100438d2a  mov     edx, r12d
0x100438d2d  mov     rcx, rdi
0x100438d30  call    ?CalculateReturnCode@TcpConnection@@SAKPEAV1@KKW4TcpConnectionErrorLevel@@@Z; TcpConnection::CalculateReturnCode(TcpConnection *,ulong,ulong,TcpConnectionErrorLevel)
0x100438d35  mov     esi, eax
0x100438d37  jmp     short loc_100438D3D
0x100438d39  mov     r14, [rbp+57h+lpHandles]
0x100438d3d  test    ebx, ebx
0x100438d3f  jz      loc_100438E25
0x100438d45  mov     rdi, r14
0x100438d48  mov     rax, r15
0x100438d4b  sub     rax, r14
0x100438d4e  mov     r12d, ebx
0x100438d51  mov     r13d, ebx
0x100438d54  mov     r14, rax
0x100438d57  mov     rcx, [rdi]; this
0x100438d5a  call    ?CloseOutstandingSocket@TcpConnection@@QEAAKXZ; TcpConnection::CloseOutstandingSocket(void)
0x100438d5f  mov     rax, [rdi]
0x100438d62  mov     rcx, [rax+10h]
0x100438d66  mov     [r14+rdi], rcx
0x100438d6a  lea     rdi, [rdi+8]
0x100438d6e  sub     r13, 1
0x100438d72  jnz     short loc_100438D57
0x100438d74  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x100438d7a  lea     r8d, [r13+1]; bWaitAll
0x100438d7e  mov     rdx, r15; lpHandles
0x100438d81  mov     ecx, ebx; nCount
0x100438d83  call    cs:__imp_WaitForMultipleObjects
0x100438d89  cmp     eax, ebx
0x100438d8b  mov     r14, [rbp+57h+lpHandles]
0x100438d8f  jnb     short loc_100438DB3
0x100438d91  mov     rcx, r14
0x100438d94  nop     dword ptr [rax+00h]
0x100438d98  nop     dword ptr [rax+rax+00000000h]
0x100438da0  mov     rax, [rcx]
0x100438da3  mov     byte ptr [rax+20h], 0
0x100438da7  lea     rcx, [rcx+8]
0x100438dab  sub     r12, 1
0x100438daf  jnz     short loc_100438DA0
0x100438db1  jmp     short loc_100438E25
0x100438db3  cmp     eax, 0FFFFFFFFh
0x100438db6  jnz     short loc_100438DED
0x100438db8  call    cs:__imp_GetLastError
0x100438dbe  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100438dc5  jz      short loc_100438E25
0x100438dc7  mov     dword ptr [rsp+0E0h+var_C0], eax
0x100438dcb  lea     r9, aErrSniwaitform_0; "ERR|SNIWaitForMultipleObjects() extende"...
0x100438dd2  mov     r8d, 1079h; int
0x100438dd8  lea     rdx, aParallelconnec_0; "ParallelConnectWaitSet::CloseConnection"...
0x100438ddf  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
  ... truncated ...
```
