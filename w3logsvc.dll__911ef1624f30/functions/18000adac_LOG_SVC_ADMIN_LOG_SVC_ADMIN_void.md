# LOG_SVC_ADMIN::~LOG_SVC_ADMIN(void)

- ea: `0x18000adac`
- end: `0x18000aec1`
- name: `??1LOG_SVC_ADMIN@@UEAA@XZ`
- size: `277`
- prototype: `void __fastcall(LOG_SVC_ADMIN *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000b050`

## callees

- `0x18000aca8`
- `0x18000adac`
- `0x18000aec8`
- `0x18000d750`
- `0x18000e400`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000adf8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000adf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000add7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000add7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ae70`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ae7d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ae70`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ae7d`

## pseudocode

```c
void __fastcall LOG_SVC_ADMIN::~LOG_SVC_ADMIN(LOG_SVC_ADMIN *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &LOG_SVC_ADMIN::`vftable';
  *((_DWORD *)this + 2) = 1987275895;
  McGenEventUnregister_EventUnregister();
  v2 = (void *)*((_QWORD *)this + 236);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 236) = 0;
  }
  if ( *((_DWORD *)this + 501) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2008));
    *((_DWORD *)this + 501) = 0;
  }
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 4) = 0;
  }
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 3) = 0;
  }
  *((_DWORD *)this + 500) = 1668246648;
  STRU::~STRU((LOG_SVC_ADMIN *)((char *)this + 1784));
  STRU::~STRU((LOG_SVC_ADMIN *)((char *)this + 1696));
  *((_QWORD *)this + 198) = &MULTI_WORK_QUEUE::`vftable';
  *((_DWORD *)this + 398) = 1483896685;
  STTABLE::~STTABLE((LOG_SVC_ADMIN *)((char *)this + 1400));
  HTTP_LOG_EVENT_HANDLER::Terminate((LOG_SVC_ADMIN *)((char *)this + 1160));
  HTTP_LOG_SITE_TABLE::~HTTP_LOG_SITE_TABLE((LOG_SVC_ADMIN *)((char *)this + 40));
}

```

## disassembly

```asm
0x18000adac  push    rbx
0x18000adae  sub     rsp, 20h
0x18000adb2  mov     rbx, rcx
0x18000adb5  lea     rax, ??_7LOG_SVC_ADMIN@@6B@; const LOG_SVC_ADMIN::`vftable'
0x18000adbc  mov     [rcx], rax
0x18000adbf  mov     dword ptr [rcx+8], 76736C77h
0x18000adc6  call    McGenEventUnregister_EventUnregister
0x18000adcb  mov     rcx, [rbx+760h]; hObject
0x18000add2  test    rcx, rcx
0x18000add5  jz      short loc_18000ADE8
0x18000add7  call    cs:__imp_CloseHandle
0x18000addd  mov     qword ptr [rbx+760h], 0
0x18000ade8  cmp     dword ptr [rbx+7D4h], 0
0x18000adef  jz      short loc_18000AE08
0x18000adf1  lea     rcx, [rbx+7D8h]; lpCriticalSection
0x18000adf8  call    cs:__imp_DeleteCriticalSection
0x18000adfe  mov     dword ptr [rbx+7D4h], 0
0x18000ae08  mov     rcx, [rbx+10h]
0x18000ae0c  test    rcx, rcx
0x18000ae0f  jz      short loc_18000AE25
0x18000ae11  mov     rax, [rcx]
0x18000ae14  mov     rax, [rax+10h]
0x18000ae18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae1d  mov     qword ptr [rbx+10h], 0
0x18000ae25  mov     rcx, [rbx+20h]
0x18000ae29  test    rcx, rcx
0x18000ae2c  jz      short loc_18000AE42
0x18000ae2e  mov     rax, [rcx]
0x18000ae31  mov     rax, [rax+10h]
0x18000ae35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae3a  mov     qword ptr [rbx+20h], 0
0x18000ae42  mov     rcx, [rbx+18h]
0x18000ae46  test    rcx, rcx
0x18000ae49  jz      short loc_18000AE5F
0x18000ae4b  mov     rax, [rcx]
0x18000ae4e  mov     rax, [rax+10h]
0x18000ae52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae57  mov     qword ptr [rbx+18h], 0
0x18000ae5f  mov     dword ptr [rbx+7D0h], 636F6C78h
0x18000ae69  lea     rcx, [rbx+6F8h]
0x18000ae70  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ae76  lea     rcx, [rbx+6A0h]
0x18000ae7d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ae83  lea     rax, ??_7MULTI_WORK_QUEUE@@6B@; const MULTI_WORK_QUEUE::`vftable'
0x18000ae8a  mov     [rbx+630h], rax
0x18000ae91  mov     dword ptr [rbx+638h], 5872776Dh
0x18000ae9b  lea     rcx, [rbx+578h]; this
0x18000aea2  call    ??1STTABLE@@UEAA@XZ; STTABLE::~STTABLE(void)
0x18000aea7  lea     rcx, [rbx+488h]; this
0x18000aeae  call    ?Terminate@HTTP_LOG_EVENT_HANDLER@@QEAAJXZ; HTTP_LOG_EVENT_HANDLER::Terminate(void)
0x18000aeb3  lea     rcx, [rbx+28h]; this
0x18000aeb7  add     rsp, 20h
0x18000aebb  pop     rbx
0x18000aebc  jmp     ??1HTTP_LOG_SITE_TABLE@@UEAA@XZ; HTTP_LOG_SITE_TABLE::~HTTP_LOG_SITE_TABLE(void)
```
