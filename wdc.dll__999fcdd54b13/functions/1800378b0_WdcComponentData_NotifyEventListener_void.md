# WdcComponentData::NotifyEventListener(void *)

- ea: `0x1800378b0`
- end: `0x180037d55`
- name: `?NotifyEventListener@WdcComponentData@@CAKPEAX@Z`
- size: `1189`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x1800378b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180037cc7`
- `KERNEL32!CloseHandle` at `0x180037cc7`
- `KERNEL32!GetLastError` at `0x180037971`
- `KERNEL32!GetLastError` at `0x1800379d8`
- `KERNEL32!GetLastError` at `0x180037a5a`
- `KERNEL32!GetLastError` at `0x180037a79`
- `KERNEL32!GetLastError` at `0x180037b33`
- `KERNEL32!GetLastError` at `0x180037b5a`
- `KERNEL32!GetLastError` at `0x180037ba9`
- `KERNEL32!GetLastError` at `0x180037bd0`
- `KERNEL32!GetLastError` at `0x180037c1e`
- `KERNEL32!GetLastError` at `0x180037c7c`
- `KERNEL32!GetLastError` at `0x180037d31`
- `KERNEL32!GetLastError` at `0x180037971`
- `KERNEL32!GetLastError` at `0x1800379d8`
- `KERNEL32!GetLastError` at `0x180037a5a`
- `KERNEL32!GetLastError` at `0x180037a79`
- `KERNEL32!GetLastError` at `0x180037b33`
- `KERNEL32!GetLastError` at `0x180037b5a`
- `KERNEL32!GetLastError` at `0x180037ba9`
- `KERNEL32!GetLastError` at `0x180037bd0`
- `KERNEL32!GetLastError` at `0x180037c1e`
- `KERNEL32!GetLastError` at `0x180037c7c`
- `KERNEL32!GetLastError` at `0x180037d31`
- `KERNEL32!LeaveCriticalSection` at `0x180037d3e`
- `KERNEL32!LeaveCriticalSection` at `0x180037d3e`
- `KERNEL32!EnterCriticalSection` at `0x180037d10`
- `KERNEL32!EnterCriticalSection` at `0x180037d10`
- `KERNEL32!CreateEventW` at `0x18003795d`
- `KERNEL32!CreateEventW` at `0x18003795d`
- `KERNEL32!ResetEvent` at `0x180037bf3`
- `KERNEL32!ResetEvent` at `0x180037d47`
- `KERNEL32!ResetEvent` at `0x180037bf3`
- `KERNEL32!ResetEvent` at `0x180037d47`
- `KERNEL32!WaitForMultipleObjects` at `0x180037c64`
- `KERNEL32!WaitForMultipleObjects` at `0x180037c64`
- `USER32!PostThreadMessageW` at `0x180037d27`
- `USER32!PostThreadMessageW` at `0x180037d27`
- `USER32!SendMessageTimeoutW` at `0x180037abe`
- `USER32!SendMessageTimeoutW` at `0x180037abe`
- `wevtapi!EvtOpenSession` at `0x1800379ca`
- `wevtapi!EvtOpenSession` at `0x1800379ca`
- `wevtapi!EvtSubscribe` at `0x180037a4b`
- `wevtapi!EvtSubscribe` at `0x180037a4b`
- `wevtapi!EvtCreateRenderContext` at `0x180037b24`
- `wevtapi!EvtCreateRenderContext` at `0x180037b9a`
- `wevtapi!EvtCreateRenderContext` at `0x180037b24`
- `wevtapi!EvtCreateRenderContext` at `0x180037b9a`
- `wevtapi!EvtOpenPublisherMetadata` at `0x180037c10`
- `wevtapi!EvtOpenPublisherMetadata` at `0x180037c10`
- `wevtapi!EvtNext` at `0x180037ae5`
- `wevtapi!EvtNext` at `0x180037ae5`
- `wevtapi!EvtClose` at `0x180037a16`
- `wevtapi!EvtClose` at `0x180037af9`
- `wevtapi!EvtClose` at `0x180037b0f`
- `wevtapi!EvtClose` at `0x180037b88`
- `wevtapi!EvtClose` at `0x180037cda`
- `wevtapi!EvtClose` at `0x180037ced`
- `wevtapi!EvtClose` at `0x180037a16`
- `wevtapi!EvtClose` at `0x180037af9`
- `wevtapi!EvtClose` at `0x180037b0f`
- `wevtapi!EvtClose` at `0x180037b88`
- `wevtapi!EvtClose` at `0x180037cda`
- `wevtapi!EvtClose` at `0x180037ced`

## string_xrefs

- `0x18003793f`: `base\diagnosis\pdui\perfmon\mmc\componentdata.cpp`
- `0x180037cae`: `base\diagnosis\pdui\perfmon\mmc\componentdata.cpp`
- `0x180037938`: `WdcComponentData::NotifyEventListener`
- `0x180037ca7`: `WdcComponentData::NotifyEventListener`

## pseudocode

```c
__int64 __fastcall WdcComponentData::NotifyEventListener(WPARAM Parameter, const char *a2, int a3)
{
  void *v4; // rcx
  void *v5; // rax
  signed int v6; // ebx
  char *EventW; // rax
  char *v8; // rsi
  signed int LastError; // eax
  char *v10; // r14
  char *v11; // rax
  char *v12; // r15
  signed int v13; // eax
  char *v14; // rcx
  EVT_HANDLE v15; // rax
  signed int v16; // eax
  signed int v17; // eax
  char *v18; // rcx
  EVT_HANDLE v19; // rax
  signed int v20; // eax
  signed int v21; // eax
  char *v22; // rcx
  EVT_HANDLE RenderContext; // rax
  signed int v24; // eax
  signed int v25; // eax
  char *v26; // rax
  signed int v27; // eax
  DWORD v28; // eax
  signed int v29; // eax
  EVT_HANDLE Bookmark; // [rsp+20h] [rbp-49h]
  int Bookmarka; // [rsp+20h] [rbp-49h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-29h] BYREF
  _OWORD Login[7]; // [rsp+50h] [rbp-19h] BYREF
  DWORD Returned; // [rsp+D0h] [rbp+67h] BYREF
  HANDLE Events; // [rsp+D8h] [rbp+6Fh] BYREF
  ULONG_PTR dwResult; // [rsp+E0h] [rbp+77h] BYREF
  LPCWSTR ValuePaths; // [rsp+E8h] [rbp+7Fh] BYREF

  Returned = 0;
  v4 = *(void **)(Parameter + 56);
  ValuePaths = L"Event/System/EventID";
  Events = 0;
  dwResult = 0;
  *(_OWORD *)Handles = 0;
  memset(Login, 0, 40);
  if ( v4 )
  {
    WdcFree(v4, a2, a3);
    *(_QWORD *)(Parameter + 56) = 0;
  }
  v5 = WdcAlloc(0x400u, a2, a3);
  *(_QWORD *)(Parameter + 56) = v5;
  if ( !v5 )
  {
    v6 = -2147024882;
    Bookmarka = -2147024882;
LABEL_5:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\componentdata.cpp",
      "WdcComponentData::NotifyEventListener",
      0,
      L"FAILURE: 0x%08x",
      Bookmarka);
    return (unsigned int)v6;
  }
  *(_DWORD *)(Parameter + 64) = 1024;
  EventW = (char *)CreateEventW(0, 0, 0, 0);
  v8 = EventW;
  if ( !EventW || (v6 = 0, EventW == (char *)-1LL) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_15;
    }
    else
    {
      v6 = -2147467259;
    }
    Bookmarka = v6;
    goto LABEL_5;
  }
LABEL_15:
  *(_QWORD *)&Login[0] = *(_QWORD *)(Parameter + 48);
  v10 = 0;
  memset((char *)Login + 8, 0, 32);
  v11 = (char *)EvtOpenSession(EvtRpcLogin, Login, 0, 0);
  v12 = v11;
  if ( !v11 || v11 == (char *)-1LL )
  {
    v13 = GetLastError();
    v6 = v13;
    if ( !v13 )
      goto LABEL_21;
    if ( v13 > 0 )
      v6 = (unsigned __int16)v13 | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_22;
  }
  v14 = *(char **)(Parameter + 40);
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    EvtClose(v14);
    *(_QWORD *)(Parameter + 40) = 0;
  }
  v15 = EvtSubscribe(v12, v8, L"Microsoft-Windows-Diagnosis-PLA/Operational", L"*", 0, 0, 0, 1u);
  *(_QWORD *)(Parameter + 40) = v15;
  if ( !v15 )
  {
    v16 = GetLastError();
    v6 = v16;
    if ( !v16 )
      goto LABEL_21;
    if ( v16 > 0 )
      v6 = (unsigned __int16)v16 | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_22;
  }
  if ( *(_QWORD *)(Parameter + 40) == -1 )
  {
    v17 = GetLastError();
    v6 = v17;
    if ( !v17 )
      goto LABEL_21;
    if ( v17 > 0 )
      v6 = (unsigned __int16)v17 | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_22;
  }
  SendMessageTimeoutW(*(HWND *)(Parameter + 80), 0, 0, 0, 1u, 0x3A98u, &dwResult);
  while ( EvtNext(*(EVT_HANDLE *)(Parameter + 40), 1u, &Events, 0, 0, &Returned) && Returned == 1 )
    EvtClose(Events);
  v18 = *(char **)(Parameter + 24);
  if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    EvtClose(v18);
    *(_QWORD *)(Parameter + 24) = 0;
  }
  v19 = EvtCreateRenderContext(1u, &ValuePaths, 0);
  *(_QWORD *)(Parameter + 24) = v19;
  if ( !v19 )
  {
    v20 = GetLastError();
    v6 = v20;
    if ( !v20 )
      goto LABEL_21;
    if ( v20 > 0 )
      v6 = (unsigned __int16)v20 | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_22;
  }
  if ( *(_QWORD *)(Parameter + 24) == -1 )
  {
    v21 = GetLastError();
    v6 = v21;
    if ( !v21 )
      goto LABEL_21;
    if ( v21 > 0 )
      v6 = (unsigned __int16)v21 | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_22;
  }
  v22 = *(char **)(Parameter + 32);
  if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    EvtClose(v22);
    *(_QWORD *)(Parameter + 32) = 0;
  }
  RenderContext = EvtCreateRenderContext(0, 0, 2u);
  *(_QWORD *)(Parameter + 32) = RenderContext;
  if ( !RenderContext )
  {
    v24 = GetLastError();
    v6 = v24;
    if ( !v24 )
      goto LABEL_21;
    if ( v24 > 0 )
      v6 = (unsigned __int16)v24 | 0x80070000;
    if ( v6 < 0 )
    {
LABEL_22:
      LODWORD(Bookmark) = v6;
LABEL_81:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\componentdata.cpp",
        "WdcComponentData::NotifyEventListener",
        0,
        L"FAILURE: 0x%08x",
        Bookmark);
      goto LABEL_82;
    }
  }
  if ( *(_QWORD *)(Parameter + 32) != -1 )
    goto LABEL_64;
  v25 = GetLastError();
  v6 = v25;
  if ( !v25 )
  {
LABEL_21:
    v6 = -2147467259;
    goto LABEL_22;
  }
  if ( v25 > 0 )
    v6 = (unsigned __int16)v25 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_22;
LABEL_64:
  ResetEvent(v8);
  v26 = (char *)EvtOpenPublisherMetadata(0, L"Microsoft-Windows-Diagnosis-PLA", 0, 0x400u, 0);
  v10 = v26;
  if ( v26 && v26 != (char *)-1LL )
    goto LABEL_71;
  v27 = GetLastError();
  v6 = v27;
  if ( !v27 )
    goto LABEL_21;
  if ( v27 > 0 )
    v6 = (unsigned __int16)v27 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_22;
LABEL_71:
  Handles[1] = *(HANDLE *)(Parameter + 8);
  Handles[0] = v8;
  while ( 1 )
  {
    while ( 1 )
    {
      v28 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( v28 )
        break;
      EnterCriticalSection(&g_cs);
      if ( !PostThreadMessageW(*(_DWORD *)Parameter, 0x113u, Parameter, (LPARAM)WdcComponentData::NotifyEvent) )
        GetLastError();
      LeaveCriticalSection(&g_cs);
      ResetEvent(v8);
      v6 = 0;
    }
    if ( v28 == 1 )
      break;
    if ( v28 == -1 )
    {
      v29 = GetLastError();
      v6 = 0;
      if ( v29 )
      {
        if ( v29 > 0 )
          v6 = (unsigned __int16)v29 | 0x80070000;
        else
          v6 = v29;
      }
      if ( v6 < 0 )
      {
        LODWORD(Bookmark) = v6;
        goto LABEL_81;
      }
    }
  }
LABEL_82:
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    EvtClose(v12);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    EvtClose(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800378b0  push    rbp
0x1800378b2  push    rbx
0x1800378b3  push    rsi
0x1800378b4  push    rdi
0x1800378b5  push    r12
0x1800378b7  push    r13
0x1800378b9  push    r14
0x1800378bb  push    r15
0x1800378bd  lea     rbp, [rsp-1Fh]
0x1800378c2  sub     rsp, 88h
0x1800378c9  xor     r12d, r12d
0x1800378cc  xor     eax, eax
0x1800378ce  xorps   xmm1, xmm1
0x1800378d1  mov     [rbp+57h+var_50], rax
0x1800378d5  mov     rdi, rcx
0x1800378d8  mov     [rbp+57h+Returned], r12d
0x1800378dc  mov     rcx, [rcx+38h]; void *
0x1800378e0  lea     rax, aEventSystemEve; "Event/System/EventID"
0x1800378e7  mov     [rbp+57h+ValuePaths], rax
0x1800378eb  xorps   xmm0, xmm0
0x1800378ee  mov     [rbp+57h+Events], r12
0x1800378f2  mov     [rbp+57h+dwResult], r12
0x1800378f6  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x1800378fa  movups  [rbp+57h+Login], xmm1
0x1800378fe  movups  [rbp+57h+var_60], xmm1
0x180037902  test    rcx, rcx
0x180037905  jz      short loc_180037910
0x180037907  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18003790c  mov     [rdi+38h], r12
0x180037910  mov     ebx, 400h
0x180037915  mov     ecx, ebx; dwBytes
0x180037917  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18003791c  mov     [rdi+38h], rax
0x180037920  test    rax, rax
0x180037923  jnz     short loc_180037950
0x180037925  mov     ebx, 8007000Eh
0x18003792a  mov     dword ptr [rsp+0C0h+Bookmark], ebx
0x18003792e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180037935  xor     r8d, r8d; int
0x180037938  lea     rdx, aWdccomponentda; "WdcComponentData::NotifyEventListener"
0x18003793f  lea     rcx, aBaseDiagnosisP_41; "base\\diagnosis\\pdui\\perfmon\\mmc\\co"...
0x180037946  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003794b  jmp     loc_180037CF3
0x180037950  xor     r9d, r9d; lpName
0x180037953  mov     [rdi+40h], ebx
0x180037956  xor     r8d, r8d; bInitialState
0x180037959  xor     edx, edx; bManualReset
0x18003795b  xor     ecx, ecx; lpEventAttributes
0x18003795d  call    cs:__imp_CreateEventW
0x180037963  mov     rsi, rax
0x180037966  mov     r13d, 80070000h
0x18003796c  test    rax, rax
0x18003796f  jnz     short loc_180037998
0x180037971  call    cs:__imp_GetLastError
0x180037977  mov     ebx, eax
0x180037979  test    eax, eax
0x18003797b  jz      short loc_18003798B
0x18003797d  jle     short loc_180037985
0x18003797f  movzx   ebx, ax
0x180037982  or      ebx, r13d
0x180037985  test    ebx, ebx
0x180037987  jns     short loc_1800379A1
0x180037989  jmp     short loc_180037990
0x18003798b  mov     ebx, 80004005h
0x180037990  mov     eax, ebx
0x180037992  mov     dword ptr [rsp+0C0h+Bookmark], ebx
0x180037996  jmp     short loc_18003792E
0x180037998  mov     ebx, r12d
0x18003799b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18003799f  jz      short loc_180037971
0x1800379a1  mov     rax, [rdi+30h]
0x1800379a5  lea     rdx, [rbp+57h+Login]; Login
0x1800379a9  xor     r9d, r9d; Flags
0x1800379ac  mov     qword ptr [rbp+57h+Login], rax
0x1800379b0  xorps   xmm0, xmm0
0x1800379b3  xorps   xmm1, xmm1
0x1800379b6  xor     r8d, r8d; Timeout
0x1800379b9  mov     r14, r12
0x1800379bc  movdqu  [rbp+57h+Login+8], xmm0
0x1800379c1  lea     ecx, [r9+1]; LoginClass
0x1800379c5  movdqu  [rbp+57h+var_60+8], xmm1
0x1800379ca  call    cs:__imp_EvtOpenSession
0x1800379d0  mov     r15, rax
0x1800379d3  test    rax, rax
0x1800379d6  jnz     short loc_180037A02
0x1800379d8  call    cs:__imp_GetLastError
0x1800379de  mov     ebx, eax
0x1800379e0  test    eax, eax
0x1800379e2  jz      short loc_1800379F2
0x1800379e4  jle     short loc_1800379EC
0x1800379e6  movzx   ebx, ax
0x1800379e9  or      ebx, r13d
0x1800379ec  test    ebx, ebx
0x1800379ee  jns     short loc_180037A08
0x1800379f0  jmp     short loc_1800379F7
0x1800379f2  mov     ebx, 80004005h
0x1800379f7  mov     eax, ebx
0x1800379f9  mov     dword ptr [rsp+0C0h+Bookmark], ebx
0x1800379fd  jmp     loc_180037C9D
0x180037a02  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180037a06  jz      short loc_1800379D8
0x180037a08  mov     rcx, [rdi+28h]; Object
0x180037a0c  lea     rax, [rcx-1]
0x180037a10  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037a14  ja      short loc_180037A20
0x180037a16  call    cs:__imp_EvtClose
0x180037a1c  mov     [rdi+28h], r12
0x180037a20  mov     [rsp+0C0h+Flags], 1; Flags
0x180037a28  lea     r9, asc_180091684; "*"
0x180037a2f  mov     [rsp+0C0h+Callback], r12; Callback
0x180037a34  lea     r8, aMicrosoftWindo_1; "Microsoft-Windows-Diagnosis-PLA/Operati"...
0x180037a3b  mov     [rsp+0C0h+Context], r12; Context
0x180037a40  mov     rdx, rsi; SignalEvent
0x180037a43  mov     rcx, r15; Session
0x180037a46  mov     [rsp+0C0h+Bookmark], r12; Bookmark
0x180037a4b  call    cs:__imp_EvtSubscribe
0x180037a51  mov     [rdi+28h], rax
0x180037a55  test    rax, rax
0x180037a58  jnz     short loc_180037A72
0x180037a5a  call    cs:__imp_GetLastError
0x180037a60  mov     ebx, eax
0x180037a62  test    eax, eax
0x180037a64  jz      short loc_1800379F2
0x180037a66  jle     short loc_180037A6E
0x180037a68  movzx   ebx, ax
0x180037a6b  or      ebx, r13d
0x180037a6e  test    ebx, ebx
0x180037a70  js      short loc_1800379F7
0x180037a72  cmp     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180037a77  jnz     short loc_180037A99
0x180037a79  call    cs:__imp_GetLastError
0x180037a7f  mov     ebx, eax
0x180037a81  test    eax, eax
0x180037a83  jz      loc_1800379F2
0x180037a89  jle     short loc_180037A91
0x180037a8b  movzx   ebx, ax
0x180037a8e  or      ebx, r13d
0x180037a91  test    ebx, ebx
0x180037a93  js      loc_1800379F7
0x180037a99  mov     rcx, [rdi+50h]; hWnd
0x180037a9d  lea     rax, [rbp+57h+dwResult]
0x180037aa1  mov     [rsp+0C0h+Callback], rax; lpdwResult
0x180037aa6  xor     r9d, r9d; lParam
0x180037aa9  mov     dword ptr [rsp+0C0h+Context], 3A98h; uTimeout
0x180037ab1  xor     r8d, r8d; wParam
0x180037ab4  xor     edx, edx; Msg
0x180037ab6  mov     dword ptr [rsp+0C0h+Bookmark], 1; fuFlags
0x180037abe  call    cs:__imp_SendMessageTimeoutW
0x180037ac4  test    ebx, ebx
0x180037ac6  js      short loc_180037B01
0x180037ac8  mov     rcx, [rdi+28h]; ResultSet
0x180037acc  lea     rax, [rbp+57h+Returned]
0x180037ad0  xor     r9d, r9d; Timeout
0x180037ad3  mov     [rsp+0C0h+Context], rax; Returned
0x180037ad8  lea     r8, [rbp+57h+Events]; Events
0x180037adc  mov     dword ptr [rsp+0C0h+Bookmark], r12d; Flags
0x180037ae1  lea     edx, [r9+1]; EventsSize
0x180037ae5  call    cs:__imp_EvtNext
0x180037aeb  test    eax, eax
0x180037aed  jz      short loc_180037B01
0x180037aef  cmp     [rbp+57h+Returned], 1
0x180037af3  jnz     short loc_180037B01
0x180037af5  mov     rcx, [rbp+57h+Events]; Object
0x180037af9  call    cs:__imp_EvtClose
0x180037aff  jmp     short loc_180037AC8
0x180037b01  mov     rcx, [rdi+18h]; Object
0x180037b05  lea     rax, [rcx-1]
0x180037b09  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037b0d  ja      short loc_180037B19
0x180037b0f  call    cs:__imp_EvtClose
0x180037b15  mov     [rdi+18h], r12
0x180037b19  xor     r8d, r8d; Flags
0x180037b1c  lea     rdx, [rbp+57h+ValuePaths]; ValuePaths
0x180037b20  lea     ecx, [r8+1]; ValuePathsCount
0x180037b24  call    cs:__imp_EvtCreateRenderContext
0x180037b2a  mov     [rdi+18h], rax
0x180037b2e  test    rax, rax
0x180037b31  jnz     short loc_180037B53
0x180037b33  call    cs:__imp_GetLastError
0x180037b39  mov     ebx, eax
0x180037b3b  test    eax, eax
0x180037b3d  jz      loc_1800379F2
0x180037b43  jle     short loc_180037B4B
0x180037b45  movzx   ebx, ax
0x180037b48  or      ebx, r13d
0x180037b4b  test    ebx, ebx
0x180037b4d  js      loc_1800379F7
0x180037b53  cmp     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x180037b58  jnz     short loc_180037B7A
0x180037b5a  call    cs:__imp_GetLastError
0x180037b60  mov     ebx, eax
0x180037b62  test    eax, eax
0x180037b64  jz      loc_1800379F2
0x180037b6a  jle     short loc_180037B72
0x180037b6c  movzx   ebx, ax
0x180037b6f  or      ebx, r13d
0x180037b72  test    ebx, ebx
0x180037b74  js      loc_1800379F7
0x180037b7a  mov     rcx, [rdi+20h]; Object
0x180037b7e  lea     rax, [rcx-1]
0x180037b82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037b86  ja      short loc_180037B92
0x180037b88  call    cs:__imp_EvtClose
0x180037b8e  mov     [rdi+20h], r12
0x180037b92  xor     edx, edx; ValuePaths
0x180037b94  xor     ecx, ecx; ValuePathsCount
0x180037b96  lea     r8d, [rdx+2]; Flags
0x180037b9a  call    cs:__imp_EvtCreateRenderContext
0x180037ba0  mov     [rdi+20h], rax
0x180037ba4  test    rax, rax
0x180037ba7  jnz     short loc_180037BC9
0x180037ba9  call    cs:__imp_GetLastError
0x180037baf  mov     ebx, eax
0x180037bb1  test    eax, eax
0x180037bb3  jz      loc_1800379F2
0x180037bb9  jle     short loc_180037BC1
0x180037bbb  movzx   ebx, ax
0x180037bbe  or      ebx, r13d
0x180037bc1  test    ebx, ebx
0x180037bc3  js      loc_1800379F7
0x180037bc9  cmp     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x180037bce  jnz     short loc_180037BF0
0x180037bd0  call    cs:__imp_GetLastError
0x180037bd6  mov     ebx, eax
0x180037bd8  test    eax, eax
0x180037bda  jz      loc_1800379F2
0x180037be0  jle     short loc_180037BE8
0x180037be2  movzx   ebx, ax
0x180037be5  or      ebx, r13d
0x180037be8  test    ebx, ebx
0x180037bea  js      loc_1800379F7
0x180037bf0  mov     rcx, rsi; hEvent
0x180037bf3  call    cs:__imp_ResetEvent
0x180037bf9  mov     r9d, 400h; Locale
0x180037bff  mov     dword ptr [rsp+0C0h+Bookmark], r12d; Flags
0x180037c04  xor     r8d, r8d; LogFilePath
0x180037c07  lea     rdx, PublisherId; "Microsoft-Windows-Diagnosis-PLA"
0x180037c0e  xor     ecx, ecx; Session
0x180037c10  call    cs:__imp_EvtOpenPublisherMetadata
0x180037c16  mov     r14, rax
0x180037c19  test    rax, rax
0x180037c1c  jnz     short loc_180037C3F
0x180037c1e  call    cs:__imp_GetLastError
0x180037c24  mov     ebx, eax
0x180037c26  test    eax, eax
0x180037c28  jz      loc_1800379F2
0x180037c2e  jle     short loc_180037C36
0x180037c30  movzx   ebx, ax
0x180037c33  or      ebx, r13d
0x180037c36  test    ebx, ebx
0x180037c38  jns     short loc_180037C45
0x180037c3a  jmp     loc_1800379F7
0x180037c3f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037c43  jz      short loc_180037C1E
0x180037c45  mov     rax, [rdi+8]
0x180037c49  mov     [rbp+57h+Handles+8], rax
0x180037c4d  mov     [rbp+57h+Handles], rsi
0x180037c51  test    ebx, ebx
0x180037c53  js      short loc_180037CBA
0x180037c55  xor     r8d, r8d; bWaitAll
0x180037c58  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180037c5c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180037c60  lea     ecx, [r8+2]; nCount
0x180037c64  call    cs:__imp_WaitForMultipleObjects
0x180037c6a  test    eax, eax
0x180037c6c  jz      loc_180037D09
0x180037c72  cmp     eax, 1
0x180037c75  jz      short loc_180037CBA
0x180037c77  cmp     eax, 0FFFFFFFFh
0x180037c7a  jnz     short loc_180037C51
0x180037c7c  call    cs:__imp_GetLastError
0x180037c82  mov     ebx, r12d
0x180037c85  test    eax, eax
0x180037c87  jz      short loc_180037C95
0x180037c89  jg      short loc_180037C8F
0x180037c8b  mov     ebx, eax
0x180037c8d  jmp     short loc_180037C95
0x180037c8f  movzx   ebx, ax
0x180037c92  or      ebx, r13d
0x180037c95  test    ebx, ebx
0x180037c97  jns     short loc_180037C55
0x180037c99  mov     dword ptr [rsp+0C0h+Bookmark], ebx
0x180037c9d  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180037ca4  xor     r8d, r8d; int
0x180037ca7  lea     rdx, aWdccomponentda; "WdcComponentData::NotifyEventListener"
0x180037cae  lea     rcx, aBaseDiagnosisP_41; "base\\diagnosis\\pdui\\perfmon\\mmc\\co"...
0x180037cb5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180037cba  lea     rax, [rsi-1]
0x180037cbe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037cc2  ja      short loc_180037CCD
0x180037cc4  mov     rcx, rsi; hObject
0x180037cc7  call    cs:__imp_CloseHandle
0x180037ccd  lea     rax, [r15-1]
0x180037cd1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037cd5  ja      short loc_180037CE0
0x180037cd7  mov     rcx, r15; Object
0x180037cda  call    cs:__imp_EvtClose
0x180037ce0  lea     rcx, [r14-1]
0x180037ce4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180037ce8  ja      short loc_180037CF3
  ... truncated ...
```
