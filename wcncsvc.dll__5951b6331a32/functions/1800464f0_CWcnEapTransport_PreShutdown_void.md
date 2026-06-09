# CWcnEapTransport::PreShutdown(void)

- ea: `0x1800464f0`
- end: `0x180046590`
- name: `?PreShutdown@CWcnEapTransport@@UEAAXXZ`
- size: `160`
- prototype: `void __fastcall(CWcnEapTransport *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800464f0`
- `0x1800504cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004650e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004650e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046531`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046531`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004655e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004655e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046547`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046547`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180046555`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180046555`

## pseudocode

```c
void __fastcall CWcnEapTransport::PreShutdown(CWcnEapTransport *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _TP_TIMER *v3; // rdi
  void *v4; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  if ( *((_QWORD *)this + 22) )
  {
    v3 = (struct _TP_TIMER *)*((_QWORD *)this + 22);
    *((_QWORD *)this + 22) = 0;
  }
  LeaveCriticalSection(v1);
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
  }
  v4 = (void *)*((_QWORD *)this + 21);
  if ( v4 )
  {
    WcnWlanCloseHandle(v4);
    *((_QWORD *)this + 21) = 0;
  }
}

```

## disassembly

```asm
0x1800464f0  mov     [rsp+arg_0], rbx
0x1800464f5  mov     [rsp+arg_8], rsi
0x1800464fa  push    rdi
0x1800464fb  sub     rsp, 20h
0x1800464ff  lea     rsi, [rcx+0B8h]
0x180046506  mov     rbx, rcx
0x180046509  mov     rcx, rsi; lpCriticalSection
0x18004650c  xor     edi, edi
0x18004650e  call    cs:__imp_EnterCriticalSection
0x180046514  mov     rax, [rbx+0B0h]
0x18004651b  test    rax, rax
0x18004651e  jz      short loc_18004652E
0x180046520  mov     rdi, rax
0x180046523  mov     qword ptr [rbx+0B0h], 0
0x18004652e  mov     rcx, rsi; lpCriticalSection
0x180046531  call    cs:__imp_LeaveCriticalSection
0x180046537  test    rdi, rdi
0x18004653a  jz      short loc_180046564
0x18004653c  xor     r9d, r9d; msWindowLength
0x18004653f  xor     r8d, r8d; msPeriod
0x180046542  xor     edx, edx; pftDueTime
0x180046544  mov     rcx, rdi; pti
0x180046547  call    cs:__imp_SetThreadpoolTimer
0x18004654d  mov     edx, 1; fCancelPendingCallbacks
0x180046552  mov     rcx, rdi; pti
0x180046555  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004655b  mov     rcx, rdi; pti
0x18004655e  call    cs:__imp_CloseThreadpoolTimer
0x180046564  mov     rcx, [rbx+0A8h]; hClientHandle
0x18004656b  test    rcx, rcx
0x18004656e  jz      short loc_180046580
0x180046570  call    ?WcnWlanCloseHandle@@YAJPEAX@Z; WcnWlanCloseHandle(void *)
0x180046575  mov     qword ptr [rbx+0A8h], 0
0x180046580  mov     rbx, [rsp+28h+arg_0]
0x180046585  mov     rsi, [rsp+28h+arg_8]
0x18004658a  add     rsp, 20h
0x18004658e  pop     rdi
0x18004658f  retn
```
