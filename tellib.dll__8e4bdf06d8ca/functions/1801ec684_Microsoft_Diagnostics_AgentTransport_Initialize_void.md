# Microsoft::Diagnostics::AgentTransport::Initialize(void)

- ea: `0x1801ec684`
- end: `0x1801ec8ca`
- name: `?Initialize@AgentTransport@Diagnostics@Microsoft@@AEAAXXZ`
- size: `582`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801ebad0`
- `0x1801ebc04`

## callees

- `0x18005af1c`
- `0x1800a1e24`
- `0x1800b83bc`
- `0x18012de40`
- `0x1801ec4c8`
- `0x1801ec684`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1801ec856`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1801ec856`
- `WS2_32!WSAIoctl` at `0x1801ec72b`
- `WS2_32!WSAIoctl` at `0x1801ec7a6`
- `WS2_32!WSAIoctl` at `0x1801ec821`
- `WS2_32!WSAIoctl` at `0x1801ec72b`
- `WS2_32!WSAIoctl` at `0x1801ec7a6`
- `WS2_32!WSAIoctl` at `0x1801ec821`

## string_xrefs

- `0x1801ec6b4`: `onecore\base\telemetry\utc\service\engine\agenttransport.cpp`
- `0x1801ec740`: `onecore\base\telemetry\utc\service\engine\agenttransport.cpp`
- `0x1801ec7bb`: `onecore\base\telemetry\utc\service\engine\agenttransport.cpp`
- `0x1801ec836`: `onecore\base\telemetry\utc\service\engine\agenttransport.cpp`
- `0x1801ec89b`: `onecore\base\telemetry\utc\service\engine\agenttransport.cpp`

## pseudocode

```c
void __fastcall Microsoft::Diagnostics::AgentTransport::Initialize(HANDLE *pv, __int64 a2, __int64 a3, const char *a4)
{
  char *lpvOutBuffer; // rax
  SOCKET v6; // rcx
  const char *v7; // r9
  SOCKET v8; // rcx
  const char *v9; // r9
  SOCKET v10; // rcx
  const char *v11; // r9
  PTP_IO ThreadpoolIo; // rax
  const char *v13; // r9
  HANDLE v14; // rsi
  PTP_IO v15; // rdi
  DWORD cbBytesReturned; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v17[8]; // [rsp+58h] [rbp-21h] BYREF
  _DWORD vInBuffer[4]; // [rsp+60h] [rbp-19h] BYREF
  _DWORD v19[4]; // [rsp+70h] [rbp-9h] BYREF
  _DWORD v20[4]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( *pv == (HANDLE)-1LL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agenttransport.cpp",
      a4);
  lpvOutBuffer = (char *)(pv + 29);
  v6 = (SOCKET)*pv;
  vInBuffer[0] = -1254720015;
  vInBuffer[1] = 298830764;
  vInBuffer[2] = -2147431787;
  vInBuffer[3] = -1834923937;
  cbBytesReturned = 0;
  if ( WSAIoctl(v6, 0xC8000006, vInBuffer, 0x10u, lpvOutBuffer, 8u, &cbBytesReturned, 0, 0) == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agenttransport.cpp",
      v7);
  v8 = (SOCKET)*pv;
  v19[0] = -1254720014;
  v19[1] = 298830764;
  v19[2] = -2147431787;
  v19[3] = -1834923937;
  if ( WSAIoctl(v8, 0xC8000006, v19, 0x10u, pv + 30, 8u, &cbBytesReturned, 0, 0) == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agenttransport.cpp",
      v9);
  v10 = (SOCKET)*pv;
  v20[0] = 631375801;
  v20[1] = 1180753395;
  v20[2] = -445191794;
  v20[3] = 1040610444;
  if ( WSAIoctl(v10, 0xC8000006, v20, 0x10u, pv + 28, 8u, &cbBytesReturned, 0, 0) == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agenttransport.cpp",
      v11);
  ThreadpoolIo = CreateThreadpoolIo(*pv, Microsoft::Diagnostics::AgentTransport::StaticIoCompletionCallback, pv, 0);
  v14 = pv[32];
  v15 = ThreadpoolIo;
  if ( v14 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v17);
    wil::details::DestroyThreadPoolIo<0>::Destroy(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v17);
  }
  pv[32] = v15;
  if ( !v15 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agenttransport.cpp",
      v13);
}

```

## disassembly

```asm
0x1801ec684  push    rbp
0x1801ec686  push    rbx
0x1801ec687  push    rsi
0x1801ec688  push    rdi
0x1801ec689  push    r12
0x1801ec68b  push    r13
0x1801ec68d  lea     rbp, [rsp-2Fh]
0x1801ec692  sub     rsp, 0A8h
0x1801ec699  mov     rax, cs:__security_cookie
0x1801ec6a0  xor     rax, rsp
0x1801ec6a3  mov     [rbp+57h+var_40], rax
0x1801ec6a7  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1801ec6ab  mov     rbx, rcx
0x1801ec6ae  jnz     short loc_1801EC6C6
0x1801ec6b0  mov     rcx, [rbp+5Fh]; this
0x1801ec6b4  lea     r8, aOnecoreBaseTel_78; "onecore\\base\\telemetry\\utc\\service"...
0x1801ec6bb  mov     edx, 54h ; 'T'; void *
0x1801ec6c0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801ec6c6  lea     rax, [rcx+0E8h]
0x1801ec6cd  mov     [rsp+0D0h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1801ec6d6  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x1801ec6df  lea     rcx, [rbp+57h+cbBytesReturned]
0x1801ec6e3  mov     [rsp+0D0h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x1801ec6e8  lea     r8, [rbp+57h+vInBuffer]; lpvInBuffer
0x1801ec6ec  mov     rcx, [rbx]; s
0x1801ec6ef  mov     edi, 8
0x1801ec6f4  mov     [rsp+0D0h+cbOutBuffer], edi; cbOutBuffer
0x1801ec6f8  mov     edx, 0C8000006h; dwIoControlCode
0x1801ec6fd  mov     [rbp+57h+vInBuffer], 0B5367DF1h
0x1801ec704  mov     [rbp+57h+var_6C], 11CFCBACh
0x1801ec70b  lea     esi, [rdi+8]
0x1801ec70e  mov     [rbp+57h+var_68], 8000CA95h
0x1801ec715  mov     r9d, esi; cbInBuffer
0x1801ec718  mov     [rbp+57h+var_64], 92A1485Fh
0x1801ec71f  mov     [rbp+57h+cbBytesReturned], 0
0x1801ec726  mov     [rsp+0D0h+lpvOutBuffer], rax; lpvOutBuffer
0x1801ec72b  call    cs:__imp_WSAIoctl
0x1801ec732  nop     dword ptr [rax+rax+00h]
0x1801ec737  cmp     eax, 0FFFFFFFFh
0x1801ec73a  jnz     short loc_1801EC750
0x1801ec73c  mov     rcx, [rbp+5Fh]; this
0x1801ec740  lea     r8, aOnecoreBaseTel_78; "onecore\\base\\telemetry\\utc\\service"...
0x1801ec747  lea     edx, [rdi+59h]; void *
0x1801ec74a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801ec750  mov     [rsp+0D0h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1801ec759  lea     rcx, [rbp+57h+cbBytesReturned]
0x1801ec75d  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x1801ec766  lea     rax, [rbx+0F0h]
0x1801ec76d  mov     [rsp+0D0h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x1801ec772  lea     r8, [rbp+57h+var_60]; lpvInBuffer
0x1801ec776  mov     rcx, [rbx]; s
0x1801ec779  mov     r9d, esi; cbInBuffer
0x1801ec77c  mov     [rsp+0D0h+cbOutBuffer], edi; cbOutBuffer
0x1801ec780  mov     edx, 0C8000006h; dwIoControlCode
0x1801ec785  mov     [rsp+0D0h+lpvOutBuffer], rax; lpvOutBuffer
0x1801ec78a  mov     [rbp+57h+var_60], 0B5367DF2h
0x1801ec791  mov     [rbp+57h+var_5C], 11CFCBACh
0x1801ec798  mov     [rbp+57h+var_58], 8000CA95h
0x1801ec79f  mov     [rbp+57h+var_54], 92A1485Fh
0x1801ec7a6  call    cs:__imp_WSAIoctl
0x1801ec7ad  nop     dword ptr [rax+rax+00h]
0x1801ec7b2  cmp     eax, 0FFFFFFFFh
0x1801ec7b5  jnz     short loc_1801EC7CB
0x1801ec7b7  mov     rcx, [rbp+5Fh]; this
0x1801ec7bb  lea     r8, aOnecoreBaseTel_78; "onecore\\base\\telemetry\\utc\\service"...
0x1801ec7c2  lea     edx, [rax+6Eh]; void *
0x1801ec7c5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801ec7cb  mov     [rsp+0D0h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1801ec7d4  lea     rcx, [rbp+57h+cbBytesReturned]
0x1801ec7d8  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x1801ec7e1  lea     rax, [rbx+0E0h]
0x1801ec7e8  mov     [rsp+0D0h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x1801ec7ed  lea     r8, [rbp+57h+var_50]; lpvInBuffer
0x1801ec7f1  mov     rcx, [rbx]; s
0x1801ec7f4  mov     r9d, esi; cbInBuffer
0x1801ec7f7  mov     [rsp+0D0h+cbOutBuffer], edi; cbOutBuffer
0x1801ec7fb  mov     edx, 0C8000006h; dwIoControlCode
0x1801ec800  mov     [rsp+0D0h+lpvOutBuffer], rax; lpvOutBuffer
0x1801ec805  mov     [rbp+57h+var_50], 25A207B9h
0x1801ec80c  mov     [rbp+57h+var_4C], 4660DDF3h
0x1801ec813  mov     [rbp+57h+var_48], 0E576E98Eh
0x1801ec81a  mov     [rbp+57h+var_44], 3E06748Ch
0x1801ec821  call    cs:__imp_WSAIoctl
0x1801ec828  nop     dword ptr [rax+rax+00h]
0x1801ec82d  cmp     eax, 0FFFFFFFFh
0x1801ec830  jnz     short loc_1801EC846
0x1801ec832  mov     rcx, [rbp+5Fh]; this
0x1801ec836  lea     r8, aOnecoreBaseTel_78; "onecore\\base\\telemetry\\utc\\service"...
0x1801ec83d  lea     edx, [rax+7Ah]; void *
0x1801ec840  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801ec846  mov     rcx, [rbx]; fl
0x1801ec849  lea     rdx, ?StaticIoCompletionCallback@AgentTransport@Diagnostics@Microsoft@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1801ec850  xor     r9d, r9d; pcbe
0x1801ec853  mov     r8, rbx; pv
0x1801ec856  call    cs:__imp_CreateThreadpoolIo
0x1801ec85d  nop     dword ptr [rax+rax+00h]
0x1801ec862  mov     rsi, [rbx+100h]
0x1801ec869  mov     rdi, rax
0x1801ec86c  test    rsi, rsi
0x1801ec86f  jz      short loc_1801EC88B
0x1801ec871  lea     rcx, [rbp+57h+var_78]; this
0x1801ec875  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801ec87a  mov     rcx, rsi
0x1801ec87d  call    ?Destroy@?$DestroyThreadPoolIo@$0A@@details@wil@@SAXPEAU_TP_IO@@@Z; wil::details::DestroyThreadPoolIo<0>::Destroy(_TP_IO *)
0x1801ec882  lea     rcx, [rbp+57h+var_78]; this
0x1801ec886  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801ec88b  mov     [rbx+100h], rdi
0x1801ec892  test    rdi, rdi
0x1801ec895  jnz     short loc_1801EC8AD
0x1801ec897  mov     rcx, [rbp+5Fh]; this
0x1801ec89b  lea     r8, aOnecoreBaseTel_78; "onecore\\base\\telemetry\\utc\\service"...
0x1801ec8a2  mov     edx, 80h; void *
0x1801ec8a7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801ec8ad  mov     rcx, [rbp+57h+var_40]
0x1801ec8b1  xor     rcx, rsp; StackCookie
0x1801ec8b4  call    __security_check_cookie
0x1801ec8b9  add     rsp, 0A8h
0x1801ec8c0  pop     r13
0x1801ec8c2  pop     r12
0x1801ec8c4  pop     rdi
0x1801ec8c5  pop     rsi
0x1801ec8c6  pop     rbx
0x1801ec8c7  pop     rbp
0x1801ec8c8  retn
```
