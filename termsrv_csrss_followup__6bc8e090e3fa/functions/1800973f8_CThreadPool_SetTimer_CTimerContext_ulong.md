# CThreadPool::SetTimer(CTimerContext *,ulong)

- ea: `0x1800973f8`
- end: `0x1800974e1`
- name: `?SetTimer@CThreadPool@@QEAAJPEAVCTimerContext@@K@Z`
- size: `233`
- prototype: `int(CThreadPool *__hidden this, struct CTimerContext *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18004e310`

## callees

- `0x180096f74`
- `0x1800970e4`
- `0x1800973f8`
- `0x1800976e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097452`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800974b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800974b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009743d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009743d`

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
0x1800973f8  mov     [rsp+arg_8], rbx
0x1800973fd  push    rdi
0x1800973fe  sub     rsp, 20h
0x180097402  mov     rbx, rdx
0x180097405  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x18009740e  mov     r8, rcx
0x180097411  cmp     dword ptr [rcx+18h], 0
0x180097415  jz      loc_1800974CE
0x18009741b  lea     rdi, [rcx+8]
0x18009741f  mov     rcx, rdi; this
0x180097422  call    ?BeginDispatch@CSafeRundown@@QEAAHXZ; CSafeRundown::BeginDispatch(void)
0x180097427  test    eax, eax
0x180097429  jz      loc_1800974CE
0x18009742f  add     r8, 30h ; '0'; pcbe
0x180097433  lea     rcx, ?staticTimerCallback@CThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18009743a  mov     rdx, rbx; pv
0x18009743d  call    cs:__imp_CreateThreadpoolTimer
0x180097444  nop     dword ptr [rax+rax+00h]
0x180097449  mov     [rbx+28h], rax
0x18009744d  test    rax, rax
0x180097450  jnz     short loc_18009749F
0x180097452  call    cs:__imp_GetLastError
0x180097459  nop     dword ptr [rax+rax+00h]
0x18009745e  mov     ebx, eax
0x180097460  test    eax, eax
0x180097462  jle     short loc_18009746D
0x180097464  movzx   ebx, ax
0x180097467  or      ebx, 80070000h
0x18009746d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097474  lea     rax, WPP_GLOBAL_Control
0x18009747b  cmp     rcx, rax
0x18009747e  jz      short loc_1800974C4
0x180097480  test    byte ptr [rcx+1Ch], 1
0x180097484  jz      short loc_1800974C4
0x180097486  cmp     byte ptr [rcx+19h], 2
0x18009748a  jb      short loc_1800974C4
0x18009748c  mov     rcx, [rcx+10h]
0x180097490  mov     edx, 22h ; '"'
0x180097495  mov     r9d, ebx
0x180097498  call    WPP_SF_d
0x18009749d  jmp     short loc_1800974C4
0x18009749f  xor     ebx, ebx
0x1800974a1  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFDC3CBA00h
0x1800974aa  xor     r9d, r9d; msWindowLength
0x1800974ad  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800974b2  xor     r8d, r8d; msPeriod
0x1800974b5  mov     rcx, rax; pti
0x1800974b8  call    cs:__imp_SetThreadpoolTimer
0x1800974bf  nop     dword ptr [rax+rax+00h]
0x1800974c4  mov     rcx, rdi; this
0x1800974c7  call    ?EndDispatch@CSafeRundown@@QEAAXXZ; CSafeRundown::EndDispatch(void)
0x1800974cc  jmp     short loc_1800974D3
0x1800974ce  mov     ebx, 80004005h
0x1800974d3  mov     eax, ebx
0x1800974d5  mov     rbx, [rsp+28h+arg_8]
0x1800974da  add     rsp, 20h
0x1800974de  pop     rdi
0x1800974df  retn
```
