# CThreadPool::SetTimer(CTimerContext *,ulong)

- ea: `0x180093474`
- end: `0x18009354a`
- name: `?SetTimer@CThreadPool@@QEAAJPEAVCTimerContext@@K@Z`
- size: `214`
- prototype: `int(CThreadPool *__hidden this, struct CTimerContext *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18004bce0`

## callees

- `0x1800930d4`
- `0x1800931a0`
- `0x180093474`
- `0x180093714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800934c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800934c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180093528`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180093528`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800934b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800934b9`

## pseudocode

```c
__int64 __fastcall CThreadPool::SetTimer(CThreadPool *this, struct CTimerContext *a2)
{
  CSafeRundown *v3; // rdi
  __int64 v4; // r8
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  __int64 v7; // r8
  unsigned int v8; // ebx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  pftDueTime = 0;
  if ( *((_DWORD *)this + 6)
    && (v3 = (CThreadPool *)((char *)this + 8),
        (unsigned int)CSafeRundown::BeginDispatch((CThreadPool *)((char *)this + 8))) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(CThreadPool::staticTimerCallback, a2, (PTP_CALLBACK_ENVIRON)(v4 + 48));
    *((_QWORD *)a2 + 5) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v8 = 0;
      pftDueTime = (struct _FILETIME)-600000000LL;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v7, v8);
      }
    }
    CSafeRundown::EndDispatch(v3);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v8;
}

```

## disassembly

```asm
0x180093474  mov     [rsp+arg_8], rbx
0x180093479  push    rdi
0x18009347a  sub     rsp, 20h
0x18009347e  mov     rbx, rdx
0x180093481  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x18009348a  mov     r8, rcx
0x18009348d  cmp     dword ptr [rcx+18h], 0
0x180093491  jz      loc_180093538
0x180093497  lea     rdi, [rcx+8]
0x18009349b  mov     rcx, rdi; this
0x18009349e  call    ?BeginDispatch@CSafeRundown@@QEAAHXZ; CSafeRundown::BeginDispatch(void)
0x1800934a3  test    eax, eax
0x1800934a5  jz      loc_180093538
0x1800934ab  add     r8, 30h ; '0'; pcbe
0x1800934af  lea     rcx, ?staticTimerCallback@CThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800934b6  mov     rdx, rbx; pv
0x1800934b9  call    cs:__imp_CreateThreadpoolTimer
0x1800934bf  mov     [rbx+28h], rax
0x1800934c3  test    rax, rax
0x1800934c6  jnz     short loc_18009350F
0x1800934c8  call    cs:__imp_GetLastError
0x1800934ce  mov     ebx, eax
0x1800934d0  test    eax, eax
0x1800934d2  jle     short loc_1800934DD
0x1800934d4  movzx   ebx, ax
0x1800934d7  or      ebx, 80070000h
0x1800934dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800934e4  lea     rax, WPP_GLOBAL_Control
0x1800934eb  cmp     rcx, rax
0x1800934ee  jz      short loc_18009352E
0x1800934f0  test    byte ptr [rcx+1Ch], 1
0x1800934f4  jz      short loc_18009352E
0x1800934f6  cmp     byte ptr [rcx+19h], 2
0x1800934fa  jb      short loc_18009352E
0x1800934fc  mov     rcx, [rcx+10h]
0x180093500  mov     edx, 22h ; '"'
0x180093505  mov     r9d, ebx
0x180093508  call    WPP_SF_d
0x18009350d  jmp     short loc_18009352E
0x18009350f  xor     ebx, ebx
0x180093511  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFDC3CBA00h
0x18009351a  xor     r9d, r9d; msWindowLength
0x18009351d  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180093522  xor     r8d, r8d; msPeriod
0x180093525  mov     rcx, rax; pti
0x180093528  call    cs:__imp_SetThreadpoolTimer
0x18009352e  mov     rcx, rdi; this
0x180093531  call    ?EndDispatch@CSafeRundown@@QEAAXXZ; CSafeRundown::EndDispatch(void)
0x180093536  jmp     short loc_18009353D
0x180093538  mov     ebx, 80004005h
0x18009353d  mov     eax, ebx
0x18009353f  mov     rbx, [rsp+28h+arg_8]
0x180093544  add     rsp, 20h
0x180093548  pop     rdi
0x180093549  retn
```
