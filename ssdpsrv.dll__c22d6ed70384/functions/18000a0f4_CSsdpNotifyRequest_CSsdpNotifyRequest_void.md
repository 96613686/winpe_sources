# CSsdpNotifyRequest::~CSsdpNotifyRequest(void)

- ea: `0x18000a0f4`
- end: `0x18000a1c9`
- name: `??1CSsdpNotifyRequest@@QEAA@XZ`
- size: `213`
- prototype: `void __fastcall(CSsdpNotifyRequest *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000931c`

## callees

- `0x18000a0f4`
- `0x18000a358`
- `0x18000a3c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a116`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a128`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a187`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a199`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a1ab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a116`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a128`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a187`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a199`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a1ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a104`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a104`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a1c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a13a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a14c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a15e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a13a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a14c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a15e`

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
0x18000a0f4  push    rbx
0x18000a0f6  sub     rsp, 20h
0x18000a0fa  mov     rbx, rcx
0x18000a0fd  add     rcx, 110h; lpCriticalSection
0x18000a104  call    cs:__imp_DeleteCriticalSection
0x18000a10a  mov     rcx, [rbx+148h]; Block
0x18000a111  test    rcx, rcx
0x18000a114  jz      short loc_18000A11C
0x18000a116  call    cs:__imp_free
0x18000a11c  mov     rcx, [rbx+150h]; Block
0x18000a123  test    rcx, rcx
0x18000a126  jz      short loc_18000A12E
0x18000a128  call    cs:__imp_free
0x18000a12e  mov     rcx, [rbx+138h]; hObject
0x18000a135  test    rcx, rcx
0x18000a138  jz      short loc_18000A140
0x18000a13a  call    cs:__imp_CloseHandle
0x18000a140  mov     rcx, [rbx+140h]; hObject
0x18000a147  test    rcx, rcx
0x18000a14a  jz      short loc_18000A152
0x18000a14c  call    cs:__imp_CloseHandle
0x18000a152  mov     rcx, [rbx+170h]; hObject
0x18000a159  test    rcx, rcx
0x18000a15c  jz      short loc_18000A164
0x18000a15e  call    cs:__imp_CloseHandle
0x18000a164  lea     rcx, [rbx+0D8h]
0x18000a16b  call    ?Clear@?$CUList@VCSsdpPendingNotification@@@@QEAAXXZ; CUList<CSsdpPendingNotification>::Clear(void)
0x18000a170  lea     rcx, [rbx+68h]; this
0x18000a174  lea     rax, ??_7?$CTimer@VCSsdpNotifyRequest@@@@6B@; const CTimer<CSsdpNotifyRequest>::`vftable'
0x18000a17b  mov     [rcx], rax
0x18000a17e  call    ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
0x18000a183  mov     rcx, [rbx+48h]; Block
0x18000a187  call    cs:__imp_free
0x18000a18d  mov     qword ptr [rbx+48h], 0
0x18000a195  mov     rcx, [rbx+38h]; Block
0x18000a199  call    cs:__imp_free
0x18000a19f  mov     qword ptr [rbx+38h], 0
0x18000a1a7  mov     rcx, [rbx+30h]; Block
0x18000a1ab  call    cs:__imp_free
0x18000a1b1  lea     rcx, [rbx+8]
0x18000a1b5  mov     qword ptr [rbx+30h], 0
0x18000a1bd  add     rsp, 20h
0x18000a1c1  pop     rbx
0x18000a1c2  jmp     cs:__imp_DeleteCriticalSection
```
