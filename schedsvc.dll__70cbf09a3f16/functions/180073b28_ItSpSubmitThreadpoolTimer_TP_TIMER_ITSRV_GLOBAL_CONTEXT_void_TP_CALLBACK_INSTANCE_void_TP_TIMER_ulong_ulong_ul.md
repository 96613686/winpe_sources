# ItSpSubmitThreadpoolTimer(_TP_TIMER * *,_ITSRV_GLOBAL_CONTEXT *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),ulong,ulong,ulong)

- ea: `0x180073b28`
- end: `0x180073bca`
- name: `?ItSpSubmitThreadpoolTimer@@YAKPEAPEAU_TP_TIMER@@PEAU_ITSRV_GLOBAL_CONTEXT@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@ZKKK@Z`
- size: `162`
- prototype: `unsigned int(struct _TP_TIMER **, struct _ITSRV_GLOBAL_CONTEXT *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *), unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003d520`

## callees

- `0x180073b28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b7f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180073b51`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180073b51`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073b79`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073bb1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073b79`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073bb1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073ba8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073ba8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180073b68`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180073b68`

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
0x180073b28  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r8
0x180073b2d  push    rbx
0x180073b2e  push    rbp
0x180073b2f  push    rsi
0x180073b30  push    rdi
0x180073b31  sub     rsp, 28h
0x180073b35  lea     rdi, [rdx+138h]
0x180073b3c  mov     ebp, r9d
0x180073b3f  mov     rsi, rcx
0x180073b42  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0
0x180073b4b  mov     rcx, rdi
0x180073b4e  mov     rbx, rdx
0x180073b51  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180073b57  lea     r8, [rbx+0E8h]; pcbe
0x180073b5e  mov     rdx, rbx; pv
0x180073b61  lea     rcx, ?ItSpIdleCancellationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180073b68  call    cs:__imp_CreateThreadpoolTimer
0x180073b6e  mov     rbx, rax
0x180073b71  test    rax, rax
0x180073b74  jnz     short loc_180073B87
0x180073b76  mov     rcx, rdi
0x180073b79  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180073b7f  call    cs:__imp_GetLastError
0x180073b85  jmp     short loc_180073BC1
0x180073b87  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x180073b8e  xor     r9d, r9d; msWindowLength
0x180073b91  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180073b96  mov     [rsp+48h+pftDueTime.dwLowDateTime], eax
0x180073b9a  xor     r8d, r8d; msPeriod
0x180073b9d  shr     rax, 20h
0x180073ba1  mov     rcx, rbx; pti
0x180073ba4  mov     [rsp+48h+pftDueTime.dwHighDateTime], eax
0x180073ba8  call    cs:__imp_SetThreadpoolTimer
0x180073bae  mov     rcx, rdi
0x180073bb1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180073bb7  test    rsi, rsi
0x180073bba  jz      short loc_180073BBF
0x180073bbc  mov     [rsi], rbx
0x180073bbf  xor     eax, eax
0x180073bc1  add     rsp, 28h
0x180073bc5  pop     rdi
0x180073bc6  pop     rsi
0x180073bc7  pop     rbp
0x180073bc8  pop     rbx
0x180073bc9  retn
```
