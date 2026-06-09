# HTTP2ServerOutChannel::SyncSend(tagHTTP2TrafficType,ulong,uchar *,int,ulong,BASE_ASYNC_OBJECT *,HTTP2SendContext *)

- ea: `0x18001a0b0`
- end: `0x18001a165`
- name: `?SyncSend@HTTP2ServerOutChannel@@UEAAJW4tagHTTP2TrafficType@@KPEAEHKPEAUBASE_ASYNC_OBJECT@@PEAVHTTP2SendContext@@@Z`
- size: `181`
- prototype: `int __high(enum tagHTTP2TrafficType, unsigned int, unsigned __int8 *, int, unsigned int, struct BASE_ASYNC_OBJECT *, struct HTTP2SendContext *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180010ccc`
- `0x18001a0b0`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x18001a0eb`
- `RPCRT4!I_RpcLogEvent` at `0x18001a14d`
- `RPCRT4!I_RpcLogEvent` at `0x18001a0eb`
- `RPCRT4!I_RpcLogEvent` at `0x18001a14d`
- `RPCRT4!I_RpcTransGetThreadEventThreadOptional` at `0x18001a0f1`
- `RPCRT4!I_RpcTransGetThreadEventThreadOptional` at `0x18001a0f1`

## pseudocode

```c
__int64 __fastcall HTTP2ServerOutChannel::SyncSend(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int8 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        struct HTTP2SendContext *a8)
{
  __int64 v9; // r8
  __int64 v11; // rdi
  __int64 v12; // rdx
  HTTP2Channel *v13; // rcx
  unsigned int v14; // ebx

  v9 = a1;
  v11 = a1;
  LOBYTE(a1) = 50;
  LOBYTE(a2) = 111;
  I_RpcLogEvent(a1, a2, v9, 16842776, 0, 0, 0);
  if ( I_RpcTransGetThreadEventThreadOptional() )
  {
    HTTP2Channel::PrepareForSyncSend(v13, a3, a4, a8);
    v14 = (*(__int64 (__fastcall **)(__int64, struct HTTP2SendContext *))(*(_QWORD *)v11 + 8LL))(v11, a8);
  }
  else
  {
    v14 = 14;
  }
  LOBYTE(v12) = 111;
  LOBYTE(v13) = 50;
  I_RpcLogEvent(v13, v12, v11, 65560, v14, 0, 0);
  return v14;
}

```

## disassembly

```asm
0x18001a0b0  mov     rax, rsp
0x18001a0b3  mov     [rax+8], rbx
0x18001a0b7  mov     [rax+10h], rsi
0x18001a0bb  push    rdi
0x18001a0bc  sub     rsp, 40h
0x18001a0c0  mov     dword ptr [rax-18h], 0
0x18001a0c7  mov     esi, r8d
0x18001a0ca  mov     r8, rcx
0x18001a0cd  mov     dword ptr [rax-20h], 0
0x18001a0d4  mov     rbx, r9
0x18001a0d7  mov     dword ptr [rax-28h], 0
0x18001a0de  mov     rdi, rcx
0x18001a0e1  mov     r9d, 1010018h
0x18001a0e7  mov     cl, 32h ; '2'
0x18001a0e9  mov     dl, 6Fh ; 'o'
0x18001a0eb  call    cs:__imp_I_RpcLogEvent
0x18001a0f1  call    cs:__imp_I_RpcTransGetThreadEventThreadOptional
0x18001a0f7  test    rax, rax
0x18001a0fa  jnz     short loc_18001A101
0x18001a0fc  lea     ebx, [rax+0Eh]
0x18001a0ff  jmp     short loc_18001A12C
0x18001a101  mov     r9, [rsp+48h+arg_38]; struct HTTP2SendContext *
0x18001a109  mov     r8, rbx; unsigned __int8 *
0x18001a10c  mov     edx, esi; unsigned int
0x18001a10e  call    ?PrepareForSyncSend@HTTP2Channel@@QEAAXKPEAEPEAVHTTP2SendContext@@@Z; HTTP2Channel::PrepareForSyncSend(ulong,uchar *,HTTP2SendContext *)
0x18001a113  mov     rax, [rdi]
0x18001a116  mov     rcx, rdi
0x18001a119  mov     rdx, [rsp+48h+arg_38]
0x18001a121  mov     rax, [rax+8]
0x18001a125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a12a  mov     ebx, eax
0x18001a12c  mov     [rsp+48h+var_18], 0
0x18001a134  mov     r9d, 10018h
0x18001a13a  mov     [rsp+48h+var_20], 0
0x18001a142  mov     r8, rdi
0x18001a145  mov     dl, 6Fh ; 'o'
0x18001a147  mov     [rsp+48h+var_28], ebx
0x18001a14b  mov     cl, 32h ; '2'
0x18001a14d  call    cs:__imp_I_RpcLogEvent
0x18001a153  mov     rsi, [rsp+48h+arg_8]
0x18001a158  mov     eax, ebx
0x18001a15a  mov     rbx, [rsp+48h+arg_0]
0x18001a15f  add     rsp, 40h
0x18001a163  pop     rdi
0x18001a164  retn
```
