# RemoteSubscription::WaitAsync(_RPC_ASYNC_STATE *)

- ea: `0x1800716bc`
- end: `0x180071817`
- name: `?WaitAsync@RemoteSubscription@@QEAAXPEAU_RPC_ASYNC_STATE@@@Z`
- size: `347`
- prototype: `void __fastcall(RemoteSubscription *this, struct _RPC_ASYNC_STATE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007e420`

## callees

- `0x180048e24`
- `0x1800716bc`
- `0x180092008`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800716e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800716e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007173d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007173d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180071766`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18007179c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180071766`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18007179c`

## pseudocode

```c
void __fastcall RemoteSubscription::WaitAsync(RemoteSubscription *this, struct _RPC_ASYNC_STATE *a2)
{
  RTL_SRWLOCK *v4; // rdi
  void (*v5)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int); // r8
  unsigned int v6; // ebx
  __int128 pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int64 v8; // [rsp+30h] [rbp-20h]
  unsigned int v9; // [rsp+38h] [rbp-18h]
  int v10; // [rsp+3Ch] [rbp-14h]
  int v11; // [rsp+40h] [rbp-10h]
  int Reply; // [rsp+70h] [rbp+20h] BYREF
  char *v13; // [rsp+80h] [rbp+30h]

  Reply = 0;
  v4 = (RTL_SRWLOCK *)((char *)this + 32);
  v13 = (char *)this + 32;
  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  if ( (*((_DWORD *)this + 101) & 0x10000000) == 0 || *((_BYTE *)this + 414) || *((_QWORD *)this + 7) )
  {
    Reply = 4317;
LABEL_9:
    RpcAsyncCompleteCall(a2, &Reply);
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 102) )
  {
    Reply = *((_DWORD *)this + 102);
    goto LABEL_9;
  }
  if ( *((_BYTE *)this + 412) )
  {
    Reply = 0;
    goto LABEL_9;
  }
  *((_QWORD *)this + 7) = a2;
  a2->UserInfo = this;
  Reply = RemoteSubscription::RpcStatusSubscription::Start(
            (RemoteSubscription *)((char *)this + 112),
            *((struct _RPC_ASYNC_STATE **)this + 7),
            v5);
  if ( Reply )
  {
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    RpcAsyncCompleteCall(a2, &Reply);
    v6 = Reply;
    if ( !Reply )
      v6 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, v6);
    }
    pExceptionObject = 0;
    v8 = 0;
    v9 = v6;
    v10 = -1;
    v11 = 1035;
    throw (EvtException *)&pExceptionObject;
  }
LABEL_7:
  ReleaseSRWLockExclusive(v4);
}

```

## disassembly

```asm
0x1800716bc  mov     [rsp-18h+arg_8], rbx
0x1800716c1  mov     [rsp-18h+arg_18], rsi
0x1800716c6  push    rbp
0x1800716c7  push    rdi
0x1800716c8  push    r14
0x1800716ca  mov     rbp, rsp
0x1800716cd  sub     rsp, 50h
0x1800716d1  mov     rsi, rdx
0x1800716d4  mov     rbx, rcx
0x1800716d7  xor     r14d, r14d
0x1800716da  mov     [rbp+Reply], r14d
0x1800716de  lea     rdi, [rcx+20h]
0x1800716e2  mov     [rbp+arg_10], rdi
0x1800716e6  mov     rcx, rdi; SRWLock
0x1800716e9  call    cs:__imp_AcquireSRWLockExclusive
0x1800716ef  nop
0x1800716f0  test    dword ptr [rbx+194h], 10000000h
0x1800716fa  jz      short loc_180071758
0x1800716fc  cmp     [rbx+19Eh], r14b
0x180071703  jnz     short loc_180071758
0x180071705  cmp     [rbx+38h], r14
0x180071709  jnz     short loc_180071758
0x18007170b  mov     eax, [rbx+198h]
0x180071711  test    eax, eax
0x180071713  jnz     short loc_18007176E
0x180071715  cmp     [rbx+19Ch], r14b
0x18007171c  jnz     short loc_180071773
0x18007171e  mov     [rbx+38h], rsi
0x180071722  mov     [rsi+18h], rbx
0x180071726  lea     rcx, [rbx+70h]; this
0x18007172a  mov     rdx, [rbx+38h]; struct _RPC_ASYNC_STATE *
0x18007172e  call    ?Start@RpcStatusSubscription@RemoteSubscription@@QEAAJPEAU_RPC_ASYNC_STATE@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z@Z; RemoteSubscription::RpcStatusSubscription::Start(_RPC_ASYNC_STATE *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long))
0x180071733  mov     [rbp+Reply], eax
0x180071736  test    eax, eax
0x180071738  jnz     short loc_180071779
0x18007173a  mov     rcx, rdi; SRWLock
0x18007173d  call    cs:__imp_ReleaseSRWLockExclusive
0x180071743  lea     r11, [rsp+50h+var_s0]
0x180071748  mov     rbx, [r11+28h]
0x18007174c  mov     rsi, [r11+38h]
0x180071750  mov     rsp, r11
0x180071753  pop     r14
0x180071755  pop     rdi
0x180071756  pop     rbp
0x180071757  retn
0x180071758  mov     [rbp+Reply], 10DDh
0x18007175f  lea     rdx, [rbp+Reply]; Reply
0x180071763  mov     rcx, rsi; pAsync
0x180071766  call    cs:__imp_RpcAsyncCompleteCall
0x18007176c  jmp     short loc_18007173A
0x18007176e  mov     [rbp+Reply], eax
0x180071771  jmp     short loc_18007175F
0x180071773  mov     [rbp+Reply], r14d
0x180071777  jmp     short loc_18007175F
0x180071779  mov     [rbx+38h], r14
0x18007177d  mov     [rbx+40h], r14
0x180071781  mov     [rbx+48h], r14
0x180071785  mov     [rbx+50h], r14
0x180071789  mov     [rbx+58h], r14
0x18007178d  mov     [rbx+60h], r14
0x180071791  mov     [rbx+68h], r14
0x180071795  lea     rdx, [rbp+Reply]; Reply
0x180071799  mov     rcx, rsi; pAsync
0x18007179c  call    cs:__imp_RpcAsyncCompleteCall
0x1800717a2  mov     ebx, [rbp+Reply]
0x1800717a5  mov     eax, 507h
0x1800717aa  test    ebx, ebx
0x1800717ac  cmovz   ebx, eax
0x1800717af  lea     rax, WPP_GLOBAL_Control
0x1800717b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800717bd  cmp     rcx, rax
0x1800717c0  jz      short loc_1800717E9
0x1800717c2  test    dword ptr [rcx+1Ch], 100h
0x1800717c9  jz      short loc_1800717E9
0x1800717cb  cmp     byte ptr [rcx+19h], 2
0x1800717cf  jb      short loc_1800717E9
0x1800717d1  mov     edx, 21h ; '!'
0x1800717d6  mov     r9d, ebx
0x1800717d9  lea     r8, WPP_939241f3766634594ecc55fb100debfa_Traceguids
0x1800717e0  mov     rcx, [rcx+10h]
0x1800717e4  call    WPP_SF_d
0x1800717e9  xorps   xmm0, xmm0
0x1800717ec  movdqu  [rbp+pExceptionObject], xmm0
0x1800717f1  mov     [rbp+var_20], r14
0x1800717f5  mov     [rbp+var_18], ebx
0x1800717f8  mov     [rbp+var_14], 0FFFFFFFFh
0x1800717ff  mov     [rbp+var_10], 40Bh
0x180071806  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18007180d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180071811  call    _CxxThrowException_0
```
