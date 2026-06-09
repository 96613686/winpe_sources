# LOG_SVC_ADMIN::InitializePipeClientHashTable(void)

- ea: `0x18000c1b4`
- end: `0x18000c39e`
- name: `?InitializePipeClientHashTable@LOG_SVC_ADMIN@@AEAAJXZ`
- size: `490`
- prototype: `__int64 __fastcall(char *pv)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bc64`

## callees

- `0x180001008`
- `0x180009a4c`
- `0x18000c1b4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c34c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c34c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c2ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c2f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c2ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c2f8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c25d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c2c3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c25d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c2c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c275`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c2d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c275`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c2d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c37a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c37a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c33a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c33a`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::InitializePipeClientHashTable(char *pv)
{
  int v2; // ebx
  __int64 v3; // r14
  __int64 v4; // rbx
  _QWORD *v5; // rdi
  HANDLE EventW; // rax
  HANDLE v7; // rax
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v12; // [rsp+48h] [rbp+10h]

  pftDueTime = 0;
  v2 = STBUFF::Resize((STBUFF *)(pv + 1408), 0x308u);
  if ( v2 >= 0 )
  {
    v3 = *((_QWORD *)pv + 177);
    v4 = 0;
    do
    {
      v12 = operator new(0x60u);
      v5 = v12;
      if ( !v12 )
        return (unsigned int)-2147024882;
      *v12 = &STTABLE_BUCKET::`vftable';
      *((_DWORD *)v5 + 6) = 0;
      v5[11] = 0;
      v5[11] = 0;
      v5[2] = v5 + 1;
      v5[1] = v5 + 1;
      if ( !*((_DWORD *)v5 + 6) )
      {
        *(_QWORD *)((char *)v5 + 28) = 0;
        if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)v5 + 1, 0x64u) )
          goto LABEL_14;
        EventW = CreateEventW(0, 0, 0, 0);
        v5[10] = EventW;
        if ( !EventW )
        {
          DeleteCriticalSection((LPCRITICAL_SECTION)v5 + 1);
LABEL_14:
          v2 = -2147467259;
          (*(void (__fastcall **)(_QWORD *, __int64))*v5)(v5, 1);
          return (unsigned int)v2;
        }
        *((_DWORD *)v5 + 6) = 1;
      }
      *(_QWORD *)(v3 + 8 * v4) = v5;
      v4 = (unsigned int)(v4 + 1);
      ++*((_DWORD *)pv + 376);
    }
    while ( (unsigned int)v4 < 0x61 );
    if ( !*((_DWORD *)pv + 378) )
    {
      *(_QWORD *)(pv + 1516) = 0;
      if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(pv + 1528), 0x64u) )
      {
        v7 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)pv + 196) = v7;
        if ( v7 )
          *((_DWORD *)pv + 378) = 1;
        else
          DeleteCriticalSection((LPCRITICAL_SECTION)(pv + 1528));
      }
    }
    *((_QWORD *)pv + 197) = 0;
    ThreadpoolTimer = CreateThreadpoolTimer(LOG_SVC_ADMIN::PipeFlushTimerCallback, pv, 0);
    *((_QWORD *)pv + 234) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      pftDueTime = (struct _FILETIME)-300000000LL;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000c1b4  mov     [rsp+arg_10], rbx
0x18000c1b9  mov     [rsp+arg_18], rbp
0x18000c1be  push    rsi
0x18000c1bf  push    rdi
0x18000c1c0  push    r14
0x18000c1c2  sub     rsp, 20h
0x18000c1c6  mov     rsi, rcx
0x18000c1c9  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0
0x18000c1d2  add     rcx, 580h; this
0x18000c1d9  mov     edx, 308h; unsigned int
0x18000c1de  call    ?Resize@STBUFF@@QEAAJK@Z; STBUFF::Resize(ulong)
0x18000c1e3  mov     ebx, eax
0x18000c1e5  test    eax, eax
0x18000c1e7  js      loc_18000C389
0x18000c1ed  mov     r14, [rsi+588h]
0x18000c1f4  xor     ebx, ebx
0x18000c1f6  mov     ecx, 60h ; '`'; Size
0x18000c1fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c200  mov     [rsp+38h+arg_8], rax
0x18000c205  mov     rdi, rax
0x18000c208  test    rax, rax
0x18000c20b  jz      loc_18000C384
0x18000c211  lea     rax, ??_7STTABLE_BUCKET@@6B@; const STTABLE_BUCKET::`vftable'
0x18000c218  mov     [rdi], rax
0x18000c21b  mov     dword ptr [rdi+18h], 0
0x18000c222  mov     qword ptr [rdi+58h], 0
0x18000c22a  test    rdi, rdi
0x18000c22d  jz      loc_18000C384
0x18000c233  lea     rax, [rdi+8]
0x18000c237  mov     qword ptr [rdi+58h], 0
0x18000c23f  mov     [rdi+10h], rax
0x18000c243  mov     [rax], rax
0x18000c246  cmp     dword ptr [rdi+18h], 0
0x18000c24a  jnz     short loc_18000C28B
0x18000c24c  mov     edx, 64h ; 'd'; dwSpinCount
0x18000c251  mov     qword ptr [rdi+1Ch], 0
0x18000c259  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000c25d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000c263  test    eax, eax
0x18000c265  jz      loc_18000C2FE
0x18000c26b  xor     r9d, r9d; lpName
0x18000c26e  xor     r8d, r8d; bInitialState
0x18000c271  xor     edx, edx; bManualReset
0x18000c273  xor     ecx, ecx; lpEventAttributes
0x18000c275  call    cs:__imp_CreateEventW
0x18000c27b  mov     [rdi+50h], rax
0x18000c27f  test    rax, rax
0x18000c282  jz      short loc_18000C2F4
0x18000c284  mov     dword ptr [rdi+18h], 1
0x18000c28b  mov     [r14+rbx*8], rdi
0x18000c28f  inc     ebx
0x18000c291  inc     dword ptr [rsi+5E0h]
0x18000c297  cmp     ebx, 61h ; 'a'
0x18000c29a  jb      loc_18000C1F6
0x18000c2a0  cmp     dword ptr [rsi+5E8h], 0
0x18000c2a7  jnz     short loc_18000C322
0x18000c2a9  lea     rbx, [rsi+5F8h]
0x18000c2b0  mov     qword ptr [rsi+5ECh], 0
0x18000c2bb  mov     rcx, rbx; lpCriticalSection
0x18000c2be  mov     edx, 64h ; 'd'; dwSpinCount
0x18000c2c3  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000c2c9  test    eax, eax
0x18000c2cb  jz      short loc_18000C322
0x18000c2cd  xor     r9d, r9d; lpName
0x18000c2d0  xor     r8d, r8d; bInitialState
0x18000c2d3  xor     edx, edx; bManualReset
0x18000c2d5  xor     ecx, ecx; lpEventAttributes
0x18000c2d7  call    cs:__imp_CreateEventW
0x18000c2dd  mov     [rsi+620h], rax
0x18000c2e4  test    rax, rax
0x18000c2e7  jnz     short loc_18000C318
0x18000c2e9  mov     rcx, rbx; lpCriticalSection
0x18000c2ec  call    cs:__imp_DeleteCriticalSection
0x18000c2f2  jmp     short loc_18000C322
0x18000c2f4  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000c2f8  call    cs:__imp_DeleteCriticalSection
0x18000c2fe  mov     rax, [rdi]
0x18000c301  mov     edx, 1
0x18000c306  mov     rcx, rdi
0x18000c309  mov     ebx, 80004005h
0x18000c30e  mov     rax, [rax]
0x18000c311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c316  jmp     short loc_18000C389
0x18000c318  mov     dword ptr [rsi+5E8h], 1
0x18000c322  xor     r8d, r8d; pcbe
0x18000c325  mov     qword ptr [rsi+628h], 0
0x18000c330  mov     rdx, rsi; pv
0x18000c333  lea     rcx, ?PipeFlushTimerCallback@LOG_SVC_ADMIN@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c33a  call    cs:__imp_CreateThreadpoolTimer
0x18000c340  mov     [rsi+750h], rax
0x18000c347  test    rax, rax
0x18000c34a  jnz     short loc_18000C363
0x18000c34c  call    cs:__imp_GetLastError
0x18000c352  mov     ebx, eax
0x18000c354  test    eax, eax
0x18000c356  jle     short loc_18000C389
0x18000c358  movzx   ebx, ax
0x18000c35b  or      ebx, 80070000h
0x18000c361  jmp     short loc_18000C389
0x18000c363  xor     r9d, r9d; msWindowLength
0x18000c366  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x18000c36f  xor     r8d, r8d; msPeriod
0x18000c372  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000c377  mov     rcx, rax; pti
0x18000c37a  call    cs:__imp_SetThreadpoolTimer
0x18000c380  xor     ebx, ebx
0x18000c382  jmp     short loc_18000C389
0x18000c384  mov     ebx, 8007000Eh
0x18000c389  mov     rbp, [rsp+38h+arg_18]
0x18000c38e  mov     eax, ebx
0x18000c390  mov     rbx, [rsp+38h+arg_10]
0x18000c395  add     rsp, 20h
0x18000c399  pop     r14
0x18000c39b  pop     rdi
0x18000c39c  pop     rsi
0x18000c39d  retn
```
