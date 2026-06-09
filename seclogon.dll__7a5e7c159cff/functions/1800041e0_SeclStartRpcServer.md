# SeclStartRpcServer

- ea: `0x1800041e0`
- end: `0x180004276`
- name: `SeclStartRpcServer`
- size: `150`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002fd0`
- `0x180003150`

## callees

- `0x1800041e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800041ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800041ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004268`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004268`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180004249`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180004249`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180004211`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180004211`

## pseudocode

```c
__int64 SeclStartRpcServer()
{
  RPC_STATUS v0; // eax
  unsigned int v1; // ebx

  EnterCriticalSection(&csForProcessCount);
  if ( *(&AuthenticationPackage + 2) )
    goto LABEL_7;
  v0 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"SECLOGON", 0);
  v1 = 0;
  if ( v0 != 1740 )
    v1 = v0;
  if ( !v1 )
  {
    v1 = RpcServerRegisterIfEx(qword_180006400, 0, 0, 9u, 0x4D2u, (RPC_IF_CALLBACK_FN *)SeclSecurityCallback);
    if ( !v1 )
    {
      *(&AuthenticationPackage + 2) = 1;
LABEL_7:
      v1 = 0;
    }
  }
  LeaveCriticalSection(&csForProcessCount);
  return v1;
}

```

## disassembly

```asm
0x1800041e0  push    rbx
0x1800041e2  sub     rsp, 30h
0x1800041e6  lea     rcx, csForProcessCount; lpCriticalSection
0x1800041ed  call    cs:__imp_EnterCriticalSection
0x1800041f3  cmp     dword ptr cs:AuthenticationPackage+8, 0
0x1800041fa  jnz     short loc_18000425F
0x1800041fc  xor     r9d, r9d; SecurityDescriptor
0x1800041ff  lea     r8, Endpoint; "SECLOGON"
0x180004206  lea     rcx, Protseq; "ncalrpc"
0x18000420d  lea     edx, [r9+0Ah]; MaxCalls
0x180004211  call    cs:__imp_RpcServerUseProtseqEpW
0x180004217  xor     ebx, ebx
0x180004219  cmp     eax, 6CCh
0x18000421e  cmovnz  ebx, eax
0x180004221  test    ebx, ebx
0x180004223  jnz     short loc_180004261
0x180004225  lea     rax, SeclSecurityCallback
0x18000422c  xor     r8d, r8d; MgrEpv
0x18000422f  mov     [rsp+38h+IfCallback], rax; IfCallback
0x180004234  lea     r9d, [rbx+9]; Flags
0x180004238  xor     edx, edx; MgrTypeUuid
0x18000423a  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x180004242  lea     rcx, qword_180006400; IfSpec
0x180004249  call    cs:__imp_RpcServerRegisterIfEx
0x18000424f  mov     ebx, eax
0x180004251  test    eax, eax
0x180004253  jnz     short loc_180004261
0x180004255  mov     dword ptr cs:AuthenticationPackage+8, 1
0x18000425f  xor     ebx, ebx
0x180004261  lea     rcx, csForProcessCount; lpCriticalSection
0x180004268  call    cs:__imp_LeaveCriticalSection
0x18000426e  mov     eax, ebx
0x180004270  add     rsp, 30h
0x180004274  pop     rbx
0x180004275  retn
```
