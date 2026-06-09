# CSsdpSearchRequest::~CSsdpSearchRequest(void)

- ea: `0x18000a220`
- end: `0x18000a34f`
- name: `??1CSsdpSearchRequest@@QEAA@XZ`
- size: `303`
- prototype: `void __fastcall(CSsdpSearchRequest *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a1d0`

## callees

- `0x180006d70`
- `0x18000a220`
- `0x18000a358`
- `0x18000a6b8`
- `0x1800186a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a2ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a2e0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a2ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a2e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a291`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a29e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a291`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a29e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a249`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a25b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a330`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a249`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a25b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a330`

## pseudocode

```c
void __fastcall CSsdpSearchRequest::~CSsdpSearchRequest(CSsdpSearchRequest *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void **v5; // rdi
  bool v6; // zf
  char *v7; // rax
  char *v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = (void *)*((_QWORD *)this + 29);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 30);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 31);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void **)((char *)this + 32);
  v6 = *((_QWORD *)this + 4) == 0;
  v7 = (char *)this + 32;
  v8 = (char *)this + 32;
  if ( !v6 )
  {
    while ( v7 )
    {
      if ( !*(_QWORD *)v7 )
        break;
      FreeSsdpRequest((struct _SSDP_REQUEST *)(*(_QWORD *)v7 + 8LL));
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext(&v8) )
        break;
      v7 = v8;
    }
  }
  if ( *v5 )
    CUList<__int64>::Node::`scalar deleting destructor'(*v5);
  *v5 = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  *((_QWORD *)this + 6) = &CTimer<CSsdpSearchRequest>::`vftable';
  CTimerBase::~CTimerBase((CSsdpSearchRequest *)((char *)this + 48));
  if ( *v5 )
    CUList<__int64>::Node::`scalar deleting destructor'(*v5);
  *v5 = 0;
  free(*((void **)this + 2));
  *((_QWORD *)this + 2) = 0;
  free(*((void **)this + 1));
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18000a220  mov     [rsp+arg_8], rbx
0x18000a225  push    rdi
0x18000a226  sub     rsp, 20h
0x18000a22a  mov     rbx, rcx
0x18000a22d  mov     rcx, [rcx+0E8h]; hObject
0x18000a234  test    rcx, rcx
0x18000a237  jnz     loc_18000A330
0x18000a23d  mov     rcx, [rbx+0F0h]; hObject
0x18000a244  test    rcx, rcx
0x18000a247  jz      short loc_18000A24F
0x18000a249  call    cs:__imp_CloseHandle
0x18000a24f  mov     rcx, [rbx+0F8h]; hObject
0x18000a256  test    rcx, rcx
0x18000a259  jz      short loc_18000A261
0x18000a25b  call    cs:__imp_CloseHandle
0x18000a261  lea     rdi, [rbx+20h]
0x18000a265  cmp     qword ptr [rdi], 0
0x18000a269  mov     rax, rdi
0x18000a26c  mov     [rsp+28h+arg_0], rax
0x18000a271  jnz     loc_18000A2F9
0x18000a277  mov     rcx, [rdi]; Block
0x18000a27a  test    rcx, rcx
0x18000a27d  jnz     loc_18000A33B
0x18000a283  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18000a28a  mov     qword ptr [rdi], 0
0x18000a291  call    cs:__imp_DeleteCriticalSection
0x18000a297  lea     rcx, [rbx+98h]; lpCriticalSection
0x18000a29e  call    cs:__imp_DeleteCriticalSection
0x18000a2a4  lea     rcx, [rbx+30h]; this
0x18000a2a8  lea     rax, ??_7?$CTimer@VCSsdpSearchRequest@@@@6B@; const CTimer<CSsdpSearchRequest>::`vftable'
0x18000a2af  mov     [rcx], rax
0x18000a2b2  call    ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
0x18000a2b7  mov     rcx, [rdi]; Block
0x18000a2ba  test    rcx, rcx
0x18000a2bd  jnz     loc_18000A345
0x18000a2c3  mov     qword ptr [rdi], 0
0x18000a2ca  mov     rcx, [rbx+10h]; Block
0x18000a2ce  call    cs:__imp_free
0x18000a2d4  mov     qword ptr [rbx+10h], 0
0x18000a2dc  mov     rcx, [rbx+8]; Block
0x18000a2e0  call    cs:__imp_free
0x18000a2e6  mov     qword ptr [rbx+8], 0
0x18000a2ee  mov     rbx, [rsp+28h+arg_8]
0x18000a2f3  add     rsp, 20h
0x18000a2f7  pop     rdi
0x18000a2f8  retn
0x18000a2f9  test    rax, rax
0x18000a2fc  jz      loc_18000A277
0x18000a302  mov     rcx, [rax]
0x18000a305  test    rcx, rcx
0x18000a308  jz      loc_18000A277
0x18000a30e  add     rcx, 8; struct _SSDP_REQUEST *
0x18000a312  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x18000a317  lea     rcx, [rsp+28h+arg_0]
0x18000a31c  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18000a321  test    eax, eax
0x18000a323  jnz     loc_18000A277
0x18000a329  mov     rax, [rsp+28h+arg_0]
0x18000a32e  jmp     short loc_18000A2F9
0x18000a330  call    cs:__imp_CloseHandle
0x18000a336  jmp     loc_18000A23D
0x18000a33b  call    ??_GNode@?$CUList@_J@@QEAAPEAXI@Z; CUList<__int64>::Node::`scalar deleting destructor'(uint)
0x18000a340  jmp     loc_18000A283
0x18000a345  call    ??_GNode@?$CUList@_J@@QEAAPEAXI@Z; CUList<__int64>::Node::`scalar deleting destructor'(uint)
0x18000a34a  jmp     loc_18000A2C3
```
