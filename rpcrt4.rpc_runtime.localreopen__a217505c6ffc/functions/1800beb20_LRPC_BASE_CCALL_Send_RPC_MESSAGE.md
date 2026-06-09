# LRPC_BASE_CCALL::Send(_RPC_MESSAGE *)

- ea: `0x1800beb20`
- end: `0x1800bebfc`
- name: `?Send@LRPC_BASE_CCALL@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(LRPC_BASE_CCALL *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bec10`

## callees

- `0x1800162e0`
- `0x1800177ac`
- `0x180026500`
- `0x1800295d8`
- `0x180066718`
- `0x1800a72e0`
- `0x1800beb20`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800beb62`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800beb62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800beb54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800beb54`

## pseudocode

```c
__int64 __fastcall LRPC_BASE_CCALL::Send(void **this, struct _RPC_MESSAGE *a2)
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
  RpcpErrorAddRecord(2u, 1764, 0x60Eu, 0, 0);
  return 1764;
}

```

## disassembly

```asm
0x1800beb20  mov     [rsp+arg_0], rbx
0x1800beb25  mov     [rsp+arg_8], rsi
0x1800beb2a  push    rdi
0x1800beb2b  sub     rsp, 30h
0x1800beb2f  mov     rsi, rcx
0x1800beb32  mov     r10, rdx
0x1800beb35  mov     ecx, 2; unsigned int
0x1800beb3a  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x1800beb3f  test    eax, eax
0x1800beb41  jnz     short loc_1800BEB91
0x1800beb43  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x1800beb4a  jz      short loc_1800BEB91
0x1800beb4c  mov     rbx, [r10+28h]
0x1800beb50  add     rbx, 4
0x1800beb54  call    cs:__imp_GetCurrentProcessId
0x1800beb5b  nop     dword ptr [rax+rax+00h]
0x1800beb60  mov     edi, eax
0x1800beb62  call    cs:__imp_GetCommandLineW
0x1800beb69  nop     dword ptr [rax+rax+00h]
0x1800beb6e  lea     rcx, aNcalrpc; "ncalrpc"
0x1800beb75  mov     [rsp+38h+var_10], rbx
0x1800beb7a  mov     r8, rax
0x1800beb7d  mov     [rsp+38h+var_18], rcx
0x1800beb82  mov     r9d, edi
0x1800beb85  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x1800beb8c  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800beb91  mov     rcx, [rsi+1F8h]; void *
0x1800beb98  call    I_RpcBCacheFree
0x1800beb9d  cmp     qword ptr [rsi+200h], 0
0x1800beba5  mov     qword ptr [rsi+1F8h], 0
0x1800bebb0  jz      short loc_1800BEBBF
0x1800bebb2  mov     edx, 1; int
0x1800bebb7  mov     rcx, rsi; this
0x1800bebba  call    ?FreeAlpcSectionAndView@LRPC_BASE_CCALL@@IEAAXH@Z; LRPC_BASE_CCALL::FreeAlpcSectionAndView(int)
0x1800bebbf  mov     rcx, rsi; this
0x1800bebc2  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x1800bebc7  xor     r9d, r9d; int
0x1800bebca  mov     [rsp+38h+var_18], 0; struct tagParam *
0x1800bebd3  mov     ebx, 6E4h
0x1800bebd8  mov     r8d, 60Eh; unsigned __int16
0x1800bebde  mov     edx, ebx; int
0x1800bebe0  lea     ecx, [r9+2]; unsigned int
0x1800bebe4  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800bebe9  mov     rsi, [rsp+38h+arg_8]
0x1800bebee  mov     eax, ebx
0x1800bebf0  mov     rbx, [rsp+38h+arg_0]
0x1800bebf5  add     rsp, 30h
0x1800bebf9  pop     rdi
0x1800bebfa  retn
```
