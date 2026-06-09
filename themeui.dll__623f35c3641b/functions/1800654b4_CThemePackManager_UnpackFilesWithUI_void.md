# CThemePackManager::_UnpackFilesWithUI(void)

- ea: `0x1800654b4`
- end: `0x1800655fc`
- name: `?_UnpackFilesWithUI@CThemePackManager@@AEAAJXZ`
- size: `328`
- prototype: `__int64 __fastcall(CThemePackManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180062f3c`

## callees

- `0x1800640a0`
- `0x1800654b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800654f4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800654fe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800654f4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800654fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065516`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065516`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800655dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800655e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800655dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800655e7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180065582`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180065582`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006555c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006555c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800655aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800655c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800655aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800655c1`

## pseudocode

```c
__int64 __fastcall CThemePackManager::_UnpackFilesWithUI(CThemePackManager *this)
{
  int v1; // edi
  unsigned int i; // esi
  HANDLE EventW; // rcx
  __int64 v5; // rax
  HANDLE Thread; // rax
  __int64 j; // rsi
  void *v8; // rcx
  DWORD ExitCode; // [rsp+70h] [rbp+8h] BYREF

  *((_QWORD *)this + 546) = this;
  *((_QWORD *)this + 545) = CThemePackManager::_UnpackNotifyWithUI;
  v1 = 0;
  *((_QWORD *)this + 620) = 0;
  *((_DWORD *)this + 38) = 0;
  ExitCode = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  for ( i = 0; i < 4; ++i )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v5 = (int)i;
    if ( !EventW )
      v1 = -2147467259;
    *((_QWORD *)this + v5 + 4) = EventW;
  }
  if ( v1 >= 0 )
  {
    Thread = CreateThread(0, 0, CThemePackManager::_UnpackThreadProc, this, 4u, (LPDWORD)this + 6);
    *((_QWORD *)this + 2) = Thread;
    if ( Thread )
    {
      v1 = CThemePackManager::_InitiateUnpack(this);
      if ( v1 >= 0 && GetExitCodeThread(*((HANDLE *)this + 2), &ExitCode) && ExitCode )
        v1 = *((_DWORD *)this + 38) != 0 ? -2147023673 : -2147467259;
      CloseHandle(*((HANDLE *)this + 2));
    }
    else
    {
      v1 = -2147467259;
    }
    for ( j = 0; j != 4; ++j )
    {
      v8 = (void *)*((_QWORD *)this + j + 4);
      if ( v8 )
        CloseHandle(v8);
      *((_QWORD *)this + j + 4) = 0;
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800654b4  push    rbx
0x1800654b6  push    rbp
0x1800654b7  push    rsi
0x1800654b8  push    rdi
0x1800654b9  push    r12
0x1800654bb  push    r14
0x1800654bd  sub     rsp, 38h
0x1800654c1  mov     [rcx+1110h], rcx
0x1800654c8  lea     rax, ?_UnpackNotifyWithUI@CThemePackManager@@CAHI_J0PEAX@Z; CThemePackManager::_UnpackNotifyWithUI(uint,__int64,__int64,void *)
0x1800654cf  mov     [rcx+1108h], rax
0x1800654d6  xor     edi, edi
0x1800654d8  mov     [rcx+1360h], rdi
0x1800654df  mov     rbx, rcx
0x1800654e2  mov     [rcx+98h], edi
0x1800654e8  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800654ec  mov     [rsp+68h+ExitCode], 1
0x1800654f4  call    cs:__imp_InitializeCriticalSection
0x1800654fa  lea     rcx, [rbx+70h]; lpCriticalSection
0x1800654fe  call    cs:__imp_InitializeCriticalSection
0x180065504  xor     esi, esi
0x180065506  mov     r12d, 80004005h
0x18006550c  xor     r9d, r9d; lpName
0x18006550f  xor     r8d, r8d; bInitialState
0x180065512  xor     edx, edx; bManualReset
0x180065514  xor     ecx, ecx; lpEventAttributes
0x180065516  call    cs:__imp_CreateEventW
0x18006551c  mov     rcx, rax
0x18006551f  movsxd  rax, esi
0x180065522  test    rcx, rcx
0x180065525  cmovz   edi, r12d
0x180065529  inc     esi
0x18006552b  mov     [rbx+rax*8+20h], rcx
0x180065530  cmp     esi, 4
0x180065533  jb      short loc_18006550C
0x180065535  test    edi, edi
0x180065537  js      loc_1800655D9
0x18006553d  lea     rax, [rbx+18h]
0x180065541  mov     r9, rbx; lpParameter
0x180065544  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180065549  lea     r8, ?_UnpackThreadProc@CThemePackManager@@CAKPEAX@Z; lpStartAddress
0x180065550  xor     edx, edx; dwStackSize
0x180065552  mov     [rsp+68h+dwCreationFlags], 4; dwCreationFlags
0x18006555a  xor     ecx, ecx; lpThreadAttributes
0x18006555c  call    cs:__imp_CreateThread
0x180065562  mov     [rbx+10h], rax
0x180065566  test    rax, rax
0x180065569  jz      short loc_1800655B2
0x18006556b  mov     rcx, rbx; this
0x18006556e  call    ?_InitiateUnpack@CThemePackManager@@AEAAJXZ; CThemePackManager::_InitiateUnpack(void)
0x180065573  mov     edi, eax
0x180065575  test    eax, eax
0x180065577  js      short loc_1800655A6
0x180065579  mov     rcx, [rbx+10h]; hThread
0x18006557d  lea     rdx, [rsp+68h+ExitCode]; lpExitCode
0x180065582  call    cs:__imp_GetExitCodeThread
0x180065588  test    eax, eax
0x18006558a  jz      short loc_1800655A6
0x18006558c  cmp     [rsp+68h+ExitCode], 0
0x180065591  jz      short loc_1800655A6
0x180065593  mov     eax, [rbx+98h]
0x180065599  neg     eax
0x18006559b  sbb     edi, edi
0x18006559d  and     edi, 6C4C2h
0x1800655a3  add     edi, r12d
0x1800655a6  mov     rcx, [rbx+10h]; hObject
0x1800655aa  call    cs:__imp_CloseHandle
0x1800655b0  jmp     short loc_1800655B5
0x1800655b2  mov     edi, r12d
0x1800655b5  xor     esi, esi
0x1800655b7  mov     rcx, [rbx+rsi*8+20h]; hObject
0x1800655bc  test    rcx, rcx
0x1800655bf  jz      short loc_1800655C7
0x1800655c1  call    cs:__imp_CloseHandle
0x1800655c7  mov     qword ptr [rbx+rsi*8+20h], 0
0x1800655d0  inc     rsi
0x1800655d3  cmp     rsi, 4
0x1800655d7  jnz     short loc_1800655B7
0x1800655d9  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800655dd  call    cs:__imp_DeleteCriticalSection
0x1800655e3  lea     rcx, [rbx+70h]; lpCriticalSection
0x1800655e7  call    cs:__imp_DeleteCriticalSection
0x1800655ed  mov     eax, edi
0x1800655ef  add     rsp, 38h
0x1800655f3  pop     r14
0x1800655f5  pop     r12
0x1800655f7  pop     rdi
0x1800655f8  pop     rsi
0x1800655f9  pop     rbp
0x1800655fa  pop     rbx
0x1800655fb  retn
```
