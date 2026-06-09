# CThemePackManager::_PackFilesWithUI(void)

- ea: `0x1800643b8`
- end: `0x18006452f`
- name: `?_PackFilesWithUI@CThemePackManager@@AEAAJXZ`
- size: `375`
- prototype: `__int64 __fastcall(CThemePackManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180062c40`

## callees

- `0x180030f64`
- `0x180063f04`
- `0x1800643b8`
- `0x180065038`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800643f2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800643fc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800643f2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800643fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064414`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064414`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180064510`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006451a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180064510`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006451a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180064483`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180064483`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006445a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006445a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800644c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800644d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800644c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800644d6`

## pseudocode

```c
__int64 __fastcall CThemePackManager::_PackFilesWithUI(CThemePackManager *this)
{
  int Error; // ebx
  unsigned int i; // esi
  HANDLE EventW; // rcx
  __int64 v5; // rax
  HANDLE Thread; // rax
  __int64 j; // rsi
  void *v8; // rcx
  DWORD ExitCode; // [rsp+70h] [rbp+8h] BYREF

  *((_QWORD *)this + 274) = this;
  *((_QWORD *)this + 273) = CThemePackManager::_PackNotifyWithUI;
  Error = 0;
  ExitCode = 1;
  *((_QWORD *)this + 278) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  for ( i = 0; i < 4; ++i )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v5 = (int)i;
    if ( !EventW )
      Error = -2147467259;
    *((_QWORD *)this + v5 + 4) = EventW;
  }
  if ( Error >= 0 )
  {
    Thread = CreateThread(0, 0, CThemePackManager::_PackNotifyWithUI, this, 4u, (LPDWORD)this + 6);
    *((_QWORD *)this + 2) = Thread;
    if ( !Thread )
    {
      Error = -2147467259;
      goto LABEL_16;
    }
    if ( (int)CThemePackManager::_InitiatePack(this) >= 0 )
    {
      if ( GetExitCodeThread(*((HANDLE *)this + 2), &ExitCode) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
LABEL_15:
          CloseHandle(*((HANDLE *)this + 2));
LABEL_16:
          for ( j = 0; j != 4; ++j )
          {
            v8 = (void *)*((_QWORD *)this + j + 4);
            if ( v8 )
              CloseHandle(v8);
            *((_QWORD *)this + j + 4) = 0;
          }
          if ( Error >= 0 && ExitCode )
            Error = *((_DWORD *)this + 38) != 0 ? -2147023673 : -2147467259;
          goto LABEL_23;
        }
      }
      if ( !ExitCode || *((_DWORD *)this + 38) )
        goto LABEL_15;
    }
    Error = CThemePackManager::_ShowDialog(this, 5, 0);
    goto LABEL_15;
  }
LABEL_23:
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800643b8  push    rbx
0x1800643ba  push    rbp
0x1800643bb  push    rsi
0x1800643bc  push    rdi
0x1800643bd  push    r12
0x1800643bf  push    r14
0x1800643c1  sub     rsp, 38h
0x1800643c5  mov     [rcx+890h], rcx
0x1800643cc  lea     rax, ?_PackNotifyWithUI@CThemePackManager@@CAHI_J0PEAX@Z; CThemePackManager::_PackNotifyWithUI(uint,__int64,__int64,void *)
0x1800643d3  mov     [rcx+888h], rax
0x1800643da  mov     rdi, rcx
0x1800643dd  xor     ebx, ebx
0x1800643df  mov     [rsp+68h+ExitCode], 1
0x1800643e7  mov     [rcx+8B0h], rbx
0x1800643ee  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800643f2  call    cs:__imp_InitializeCriticalSection
0x1800643f8  lea     rcx, [rdi+70h]; lpCriticalSection
0x1800643fc  call    cs:__imp_InitializeCriticalSection
0x180064402  xor     esi, esi
0x180064404  mov     r12d, 80004005h
0x18006440a  xor     r9d, r9d; lpName
0x18006440d  xor     r8d, r8d; bInitialState
0x180064410  xor     edx, edx; bManualReset
0x180064412  xor     ecx, ecx; lpEventAttributes
0x180064414  call    cs:__imp_CreateEventW
0x18006441a  mov     rcx, rax
0x18006441d  movsxd  rax, esi
0x180064420  test    rcx, rcx
0x180064423  cmovz   ebx, r12d
0x180064427  inc     esi
0x180064429  mov     [rdi+rax*8+20h], rcx
0x18006442e  cmp     esi, 4
0x180064431  jb      short loc_18006440A
0x180064433  test    ebx, ebx
0x180064435  js      loc_18006450C
0x18006443b  lea     rax, [rdi+18h]
0x18006443f  mov     r9, rdi; lpParameter
0x180064442  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180064447  lea     r8, ?_PackNotifyWithUI@CThemePackManager@@CAKPEAX@Z; lpStartAddress
0x18006444e  xor     edx, edx; dwStackSize
0x180064450  mov     [rsp+68h+dwCreationFlags], 4; dwCreationFlags
0x180064458  xor     ecx, ecx; lpThreadAttributes
0x18006445a  call    cs:__imp_CreateThread
0x180064460  mov     [rdi+10h], rax
0x180064464  test    rax, rax
0x180064467  jnz     short loc_18006446E
0x180064469  mov     ebx, r12d
0x18006446c  jmp     short loc_1800644CA
0x18006446e  mov     rcx, rdi; this
0x180064471  call    ?_InitiatePack@CThemePackManager@@AEAAJXZ; CThemePackManager::_InitiatePack(void)
0x180064476  test    eax, eax
0x180064478  js      short loc_1800644AC
0x18006447a  mov     rcx, [rdi+10h]; hThread
0x18006447e  lea     rdx, [rsp+68h+ExitCode]; lpExitCode
0x180064483  call    cs:__imp_GetExitCodeThread
0x180064489  test    eax, eax
0x18006448b  jz      short loc_180064491
0x18006448d  xor     ebx, ebx
0x18006448f  jmp     short loc_18006449C
0x180064491  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180064496  mov     ebx, eax
0x180064498  test    eax, eax
0x18006449a  js      short loc_1800644C0
0x18006449c  cmp     [rsp+68h+ExitCode], 0
0x1800644a1  jz      short loc_1800644C0
0x1800644a3  cmp     dword ptr [rdi+98h], 0
0x1800644aa  jnz     short loc_1800644C0
0x1800644ac  xor     r9d, r9d
0x1800644af  xor     r8d, r8d
0x1800644b2  mov     rcx, rdi
0x1800644b5  lea     edx, [r9+5]
0x1800644b9  call    ?_ShowDialog@CThemePackManager@@CAJPEAV1@HW4THEMEPACK_FLAGS@@PEAH@Z; CThemePackManager::_ShowDialog(CThemePackManager *,int,THEMEPACK_FLAGS,int *)
0x1800644be  mov     ebx, eax
0x1800644c0  mov     rcx, [rdi+10h]; hObject
0x1800644c4  call    cs:__imp_CloseHandle
0x1800644ca  xor     esi, esi
0x1800644cc  mov     rcx, [rdi+rsi*8+20h]; hObject
0x1800644d1  test    rcx, rcx
0x1800644d4  jz      short loc_1800644DC
0x1800644d6  call    cs:__imp_CloseHandle
0x1800644dc  mov     qword ptr [rdi+rsi*8+20h], 0
0x1800644e5  inc     rsi
0x1800644e8  cmp     rsi, 4
0x1800644ec  jnz     short loc_1800644CC
0x1800644ee  test    ebx, ebx
0x1800644f0  js      short loc_18006450C
0x1800644f2  cmp     [rsp+68h+ExitCode], 0
0x1800644f7  jz      short loc_18006450C
0x1800644f9  mov     eax, [rdi+98h]
0x1800644ff  neg     eax
0x180064501  sbb     ebx, ebx
0x180064503  and     ebx, 6C4C2h
0x180064509  add     ebx, r12d
0x18006450c  lea     rcx, [rdi+48h]; lpCriticalSection
0x180064510  call    cs:__imp_DeleteCriticalSection
0x180064516  lea     rcx, [rdi+70h]; lpCriticalSection
0x18006451a  call    cs:__imp_DeleteCriticalSection
0x180064520  mov     eax, ebx
0x180064522  add     rsp, 38h
0x180064526  pop     r14
0x180064528  pop     r12
0x18006452a  pop     rdi
0x18006452b  pop     rsi
0x18006452c  pop     rbp
0x18006452d  pop     rbx
0x18006452e  retn
```
