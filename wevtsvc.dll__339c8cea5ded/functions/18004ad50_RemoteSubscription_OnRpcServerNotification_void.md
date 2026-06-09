# RemoteSubscription::OnRpcServerNotification(void)

- ea: `0x18004ad50`
- end: `0x18004adfe`
- name: `?OnRpcServerNotification@RemoteSubscription@@AEAAXXZ`
- size: `174`
- prototype: `void __fastcall(RemoteSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004ad40`

## callees

- `0x180019d28`
- `0x18004ad50`
- `0x18004b378`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ad6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ad6a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004adbc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004adbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ade1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ade1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004add7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004add7`

## pseudocode

```c
void __fastcall RemoteSubscription::OnRpcServerNotification(RemoteSubscription *this)
{
  struct _RPC_ASYNC_STATE *v2; // rsi
  int Reply; // [rsp+30h] [rbp+8h] BYREF

  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  RemoteSubscription::RpcStatusSubscription::Stop((RemoteSubscription *)((char *)this + 112));
  v2 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  SetEvent(*((HANDLE *)this + 17));
  if ( v2 )
  {
    Reply = 1818;
    RpcAsyncCompleteCall(v2, &Reply);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this + 4);
  wmi::RefBase::Release(this);
}

```

## disassembly

```asm
0x18004ad50  mov     [rsp+arg_8], rbx
0x18004ad55  mov     [rsp+arg_10], rsi
0x18004ad5a  push    rdi
0x18004ad5b  sub     rsp, 20h
0x18004ad5f  mov     rbx, rcx
0x18004ad62  lock inc dword ptr [rcx+8]
0x18004ad66  add     rcx, 20h ; ' '; SRWLock
0x18004ad6a  call    cs:__imp_AcquireSRWLockExclusive
0x18004ad70  lea     rcx, [rbx+70h]; this
0x18004ad74  call    ?Stop@RpcStatusSubscription@RemoteSubscription@@QEAA_NXZ; RemoteSubscription::RpcStatusSubscription::Stop(void)
0x18004ad79  mov     rsi, [rbx+38h]
0x18004ad7d  mov     qword ptr [rbx+38h], 0
0x18004ad85  mov     qword ptr [rbx+40h], 0
0x18004ad8d  mov     qword ptr [rbx+48h], 0
0x18004ad95  mov     qword ptr [rbx+50h], 0
0x18004ad9d  mov     qword ptr [rbx+58h], 0
0x18004ada5  mov     qword ptr [rbx+60h], 0
0x18004adad  mov     qword ptr [rbx+68h], 0
0x18004adb5  mov     rcx, [rbx+88h]; hEvent
0x18004adbc  call    cs:__imp_SetEvent
0x18004adc2  test    rsi, rsi
0x18004adc5  jz      short loc_18004ADDD
0x18004adc7  lea     rdx, [rsp+28h+Reply]; Reply
0x18004adcc  mov     [rsp+28h+Reply], 71Ah
0x18004add4  mov     rcx, rsi; pAsync
0x18004add7  call    cs:__imp_RpcAsyncCompleteCall
0x18004addd  lea     rcx, [rbx+20h]; SRWLock
0x18004ade1  call    cs:__imp_ReleaseSRWLockExclusive
0x18004ade7  mov     rcx, rbx; this
0x18004adea  mov     rbx, [rsp+28h+arg_8]
0x18004adef  mov     rsi, [rsp+28h+arg_10]
0x18004adf4  add     rsp, 20h
0x18004adf8  pop     rdi
0x18004adf9  jmp     ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
```
