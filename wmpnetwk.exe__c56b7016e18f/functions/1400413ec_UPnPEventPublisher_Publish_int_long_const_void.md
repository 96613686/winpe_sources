# UPnPEventPublisher::Publish(int,long * const,void *)

- ea: `0x1400413ec`
- end: `0x14004186b`
- name: `?Publish@UPnPEventPublisher@@QEAAJHQEAJPEAX@Z`
- size: `1151`
- prototype: `int(UPnPEventPublisher *__hidden this, int, int *const, void *)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x140058070`
- `0x140058774`
- `0x14005b184`
- `0x14005f7ac`

## callees

- `0x1400413ec`
- `0x140041874`
- `0x140046020`
- `0x140046358`
- `0x14004639c`
- `0x140065770`
- `0x1400657e8`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140041461`
- `KERNEL32!EnterCriticalSection` at `0x140041461`
- `KERNEL32!LeaveCriticalSection` at `0x14004182a`
- `KERNEL32!LeaveCriticalSection` at `0x14004182a`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400414a4`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400414a4`
- `KERNEL32!ChangeTimerQueueTimer` at `0x140041818`
- `KERNEL32!ChangeTimerQueueTimer` at `0x140041818`
- `KERNEL32!CreateTimerQueueTimer` at `0x140041769`
- `KERNEL32!CreateTimerQueueTimer` at `0x140041769`
- `KERNEL32!GetTickCount` at `0x1400414f2`
- `KERNEL32!GetTickCount` at `0x140041688`
- `KERNEL32!GetTickCount` at `0x140041730`
- `KERNEL32!GetTickCount` at `0x1400414f2`
- `KERNEL32!GetTickCount` at `0x140041688`
- `KERNEL32!GetTickCount` at `0x140041730`
- `KERNEL32!GetLastError` at `0x140041773`
- `KERNEL32!GetLastError` at `0x140041773`
- `ole32!CoUnmarshalInterface` at `0x140041647`
- `ole32!CoUnmarshalInterface` at `0x140041647`

## pseudocode

```c
__int64 __fastcall UPnPEventPublisher::Publish(UPnPEventPublisher *this, int a2, int *const a3, void *a4)
{
  _DWORD *v9; // r13
  unsigned int v10; // edx
  int v11; // edi
  TimerCallbackContext *v12; // rcx
  int v13; // ebp
  DWORD TickCount; // eax
  int v15; // r8d
  unsigned int v16; // r15d
  int v17; // edx
  int i; // ecx
  int v19; // r8d
  DWORD DueTime; // esi
  char *v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  DWORD v25; // eax
  int k; // r8d
  DWORD v27; // ecx
  void *v28; // rcx
  void *v29; // rdx
  TimerCallbackContext *v30; // rcx
  void **v31; // r14
  DWORD v32; // eax
  void *v33; // rdx
  _QWORD *v34; // r15
  DWORD v35; // r12d
  signed int LastError; // eax
  unsigned int v37; // edx
  unsigned int v38; // ecx
  int j; // ecx
  LPVOID ppv; // [rsp+40h] [rbp-58h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-50h]
  void **v42; // [rsp+A0h] [rbp+8h]

  if ( *((_DWORD *)this + 2) == 1 )
    return 2147943515LL;
  if ( !*((_DWORD *)this + 36) )
    return 0;
  if ( (unsigned int)a2 > 0x20 )
    return 2147942487LL;
  if ( !(unsigned int)IsWMC() || !(unsigned int)IsNetworkService() )
    return 2147549183LL;
  if ( *((_DWORD *)this + 2) == 1 )
    return 2147943515LL;
  v9 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 2) == 1 )
    goto LABEL_9;
  if ( a4 )
  {
    v12 = (TimerCallbackContext *)*((_QWORD *)this + 17);
    if ( v12 )
    {
      TimerCallbackContext::`scalar deleting destructor'(v12, v10);
      *((_QWORD *)this + 17) = 0;
    }
    if ( *((_QWORD *)this + 15) )
    {
      DeleteTimerQueueTimer(*((HANDLE *)this + 14), a4, 0);
      if ( a4 != *((void **)this + 15) )
        goto LABEL_68;
      *((_QWORD *)this + 15) = 0;
    }
  }
  if ( !*((_QWORD *)this + 2) )
    goto LABEL_68;
  v9 = operator new[](saturated_mul(a2 + 2, 4u));
  LOWORD(v42) = 0;
  v13 = 0;
  TickCount = GetTickCount();
  v15 = 0;
  v16 = TickCount;
  if ( a2 > 0 )
  {
    while ( 1 )
    {
      v17 = *((_DWORD *)this + 14);
      for ( i = 0; i < v17; ++i )
      {
        if ( *((_DWORD *)this + 4 * i + 6) == a3[v15] )
          break;
      }
      if ( i == v17 )
        break;
      if ( *((_BYTE *)this + 16 * i + 36) != 1
        || TickCount >= *((_DWORD *)this + 4 * i + 8) && TickCount <= ~*((_DWORD *)this + 4 * i + 7) )
      {
        *((_BYTE *)&v42 + i) = 1;
        v9[v13] = a3[v15];
        *((_WORD *)this + 8 * i + 18) = 0;
        goto LABEL_28;
      }
      *((_BYTE *)this + 16 * i + 37) = 1;
LABEL_29:
      if ( ++v15 >= a2 )
        goto LABEL_30;
    }
    v9[v13] = a3[v15];
LABEL_28:
    ++v13;
    goto LABEL_29;
  }
LABEL_30:
  v19 = 0;
  for ( DueTime = -1; v19 < *((_DWORD *)this + 14); ++v19 )
  {
    if ( *((_BYTE *)this + 16 * v19 + 37) )
    {
      v21 = (char *)this + 16 * v19;
      if ( v16 < *((_DWORD *)this + 4 * v19 + 8) || v16 > ~*((_DWORD *)v21 + 7) )
      {
        if ( DueTime > *((_DWORD *)v21 + 7) )
          DueTime = *((_DWORD *)v21 + 7);
      }
      else
      {
        v22 = *((_DWORD *)this + 4 * v19 + 6);
        v23 = v13++;
        *((_BYTE *)&v42 + v19) = 1;
        v9[v23] = v22;
        *((_WORD *)this + 8 * v19 + 18) = 0;
      }
    }
  }
  if ( *((_DWORD *)this + 2) != 1 )
  {
    v11 = 0;
    if ( v13 > 0 )
    {
      v24 = *((_QWORD *)this + 2);
      ppv = 0;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v24 + 40LL))(v24, 0, 0, 0);
      v11 = CoUnmarshalInterface(*((LPSTREAM *)this + 2), &IID_IUPnPEventSink, &ppv);
      if ( v11 < 0
        || (v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _DWORD *))(*(_QWORD *)ppv + 24LL))(
                    ppv,
                    (unsigned int)v13,
                    v9),
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv),
            v11 < 0) )
      {
        v38 = *((_DWORD *)this + 26);
        *((_DWORD *)this + 26) = v38 + 1;
        if ( v38 < 3 )
        {
          for ( j = 0; j < *((_DWORD *)this + 14); ++j )
          {
            if ( *((_BYTE *)&v42 + j) )
            {
              if ( DueTime > 0x64 )
                DueTime = 100;
              *((_WORD *)this + 8 * j + 18) = 257;
            }
          }
          v11 = 0;
          goto LABEL_47;
        }
      }
      else
      {
        v25 = GetTickCount();
        for ( k = 0; k < *((_DWORD *)this + 14); ++k )
        {
          if ( *((_BYTE *)&v42 + k) )
          {
            v27 = v25 + *((_DWORD *)this + 4 * k + 7);
            *((_WORD *)this + 8 * k + 18) = 1;
            *((_DWORD *)this + 4 * k + 8) = v27;
          }
        }
      }
      *((_DWORD *)this + 26) = 0;
    }
LABEL_47:
    if ( DueTime == -1 )
      goto LABEL_69;
    v28 = (void *)*((_QWORD *)this + 14);
    if ( v28 == (void *)-1LL )
      goto LABEL_69;
    v29 = (void *)*((_QWORD *)this + 15);
    if ( !v29 )
    {
      if ( *((_DWORD *)this + 2) != 1 )
      {
        v30 = (TimerCallbackContext *)*((_QWORD *)this + 17);
        if ( v30 )
        {
          TimerCallbackContext::`scalar deleting destructor'(v30, 0);
          *((_QWORD *)this + 17) = 0;
        }
        v42 = (void **)operator new(0x10u);
        v31 = v42;
        *v42 = this;
        v32 = GetTickCount();
        v33 = (void *)*((_QWORD *)this + 14);
        v34 = v31 + 1;
        *((_QWORD *)this + 17) = v31;
        v35 = v32;
        if ( CreateTimerQueueTimer(v31 + 1, v33, UPnPEventPublisher::TimerQueueCallback, v31, DueTime, 0, 0x28u) )
        {
          *((_QWORD *)this + 15) = *v34;
          *((_DWORD *)this + 32) = v35 + DueTime;
        }
        else
        {
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          *((_QWORD *)this + 17) = 0;
          *v34 = 0;
          *v31 = 0;
          TimerCallbackContext::`scalar deleting destructor'((TimerCallbackContext *)v31, v37);
        }
        goto LABEL_69;
      }
      goto LABEL_9;
    }
    if ( DueTime + v16 < *((_DWORD *)this + 32) && ChangeTimerQueueTimer(v28, v29, DueTime, 0) )
      goto LABEL_69;
LABEL_68:
    v11 = 0;
    goto LABEL_69;
  }
LABEL_9:
  v11 = -2147023781;
LABEL_69:
  LeaveCriticalSection(lpCriticalSection);
  if ( v9 )
    operator delete(v9);
  if ( v11 >= 0 )
    return 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400413ec  push    rbx
0x1400413ee  push    rbp
0x1400413ef  push    rsi
0x1400413f0  push    rdi
0x1400413f1  push    r12
0x1400413f3  push    r13
0x1400413f5  push    r14
0x1400413f7  push    r15
0x1400413f9  sub     rsp, 58h
0x1400413fd  cmp     dword ptr [rcx+8], 1
0x140041401  mov     rdi, r9
0x140041404  mov     r14, r8
0x140041407  mov     esi, edx
0x140041409  mov     rbx, rcx
0x14004140c  jz      loc_140041855
0x140041412  xor     r12d, r12d
0x140041415  cmp     [rcx+90h], r12d
0x14004141c  jnz     short loc_140041425
0x14004141e  xor     eax, eax
0x140041420  jmp     loc_14004185A
0x140041425  cmp     esi, 20h ; ' '
0x140041428  ja      loc_14004184E
0x14004142e  call    ?IsWMC@@YAHXZ; IsWMC(void)
0x140041433  test    eax, eax
0x140041435  jz      loc_140041847
0x14004143b  call    ?IsNetworkService@@YAHXZ; IsNetworkService(void)
0x140041440  test    eax, eax
0x140041442  jz      loc_140041847
0x140041448  cmp     dword ptr [rbx+8], 1
0x14004144c  jz      loc_140041855
0x140041452  lea     rax, [rbx+40h]
0x140041456  mov     r13, r12
0x140041459  mov     rcx, rax; lpCriticalSection
0x14004145c  mov     [rsp+98h+lpCriticalSection], rax
0x140041461  call    cs:__imp_EnterCriticalSection
0x140041467  cmp     dword ptr [rbx+8], 1
0x14004146b  jnz     short loc_140041477
0x14004146d  mov     edi, 8007045Bh
0x140041472  jmp     loc_140041825
0x140041477  test    rdi, rdi
0x14004147a  jz      short loc_1400414B8
0x14004147c  mov     rcx, [rbx+88h]; this
0x140041483  test    rcx, rcx
0x140041486  jz      short loc_140041494
0x140041488  call    ??_GTimerCallbackContext@@QEAAPEAXI@Z; TimerCallbackContext::`scalar deleting destructor'(uint)
0x14004148d  mov     [rbx+88h], r12
0x140041494  cmp     [rbx+78h], r12
0x140041498  jz      short loc_1400414B8
0x14004149a  mov     rcx, [rbx+70h]; TimerQueue
0x14004149e  xor     r8d, r8d; CompletionEvent
0x1400414a1  mov     rdx, rdi; Timer
0x1400414a4  call    cs:__imp_DeleteTimerQueueTimer
0x1400414aa  cmp     rdi, [rbx+78h]
0x1400414ae  jnz     loc_140041822
0x1400414b4  mov     [rbx+78h], r12
0x1400414b8  cmp     [rbx+10h], r12
0x1400414bc  jz      loc_140041822
0x1400414c2  lea     eax, [rsi+2]
0x1400414c5  movsxd  rcx, eax
0x1400414c8  mov     eax, 4
0x1400414cd  mul     rcx
0x1400414d0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400414d7  cmovb   rax, rcx
0x1400414db  mov     rcx, rax; unsigned __int64
0x1400414de  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400414e3  mov     r13, rax
0x1400414e6  mov     word ptr [rsp+98h+arg_0], r12w
0x1400414ef  mov     ebp, r12d
0x1400414f2  call    cs:__imp_GetTickCount
0x1400414f8  mov     r8d, r12d
0x1400414fb  mov     r15d, eax
0x1400414fe  test    esi, esi
0x140041500  jle     loc_14004159A
0x140041506  mov     edx, [rbx+38h]
0x140041509  mov     ecx, r12d
0x14004150c  test    edx, edx
0x14004150e  jle     short loc_14004152A
0x140041510  mov     eax, r8d
0x140041513  mov     r9d, [r14+rax*4]
0x140041517  movsxd  rax, ecx
0x14004151a  add     rax, rax
0x14004151d  cmp     [rbx+rax*8+18h], r9d
0x140041522  jz      short loc_14004152A
0x140041524  inc     ecx
0x140041526  cmp     ecx, edx
0x140041528  jl      short loc_140041517
0x14004152a  cmp     ecx, edx
0x14004152c  jnz     short loc_14004153F
0x14004152e  mov     eax, r8d
0x140041531  movsxd  rcx, ebp
0x140041534  mov     eax, [r14+rax*4]
0x140041538  mov     [r13+rcx*4+0], eax
0x14004153d  jmp     short loc_14004158C
0x14004153f  movsxd  r9, ecx
0x140041542  mov     rdx, r9
0x140041545  add     rdx, rdx
0x140041548  cmp     byte ptr [rbx+rdx*8+24h], 1
0x14004154d  jnz     short loc_14004156E
0x14004154f  lea     rax, [r9+2]
0x140041553  add     rax, rax
0x140041556  cmp     r15d, [rbx+rax*8]
0x14004155a  jb      short loc_140041567
0x14004155c  mov     eax, [rbx+rdx*8+1Ch]
0x140041560  not     eax
0x140041562  cmp     r15d, eax
0x140041565  jbe     short loc_14004156E
0x140041567  mov     byte ptr [rbx+rdx*8+25h], 1
0x14004156c  jmp     short loc_14004158E
0x14004156e  mov     eax, r8d
0x140041571  movsxd  rcx, ebp
0x140041574  mov     byte ptr [rsp+r9+98h+arg_0], 1
0x14004157d  mov     eax, [r14+rax*4]
0x140041581  mov     [r13+rcx*4+0], eax
0x140041586  mov     [rbx+rdx*8+24h], r12w
0x14004158c  inc     ebp
0x14004158e  inc     r8d
0x140041591  cmp     r8d, esi
0x140041594  jl      loc_140041506
0x14004159a  or      r14d, 0FFFFFFFFh
0x14004159e  mov     r8d, r12d
0x1400415a1  mov     esi, r14d
0x1400415a4  cmp     [rbx+38h], r12d
0x1400415a8  jle     short loc_140041604
0x1400415aa  movsxd  r9, r8d
0x1400415ad  mov     rdx, r9
0x1400415b0  add     rdx, rdx
0x1400415b3  cmp     [rbx+rdx*8+25h], r12b
0x1400415b8  jz      short loc_1400415FB
0x1400415ba  lea     rax, [r9+2]
0x1400415be  add     rax, rax
0x1400415c1  lea     rcx, [rbx+rdx*8]
0x1400415c5  cmp     r15d, [rbx+rax*8]
0x1400415c9  jb      short loc_1400415F4
0x1400415cb  mov     eax, [rcx+1Ch]
0x1400415ce  not     eax
0x1400415d0  cmp     r15d, eax
0x1400415d3  ja      short loc_1400415F4
0x1400415d5  mov     eax, [rbx+rdx*8+18h]
0x1400415d9  movsxd  rcx, ebp
0x1400415dc  inc     ebp
0x1400415de  mov     byte ptr [rsp+r9+98h+arg_0], 1
0x1400415e7  mov     [r13+rcx*4+0], eax
0x1400415ec  mov     [rbx+rdx*8+24h], r12w
0x1400415f2  jmp     short loc_1400415FB
0x1400415f4  cmp     esi, [rcx+1Ch]
0x1400415f7  cmova   esi, [rcx+1Ch]
0x1400415fb  inc     r8d
0x1400415fe  cmp     r8d, [rbx+38h]
0x140041602  jl      short loc_1400415AA
0x140041604  cmp     dword ptr [rbx+8], 1
0x140041608  jz      loc_14004146D
0x14004160e  mov     edi, r12d
0x140041611  test    ebp, ebp
0x140041613  jle     loc_1400416D2
0x140041619  mov     rcx, [rbx+10h]
0x14004161d  mov     rdx, r12
0x140041620  mov     [rsp+98h+ppv], r12
0x140041625  xor     r9d, r9d
0x140041628  xor     r8d, r8d
0x14004162b  mov     rax, [rcx]
0x14004162e  mov     rax, [rax+28h]
0x140041632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041637  mov     rcx, [rbx+10h]; pStm
0x14004163b  lea     r8, [rsp+98h+ppv]; ppv
0x140041640  lea     rdx, IID_IUPnPEventSink; riid
0x140041647  call    cs:__imp_CoUnmarshalInterface
0x14004164d  mov     edi, eax
0x14004164f  test    eax, eax
0x140041651  js      loc_1400417A5
0x140041657  mov     rcx, [rsp+98h+ppv]
0x14004165c  mov     r8, r13
0x14004165f  mov     edx, ebp
0x140041661  mov     rax, [rcx]
0x140041664  mov     rax, [rax+18h]
0x140041668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004166d  mov     rcx, [rsp+98h+ppv]
0x140041672  mov     edi, eax
0x140041674  mov     rax, [rcx]
0x140041677  mov     rax, [rax+10h]
0x14004167b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041680  test    edi, edi
0x140041682  js      loc_1400417A5
0x140041688  call    cs:__imp_GetTickCount
0x14004168e  mov     r8d, r12d
0x140041691  mov     r10d, eax
0x140041694  cmp     [rbx+38h], r12d
0x140041698  jle     short loc_1400416CE
0x14004169a  movsxd  r9, r8d
0x14004169d  cmp     byte ptr [rsp+r9+98h+arg_0], r12b
0x1400416a5  jz      short loc_1400416C5
0x1400416a7  mov     rdx, r9
0x1400416aa  lea     rax, [r9+2]
0x1400416ae  add     rdx, rdx
0x1400416b1  mov     ecx, [rbx+rdx*8+1Ch]
0x1400416b5  add     ecx, r10d
0x1400416b8  mov     word ptr [rbx+rdx*8+24h], 1
0x1400416bf  add     rax, rax
0x1400416c2  mov     [rbx+rax*8], ecx
0x1400416c5  inc     r8d
0x1400416c8  cmp     r8d, [rbx+38h]
0x1400416cc  jl      short loc_14004169A
0x1400416ce  mov     [rbx+68h], r12d
0x1400416d2  cmp     esi, r14d
0x1400416d5  jz      loc_140041825
0x1400416db  mov     rcx, [rbx+70h]; TimerQueue
0x1400416df  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400416e3  jz      loc_140041825
0x1400416e9  mov     rdx, [rbx+78h]; unsigned int
0x1400416ed  test    rdx, rdx
0x1400416f0  jnz     loc_140041806
0x1400416f6  cmp     dword ptr [rbx+8], 1
0x1400416fa  jz      loc_14004146D
0x140041700  mov     rcx, [rbx+88h]; this
0x140041707  test    rcx, rcx
0x14004170a  jz      short loc_140041718
0x14004170c  call    ??_GTimerCallbackContext@@QEAAPEAXI@Z; TimerCallbackContext::`scalar deleting destructor'(uint)
0x140041711  mov     [rbx+88h], r12
0x140041718  mov     ecx, 10h; Size
0x14004171d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140041722  mov     [rsp+98h+arg_0], rax
0x14004172a  mov     r14, rax
0x14004172d  mov     [rax], rbx
0x140041730  call    cs:__imp_GetTickCount
0x140041736  mov     rdx, [rbx+70h]; TimerQueue
0x14004173a  lea     r15, [r14+8]
0x14004173e  mov     [rsp+98h+Flags], 28h ; '('; Flags
0x140041746  lea     r8, ?TimerQueueCallback@UPnPEventPublisher@@SAXPEAXE@Z; Callback
0x14004174d  mov     rcx, r15; phNewTimer
0x140041750  mov     [rsp+98h+Period], 0; Period
0x140041758  mov     r9, r14; Parameter
0x14004175b  mov     [rbx+88h], r14
0x140041762  mov     r12d, eax
0x140041765  mov     [rsp+98h+DueTime], esi; DueTime
0x140041769  call    cs:__imp_CreateTimerQueueTimer
0x14004176f  test    eax, eax
0x140041771  jnz     short loc_1400417F0
0x140041773  call    cs:__imp_GetLastError
0x140041779  xor     r12d, r12d
0x14004177c  mov     edi, eax
0x14004177e  test    eax, eax
0x140041780  jle     short loc_14004178B
0x140041782  movzx   edi, ax
0x140041785  or      edi, 80070000h
0x14004178b  mov     [rbx+88h], r12
0x140041792  mov     rcx, r14; this
0x140041795  mov     [r15], r12
0x140041798  mov     [r14], r12
0x14004179b  call    ??_GTimerCallbackContext@@QEAAPEAXI@Z; TimerCallbackContext::`scalar deleting destructor'(uint)
0x1400417a0  jmp     loc_140041825
0x1400417a5  mov     ecx, [rbx+68h]
0x1400417a8  lea     eax, [rcx+1]
0x1400417ab  mov     [rbx+68h], eax
0x1400417ae  cmp     ecx, 3
0x1400417b1  jnb     loc_1400416CE
0x1400417b7  mov     ecx, r12d
0x1400417ba  cmp     [rbx+38h], r12d
0x1400417be  jle     short loc_1400417E8
0x1400417c0  mov     edx, 64h ; 'd'
0x1400417c5  movsxd  rax, ecx
0x1400417c8  cmp     byte ptr [rsp+rax+98h+arg_0], r12b
0x1400417d0  jz      short loc_1400417E1
0x1400417d2  add     rax, rax
0x1400417d5  cmp     esi, edx
0x1400417d7  cmova   esi, edx
0x1400417da  mov     word ptr [rbx+rax*8+24h], 101h
0x1400417e1  inc     ecx
0x1400417e3  cmp     ecx, [rbx+38h]
0x1400417e6  jl      short loc_1400417C5
0x1400417e8  mov     edi, r12d
0x1400417eb  jmp     loc_1400416D2
0x1400417f0  mov     rax, [r15]
0x1400417f3  mov     [rbx+78h], rax
0x1400417f7  lea     eax, [r12+rsi]
0x1400417fb  mov     [rbx+80h], eax
0x140041801  xor     r12d, r12d
0x140041804  jmp     short loc_140041825
0x140041806  lea     eax, [rsi+r15]
0x14004180a  cmp     eax, [rbx+80h]
0x140041810  jnb     short loc_140041822
0x140041812  xor     r9d, r9d; Period
0x140041815  mov     r8d, esi; DueTime
0x140041818  call    cs:__imp_ChangeTimerQueueTimer
0x14004181e  test    eax, eax
0x140041820  jnz     short loc_140041825
0x140041822  mov     edi, r12d
0x140041825  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x14004182a  call    cs:__imp_LeaveCriticalSection
0x140041830  test    r13, r13
0x140041833  jz      short loc_14004183D
0x140041835  mov     rcx, r13; Block
0x140041838  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14004183d  test    edi, edi
0x14004183f  cmovns  edi, r12d
0x140041843  mov     eax, edi
0x140041845  jmp     short loc_14004185A
0x140041847  mov     eax, 8000FFFFh
0x14004184c  jmp     short loc_14004185A
0x14004184e  mov     eax, 80070057h
0x140041853  jmp     short loc_14004185A
0x140041855  mov     eax, 8007045Bh
  ... truncated ...
```
