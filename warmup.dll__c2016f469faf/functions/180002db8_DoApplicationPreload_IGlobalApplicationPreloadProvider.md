# DoApplicationPreload(IGlobalApplicationPreloadProvider *)

- ea: `0x180002db8`
- end: `0x180003390`
- name: `?DoApplicationPreload@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalApplicationPreloadProvider@@@Z`
- size: `1496`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001c90`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002db8`
- `0x180003c74`
- `0x180004204`
- `0x180006010`

## import_xrefs

- `ntdll!RtlIpv4StringToAddressExA` at `0x180002dfb`
- `ntdll!RtlIpv4StringToAddressExA` at `0x180002e41`
- `ntdll!RtlIpv4StringToAddressExA` at `0x180002dfb`
- `ntdll!RtlIpv4StringToAddressExA` at `0x180002e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f49`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800032a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800032a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002f3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002f3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000335a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000335a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003253`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000325d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003267`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003271`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003319`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003323`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000332d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003337`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003253`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000325d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003267`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003271`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003319`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003323`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000332d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003337`
- `iisutil!PuDbgPrint` at `0x180002f09`
- `iisutil!PuDbgPrint` at `0x180003115`
- `iisutil!PuDbgPrint` at `0x180003224`
- `iisutil!PuDbgPrint` at `0x1800032eb`
- `iisutil!PuDbgPrint` at `0x180002f09`
- `iisutil!PuDbgPrint` at `0x180003115`
- `iisutil!PuDbgPrint` at `0x180003224`
- `iisutil!PuDbgPrint` at `0x1800032eb`

## string_xrefs

- `0x180002f02`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmup.cxx`
- `0x1800030f2`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmup.cxx`
- `0x1800031f2`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmup.cxx`
- `0x1800032e4`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmup.cxx`
- `0x180003099`: `User-Agent`
- `0x1800032c6`: `Error 0x%08x occurred during application preload.\n`

## pseudocode

```c
__int64 __fastcall DoApplicationPreload(__int64 a1)
{
  LONG v2; // eax
  signed int PreloadRequests; // r15d
  bool v4; // cc
  struct _LIST_ENTRY **p_Blink; // r13
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v10; // rbx
  void *v11; // rcx
  struct _LIST_ENTRY *Flink; // r13
  struct _LIST_ENTRY *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // ebx
  const char *v19; // rdi
  int v20; // esi
  int v21; // r14d
  __int64 v22; // rax
  __int64 v23; // rax
  void *v24; // rcx
  _QWORD *v25; // rbx
  void *v26; // rcx
  int v28; // [rsp+60h] [rbp-9h] BYREF
  struct IHttpContext *v29; // [rsp+68h] [rbp-1h] BYREF
  __int64 v30; // [rsp+70h] [rbp+7h] BYREF
  const char *v31; // [rsp+78h] [rbp+Fh] BYREF
  struct _LIST_ENTRY v32; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int16 v33; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int16 v34; // [rsp+E0h] [rbp+77h] BYREF
  __int16 v35; // [rsp+E8h] [rbp+7Fh] BYREF

  v29 = 0;
  v32 = 0;
  v2 = RtlIpv4StringToAddressExA("127.0.0.1:80", 0, &Address, &Port);
  PreloadRequests = v2;
  v4 = v2 <= 0;
  if ( v2
    || (g_WarmupLocalAddr.ss_family = 2,
        v2 = RtlIpv4StringToAddressExA("127.0.0.1:3500", 0, &stru_18000A674, &word_18000A672),
        PreloadRequests = v2,
        v4 = v2 <= 0,
        v2) )
  {
    if ( !v4 )
      PreloadRequests = (unsigned __int16)v2 | 0x80070000;
    goto LABEL_40;
  }
  g_WarmupRemoteAddr.ss_family = 2;
  v30 = 0;
  PreloadRequests = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, __int64 *))(*(_QWORD *)g_pServer + 200LL))(
                      g_pServer,
                      0,
                      &v30);
  if ( PreloadRequests < 0
    || (PreloadRequests = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, GUID *, struct IGlobalApplicationPreloadProvider2 **))(*(_QWORD *)v30 + 224LL))(
                            v30,
                            &GUID_2111f8d6_0c41_4ff7_bd45_5c04c7e91a73,
                            a1,
                            &GUID_251db2dd_81e7_44ce_ae02_46529f2d71ea,
                            &g_pPreloadProvider),
        PreloadRequests < 0) )
  {
    p_Blink = 0;
  }
  else
  {
    p_Blink = 0;
    if ( (*(unsigned int (__fastcall **)(struct IGlobalApplicationPreloadProvider2 *))(*(_QWORD *)g_pPreloadProvider
                                                                                     + 24LL))(g_pPreloadProvider) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmup.cxx",
          592,
          "DoApplicationPreload",
          "Recycled Process.  Need to block preload notification.\r\n");
      v6 = operator new(0x10u);
      v7 = v6;
      if ( !v6 )
      {
        g_pPreloadBlock = 0;
        PreloadRequests = -2147024882;
        goto LABEL_43;
      }
      *(_DWORD *)v6 = 0;
      v6[1] = 0;
      g_pPreloadBlock = v6;
      EventW = CreateEventW(0, 1, 1, 0);
      v7[1] = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        PreloadRequests = LastError;
        if ( LastError > 0 )
          PreloadRequests = (unsigned __int16)LastError | 0x80070000;
        if ( PreloadRequests < 0 )
        {
          v10 = g_pPreloadBlock;
          if ( g_pPreloadBlock )
          {
            v11 = (void *)*((_QWORD *)g_pPreloadBlock + 1);
            if ( v11 )
            {
              CloseHandle(v11);
              v10[1] = 0;
            }
            operator delete(v10);
          }
          g_pPreloadBlock = 0;
          goto LABEL_43;
        }
      }
    }
    v32.Blink = &v32;
    v32.Flink = &v32;
    PreloadRequests = GetPreloadRequests(&v32);
    if ( PreloadRequests >= 0 )
    {
      while ( 1 )
      {
        Flink = v32.Flink;
        if ( v32.Flink == &v32 )
          break;
        if ( v32.Flink->Blink != &v32 || (v13 = v32.Flink->Flink, v32.Flink->Flink->Blink != v32.Flink) )
          __fastfail(3u);
        v32.Flink = v32.Flink->Flink;
        v13->Blink = &v32;
        p_Blink = &Flink[-15].Blink;
        PreloadRequests = (*(__int64 (__fastcall **)(__int64, struct IHttpContext **))(*(_QWORD *)a1 + 8LL))(a1, &v29);
        if ( PreloadRequests < 0 )
          goto LABEL_43;
        PreloadRequests = InitializeWarmupRequest((struct WARMUP_REQUEST *)p_Blink, v29);
        if ( PreloadRequests < 0 )
          goto LABEL_43;
        PreloadRequests = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, const wchar_t *))(*(_QWORD *)v29 + 136LL))(
                            v29,
                            "PRELOAD_REQUEST",
                            L"1");
        if ( PreloadRequests < 0 )
          goto LABEL_43;
        v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v29 + 24LL))(v29);
        PreloadRequests = (*(__int64 (__fastcall **)(__int64, const char *, const char *, __int64, int))(*(_QWORD *)v14 + 40LL))(
                            v14,
                            "User-Agent",
                            "IIS Application Initialization Preload",
                            38,
                            1);
        if ( PreloadRequests < 0 )
          goto LABEL_43;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v29 + 24LL))(v29);
          v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmup.cxx",
            697,
            "DoApplicationPreload",
            "Running preload request [%S]\r\n",
            *(const wchar_t **)(v16 + 72));
        }
        PreloadRequests = (*(__int64 (__fastcall **)(__int64, struct IHttpContext *, _QWORD))(*(_QWORD *)a1 + 16LL))(
                            a1,
                            v29,
                            0);
        if ( PreloadRequests < 0 )
          goto LABEL_43;
        v34 = 0;
        v33 = 0;
        v31 = 0;
        v35 = 0;
        v28 = 0;
        v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v29 + 32LL))(v29);
        (*(void (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, const char **, __int16 *, int *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 184LL))(
          v17,
          &v34,
          &v33,
          &v31,
          &v35,
          &v28,
          0,
          0,
          0,
          0);
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v18 = v28;
          v19 = v31;
          v20 = v33;
          v21 = v34;
          v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v29 + 24LL))(v29);
          v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmup.cxx",
            733,
            "DoApplicationPreload",
            "Preload Request [%S] returned \"%d.%d %s\", hr=0x%08x.\r\n",
            *(const wchar_t **)(v23 + 72),
            v21,
            v20,
            v19,
            v18);
        }
        (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v29 + 256LL))(v29);
        v29 = 0;
        if ( p_Blink )
        {
          STRU::~STRU((STRU *)(p_Blink + 22));
          STRU::~STRU((STRU *)(p_Blink + 15));
          STRU::~STRU((STRU *)(p_Blink + 8));
          STRU::~STRU((STRU *)(p_Blink + 1));
          operator delete(p_Blink);
        }
      }
      if ( g_pPreloadBlock )
      {
        v24 = (void *)*((_QWORD *)g_pPreloadBlock + 1);
        if ( v24 )
          WaitForSingleObject(v24, 0xFFFFFFFF);
      }
LABEL_40:
      p_Blink = 0;
      if ( PreloadRequests >= 0 )
        goto LABEL_45;
    }
  }
LABEL_43:
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmup.cxx",
      754,
      "DoApplicationPreload",
      "Error 0x%08x occurred during application preload.\r\n",
      PreloadRequests);
LABEL_45:
  if ( v29 )
  {
    (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v29 + 256LL))(v29);
    v29 = 0;
  }
  if ( p_Blink )
  {
    STRU::~STRU((STRU *)(p_Blink + 22));
    STRU::~STRU((STRU *)(p_Blink + 15));
    STRU::~STRU((STRU *)(p_Blink + 8));
    STRU::~STRU((STRU *)(p_Blink + 1));
    operator delete(p_Blink);
  }
  v25 = g_pPreloadBlock;
  if ( g_pPreloadBlock )
  {
    v26 = (void *)*((_QWORD *)g_pPreloadBlock + 1);
    if ( v26 )
    {
      CloseHandle(v26);
      v25[1] = 0;
    }
    operator delete(v25);
    g_pPreloadBlock = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180002db8  mov     [rsp-8+arg_0], rbx
0x180002dbd  push    rbp
0x180002dbe  push    rsi
0x180002dbf  push    rdi
0x180002dc0  push    r12
0x180002dc2  push    r13
0x180002dc4  push    r14
0x180002dc6  push    r15
0x180002dc8  lea     rbp, [rsp-27h]
0x180002dcd  sub     rsp, 90h
0x180002dd4  mov     r12, rcx
0x180002dd7  lea     r9, Port; Port
0x180002dde  xorps   xmm0, xmm0
0x180002de1  lea     rcx, AddressString; "127.0.0.1:80"
0x180002de8  xor     edi, edi
0x180002dea  lea     r8, Address; Address
0x180002df1  xor     edx, edx; Strict
0x180002df3  mov     [rbp+57h+var_58], rdi
0x180002df7  movups  xmmword ptr [rbp+57h+var_40.Flink], xmm0
0x180002dfb  call    cs:__imp_RtlIpv4StringToAddressExA
0x180002e01  mov     r15d, eax
0x180002e04  test    eax, eax
0x180002e06  jz      short loc_180002E1E
0x180002e08  jle     loc_1800032A9
0x180002e0e  movzx   r15d, ax
0x180002e12  or      r15d, 80070000h
0x180002e19  jmp     loc_1800032A9
0x180002e1e  mov     ebx, 2
0x180002e23  lea     r9, word_18000A672; Port
0x180002e2a  lea     r8, stru_18000A674; Address
0x180002e31  mov     cs:?g_WarmupLocalAddr@@3Usockaddr_storage@@A, bx; sockaddr_storage g_WarmupLocalAddr
0x180002e38  xor     edx, edx; Strict
0x180002e3a  lea     rcx, a1270013500; "127.0.0.1:3500"
0x180002e41  call    cs:__imp_RtlIpv4StringToAddressExA
0x180002e47  mov     r15d, eax
0x180002e4a  test    eax, eax
0x180002e4c  jnz     short loc_180002E08
0x180002e4e  mov     rcx, cs:?g_pServer@@3PEAVIHttpServer@@EA; IHttpServer * g_pServer
0x180002e55  lea     r8, [rbp+57h+var_50]
0x180002e59  mov     cs:?g_WarmupRemoteAddr@@3Usockaddr_storage@@A, bx; sockaddr_storage g_WarmupRemoteAddr
0x180002e60  xor     edx, edx
0x180002e62  mov     [rbp+57h+var_50], rdi
0x180002e66  mov     rax, [rcx]
0x180002e69  mov     rax, [rax+0C8h]
0x180002e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e75  mov     r15d, eax
0x180002e78  test    eax, eax
0x180002e7a  js      loc_1800032B3
0x180002e80  mov     rcx, [rbp+57h+var_50]
0x180002e84  lea     rdx, ?g_pPreloadProvider@@3PEAVIGlobalApplicationPreloadProvider2@@EA; IGlobalApplicationPreloadProvider2 * g_pPreloadProvider
0x180002e8b  mov     [rsp+0C0h+var_A0], rdx
0x180002e90  lea     r9, _GUID_251db2dd_81e7_44ce_ae02_46529f2d71ea
0x180002e97  mov     r8, r12
0x180002e9a  lea     rdx, _GUID_2111f8d6_0c41_4ff7_bd45_5c04c7e91a73
0x180002ea1  mov     rax, [rcx]
0x180002ea4  mov     rax, [rax+0E0h]
0x180002eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eb0  mov     r15d, eax
0x180002eb3  test    eax, eax
0x180002eb5  js      loc_1800032B3
0x180002ebb  mov     rcx, cs:?g_pPreloadProvider@@3PEAVIGlobalApplicationPreloadProvider2@@EA; IGlobalApplicationPreloadProvider2 * g_pPreloadProvider
0x180002ec2  mov     r13, rdi
0x180002ec5  mov     rax, [rcx]
0x180002ec8  mov     rax, [rax+18h]
0x180002ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed1  test    eax, eax
0x180002ed3  jz      loc_180002FAB
0x180002ed9  test    byte ptr cs:g_dwDebugFlags, 3
0x180002ee0  jz      short loc_180002F0F
0x180002ee2  mov     rcx, cs:g_pDebug
0x180002ee9  lea     rax, aRecycledProces; "Recycled Process.  Need to block preloa"...
0x180002ef0  lea     r9, aDoapplicationp; "DoApplicationPreload"
0x180002ef7  mov     [rsp+0C0h+var_A0], rax
0x180002efc  mov     r8d, 250h
0x180002f02  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002f09  call    cs:__imp_PuDbgPrint
0x180002f0f  mov     ecx, 10h; Size
0x180002f14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002f19  mov     rbx, rax
0x180002f1c  test    rax, rax
0x180002f1f  jz      short loc_180002F99
0x180002f21  xor     r9d, r9d; lpName
0x180002f24  mov     [rax], edi
0x180002f26  xor     ecx, ecx; lpEventAttributes
0x180002f28  mov     [rax+8], rdi
0x180002f2c  mov     cs:?g_pPreloadBlock@@3PEAVPRELOAD_BLOCK@@EA, rax; PRELOAD_BLOCK * g_pPreloadBlock
0x180002f33  lea     edx, [r9+1]; bManualReset
0x180002f37  mov     r8d, edx; bInitialState
0x180002f3a  call    cs:__imp_CreateEventW
0x180002f40  mov     [rbx+8], rax
0x180002f44  test    rax, rax
0x180002f47  jnz     short loc_180002FAB
0x180002f49  call    cs:__imp_GetLastError
0x180002f4f  mov     r15d, eax
0x180002f52  test    eax, eax
0x180002f54  jle     short loc_180002F61
0x180002f56  movzx   r15d, ax
0x180002f5a  or      r15d, 80070000h
0x180002f61  test    r15d, r15d
0x180002f64  jns     short loc_180002FAB
0x180002f66  mov     rbx, cs:?g_pPreloadBlock@@3PEAVPRELOAD_BLOCK@@EA; PRELOAD_BLOCK * g_pPreloadBlock
0x180002f6d  test    rbx, rbx
0x180002f70  jz      short loc_180002F8D
0x180002f72  mov     rcx, [rbx+8]; hObject
0x180002f76  test    rcx, rcx
0x180002f79  jz      short loc_180002F85
0x180002f7b  call    cs:__imp_CloseHandle
0x180002f81  mov     [rbx+8], rdi
0x180002f85  mov     rcx, rbx; Block
0x180002f88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f8d  mov     cs:?g_pPreloadBlock@@3PEAVPRELOAD_BLOCK@@EA, rdi; PRELOAD_BLOCK * g_pPreloadBlock
0x180002f94  jmp     loc_1800032B6
0x180002f99  mov     cs:?g_pPreloadBlock@@3PEAVPRELOAD_BLOCK@@EA, rdi; PRELOAD_BLOCK * g_pPreloadBlock
0x180002fa0  mov     r15d, 8007000Eh
0x180002fa6  jmp     loc_1800032B6
0x180002fab  lea     rax, [rbp+57h+var_40]
0x180002faf  mov     [rbp+57h+var_40.Blink], rax
0x180002fb3  lea     rcx, [rbp+57h+var_40]; struct _LIST_ENTRY *
0x180002fb7  lea     rax, [rbp+57h+var_40]
0x180002fbb  mov     [rbp+57h+var_40.Flink], rax
0x180002fbf  call    ?GetPreloadRequests@@YAJPEAU_LIST_ENTRY@@@Z; GetPreloadRequests(_LIST_ENTRY *)
0x180002fc4  mov     r15d, eax
0x180002fc7  test    eax, eax
0x180002fc9  js      loc_1800032B6
0x180002fcf  mov     r13, [rbp+57h+var_40.Flink]
0x180002fd3  lea     rax, [rbp+57h+var_40]
0x180002fd7  cmp     r13, rax
0x180002fda  jz      loc_18000328B
0x180002fe0  lea     rax, [rbp+57h+var_40]
0x180002fe4  cmp     [r13+8], rax
0x180002fe8  jnz     loc_180003284
0x180002fee  mov     rax, [r13+0]
0x180002ff2  cmp     [rax+8], r13
0x180002ff6  jnz     loc_180003284
0x180002ffc  mov     [rbp+57h+var_40.Flink], rax
0x180003000  lea     rcx, [rbp+57h+var_40]
0x180003004  mov     [rax+8], rcx
0x180003008  lea     rdx, [rbp+57h+var_58]
0x18000300c  mov     rax, [r12]
0x180003010  mov     rcx, r12
0x180003013  add     r13, 0FFFFFFFFFFFFFF18h
0x18000301a  mov     rax, [rax+8]
0x18000301e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003023  mov     r15d, eax
0x180003026  test    eax, eax
0x180003028  js      loc_1800032B6
0x18000302e  mov     rdx, [rbp+57h+var_58]; struct IHttpContext *
0x180003032  mov     rcx, r13; struct WARMUP_REQUEST *
0x180003035  call    ?InitializeWarmupRequest@@YAJPEAUWARMUP_REQUEST@@PEAVIHttpContext@@@Z; InitializeWarmupRequest(WARMUP_REQUEST *,IHttpContext *)
0x18000303a  mov     r15d, eax
0x18000303d  test    eax, eax
0x18000303f  js      loc_1800032B6
0x180003045  mov     rcx, [rbp+57h+var_58]
0x180003049  lea     r8, a1; "1"
0x180003050  lea     rdx, aPreloadRequest_0; "PRELOAD_REQUEST"
0x180003057  mov     rax, [rcx]
0x18000305a  mov     rax, [rax+88h]
0x180003061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003066  mov     r15d, eax
0x180003069  test    eax, eax
0x18000306b  js      loc_1800032B6
0x180003071  mov     rcx, [rbp+57h+var_58]
0x180003075  mov     rax, [rcx]
0x180003078  mov     rax, [rax+18h]
0x18000307c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003081  mov     r10, rax
0x180003084  mov     dword ptr [rsp+0C0h+var_A0], 1
0x18000308c  mov     r9d, 26h ; '&'
0x180003092  lea     r8, aIisApplication; "IIS Application Initialization Preload"
0x180003099  lea     rdx, aUserAgent; "User-Agent"
0x1800030a0  mov     rcx, [rax]
0x1800030a3  mov     rax, [rcx+28h]
0x1800030a7  mov     rcx, r10
0x1800030aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030af  mov     r15d, eax
0x1800030b2  test    eax, eax
0x1800030b4  js      loc_1800032B6
0x1800030ba  test    byte ptr cs:g_dwDebugFlags, 3
0x1800030c1  jz      short loc_18000311B
0x1800030c3  mov     rcx, [rbp+57h+var_58]
0x1800030c7  mov     rax, [rcx]
0x1800030ca  mov     rax, [rax+18h]
0x1800030ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d3  mov     rdx, rax
0x1800030d6  mov     rcx, [rax]
0x1800030d9  mov     rax, [rcx+8]
0x1800030dd  mov     rcx, rdx
0x1800030e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e5  lea     r9, aDoapplicationp; "DoApplicationPreload"
0x1800030ec  mov     r8d, 2B9h
0x1800030f2  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800030f9  mov     rcx, [rax+48h]
0x1800030fd  lea     rax, aRunningPreload; "Running preload request [%S]\r\n"
0x180003104  mov     [rsp+0C0h+var_98], rcx
0x180003109  mov     rcx, cs:g_pDebug
0x180003110  mov     [rsp+0C0h+var_A0], rax
0x180003115  call    cs:__imp_PuDbgPrint
0x18000311b  mov     rax, [r12]
0x18000311f  xor     r8d, r8d
0x180003122  mov     rdx, [rbp+57h+var_58]
0x180003126  mov     rcx, r12
0x180003129  mov     rax, [rax+10h]
0x18000312d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003132  mov     r15d, eax
0x180003135  test    eax, eax
0x180003137  js      loc_1800032B6
0x18000313d  mov     rcx, [rbp+57h+var_58]
0x180003141  mov     [rbp+57h+arg_10], di
0x180003145  mov     [rbp+57h+arg_8], di
0x180003149  mov     [rbp+57h+var_48], rdi
0x18000314d  mov     [rbp+57h+arg_18], di
0x180003151  mov     [rbp+57h+var_60], edi
0x180003154  mov     rax, [rcx]
0x180003157  mov     rax, [rax+20h]
0x18000315b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003160  mov     [rsp+0C0h+var_78], rdi
0x180003165  lea     r9, [rbp+57h+var_48]
0x180003169  mov     [rsp+0C0h+var_80], rdi
0x18000316e  lea     r8, [rbp+57h+arg_8]
0x180003172  mov     r10, rax
0x180003175  mov     [rsp+0C0h+var_88], rdi
0x18000317a  mov     rcx, [rax]
0x18000317d  lea     rdx, [rbp+57h+arg_10]
0x180003181  mov     [rsp+0C0h+var_90], rdi
0x180003186  mov     rax, [rcx+0B8h]
0x18000318d  lea     rcx, [rbp+57h+var_60]
0x180003191  mov     [rsp+0C0h+var_98], rcx
0x180003196  lea     rcx, [rbp+57h+arg_18]
0x18000319a  mov     [rsp+0C0h+var_A0], rcx
0x18000319f  mov     rcx, r10
0x1800031a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a7  test    byte ptr cs:g_dwDebugFlags, 3
0x1800031ae  jz      short loc_18000322C
0x1800031b0  mov     rcx, [rbp+57h+var_58]
0x1800031b4  mov     ebx, [rbp+57h+var_60]
0x1800031b7  mov     rdi, [rbp+57h+var_48]
0x1800031bb  movzx   esi, [rbp+57h+arg_8]
0x1800031bf  mov     rax, [rcx]
0x1800031c2  movzx   r14d, [rbp+57h+arg_10]
0x1800031c7  mov     rax, [rax+18h]
0x1800031cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d0  mov     rdx, rax
0x1800031d3  mov     rcx, [rax]
0x1800031d6  mov     rax, [rcx+8]
0x1800031da  mov     rcx, rdx
0x1800031dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e2  mov     dword ptr [rsp+0C0h+var_78], ebx
0x1800031e6  lea     r9, aDoapplicationp; "DoApplicationPreload"
0x1800031ed  mov     [rsp+0C0h+var_80], rdi
0x1800031f2  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800031f9  mov     dword ptr [rsp+0C0h+var_88], esi
0x1800031fd  mov     r8d, 2DDh
0x180003203  mov     rcx, [rax+48h]
0x180003207  lea     rax, aPreloadRequest; "Preload Request [%S] returned \"%d.%d %"...
0x18000320e  mov     dword ptr [rsp+0C0h+var_90], r14d
0x180003213  mov     [rsp+0C0h+var_98], rcx
0x180003218  mov     rcx, cs:g_pDebug
0x18000321f  mov     [rsp+0C0h+var_A0], rax
0x180003224  call    cs:__imp_PuDbgPrint
0x18000322a  xor     edi, edi
0x18000322c  mov     rcx, [rbp+57h+var_58]
0x180003230  mov     rax, [rcx]
0x180003233  mov     rax, [rax+100h]
0x18000323a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000323f  mov     [rbp+57h+var_58], rdi
0x180003243  test    r13, r13
0x180003246  jz      loc_180002FCF
0x18000324c  lea     rcx, [r13+0B0h]
0x180003253  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003259  lea     rcx, [r13+78h]
0x18000325d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003263  lea     rcx, [r13+40h]
0x180003267  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000326d  lea     rcx, [r13+8]
0x180003271  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003277  mov     rcx, r13; Block
0x18000327a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000327f  jmp     loc_180002FCF
0x180003284  mov     ecx, 3
0x180003289  int     29h; Win8: RtlFailFast(ecx)
0x18000328b  mov     rbx, cs:?g_pPreloadBlock@@3PEAVPRELOAD_BLOCK@@EA; PRELOAD_BLOCK * g_pPreloadBlock
0x180003292  test    rbx, rbx
0x180003295  jz      short loc_1800032A9
0x180003297  mov     rcx, [rbx+8]; hHandle
0x18000329b  test    rcx, rcx
0x18000329e  jz      short loc_1800032A9
0x1800032a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800032a3  call    cs:__imp_WaitForSingleObject
0x1800032a9  mov     r13, rdi
0x1800032ac  test    r15d, r15d
0x1800032af  jns     short loc_1800032F1
0x1800032b1  jmp     short loc_1800032B6
0x1800032b3  mov     r13, rdi
0x1800032b6  test    byte ptr cs:g_dwDebugFlags, 3
0x1800032bd  jz      short loc_1800032F1
0x1800032bf  mov     rcx, cs:g_pDebug
0x1800032c6  lea     rax, aError0x08xOccu; "Error 0x%08x occurred during applicatio"...
0x1800032cd  mov     dword ptr [rsp+0C0h+var_98], r15d
0x1800032d2  lea     r9, aDoapplicationp; "DoApplicationPreload"
0x1800032d9  mov     r8d, 2F2h
  ... truncated ...
```
