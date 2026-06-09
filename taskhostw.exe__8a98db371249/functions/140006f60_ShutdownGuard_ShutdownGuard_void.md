# ShutdownGuard::~ShutdownGuard(void)

- ea: `0x140006f60`
- end: `0x140006f94`
- name: `??1ShutdownGuard@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(ShutdownGuard *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009910`
- `0x140009a40`
- `0x14000ac90`
- `0x14000acd0`
- `0x14000b03e`
- `0x14000b064`

## callees

- `0x140006f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006f89`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006f89`

## pseudocode

```c
void __fastcall ShutdownGuard::~ShutdownGuard(ShutdownGuard *this)
{
  _InterlockedExchange((volatile __int32 *)this, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&ShutdownMgr::s_sync, 0xFFFFFFFF) == 1 )
    SetEvent((HANDLE)_InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1));
}

```

## disassembly

```asm
0x140006f60  sub     rsp, 28h
0x140006f64  xor     eax, eax
0x140006f66  xchg    eax, [rcx]
0x140006f68  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140006f6c  mov     eax, ecx
0x140006f6e  lock xadd cs:?s_sync@ShutdownMgr@@0USync@1@A, eax; ShutdownMgr::Sync ShutdownMgr::s_sync
0x140006f76  add     eax, ecx
0x140006f78  jnz     short loc_140006F8F
0x140006f7a  mov     rax, rcx
0x140006f7d  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rcx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x140006f86  mov     rcx, rax; hEvent
0x140006f89  call    cs:__imp_SetEvent
0x140006f8f  add     rsp, 28h
0x140006f93  retn
```
