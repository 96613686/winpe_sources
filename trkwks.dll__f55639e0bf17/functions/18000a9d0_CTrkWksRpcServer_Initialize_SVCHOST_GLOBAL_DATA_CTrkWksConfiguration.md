# CTrkWksRpcServer::Initialize(_SVCHOST_GLOBAL_DATA *,CTrkWksConfiguration *)

- ea: `0x18000a9d0`
- end: `0x18000aac6`
- name: `?Initialize@CTrkWksRpcServer@@QEAAXPEAU_SVCHOST_GLOBAL_DATA@@PEAVCTrkWksConfiguration@@@Z`
- size: `246`
- prototype: `void __fastcall(CTrkWksRpcServer *__hidden this, struct _SVCHOST_GLOBAL_DATA *, struct CTrkWksConfiguration *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a524`

## callees

- `0x18000a9d0`
- `0x18000aacc`
- `0x18000d038`
- `0x18000feb0`

## import_xrefs

- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000a9fc`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000aa58`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000a9fc`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000aa58`

## pseudocode

```c
void __fastcall CTrkWksRpcServer::Initialize(
        CTrkWksRpcServer *this,
        struct _SVCHOST_GLOBAL_DATA *a2,
        struct CTrkWksConfiguration *a3)
{
  RPC_STATUS v5; // eax
  int v6; // ebx
  unsigned int v7; // r8d
  RPC_STATUS v8; // eax
  void *v9; // rdx
  int v10; // ebx
  unsigned int v11; // r8d
  int v12; // [rsp+20h] [rbp-18h]
  const unsigned __int16 *v13; // [rsp+28h] [rbp-10h]

  v5 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_np", MaxCalls, (RPC_WSTR)L"\\pipe\\trkwks", 0);
  v6 = v5;
  if ( v5 && v5 != 1740 )
  {
    if ( v5 > 0 )
      v7 = (unsigned __int16)v5 | 0x80070000;
    else
      v7 = v5;
    TrkReportInternalError(0x72u, 0x71Du, v7, L"ncacn_np");
    TrkRaiseWin32Error(v6);
  }
  v8 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", MaxCalls, (RPC_WSTR)L"trkwks", 0);
  v10 = v8;
  if ( v8 && v8 != 1740 )
  {
    if ( v8 > 0 )
      v11 = (unsigned __int16)v8 | 0x80070000;
    else
      v11 = v8;
    TrkReportInternalError(0x72u, 0x72Fu, v11, L"ncalrpc");
    TrkRaiseWin32Error(v10);
  }
  CRpcServer::Initialize(this, v9, a2 == 0, MaxCalls, v12, v13);
}

```

## disassembly

```asm
0x18000a9d0  mov     [rsp+arg_0], rbx
0x18000a9d5  mov     [rsp+arg_8], rsi
0x18000a9da  push    rdi
0x18000a9db  sub     rsp, 30h
0x18000a9df  mov     rdi, rdx
0x18000a9e2  lea     r8, ?s_tszTrkWksRemoteRpcEndPoint@@3QBGB; "\\pipe\\trkwks"
0x18000a9e9  mov     edx, cs:MaxCalls; MaxCalls
0x18000a9ef  mov     rsi, rcx
0x18000a9f2  lea     rcx, ?s_tszTrkWksRemoteRpcProtocol@@3QBGB; "ncacn_np"
0x18000a9f9  xor     r9d, r9d; SecurityDescriptor
0x18000a9fc  call    cs:__imp_RpcServerUseProtseqEpW
0x18000aa02  mov     ebx, eax
0x18000aa04  test    eax, eax
0x18000aa06  jz      short loc_18000AA41
0x18000aa08  cmp     eax, 6CCh
0x18000aa0d  jz      short loc_18000AA41
0x18000aa0f  test    eax, eax
0x18000aa11  jg      short loc_18000AA18
0x18000aa13  mov     r8d, eax
0x18000aa16  jmp     short loc_18000AA23
0x18000aa18  movzx   r8d, bx
0x18000aa1c  or      r8d, 80070000h; int
0x18000aa23  lea     r9, ?s_tszTrkWksRemoteRpcProtocol@@3QBGB; "ncacn_np"
0x18000aa2a  mov     edx, 71Dh; unsigned int
0x18000aa2f  mov     ecx, 72h ; 'r'; unsigned int
0x18000aa34  call    ?TrkReportInternalError@@YAJKKJPEBG@Z; TrkReportInternalError(ulong,ulong,long,ushort const *)
0x18000aa39  mov     ecx, ebx; int
0x18000aa3b  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000aa41  mov     edx, cs:MaxCalls; MaxCalls
0x18000aa47  lea     r8, ?s_tszTrkWksLocalRpcEndPoint@@3QBGB; "trkwks"
0x18000aa4e  xor     r9d, r9d; SecurityDescriptor
0x18000aa51  lea     rcx, ?s_tszTrkWksLocalRpcProtocol@@3QBGB; "ncalrpc"
0x18000aa58  call    cs:__imp_RpcServerUseProtseqEpW
0x18000aa5e  mov     ebx, eax
0x18000aa60  test    eax, eax
0x18000aa62  jz      short loc_18000AA9D
0x18000aa64  cmp     eax, 6CCh
0x18000aa69  jz      short loc_18000AA9D
0x18000aa6b  test    eax, eax
0x18000aa6d  jg      short loc_18000AA74
0x18000aa6f  mov     r8d, eax
0x18000aa72  jmp     short loc_18000AA7F
0x18000aa74  movzx   r8d, bx
0x18000aa78  or      r8d, 80070000h; int
0x18000aa7f  lea     r9, ?s_tszTrkWksLocalRpcProtocol@@3QBGB; "ncalrpc"
0x18000aa86  mov     edx, 72Fh; unsigned int
0x18000aa8b  mov     ecx, 72h ; 'r'; unsigned int
0x18000aa90  call    ?TrkReportInternalError@@YAJKKJPEBG@Z; TrkReportInternalError(ulong,ulong,long,ushort const *)
0x18000aa95  mov     ecx, ebx; int
0x18000aa97  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000aa9d  mov     r9d, cs:MaxCalls; unsigned int
0x18000aaa4  xor     r8d, r8d
0x18000aaa7  test    rdi, rdi
0x18000aaaa  mov     rcx, rsi; this
0x18000aaad  setz    r8b; unsigned int
0x18000aab1  call    ?Initialize@CRpcServer@@QEAAXPEAXKIHPEBG@Z; CRpcServer::Initialize(void *,ulong,uint,int,ushort const *)
0x18000aab6  mov     rbx, [rsp+38h+arg_0]
0x18000aabb  mov     rsi, [rsp+38h+arg_8]
0x18000aac0  add     rsp, 30h
0x18000aac4  pop     rdi
0x18000aac5  retn
```
