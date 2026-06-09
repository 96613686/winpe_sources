# CSsdpSearchRequest::~CSsdpSearchRequest(void)

- ea: `0x18000b8cc`
- end: `0x18000ba26`
- name: `??1CSsdpSearchRequest@@QEAA@XZ`
- size: `346`
- prototype: `void __fastcall(CSsdpSearchRequest *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b87c`

## callees

- `0x180008190`
- `0x18000ae2c`
- `0x18000b8cc`
- `0x18000ba2c`
- `0x180019920`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b992`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b9aa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b992`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b9aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b949`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b95c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b949`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b95c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b90d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b90d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba01`

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
0x18000b8cc  mov     [rsp+arg_8], rbx
0x18000b8d1  push    rdi
0x18000b8d2  sub     rsp, 20h
0x18000b8d6  mov     rbx, rcx
0x18000b8d9  mov     rcx, [rcx+0E8h]; hObject
0x18000b8e0  test    rcx, rcx
0x18000b8e3  jnz     loc_18000BA01
0x18000b8e9  mov     rcx, [rbx+0F0h]; hObject
0x18000b8f0  test    rcx, rcx
0x18000b8f3  jz      short loc_18000B901
0x18000b8f5  call    cs:__imp_CloseHandle
0x18000b8fc  nop     dword ptr [rax+rax+00h]
0x18000b901  mov     rcx, [rbx+0F8h]; hObject
0x18000b908  test    rcx, rcx
0x18000b90b  jz      short loc_18000B919
0x18000b90d  call    cs:__imp_CloseHandle
0x18000b914  nop     dword ptr [rax+rax+00h]
0x18000b919  lea     rdi, [rbx+20h]
0x18000b91d  cmp     qword ptr [rdi], 0
0x18000b921  mov     rax, rdi
0x18000b924  mov     [rsp+28h+arg_0], rax
0x18000b929  jnz     loc_18000B9CA
0x18000b92f  mov     rcx, [rdi]; void *
0x18000b932  test    rcx, rcx
0x18000b935  jnz     loc_18000BA12
0x18000b93b  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18000b942  mov     qword ptr [rdi], 0
0x18000b949  call    cs:__imp_DeleteCriticalSection
0x18000b950  nop     dword ptr [rax+rax+00h]
0x18000b955  lea     rcx, [rbx+98h]; lpCriticalSection
0x18000b95c  call    cs:__imp_DeleteCriticalSection
0x18000b963  nop     dword ptr [rax+rax+00h]
0x18000b968  lea     rcx, [rbx+30h]; this
0x18000b96c  lea     rax, ??_7?$CTimer@VCSsdpSearchRequest@@@@6B@; const CTimer<CSsdpSearchRequest>::`vftable'
0x18000b973  mov     [rcx], rax
0x18000b976  call    ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
0x18000b97b  mov     rcx, [rdi]; void *
0x18000b97e  test    rcx, rcx
0x18000b981  jnz     loc_18000BA1C
0x18000b987  mov     qword ptr [rdi], 0
0x18000b98e  mov     rcx, [rbx+10h]; Block
0x18000b992  call    cs:__imp_free
0x18000b999  nop     dword ptr [rax+rax+00h]
0x18000b99e  mov     qword ptr [rbx+10h], 0
0x18000b9a6  mov     rcx, [rbx+8]; Block
0x18000b9aa  call    cs:__imp_free
0x18000b9b1  nop     dword ptr [rax+rax+00h]
0x18000b9b6  mov     qword ptr [rbx+8], 0
0x18000b9be  mov     rbx, [rsp+28h+arg_8]
0x18000b9c3  add     rsp, 20h
0x18000b9c7  pop     rdi
0x18000b9c8  retn
0x18000b9ca  test    rax, rax
0x18000b9cd  jz      loc_18000B92F
0x18000b9d3  mov     rcx, [rax]
0x18000b9d6  test    rcx, rcx
0x18000b9d9  jz      loc_18000B92F
0x18000b9df  add     rcx, 8; struct _SSDP_REQUEST *
0x18000b9e3  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x18000b9e8  lea     rcx, [rsp+28h+arg_0]
0x18000b9ed  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18000b9f2  test    eax, eax
0x18000b9f4  jnz     loc_18000B92F
0x18000b9fa  mov     rax, [rsp+28h+arg_0]
0x18000b9ff  jmp     short loc_18000B9CA
0x18000ba01  call    cs:__imp_CloseHandle
0x18000ba08  nop     dword ptr [rax+rax+00h]
0x18000ba0d  jmp     loc_18000B8E9
0x18000ba12  call    ??_GNode@?$CUList@_J@@QEAAPEAXI@Z; CUList<__int64>::Node::`scalar deleting destructor'(uint)
0x18000ba17  jmp     loc_18000B93B
0x18000ba1c  call    ??_GNode@?$CUList@_J@@QEAAPEAXI@Z; CUList<__int64>::Node::`scalar deleting destructor'(uint)
0x18000ba21  jmp     loc_18000B987
```
