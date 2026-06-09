# CSsdpNotifyRequest::~CSsdpNotifyRequest(void)

- ea: `0x18000b764`
- end: `0x18000b874`
- name: `??1CSsdpNotifyRequest@@QEAA@XZ`
- size: `272`
- prototype: `void __fastcall(CSsdpNotifyRequest *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a95c`

## callees

- `0x18000b764`
- `0x18000ba2c`
- `0x18000baa4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b78c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b7a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b81b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b833`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b84b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b78c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b7a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b81b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b833`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b84b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b774`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b774`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b868`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7ec`

## pseudocode

```c
void __fastcall CSsdpNotifyRequest::~CSsdpNotifyRequest(CSsdpNotifyRequest *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  v2 = (void *)*((_QWORD *)this + 41);
  if ( v2 )
    free(v2);
  v3 = (void *)*((_QWORD *)this + 42);
  if ( v3 )
    free(v3);
  v4 = (void *)*((_QWORD *)this + 39);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 40);
  if ( v5 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 46);
  if ( v6 )
    CloseHandle(v6);
  CUList<CSsdpPendingNotification>::Clear((char *)this + 216);
  *((_QWORD *)this + 13) = &CTimer<CSsdpNotifyRequest>::`vftable';
  CTimerBase::~CTimerBase((CSsdpNotifyRequest *)((char *)this + 104));
  free(*((void **)this + 9));
  *((_QWORD *)this + 9) = 0;
  free(*((void **)this + 7));
  *((_QWORD *)this + 7) = 0;
  free(*((void **)this + 6));
  *((_QWORD *)this + 6) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000b764  push    rbx
0x18000b766  sub     rsp, 20h
0x18000b76a  mov     rbx, rcx
0x18000b76d  add     rcx, 110h; lpCriticalSection
0x18000b774  call    cs:__imp_DeleteCriticalSection
0x18000b77b  nop     dword ptr [rax+rax+00h]
0x18000b780  mov     rcx, [rbx+148h]; Block
0x18000b787  test    rcx, rcx
0x18000b78a  jz      short loc_18000B798
0x18000b78c  call    cs:__imp_free
0x18000b793  nop     dword ptr [rax+rax+00h]
0x18000b798  mov     rcx, [rbx+150h]; Block
0x18000b79f  test    rcx, rcx
0x18000b7a2  jz      short loc_18000B7B0
0x18000b7a4  call    cs:__imp_free
0x18000b7ab  nop     dword ptr [rax+rax+00h]
0x18000b7b0  mov     rcx, [rbx+138h]; hObject
0x18000b7b7  test    rcx, rcx
0x18000b7ba  jz      short loc_18000B7C8
0x18000b7bc  call    cs:__imp_CloseHandle
0x18000b7c3  nop     dword ptr [rax+rax+00h]
0x18000b7c8  mov     rcx, [rbx+140h]; hObject
0x18000b7cf  test    rcx, rcx
0x18000b7d2  jz      short loc_18000B7E0
0x18000b7d4  call    cs:__imp_CloseHandle
0x18000b7db  nop     dword ptr [rax+rax+00h]
0x18000b7e0  mov     rcx, [rbx+170h]; hObject
0x18000b7e7  test    rcx, rcx
0x18000b7ea  jz      short loc_18000B7F8
0x18000b7ec  call    cs:__imp_CloseHandle
0x18000b7f3  nop     dword ptr [rax+rax+00h]
0x18000b7f8  lea     rcx, [rbx+0D8h]
0x18000b7ff  call    ?Clear@?$CUList@VCSsdpPendingNotification@@@@QEAAXXZ; CUList<CSsdpPendingNotification>::Clear(void)
0x18000b804  lea     rcx, [rbx+68h]; this
0x18000b808  lea     rax, ??_7?$CTimer@VCSsdpNotifyRequest@@@@6B@; const CTimer<CSsdpNotifyRequest>::`vftable'
0x18000b80f  mov     [rcx], rax
0x18000b812  call    ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
0x18000b817  mov     rcx, [rbx+48h]; Block
0x18000b81b  call    cs:__imp_free
0x18000b822  nop     dword ptr [rax+rax+00h]
0x18000b827  mov     qword ptr [rbx+48h], 0
0x18000b82f  mov     rcx, [rbx+38h]; Block
0x18000b833  call    cs:__imp_free
0x18000b83a  nop     dword ptr [rax+rax+00h]
0x18000b83f  mov     qword ptr [rbx+38h], 0
0x18000b847  mov     rcx, [rbx+30h]; Block
0x18000b84b  call    cs:__imp_free
0x18000b852  nop     dword ptr [rax+rax+00h]
0x18000b857  lea     rcx, [rbx+8]
0x18000b85b  mov     qword ptr [rbx+30h], 0
0x18000b863  add     rsp, 20h
0x18000b867  pop     rbx
0x18000b868  jmp     cs:__imp_DeleteCriticalSection
```
