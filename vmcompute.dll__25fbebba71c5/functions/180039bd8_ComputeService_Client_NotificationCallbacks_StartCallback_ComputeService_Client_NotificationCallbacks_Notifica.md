# ComputeService::Client::NotificationCallbacks::StartCallback(ComputeService::Client::NotificationCallbacks::NotificationContext *)

- ea: `0x180039bd8`
- end: `0x180039c68`
- name: `?StartCallback@NotificationCallbacks@Client@ComputeService@@AEAA_NPEAUNotificationContext@123@@Z`
- size: `144`
- prototype: `bool __fastcall(ComputeService::Client::NotificationCallbacks *__hidden this, struct ComputeService::Client::NotificationCallbacks::NotificationContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003941c`
- `0x180039d40`

## callees

- `0x180039bd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039bf1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039bf1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039c48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039c48`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180039c16`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180039c16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039c2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039c2e`

## pseudocode

```c
char __fastcall ComputeService::Client::NotificationCallbacks::StartCallback(
        ComputeService::Client::NotificationCallbacks *this,
        struct ComputeService::Client::NotificationCallbacks::NotificationContext *a2)
{
  RTL_SRWLOCK *v2; // rbx
  char v4; // si

  v2 = (RTL_SRWLOCK *)((char *)a2 + 72);
  AcquireSRWLockExclusive((PSRWLOCK)a2 + 9);
  v4 = 0;
  while ( *((_DWORD *)a2 + 16) )
  {
    if ( *((_BYTE *)a2 + 68) )
      goto LABEL_7;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)a2 + 10, v2, 0xFFFFFFFF, 0);
  }
  if ( !*((_BYTE *)a2 + 68) )
  {
    *((_DWORD *)a2 + 16) = GetCurrentThreadId();
    v4 = 1;
  }
LABEL_7:
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return v4;
}

```

## disassembly

```asm
0x180039bd8  mov     [rsp+arg_0], rbx
0x180039bdd  mov     [rsp+arg_10], rsi
0x180039be2  push    rdi
0x180039be3  sub     rsp, 20h
0x180039be7  lea     rbx, [rdx+48h]
0x180039beb  mov     rdi, rdx
0x180039bee  mov     rcx, rbx; SRWLock
0x180039bf1  call    cs:__imp_AcquireSRWLockExclusive
0x180039bf8  nop     dword ptr [rax+rax+00h]
0x180039bfd  xor     sil, sil
0x180039c00  jmp     short loc_180039C22
0x180039c02  cmp     [rdi+44h], sil
0x180039c06  jnz     short loc_180039C40
0x180039c08  lea     rcx, [rdi+50h]; ConditionVariable
0x180039c0c  xor     r9d, r9d; Flags
0x180039c0f  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180039c13  mov     rdx, rbx; SRWLock
0x180039c16  call    cs:__imp_SleepConditionVariableSRW
0x180039c1d  nop     dword ptr [rax+rax+00h]
0x180039c22  cmp     dword ptr [rdi+40h], 0
0x180039c26  jnz     short loc_180039C02
0x180039c28  cmp     [rdi+44h], sil
0x180039c2c  jnz     short loc_180039C40
0x180039c2e  call    cs:__imp_GetCurrentThreadId
0x180039c35  nop     dword ptr [rax+rax+00h]
0x180039c3a  mov     [rdi+40h], eax
0x180039c3d  mov     sil, 1
0x180039c40  test    rbx, rbx
0x180039c43  jz      short loc_180039C54
0x180039c45  mov     rcx, rbx; SRWLock
0x180039c48  call    cs:__imp_ReleaseSRWLockExclusive
0x180039c4f  nop     dword ptr [rax+rax+00h]
0x180039c54  mov     rbx, [rsp+28h+arg_0]
0x180039c59  mov     al, sil
0x180039c5c  mov     rsi, [rsp+28h+arg_10]
0x180039c61  add     rsp, 20h
0x180039c65  pop     rdi
0x180039c66  retn
```
