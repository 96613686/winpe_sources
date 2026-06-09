# SeclStopRpcServer

- ea: `0x18000427c`
- end: `0x1800042cd`
- name: `SeclStopRpcServer`
- size: `81`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fd0`
- `0x1800042d4`

## callees

- `0x18000427c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004289`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004289`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800042bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800042bf`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800042a4`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800042a4`

## pseudocode

```c
__int64 SeclStopRpcServer()
{
  unsigned int v0; // ebx

  EnterCriticalSection(&csForProcessCount);
  if ( !*(&AuthenticationPackage + 2) )
    goto LABEL_4;
  v0 = RpcServerUnregisterIf(qword_180006400, 0, 0);
  if ( !v0 )
  {
    *(&AuthenticationPackage + 2) = 0;
LABEL_4:
    v0 = 0;
  }
  LeaveCriticalSection(&csForProcessCount);
  return v0;
}

```

## disassembly

```asm
0x18000427c  push    rbx
0x18000427e  sub     rsp, 20h
0x180004282  lea     rcx, csForProcessCount; lpCriticalSection
0x180004289  call    cs:__imp_EnterCriticalSection
0x18000428f  cmp     dword ptr cs:AuthenticationPackage+8, 0
0x180004296  jz      short loc_1800042B6
0x180004298  xor     r8d, r8d; WaitForCallsToComplete
0x18000429b  lea     rcx, qword_180006400; IfSpec
0x1800042a2  xor     edx, edx; MgrTypeUuid
0x1800042a4  call    cs:__imp_RpcServerUnregisterIf
0x1800042aa  mov     ebx, eax
0x1800042ac  test    eax, eax
0x1800042ae  jnz     short loc_1800042B8
0x1800042b0  mov     dword ptr cs:AuthenticationPackage+8, eax
0x1800042b6  xor     ebx, ebx
0x1800042b8  lea     rcx, csForProcessCount; lpCriticalSection
0x1800042bf  call    cs:__imp_LeaveCriticalSection
0x1800042c5  mov     eax, ebx
0x1800042c7  add     rsp, 20h
0x1800042cb  pop     rbx
0x1800042cc  retn
```
