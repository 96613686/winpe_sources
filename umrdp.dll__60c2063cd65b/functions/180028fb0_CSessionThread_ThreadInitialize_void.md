# CSessionThread::ThreadInitialize(void)

- ea: `0x180028fb0`
- end: `0x1800291cd`
- name: `?ThreadInitialize@CSessionThread@@AEAAJXZ`
- size: `541`
- prototype: `__int64 __fastcall(CSessionThread *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180028d00`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f79c`
- `0x180028fb0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002911d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002911d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028fce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028fce`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029110`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029110`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002904a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002904a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800290ee`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800290ee`

## string_xrefs

- `0x18002902b`: `CSessionThread::ThreadInitialize failed to create Wakeup Event`
- `0x180029163`: `CSessionThread::ThreadInitialize failed to create worker thread`

## pseudocode

```c
__int64 __fastcall CSessionThread::ThreadInitialize(CSessionThread *this)
{
  signed int v2; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // edx
  const char *v7; // rcx
  HMODULE *v8; // rsi
  unsigned int v9; // eax
  HANDLE Thread; // rax
  signed int v11; // eax
  void *v12; // rcx
  void *v13; // rcx

  v2 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 13) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_28;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 17;
      v7 = "CSessionThread::ThreadInitialize failed to create Wakeup Event";
LABEL_27:
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        v6,
        (unsigned int)WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v7,
        v2);
LABEL_28:
      v12 = (void *)*((_QWORD *)this + 13);
      if ( v12 )
      {
        CloseHandle(v12);
        *((_QWORD *)this + 13) = 0;
      }
      v13 = (void *)*((_QWORD *)this + 12);
      if ( v13 )
      {
        CloseHandle(v13);
        *((_QWORD *)this + 12) = 0;
      }
      return (unsigned int)v2;
    }
  }
  v8 = (HMODULE *)((char *)this + 120);
  if ( !GetModuleHandleExW(4u, (LPCWSTR)CSessionThread::static_ThreadProc, (HMODULE *)this + 15) )
  {
    v2 = GetLastError();
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        18,
        WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids,
        v9,
        v2);
    }
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    if ( v2 >= 0 )
      v2 = -2147467259;
    goto LABEL_28;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
  Thread = CreateThread(0, 0, CSessionThread::static_ThreadProc, this, 0, 0);
  *((_QWORD *)this + 12) = Thread;
  if ( !Thread )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
    FreeLibrary(*v8);
    *v8 = 0;
    v11 = GetLastError();
    v2 = v11;
    if ( v11 > 0 )
      v2 = (unsigned __int16)v11 | 0x80070000;
  }
  if ( v2 < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_28;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 19;
    v7 = "CSessionThread::ThreadInitialize failed to create worker thread";
    goto LABEL_27;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180028fb0  mov     [rsp+arg_0], rbx
0x180028fb5  mov     [rsp+arg_8], rsi
0x180028fba  push    rdi
0x180028fbb  sub     rsp, 30h
0x180028fbf  mov     rdi, rcx
0x180028fc2  xor     r9d, r9d; lpName
0x180028fc5  xor     ecx, ecx; lpEventAttributes
0x180028fc7  xor     r8d, r8d; bInitialState
0x180028fca  xor     edx, edx; bManualReset
0x180028fcc  xor     ebx, ebx
0x180028fce  call    cs:__imp_CreateEventW
0x180028fd4  mov     [rdi+68h], rax
0x180028fd8  test    rax, rax
0x180028fdb  jnz     short loc_180029037
0x180028fdd  call    cs:__imp_GetLastError
0x180028fe3  mov     ebx, eax
0x180028fe5  test    eax, eax
0x180028fe7  jle     short loc_180028FF2
0x180028fe9  movzx   ebx, ax
0x180028fec  or      ebx, 80070000h
0x180028ff2  test    ebx, ebx
0x180028ff4  jns     short loc_180029037
0x180028ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ffd  lea     rax, WPP_GLOBAL_Control
0x180029004  cmp     rcx, rax
0x180029007  jz      loc_18002918D
0x18002900d  test    byte ptr [rcx+1Ch], 8
0x180029011  jz      loc_18002918D
0x180029017  cmp     byte ptr [rcx+19h], 2
0x18002901b  jb      loc_18002918D
0x180029021  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029026  mov     edx, 11h
0x18002902b  lea     rcx, aCsessionthread_2; "CSessionThread::ThreadInitialize failed"...
0x180029032  jmp     loc_18002916A
0x180029037  lea     rsi, [rdi+78h]
0x18002903b  mov     ecx, 4; dwFlags
0x180029040  mov     r8, rsi; phModule
0x180029043  lea     rdx, ?static_ThreadProc@CSessionThread@@CAKPEAX@Z; lpModuleName
0x18002904a  call    cs:__imp_GetModuleHandleExW
0x180029050  test    eax, eax
0x180029052  jnz     short loc_1800290BF
0x180029054  call    cs:__imp_GetLastError
0x18002905a  mov     ebx, eax
0x18002905c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029063  lea     rax, WPP_GLOBAL_Control
0x18002906a  cmp     rcx, rax
0x18002906d  jz      short loc_1800290A3
0x18002906f  test    byte ptr [rcx+1Ch], 8
0x180029073  jz      short loc_1800290A3
0x180029075  cmp     byte ptr [rcx+19h], 2
0x180029079  jb      short loc_1800290A3
0x18002907b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029080  mov     rcx, cs:WPP_GLOBAL_Control
0x180029087  lea     r8, WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids
0x18002908e  mov     edx, 12h
0x180029093  mov     [rsp+38h+dwCreationFlags], ebx
0x180029097  mov     r9d, eax
0x18002909a  mov     rcx, [rcx+10h]
0x18002909e  call    WPP_SF_Dd
0x1800290a3  test    ebx, ebx
0x1800290a5  jle     short loc_1800290B0
0x1800290a7  movzx   ebx, bx
0x1800290aa  or      ebx, 80070000h
0x1800290b0  test    ebx, ebx
0x1800290b2  mov     eax, 80004005h
0x1800290b7  cmovns  ebx, eax
0x1800290ba  jmp     loc_18002918D
0x1800290bf  mov     rcx, [rdi+20h]
0x1800290c3  mov     rax, [rcx]
0x1800290c6  mov     rax, [rax+8]
0x1800290ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290cf  mov     r9, rdi; lpParameter
0x1800290d2  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800290db  lea     r8, ?static_ThreadProc@CSessionThread@@CAKPEAX@Z; lpStartAddress
0x1800290e2  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800290ea  xor     edx, edx; dwStackSize
0x1800290ec  xor     ecx, ecx; lpThreadAttributes
0x1800290ee  call    cs:__imp_CreateThread
0x1800290f4  mov     [rdi+60h], rax
0x1800290f8  test    rax, rax
0x1800290fb  jnz     short loc_180029132
0x1800290fd  mov     rcx, [rdi+20h]
0x180029101  mov     rax, [rcx]
0x180029104  mov     rax, [rax+10h]
0x180029108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002910d  mov     rcx, [rsi]; hLibModule
0x180029110  call    cs:__imp_FreeLibrary
0x180029116  mov     qword ptr [rsi], 0
0x18002911d  call    cs:__imp_GetLastError
0x180029123  mov     ebx, eax
0x180029125  test    eax, eax
0x180029127  jle     short loc_180029132
0x180029129  movzx   ebx, ax
0x18002912c  or      ebx, 80070000h
0x180029132  test    ebx, ebx
0x180029134  jns     loc_1800291BB
0x18002913a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029141  lea     rax, WPP_GLOBAL_Control
0x180029148  cmp     rcx, rax
0x18002914b  jz      short loc_18002918D
0x18002914d  test    byte ptr [rcx+1Ch], 8
0x180029151  jz      short loc_18002918D
0x180029153  cmp     byte ptr [rcx+19h], 2
0x180029157  jb      short loc_18002918D
0x180029159  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002915e  mov     edx, 13h
0x180029163  lea     rcx, aCsessionthread_0; "CSessionThread::ThreadInitialize failed"...
0x18002916a  mov     dword ptr [rsp+38h+lpThreadId], ebx
0x18002916e  lea     r8, WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids
0x180029175  mov     qword ptr [rsp+38h+dwCreationFlags], rcx
0x18002917a  mov     r9d, eax
0x18002917d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029184  mov     rcx, [rcx+10h]
0x180029188  call    WPP_SF_DsD
0x18002918d  mov     rcx, [rdi+68h]; hObject
0x180029191  test    rcx, rcx
0x180029194  jz      short loc_1800291A4
0x180029196  call    cs:__imp_CloseHandle
0x18002919c  mov     qword ptr [rdi+68h], 0
0x1800291a4  mov     rcx, [rdi+60h]; hObject
0x1800291a8  test    rcx, rcx
0x1800291ab  jz      short loc_1800291BB
0x1800291ad  call    cs:__imp_CloseHandle
0x1800291b3  mov     qword ptr [rdi+60h], 0
0x1800291bb  mov     rsi, [rsp+38h+arg_8]
0x1800291c0  mov     eax, ebx
0x1800291c2  mov     rbx, [rsp+38h+arg_0]
0x1800291c7  add     rsp, 30h
0x1800291cb  pop     rdi
0x1800291cc  retn
```
