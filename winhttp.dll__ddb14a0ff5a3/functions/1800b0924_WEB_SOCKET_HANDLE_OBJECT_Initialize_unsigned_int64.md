# WEB_SOCKET_HANDLE_OBJECT::Initialize(unsigned __int64)

- ea: `0x1800b0924`
- end: `0x1800b0b51`
- name: `?Initialize@WEB_SOCKET_HANDLE_OBJECT@@QEAAK_K@Z`
- size: `557`
- prototype: `unsigned int __fastcall(WEB_SOCKET_HANDLE_OBJECT *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b047c`

## callees

- `0x1800061e4`
- `0x180013680`
- `0x180015410`
- `0x180027514`
- `0x180033ac0`
- `0x1800a1d10`
- `0x1800ae828`
- `0x1800b0924`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b09e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b0a0e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b0a2a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b09e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b0a0e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b0a2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0b0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b09f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b09f7`
- `webio!__imp_WebCloseHttpRequest` at `0x1800b0b24`
- `webio!__imp_WebCloseHttpRequest` at `0x1800b0b24`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x1800b0995`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x1800b0995`
- `webio!__imp_WebCompleteProtocolUpgrade` at `0x1800b09ae`
- `webio!__imp_WebCompleteProtocolUpgrade` at `0x1800b09ae`

## pseudocode

```c
__int64 __fastcall WEB_SOCKET_HANDLE_OBJECT::Initialize(WEB_SOCKET_HANDLE_OBJECT *this, __int64 a2)
{
  HTTP_THREAD_POOL *v4; // rcx
  bool v5; // zf
  HANDLE EventA; // rax
  DWORD WorkItem; // edi
  HANDLE v8; // rax
  HANDLE v9; // rax
  HTTP_THREAD_POOL *v10; // rcx
  unsigned int v11; // r8d
  struct _TP_TIMER *v12; // rcx
  _QWORD v14[3]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v15; // [rsp+58h] [rbp-40h] BYREF
  __int64 v16; // [rsp+60h] [rbp-38h] BYREF
  struct _FILETIME v17; // [rsp+68h] [rbp-30h] BYREF

  v14[1] = &v15;
  v16 = 0;
  v14[0] = 0;
  v14[2] = 1;
  if ( (unsigned int)WebReceiveHttpResponseEntity(a2, 0, v14, 1, &v16, 0, 0) != 38
    || (unsigned int)WebCompleteProtocolUpgrade(a2, (char *)this + 808) )
  {
    WorkItem = 12004;
  }
  else
  {
    GetRootHandle(this);
    v5 = *((_DWORD *)this + 35) == 0;
    *((_QWORD *)this + 107) = qword_180107DE8;
    if ( !v5
      || (EventA = CreateEventA(0, 0, 0, 0), (*((_QWORD *)this + 73) = EventA) != 0)
      && (v8 = CreateEventA(0, 0, 0, 0), (*((_QWORD *)this + 77) = v8) != 0)
      && (v9 = CreateEventA(0, 0, 0, 0), (*((_QWORD *)this + 81) = v9) != 0) )
    {
      WorkItem = HTTP_THREAD_POOL::CreateWorkItem(
                   v4,
                   (struct IHttpAsyncCallback *)(((unsigned __int64)this + 432)
                                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
                   1u,
                   (WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 864));
      if ( !WorkItem )
      {
        WorkItem = HTTP_THREAD_POOL::CreateWorkItem(
                     v10,
                     (WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 432),
                     0,
                     (WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 928));
        if ( !WorkItem )
        {
          WorkItem = HTTP_THREAD_POOL::CreateTimer(
                       *((HTTP_THREAD_POOL **)this + 107),
                       (WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 432),
                       0,
                       (WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 992));
          if ( !WorkItem )
          {
            WorkItem = HTTP_THREAD_POOL::CreateTimer(
                         *((HTTP_THREAD_POOL **)this + 107),
                         (WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 432),
                         1u,
                         (WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 1048));
            if ( !WorkItem )
            {
              if ( !*((_DWORD *)this + 277) )
              {
                HANDLE_OBJECT::Reference(this);
                *((_DWORD *)this + 277) = 1;
              }
              v11 = *((_DWORD *)this + 279);
              v12 = (struct _TP_TIMER *)*((_QWORD *)this + 130);
              v17 = (struct _FILETIME)(-10000LL * v11);
              WxSetThreadpoolTimer(v12, &v17, v11, 0x3E8u);
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 816));
              WEB_SOCKET_HANDLE_OBJECT::BeginBackgroundReceive(this);
            }
          }
        }
      }
    }
    else
    {
      WorkItem = GetLastError();
    }
  }
  WebCloseHttpRequest(a2, 0);
  return WorkItem;
}

```

## disassembly

```asm
0x1800b0924  mov     r11, rsp
0x1800b0927  mov     [r11+18h], rbx
0x1800b092b  mov     [r11+20h], rbp
0x1800b092f  push    rsi
0x1800b0930  push    rdi
0x1800b0931  push    r15
0x1800b0933  sub     rsp, 80h
0x1800b093a  mov     rax, cs:__security_cookie
0x1800b0941  xor     rax, rsp
0x1800b0944  mov     [rsp+98h+var_28], rax
0x1800b0949  lea     rax, [r11-40h]
0x1800b094d  mov     qword ptr [r11-68h], 0
0x1800b0955  mov     rbp, rdx
0x1800b0958  mov     [r11-50h], rax
0x1800b095c  mov     r15d, 1
0x1800b0962  mov     qword ptr [r11-70h], 0
0x1800b096a  lea     rax, [r11-38h]
0x1800b096e  mov     qword ptr [r11-38h], 0
0x1800b0976  mov     rbx, rcx
0x1800b0979  mov     [r11-78h], rax
0x1800b097d  mov     r9d, r15d
0x1800b0980  mov     qword ptr [r11-58h], 0
0x1800b0988  lea     r8, [r11-58h]
0x1800b098c  mov     [r11-48h], r15
0x1800b0990  xor     edx, edx
0x1800b0992  mov     rcx, rbp
0x1800b0995  call    cs:__imp_WebReceiveHttpResponseEntity
0x1800b099b  cmp     eax, 26h ; '&'
0x1800b099e  jnz     loc_1800B0B1A
0x1800b09a4  lea     rdx, [rbx+328h]
0x1800b09ab  mov     rcx, rbp
0x1800b09ae  call    cs:__imp_WebCompleteProtocolUpgrade
0x1800b09b4  test    eax, eax
0x1800b09b6  jnz     loc_1800B0B1A
0x1800b09bc  mov     rcx, rbx; struct HANDLE_OBJECT *
0x1800b09bf  call    ?GetRootHandle@@YAPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEAVHANDLE_OBJECT@@@Z; GetRootHandle(HANDLE_OBJECT *)
0x1800b09c4  cmp     dword ptr [rbx+8Ch], 0
0x1800b09cb  mov     rax, cs:qword_180107DE8
0x1800b09d2  mov     [rbx+358h], rax
0x1800b09d9  jnz     short loc_1800B0A3C
0x1800b09db  xor     r9d, r9d; lpName
0x1800b09de  xor     r8d, r8d; bInitialState
0x1800b09e1  xor     edx, edx; bManualReset
0x1800b09e3  xor     ecx, ecx; lpEventAttributes
0x1800b09e5  call    cs:__imp_CreateEventA
0x1800b09eb  mov     [rbx+248h], rax
0x1800b09f2  test    rax, rax
0x1800b09f5  jnz     short loc_1800B0A04
0x1800b09f7  call    cs:__imp_GetLastError
0x1800b09fd  mov     edi, eax
0x1800b09ff  jmp     loc_1800B0B1F
0x1800b0a04  xor     r9d, r9d; lpName
0x1800b0a07  xor     r8d, r8d; bInitialState
0x1800b0a0a  xor     edx, edx; bManualReset
0x1800b0a0c  xor     ecx, ecx; lpEventAttributes
0x1800b0a0e  call    cs:__imp_CreateEventA
0x1800b0a14  mov     [rbx+268h], rax
0x1800b0a1b  test    rax, rax
0x1800b0a1e  jz      short loc_1800B09F7
0x1800b0a20  xor     r9d, r9d; lpName
0x1800b0a23  xor     r8d, r8d; bInitialState
0x1800b0a26  xor     edx, edx; bManualReset
0x1800b0a28  xor     ecx, ecx; lpEventAttributes
0x1800b0a2a  call    cs:__imp_CreateEventA
0x1800b0a30  mov     [rbx+288h], rax
0x1800b0a37  test    rax, rax
0x1800b0a3a  jz      short loc_1800B09F7
0x1800b0a3c  mov     rax, rbx
0x1800b0a3f  lea     rsi, [rbx+1B0h]
0x1800b0a46  neg     rax
0x1800b0a49  lea     r9, [rbx+360h]; struct HTTP_THREAD_POOL::WORK_ITEM *
0x1800b0a50  mov     r8, r15; unsigned __int64
0x1800b0a53  sbb     rdx, rdx
0x1800b0a56  and     rdx, rsi; struct IHttpAsyncCallback *
0x1800b0a59  call    ?CreateWorkItem@HTTP_THREAD_POOL@@QEAAKPEAVIHttpAsyncCallback@@_KPEAUWORK_ITEM@1@@Z; HTTP_THREAD_POOL::CreateWorkItem(IHttpAsyncCallback *,unsigned __int64,HTTP_THREAD_POOL::WORK_ITEM *)
0x1800b0a5e  mov     edi, eax
0x1800b0a60  test    eax, eax
0x1800b0a62  jnz     loc_1800B0B1F
0x1800b0a68  lea     r9, [rbx+3A0h]; struct HTTP_THREAD_POOL::WORK_ITEM *
0x1800b0a6f  xor     r8d, r8d; unsigned __int64
0x1800b0a72  mov     rdx, rsi; struct IHttpAsyncCallback *
0x1800b0a75  call    ?CreateWorkItem@HTTP_THREAD_POOL@@QEAAKPEAVIHttpAsyncCallback@@_KPEAUWORK_ITEM@1@@Z; HTTP_THREAD_POOL::CreateWorkItem(IHttpAsyncCallback *,unsigned __int64,HTTP_THREAD_POOL::WORK_ITEM *)
0x1800b0a7a  mov     edi, eax
0x1800b0a7c  test    eax, eax
0x1800b0a7e  jnz     loc_1800B0B1F
0x1800b0a84  mov     rcx, [rbx+358h]; this
0x1800b0a8b  lea     r9, [rbx+3E0h]; struct HTTP_THREAD_POOL::TIMER *
0x1800b0a92  xor     r8d, r8d; unsigned __int64
0x1800b0a95  mov     rdx, rsi; struct IHttpAsyncCallback *
0x1800b0a98  call    ?CreateTimer@HTTP_THREAD_POOL@@QEAAKPEAVIHttpAsyncCallback@@_KPEAUTIMER@1@@Z; HTTP_THREAD_POOL::CreateTimer(IHttpAsyncCallback *,unsigned __int64,HTTP_THREAD_POOL::TIMER *)
0x1800b0a9d  mov     edi, eax
0x1800b0a9f  test    eax, eax
0x1800b0aa1  jnz     short loc_1800B0B1F
0x1800b0aa3  mov     rcx, [rbx+358h]; this
0x1800b0aaa  lea     r9, [rbx+418h]; struct HTTP_THREAD_POOL::TIMER *
0x1800b0ab1  mov     r8, r15; unsigned __int64
0x1800b0ab4  mov     rdx, rsi; struct IHttpAsyncCallback *
0x1800b0ab7  call    ?CreateTimer@HTTP_THREAD_POOL@@QEAAKPEAVIHttpAsyncCallback@@_KPEAUTIMER@1@@Z; HTTP_THREAD_POOL::CreateTimer(IHttpAsyncCallback *,unsigned __int64,HTTP_THREAD_POOL::TIMER *)
0x1800b0abc  mov     edi, eax
0x1800b0abe  test    eax, eax
0x1800b0ac0  jnz     short loc_1800B0B1F
0x1800b0ac2  cmp     [rbx+454h], eax
0x1800b0ac8  jnz     short loc_1800B0AD9
0x1800b0aca  mov     rcx, rbx; this
0x1800b0acd  call    ?Reference@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::Reference(void)
0x1800b0ad2  mov     [rbx+454h], r15d
0x1800b0ad9  mov     r8d, [rbx+45Ch]; unsigned int
0x1800b0ae0  lea     rdx, [rsp+98h+var_30]; struct _FILETIME *
0x1800b0ae5  mov     rcx, [rbx+410h]; struct _TP_TIMER *
0x1800b0aec  mov     r9d, 3E8h; unsigned int
0x1800b0af2  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x1800b0af9  mov     qword ptr [rsp+98h+var_30.dwLowDateTime], rax
0x1800b0afe  call    ?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x1800b0b03  lea     rcx, [rbx+330h]; lpCriticalSection
0x1800b0b0a  call    cs:__imp_EnterCriticalSection
0x1800b0b10  mov     rcx, rbx; this
0x1800b0b13  call    ?BeginBackgroundReceive@WEB_SOCKET_HANDLE_OBJECT@@AEAAKXZ; WEB_SOCKET_HANDLE_OBJECT::BeginBackgroundReceive(void)
0x1800b0b18  jmp     short loc_1800B0B1F
0x1800b0b1a  mov     edi, 2EE4h
0x1800b0b1f  xor     edx, edx
0x1800b0b21  mov     rcx, rbp
0x1800b0b24  call    cs:__imp_WebCloseHttpRequest
0x1800b0b2a  mov     eax, edi
0x1800b0b2c  mov     rcx, [rsp+98h+var_28]
0x1800b0b31  xor     rcx, rsp; StackCookie
0x1800b0b34  call    __security_check_cookie
0x1800b0b39  lea     r11, [rsp+98h+var_18]
0x1800b0b41  mov     rbx, [r11+30h]
0x1800b0b45  mov     rbp, [r11+38h]
0x1800b0b49  mov     rsp, r11
0x1800b0b4c  pop     r15
0x1800b0b4e  pop     rdi
0x1800b0b4f  pop     rsi
0x1800b0b50  retn
```
