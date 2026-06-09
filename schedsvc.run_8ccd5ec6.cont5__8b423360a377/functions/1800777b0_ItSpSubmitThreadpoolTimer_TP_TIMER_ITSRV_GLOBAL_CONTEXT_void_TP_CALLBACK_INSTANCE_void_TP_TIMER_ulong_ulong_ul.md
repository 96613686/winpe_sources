# ItSpSubmitThreadpoolTimer(_TP_TIMER * *,_ITSRV_GLOBAL_CONTEXT *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),ulong,ulong,ulong)

- ea: `0x1800777b0`
- end: `0x180077877`
- name: `?ItSpSubmitThreadpoolTimer@@YAKPEAPEAU_TP_TIMER@@PEAU_ITSRV_GLOBAL_CONTEXT@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@ZKKK@Z`
- size: `199`
- prototype: `unsigned int(struct _TP_TIMER **, struct _ITSRV_GLOBAL_CONTEXT *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *), unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003ee60`

## callees

- `0x1800777b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077819`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800777d9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800777d9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007780d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180077857`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007780d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180077857`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180077848`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180077848`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800777f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800777f6`

## pseudocode

```c
DWORD __fastcall ItSpSubmitThreadpoolTimer(
        struct _TP_TIMER **a1,
        struct _ITSRV_GLOBAL_CONTEXT *a2,
        void (*a3)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *),
        unsigned int a4)
{
  char *v4; // rdi
  __int64 v5; // rbp
  struct _TP_TIMER *ThreadpoolTimer; // rbx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+18h] BYREF

  v4 = (char *)a2 + 312;
  v5 = a4;
  pftDueTime = 0;
  RtlAcquireSRWLockExclusive((char *)a2 + 312);
  ThreadpoolTimer = CreateThreadpoolTimer(ItSpIdleCancellationCallback, a2, (PTP_CALLBACK_ENVIRON)((char *)a2 + 232));
  if ( ThreadpoolTimer )
  {
    pftDueTime = (struct _FILETIME)(-10000 * v5);
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
    RtlReleaseSRWLockExclusive(v4);
    if ( a1 )
      *a1 = ThreadpoolTimer;
    return 0;
  }
  else
  {
    RtlReleaseSRWLockExclusive(v4);
    return GetLastError();
  }
}

```

## disassembly

```asm
0x1800777b0  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r8
0x1800777b5  push    rbx
0x1800777b6  push    rbp
0x1800777b7  push    rsi
0x1800777b8  push    rdi
0x1800777b9  sub     rsp, 28h
0x1800777bd  lea     rdi, [rdx+138h]
0x1800777c4  mov     ebp, r9d
0x1800777c7  mov     rsi, rcx
0x1800777ca  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0
0x1800777d3  mov     rcx, rdi
0x1800777d6  mov     rbx, rdx
0x1800777d9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800777e0  nop     dword ptr [rax+rax+00h]
0x1800777e5  lea     r8, [rbx+0E8h]; pcbe
0x1800777ec  mov     rdx, rbx; pv
0x1800777ef  lea     rcx, ?ItSpIdleCancellationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800777f6  call    cs:__imp_CreateThreadpoolTimer
0x1800777fd  nop     dword ptr [rax+rax+00h]
0x180077802  mov     rbx, rax
0x180077805  test    rax, rax
0x180077808  jnz     short loc_180077827
0x18007780a  mov     rcx, rdi
0x18007780d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180077814  nop     dword ptr [rax+rax+00h]
0x180077819  call    cs:__imp_GetLastError
0x180077820  nop     dword ptr [rax+rax+00h]
0x180077825  jmp     short loc_18007786D
0x180077827  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x18007782e  xor     r9d, r9d; msWindowLength
0x180077831  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180077836  mov     [rsp+48h+pftDueTime.dwLowDateTime], eax
0x18007783a  xor     r8d, r8d; msPeriod
0x18007783d  shr     rax, 20h
0x180077841  mov     rcx, rbx; pti
0x180077844  mov     [rsp+48h+pftDueTime.dwHighDateTime], eax
0x180077848  call    cs:__imp_SetThreadpoolTimer
0x18007784f  nop     dword ptr [rax+rax+00h]
0x180077854  mov     rcx, rdi
0x180077857  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18007785e  nop     dword ptr [rax+rax+00h]
0x180077863  test    rsi, rsi
0x180077866  jz      short loc_18007786B
0x180077868  mov     [rsi], rbx
0x18007786b  xor     eax, eax
0x18007786d  add     rsp, 28h
0x180077871  pop     rdi
0x180077872  pop     rsi
0x180077873  pop     rbp
0x180077874  pop     rbx
0x180077875  retn
```
