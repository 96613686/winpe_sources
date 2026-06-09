# LRPC_BASE_CCALL::Receive(_RPC_MESSAGE *,uint)

- ea: `0x1800be980`
- end: `0x1800bea5c`
- name: `?Receive@LRPC_BASE_CCALL@@UEAAJPEAU_RPC_MESSAGE@@I@Z`
- size: `220`
- prototype: `__int64 __fastcall(LRPC_BASE_CCALL *__hidden this, struct _RPC_MESSAGE *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800162e0`
- `0x1800177ac`
- `0x180026500`
- `0x1800295d8`
- `0x180066718`
- `0x1800a72e0`
- `0x1800be980`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800be9c2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800be9c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800be9b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800be9b4`

## pseudocode

```c
__int64 __fastcall LRPC_BASE_CCALL::Receive(void **this, struct _RPC_MESSAGE *a2)
{
  __int64 v3; // r10
  __int64 v4; // rbx
  DWORD CurrentProcessId; // edi
  unsigned int CommandLineW; // eax
  bool v7; // zf

  if ( !(unsigned int)ShouldSkipLogging(2u) && (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
  {
    v4 = *(_QWORD *)(v3 + 40) + 4LL;
    CurrentProcessId = GetCurrentProcessId();
    CommandLineW = (unsigned int)GetCommandLineW();
    McTemplateU0zdzj_EtwEventWriteTransfer(
      (unsigned int)L"ncalrpc",
      (unsigned int)RPC_EVENTLOG_SYNC_PIPE_USE_ERR,
      CommandLineW,
      CurrentProcessId,
      (__int64)L"ncalrpc",
      v4);
  }
  I_RpcBCacheFree(this[63]);
  v7 = this[64] == 0;
  this[63] = 0;
  if ( !v7 )
    LRPC_BASE_CCALL::FreeAlpcSectionAndView((LRPC_BASE_CCALL *)this, 1);
  REFERENCED_OBJECT::RemoveReference((REFERENCED_OBJECT *)this);
  RpcpErrorAddRecord(2u, 1764, 0x618u, 0, 0);
  return 1764;
}

```

## disassembly

```asm
0x1800be980  mov     [rsp+arg_0], rbx
0x1800be985  mov     [rsp+arg_8], rsi
0x1800be98a  push    rdi
0x1800be98b  sub     rsp, 30h
0x1800be98f  mov     rsi, rcx
0x1800be992  mov     r10, rdx
0x1800be995  mov     ecx, 2; unsigned int
0x1800be99a  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x1800be99f  test    eax, eax
0x1800be9a1  jnz     short loc_1800BE9F1
0x1800be9a3  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x1800be9aa  jz      short loc_1800BE9F1
0x1800be9ac  mov     rbx, [r10+28h]
0x1800be9b0  add     rbx, 4
0x1800be9b4  call    cs:__imp_GetCurrentProcessId
0x1800be9bb  nop     dword ptr [rax+rax+00h]
0x1800be9c0  mov     edi, eax
0x1800be9c2  call    cs:__imp_GetCommandLineW
0x1800be9c9  nop     dword ptr [rax+rax+00h]
0x1800be9ce  lea     rcx, aNcalrpc; "ncalrpc"
0x1800be9d5  mov     [rsp+38h+var_10], rbx
0x1800be9da  mov     r8, rax
0x1800be9dd  mov     [rsp+38h+var_18], rcx
0x1800be9e2  mov     r9d, edi
0x1800be9e5  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x1800be9ec  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800be9f1  mov     rcx, [rsi+1F8h]; void *
0x1800be9f8  call    I_RpcBCacheFree
0x1800be9fd  cmp     qword ptr [rsi+200h], 0
0x1800bea05  mov     qword ptr [rsi+1F8h], 0
0x1800bea10  jz      short loc_1800BEA1F
0x1800bea12  mov     edx, 1; int
0x1800bea17  mov     rcx, rsi; this
0x1800bea1a  call    ?FreeAlpcSectionAndView@LRPC_BASE_CCALL@@IEAAXH@Z; LRPC_BASE_CCALL::FreeAlpcSectionAndView(int)
0x1800bea1f  mov     rcx, rsi; this
0x1800bea22  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x1800bea27  xor     r9d, r9d; int
0x1800bea2a  mov     [rsp+38h+var_18], 0; struct tagParam *
0x1800bea33  mov     ebx, 6E4h
0x1800bea38  mov     r8d, 618h; unsigned __int16
0x1800bea3e  mov     edx, ebx; int
0x1800bea40  lea     ecx, [r9+2]; unsigned int
0x1800bea44  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800bea49  mov     rsi, [rsp+38h+arg_8]
0x1800bea4e  mov     eax, ebx
0x1800bea50  mov     rbx, [rsp+38h+arg_0]
0x1800bea55  add     rsp, 30h
0x1800bea59  pop     rdi
0x1800bea5a  retn
```
