# CMulticastServer::Initialize(void *)

- ea: `0x1800053a0`
- end: `0x180005a45`
- name: `?Initialize@CMulticastServer@@QEAAKPEAX@Z`
- size: `1701`
- prototype: `unsigned int __fastcall(CMulticastServer *__hidden this, void *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180008ff0`

## callees

- `0x1800039a0`
- `0x1800053a0`
- `0x180005e28`
- `0x180005f18`
- `0x18000881c`
- `0x1800089d4`
- `0x180008dcc`
- `0x1800092cc`
- `0x18000aa44`
- `0x180018174`
- `0x18001a9a8`
- `0x18001a9ec`
- `0x1800248d4`
- `0x180024b0c`
- `0x180025850`
- `0x180025ae4`
- `0x180025ba4`
- `0x180026670`
- `0x180026d46`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800055d0`
- `KERNEL32!CreateEventW` at `0x1800055d0`
- `KERNEL32!GetLastError` at `0x180005591`
- `KERNEL32!GetLastError` at `0x1800055e2`
- `KERNEL32!GetLastError` at `0x180005591`
- `KERNEL32!GetLastError` at `0x1800055e2`
- `ADVAPI32!RegisterEventSourceW` at `0x18000557f`
- `ADVAPI32!RegisterEventSourceW` at `0x18000557f`
- `WS2_32!__imp_WSAStartup` at `0x180005468`
- `WS2_32!__imp_WSAStartup` at `0x180005468`
- `WDSSRV!WdsEndpointOpen` at `0x1800057fc`
- `WDSSRV!WdsEndpointOpen` at `0x180005876`
- `WDSSRV!WdsEndpointOpen` at `0x180005918`
- `WDSSRV!WdsEndpointOpen` at `0x1800057fc`
- `WDSSRV!WdsEndpointOpen` at `0x180005876`
- `WDSSRV!WdsEndpointOpen` at `0x180005918`
- `WDSSRV!WdsRegisterCallback` at `0x1800054be`
- `WDSSRV!WdsRegisterCallback` at `0x1800054ed`
- `WDSSRV!WdsRegisterCallback` at `0x18000551d`
- `WDSSRV!WdsRegisterCallback` at `0x1800054be`
- `WDSSRV!WdsRegisterCallback` at `0x1800054ed`
- `WDSSRV!WdsRegisterCallback` at `0x18000551d`
- `WDSCSL!WdsClientInitializeLibrary` at `0x180005547`
- `WDSCSL!WdsClientInitializeLibrary` at `0x180005547`

## string_xrefs

- `0x18000544c`: `onecore\base\eco\wds\wdslib\common\src\winsockinitializer.cpp`
- `0x180005480`: `onecore\base\eco\wds\wdslib\common\src\winsockinitializer.cpp`

## pseudocode

```c
__int64 __fastcall CMulticastServer::Initialize(CMulticastServer *this, void *a2)
{
  unsigned __int16 *v4; // r14
  DWORD LastError; // ebx
  const char *v6; // rdx
  const char *v7; // rdx
  unsigned int v8; // eax
  const char *v9; // rdx
  const char *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  CMRSWLock *v14; // rbx
  HANDLE EventW; // rax
  unsigned int v16; // edx
  DWORD v17; // eax
  const char *v18; // rdx
  const char *v19; // rdx
  const char *v20; // rdx
  const char *v21; // rdx
  const char *v22; // rdx
  struct _GUID *v23; // rdx
  const unsigned __int16 *v24; // r8
  unsigned int v25; // r9d
  const char *v26; // rdx
  const unsigned __int16 *v27; // rdx
  const unsigned __int16 *v28; // rcx
  const char *v29; // rdx
  const char *v30; // rdx
  const char *v31; // rdx
  const char *v32; // rdx
  const char *v33; // rdx
  const char *v34; // rdx
  const char *v35; // rdx
  const char *v36; // rdx
  const char *v37; // rdx
  const char *v38; // rdx
  CMulticastNamespace *v39; // rsi
  CMulticastNamespace *v40; // rcx
  const char *v41; // rdx
  unsigned int v42; // eax
  const char *v43; // rdx
  int v44; // edi
  unsigned int v46; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v47; // [rsp+40h] [rbp-C0h] BYREF
  CMRSWLock *v48; // [rsp+48h] [rbp-B8h] BYREF
  int v49; // [rsp+50h] [rbp-B0h]
  int v50; // [rsp+60h] [rbp-A0h] BYREF
  int v51; // [rsp+64h] [rbp-9Ch]
  int v52; // [rsp+68h] [rbp-98h]
  GUID v53; // [rsp+6Ch] [rbp-94h]
  WSAData WSAData; // [rsp+480h] [rbp+380h] BYREF
  int v55; // [rsp+620h] [rbp+520h] BYREF
  unsigned int (__fastcall *v56)(void *, void *, struct tagWDS_ENDPOINT *, struct tagWDS_ENDPOINT *, void *, unsigned int); // [rsp+628h] [rbp+528h] BYREF
  CMulticastServer *v57; // [rsp+630h] [rbp+530h]
  int v58; // [rsp+658h] [rbp+558h]
  int v59; // [rsp+660h] [rbp+560h]

  memset_0(&v50, 0, 0x41Cu);
  v55 = 0;
  memset_0(&v56, 0, 0x68u);
  *((_QWORD *)this + 36) = a2;
  v4 = 0;
  v48 = (CMulticastServer *)((char *)this + 120);
  v49 = 0;
  v47 = 0;
  LastError = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( !*((_DWORD *)this + 282)
    || (LastError = 1247,
        !ElValidateWin32(0x4DFu, v6, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\winsockinitializer.cpp", 0x6Fu)) )
  {
    v8 = WSAStartup(2u, &WSAData);
    if ( v8 )
    {
      LastError = v8;
      ElValidateWin32(v8, v7, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\winsockinitializer.cpp", 0x7Bu);
    }
    else
    {
      *((_DWORD *)this + 282) = 1;
    }
  }
  if ( !ElValidateWin32(LastError, v7, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x65u) )
  {
    LastError = WdsRegisterCallback(a2, 0, WdsProviderShutdown, 0);
    if ( !ElValidateWin32(LastError, v9, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x70u) )
    {
      LastError = WdsRegisterCallback(a2, 1, CMulticastServer::_RecvRequest, 0);
      if ( !ElValidateWin32(LastError, v10, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x7Bu) )
      {
        LastError = WdsRegisterCallback(a2, 7, CMulticastServer::_ServiceControl, 0);
        if ( !ElValidateWin32(LastError, v11, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x86u) )
        {
          LastError = 0;
          if ( !*((_DWORD *)this + 283) )
          {
            LastError = WdsClientInitializeLibrary();
            *((_DWORD *)this + 283) = LastError == 0;
          }
          if ( !ElValidateWin32(LastError, v12, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x8Du) )
          {
            LastError = 0;
            hEventLog = RegisterEventSourceW(0, L"WDSMC");
            if ( hEventLog )
              word_180033690 = 288;
            else
              LastError = GetLastError();
            if ( !ElValidateWin32(LastError, v13, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x94u) )
            {
              v14 = qword_1800336E8;
              EventW = CreateEventW(0, 0, 0, 0);
              *((_QWORD *)v14 + 119) = EventW;
              if ( EventW )
              {
                LastError = CMRSWLock::Initialize((CMRSWLock *)((char *)v14 + 960), v16);
                ElValidateWin32(LastError, v20, "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h", 0xD9u);
              }
              else
              {
                v17 = GetLastError();
                LastError = ElValidateWin32(
                              v17,
                              v18,
                              "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h",
                              0xD5u);
                if ( !LastError )
                  LastError = 31;
              }
              ElValidateWin32(LastError, v19, "base\\eco\\wds\\transport\\server\\mc\\mcnotification.cpp", 0x8Au);
              if ( !ElValidateWin32(LastError, v21, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x9Bu) )
              {
                LastError = CMulticastPerfCounters::InitializeServer((CMulticastPerfCounters *)&qword_1800336A0);
                if ( !ElValidateWin32(LastError, v22, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0xA2u) )
                {
                  LastError = CCryptStore::Initialize((HCRYPTPROV *)this + 107, v23, v24, v25);
                  if ( !ElValidateWin32(LastError, v26, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0xA9u) )
                  {
                    LastError = CWdsTptNamespaceStore::CreateInstance(
                                  v28,
                                  v27,
                                  (struct CWdsTptNamespaceStore **)this + 106);
                    if ( !ElValidateWin32(LastError, v29, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0xB0u) )
                    {
                      LastError = CMulticastServer::ReadParameters(this);
                      if ( !ElValidateWin32(
                              LastError,
                              v30,
                              "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                              0xB7u) )
                      {
                        LastError = CCryptKey::GenerateKey(
                                      (CMulticastServer *)((char *)this + 1080),
                                      (CMulticastServer *)((char *)this + 856),
                                      2u,
                                      *((_DWORD *)this + 94),
                                      v46);
                        if ( !ElValidateWin32(
                                LastError,
                                v31,
                                "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                0xBEu) )
                        {
                          LastError = CContentProvidersHandler::Initialize((CMulticastServer *)((char *)this + 536));
                          if ( !ElValidateWin32(
                                  LastError,
                                  v32,
                                  "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                  0xC5u) )
                          {
                            LastError = CBandwidthManager::UpdateSettings((LPCRITICAL_SECTION)this + 14);
                            if ( !ElValidateWin32(
                                    LastError,
                                    v33,
                                    "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                    0xCCu) )
                            {
                              LastError = CMulticastServer::RegisterNamespaces(this);
                              if ( !ElValidateWin32(
                                      LastError,
                                      v34,
                                      "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                      0xD3u) )
                              {
                                v50 = 1052;
                                v51 = 1;
                                v56 = CMulticastServer::_ManagementRequest;
                                v52 = 1;
                                v55 = 66567;
                                v57 = this;
                                v53 = WDSMC_MGMT_ENDPOINT;
                                v58 = 197124;
                                v59 = 1;
                                LastError = WdsEndpointOpen(a2, &v50, 2, &v55, (char *)this + 296);
                                if ( !ElValidateWin32(
                                        LastError,
                                        v35,
                                        "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                        0xECu) )
                                {
                                  v50 = 1052;
                                  v56 = CMulticastServer::_ClientRequest;
                                  v51 = 1;
                                  v52 = 1;
                                  v55 = 66567;
                                  v53 = WDSMC_CLIENT_ENDPOINT;
                                  v57 = this;
                                  LastError = WdsEndpointOpen(a2, &v50, 1, &v55, (char *)this + 304);
                                  if ( !ElValidateWin32(
                                          LastError,
                                          v36,
                                          "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                          0x102u) )
                                  {
                                    if ( !*((_DWORD *)this + 118) )
                                      goto LABEL_51;
                                    memset_0(&v50, 0, 0x41Cu);
                                    v51 = 0;
                                    v50 = 1052;
                                    LOWORD(v53.Data1) = 5041;
                                    v55 = 66567;
                                    v56 = CMulticastServer::_ClientUdpRequest;
                                    v57 = this;
                                    v58 = 524548;
                                    v59 = 1;
                                    LastError = WdsEndpointOpen(a2, &v50, 2, &v55, (char *)this + 312);
                                    if ( !ElValidateWin32(
                                            LastError,
                                            v37,
                                            "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                            0x11Cu) )
                                    {
LABEL_51:
                                      LastError = CTimer<CMulticastServer>::Initialize((char *)this + 480);
                                      if ( !ElValidateWin32(
                                              LastError,
                                              v38,
                                              "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                              0x124u) )
                                      {
                                        CAutoWriterLock::Lock((CAutoWriterLock *)&v48);
                                        v39 = (CMulticastNamespace *)*((_QWORD *)this + 103);
                                        while ( v39 )
                                        {
                                          v40 = v39;
                                          v39 = (CMulticastNamespace *)*((_QWORD *)v39 + 57);
                                          LastError = CMulticastNamespace::GetName(v40, &v47);
                                          v42 = ElValidateWin32(
                                                  LastError,
                                                  v41,
                                                  "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                                  0x133u);
                                          v4 = v47;
                                          if ( v42
                                            || (LastError = CDynArray<unsigned short *,CDeallocateString>::AddItem(
                                                              (char *)this + 1104,
                                                              v47),
                                                ElValidateWin32(
                                                  LastError,
                                                  v43,
                                                  "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp",
                                                  0x137u)) )
                                          {
                                            v44 = v49;
LABEL_43:
                                            if ( v4 )
                                              operator delete(v4);
                                            goto LABEL_45;
                                          }
                                          v4 = 0;
                                          v47 = 0;
                                        }
                                        if ( !v49 )
                                          return LastError;
                                        v44 = v49 - 1;
                                        if ( v49 == 1 )
                                        {
                                          CMRSWLock::WriterRelease(v48);
                                          goto LABEL_43;
                                        }
LABEL_45:
                                        if ( v44 == 1 )
                                          CMRSWLock::WriterRelease(v48);
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800053a0  mov     [rsp-8+arg_10], rbx
0x1800053a5  mov     [rsp-8+arg_18], rsi
0x1800053aa  push    rbp
0x1800053ab  push    rdi
0x1800053ac  push    r13
0x1800053ae  push    r14
0x1800053b0  push    r15
0x1800053b2  lea     rbp, [rsp-5A0h]
0x1800053ba  sub     rsp, 6A0h
0x1800053c1  mov     rax, cs:__security_cookie
0x1800053c8  xor     rax, rsp
0x1800053cb  mov     [rbp+5C0h+var_30], rax
0x1800053d2  mov     r15, rdx
0x1800053d5  mov     rdi, rcx
0x1800053d8  xor     edx, edx; Val
0x1800053da  lea     rcx, [rsp+6C0h+var_660]; void *
0x1800053df  mov     r8d, 41Ch; Size
0x1800053e5  call    memset_0
0x1800053ea  and     [rbp+5C0h+var_A0], 0
0x1800053f1  lea     rcx, [rbp+5C0h+var_98]; void *
0x1800053f8  xor     edx, edx; Val
0x1800053fa  lea     r8d, [rdx+68h]; Size
0x1800053fe  call    memset_0
0x180005403  lea     rax, [rdi+78h]
0x180005407  mov     [rdi+120h], r15
0x18000540e  xor     r14d, r14d
0x180005411  mov     [rsp+6C0h+var_678], rax
0x180005416  and     [rsp+6C0h+var_670], r14d
0x18000541b  lea     rcx, [rbp+5C0h+WSAData]; void *
0x180005422  xor     edx, edx; Val
0x180005424  mov     [rsp+6C0h+var_680], r14
0x180005429  mov     r8d, 198h; Size
0x18000542f  xor     ebx, ebx
0x180005431  call    memset_0
0x180005436  lea     esi, [rbx+1]
0x180005439  cmp     [rdi+468h], ebx
0x18000543f  jz      short loc_18000545C
0x180005441  mov     ebx, 4DFh
0x180005446  lea     r9d, [r14+6Fh]; unsigned int
0x18000544a  mov     ecx, ebx; unsigned int
0x18000544c  lea     r8, aOnecoreBaseEco_2; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180005453  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005458  test    eax, eax
0x18000545a  jnz     short loc_180005490
0x18000545c  mov     ecx, 2; wVersionRequested
0x180005461  lea     rdx, [rbp+5C0h+WSAData]; lpWSAData
0x180005468  call    cs:__imp_WSAStartup
0x18000546e  test    eax, eax
0x180005470  jnz     short loc_18000547A
0x180005472  mov     [rdi+468h], esi
0x180005478  jmp     short loc_180005490
0x18000547a  mov     r9d, 7Bh ; '{'; unsigned int
0x180005480  lea     r8, aOnecoreBaseEco_2; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180005487  mov     ecx, eax; unsigned int
0x180005489  mov     ebx, eax
0x18000548b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005490  lea     r13, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005497  mov     r9d, 65h ; 'e'; unsigned int
0x18000549d  mov     r8, r13; char *
0x1800054a0  mov     ecx, ebx; unsigned int
0x1800054a2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800054a7  test    eax, eax
0x1800054a9  jnz     loc_180005A12
0x1800054af  xor     r9d, r9d
0x1800054b2  lea     r8, ?WdsProviderShutdown@@YAKPEAX@Z; WdsProviderShutdown(void *)
0x1800054b9  xor     edx, edx
0x1800054bb  mov     rcx, r15
0x1800054be  call    cs:__imp_WdsRegisterCallback
0x1800054c4  mov     r9d, 70h ; 'p'; unsigned int
0x1800054ca  mov     r8, r13; char *
0x1800054cd  mov     ecx, eax; unsigned int
0x1800054cf  mov     ebx, eax
0x1800054d1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800054d6  test    eax, eax
0x1800054d8  jnz     loc_180005A12
0x1800054de  xor     r9d, r9d
0x1800054e1  lea     r8, ?_RecvRequest@CMulticastServer@@SAKPEAX0PEAUtagWDS_ENDPOINT@@10K@Z; CMulticastServer::_RecvRequest(void *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)
0x1800054e8  mov     edx, esi
0x1800054ea  mov     rcx, r15
0x1800054ed  call    cs:__imp_WdsRegisterCallback
0x1800054f3  mov     r9d, 7Bh ; '{'; unsigned int
0x1800054f9  mov     r8, r13; char *
0x1800054fc  mov     ecx, eax; unsigned int
0x1800054fe  mov     ebx, eax
0x180005500  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005505  test    eax, eax
0x180005507  jnz     loc_180005A12
0x18000550d  xor     r9d, r9d
0x180005510  lea     r8, ?_ServiceControl@CMulticastServer@@SAXPEAXK@Z; CMulticastServer::_ServiceControl(void *,ulong)
0x180005517  lea     edx, [rax+7]
0x18000551a  mov     rcx, r15
0x18000551d  call    cs:__imp_WdsRegisterCallback
0x180005523  mov     r9d, 86h; unsigned int
0x180005529  mov     r8, r13; char *
0x18000552c  mov     ecx, eax; unsigned int
0x18000552e  mov     ebx, eax
0x180005530  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005535  test    eax, eax
0x180005537  jnz     loc_180005A12
0x18000553d  xor     ebx, ebx
0x18000553f  cmp     [rdi+46Ch], ebx
0x180005545  jnz     short loc_18000555C
0x180005547  call    cs:__imp_WdsClientInitializeLibrary
0x18000554d  mov     ebx, eax
0x18000554f  xor     eax, eax
0x180005551  test    ebx, ebx
0x180005553  setz    al
0x180005556  mov     [rdi+46Ch], eax
0x18000555c  mov     r9d, 8Dh; unsigned int
0x180005562  mov     r8, r13; char *
0x180005565  mov     ecx, ebx; unsigned int
0x180005567  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000556c  test    eax, eax
0x18000556e  jnz     loc_180005A12
0x180005574  lea     rdx, SourceName; "WDSMC"
0x18000557b  xor     ecx, ecx; lpUNCServerName
0x18000557d  xor     ebx, ebx
0x18000557f  call    cs:__imp_RegisterEventSourceW
0x180005585  mov     cs:hEventLog, rax
0x18000558c  test    rax, rax
0x18000558f  jnz     short loc_18000559B
0x180005591  call    cs:__imp_GetLastError
0x180005597  mov     ebx, eax
0x180005599  jmp     short loc_1800055A7
0x18000559b  mov     eax, 120h
0x1800055a0  mov     cs:word_180033690, ax
0x1800055a7  mov     r9d, 94h; unsigned int
0x1800055ad  mov     r8, r13; char *
0x1800055b0  mov     ecx, ebx; unsigned int
0x1800055b2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800055b7  test    eax, eax
0x1800055b9  jnz     loc_180005A12
0x1800055bf  mov     rbx, cs:qword_1800336E8
0x1800055c6  xor     r9d, r9d; lpName
0x1800055c9  xor     r8d, r8d; bInitialState
0x1800055cc  xor     edx, edx; bManualReset
0x1800055ce  xor     ecx, ecx; lpEventAttributes
0x1800055d0  call    cs:__imp_CreateEventW
0x1800055d6  mov     [rbx+3B8h], rax
0x1800055dd  test    rax, rax
0x1800055e0  jnz     short loc_180005607
0x1800055e2  call    cs:__imp_GetLastError
0x1800055e8  mov     r9d, 0D5h; unsigned int
0x1800055ee  lea     r8, aInternalOnecor; "internal\\onecorebase\\private\\inc\\ec"...
0x1800055f5  mov     ecx, eax; unsigned int
0x1800055f7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800055fc  mov     ebx, eax
0x1800055fe  test    eax, eax
0x180005600  jnz     short loc_180005629
0x180005602  lea     ebx, [rax+1Fh]
0x180005605  jmp     short loc_180005629
0x180005607  lea     rcx, [rbx+3C0h]; this
0x18000560e  call    ?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x180005613  mov     r9d, 0D9h; unsigned int
0x180005619  lea     r8, aInternalOnecor; "internal\\onecorebase\\private\\inc\\ec"...
0x180005620  mov     ecx, eax; unsigned int
0x180005622  mov     ebx, eax
0x180005624  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005629  mov     r9d, 8Ah; unsigned int
0x18000562f  lea     r8, aBaseEcoWdsTran_1; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005636  mov     ecx, ebx; unsigned int
0x180005638  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000563d  mov     r9d, 9Bh; unsigned int
0x180005643  mov     r8, r13; char *
0x180005646  mov     ecx, ebx; unsigned int
0x180005648  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000564d  test    eax, eax
0x18000564f  jnz     loc_180005A12
0x180005655  lea     rcx, qword_1800336A0; this
0x18000565c  call    ?InitializeServer@CMulticastPerfCounters@@QEAAKXZ; CMulticastPerfCounters::InitializeServer(void)
0x180005661  mov     r9d, 0A2h; unsigned int
0x180005667  mov     r8, r13; char *
0x18000566a  mov     ecx, eax; unsigned int
0x18000566c  mov     ebx, eax
0x18000566e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005673  test    eax, eax
0x180005675  jnz     loc_180005A12
0x18000567b  lea     rsi, [rdi+358h]
0x180005682  mov     rcx, rsi; phProv
0x180005685  call    ?Initialize@CCryptStore@@QEAAKPEAU_GUID@@PEBGK@Z; CCryptStore::Initialize(_GUID *,ushort const *,ulong)
0x18000568a  mov     r9d, 0A9h; unsigned int
0x180005690  mov     r8, r13; char *
0x180005693  mov     ecx, eax; unsigned int
0x180005695  mov     ebx, eax
0x180005697  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000569c  test    eax, eax
0x18000569e  jnz     loc_180005A12
0x1800056a4  lea     r8, [rdi+350h]; struct CWdsTptNamespaceStore **
0x1800056ab  call    ?CreateInstance@CWdsTptNamespaceStore@@SAKPEBG0PEAPEAV1@@Z; CWdsTptNamespaceStore::CreateInstance(ushort const *,ushort const *,CWdsTptNamespaceStore * *)
0x1800056b0  mov     r9d, 0B0h; unsigned int
0x1800056b6  mov     r8, r13; char *
0x1800056b9  mov     ecx, eax; unsigned int
0x1800056bb  mov     ebx, eax
0x1800056bd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800056c2  test    eax, eax
0x1800056c4  jnz     loc_180005A12
0x1800056ca  mov     rcx, rdi; this
0x1800056cd  call    ?ReadParameters@CMulticastServer@@AEAAKXZ; CMulticastServer::ReadParameters(void)
0x1800056d2  mov     r9d, 0B7h; unsigned int
0x1800056d8  mov     r8, r13; char *
0x1800056db  mov     ecx, eax; unsigned int
0x1800056dd  mov     ebx, eax
0x1800056df  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800056e4  test    eax, eax
0x1800056e6  jnz     loc_180005A12
0x1800056ec  mov     r9d, [rdi+178h]; unsigned int
0x1800056f3  lea     rcx, [rdi+438h]; this
0x1800056fa  lea     r8d, [rax+2]; unsigned int
0x1800056fe  mov     rdx, rsi; struct CCryptStore *
0x180005701  call    ?GenerateKey@CCryptKey@@QEAAKPEAVCCryptStore@@IKK@Z; CCryptKey::GenerateKey(CCryptStore *,uint,ulong,ulong)
0x180005706  mov     r9d, 0BEh; unsigned int
0x18000570c  mov     r8, r13; char *
0x18000570f  mov     ecx, eax; unsigned int
0x180005711  mov     ebx, eax
0x180005713  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005718  test    eax, eax
0x18000571a  jnz     loc_180005A12
0x180005720  lea     rcx, [rdi+218h]; this
0x180005727  call    ?Initialize@CContentProvidersHandler@@QEAAKXZ; CContentProvidersHandler::Initialize(void)
0x18000572c  mov     r9d, 0C5h; unsigned int
0x180005732  mov     r8, r13; char *
0x180005735  mov     ecx, eax; unsigned int
0x180005737  mov     ebx, eax
0x180005739  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000573e  test    eax, eax
0x180005740  jnz     loc_180005A12
0x180005746  lea     rcx, [rdi+230h]; lpCriticalSection
0x18000574d  call    ?UpdateSettings@CBandwidthManager@@QEAAKXZ; CBandwidthManager::UpdateSettings(void)
0x180005752  mov     r9d, 0CCh; unsigned int
0x180005758  mov     r8, r13; char *
0x18000575b  mov     ecx, eax; unsigned int
0x18000575d  mov     ebx, eax
0x18000575f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005764  test    eax, eax
0x180005766  jnz     loc_180005A12
0x18000576c  mov     rcx, rdi; this
0x18000576f  call    ?RegisterNamespaces@CMulticastServer@@QEAAKXZ; CMulticastServer::RegisterNamespaces(void)
0x180005774  mov     r9d, 0D3h; unsigned int
0x18000577a  mov     r8, r13; char *
0x18000577d  mov     ecx, eax; unsigned int
0x18000577f  mov     ebx, eax
0x180005781  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005786  test    eax, eax
0x180005788  jnz     loc_180005A12
0x18000578e  movups  xmm0, xmmword ptr cs:?WDSMC_MGMT_ENDPOINT@@3U_GUID@@B.Data1; _GUID const WDSMC_MGMT_ENDPOINT ...
0x180005795  lea     esi, [rax+1]
0x180005798  mov     [rsp+6C0h+var_660], 41Ch
0x1800057a0  lea     rax, ?_ManagementRequest@CMulticastServer@@SAKPEAX0PEAUtagWDS_ENDPOINT@@10K@Z; CMulticastServer::_ManagementRequest(void *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)
0x1800057a7  mov     [rsp+6C0h+var_65C], esi
0x1800057ab  mov     [rbp+5C0h+var_98], rax
0x1800057b2  lea     r9, [rbp+5C0h+var_A0]
0x1800057b9  lea     rax, [rdi+128h]
0x1800057c0  mov     [rsp+6C0h+var_658], esi
0x1800057c4  lea     r8d, [rsi+1]
0x1800057c8  mov     qword ptr [rsp+6C0h+var_6A0], rax
0x1800057cd  lea     rdx, [rsp+6C0h+var_660]
0x1800057d2  mov     [rbp+5C0h+var_A0], 10407h
0x1800057dc  mov     rcx, r15
0x1800057df  mov     [rbp+5C0h+var_90], rdi
0x1800057e6  movdqu  [rsp+6C0h+var_654], xmm0
0x1800057ec  mov     [rbp+5C0h+var_68], 30204h
0x1800057f6  mov     [rbp+5C0h+var_60], esi
0x1800057fc  call    cs:__imp_WdsEndpointOpen
0x180005802  mov     r9d, 0ECh; unsigned int
0x180005808  mov     r8, r13; char *
0x18000580b  mov     ecx, eax; unsigned int
0x18000580d  mov     ebx, eax
0x18000580f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005814  test    eax, eax
0x180005816  jnz     loc_180005A12
0x18000581c  movups  xmm0, xmmword ptr cs:?WDSMC_CLIENT_ENDPOINT@@3U_GUID@@B.Data1; _GUID const WDSMC_CLIENT_ENDPOINT ...
0x180005823  lea     rax, ?_ClientRequest@CMulticastServer@@SAKPEAX0PEAUtagWDS_ENDPOINT@@10K@Z; CMulticastServer::_ClientRequest(void *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)
0x18000582a  mov     [rsp+6C0h+var_660], 41Ch
0x180005832  mov     [rbp+5C0h+var_98], rax
0x180005839  lea     r9, [rbp+5C0h+var_A0]
0x180005840  lea     rax, [rdi+130h]
0x180005847  mov     [rsp+6C0h+var_65C], esi
0x18000584b  mov     r8d, esi
0x18000584e  mov     qword ptr [rsp+6C0h+var_6A0], rax
0x180005853  lea     rdx, [rsp+6C0h+var_660]
0x180005858  mov     [rsp+6C0h+var_658], esi
0x18000585c  mov     rcx, r15
0x18000585f  mov     [rbp+5C0h+var_A0], 10407h
0x180005869  movdqu  [rsp+6C0h+var_654], xmm0
0x18000586f  mov     [rbp+5C0h+var_90], rdi
0x180005876  call    cs:__imp_WdsEndpointOpen
0x18000587c  mov     r9d, 102h; unsigned int
0x180005882  mov     r8, r13; char *
0x180005885  mov     ecx, eax; unsigned int
0x180005887  mov     ebx, eax
0x180005889  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000588e  test    eax, eax
0x180005890  jnz     loc_180005A12
0x180005896  cmp     [rdi+1D8h], r14d
0x18000589d  jz      loc_180005938
0x1800058a3  mov     ebx, 41Ch
0x1800058a8  lea     rcx, [rsp+6C0h+var_660]; void *
0x1800058ad  mov     r8d, ebx; Size
0x1800058b0  xor     edx, edx; Val
0x1800058b2  call    memset_0
  ... truncated ...
```
