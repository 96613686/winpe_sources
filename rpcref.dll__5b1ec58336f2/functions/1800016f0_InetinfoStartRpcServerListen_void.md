# InetinfoStartRpcServerListen(void)

- ea: `0x1800016f0`
- end: `0x180001741`
- name: `?InetinfoStartRpcServerListen@@YAKXZ`
- size: `81`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800016f0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800016ff`
- `KERNEL32!EnterCriticalSection` at `0x1800016ff`
- `KERNEL32!LeaveCriticalSection` at `0x180001733`
- `KERNEL32!LeaveCriticalSection` at `0x180001733`
- `RPCRT4!RpcServerListen` at `0x180001724`
- `RPCRT4!RpcServerListen` at `0x180001724`

## pseudocode

```c
__int64 InetinfoStartRpcServerListen(void)
{
  unsigned int v0; // ebx

  v0 = 0;
  EnterCriticalSection(&csCritRef);
  if ( !cRefs++ )
    v0 = RpcServerListen(1u, 0x4D2u, 1u);
  LeaveCriticalSection(&csCritRef);
  return v0;
}

```

## disassembly

```asm
0x1800016f0  push    rbx
0x1800016f2  sub     rsp, 20h
0x1800016f6  lea     rcx, ?csCritRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800016fd  xor     ebx, ebx
0x1800016ff  call    cs:__imp_EnterCriticalSection
0x180001705  mov     eax, cs:?cRefs@@3KA; ulong cRefs
0x18000170b  lea     ecx, [rbx+1]; MinimumCallThreads
0x18000170e  mov     edx, eax
0x180001710  add     eax, ecx
0x180001712  mov     cs:?cRefs@@3KA, eax; ulong cRefs
0x180001718  test    edx, edx
0x18000171a  jnz     short loc_18000172C
0x18000171c  mov     r8d, ecx; DontWait
0x18000171f  mov     edx, 4D2h; MaxCalls
0x180001724  call    cs:__imp_RpcServerListen
0x18000172a  mov     ebx, eax
0x18000172c  lea     rcx, ?csCritRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001733  call    cs:__imp_LeaveCriticalSection
0x180001739  mov     eax, ebx
0x18000173b  add     rsp, 20h
0x18000173f  pop     rbx
0x180001740  retn
```
