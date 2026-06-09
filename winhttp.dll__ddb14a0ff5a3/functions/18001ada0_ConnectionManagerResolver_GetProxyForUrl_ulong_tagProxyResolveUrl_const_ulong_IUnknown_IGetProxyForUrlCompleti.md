# ConnectionManagerResolver::GetProxyForUrl(ulong,tagProxyResolveUrl const *,ulong *,IUnknown *,IGetProxyForUrlCompletion *,IProxyResult * *)

- ea: `0x18001ada0`
- end: `0x18001b43b`
- name: `?GetProxyForUrl@ConnectionManagerResolver@@UEAAJKPEBUtagProxyResolveUrl@@PEAKPEAUIUnknown@@PEAUIGetProxyForUrlCompletion@@PEAPEAUIProxyResult@@@Z`
- size: `1691`
- prototype: `int(ConnectionManagerResolver *__hidden this, unsigned int, const struct tagProxyResolveUrl *, unsigned int *, struct IUnknown *, struct IGetProxyForUrlCompletion *, struct IProxyResult **)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180008030`
- `0x18001ada0`
- `0x18001b480`
- `0x18007947c`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800bee58`
- `0x1800bf1a0`
- `0x1800c8a50`
- `0x1800d0220`
- `0x1800d7760`
- `0x1800d7840`
- `0x1800d7bc8`
- `0x1800d8018`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800db758`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b3f9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b3f9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b002`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b002`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001afec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001afec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001aeea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b011`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001aeea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b05d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b05d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b404`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b412`
- `DNSAPI!DnsConnectionFreeProxyInfoEx` at `0x18001aed9`
- `DNSAPI!DnsConnectionFreeProxyInfoEx` at `0x18001aed9`
- `DNSAPI!DnsConnectionGetProxyInfoForHostUrlEx` at `0x18001ae99`
- `DNSAPI!DnsConnectionGetProxyInfoForHostUrlEx` at `0x18001ae99`

## pseudocode

```c
__int64 __fastcall ConnectionManagerResolver::GetProxyForUrl(
        ConnectionManagerResolver *this,
        unsigned int a2,
        const struct tagProxyResolveUrl *a3,
        unsigned int *a4,
        struct IUnknown *a5,
        struct IGetProxyForUrlCompletion *a6,
        struct IProxyResult **a7)
{
  int v7; // r13d
  struct tagProxyResolveUrl *v10; // rsi
  __int64 v11; // r14
  int v12; // edx
  int v13; // ecx
  int v14; // r8d
  unsigned int v15; // ebx
  struct CWxString *v16; // r15
  __int64 v17; // r13
  unsigned int v18; // r12d
  struct tagProxyResolveUrl *v19; // r15
  int ProxyInfoForHostUrl; // eax
  int v21; // edx
  int v22; // ecx
  int v23; // r8d
  signed int LastError; // ebx
  unsigned int v25; // edi
  HANDLE hConnection; // rax
  HANDLE CurrentThread; // rax
  __int64 v29; // rcx
  bool v30; // sf
  __int64 v31; // rax
  int v32; // edx
  int v33; // ecx
  int v34; // r8d
  int ProxyResultFromProxyString; // eax
  int v36; // edx
  int v37; // ecx
  int v38; // r8d
  int v39; // eax
  int v40; // ebx
  struct CWxString *v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+54h] [rbp-ACh]
  unsigned int v44; // [rsp+58h] [rbp-A8h]
  struct tagProxyResolveUrl *v45; // [rsp+60h] [rbp-A0h] BYREF
  ConnectionManagerResolver *v46; // [rsp+68h] [rbp-98h]
  unsigned int v47; // [rsp+70h] [rbp-90h]
  _QWORD v48[2]; // [rsp+78h] [rbp-88h] BYREF
  struct IGetProxyForUrlCompletion *v49; // [rsp+88h] [rbp-78h]
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  DNS_CONNECTION_PROXY_INFO_EX pProxyInfoEx; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v53; // [rsp+118h] [rbp+18h] BYREF
  __int64 v54; // [rsp+120h] [rbp+20h]
  unsigned __int16 *v55; // [rsp+128h] [rbp+28h] BYREF
  __int64 v56; // [rsp+130h] [rbp+30h]
  __int64 v57[2]; // [rsp+138h] [rbp+38h] BYREF

  v7 = (int)this;
  v46 = this;
  v49 = a6;
  v10 = (struct tagProxyResolveUrl *)qword_1800E7D10;
  v47 = a2;
  v57[0] = (__int64)qword_1800E7D10;
  v55 = (unsigned __int16 *)qword_1800E7D10;
  v11 = 0;
  v53 = (unsigned __int16 *)qword_1800E7D10;
  v48[0] = qword_1800E7D10;
  v45 = a3;
  v43 = 0;
  v57[1] = 0;
  v56 = 0;
  v54 = 0;
  v48[1] = 0;
  memset_0(&pProxyInfoEx, 0, sizeof(pProxyInfoEx));
  v52 = 0;
  v42 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qdSqqq(v13, v12, v14, v7, v47, *(_QWORD *)a3, (__int64)a5, (__int64)v49, (__int64)a7);
  if ( a7 )
    *a7 = 0;
  if ( !a4 )
    goto LABEL_6;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 43, WPP_52b9ef2e0ce03807e04b532c07148c79_Traceguids);
  TokenHandle = (void *)-1LL;
  v11 = -1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_60;
    TokenHandle = 0;
  }
  if ( SetThreadToken(0, a4) )
  {
    v11 = (__int64)TokenHandle;
    v29 = -1;
    TokenHandle = (void *)-1LL;
    LastError = 0;
    goto LABEL_41;
  }
  LastError = GetLastError();
LABEL_60:
  v29 = (__int64)TokenHandle;
LABEL_41:
  if ( v29 != -1 )
    CloseHandle((HANDLE)v29);
  v30 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v30 = LastError < 0;
  }
  if ( v30 )
  {
    v43 = 1246;
    v25 = LastError;
    goto LABEL_13;
  }
LABEL_6:
  v15 = 0;
  v16 = 0;
  v17 = 0;
  if ( a5
    && ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a5->lpVtbl->QueryInterface)(
         a5,
         &IID_IConnectionSelectionContextEx,
         &v52) >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 24LL))(v52);
    v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 48LL))(v52);
    v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 40LL))(v52);
    v16 = (struct CWxString *)v31;
    v18 = v44;
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_qDSD(v33, v32, v34, v17, v44, v31, v15);
  }
  else
  {
    v18 = 0;
  }
  v41 = v16;
  v19 = v45;
  ProxyInfoForHostUrl = DnsConnectionGetProxyInfoForHostUrlEx(*((_QWORD *)v45 + 1), v17, v18, v15);
  LastError = ProxyInfoForHostUrl;
  if ( ProxyInfoForHostUrl > 0 )
    LastError = (unsigned __int16)ProxyInfoForHostUrl | 0x80070000;
  if ( LastError < 0 )
  {
    v43 = 1272;
LABEL_12:
    v7 = (int)v46;
    v25 = LastError;
    goto LABEL_13;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_DSlq(
      v22,
      v21,
      v23,
      pProxyInfoEx.dwInterfaceIndex,
      (__int64)pProxyInfoEx.pwszConnectionName,
      pProxyInfoEx.fDirectConfiguration,
      (__int64)pProxyInfoEx.hConnection);
  if ( pProxyInfoEx.fDirectConfiguration )
    goto LABEL_55;
  LastError = WxGetProxyForProxyInfo(
                &pProxyInfoEx.ProxyInfo,
                (enum WX_CONNECTION_PROXY_INFO_SWITCH *)&v42,
                (struct CWxString *)v57,
                (struct CWxString *)&v55,
                (struct CWxString *)&v53);
  if ( LastError < 0 )
  {
    v43 = 1288;
    goto LABEL_12;
  }
  v39 = 0;
  if ( LastError == 1 )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_DS(
        v37,
        46,
        (unsigned int)WPP_52b9ef2e0ce03807e04b532c07148c79_Traceguids,
        pProxyInfoEx.dwInterfaceIndex,
        (__int64)pProxyInfoEx.pwszConnectionName);
    v39 = 1;
  }
  if ( pProxyInfoEx.fDirectConfiguration || v39 )
  {
LABEL_55:
    ProxyResultFromProxyString = CWxString::Append((CWxString *)v48, L"DIRECT");
    v7 = (int)v46;
    LastError = ProxyResultFromProxyString;
    if ( ProxyResultFromProxyString < 0 )
    {
      v43 = 1308;
    }
    else
    {
      LODWORD(v41) = pProxyInfoEx.dwInterfaceIndex;
      ProxyResultFromProxyString = ConnectionManagerResolver::GetProxyResultFromProxyString(
                                     v46,
                                     v48,
                                     *((unsigned int *)v19 + 6),
                                     pProxyInfoEx.pwszConnectionName);
      LastError = ProxyResultFromProxyString;
      if ( ProxyResultFromProxyString >= 0 )
      {
        v10 = (struct tagProxyResolveUrl *)v48[0];
        goto LABEL_58;
      }
      v43 = 1316;
    }
    v10 = (struct tagProxyResolveUrl *)v48[0];
    goto LABEL_84;
  }
  v40 = v42;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_SDSSS(v37, v36, v38, pProxyInfoEx.pwszConnectionName, v42, v57[0], (__int64)v55, (__int64)v53);
  v7 = (int)v46;
  if ( v40 )
  {
    if ( (v47 & 2) != 0 )
    {
      LastError = -2147023728;
      v43 = 1345;
    }
    else
    {
      LODWORD(v41) = v40;
      ProxyResultFromProxyString = ConnectionManagerResolver::GetAutoProxyResults(
                                     v46,
                                     v47,
                                     v19,
                                     pProxyInfoEx.pwszConnectionName);
      v25 = 787429;
      LastError = ProxyResultFromProxyString;
      if ( ProxyResultFromProxyString == 787429 )
        goto LABEL_14;
      if ( ProxyResultFromProxyString < 0 )
      {
        v43 = 1358;
        goto LABEL_84;
      }
      LastError = -2147418113;
      v43 = 1359;
    }
    v25 = LastError;
    goto LABEL_13;
  }
  ProxyResultFromProxyString = ConnectionManagerResolver::GetStaticProxyForConnection(
                                 v46,
                                 v19,
                                 v55,
                                 v53,
                                 pProxyInfoEx.pwszConnectionName,
                                 pProxyInfoEx.dwInterfaceIndex,
                                 pProxyInfoEx.hConnection,
                                 a7);
  LastError = ProxyResultFromProxyString;
  if ( ProxyResultFromProxyString >= 0 )
  {
LABEL_58:
    v25 = 0;
    LastError = 0;
    goto LABEL_14;
  }
  v43 = 1337;
LABEL_84:
  v25 = ProxyResultFromProxyString;
LABEL_13:
  hConnection = pProxyInfoEx.hConnection;
  if ( pProxyInfoEx.hConnection )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
    {
      WPP_SF_qqD(
        1029,
        48,
        (unsigned int)WPP_52b9ef2e0ce03807e04b532c07148c79_Traceguids,
        v7,
        (__int64)pProxyInfoEx.hConnection);
      hConnection = pProxyInfoEx.hConnection;
    }
    SetEvent(hConnection);
  }
LABEL_14:
  DnsConnectionFreeProxyInfoEx(&pProxyInfoEx);
  if ( v11 != -1 )
  {
    if ( !SetThreadToken(0, (HANDLE)v11) )
      GetLastError();
    if ( v11 )
      CloseHandle((HANDLE)v11);
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 49, WPP_52b9ef2e0ce03807e04b532c07148c79_Traceguids, (unsigned int)LastError, v41);
  if ( v52 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v52 = 0;
  }
  v45 = v10;
  if ( v10 != (struct tagProxyResolveUrl *)qword_1800E7D10 && v10 )
    WxFreeHeapEx(&v45);
  v45 = (struct tagProxyResolveUrl *)v53;
  if ( v53 != (unsigned __int16 *)qword_1800E7D10 && v53 )
    WxFreeHeapEx(&v45);
  v53 = (unsigned __int16 *)qword_1800E7D10;
  v54 = 0;
  v45 = (struct tagProxyResolveUrl *)v55;
  if ( v55 != (unsigned __int16 *)qword_1800E7D10 && v55 )
    WxFreeHeapEx(&v45);
  v55 = (unsigned __int16 *)qword_1800E7D10;
  v56 = 0;
  v45 = (struct tagProxyResolveUrl *)v57[0];
  if ( (__int64 *)v57[0] != qword_1800E7D10 && v57[0] )
    WxFreeHeapEx(&v45);
  return v25;
}

```

## disassembly

```asm
0x18001ada0  push    rbp
0x18001ada2  push    rbx
0x18001ada3  push    rsi
0x18001ada4  push    rdi
0x18001ada5  push    r12
0x18001ada7  push    r13
0x18001ada9  push    r14
0x18001adab  push    r15
0x18001adad  lea     rbp, [rsp-58h]
0x18001adb2  sub     rsp, 158h
0x18001adb9  mov     rax, cs:__security_cookie
0x18001adc0  xor     rax, rsp
0x18001adc3  mov     [rbp+90h+var_48], rax
0x18001adc7  mov     rax, [rbp+90h+arg_28]
0x18001adce  mov     r13, rcx
0x18001add1  mov     r12, [rbp+90h+arg_20]
0x18001add8  mov     rbx, r8
0x18001addb  mov     rdi, [rbp+90h+arg_30]
0x18001ade2  mov     r15, r9
0x18001ade5  mov     [rsp+190h+var_128], rcx
0x18001adea  lea     rcx, qword_1800E7D10
0x18001adf1  mov     [rbp+90h+var_108], rax
0x18001adf5  mov     rsi, rcx
0x18001adf8  xor     eax, eax
0x18001adfa  mov     [rsp+190h+var_120], edx
0x18001adfe  mov     [rbp+90h+var_58], rcx
0x18001ae02  xor     edx, edx; Val
0x18001ae04  mov     [rbp+90h+var_68], rcx
0x18001ae08  mov     r14d, eax
0x18001ae0b  mov     [rbp+90h+var_78], rcx
0x18001ae0f  mov     [rsp+190h+var_118], rcx
0x18001ae14  lea     r8d, [rax+68h]; Size
0x18001ae18  lea     rcx, [rbp+90h+pProxyInfoEx]; void *
0x18001ae1c  mov     [rsp+190h+var_130], rbx
0x18001ae21  mov     [rsp+190h+var_13C], eax
0x18001ae25  mov     [rbp+90h+var_50], rax
0x18001ae29  mov     [rbp+90h+var_60], rax
0x18001ae2d  mov     [rbp+90h+var_70], rax
0x18001ae31  mov     [rbp+90h+var_110], rax
0x18001ae35  call    memset_0
0x18001ae3a  mov     [rbp+90h+var_80], r14
0x18001ae3e  mov     [rsp+190h+var_140], r14d
0x18001ae43  test    byte ptr cs:xmmword_180107A60, 20h
0x18001ae4a  jnz     loc_18001B1BA
0x18001ae50  test    rdi, rdi
0x18001ae53  jz      short loc_18001AE58
0x18001ae55  mov     [rdi], r14
0x18001ae58  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ae5c  test    r15, r15
0x18001ae5f  jnz     loc_18001AFD8
0x18001ae65  xor     ebx, ebx
0x18001ae67  xor     r15d, r15d
0x18001ae6a  xor     r13d, r13d
0x18001ae6d  test    r12, r12
0x18001ae70  jnz     loc_18001B07E
0x18001ae76  mov     r12d, ebx
0x18001ae79  lea     rax, [rbp+90h+pProxyInfoEx]
0x18001ae7d  mov     r9d, ebx
0x18001ae80  mov     qword ptr [rsp+190h+var_168], rax
0x18001ae85  mov     r8d, r12d
0x18001ae88  mov     [rsp+190h+var_170], r15
0x18001ae8d  mov     rdx, r13
0x18001ae90  mov     r15, [rsp+190h+var_130]
0x18001ae95  mov     rcx, [r15+8]
0x18001ae99  call    cs:__imp_DnsConnectionGetProxyInfoForHostUrlEx
0x18001ae9f  xor     r12d, r12d
0x18001aea2  mov     ebx, eax
0x18001aea4  test    eax, eax
0x18001aea6  jle     short loc_18001AEB1
0x18001aea8  movzx   ebx, ax
0x18001aeab  or      ebx, 80070000h
0x18001aeb1  test    ebx, ebx
0x18001aeb3  jns     loc_18001B119
0x18001aeb9  mov     [rsp+190h+var_13C], 4F8h
0x18001aec1  mov     r13, [rsp+190h+var_128]
0x18001aec6  mov     edi, ebx
0x18001aec8  mov     rax, [rbp+90h+pProxyInfoEx.hConnection]
0x18001aecc  test    rax, rax
0x18001aecf  jnz     loc_18001B3C7
0x18001aed5  lea     rcx, [rbp+90h+pProxyInfoEx]; pProxyInfoEx
0x18001aed9  call    cs:__imp_DnsConnectionFreeProxyInfoEx
0x18001aedf  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001aee3  jz      short loc_18001AF01
0x18001aee5  mov     rdx, r14; Token
0x18001aee8  xor     ecx, ecx; Thread
0x18001aeea  call    cs:__imp_SetThreadToken
0x18001aef0  test    eax, eax
0x18001aef2  jz      loc_18001B404
0x18001aef8  test    r14, r14
0x18001aefb  jnz     loc_18001B40F
0x18001af01  test    byte ptr cs:xmmword_180107A60, 20h
0x18001af08  jnz     loc_18001B41D
0x18001af0e  mov     rcx, [rbp+90h+var_80]
0x18001af12  test    rcx, rcx
0x18001af15  jz      short loc_18001AF27
0x18001af17  mov     rax, [rcx]
0x18001af1a  mov     rax, [rax+10h]
0x18001af1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af23  mov     [rbp+90h+var_80], r12
0x18001af27  lea     rbx, qword_1800E7D10
0x18001af2e  mov     [rsp+190h+var_130], rsi
0x18001af33  cmp     rsi, rbx
0x18001af36  jnz     short loc_18001AF94
0x18001af38  mov     rax, [rbp+90h+var_78]
0x18001af3c  mov     [rsp+190h+var_130], rax
0x18001af41  cmp     rax, rbx
0x18001af44  jnz     short loc_18001AFA5
0x18001af46  mov     rax, [rbp+90h+var_68]
0x18001af4a  mov     [rbp+90h+var_78], rbx
0x18001af4e  mov     [rbp+90h+var_70], r12
0x18001af52  mov     [rsp+190h+var_130], rax
0x18001af57  cmp     rax, rbx
0x18001af5a  jnz     short loc_18001AFB6
0x18001af5c  mov     rax, [rbp+90h+var_58]
0x18001af60  mov     [rbp+90h+var_68], rbx
0x18001af64  mov     [rbp+90h+var_60], r12
0x18001af68  mov     [rsp+190h+var_130], rax
0x18001af6d  cmp     rax, rbx
0x18001af70  jnz     short loc_18001AFC7
0x18001af72  mov     eax, edi
0x18001af74  mov     rcx, [rbp+90h+var_48]
0x18001af78  xor     rcx, rsp; StackCookie
0x18001af7b  call    __security_check_cookie
0x18001af80  add     rsp, 158h
0x18001af87  pop     r15
0x18001af89  pop     r14
0x18001af8b  pop     r13
0x18001af8d  pop     r12
0x18001af8f  pop     rdi
0x18001af90  pop     rsi
0x18001af91  pop     rbx
0x18001af92  pop     rbp
0x18001af93  retn
0x18001af94  test    rsi, rsi
0x18001af97  jz      short loc_18001AF38
0x18001af99  lea     rcx, [rsp+190h+var_130]
0x18001af9e  call    WxFreeHeapEx
0x18001afa3  jmp     short loc_18001AF38
0x18001afa5  test    rax, rax
0x18001afa8  jz      short loc_18001AF46
0x18001afaa  lea     rcx, [rsp+190h+var_130]
0x18001afaf  call    WxFreeHeapEx
0x18001afb4  jmp     short loc_18001AF46
0x18001afb6  test    rax, rax
0x18001afb9  jz      short loc_18001AF5C
0x18001afbb  lea     rcx, [rsp+190h+var_130]
0x18001afc0  call    WxFreeHeapEx
0x18001afc5  jmp     short loc_18001AF5C
0x18001afc7  test    rax, rax
0x18001afca  jz      short loc_18001AF72
0x18001afcc  lea     rcx, [rsp+190h+var_130]
0x18001afd1  call    WxFreeHeapEx
0x18001afd6  jmp     short loc_18001AF72
0x18001afd8  test    byte ptr cs:xmmword_180107A60, 20h
0x18001afdf  jnz     loc_18001B19C
0x18001afe5  mov     [rbp+90h+TokenHandle], rbx
0x18001afe9  mov     r14, rbx
0x18001afec  call    cs:__imp_GetCurrentThread
0x18001aff2  mov     edx, 4; DesiredAccess
0x18001aff7  lea     r9, [rbp+90h+TokenHandle]; TokenHandle
0x18001affb  mov     rcx, rax; ThreadHandle
0x18001affe  lea     r8d, [rdx-3]; OpenAsSelf
0x18001b002  call    cs:__imp_OpenThreadToken
0x18001b008  test    eax, eax
0x18001b00a  jz      short loc_18001B05D
0x18001b00c  mov     rdx, r15; Token
0x18001b00f  xor     ecx, ecx; Thread
0x18001b011  call    cs:__imp_SetThreadToken
0x18001b017  test    eax, eax
0x18001b019  jz      loc_18001B1EA
0x18001b01f  mov     r14, [rbp+90h+TokenHandle]
0x18001b023  mov     rcx, rbx; hObject
0x18001b026  mov     [rbp+90h+TokenHandle], rbx
0x18001b02a  xor     ebx, ebx
0x18001b02c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b030  jnz     loc_18001B1FB
0x18001b036  test    ebx, ebx
0x18001b038  jle     short loc_18001B045
0x18001b03a  movzx   ebx, bx
0x18001b03d  or      ebx, 80070000h
0x18001b043  test    ebx, ebx
0x18001b045  jns     loc_18001AE65
0x18001b04b  mov     [rsp+190h+var_13C], 4DEh
0x18001b053  mov     edi, ebx
0x18001b055  xor     r12d, r12d
0x18001b058  jmp     loc_18001AEC8
0x18001b05d  call    cs:__imp_GetLastError
0x18001b063  mov     ebx, eax
0x18001b065  cmp     eax, 3F0h
0x18001b06a  jnz     loc_18001B1F2
0x18001b070  mov     [rbp+90h+TokenHandle], 0
0x18001b078  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b07c  jmp     short loc_18001B00C
0x18001b07e  mov     rax, [r12]
0x18001b082  lea     r8, [rbp+90h+var_80]
0x18001b086  lea     rdx, ?IID_IConnectionSelectionContextEx@@3U_GUID@@B; _GUID const IID_IConnectionSelectionContextEx
0x18001b08d  mov     rcx, r12
0x18001b090  mov     rax, [rax]
0x18001b093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b098  test    eax, eax
0x18001b09a  js      loc_18001AE76
0x18001b0a0  mov     rcx, [rbp+90h+var_80]
0x18001b0a4  mov     rax, [rcx]
0x18001b0a7  mov     rax, [rax+18h]
0x18001b0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0b0  mov     rcx, [rbp+90h+var_80]
0x18001b0b4  mov     r13, rax
0x18001b0b7  mov     rdx, [rcx]
0x18001b0ba  mov     rax, [rdx+20h]
0x18001b0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0c3  mov     rcx, [rbp+90h+var_80]
0x18001b0c7  mov     [rsp+190h+var_138], eax
0x18001b0cb  mov     rdx, [rcx]
0x18001b0ce  mov     rax, [rdx+30h]
0x18001b0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0d7  mov     rcx, [rbp+90h+var_80]
0x18001b0db  mov     ebx, eax
0x18001b0dd  mov     rdx, [rcx]
0x18001b0e0  mov     rax, [rdx+28h]
0x18001b0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0e9  mov     r15, rax
0x18001b0ec  test    byte ptr cs:xmmword_180107A60, 20h
0x18001b0f3  mov     r12d, [rsp+190h+var_138]
0x18001b0f8  jz      loc_18001AE79
0x18001b0fe  mov     dword ptr [rsp+190h+var_160], ebx
0x18001b102  mov     r9, r13
0x18001b105  mov     qword ptr [rsp+190h+var_168], rax
0x18001b10a  mov     dword ptr [rsp+190h+var_170], r12d
0x18001b10f  call    WPP_SF_qDSD
0x18001b114  jmp     loc_18001AE79
0x18001b119  mov     r13b, 20h ; ' '
0x18001b11c  test    byte ptr cs:xmmword_180107A60, r13b
0x18001b123  jnz     loc_18001B206
0x18001b129  cmp     [rbp+90h+pProxyInfoEx.fDirectConfiguration], r12d
0x18001b12d  jz      loc_18001B22D
0x18001b133  lea     rdx, SubStr; "DIRECT"
0x18001b13a  lea     rcx, [rsp+190h+var_118]; this
0x18001b13f  call    ?Append@CWxString@@QEAAJPEBG@Z; CWxString::Append(ushort const *)
0x18001b144  mov     r13, [rsp+190h+var_128]
0x18001b149  mov     ebx, eax
0x18001b14b  test    eax, eax
0x18001b14d  js      loc_18001B3A9
0x18001b153  mov     rax, [rbp+90h+pProxyInfoEx.hConnection]
0x18001b157  lea     rdx, [rsp+190h+var_118]
0x18001b15c  mov     r9, [rbp+90h+pProxyInfoEx.pwszConnectionName]
0x18001b160  mov     rcx, r13
0x18001b163  mov     r8d, [r15+18h]
0x18001b167  mov     [rsp+190h+var_158], rdi
0x18001b16c  mov     dword ptr [rsp+190h+var_160], r12d
0x18001b171  mov     qword ptr [rsp+190h+var_168], rax
0x18001b176  mov     eax, [rbp+90h+pProxyInfoEx.dwInterfaceIndex]
0x18001b179  mov     dword ptr [rsp+190h+var_170], eax
0x18001b17d  call    ?GetProxyResultFromProxyString@ConnectionManagerResolver@@AEAAJPEAVCWxString@@W4ProxyResolveScheme@@PEBGKPEAXHPEAPEAUIProxyResult@@@Z; ConnectionManagerResolver::GetProxyResultFromProxyString(CWxString *,ProxyResolveScheme,ushort const *,ulong,void *,int,IProxyResult * *)
0x18001b182  mov     ebx, eax
0x18001b184  test    eax, eax
0x18001b186  js      loc_18001B3B3
0x18001b18c  mov     rsi, [rsp+190h+var_118]
0x18001b191  mov     edi, r12d
0x18001b194  mov     ebx, r12d
0x18001b197  jmp     loc_18001AED5
0x18001b19c  mov     edx, 2Bh ; '+'
0x18001b1a1  lea     r8, WPP_52b9ef2e0ce03807e04b532c07148c79_Traceguids
0x18001b1a8  mov     ecx, 405h
0x18001b1ad  mov     r9, r15
0x18001b1b0  call    WPP_SF_q
0x18001b1b5  jmp     loc_18001AFE5
0x18001b1ba  mov     rax, [rbp+90h+var_108]
0x18001b1be  mov     r9, r13
0x18001b1c1  mov     [rsp+190h+var_150], rdi
0x18001b1c6  mov     [rsp+190h+var_158], rax
0x18001b1cb  mov     rax, [rbx]
0x18001b1ce  mov     [rsp+190h+var_160], r12
0x18001b1d3  mov     qword ptr [rsp+190h+var_168], rax
0x18001b1d8  mov     eax, [rsp+190h+var_120]
0x18001b1dc  mov     dword ptr [rsp+190h+var_170], eax
0x18001b1e0  call    WPP_SF_qdSqqq
0x18001b1e5  jmp     loc_18001AE50
0x18001b1ea  call    cs:__imp_GetLastError
0x18001b1f0  mov     ebx, eax
0x18001b1f2  mov     rcx, [rbp+90h+TokenHandle]
0x18001b1f6  jmp     loc_18001B02C
0x18001b1fb  call    cs:__imp_CloseHandle
0x18001b201  jmp     loc_18001B036
0x18001b206  mov     rax, [rbp+90h+pProxyInfoEx.hConnection]
0x18001b20a  mov     r9d, [rbp+90h+pProxyInfoEx.dwInterfaceIndex]
0x18001b20e  mov     [rsp+190h+var_160], rax
0x18001b213  mov     eax, [rbp+90h+pProxyInfoEx.fDirectConfiguration]
0x18001b216  mov     [rsp+190h+var_168], eax
0x18001b21a  mov     rax, [rbp+90h+pProxyInfoEx.pwszConnectionName]
0x18001b21e  mov     [rsp+190h+var_170], rax
0x18001b223  call    WPP_SF_DSlq
0x18001b228  jmp     loc_18001B129
0x18001b22d  lea     rax, [rbp+90h+var_78]
0x18001b231  lea     r9, [rbp+90h+var_68]; struct CWxString *
0x18001b235  mov     [rsp+190h+var_170], rax; struct CWxString *
0x18001b23a  lea     r8, [rbp+90h+var_58]; struct CWxString *
0x18001b23e  lea     rdx, [rsp+190h+var_140]; enum WX_CONNECTION_PROXY_INFO_SWITCH *
0x18001b243  lea     rcx, [rbp+90h+pProxyInfoEx]; struct _DNS_CONNECTION_PROXY_INFO *
0x18001b247  call    ?WxGetProxyForProxyInfo@@YAJPEAU_DNS_CONNECTION_PROXY_INFO@@PEAW4WX_CONNECTION_PROXY_INFO_SWITCH@@PEAVCWxString@@22@Z; WxGetProxyForProxyInfo(_DNS_CONNECTION_PROXY_INFO *,WX_CONNECTION_PROXY_INFO_SWITCH *,CWxString *,CWxString *,CWxString *)
0x18001b24c  mov     ebx, eax
  ... truncated ...
```
