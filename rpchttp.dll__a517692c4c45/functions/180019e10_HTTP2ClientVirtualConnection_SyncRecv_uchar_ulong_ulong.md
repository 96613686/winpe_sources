# HTTP2ClientVirtualConnection::SyncRecv(uchar * *,ulong *,ulong)

- ea: `0x180019e10`
- end: `0x180019ff3`
- name: `?SyncRecv@HTTP2ClientVirtualConnection@@UEAAJPEAPEAEPEAKK@Z`
- size: `483`
- prototype: `__int64 __fastcall(HTTP2ClientVirtualConnection *__hidden this, unsigned __int8 **, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800043d8`
- `0x18000f334`
- `0x1800117f0`
- `0x180016df8`
- `0x180019e10`
- `0x18001ac1c`
- `0x18001b024`
- `0x18001f1a8`
- `0x180025010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180019eb7`
- `KERNEL32!ResetEvent` at `0x180019eb7`
- `RPCRT4!I_RpcLogEvent` at `0x180019ea4`
- `RPCRT4!I_RpcLogEvent` at `0x180019ea4`
- `RPCRT4!I_RpcTransGetThreadEvent` at `0x180019eaa`
- `RPCRT4!I_RpcTransGetThreadEvent` at `0x180019eaa`

## pseudocode

```c
__int64 __fastcall HTTP2ClientVirtualConnection::SyncRecv(
        HTTP2ClientVirtualConnection *this,
        unsigned __int8 **a2,
        unsigned int *a3,
        unsigned int a4)
{
  unsigned __int8 *v4; // rax
  int v5; // r14d
  unsigned int v6; // ebp
  __int64 result; // rax
  volatile int *i; // rax
  struct HTTP2Channel *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  struct HTTP2Channel *v15; // rsi
  void *ThreadEvent; // rax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  unsigned int v19; // eax
  int v20; // ebp
  int v21; // [rsp+40h] [rbp-48h] BYREF
  HTTP2ChannelPointer *v22; // [rsp+48h] [rbp-40h] BYREF
  int v23; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v24; // [rsp+A8h] [rbp+20h]

  v24 = a4;
  v4 = (unsigned __int8 *)*((_QWORD *)this + 5);
  v5 = 0;
  v22 = 0;
  v6 = a4;
  if ( v4 )
  {
    *a2 = v4;
    *a3 = *((_DWORD *)this + 12);
    result = 0;
    *((_QWORD *)this + 5) = 0;
    *((_DWORD *)this + 12) = 0;
  }
  else
  {
    for ( i = (volatile int *)((char *)this + 272); ; i = (volatile int *)((char *)this + 272) )
    {
      v12 = HTTP2VirtualConnection::LockDefaultChannel(
              this,
              i,
              (HTTP2ClientVirtualConnection *)((char *)this + 200),
              &v22);
      v15 = v12;
      if ( !v12 )
        return (unsigned int)-1073606647;
      LOBYTE(v13) = 111;
      LOBYTE(v14) = 50;
      I_RpcLogEvent(v14, v13, v12, 17498129, 2, 0, 0);
      ThreadEvent = (void *)I_RpcTransGetThreadEvent();
      *((_QWORD *)v15 + 12) = ThreadEvent;
      ResetEvent(ThreadEvent);
      *((_DWORD *)v15 + 23) = 0;
      v17 = HTTP2Channel::Receive(v15, 2u);
      HTTP2Channel::AddReference(v15);
      HTTP2ChannelPointer::UnlockChannelPointer(v22, v18);
      v21 = 0;
      if ( v17 )
      {
        v20 = 1;
      }
      else
      {
        v23 = 0;
        v19 = HTTP2ClientChannel::WaitForSyncRecv(v15, a2, a3, v6, *((_DWORD *)this + 94), this, &v23, &v21);
        v20 = v23;
        v17 = v19;
        v5 = v21;
      }
      if ( v20 )
        (*(void (__fastcall **)(struct HTTP2Channel *, _QWORD))(*(_QWORD *)v15 + 40LL))(v15, v17);
      if ( v5 )
      {
        UTIL_WaitForSyncHTTP2IO((struct _OVERLAPPED *)((char *)v15 + 72), *((void **)v15 + 12), 0, 0xFFFFFFFF);
        v5 = 0;
        *((_QWORD *)v15 + 12) = 0;
      }
      else
      {
        v5 = 0;
      }
      if ( !v20 )
        break;
      if ( !*((_DWORD *)this + 148) )
        break;
      *((_DWORD *)this + 148) = 0;
      if ( v17 == 1818 )
        break;
      HTTP2Channel::RemoveReference(v15);
      v6 = v24;
    }
    HTTP2Channel::RemoveReference(v15);
    if ( ((v17 + 1073606646) & 0xFFFFFFF7) == 0 || v17 == 1722 || v17 == -1073606648 )
      return (unsigned int)-1073606647;
    return v17;
  }
  return result;
}

```

## disassembly

```asm
0x180019e10  mov     [rsp+arg_8], rbx
0x180019e15  mov     [rsp+arg_18], r9d
0x180019e1a  push    rbp
0x180019e1b  push    rsi
0x180019e1c  push    rdi
0x180019e1d  push    r12
0x180019e1f  push    r13
0x180019e21  push    r14
0x180019e23  push    r15
0x180019e25  sub     rsp, 50h
0x180019e29  mov     rax, [rcx+28h]
0x180019e2d  xor     r14d, r14d
0x180019e30  mov     [rsp+88h+var_40], r14
0x180019e35  mov     ebp, r9d
0x180019e38  mov     r15, r8
0x180019e3b  mov     r12, rdx
0x180019e3e  mov     rdi, rcx
0x180019e41  test    rax, rax
0x180019e44  jz      short loc_180019E5E
0x180019e46  mov     [rdx], rax
0x180019e49  mov     eax, [rcx+30h]
0x180019e4c  mov     [r8], eax
0x180019e4f  xor     eax, eax
0x180019e51  mov     [rcx+28h], r14
0x180019e55  mov     [rcx+30h], r14d
0x180019e59  jmp     loc_180019FDB
0x180019e5e  lea     rax, [rcx+110h]
0x180019e65  lea     r9, [rsp+88h+var_40]; struct HTTP2ChannelPointer **
0x180019e6a  mov     rdx, rax; volatile int *
0x180019e6d  lea     r8, [rdi+0C8h]; struct HTTP2ChannelPointer *
0x180019e74  call    ?LockDefaultChannel@HTTP2VirtualConnection@@AEAAPEAVHTTP2Channel@@PECHQEAVHTTP2ChannelPointer@@PEAPEAV3@@Z; HTTP2VirtualConnection::LockDefaultChannel(int volatile *,HTTP2ChannelPointer * const,HTTP2ChannelPointer * *)
0x180019e79  mov     rsi, rax
0x180019e7c  test    rax, rax
0x180019e7f  jz      loc_180019FD4
0x180019e85  mov     dword ptr [rsp+88h+var_58], r14d
0x180019e8a  mov     r9d, 10B0011h
0x180019e90  mov     dword ptr [rsp+88h+var_60], r14d
0x180019e95  mov     r8, rax
0x180019e98  mov     dl, 6Fh ; 'o'
0x180019e9a  mov     [rsp+88h+var_68], 2
0x180019ea2  mov     cl, 32h ; '2'
0x180019ea4  call    cs:__imp_I_RpcLogEvent
0x180019eaa  call    cs:__imp_I_RpcTransGetThreadEvent
0x180019eb0  mov     rcx, rax; hEvent
0x180019eb3  mov     [rsi+60h], rax
0x180019eb7  call    cs:__imp_ResetEvent
0x180019ebd  mov     edx, 2
0x180019ec2  mov     [rsi+5Ch], r14d
0x180019ec6  mov     rcx, rsi
0x180019ec9  call    ?Receive@HTTP2Channel@@UEAAJW4tagHTTP2TrafficType@@@Z; HTTP2Channel::Receive(tagHTTP2TrafficType)
0x180019ece  mov     rcx, rsi; this
0x180019ed1  mov     ebx, eax
0x180019ed3  call    ?AddReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::AddReference(void)
0x180019ed8  mov     rcx, [rsp+88h+var_40]; this
0x180019edd  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x180019ee2  mov     [rsp+88h+var_48], r14d
0x180019ee7  test    ebx, ebx
0x180019ee9  jnz     short loc_180019F39
0x180019eeb  lea     rax, [rsp+88h+var_48]
0x180019ef0  mov     [rsp+88h+arg_0], ebx
0x180019ef7  mov     [rsp+88h+var_50], rax; int *
0x180019efc  mov     r9d, ebp; unsigned int
0x180019eff  lea     rax, [rsp+88h+arg_0]
0x180019f07  mov     r8, r15; unsigned int *
0x180019f0a  mov     [rsp+88h+var_58], rax; int *
0x180019f0f  mov     rdx, r12; unsigned __int8 **
0x180019f12  mov     eax, [rdi+178h]
0x180019f18  mov     rcx, rsi; this
0x180019f1b  mov     [rsp+88h+var_60], rdi; struct BASE_ASYNC_OBJECT *
0x180019f20  mov     [rsp+88h+var_68], eax; unsigned int
0x180019f24  call    ?WaitForSyncRecv@HTTP2ClientChannel@@QEAAJPEAPEAEPEAKKKPEAUBASE_ASYNC_OBJECT@@PEAH3@Z; HTTP2ClientChannel::WaitForSyncRecv(uchar * *,ulong *,ulong,ulong,BASE_ASYNC_OBJECT *,int *,int *)
0x180019f29  mov     ebp, [rsp+88h+arg_0]
0x180019f30  mov     ebx, eax
0x180019f32  mov     r14d, [rsp+88h+var_48]
0x180019f37  jmp     short loc_180019F3E
0x180019f39  mov     ebp, 1
0x180019f3e  test    ebp, ebp
0x180019f40  jz      short loc_180019F53
0x180019f42  mov     rax, [rsi]
0x180019f45  mov     edx, ebx
0x180019f47  mov     rcx, rsi
0x180019f4a  mov     rax, [rax+28h]
0x180019f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f53  test    r14d, r14d
0x180019f56  jz      short loc_180019F75
0x180019f58  mov     rdx, [rsi+60h]; void *
0x180019f5c  lea     rcx, [rsi+48h]; struct _OVERLAPPED *
0x180019f60  or      r9d, 0FFFFFFFFh; unsigned int
0x180019f64  xor     r8d, r8d; int
0x180019f67  call    ?UTIL_WaitForSyncHTTP2IO@@YAKPEAU_OVERLAPPED@@PEAXHK@Z; UTIL_WaitForSyncHTTP2IO(_OVERLAPPED *,void *,int,ulong)
0x180019f6c  xor     r14d, r14d
0x180019f6f  mov     [rsi+60h], r14
0x180019f73  jmp     short loc_180019F78
0x180019f75  xor     r14d, r14d
0x180019f78  test    ebp, ebp
0x180019f7a  jz      short loc_180019FAF
0x180019f7c  cmp     [rdi+250h], r14d
0x180019f83  jz      short loc_180019FAF
0x180019f85  mov     [rdi+250h], r14d
0x180019f8c  cmp     ebx, 71Ah
0x180019f92  jz      short loc_180019FAF
0x180019f94  mov     rcx, rsi; this
0x180019f97  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x180019f9c  mov     ebp, [rsp+88h+arg_18]
0x180019fa3  lea     rax, [rdi+110h]
0x180019faa  jmp     loc_180019E65
0x180019faf  mov     rcx, rsi; this
0x180019fb2  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x180019fb7  lea     eax, [rbx+3FFDEFF6h]
0x180019fbd  test    eax, 0FFFFFFF7h
0x180019fc2  jz      short loc_180019FD4
0x180019fc4  cmp     ebx, 6BAh
0x180019fca  jz      short loc_180019FD4
0x180019fcc  cmp     ebx, 0C0021008h
0x180019fd2  jnz     short loc_180019FD9
0x180019fd4  mov     ebx, 0C0021009h
0x180019fd9  mov     eax, ebx
0x180019fdb  mov     rbx, [rsp+88h+arg_8]
0x180019fe3  add     rsp, 50h
0x180019fe7  pop     r15
0x180019fe9  pop     r14
0x180019feb  pop     r13
0x180019fed  pop     r12
0x180019fef  pop     rdi
0x180019ff0  pop     rsi
0x180019ff1  pop     rbp
0x180019ff2  retn
```
