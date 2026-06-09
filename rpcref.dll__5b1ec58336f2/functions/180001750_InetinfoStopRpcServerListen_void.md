# InetinfoStopRpcServerListen(void)

- ea: `0x180001750`
- end: `0x180001799`
- name: `?InetinfoStopRpcServerListen@@YAKXZ`
- size: `73`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001750`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000175f`
- `KERNEL32!EnterCriticalSection` at `0x18000175f`
- `KERNEL32!LeaveCriticalSection` at `0x18000178b`
- `KERNEL32!LeaveCriticalSection` at `0x18000178b`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x18000177c`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x18000177c`
- `RPCRT4!RpcMgmtStopServerListening` at `0x180001770`
- `RPCRT4!RpcMgmtStopServerListening` at `0x180001770`

## pseudocode

```c
__int64 InetinfoStopRpcServerListen(void)
{
  unsigned int v0; // ebx

  v0 = 0;
  EnterCriticalSection(&csCritRef);
  if ( !--cRefs )
  {
    v0 = RpcMgmtStopServerListening(0);
    if ( !v0 )
      v0 = RpcMgmtWaitServerListen();
  }
  LeaveCriticalSection(&csCritRef);
  return v0;
}

```

## disassembly

```asm
0x180001750  push    rbx
0x180001752  sub     rsp, 20h
0x180001756  lea     rcx, ?csCritRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000175d  xor     ebx, ebx
0x18000175f  call    cs:__imp_EnterCriticalSection
0x180001765  add     cs:?cRefs@@3KA, 0FFFFFFFFh; ulong cRefs
0x18000176c  jnz     short loc_180001784
0x18000176e  xor     ecx, ecx; Binding
0x180001770  call    cs:__imp_RpcMgmtStopServerListening
0x180001776  mov     ebx, eax
0x180001778  test    eax, eax
0x18000177a  jnz     short loc_180001784
0x18000177c  call    cs:__imp_RpcMgmtWaitServerListen
0x180001782  mov     ebx, eax
0x180001784  lea     rcx, ?csCritRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000178b  call    cs:__imp_LeaveCriticalSection
0x180001791  mov     eax, ebx
0x180001793  add     rsp, 20h
0x180001797  pop     rbx
0x180001798  retn
```
