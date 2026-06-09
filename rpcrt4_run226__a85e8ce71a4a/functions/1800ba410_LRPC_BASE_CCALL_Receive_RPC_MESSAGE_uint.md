# LRPC_BASE_CCALL::Receive(_RPC_MESSAGE *,uint)

- ea: `0x1800ba410`
- end: `0x1800ba4df`
- name: `?Receive@LRPC_BASE_CCALL@@UEAAJPEAU_RPC_MESSAGE@@I@Z`
- size: `207`
- prototype: `__int64 __fastcall(LRPC_BASE_CCALL *__hidden this, struct _RPC_MESSAGE *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800191d0`
- `0x180025280`
- `0x1800283bc`
- `0x18004b70c`
- `0x180061948`
- `0x1800a3fd4`
- `0x1800ba410`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800ba44c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800ba44c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ba444`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ba444`

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
0x1800ba410  mov     [rsp+arg_0], rbx
0x1800ba415  mov     [rsp+arg_8], rsi
0x1800ba41a  push    rdi
0x1800ba41b  sub     rsp, 30h
0x1800ba41f  mov     rsi, rcx
0x1800ba422  mov     r10, rdx
0x1800ba425  mov     ecx, 2; unsigned int
0x1800ba42a  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x1800ba42f  test    eax, eax
0x1800ba431  jnz     short loc_1800BA475
0x1800ba433  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x1800ba43a  jz      short loc_1800BA475
0x1800ba43c  mov     rbx, [r10+28h]
0x1800ba440  add     rbx, 4
0x1800ba444  call    cs:__imp_GetCurrentProcessId
0x1800ba44a  mov     edi, eax
0x1800ba44c  call    cs:__imp_GetCommandLineW
0x1800ba452  lea     rcx, aNcalrpc; "ncalrpc"
0x1800ba459  mov     [rsp+38h+var_10], rbx
0x1800ba45e  mov     r8, rax
0x1800ba461  mov     [rsp+38h+var_18], rcx
0x1800ba466  mov     r9d, edi
0x1800ba469  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x1800ba470  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800ba475  mov     rcx, [rsi+1F8h]; void *
0x1800ba47c  call    I_RpcBCacheFree
0x1800ba481  cmp     qword ptr [rsi+200h], 0
0x1800ba489  mov     qword ptr [rsi+1F8h], 0
0x1800ba494  jz      short loc_1800BA4A3
0x1800ba496  mov     edx, 1; int
0x1800ba49b  mov     rcx, rsi; this
0x1800ba49e  call    ?FreeAlpcSectionAndView@LRPC_BASE_CCALL@@IEAAXH@Z; LRPC_BASE_CCALL::FreeAlpcSectionAndView(int)
0x1800ba4a3  mov     rcx, rsi; this
0x1800ba4a6  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x1800ba4ab  xor     r9d, r9d; int
0x1800ba4ae  mov     [rsp+38h+var_18], 0; struct tagParam *
0x1800ba4b7  mov     ebx, 6E4h
0x1800ba4bc  mov     r8d, 618h; unsigned __int16
0x1800ba4c2  mov     edx, ebx; int
0x1800ba4c4  lea     ecx, [r9+2]; unsigned int
0x1800ba4c8  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800ba4cd  mov     rsi, [rsp+38h+arg_8]
0x1800ba4d2  mov     eax, ebx
0x1800ba4d4  mov     rbx, [rsp+38h+arg_0]
0x1800ba4d9  add     rsp, 30h
0x1800ba4dd  pop     rdi
0x1800ba4de  retn
```
