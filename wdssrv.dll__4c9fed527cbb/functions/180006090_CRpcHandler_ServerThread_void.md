# CRpcHandler::_ServerThread(void *)

- ea: `0x180006090`
- end: `0x18000617d`
- name: `?_ServerThread@CRpcHandler@@SAKPEAX@Z`
- size: `237`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003944`
- `0x180006090`

## import_xrefs

- `RPCRT4!RpcServerListen` at `0x1800060ed`
- `RPCRT4!RpcServerListen` at `0x1800060ed`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800060ac`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006168`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800060ac`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006168`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800060d5`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180006125`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180006146`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800060d5`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180006125`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180006146`

## pseudocode

```c
__int64 __fastcall CRpcHandler::_ServerThread(PVOID Parameter)
{
  unsigned int v1; // eax
  __int64 v2; // rdx
  unsigned int v3; // ebx

  CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[RPC] Server Started.");
  CEventLog::Log((CEventLog *)qword_180039300, 0x41010401u, 1);
  v1 = RpcServerListen(1u, 0x4D2u, 0);
  v3 = ElValidateWin32(v1, v2, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 1639);
  if ( v3 )
    CEventLog::Log((CEventLog *)qword_180039300, 0xC1010403, 1);
  else
    CEventLog::Log((CEventLog *)qword_180039300, 0x41010402u, 0, 0);
  CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[RPC] Server terminated (rc=%u)", v3);
  return v3;
}

```

## disassembly

```asm
0x180006090  push    rbx
0x180006092  sub     rsp, 30h
0x180006096  mov     rbx, rcx
0x180006099  lea     r8, aRpcServerStart; "[RPC] Server Started."
0x1800060a0  lea     rcx, qword_180039310
0x1800060a7  mov     edx, 20000h
0x1800060ac  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800060b3  nop     dword ptr [rax+rax+00h]
0x1800060b8  mov     eax, [rbx+58h]
0x1800060bb  lea     rcx, qword_180039300
0x1800060c2  mov     r9d, 2
0x1800060c8  mov     [rsp+38h+var_18], eax
0x1800060cc  mov     edx, 41010401h
0x1800060d1  lea     r8d, [r9-1]
0x1800060d5  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x1800060dc  nop     dword ptr [rax+rax+00h]
0x1800060e1  xor     r8d, r8d; DontWait
0x1800060e4  mov     edx, 4D2h; MaxCalls
0x1800060e9  lea     ecx, [r8+1]; MinimumCallThreads
0x1800060ed  call    cs:__imp_RpcServerListen
0x1800060f4  nop     dword ptr [rax+rax+00h]
0x1800060f9  mov     r9d, 667h
0x1800060ff  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180006106  mov     ecx, eax
0x180006108  call    ElValidateWin32
0x18000610d  lea     rcx, qword_180039300
0x180006114  mov     ebx, eax
0x180006116  test    eax, eax
0x180006118  jnz     short loc_180006133
0x18000611a  xor     r9d, r9d
0x18000611d  xor     r8d, r8d
0x180006120  mov     edx, 41010402h
0x180006125  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000612c  nop     dword ptr [rax+rax+00h]
0x180006131  jmp     short loc_180006152
0x180006133  mov     r9d, 5
0x180006139  mov     [rsp+38h+var_18], ebx
0x18000613d  mov     edx, 0C1010403h
0x180006142  lea     r8d, [r9-4]
0x180006146  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000614d  nop     dword ptr [rax+rax+00h]
0x180006152  mov     r9d, ebx
0x180006155  lea     r8, aRpcServerTermi; "[RPC] Server terminated (rc=%u)"
0x18000615c  mov     edx, 20000h
0x180006161  lea     rcx, qword_180039310
0x180006168  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000616f  nop     dword ptr [rax+rax+00h]
0x180006174  mov     eax, ebx
0x180006176  add     rsp, 30h
0x18000617a  pop     rbx
0x18000617b  retn
```
