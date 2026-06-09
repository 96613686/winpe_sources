# GetPreloadRequests(_LIST_ENTRY *)

- ea: `0x180003c74`
- end: `0x180004112`
- name: `?GetPreloadRequests@@YAJPEAU_LIST_ENTRY@@@Z`
- size: `1182`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002db8`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002924`
- `0x1800029a8`
- `0x1800029f0`
- `0x180002af0`
- `0x180002bd8`
- `0x180003c74`
- `0x180004fb6`
- `0x180004fe0`
- `0x180006010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003e8f`
- `msvcrt!_wcsicmp` at `0x180003e8f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000402d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004037`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004041`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000404b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800040e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800040ea`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000402d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004037`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004041`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000404b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800040e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800040ea`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003cbd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003cc7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003eb7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003ec1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003ecb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003ed8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003cbd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003cc7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003eb7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003ec1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003ecb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003ed8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003efd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f18`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f33`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003efd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f18`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f33`
- `iisutil!PuDbgPrint` at `0x18000401b`
- `iisutil!PuDbgPrint` at `0x18000401b`

## string_xrefs

- `0x180004014`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmup.cxx`
- `0x180003ff7`: `Error 0x%08x occurred during application preload.\n`

## pseudocode

```c
__int64 __fastcall GetPreloadRequests(struct _LIST_ENTRY *a1)
{
  char *v2; // rdi
  __int64 v3; // rax
  struct IAppHostAdminManager *v4; // rax
  int AdminElement; // ebx
  unsigned int v6; // r12d
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // r14d
  unsigned int v9; // r13d
  const wchar_t *v10; // rax
  char *v11; // rax
  char *v12; // rsi
  struct _LIST_ENTRY *Blink; // rcx
  struct IAppHostElement *v15; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-91h] BYREF
  unsigned int v17; // [rsp+3Ch] [rbp-8Dh] BYREF
  struct IAppHostElementCollection *v18; // [rsp+40h] [rbp-89h] BYREF
  struct IAppHostElement *v19; // [rsp+48h] [rbp-81h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-79h] BYREF
  int v21; // [rsp+54h] [rbp-75h] BYREF
  struct IAppHostElementCollection *v22; // [rsp+58h] [rbp-71h] BYREF
  struct IAppHostElement *v23; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v24[32]; // [rsp+68h] [rbp-61h] BYREF
  const unsigned __int16 *v25; // [rsp+88h] [rbp-41h]
  int v26; // [rsp+98h] [rbp-31h]
  _BYTE v27[32]; // [rsp+A0h] [rbp-29h] BYREF
  wchar_t *String1; // [rsp+C0h] [rbp-9h]

  v23 = 0;
  v19 = 0;
  v2 = 0;
  v15 = 0;
  v22 = 0;
  v18 = 0;
  STRU::STRU((STRU *)v24);
  STRU::STRU((STRU *)v27);
  v17 = 0;
  v16 = 0;
  v20 = 0;
  v3 = *(_QWORD *)g_pServer;
  v21 = 0;
  v4 = (struct IAppHostAdminManager *)(*(__int64 (__fastcall **)(struct IHttpServer *))(v3 + 56))(g_pServer);
  AdminElement = GetAdminElement(v4, L"MACHINE/WEBROOT/APPHOST", L"system.applicationHost/sites", &v23);
  if ( AdminElement >= 0 )
  {
    AdminElement = ((__int64 (__fastcall *)(struct IAppHostElement *, struct IAppHostElementCollection **))v23->lpVtbl->get_Collection)(
                     v23,
                     &v22);
    if ( AdminElement >= 0 )
    {
      AdminElement = ((__int64 (__fastcall *)(struct IAppHostElementCollection *, unsigned int *))v22->lpVtbl->get_Count)(
                       v22,
                       &v17);
      if ( AdminElement >= 0 )
      {
        v6 = 0;
        if ( !v17 )
          goto LABEL_35;
        while ( 1 )
        {
          AdminElement = GetCollectionElement(v22, v6, &v19);
          if ( AdminElement < 0 )
            break;
          AdminElement = GetConfigDWORD(v19, v7, &v20);
          if ( AdminElement < 0 )
            break;
          AdminElement = ((__int64 (__fastcall *)(struct IAppHostElement *, struct IAppHostElementCollection **))v19->lpVtbl->get_Collection)(
                           v19,
                           &v18);
          if ( AdminElement < 0 )
            break;
          AdminElement = ((__int64 (__fastcall *)(struct IAppHostElementCollection *, unsigned int *))v18->lpVtbl->get_Count)(
                           v18,
                           &v16);
          v2 = 0;
          if ( AdminElement < 0 )
            goto LABEL_31;
          v8 = 0;
          if ( v16 )
          {
            v9 = v20;
            do
            {
              AdminElement = GetCollectionElement(v18, v8, &v15);
              if ( AdminElement < 0 )
                goto LABEL_30;
              AdminElement = GetConfigString(v15, L"path", (struct STRU *)v24);
              if ( AdminElement < 0 )
                goto LABEL_30;
              if ( v26 == 1 )
              {
                *v25 = 0;
                v26 = 0;
              }
              AdminElement = GetConfigString(v15, L"applicationPool", (struct STRU *)v27);
              if ( AdminElement < 0 )
                goto LABEL_30;
              AdminElement = GetConfigBool(v15, L"preloadEnabled", &v21);
              if ( AdminElement < 0 )
                goto LABEL_30;
              if ( v21 )
              {
                v10 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pServer + 8LL))(g_pServer);
                if ( !_wcsicmp(String1, v10) )
                {
                  v11 = (char *)operator new(0xF8u);
                  v12 = v11;
                  if ( !v11 )
                  {
                    AdminElement = -2147024882;
                    goto LABEL_30;
                  }
                  STRU::STRU((STRU *)(v11 + 8));
                  STRU::STRU((STRU *)(v12 + 64));
                  STRU::STRU((STRU *)(v12 + 120));
                  STRU::STRU((STRU *)(v12 + 176));
                  memset_0(v12 + 4, 0, 0xF4u);
                  *(_DWORD *)v12 = v9;
                  AdminElement = STRU::Copy((STRU *)(v12 + 120), L"localhost");
                  v2 = v12;
                  if ( AdminElement < 0 )
                    goto LABEL_31;
                  AdminElement = STRU::Copy((STRU *)(v12 + 8), v25);
                  if ( AdminElement < 0 )
                    goto LABEL_31;
                  AdminElement = STRU::Copy((STRU *)(v12 + 64), L"/");
                  if ( AdminElement < 0 )
                    goto LABEL_31;
                  Blink = a1->Blink;
                  if ( Blink->Flink != a1 )
                    __fastfail(3u);
                  *((_QWORD *)v12 + 29) = a1;
                  *((_QWORD *)v12 + 30) = Blink;
                  Blink->Flink = (struct _LIST_ENTRY *)(v12 + 232);
                  a1->Blink = (struct _LIST_ENTRY *)(v12 + 232);
                }
              }
              ((void (__fastcall *)(struct IAppHostElement *))v15->lpVtbl->Release)(v15);
              ++v8;
              v15 = 0;
            }
            while ( v8 < v16 );
          }
          ((void (__fastcall *)(struct IAppHostElementCollection *))v18->lpVtbl->Release)(v18);
          v18 = 0;
          ((void (__fastcall *)(struct IAppHostElement *))v19->lpVtbl->Release)(v19);
          ++v6;
          v19 = 0;
          if ( v6 >= v17 )
            goto LABEL_35;
        }
LABEL_30:
        v2 = 0;
      }
    }
  }
LABEL_31:
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmup.cxx",
      1375,
      "GetPreloadRequests",
      "Error 0x%08x occurred during application preload.\r\n",
      AdminElement);
  if ( v2 )
  {
    STRU::~STRU((STRU *)(v2 + 176));
    STRU::~STRU((STRU *)(v2 + 120));
    STRU::~STRU((STRU *)(v2 + 64));
    STRU::~STRU((STRU *)(v2 + 8));
    operator delete(v2);
  }
LABEL_35:
  if ( v15 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v15->lpVtbl->Release)(v15);
    v15 = 0;
  }
  if ( v18 )
  {
    ((void (__fastcall *)(struct IAppHostElementCollection *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v19->lpVtbl->Release)(v19);
    v19 = 0;
  }
  if ( v22 )
  {
    ((void (__fastcall *)(struct IAppHostElementCollection *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v23->lpVtbl->Release)(v23);
    v23 = 0;
  }
  STRU::~STRU((STRU *)v27);
  STRU::~STRU((STRU *)v24);
  return (unsigned int)AdminElement;
}

```

## disassembly

```asm
0x180003c74  push    rbp
0x180003c76  push    rbx
0x180003c77  push    rsi
0x180003c78  push    rdi
0x180003c79  push    r12
0x180003c7b  push    r13
0x180003c7d  push    r14
0x180003c7f  push    r15
0x180003c81  lea     rbp, [rsp-1Fh]
0x180003c86  sub     rsp, 0E8h
0x180003c8d  mov     rax, cs:__security_cookie
0x180003c94  xor     rax, rsp
0x180003c97  mov     [rbp+57h+var_48], rax
0x180003c9b  xor     esi, esi
0x180003c9d  mov     r15, rcx
0x180003ca0  lea     rcx, [rbp+57h+var_B8]
0x180003ca4  mov     [rbp+57h+var_C0], rsi
0x180003ca8  mov     [rsp+120h+var_D8], rsi
0x180003cad  mov     edi, esi
0x180003caf  mov     [rsp+120h+var_F0], rsi
0x180003cb4  mov     [rbp+57h+var_C8], rsi
0x180003cb8  mov     [rsp+120h+var_E0], rsi
0x180003cbd  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003cc3  lea     rcx, [rbp+57h+var_80]
0x180003cc7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003ccd  mov     rcx, cs:?g_pServer@@3PEAVIHttpServer@@EA; IHttpServer * g_pServer
0x180003cd4  mov     [rsp+120h+var_E4], esi
0x180003cd8  mov     [rsp+120h+var_E8], esi
0x180003cdc  mov     [rbp+57h+var_D0], esi
0x180003cdf  mov     rax, [rcx]
0x180003ce2  mov     [rbp+57h+var_CC], esi
0x180003ce5  mov     rax, [rax+38h]
0x180003ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cee  mov     rcx, rax; struct IAppHostAdminManager *
0x180003cf1  lea     r9, [rbp+57h+var_C0]; struct IAppHostElement **
0x180003cf5  lea     r8, aSystemApplicat; "system.applicationHost/sites"
0x180003cfc  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180003d03  call    ?GetAdminElement@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@@Z; GetAdminElement(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *)
0x180003d08  mov     ebx, eax
0x180003d0a  test    eax, eax
0x180003d0c  js      loc_180003FE7
0x180003d12  mov     rcx, [rbp+57h+var_C0]
0x180003d16  lea     rdx, [rbp+57h+var_C8]
0x180003d1a  mov     rax, [rcx]
0x180003d1d  mov     rax, [rax+20h]
0x180003d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d26  mov     ebx, eax
0x180003d28  test    eax, eax
0x180003d2a  js      loc_180003FE7
0x180003d30  mov     rcx, [rbp+57h+var_C8]
0x180003d34  lea     rdx, [rsp+120h+var_E4]
0x180003d39  mov     rax, [rcx]
0x180003d3c  mov     rax, [rax+18h]
0x180003d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d45  mov     ebx, eax
0x180003d47  test    eax, eax
0x180003d49  js      loc_180003FE7
0x180003d4f  mov     r12d, esi
0x180003d52  cmp     [rsp+120h+var_E4], esi
0x180003d56  jbe     loc_180004059
0x180003d5c  mov     rcx, [rbp+57h+var_C8]; struct IAppHostElementCollection *
0x180003d60  lea     r8, [rsp+120h+var_D8]; struct IAppHostElement **
0x180003d65  mov     edx, r12d; unsigned int
0x180003d68  call    ?GetCollectionElement@@YAJPEAUIAppHostElementCollection@@KPEAPEAUIAppHostElement@@@Z; GetCollectionElement(IAppHostElementCollection *,ulong,IAppHostElement * *)
0x180003d6d  mov     ebx, eax
0x180003d6f  test    eax, eax
0x180003d71  js      loc_180003FE0
0x180003d77  mov     rcx, [rsp+120h+var_D8]; struct IAppHostElement *
0x180003d7c  lea     r8, [rbp+57h+var_D0]; unsigned int *
0x180003d80  call    ?GetConfigDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; GetConfigDWORD(IAppHostElement *,ushort const *,ulong *)
0x180003d85  mov     ebx, eax
0x180003d87  test    eax, eax
0x180003d89  js      loc_180003FE0
0x180003d8f  mov     rcx, [rsp+120h+var_D8]
0x180003d94  lea     rdx, [rsp+120h+var_E0]
0x180003d99  mov     rax, [rcx]
0x180003d9c  mov     rax, [rax+20h]
0x180003da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da5  mov     ebx, eax
0x180003da7  test    eax, eax
0x180003da9  js      loc_180003FE0
0x180003daf  mov     rcx, [rsp+120h+var_E0]
0x180003db4  lea     rdx, [rsp+120h+var_E8]
0x180003db9  mov     rax, [rcx]
0x180003dbc  mov     rax, [rax+18h]
0x180003dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dc5  mov     ebx, eax
0x180003dc7  mov     rdi, rsi
0x180003dca  test    eax, eax
0x180003dcc  js      loc_180003FE7
0x180003dd2  mov     r14d, esi
0x180003dd5  cmp     [rsp+120h+var_E8], esi
0x180003dd9  jbe     loc_180003F8E
0x180003ddf  mov     r13d, [rbp+57h+var_D0]
0x180003de3  mov     rcx, [rsp+120h+var_E0]; struct IAppHostElementCollection *
0x180003de8  lea     r8, [rsp+120h+var_F0]; struct IAppHostElement **
0x180003ded  mov     edx, r14d; unsigned int
0x180003df0  call    ?GetCollectionElement@@YAJPEAUIAppHostElementCollection@@KPEAPEAUIAppHostElement@@@Z; GetCollectionElement(IAppHostElementCollection *,ulong,IAppHostElement * *)
0x180003df5  mov     ebx, eax
0x180003df7  test    eax, eax
0x180003df9  js      loc_180003FE0
0x180003dff  mov     rcx, [rsp+120h+var_F0]; struct IAppHostElement *
0x180003e04  lea     r8, [rbp+57h+var_B8]; struct STRU *
0x180003e08  lea     rdx, aPath; "path"
0x180003e0f  call    ?GetConfigString@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z; GetConfigString(IAppHostElement *,ushort const *,STRU *)
0x180003e14  mov     ebx, eax
0x180003e16  test    eax, eax
0x180003e18  js      loc_180003FE0
0x180003e1e  cmp     [rbp+57h+var_88], 1
0x180003e22  jnz     short loc_180003E2E
0x180003e24  mov     rax, [rbp+57h+var_98]
0x180003e28  mov     [rax], si
0x180003e2b  mov     [rbp+57h+var_88], esi
0x180003e2e  mov     rcx, [rsp+120h+var_F0]; struct IAppHostElement *
0x180003e33  lea     r8, [rbp+57h+var_80]; struct STRU *
0x180003e37  lea     rdx, aApplicationpoo; "applicationPool"
0x180003e3e  call    ?GetConfigString@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z; GetConfigString(IAppHostElement *,ushort const *,STRU *)
0x180003e43  mov     ebx, eax
0x180003e45  test    eax, eax
0x180003e47  js      loc_180003FE0
0x180003e4d  mov     rcx, [rsp+120h+var_F0]; struct IAppHostElement *
0x180003e52  lea     r8, [rbp+57h+var_CC]; int *
0x180003e56  lea     rdx, aPreloadenabled; "preloadEnabled"
0x180003e5d  call    ?GetConfigBool@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; GetConfigBool(IAppHostElement *,ushort const *,int *)
0x180003e62  mov     ebx, eax
0x180003e64  test    eax, eax
0x180003e66  js      loc_180003FE0
0x180003e6c  cmp     [rbp+57h+var_CC], esi
0x180003e6f  jz      loc_180003F67
0x180003e75  mov     rcx, cs:?g_pServer@@3PEAVIHttpServer@@EA; IHttpServer * g_pServer
0x180003e7c  mov     rax, [rcx]
0x180003e7f  mov     rax, [rax+8]
0x180003e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e88  mov     rcx, [rbp+57h+String1]; String1
0x180003e8c  mov     rdx, rax; String2
0x180003e8f  call    cs:__imp__wcsicmp
0x180003e95  test    eax, eax
0x180003e97  jnz     loc_180003F67
0x180003e9d  mov     ecx, 0F8h; Size
0x180003ea2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ea7  mov     rsi, rax
0x180003eaa  test    rax, rax
0x180003ead  jz      loc_180003FD9
0x180003eb3  lea     rcx, [rax+8]
0x180003eb7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003ebd  lea     rcx, [rsi+40h]
0x180003ec1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003ec7  lea     rcx, [rsi+78h]
0x180003ecb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003ed1  lea     rcx, [rsi+0B0h]
0x180003ed8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003ede  lea     rcx, [rsi+4]; void *
0x180003ee2  xor     edx, edx; Val
0x180003ee4  mov     r8d, 0F4h; Size
0x180003eea  call    memset_0
0x180003eef  lea     rcx, [rsi+78h]
0x180003ef3  mov     [rsi], r13d
0x180003ef6  lea     rdx, aLocalhost; "localhost"
0x180003efd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003f03  mov     ebx, eax
0x180003f05  mov     rdi, rsi
0x180003f08  test    eax, eax
0x180003f0a  js      loc_180003FE5
0x180003f10  mov     rdx, [rbp+57h+var_98]
0x180003f14  lea     rcx, [rsi+8]
0x180003f18  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003f1e  mov     ebx, eax
0x180003f20  test    eax, eax
0x180003f22  js      loc_180003FE5
0x180003f28  lea     rcx, [rsi+40h]
0x180003f2c  lea     rdx, asc_180007870; "/"
0x180003f33  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003f39  mov     ebx, eax
0x180003f3b  test    eax, eax
0x180003f3d  js      loc_180003FE5
0x180003f43  mov     rcx, [r15+8]
0x180003f47  cmp     [rcx], r15
0x180003f4a  jnz     loc_180003FD2
0x180003f50  lea     rax, [rsi+0E8h]
0x180003f57  xor     esi, esi
0x180003f59  mov     [rax], r15
0x180003f5c  mov     [rax+8], rcx
0x180003f60  mov     [rcx], rax
0x180003f63  mov     [r15+8], rax
0x180003f67  mov     rcx, [rsp+120h+var_F0]
0x180003f6c  mov     rax, [rcx]
0x180003f6f  mov     rax, [rax+10h]
0x180003f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f78  inc     r14d
0x180003f7b  mov     [rsp+120h+var_F0], rsi
0x180003f80  cmp     r14d, [rsp+120h+var_E8]
0x180003f85  jb      loc_180003DE3
0x180003f8b  mov     rdi, rsi
0x180003f8e  mov     rcx, [rsp+120h+var_E0]
0x180003f93  mov     rax, [rcx]
0x180003f96  mov     rax, [rax+10h]
0x180003f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f9f  mov     rcx, [rsp+120h+var_D8]
0x180003fa4  mov     [rsp+120h+var_E0], rsi
0x180003fa9  mov     rax, [rcx]
0x180003fac  mov     rax, [rax+10h]
0x180003fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb5  inc     r12d
0x180003fb8  mov     [rsp+120h+var_D8], rsi
0x180003fbd  cmp     r12d, [rsp+120h+var_E4]
0x180003fc2  jb      loc_180003D5C
0x180003fc8  test    ebx, ebx
0x180003fca  jns     loc_180004059
0x180003fd0  jmp     short loc_180003FE7
0x180003fd2  mov     ecx, 3
0x180003fd7  int     29h; Win8: RtlFailFast(ecx)
0x180003fd9  mov     ebx, 8007000Eh
0x180003fde  xor     esi, esi
0x180003fe0  mov     rdi, rsi
0x180003fe3  jmp     short loc_180003FE7
0x180003fe5  xor     esi, esi
0x180003fe7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003fee  jz      short loc_180004021
0x180003ff0  mov     rcx, cs:g_pDebug
0x180003ff7  lea     rax, aError0x08xOccu; "Error 0x%08x occurred during applicatio"...
0x180003ffe  mov     [rsp+120h+var_F8], ebx
0x180004002  lea     r9, aGetpreloadrequ; "GetPreloadRequests"
0x180004009  mov     r8d, 55Fh
0x18000400f  mov     [rsp+120h+var_100], rax
0x180004014  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000401b  call    cs:__imp_PuDbgPrint
0x180004021  test    rdi, rdi
0x180004024  jz      short loc_180004059
0x180004026  lea     rcx, [rdi+0B0h]
0x18000402d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004033  lea     rcx, [rdi+78h]
0x180004037  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000403d  lea     rcx, [rdi+40h]
0x180004041  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004047  lea     rcx, [rdi+8]
0x18000404b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004051  mov     rcx, rdi; Block
0x180004054  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004059  mov     rcx, [rsp+120h+var_F0]
0x18000405e  test    rcx, rcx
0x180004061  jz      short loc_180004074
0x180004063  mov     rax, [rcx]
0x180004066  mov     rax, [rax+10h]
0x18000406a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000406f  mov     [rsp+120h+var_F0], rsi
0x180004074  mov     rcx, [rsp+120h+var_E0]
0x180004079  test    rcx, rcx
0x18000407c  jz      short loc_18000408F
0x18000407e  mov     rax, [rcx]
0x180004081  mov     rax, [rax+10h]
0x180004085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000408a  mov     [rsp+120h+var_E0], rsi
0x18000408f  mov     rcx, [rsp+120h+var_D8]
0x180004094  test    rcx, rcx
0x180004097  jz      short loc_1800040AA
0x180004099  mov     rax, [rcx]
0x18000409c  mov     rax, [rax+10h]
0x1800040a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040a5  mov     [rsp+120h+var_D8], rsi
0x1800040aa  mov     rcx, [rbp+57h+var_C8]
0x1800040ae  test    rcx, rcx
0x1800040b1  jz      short loc_1800040C3
0x1800040b3  mov     rax, [rcx]
0x1800040b6  mov     rax, [rax+10h]
0x1800040ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040bf  mov     [rbp+57h+var_C8], rsi
0x1800040c3  mov     rcx, [rbp+57h+var_C0]
0x1800040c7  test    rcx, rcx
0x1800040ca  jz      short loc_1800040DC
0x1800040cc  mov     rax, [rcx]
0x1800040cf  mov     rax, [rax+10h]
0x1800040d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040d8  mov     [rbp+57h+var_C0], rsi
0x1800040dc  lea     rcx, [rbp+57h+var_80]
0x1800040e0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800040e6  lea     rcx, [rbp+57h+var_B8]
0x1800040ea  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800040f0  mov     eax, ebx
0x1800040f2  mov     rcx, [rbp+57h+var_48]
0x1800040f6  xor     rcx, rsp; StackCookie
0x1800040f9  call    __security_check_cookie
0x1800040fe  add     rsp, 0E8h
0x180004105  pop     r15
0x180004107  pop     r14
0x180004109  pop     r13
0x18000410b  pop     r12
0x18000410d  pop     rdi
0x18000410e  pop     rsi
0x18000410f  pop     rbx
0x180004110  pop     rbp
0x180004111  retn
```
