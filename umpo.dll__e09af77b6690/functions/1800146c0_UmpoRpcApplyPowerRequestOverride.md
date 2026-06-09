# UmpoRpcApplyPowerRequestOverride

- ea: `0x1800146c0`
- end: `0x180014765`
- name: `UmpoRpcApplyPowerRequestOverride`
- size: `165`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000c534`
- `0x18000f3dc`
- `0x1800146c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001471e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001471e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001470b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001470b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800146f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800146f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001473e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001473e`
- `RPCRT4!RpcRevertToSelf` at `0x180014749`
- `RPCRT4!RpcRevertToSelf` at `0x180014749`
- `RPCRT4!RpcImpersonateClient` at `0x1800146e6`
- `RPCRT4!RpcImpersonateClient` at `0x1800146e6`

## pseudocode

```c
__int64 UmpoRpcApplyPowerRequestOverride()
{
  char v0; // di
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  v0 = 0;
  TokenHandle = 0;
  if ( UmpoIsClientLocal() )
  {
    LastError = RpcImpersonateClient(0);
    if ( !LastError )
    {
      v0 = 1;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x2000000u, 0, &TokenHandle) )
      {
        UmpoApplyAllPowerRequestOverride(0, 1);
        LastError = 0;
      }
      else
      {
        TokenHandle = 0;
        LastError = GetLastError();
      }
    }
  }
  else
  {
    LastError = 5;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v0 && RpcRevertToSelf() )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return LastError;
}

```

## disassembly

```asm
0x1800146c0  mov     [rsp+arg_0], rbx
0x1800146c5  push    rdi
0x1800146c6  sub     rsp, 20h
0x1800146ca  xor     dil, dil
0x1800146cd  mov     [rsp+28h+TokenHandle], 0
0x1800146d6  call    UmpoIsClientLocal
0x1800146db  test    eax, eax
0x1800146dd  jnz     short loc_1800146E4
0x1800146df  lea     ebx, [rax+5]
0x1800146e2  jmp     short loc_180014734
0x1800146e4  xor     ecx, ecx; BindingHandle
0x1800146e6  call    cs:__imp_RpcImpersonateClient
0x1800146ec  mov     ebx, eax
0x1800146ee  test    eax, eax
0x1800146f0  jnz     short loc_180014734
0x1800146f2  mov     dil, 1
0x1800146f5  call    cs:__imp_GetCurrentThread
0x1800146fb  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180014700  xor     r8d, r8d; OpenAsSelf
0x180014703  mov     rcx, rax; ThreadHandle
0x180014706  mov     edx, 2000000h; DesiredAccess
0x18001470b  call    cs:__imp_OpenThreadToken
0x180014711  test    eax, eax
0x180014713  jnz     short loc_180014728
0x180014715  mov     [rsp+28h+TokenHandle], 0
0x18001471e  call    cs:__imp_GetLastError
0x180014724  mov     ebx, eax
0x180014726  jmp     short loc_180014734
0x180014728  mov     dl, dil
0x18001472b  xor     ecx, ecx
0x18001472d  call    UmpoApplyAllPowerRequestOverride
0x180014732  xor     ebx, ebx
0x180014734  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180014739  test    rcx, rcx
0x18001473c  jz      short loc_180014744
0x18001473e  call    cs:__imp_CloseHandle
0x180014744  test    dil, dil
0x180014747  jz      short loc_180014758
0x180014749  call    cs:__imp_RpcRevertToSelf
0x18001474f  test    eax, eax
0x180014751  jz      short loc_180014758
0x180014753  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014758  mov     eax, ebx
0x18001475a  mov     rbx, [rsp+28h+arg_0]
0x18001475f  add     rsp, 20h
0x180014763  pop     rdi
0x180014764  retn
```
