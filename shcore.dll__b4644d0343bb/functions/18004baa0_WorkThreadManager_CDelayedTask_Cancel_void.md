# WorkThreadManager::CDelayedTask::Cancel(void)

- ea: `0x18004baa0`
- end: `0x18004bafc`
- name: `?Cancel@CDelayedTask@WorkThreadManager@@UEAAXXZ`
- size: `92`
- prototype: `void __fastcall(WorkThreadManager::CDelayedTask *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001e800`
- `0x18004baa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bad0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bad0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004bae2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004bae2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004baf4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004baf4`

## pseudocode

```c
void __fastcall WorkThreadManager::CDelayedTask::Cancel(WorkThreadManager::CDelayedTask *this)
{
  struct _TP_TIMER *v2; // rbx
  int v3; // edi

  v2 = (struct _TP_TIMER *)_InterlockedExchange64((volatile __int64 *)this + 3, 0);
  if ( v2 )
  {
    v3 = *((_DWORD *)this + 12);
    if ( v3 != GetCurrentThreadId() )
      WaitForThreadpoolTimerCallbacks(v2, 1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 40);
    CloseThreadpoolTimer(v2);
  }
}

```

## disassembly

```asm
0x18004baa0  mov     [rsp+arg_0], rbx
0x18004baa5  mov     [rsp+arg_8], rsi
0x18004baaa  push    rdi
0x18004baab  sub     rsp, 20h
0x18004baaf  xor     ebx, ebx
0x18004bab1  mov     rsi, rcx
0x18004bab4  xchg    rbx, [rcx+18h]
0x18004bab8  test    rbx, rbx
0x18004babb  jnz     short loc_18004BACD
0x18004babd  mov     rbx, [rsp+28h+arg_0]
0x18004bac2  mov     rsi, [rsp+28h+arg_8]
0x18004bac7  add     rsp, 20h
0x18004bacb  pop     rdi
0x18004bacc  retn
0x18004bacd  mov     edi, [rcx+30h]
0x18004bad0  call    cs:__imp_GetCurrentThreadId
0x18004bad6  cmp     edi, eax
0x18004bad8  jz      short loc_18004BAE8
0x18004bada  mov     edx, 1; fCancelPendingCallbacks
0x18004badf  mov     rcx, rbx; pti
0x18004bae2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004bae8  lea     rcx, [rsi+28h]
0x18004baec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004baf1  mov     rcx, rbx; pti
0x18004baf4  call    cs:__imp_CloseThreadpoolTimer
0x18004bafa  jmp     short loc_18004BABD
```
