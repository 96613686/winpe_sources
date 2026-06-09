# CAPCThread::Initialize(void)

- ea: `0x18002d270`
- end: `0x18002d44f`
- name: `?Initialize@CAPCThread@@UEAAJXZ`
- size: `479`
- prototype: `__int64 __fastcall(CAPCThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a99c`

## callees

- `0x18000b8f8`
- `0x18000f79c`
- `0x18002d270`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d401`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d401`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d418`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d292`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d292`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d42f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d42f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d2f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d2f3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002d369`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002d369`

## pseudocode

```c
__int64 __fastcall CAPCThread::Initialize(CAPCThread *this)
{
  HANDLE EventW; // rax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  HANDLE Thread; // rax
  bool v7; // sf
  void *v8; // rcx
  void *v9; // rcx
  HMODULE v10; // rcx

  *((_DWORD *)this + 5) |= 2u;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 6) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_19;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 13;
LABEL_18:
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v5,
      WPP_e06d9da063383fc2b93c39ab877dcc3d_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
LABEL_19:
    v7 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError < 0;
    }
    v8 = (void *)*((_QWORD *)this + 6);
    if ( !v7 )
      LastError = -2147467259;
    if ( v8 )
    {
      CloseHandle(v8);
      *((_QWORD *)this + 6) = 0;
    }
    v9 = (void *)*((_QWORD *)this + 5);
    if ( v9 )
    {
      CloseHandle(v9);
      *((_QWORD *)this + 5) = 0;
    }
    v10 = (HMODULE)*((_QWORD *)this + 7);
    if ( v10 )
    {
      FreeLibrary(v10);
      *((_QWORD *)this + 7) = 0;
    }
    return (unsigned int)LastError;
  }
  if ( !GetModuleHandleExW(4u, (LPCWSTR)CAPCThread::static_APC_thread, (HMODULE *)this + 7) )
  {
    LastError = GetLastError();
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_19;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 14;
    goto LABEL_18;
  }
  LastError = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
  Thread = CreateThread(0, 0, CAPCThread::static_APC_thread, (char *)this - 16, 0, 0);
  *((_QWORD *)this + 5) = Thread;
  if ( !Thread )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 16LL))(*((_QWORD *)this + 3));
  if ( !*((_QWORD *)this + 5) )
  {
    LastError = GetLastError();
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_19;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 15;
    goto LABEL_18;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002d270  mov     [rsp+arg_0], rbx
0x18002d275  mov     [rsp+arg_8], rsi
0x18002d27a  push    rdi
0x18002d27b  sub     rsp, 30h
0x18002d27f  or      dword ptr [rcx+14h], 2
0x18002d283  xor     r9d, r9d; lpName
0x18002d286  mov     rdi, rcx
0x18002d289  xor     r8d, r8d; bInitialState
0x18002d28c  xor     ecx, ecx; lpEventAttributes
0x18002d28e  lea     edx, [r9+1]; bManualReset
0x18002d292  call    cs:__imp_CreateEventW
0x18002d298  mov     [rdi+30h], rax
0x18002d29c  test    rax, rax
0x18002d29f  jnz     short loc_18002D2E3
0x18002d2a1  call    cs:__imp_GetLastError
0x18002d2a7  mov     ebx, eax
0x18002d2a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2b0  lea     rax, WPP_GLOBAL_Control
0x18002d2b7  cmp     rcx, rax
0x18002d2ba  jz      loc_18002D3E1
0x18002d2c0  test    byte ptr [rcx+1Ch], 8
0x18002d2c4  jz      loc_18002D3E1
0x18002d2ca  cmp     byte ptr [rcx+19h], 2
0x18002d2ce  jb      loc_18002D3E1
0x18002d2d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002d2d9  mov     edx, 0Dh
0x18002d2de  jmp     loc_18002D3C3
0x18002d2e3  lea     r8, [rdi+38h]; phModule
0x18002d2e7  mov     ecx, 4; dwFlags
0x18002d2ec  lea     rdx, ?static_APC_thread@CAPCThread@@SAKPEAX@Z; lpModuleName
0x18002d2f3  call    cs:__imp_GetModuleHandleExW
0x18002d2f9  test    eax, eax
0x18002d2fb  jnz     short loc_18002D33F
0x18002d2fd  call    cs:__imp_GetLastError
0x18002d303  mov     ebx, eax
0x18002d305  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d30c  lea     rax, WPP_GLOBAL_Control
0x18002d313  cmp     rcx, rax
0x18002d316  jz      loc_18002D3E1
0x18002d31c  test    byte ptr [rcx+1Ch], 8
0x18002d320  jz      loc_18002D3E1
0x18002d326  cmp     byte ptr [rcx+19h], 2
0x18002d32a  jb      loc_18002D3E1
0x18002d330  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002d335  mov     edx, 0Eh
0x18002d33a  jmp     loc_18002D3C3
0x18002d33f  mov     rcx, [rdi+18h]
0x18002d343  xor     ebx, ebx
0x18002d345  mov     rax, [rcx]
0x18002d348  mov     rax, [rax+8]
0x18002d34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d351  lea     r9, [rdi-10h]; lpParameter
0x18002d355  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x18002d35a  lea     r8, ?static_APC_thread@CAPCThread@@SAKPEAX@Z; lpStartAddress
0x18002d361  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x18002d365  xor     edx, edx; dwStackSize
0x18002d367  xor     ecx, ecx; lpThreadAttributes
0x18002d369  call    cs:__imp_CreateThread
0x18002d36f  mov     [rdi+28h], rax
0x18002d373  test    rax, rax
0x18002d376  jnz     short loc_18002D388
0x18002d378  mov     rcx, [rdi+18h]
0x18002d37c  mov     rax, [rcx]
0x18002d37f  mov     rax, [rax+10h]
0x18002d383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d388  cmp     [rdi+28h], rbx
0x18002d38c  jnz     loc_18002D43D
0x18002d392  call    cs:__imp_GetLastError
0x18002d398  mov     ebx, eax
0x18002d39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3a1  lea     rax, WPP_GLOBAL_Control
0x18002d3a8  cmp     rcx, rax
0x18002d3ab  jz      short loc_18002D3E1
0x18002d3ad  test    byte ptr [rcx+1Ch], 8
0x18002d3b1  jz      short loc_18002D3E1
0x18002d3b3  cmp     byte ptr [rcx+19h], 2
0x18002d3b7  jb      short loc_18002D3E1
0x18002d3b9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002d3be  mov     edx, 0Fh
0x18002d3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3ca  lea     r8, WPP_e06d9da063383fc2b93c39ab877dcc3d_Traceguids
0x18002d3d1  mov     r9d, eax
0x18002d3d4  mov     [rsp+38h+dwCreationFlags], ebx
0x18002d3d8  mov     rcx, [rcx+10h]
0x18002d3dc  call    WPP_SF_Dd
0x18002d3e1  test    ebx, ebx
0x18002d3e3  jle     short loc_18002D3F0
0x18002d3e5  movzx   ebx, bx
0x18002d3e8  or      ebx, 80070000h
0x18002d3ee  test    ebx, ebx
0x18002d3f0  mov     rcx, [rdi+30h]; hObject
0x18002d3f4  mov     eax, 80004005h
0x18002d3f9  cmovns  ebx, eax
0x18002d3fc  test    rcx, rcx
0x18002d3ff  jz      short loc_18002D40F
0x18002d401  call    cs:__imp_CloseHandle
0x18002d407  mov     qword ptr [rdi+30h], 0
0x18002d40f  mov     rcx, [rdi+28h]; hObject
0x18002d413  test    rcx, rcx
0x18002d416  jz      short loc_18002D426
0x18002d418  call    cs:__imp_CloseHandle
0x18002d41e  mov     qword ptr [rdi+28h], 0
0x18002d426  mov     rcx, [rdi+38h]; hLibModule
0x18002d42a  test    rcx, rcx
0x18002d42d  jz      short loc_18002D43D
0x18002d42f  call    cs:__imp_FreeLibrary
0x18002d435  mov     qword ptr [rdi+38h], 0
0x18002d43d  mov     rsi, [rsp+38h+arg_8]
0x18002d442  mov     eax, ebx
0x18002d444  mov     rbx, [rsp+38h+arg_0]
0x18002d449  add     rsp, 30h
0x18002d44d  pop     rdi
0x18002d44e  retn
```
