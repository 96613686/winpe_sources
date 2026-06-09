# RemoteSubscription::Disconnect(void)

- ea: `0x180049d30`
- end: `0x180049dee`
- name: `?Disconnect@RemoteSubscription@@QEAAXXZ`
- size: `190`
- prototype: `void __fastcall(RemoteSubscription *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180049c5c`
- `0x180093560`

## callees

- `0x180048930`
- `0x180049d30`
- `0x180049df4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180049d9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180049d9d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049d86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049d86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049d4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049da7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049d4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049da7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049d76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049dbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049dd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049d76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049dbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049dd5`

## pseudocode

```c
void __fastcall RemoteSubscription::Disconnect(RemoteSubscription *this)
{
  RTL_SRWLOCK *v2; // rbx
  struct _TP_WAIT *v3; // rcx

  v2 = (RTL_SRWLOCK *)((char *)this + 32);
  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  if ( *((_BYTE *)this + 414) )
  {
    ReleaseSRWLockExclusive(v2);
  }
  else
  {
    RemoteSubscription::InternalNotifySubscriptionTermination(this, 1818);
    *((_BYTE *)this + 414) = 1;
    ReleaseSRWLockExclusive(v2);
    WaitForSingleObject(*((HANDLE *)this + 17), 0xFFFFFFFF);
    v3 = (struct _TP_WAIT *)*((_QWORD *)this + 27);
    if ( v3 )
      SetThreadpoolWait(v3, 0, 0);
    AcquireSRWLockExclusive((PSRWLOCK)this + 6);
    ChannelManager::UnregisterSubscription(*((PSRWLOCK *)this + 3), this);
    ReleaseSRWLockExclusive((PSRWLOCK)this + 6);
    _InterlockedDecrement(&g_ActiveSubscriptionCount);
  }
}

```

## disassembly

```asm
0x180049d30  mov     [rsp+arg_0], rcx
0x180049d35  push    rbx
0x180049d36  push    rsi
0x180049d37  push    rdi
0x180049d38  sub     rsp, 40h
0x180049d3c  mov     rdi, rcx
0x180049d3f  lea     rbx, [rcx+20h]
0x180049d43  mov     [rsp+58h+arg_8], rbx
0x180049d48  mov     rcx, rbx; SRWLock
0x180049d4b  call    cs:__imp_AcquireSRWLockExclusive
0x180049d51  lea     rsi, [rdi+19Eh]
0x180049d58  mov     [rsp+58h+arg_10], rsi
0x180049d5d  cmp     byte ptr [rsi], 0
0x180049d60  jnz     short loc_180049DD2
0x180049d62  mov     edx, 71Ah
0x180049d67  mov     rcx, rdi
0x180049d6a  call    ?InternalNotifySubscriptionTermination@RemoteSubscription@@AEAAXKAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z; RemoteSubscription::InternalNotifySubscriptionTermination(ulong,utl::unique_lock<utl::mutex> &)
0x180049d6f  nop
0x180049d70  mov     byte ptr [rsi], 1
0x180049d73  mov     rcx, rbx; SRWLock
0x180049d76  call    cs:__imp_ReleaseSRWLockExclusive
0x180049d7c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180049d7f  mov     rcx, [rdi+88h]; hHandle
0x180049d86  call    cs:__imp_WaitForSingleObject
0x180049d8c  mov     rcx, [rdi+0D8h]; pwa
0x180049d93  test    rcx, rcx
0x180049d96  jz      short loc_180049DA3
0x180049d98  xor     r8d, r8d; pftTimeout
0x180049d9b  xor     edx, edx; h
0x180049d9d  call    cs:__imp_SetThreadpoolWait
0x180049da3  lea     rcx, [rdi+30h]; SRWLock
0x180049da7  call    cs:__imp_AcquireSRWLockExclusive
0x180049dad  mov     rdx, rdi; struct RemoteSubscription *
0x180049db0  mov     rcx, [rdi+18h]; SRWLock
0x180049db4  call    ?UnregisterSubscription@ChannelManager@@QEAAXPEAVRemoteSubscription@@@Z; ChannelManager::UnregisterSubscription(RemoteSubscription *)
0x180049db9  lea     rcx, [rdi+30h]; SRWLock
0x180049dbd  call    cs:__imp_ReleaseSRWLockExclusive
0x180049dc3  lock dec cs:?g_ActiveSubscriptionCount@@3JA; long g_ActiveSubscriptionCount
0x180049dca  add     rsp, 40h
0x180049dce  pop     rdi
0x180049dcf  pop     rsi
0x180049dd0  pop     rbx
0x180049dd1  retn
0x180049dd2  mov     rcx, rbx; SRWLock
0x180049dd5  call    cs:__imp_ReleaseSRWLockExclusive
0x180049ddb  jmp     short loc_180049DCA
0x180049ddd  mov     rdi, [rsp+58h+arg_0]
0x180049de2  mov     rbx, [rsp+58h+arg_8]
0x180049de7  mov     rsi, [rsp+58h+arg_10]
0x180049dec  jmp     short loc_180049D70
```
