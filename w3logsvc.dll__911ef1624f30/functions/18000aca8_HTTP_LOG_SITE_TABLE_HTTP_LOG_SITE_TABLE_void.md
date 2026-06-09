# HTTP_LOG_SITE_TABLE::~HTTP_LOG_SITE_TABLE(void)

- ea: `0x18000aca8`
- end: `0x18000ada6`
- name: `??1HTTP_LOG_SITE_TABLE@@UEAA@XZ`
- size: `254`
- prototype: `void __fastcall(HTTP_LOG_SITE_TABLE *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000adac`
- `0x18000b010`
- `0x18000f11d`

## callees

- `0x180001048`
- `0x18000aca8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000acf4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000acf4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ace7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ace7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000acd8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000acd8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ad78`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ad82`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ad78`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ad82`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000ad6e`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000ad6e`

## pseudocode

```c
void __fastcall HTTP_LOG_SITE_TABLE::~HTTP_LOG_SITE_TABLE(HTTP_LOG_SITE_TABLE *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rdi

  *(_QWORD *)this = &HTTP_LOG_SITE_TABLE::`vftable';
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 138);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 138), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 138));
    *((_QWORD *)this + 138) = 0;
  }
  v3 = *((_QWORD *)this + 134);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 134) = 0;
  }
  v4 = *((_QWORD *)this + 135);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 672), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
    *((_QWORD *)this + 135) = 0;
  }
  v5 = *((_QWORD *)this + 136);
  if ( v5 )
  {
    MULTISZ::~MULTISZ((MULTISZ *)(v5 + 160));
    STRU::~STRU((STRU *)(v5 + 104));
    STRU::~STRU((STRU *)(v5 + 48));
    operator delete((void *)v5);
    *((_QWORD *)this + 136) = 0;
  }
}

```

## disassembly

```asm
0x18000aca8  mov     [rsp+arg_8], rbx
0x18000acad  push    rdi
0x18000acae  sub     rsp, 20h
0x18000acb2  mov     rbx, rcx
0x18000acb5  lea     rax, ??_7HTTP_LOG_SITE_TABLE@@6B@; const HTTP_LOG_SITE_TABLE::`vftable'
0x18000acbc  mov     [rcx], rax
0x18000acbf  mov     rcx, [rcx+450h]; pti
0x18000acc6  mov     edi, 1
0x18000accb  test    rcx, rcx
0x18000acce  jz      short loc_18000AD05
0x18000acd0  xor     r9d, r9d; msWindowLength
0x18000acd3  xor     r8d, r8d; msPeriod
0x18000acd6  xor     edx, edx; pftDueTime
0x18000acd8  call    cs:__imp_SetThreadpoolTimer
0x18000acde  mov     edx, edi; fCancelPendingCallbacks
0x18000ace0  mov     rcx, [rbx+450h]; pti
0x18000ace7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000aced  mov     rcx, [rbx+450h]; pti
0x18000acf4  call    cs:__imp_CloseThreadpoolTimer
0x18000acfa  mov     qword ptr [rbx+450h], 0
0x18000ad05  mov     rcx, [rbx+430h]
0x18000ad0c  test    rcx, rcx
0x18000ad0f  jz      short loc_18000AD28
0x18000ad11  mov     rax, [rcx]
0x18000ad14  mov     rax, [rax+10h]
0x18000ad18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad1d  mov     qword ptr [rbx+430h], 0
0x18000ad28  mov     rcx, [rbx+438h]
0x18000ad2f  test    rcx, rcx
0x18000ad32  jz      short loc_18000AD5B
0x18000ad34  or      eax, 0FFFFFFFFh
0x18000ad37  lock xadd [rcx+2A0h], eax
0x18000ad3f  cmp     eax, edi
0x18000ad41  jnz     short loc_18000AD50
0x18000ad43  mov     rax, [rcx]
0x18000ad46  mov     edx, edi
0x18000ad48  mov     rax, [rax]
0x18000ad4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad50  mov     qword ptr [rbx+438h], 0
0x18000ad5b  mov     rdi, [rbx+440h]
0x18000ad62  test    rdi, rdi
0x18000ad65  jz      short loc_18000AD9B
0x18000ad67  lea     rcx, [rdi+0A0h]
0x18000ad6e  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000ad74  lea     rcx, [rdi+68h]
0x18000ad78  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ad7e  lea     rcx, [rdi+30h]
0x18000ad82  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ad88  mov     rcx, rdi; Block
0x18000ad8b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ad90  mov     qword ptr [rbx+440h], 0
0x18000ad9b  mov     rbx, [rsp+28h+arg_8]
0x18000ada0  add     rsp, 20h
0x18000ada4  pop     rdi
0x18000ada5  retn
```
