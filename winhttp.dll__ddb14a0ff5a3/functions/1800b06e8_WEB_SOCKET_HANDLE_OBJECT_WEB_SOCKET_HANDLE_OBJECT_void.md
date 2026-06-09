# WEB_SOCKET_HANDLE_OBJECT::~WEB_SOCKET_HANDLE_OBJECT(void)

- ea: `0x1800b06e8`
- end: `0x1800b07fc`
- name: `??1WEB_SOCKET_HANDLE_OBJECT@@UEAA@XZ`
- size: `276`
- prototype: `void __fastcall(WEB_SOCKET_HANDLE_OBJECT *this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800b0890`

## callees

- `0x18001b4d0`
- `0x180033ac0`
- `0x18006bc50`
- `0x1800b06e8`
- `0x1800b08f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b07e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b07e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b074c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b077e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b074c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b077e`
- `webio!__imp_WebCloseProtocolHandle` at `0x1800b0733`
- `webio!__imp_WebCloseProtocolHandle` at `0x1800b0733`

## pseudocode

```c
void __fastcall WEB_SOCKET_HANDLE_OBJECT::~WEB_SOCKET_HANDLE_OBJECT(WEB_SOCKET_HANDLE_OBJECT *this, unsigned int a2)
{
  WebSocketLibrary *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &WEB_SOCKET_HANDLE_OBJECT::`vftable'{for `INTERNET_CONNECT_HANDLE_OBJECT'};
  *((_QWORD *)this + 54) = &WEB_SOCKET_HANDLE_OBJECT::`vftable'{for `IHttpAsyncCallback'};
  v3 = (WebSocketLibrary *)*((_QWORD *)this + 100);
  if ( v3 )
  {
    WebSocketLibrary::`scalar deleting destructor'(v3, a2);
    *((_QWORD *)this + 100) = 0;
  }
  if ( *((_QWORD *)this + 101) )
  {
    WebCloseProtocolHandle();
    *((_QWORD *)this + 101) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 73);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 73) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 77);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 77) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 81);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 81) = 0;
  }
  GetRootHandle(this);
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 131) = &HTTP_THREAD_POOL::CONTEXT::`vftable';
  HTTP_THREAD_POOL::CONTEXT::CleanUp((WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 1048));
  *((_QWORD *)this + 124) = &HTTP_THREAD_POOL::CONTEXT::`vftable';
  HTTP_THREAD_POOL::CONTEXT::CleanUp((WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 992));
  *((_QWORD *)this + 116) = &HTTP_THREAD_POOL::CONTEXT::`vftable';
  HTTP_THREAD_POOL::CONTEXT::CleanUp((WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 928));
  *((_QWORD *)this + 108) = &HTTP_THREAD_POOL::CONTEXT::`vftable';
  HTTP_THREAD_POOL::CONTEXT::CleanUp((WEB_SOCKET_HANDLE_OBJECT *)((char *)this + 864));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 816));
  INTERNET_CONNECT_HANDLE_OBJECT::~INTERNET_CONNECT_HANDLE_OBJECT(this);
}

```

## disassembly

```asm
0x1800b06e8  mov     [rsp+arg_0], rbx
0x1800b06ed  push    rdi
0x1800b06ee  sub     rsp, 20h
0x1800b06f2  lea     rax, ??_7WEB_SOCKET_HANDLE_OBJECT@@6BINTERNET_CONNECT_HANDLE_OBJECT@@@; const WEB_SOCKET_HANDLE_OBJECT::`vftable'{for `INTERNET_CONNECT_HANDLE_OBJECT'}
0x1800b06f9  mov     rbx, rcx
0x1800b06fc  mov     [rcx], rax
0x1800b06ff  xor     edi, edi
0x1800b0701  lea     rax, ??_7WEB_SOCKET_HANDLE_OBJECT@@6BIHttpAsyncCallback@@@; const WEB_SOCKET_HANDLE_OBJECT::`vftable'{for `IHttpAsyncCallback'}
0x1800b0708  mov     [rcx+1B0h], rax
0x1800b070f  mov     rcx, [rcx+320h]; this
0x1800b0716  test    rcx, rcx
0x1800b0719  jz      short loc_1800B0727
0x1800b071b  call    ??_GWebSocketLibrary@@QEAAPEAXI@Z; WebSocketLibrary::`scalar deleting destructor'(uint)
0x1800b0720  mov     [rbx+320h], rdi
0x1800b0727  mov     rcx, [rbx+328h]
0x1800b072e  test    rcx, rcx
0x1800b0731  jz      short loc_1800B0740
0x1800b0733  call    cs:__imp_WebCloseProtocolHandle
0x1800b0739  mov     [rbx+328h], rdi
0x1800b0740  mov     rcx, [rbx+248h]; hObject
0x1800b0747  test    rcx, rcx
0x1800b074a  jz      short loc_1800B0759
0x1800b074c  call    cs:__imp_CloseHandle
0x1800b0752  mov     [rbx+248h], rdi
0x1800b0759  mov     rcx, [rbx+268h]; hObject
0x1800b0760  test    rcx, rcx
0x1800b0763  jz      short loc_1800B0772
0x1800b0765  call    cs:__imp_CloseHandle
0x1800b076b  mov     [rbx+268h], rdi
0x1800b0772  mov     rcx, [rbx+288h]; hObject
0x1800b0779  test    rcx, rcx
0x1800b077c  jz      short loc_1800B078B
0x1800b077e  call    cs:__imp_CloseHandle
0x1800b0784  mov     [rbx+288h], rdi
0x1800b078b  mov     rcx, rbx; struct HANDLE_OBJECT *
0x1800b078e  call    ?GetRootHandle@@YAPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEAVHANDLE_OBJECT@@@Z; GetRootHandle(HANDLE_OBJECT *)
0x1800b0793  mov     [rbx+358h], rdi
0x1800b079a  lea     rcx, [rbx+418h]; this
0x1800b07a1  lea     rdi, ??_7CONTEXT@HTTP_THREAD_POOL@@6B@; const HTTP_THREAD_POOL::CONTEXT::`vftable'
0x1800b07a8  mov     [rcx], rdi
0x1800b07ab  call    ?CleanUp@CONTEXT@HTTP_THREAD_POOL@@QEAAXXZ; HTTP_THREAD_POOL::CONTEXT::CleanUp(void)
0x1800b07b0  lea     rcx, [rbx+3E0h]; this
0x1800b07b7  mov     [rcx], rdi
0x1800b07ba  call    ?CleanUp@CONTEXT@HTTP_THREAD_POOL@@QEAAXXZ; HTTP_THREAD_POOL::CONTEXT::CleanUp(void)
0x1800b07bf  lea     rcx, [rbx+3A0h]; this
0x1800b07c6  mov     [rcx], rdi
0x1800b07c9  call    ?CleanUp@CONTEXT@HTTP_THREAD_POOL@@QEAAXXZ; HTTP_THREAD_POOL::CONTEXT::CleanUp(void)
0x1800b07ce  lea     rcx, [rbx+360h]; this
0x1800b07d5  mov     [rcx], rdi
0x1800b07d8  call    ?CleanUp@CONTEXT@HTTP_THREAD_POOL@@QEAAXXZ; HTTP_THREAD_POOL::CONTEXT::CleanUp(void)
0x1800b07dd  lea     rcx, [rbx+330h]; lpCriticalSection
0x1800b07e4  call    cs:__imp_DeleteCriticalSection
0x1800b07ea  mov     rcx, rbx; this
0x1800b07ed  mov     rbx, [rsp+28h+arg_0]
0x1800b07f2  add     rsp, 20h
0x1800b07f6  pop     rdi
0x1800b07f7  jmp     ??1INTERNET_CONNECT_HANDLE_OBJECT@@UEAA@XZ; INTERNET_CONNECT_HANDLE_OBJECT::~INTERNET_CONNECT_HANDLE_OBJECT(void)
```
