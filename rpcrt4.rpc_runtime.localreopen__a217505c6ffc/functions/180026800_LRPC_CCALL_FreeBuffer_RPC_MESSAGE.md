# LRPC_CCALL::FreeBuffer(_RPC_MESSAGE *)

- ea: `0x180026800`
- end: `0x180026c59`
- name: `?FreeBuffer@LRPC_CCALL@@UEAAXPEAU_RPC_MESSAGE@@@Z`
- size: `1113`
- prototype: `void __fastcall(LRPC_CCALL *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1800177ac`
- `0x180025d70`
- `0x180026800`
- `0x180026df0`
- `0x180026e80`
- `0x180027e20`
- `0x180027e90`
- `0x1800283b0`
- `0x180028670`
- `0x18002cab0`
- `0x180096f20`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `KERNELBASE!Sleep` at `0x180026ae5`
- `KERNELBASE!Sleep` at `0x180026ae5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026ba7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026ba7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026b6e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026b6e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180026b87`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180026b87`

## pseudocode

```c
void __fastcall LRPC_CCALL::FreeBuffer(LRPC_CCALL *this, struct _RPC_MESSAGE *a2)
{
  unsigned __int64 ReservedForNtRpc; // rbx
  signed __int64 v5; // rbp
  signed __int64 v6; // rdi
  __int64 v7; // rax
  unsigned int v8; // edx
  BCACHE *v9; // rcx
  unsigned int v10; // ebx
  struct _PORT_MESSAGE *v11; // rdi
  unsigned int v12; // r10d
  unsigned __int64 HeaderSize; // r9
  int v14; // r10d
  int v15; // r11d
  int v16; // r11d
  unsigned __int64 v17; // rax
  unsigned int v18; // eax
  void *v19; // rdx
  void *v20; // rdx
  void *v21; // rdx
  void *v22; // rdx
  union _LARGE_INTEGER *v23; // [rsp+38h] [rbp-70h]
  int v24; // [rsp+40h] [rbp-68h] BYREF
  int v25; // [rsp+44h] [rbp-64h]
  _QWORD v26[7]; // [rsp+48h] [rbp-60h]

  if ( !(*(unsigned int (__fastcall **)(LRPC_CCALL *))(*(_QWORD *)this + 288LL))(this)
    || !*(_DWORD *)(*((_QWORD *)this + 74) + 8LL) )
  {
    if ( (*((_DWORD *)this + 72) & 0x800) != 0
      && (!(*(unsigned int (__fastcall **)(LRPC_CCALL *))(*(_QWORD *)this + 288LL))(this)
       || !*(_DWORD *)(*((_QWORD *)this + 74) + 8LL)) )
    {
      ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
      if ( ReservedForNtRpc )
      {
        ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
        if ( *(HANDLE *)(ReservedForNtRpc + 16) != NtCurrentTeb()->ClientId.UniqueThread )
          __fastfail(0x1Eu);
      }
      v5 = *((_QWORD *)this + 104);
      do
      {
        v6 = *(_QWORD *)(ReservedForNtRpc + 72);
        if ( (LRPC_CCALL *)(v6 & 0xFFFFFFFFFFFFFFFCuLL) != this )
        {
          RpcpReportFatalError(21, this);
          __debugbreak();
        }
        while ( (*(_QWORD *)(ReservedForNtRpc + 72) & 1) != 0 )
          Sleep(0xAu);
      }
      while ( v6 != _InterlockedCompareExchange64((volatile signed __int64 *)(ReservedForNtRpc + 72), v5, v6) );
      v7 = *((_QWORD *)this + 105);
      *((_QWORD *)this + 104) = 0;
      if ( v7 )
      {
        _InterlockedOr((volatile signed __int32 *)this + 72, 0x10000u);
        if ( *((_QWORD *)this + 105) )
        {
          ResetEvent(*(HANDLE *)(ReservedForNtRpc + 24));
          DeleteTimerQueueTimer(0, *((HANDLE *)this + 105), *(HANDLE *)(ReservedForNtRpc + 24));
          _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFEFFFF);
          WaitForSingleObject(*(HANDLE *)(ReservedForNtRpc + 24), 0xFFFFFFFF);
        }
        else
        {
          _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFEFFFF);
        }
      }
    }
    v8 = 3;
    if ( *((int *)this + 67) < 3 )
      v8 = 0;
    LRPC_SYSTEM_HANDLE_DATA::CleanupSystemHandles((void **)this + 77, v8);
    if ( *((int *)this + 67) < 3 )
    {
      if ( (*((_DWORD *)this + 72) & 2) != 0 && *((int *)this + 66) < 10 )
        LRPC_BASE_CCALL::CancelCall(this);
      if ( *((_DWORD *)this + 67) == 2 )
      {
        v21 = (void *)*((_QWORD *)this + 63);
        if ( v21 )
          BCACHE::Free(v9, v21);
        *((_QWORD *)this + 63) = 0;
        if ( *((_QWORD *)this + 64) )
        {
          if ( (*((_DWORD *)this + 72) & 0x10) != 0 )
          {
            v22 = (void *)*((_QWORD *)this + 64);
            if ( v22 )
              BCACHE::Free(v9, v22);
            *((_QWORD *)this + 64) = 0;
            _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFFFFEF);
          }
          else
          {
            LRPC_BASE_CCALL::FreeAlpcSectionAndView(this, 1);
          }
        }
      }
      goto LABEL_32;
    }
    if ( !*((_QWORD *)this + 63) )
    {
LABEL_32:
      (*(void (__fastcall **)(LRPC_CCALL *))(*(_QWORD *)this + 32LL))(this);
      return;
    }
    v10 = 0;
    if ( *((_QWORD *)this + 68) )
    {
      if ( (*((_DWORD *)this + 72) & 0x4000) != 0 )
      {
        v20 = (void *)*((_QWORD *)this + 68);
        if ( v20 )
        {
          BCACHE::Free(v9, v20);
          *((_QWORD *)this + 68) = 0;
          goto LABEL_16;
        }
      }
      else
      {
        v10 = 0x40000000;
      }
      *((_QWORD *)this + 68) = 0;
    }
LABEL_16:
    if ( *((_DWORD *)this + 152) )
    {
      v10 |= 0x10000000u;
      *((_DWORD *)this + 152) = 0;
    }
    if ( v10 )
    {
      v11 = (struct _PORT_MESSAGE *)*((_QWORD *)this + 69);
      v12 = v10 & 0xEFFFFFFF;
      if ( (v10 & 0x10000000) == 0 )
        v12 = v10;
      HeaderSize = RpcpAlpcpGetHeaderSize(v12);
      v16 = v15 & 0x40000000;
      v17 = 40;
      if ( !v16 )
        v17 = 8;
      if ( HeaderSize > v17 )
      {
        v14 = v24;
      }
      else
      {
        v24 = v14;
        v25 = 0;
      }
      if ( v16 )
      {
        v18 = RpcpAlpcpGetHeaderSize(v14 & 0x80000000);
        *(int *)((char *)&v24 + v18) = 0x10000;
        *(_QWORD *)((char *)v26 + v18) = 0;
        *(_QWORD *)((char *)&v26[1] + v18) = 0;
        *(_QWORD *)((char *)&v26[2] + v18) = 0;
        v25 |= 0x40000000u;
      }
      LRPC_CASSOCIATION::AlpcSendWaitReceivePort(
        *((LRPC_CASSOCIATION **)this + 35),
        0,
        v11,
        (struct _ALPC_MESSAGE_ATTRIBUTES *)&v24,
        0,
        0,
        0,
        v23);
      if ( dword_1800FE624 )
        LogEventToEtw(0x4Cu, 0x40u, (__int64)v11, v10, 0);
    }
    v19 = (void *)*((_QWORD *)this + 69);
    if ( v19 )
      BCACHE::Free(v9, v19);
    *((_QWORD *)this + 69) = 0;
    *((_QWORD *)this + 63) = 0;
    goto LABEL_32;
  }
  REFERENCED_OBJECT::AddReference(this);
  LRPC_BASE_CCALL::FreeBuffer(this, a2);
  *((_DWORD *)this + 67) = 0;
}

```

## disassembly

```asm
0x180026800  mov     [rsp+arg_10], rbx
0x180026805  push    rsi
0x180026806  push    rdi
0x180026807  push    r14
0x180026809  sub     rsp, 90h
0x180026810  mov     rax, cs:__security_cookie
0x180026817  xor     rax, rsp
0x18002681a  mov     [rsp+0A8h+var_28], rax
0x180026822  mov     rax, [rcx]
0x180026825  mov     rdi, rdx
0x180026828  mov     rsi, rcx
0x18002682b  mov     rax, [rax+120h]
0x180026832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026837  test    eax, eax
0x180026839  jnz     loc_180026A91
0x18002683f  mov     eax, [rsi+120h]
0x180026845  xor     r14d, r14d
0x180026848  mov     [rsp+0A8h+arg_8], rbp
0x180026850  bt      eax, 0Bh
0x180026854  jnb     loc_180026902
0x18002685a  mov     rax, [rsi]
0x18002685d  mov     rcx, rsi
0x180026860  mov     rax, [rax+120h]
0x180026867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002686c  test    eax, eax
0x18002686e  jnz     loc_180026B54
0x180026874  mov     rbx, gs:30h
0x18002687d  mov     rbx, [rbx+1698h]
0x180026884  test    rbx, rbx
0x180026887  jz      short loc_1800268AD
0x180026889  mov     rax, 0ABABABABDEDEDEDEh
0x180026893  xor     rbx, rax
0x180026896  mov     rax, gs:30h
0x18002689f  mov     rcx, [rax+48h]
0x1800268a3  cmp     [rbx+10h], rcx
0x1800268a7  jnz     loc_180026A8A
0x1800268ad  mov     rbp, [rsi+340h]
0x1800268b4  nop     dword ptr [rax+00h]
0x1800268b8  nop     dword ptr [rax+rax+00000000h]
0x1800268c0  mov     rdi, [rbx+48h]
0x1800268c4  mov     rax, rdi
0x1800268c7  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800268cb  cmp     rax, rsi
0x1800268ce  jnz     loc_180026A7C
0x1800268d4  mov     rax, [rbx+48h]
0x1800268d8  test    al, 1
0x1800268da  jnz     loc_180026AE0
0x1800268e0  mov     rax, rdi
0x1800268e3  lock cmpxchg [rbx+48h], rbp
0x1800268e9  jnz     short loc_1800268C0
0x1800268eb  mov     rax, [rsi+348h]
0x1800268f2  mov     [rsi+340h], r14
0x1800268f9  test    rax, rax
0x1800268fc  jnz     loc_180026B2D
0x180026902  mov     edx, 3
0x180026907  lea     rcx, [rsi+268h]; this
0x18002690e  cmp     [rsi+10Ch], edx
0x180026914  cmovl   edx, r14d; unsigned int
0x180026918  call    ?CleanupSystemHandles@LRPC_SYSTEM_HANDLE_DATA@@QEAAHK@Z; LRPC_SYSTEM_HANDLE_DATA::CleanupSystemHandles(ulong)
0x18002691d  cmp     dword ptr [rsi+10Ch], 3
0x180026924  jl      loc_180026BB8
0x18002692a  cmp     [rsi+1F8h], r14
0x180026931  jz      loc_180026A40
0x180026937  mov     ebx, r14d
0x18002693a  cmp     [rsi+220h], rbx
0x180026941  jnz     loc_180026AC1
0x180026947  cmp     [rsi+260h], r14d
0x18002694e  jnz     loc_180026B00
0x180026954  test    ebx, ebx
0x180026956  jz      loc_180026A21
0x18002695c  mov     rdi, [rsi+228h]
0x180026963  mov     r10d, ebx
0x180026966  btr     r10d, 1Ch
0x18002696b  mov     r11d, ebx
0x18002696e  bt      ebx, 1Ch
0x180026972  cmovnb  r10d, ebx
0x180026976  mov     ecx, r10d; unsigned int
0x180026979  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x18002697e  mov     r9d, eax
0x180026981  and     r11d, 40000000h
0x180026988  mov     eax, 28h ; '('
0x18002698d  mov     ecx, 8
0x180026992  cmovz   eax, ecx
0x180026995  cmp     r9, rax
0x180026998  ja      loc_180026C35
0x18002699e  mov     [rsp+0A8h+var_68], r10d
0x1800269a3  mov     [rsp+0A8h+var_64], r14d
0x1800269a8  test    r11d, r11d
0x1800269ab  jz      short loc_1800269DF
0x1800269ad  and     r10d, 80000000h
0x1800269b4  mov     ecx, r10d; unsigned int
0x1800269b7  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x1800269bc  mov     r9d, eax
0x1800269bf  mov     [rsp+r9+0A8h+var_68], 10000h
0x1800269c8  mov     [rsp+r9+0A8h+var_60], r14
0x1800269cd  mov     [rsp+r9+0A8h+var_58], r14
0x1800269d2  mov     [rsp+r9+0A8h+var_50], r14
0x1800269d7  or      [rsp+0A8h+var_64], 40000000h
0x1800269df  mov     rcx, [rsi+118h]; this
0x1800269e6  lea     r9, [rsp+0A8h+var_68]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x1800269eb  mov     [rsp+0A8h+var_78], r14; struct _ALPC_MESSAGE_ATTRIBUTES *
0x1800269f0  mov     r8, rdi; struct _PORT_MESSAGE *
0x1800269f3  mov     [rsp+0A8h+var_80], r14; unsigned __int64 *
0x1800269f8  xor     edx, edx; unsigned int
0x1800269fa  mov     [rsp+0A8h+var_88], r14; struct _PORT_MESSAGE *
0x1800269ff  call    ?AlpcSendWaitReceivePort@LRPC_CASSOCIATION@@QEAAJKPEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@0PEA_K1PEAT_LARGE_INTEGER@@@Z; LRPC_CASSOCIATION::AlpcSendWaitReceivePort(ulong,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,unsigned __int64 *,_ALPC_MESSAGE_ATTRIBUTES *,_LARGE_INTEGER *)
0x180026a04  cmp     cs:dword_1800FE624, r14d
0x180026a0b  jz      short loc_180026A21
0x180026a0d  mov     r9d, ebx; __int64
0x180026a10  mov     r8, rdi; __int64
0x180026a13  mov     dl, 40h ; '@'; unsigned __int8
0x180026a15  mov     [rsp+0A8h+var_88], r14; __int64
0x180026a1a  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180026a1c  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x180026a21  mov     rdx, [rsi+228h]; void *
0x180026a28  test    rdx, rdx
0x180026a2b  jz      short loc_180026A32
0x180026a2d  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x180026a32  mov     [rsi+228h], r14
0x180026a39  mov     [rsi+1F8h], r14
0x180026a40  mov     rax, [rsi]
0x180026a43  mov     rcx, rsi
0x180026a46  mov     rax, [rax+20h]
0x180026a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a4f  mov     rbp, [rsp+0A8h+arg_8]
0x180026a57  mov     rcx, [rsp+0A8h+var_28]
0x180026a5f  xor     rcx, rsp; StackCookie
0x180026a62  call    __security_check_cookie
0x180026a67  mov     rbx, [rsp+0A8h+arg_10]
0x180026a6f  add     rsp, 90h
0x180026a76  pop     r14
0x180026a78  pop     rdi
0x180026a79  pop     rsi
0x180026a7a  retn
0x180026a7c  mov     rdx, rsi
0x180026a7f  mov     ecx, 15h
0x180026a84  call    RpcpReportFatalError
0x180026a89  int     3; Trap to Debugger
0x180026a8a  mov     ecx, 1Eh
0x180026a8f  int     29h; Win8: RtlFailFast(ecx)
0x180026a91  mov     rax, [rsi+250h]
0x180026a98  cmp     dword ptr [rax+8], 0
0x180026a9c  jbe     loc_18002683F
0x180026aa2  mov     rcx, rsi; this
0x180026aa5  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x180026aaa  mov     rdx, rdi; struct _RPC_MESSAGE *
0x180026aad  mov     rcx, rsi; this
0x180026ab0  call    ?FreeBuffer@LRPC_BASE_CCALL@@UEAAXPEAU_RPC_MESSAGE@@@Z; LRPC_BASE_CCALL::FreeBuffer(_RPC_MESSAGE *)
0x180026ab5  xor     r14d, r14d
0x180026ab8  mov     [rsi+10Ch], r14d
0x180026abf  jmp     short loc_180026A57
0x180026ac1  mov     eax, [rsi+120h]
0x180026ac7  bt      eax, 0Eh
0x180026acb  jb      short loc_180026B10
0x180026acd  mov     ebx, 40000000h
0x180026ad2  mov     [rsi+220h], r14
0x180026ad9  jmp     loc_180026947
0x180026ae0  mov     ecx, 0Ah; dwMilliseconds
0x180026ae5  call    cs:__imp_Sleep
0x180026aec  nop     dword ptr [rax+rax+00h]
0x180026af1  mov     rcx, [rbx+48h]
0x180026af5  test    cl, 1
0x180026af8  jz      loc_1800268E0
0x180026afe  jmp     short loc_180026AE0
0x180026b00  bts     ebx, 1Ch
0x180026b04  mov     [rsi+260h], r14d
0x180026b0b  jmp     loc_180026954
0x180026b10  mov     rdx, [rsi+220h]; void *
0x180026b17  test    rdx, rdx
0x180026b1a  jz      short loc_180026AD2
0x180026b1c  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x180026b21  mov     [rsi+220h], r14
0x180026b28  jmp     loc_180026947
0x180026b2d  lock or dword ptr [rsi+120h], 10000h
0x180026b38  mov     rax, [rsi+348h]
0x180026b3f  test    rax, rax
0x180026b42  jnz     short loc_180026B6A
0x180026b44  lock and dword ptr [rsi+120h], 0FFFEFFFFh
0x180026b4f  jmp     loc_180026902
0x180026b54  mov     rax, [rsi+250h]
0x180026b5b  cmp     [rax+8], r14d
0x180026b5f  jz      loc_180026874
0x180026b65  jmp     loc_180026902
0x180026b6a  mov     rcx, [rbx+18h]; hEvent
0x180026b6e  call    cs:__imp_ResetEvent
0x180026b75  nop     dword ptr [rax+rax+00h]
0x180026b7a  mov     r8, [rbx+18h]; CompletionEvent
0x180026b7e  xor     ecx, ecx; TimerQueue
0x180026b80  mov     rdx, [rsi+348h]; Timer
0x180026b87  call    cs:__imp_DeleteTimerQueueTimer
0x180026b8e  nop     dword ptr [rax+rax+00h]
0x180026b93  lock and dword ptr [rsi+120h], 0FFFEFFFFh
0x180026b9e  mov     rcx, [rbx+18h]; hHandle
0x180026ba2  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180026ba7  call    cs:__imp_WaitForSingleObject
0x180026bae  nop     dword ptr [rax+rax+00h]
0x180026bb3  jmp     loc_180026902
0x180026bb8  mov     eax, [rsi+120h]
0x180026bbe  test    al, 2
0x180026bc0  jnz     short loc_180026C3F
0x180026bc2  cmp     dword ptr [rsi+10Ch], 2
0x180026bc9  jnz     loc_180026A40
0x180026bcf  mov     rdx, [rsi+1F8h]; void *
0x180026bd6  test    rdx, rdx
0x180026bd9  jz      short loc_180026BE0
0x180026bdb  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x180026be0  mov     [rsi+1F8h], r14
0x180026be7  cmp     [rsi+200h], r14
0x180026bee  jz      loc_180026A40
0x180026bf4  mov     eax, [rsi+120h]
0x180026bfa  test    al, 10h
0x180026bfc  jnz     short loc_180026C10
0x180026bfe  mov     edx, 1; int
0x180026c03  mov     rcx, rsi; this
0x180026c06  call    ?FreeAlpcSectionAndView@LRPC_BASE_CCALL@@IEAAXH@Z; LRPC_BASE_CCALL::FreeAlpcSectionAndView(int)
0x180026c0b  jmp     loc_180026A40
0x180026c10  mov     rdx, [rsi+200h]; void *
0x180026c17  test    rdx, rdx
0x180026c1a  jz      short loc_180026C21
0x180026c1c  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x180026c21  mov     [rsi+200h], r14
0x180026c28  lock and dword ptr [rsi+120h], 0FFFFFFEFh
0x180026c30  jmp     loc_180026A40
0x180026c35  mov     r10d, [rsp+0A8h+var_68]
0x180026c3a  jmp     loc_1800269A8
0x180026c3f  cmp     dword ptr [rsi+108h], 0Ah
0x180026c46  jge     loc_180026BC2
0x180026c4c  mov     rcx, rsi; this
0x180026c4f  call    ?CancelCall@LRPC_BASE_CCALL@@IEAAXXZ; LRPC_BASE_CCALL::CancelCall(void)
0x180026c54  jmp     loc_180026BC2
```
