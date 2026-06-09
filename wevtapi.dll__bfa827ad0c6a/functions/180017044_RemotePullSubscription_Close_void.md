# RemotePullSubscription::Close(void)

- ea: `0x180017044`
- end: `0x1800171eb`
- name: `?Close@RemotePullSubscription@@AEAAXXZ`
- size: `423`
- prototype: `void __fastcall(RemotePullSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800291f0`

## callees

- `0x180014b90`
- `0x1800158d4`
- `0x180017044`
- `0x18001fdb4`
- `0x180023548`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017144`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017144`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017065`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017151`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017065`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017151`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800171b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800171b5`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x1800170cd`
- `RPCRT4!RpcAsyncGetCallStatus` at `0x1800170cd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180017170`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180017170`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800170e0`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800170e0`

## pseudocode

```c
void __fastcall RemotePullSubscription::Close(RemotePullSubscription *this)
{
  char v2; // di
  RTL_SRWLOCK *v3; // rsi
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  struct _TP_WAIT *v7; // rcx
  DWORD Reply; // [rsp+50h] [rbp+8h] BYREF

  v2 = 1;
  v3 = (RTL_SRWLOCK *)((char *)this + 56);
  AcquireSRWLockExclusive((PSRWLOCK)this + 7);
  *((_BYTE *)this + 272) = 1;
  if ( *((_BYTE *)this + 273) )
  {
    v4 = EvtRpcCancel(*((_QWORD *)this + 6));
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, v4);
      }
      *((_QWORD *)this + 5) = 0;
    }
    if ( RpcAsyncGetCallStatus((PRPC_ASYNC_STATE)((char *)this + 64)) == 997 )
    {
      v5 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)this + 64), 1);
      if ( v5 != 1818 )
      {
        if ( v5 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, v5);
          }
          v2 = 0;
        }
      }
    }
  }
  ReleaseSRWLockExclusive(v3);
  Reply = 0;
  if ( v2 )
    Reply = WaitForSingleObject(*((HANDLE *)this + 25), 0xFFFFFFFF);
  AcquireSRWLockExclusive(v3);
  if ( *((_BYTE *)this + 273) )
  {
    *((_BYTE *)this + 273) = 0;
    v6 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 64), &Reply);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, v6, Reply);
      }
    }
  }
  ReleaseSRWLockExclusive(v3);
  v7 = (struct _TP_WAIT *)*((_QWORD *)this + 23);
  *((_QWORD *)this + 23) = 0;
  if ( v7 )
    RemotePushSubscription::WaitAndCloseThreadpoolWait(v7);
}

```

## disassembly

```asm
0x180017044  mov     [rsp+arg_8], rbx
0x180017049  mov     [rsp+arg_10], rbp
0x18001704e  push    rsi
0x18001704f  push    rdi
0x180017050  push    r12
0x180017052  sub     rsp, 30h
0x180017056  mov     rbx, rcx
0x180017059  mov     edi, 1
0x18001705e  lea     rsi, [rcx+38h]
0x180017062  mov     rcx, rsi; SRWLock
0x180017065  call    cs:__imp_AcquireSRWLockExclusive
0x18001706b  mov     [rbx+110h], dil
0x180017072  lea     r12, WPP_GLOBAL_Control
0x180017079  cmp     byte ptr [rbx+111h], 0
0x180017080  jz      loc_180017124
0x180017086  mov     rcx, [rbx+30h]
0x18001708a  call    EvtRpcCancel
0x18001708f  test    eax, eax
0x180017091  jz      short loc_1800170C9
0x180017093  mov     rcx, cs:WPP_GLOBAL_Control
0x18001709a  cmp     rcx, r12
0x18001709d  jz      short loc_1800170C1
0x18001709f  test    byte ptr [rcx+1Ch], 80h
0x1800170a3  jz      short loc_1800170C1
0x1800170a5  cmp     byte ptr [rcx+19h], 2
0x1800170a9  jb      short loc_1800170C1
0x1800170ab  lea     edx, [rdi+0Eh]
0x1800170ae  mov     r9d, eax
0x1800170b1  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x1800170b8  mov     rcx, [rcx+10h]
0x1800170bc  call    WPP_SF_D
0x1800170c1  mov     qword ptr [rbx+28h], 0
0x1800170c9  lea     rcx, [rbx+40h]; pAsync
0x1800170cd  call    cs:__imp_RpcAsyncGetCallStatus
0x1800170d3  cmp     eax, 3E5h
0x1800170d8  jnz     short loc_180017124
0x1800170da  mov     edx, edi; fAbort
0x1800170dc  lea     rcx, [rbx+40h]; pAsync
0x1800170e0  call    cs:__imp_RpcAsyncCancelCall
0x1800170e6  cmp     eax, 71Ah
0x1800170eb  jz      short loc_180017124
0x1800170ed  test    eax, eax
0x1800170ef  jz      short loc_180017124
0x1800170f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170f8  cmp     rcx, r12
0x1800170fb  jz      short loc_180017121
0x1800170fd  test    byte ptr [rcx+1Ch], 80h
0x180017101  jz      short loc_180017121
0x180017103  cmp     byte ptr [rcx+19h], 2
0x180017107  jb      short loc_180017121
0x180017109  mov     edx, 10h
0x18001710e  mov     r9d, eax
0x180017111  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180017118  mov     rcx, [rcx+10h]
0x18001711c  call    WPP_SF_D
0x180017121  xor     dil, dil
0x180017124  mov     rcx, rsi; SRWLock
0x180017127  call    cs:__imp_ReleaseSRWLockExclusive
0x18001712d  mov     [rsp+48h+Reply], 0
0x180017135  test    dil, dil
0x180017138  jz      short loc_18001714E
0x18001713a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001713d  mov     rcx, [rbx+0C8h]; hHandle
0x180017144  call    cs:__imp_WaitForSingleObject
0x18001714a  mov     [rsp+48h+Reply], eax
0x18001714e  mov     rcx, rsi; SRWLock
0x180017151  call    cs:__imp_AcquireSRWLockExclusive
0x180017157  cmp     byte ptr [rbx+111h], 0
0x18001715e  jz      short loc_1800171B2
0x180017160  mov     byte ptr [rbx+111h], 0
0x180017167  lea     rcx, [rbx+40h]; pAsync
0x18001716b  lea     rdx, [rsp+48h+Reply]; Reply
0x180017170  call    cs:__imp_RpcAsyncCompleteCall
0x180017176  mov     r9d, eax
0x180017179  test    eax, eax
0x18001717b  jz      short loc_1800171B2
0x18001717d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017184  cmp     rcx, r12
0x180017187  jz      short loc_1800171B2
0x180017189  test    byte ptr [rcx+1Ch], 80h
0x18001718d  jz      short loc_1800171B2
0x18001718f  cmp     byte ptr [rcx+19h], 2
0x180017193  jb      short loc_1800171B2
0x180017195  mov     edx, 11h
0x18001719a  mov     eax, [rsp+48h+Reply]
0x18001719e  mov     [rsp+48h+var_28], eax
0x1800171a2  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x1800171a9  mov     rcx, [rcx+10h]
0x1800171ad  call    WPP_SF_DD
0x1800171b2  mov     rcx, rsi; SRWLock
0x1800171b5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800171bb  mov     rcx, [rbx+0B8h]; pwa
0x1800171c2  mov     qword ptr [rbx+0B8h], 0
0x1800171cd  test    rcx, rcx
0x1800171d0  jz      short loc_1800171D8
0x1800171d2  call    ?WaitAndCloseThreadpoolWait@RemotePushSubscription@@CAXPEAU_TP_WAIT@@@Z; RemotePushSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *)
0x1800171d7  nop
0x1800171d8  mov     rbx, [rsp+48h+arg_8]
0x1800171dd  mov     rbp, [rsp+48h+arg_10]
0x1800171e2  add     rsp, 30h
0x1800171e6  pop     r12
0x1800171e8  pop     rdi
0x1800171e9  pop     rsi
0x1800171ea  retn
```
