# WEB_SOCKET_HANDLE_OBJECT::LockedAbortConnection(ulong)

- ea: `0x180098f1c`
- end: `0x180098fb1`
- name: `?LockedAbortConnection@WEB_SOCKET_HANDLE_OBJECT@@AEAAXK@Z`
- size: `149`
- prototype: `void __fastcall(WEB_SOCKET_HANDLE_OBJECT *__hidden this, unsigned int)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007148`
- `0x1800268d0`
- `0x180026d14`
- `0x180027334`
- `0x1800273d4`
- `0x180027514`
- `0x1800c63fc`
- `0x1800c6ae8`

## callees

- `0x180098f1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098f85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098f85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098faa`
- `websocket!WebSocketCompleteAction` at `0x180098f6d`
- `websocket!WebSocketCompleteAction` at `0x180098f6d`
- `websocket!WebSocketAbortHandle` at `0x180098f4e`
- `websocket!WebSocketAbortHandle` at `0x180098f4e`
- `webio!__imp_WebCancelProtocolHandle` at `0x180098f97`

## pseudocode

```c
void __fastcall WEB_SOCKET_HANDLE_OBJECT::LockedAbortConnection(WEB_SOCKET_HANDLE_OBJECT *this, int a2)
{
  __int64 v3; // rdx

  if ( *((_DWORD *)this + 276) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 816));
  }
  else
  {
    *((_DWORD *)this + 276) = 1;
    *((_DWORD *)this + 115) = a2;
    *((_DWORD *)this + 126) = a2;
    WebSocketAbortHandle(**((_QWORD **)this + 100));
    v3 = *((_QWORD *)this + 58);
    if ( v3 )
    {
      WebSocketCompleteAction(**((_QWORD **)this + 100), v3, 0);
      *((_QWORD *)this + 58) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 816));
    WebCancelProtocolHandle(*((_QWORD *)this + 101));
  }
}

```

## disassembly

```asm
0x180098f1c  push    rbx
0x180098f1e  sub     rsp, 20h
0x180098f22  cmp     dword ptr [rcx+450h], 0
0x180098f29  mov     rbx, rcx
0x180098f2c  jnz     short loc_180098F9E
0x180098f2e  mov     dword ptr [rcx+450h], 1
0x180098f38  mov     [rcx+1CCh], edx
0x180098f3e  mov     [rcx+1F8h], edx
0x180098f44  mov     rcx, [rcx+320h]
0x180098f4b  mov     rcx, [rcx]
0x180098f4e  call    cs:__imp_WebSocketAbortHandle
0x180098f54  mov     rdx, [rbx+1D0h]
0x180098f5b  test    rdx, rdx
0x180098f5e  jz      short loc_180098F7E
0x180098f60  mov     rcx, [rbx+320h]
0x180098f67  xor     r8d, r8d
0x180098f6a  mov     rcx, [rcx]
0x180098f6d  call    cs:__imp_WebSocketCompleteAction
0x180098f73  mov     qword ptr [rbx+1D0h], 0
0x180098f7e  lea     rcx, [rbx+330h]; lpCriticalSection
0x180098f85  call    cs:__imp_LeaveCriticalSection
0x180098f8b  mov     rcx, [rbx+328h]
0x180098f92  add     rsp, 20h
0x180098f96  pop     rbx
0x180098f97  jmp     cs:__imp_WebCancelProtocolHandle
0x180098f9e  add     rcx, 330h
0x180098fa5  add     rsp, 20h
0x180098fa9  pop     rbx
0x180098faa  jmp     cs:__imp_LeaveCriticalSection
```
