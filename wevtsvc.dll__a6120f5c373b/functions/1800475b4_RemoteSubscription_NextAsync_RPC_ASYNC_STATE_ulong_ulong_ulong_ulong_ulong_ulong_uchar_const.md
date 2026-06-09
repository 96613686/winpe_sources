# RemoteSubscription::NextAsync(_RPC_ASYNC_STATE *,ulong,ulong,ulong &,ulong * &,ulong * &,ulong &,uchar const * &)

- ea: `0x1800475b4`
- end: `0x1800479a2`
- name: `?NextAsync@RemoteSubscription@@QEAAXPEAU_RPC_ASYNC_STATE@@KKAEAKAEAPEAK21AEAPEBE@Z`
- size: `1006`
- prototype: `void __fastcall(RemoteSubscription *this, struct _RPC_ASYNC_STATE *, unsigned int, int, unsigned int *, unsigned int **, unsigned int **, unsigned int *, const unsigned __int8 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007e1d0`

## callees

- `0x180016250`
- `0x18001c320`
- `0x1800462a4`
- `0x1800475b4`
- `0x1800479b0`
- `0x180048e24`
- `0x180090c60`
- `0x180092008`
- `0x1800d334c`
- `0x1800d3370`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800475ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800475ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800477c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004788a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800477c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004788a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004779f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800478ab`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047911`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004779f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800478ab`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047911`

## pseudocode

```c
void __fastcall RemoteSubscription::NextAsync(
        RemoteSubscription *this,
        struct _RPC_ASYNC_STATE *a2,
        unsigned int a3,
        int a4,
        unsigned int *a5,
        unsigned int **a6,
        unsigned int **a7,
        unsigned int *a8,
        const unsigned __int8 **a9)
{
  RTL_SRWLOCK *v13; // rbx
  unsigned int *v14; // r15
  void *v15; // r14
  unsigned int v16; // eax
  void (*v17)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int); // r8
  unsigned int *v18; // rdx
  unsigned int *v19; // rcx
  unsigned int *v20; // rcx
  const unsigned __int8 **v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int *v24; // r14
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned int v28; // ebx
  void **v29; // [rsp+30h] [rbp-A8h] BYREF
  void *Src; // [rsp+38h] [rbp-A0h]
  size_t Size; // [rsp+40h] [rbp-98h]
  char v32; // [rsp+48h] [rbp-90h]
  void *v33; // [rsp+50h] [rbp-88h] BYREF
  void *v34; // [rsp+58h] [rbp-80h] BYREF
  void ***v35; // [rsp+60h] [rbp-78h] BYREF
  __int64 v36; // [rsp+68h] [rbp-70h]
  __int64 v37; // [rsp+70h] [rbp-68h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-60h] BYREF
  __int64 v39; // [rsp+88h] [rbp-50h]
  unsigned int v40; // [rsp+90h] [rbp-48h]
  int v41; // [rsp+94h] [rbp-44h]
  int v42; // [rsp+98h] [rbp-40h]
  char *v43; // [rsp+A0h] [rbp-38h]
  int Reply; // [rsp+E0h] [rbp+8h] BYREF
  struct _RPC_ASYNC_STATE *v45; // [rsp+E8h] [rbp+10h]

  v45 = a2;
  v13 = (RTL_SRWLOCK *)((char *)this + 32);
  v43 = (char *)this + 32;
  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  Reply = 0;
  if ( (*((_DWORD *)this + 101) & 0x10000000) != 0 || *((_BYTE *)this + 414) || *((_QWORD *)this + 7) )
  {
    Reply = 4317;
LABEL_20:
    RpcAsyncCompleteCall(a2, &Reply);
    goto LABEL_10;
  }
  v14 = a8;
  if ( *((_DWORD *)this + 102) )
  {
    Reply = *((_DWORD *)this + 102);
    goto LABEL_20;
  }
  MergedLogQueryResult::StartNewBatch(*((MergedLogQueryResult **)this + 34));
  v29 = &Buffer::`vftable';
  Size = 0x50000000000LL;
  v15 = operator new(0x500u);
  memcpy_0(v15, 0, 0);
  operator delete(0);
  Src = v15;
  v32 = 1;
  v35 = &v29;
  v36 = 0;
  v37 = 0;
  LODWORD(v15) = Buffer::GetSize((Buffer *)&v29);
  v36 = ((__int64 (__fastcall *)(void ***))(*v35)[6])(v35);
  HIDWORD(v37) = (_DWORD)v15;
  v34 = 0;
  v33 = 0;
  v16 = RemoteSubscription::WriteEventsFromLog(this, a3, 0xFFFFFFFFLL, &v35, &v34, &v33);
  if ( v16 )
  {
    v18 = a5;
    *a5 = v16;
    v19 = (unsigned int *)v34;
    v34 = 0;
    *a6 = v19;
    v20 = (unsigned int *)v33;
    v33 = 0;
    *a7 = v20;
    *v14 = v37;
    v32 = 0;
    v21 = a9;
    *a9 = (const unsigned __int8 *)Src;
    v22 = *v18;
    v23 = *v14;
    if ( (_DWORD)v22 )
    {
      if ( (_DWORD)v23 )
        goto LABEL_8;
    }
    else if ( !(_DWORD)v23 )
    {
      goto LABEL_8;
    }
    MicrosoftTelemetryAssertTriggeredArgs(v21, v22, v23);
LABEL_8:
    Reply = 0;
    RpcAsyncCompleteCall(a2, &Reply);
    v29 = &Buffer::`vftable';
    if ( v32 )
      operator delete(Src);
    goto LABEL_10;
  }
  if ( v33 )
    operator delete(v33);
  if ( v34 )
    operator delete(v34);
  v29 = &Buffer::`vftable';
  if ( v32 )
    operator delete(Src);
  *((_QWORD *)this + 7) = a2;
  *((_DWORD *)this + 16) = a3;
  *((_DWORD *)this + 17) = a4;
  v24 = a5;
  *((_QWORD *)this + 9) = a5;
  *((_QWORD *)this + 10) = a6;
  *((_QWORD *)this + 11) = a7;
  *((_QWORD *)this + 12) = v14;
  *((_QWORD *)this + 13) = a9;
  a2->UserInfo = this;
  Reply = RemoteSubscription::RpcStatusSubscription::Start(
            (RemoteSubscription *)((char *)this + 112),
            *((struct _RPC_ASYNC_STATE **)this + 7),
            v17);
  if ( Reply )
  {
    v26 = *v24;
    v27 = *v14;
    if ( (_DWORD)v26 )
    {
      if ( (_DWORD)v27 )
        goto LABEL_29;
    }
    else if ( !(_DWORD)v27 )
    {
LABEL_29:
      *((_QWORD *)this + 7) = 0;
      *((_QWORD *)this + 8) = 0;
      *((_QWORD *)this + 9) = 0;
      *((_QWORD *)this + 10) = 0;
      *((_QWORD *)this + 11) = 0;
      *((_QWORD *)this + 12) = 0;
      *((_QWORD *)this + 13) = 0;
      RpcAsyncCompleteCall(a2, &Reply);
      v28 = Reply;
      if ( !Reply )
        v28 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, v28);
      }
      pExceptionObject = 0;
      v39 = 0;
      v40 = v28;
      v41 = -1;
      v42 = 939;
      throw (EvtException *)&pExceptionObject;
    }
    MicrosoftTelemetryAssertTriggeredArgs(v25, v26, v27);
    goto LABEL_29;
  }
LABEL_10:
  ReleaseSRWLockExclusive(v13);
}

```

## disassembly

```asm
0x1800475b4  mov     rax, rsp
0x1800475b7  mov     [rax+18h], rbx
0x1800475bb  mov     [rax+20h], rsi
0x1800475bf  mov     [rax+10h], rdx
0x1800475c3  push    rdi
0x1800475c4  push    r12
0x1800475c6  push    r13
0x1800475c8  push    r14
0x1800475ca  push    r15
0x1800475cc  sub     rsp, 0B0h
0x1800475d3  mov     r13d, r9d
0x1800475d6  mov     r12d, r8d
0x1800475d9  mov     rsi, rdx
0x1800475dc  mov     rdi, rcx
0x1800475df  lea     rbx, [rcx+20h]
0x1800475e3  mov     [rax-38h], rbx
0x1800475e7  mov     rcx, rbx; SRWLock
0x1800475ea  call    cs:__imp_AcquireSRWLockExclusive
0x1800475f0  nop
0x1800475f1  xor     r14d, r14d
0x1800475f4  mov     [rsp+0D8h+Reply], r14d
0x1800475fc  test    dword ptr [rdi+194h], 10000000h
0x180047606  jnz     loc_180047895
0x18004760c  cmp     [rdi+19Eh], r14b
0x180047613  jnz     loc_180047895
0x180047619  cmp     [rdi+38h], r14
0x18004761d  jnz     loc_180047895
0x180047623  mov     r15, [rsp+0D8h+arg_38]
0x18004762b  mov     eax, [rdi+198h]
0x180047631  test    eax, eax
0x180047633  jnz     loc_1800478B3
0x180047639  mov     rcx, [rdi+110h]; this
0x180047640  call    ?StartNewBatch@MergedLogQueryResult@@UEAAXXZ; MergedLogQueryResult::StartNewBatch(void)
0x180047645  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x18004764c  mov     [rsp+0D8h+var_A8], rax
0x180047651  mov     [rsp+0D8h+Src], r14
0x180047656  mov     [rsp+0D8h+Size], r14
0x18004765b  mov     [rsp+0D8h+var_90], 1
0x180047660  mov     ecx, 500h; dwBytes
0x180047665  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004766a  mov     r14, rax
0x18004766d  mov     r8d, dword ptr [rsp+0D8h+Size]; Size
0x180047672  mov     rdx, [rsp+0D8h+Src]; Src
0x180047677  mov     rcx, rax; void *
0x18004767a  call    memcpy_0
0x18004767f  cmp     [rsp+0D8h+var_90], 0
0x180047684  jz      short loc_180047690
0x180047686  mov     rcx, [rsp+0D8h+Src]; void *
0x18004768b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180047690  mov     dword ptr [rsp+0D8h+Size+4], 500h
0x180047698  mov     [rsp+0D8h+Src], r14
0x18004769d  mov     [rsp+0D8h+var_90], 1
0x1800476a2  lea     rax, [rsp+0D8h+var_A8]
0x1800476a7  mov     [rsp+0D8h+var_78], rax
0x1800476ac  xor     eax, eax
0x1800476ae  mov     [rsp+0D8h+var_70], rax
0x1800476b3  mov     [rsp+0D8h+var_68], rax
0x1800476b8  mov     rax, [rsp+0D8h+var_A8]
0x1800476bd  lea     rcx, [rsp+0D8h+var_A8]
0x1800476c2  mov     rax, [rax+10h]
0x1800476c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476cb  mov     r14d, eax
0x1800476ce  mov     rcx, [rsp+0D8h+var_78]
0x1800476d3  mov     rdx, [rcx]
0x1800476d6  mov     rax, [rdx+30h]
0x1800476da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476df  mov     [rsp+0D8h+var_70], rax
0x1800476e4  mov     dword ptr [rsp+0D8h+var_68+4], r14d
0x1800476e9  xor     r14d, r14d
0x1800476ec  mov     [rsp+0D8h+var_80], r14
0x1800476f1  mov     [rsp+0D8h+var_88], r14
0x1800476f6  lea     rax, [rsp+0D8h+var_88]
0x1800476fb  mov     [rsp+0D8h+var_B0], rax
0x180047700  lea     rax, [rsp+0D8h+var_80]
0x180047705  mov     [rsp+0D8h+var_B8], rax
0x18004770a  lea     r9, [rsp+0D8h+var_78]
0x18004770f  or      r8d, 0FFFFFFFFh
0x180047713  mov     edx, r12d
0x180047716  mov     rcx, rdi
0x180047719  call    ?WriteEventsFromLog@RemoteSubscription@@AEAAKKKAEAVWriteBuffer@@AEAV?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@utl@@@utl@@1@Z; RemoteSubscription::WriteEventsFromLog(ulong,ulong,WriteBuffer &,utl::unique_ptr<ulong [0],utl::default_delete<ulong [0]>> &,utl::unique_ptr<ulong [0],utl::default_delete<ulong [0]>> &)
0x18004771e  test    eax, eax
0x180047720  jz      loc_1800477EA
0x180047726  mov     rdx, [rsp+0D8h+arg_20]
0x18004772e  mov     [rdx], eax
0x180047730  mov     rcx, [rsp+0D8h+var_80]
0x180047735  mov     [rsp+0D8h+var_80], r14
0x18004773a  mov     rax, [rsp+0D8h+arg_28]
0x180047742  mov     [rax], rcx
0x180047745  mov     rcx, [rsp+0D8h+var_88]
0x18004774a  mov     [rsp+0D8h+var_88], r14
0x18004774f  mov     rax, [rsp+0D8h+arg_30]
0x180047757  mov     [rax], rcx
0x18004775a  mov     eax, dword ptr [rsp+0D8h+var_68]
0x18004775e  mov     [r15], eax
0x180047761  mov     [rsp+0D8h+var_90], r14b
0x180047766  mov     rcx, [rsp+0D8h+arg_40]
0x18004776e  mov     rax, [rsp+0D8h+Src]
0x180047773  mov     [rcx], rax
0x180047776  mov     edx, [rdx]
0x180047778  mov     r8d, [r15]
0x18004777b  test    edx, edx
0x18004777d  jz      loc_1800478BC
0x180047783  test    r8d, r8d
0x180047786  jz      loc_1800478C5
0x18004778c  mov     [rsp+0D8h+Reply], r14d
0x180047794  lea     rdx, [rsp+0D8h+Reply]; Reply
0x18004779c  mov     rcx, rsi; pAsync
0x18004779f  call    cs:__imp_RpcAsyncCompleteCall
0x1800477a5  nop
0x1800477a6  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x1800477ad  mov     [rsp+0D8h+var_A8], rax
0x1800477b2  cmp     [rsp+0D8h+var_90], r14b
0x1800477b7  jz      short loc_1800477C4
0x1800477b9  mov     rcx, [rsp+0D8h+Src]; void *
0x1800477be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800477c3  nop
0x1800477c4  mov     rcx, rbx; SRWLock
0x1800477c7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800477cd  lea     r11, [rsp+0D8h+var_28]
0x1800477d5  mov     rbx, [r11+40h]
0x1800477d9  mov     rsi, [r11+48h]
0x1800477dd  mov     rsp, r11
0x1800477e0  pop     r15
0x1800477e2  pop     r14
0x1800477e4  pop     r13
0x1800477e6  pop     r12
0x1800477e8  pop     rdi
0x1800477e9  retn
0x1800477ea  mov     rcx, [rsp+0D8h+var_88]; void *
0x1800477ef  test    rcx, rcx
0x1800477f2  jz      short loc_1800477FA
0x1800477f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800477f9  nop
0x1800477fa  mov     rcx, [rsp+0D8h+var_80]; void *
0x1800477ff  test    rcx, rcx
0x180047802  jz      short loc_18004780A
0x180047804  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180047809  nop
0x18004780a  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x180047811  mov     [rsp+0D8h+var_A8], rax
0x180047816  cmp     [rsp+0D8h+var_90], r14b
0x18004781b  jz      short loc_180047828
0x18004781d  mov     rcx, [rsp+0D8h+Src]; void *
0x180047822  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180047827  nop
0x180047828  mov     [rdi+38h], rsi
0x18004782c  mov     [rdi+40h], r12d
0x180047830  mov     [rdi+44h], r13d
0x180047834  mov     r14, [rsp+0D8h+arg_20]
0x18004783c  mov     [rdi+48h], r14
0x180047840  mov     rax, [rsp+0D8h+arg_28]
0x180047848  mov     [rdi+50h], rax
0x18004784c  mov     rax, [rsp+0D8h+arg_30]
0x180047854  mov     [rdi+58h], rax
0x180047858  mov     [rdi+60h], r15
0x18004785c  mov     rax, [rsp+0D8h+arg_40]
0x180047864  mov     [rdi+68h], rax
0x180047868  mov     [rsi+18h], rdi
0x18004786c  lea     rcx, [rdi+70h]; this
0x180047870  mov     rdx, [rdi+38h]; struct _RPC_ASYNC_STATE *
0x180047874  call    ?Start@RpcStatusSubscription@RemoteSubscription@@QEAAJPEAU_RPC_ASYNC_STATE@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z@Z; RemoteSubscription::RpcStatusSubscription::Start(_RPC_ASYNC_STATE *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long))
0x180047879  mov     [rsp+0D8h+Reply], eax
0x180047880  xor     r12d, r12d
0x180047883  test    eax, eax
0x180047885  jnz     short loc_1800478CF
0x180047887  mov     rcx, rbx; SRWLock
0x18004788a  call    cs:__imp_ReleaseSRWLockExclusive
0x180047890  jmp     loc_1800477CD
0x180047895  mov     [rsp+0D8h+Reply], 10DDh
0x1800478a0  lea     rdx, [rsp+0D8h+Reply]; Reply
0x1800478a8  mov     rcx, rsi; pAsync
0x1800478ab  call    cs:__imp_RpcAsyncCompleteCall
0x1800478b1  jmp     short loc_180047887
0x1800478b3  mov     [rsp+0D8h+Reply], eax
0x1800478ba  jmp     short loc_1800478A0
0x1800478bc  test    r8d, r8d
0x1800478bf  jz      loc_18004778C
0x1800478c5  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800478ca  jmp     loc_18004778C
0x1800478cf  mov     edx, [r14]
0x1800478d2  mov     r8d, [r15]
0x1800478d5  test    edx, edx
0x1800478d7  jnz     short loc_1800478E0
0x1800478d9  test    r8d, r8d
0x1800478dc  jnz     short loc_1800478E5
0x1800478de  jmp     short loc_1800478EA
0x1800478e0  test    r8d, r8d
0x1800478e3  jnz     short loc_1800478EA
0x1800478e5  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800478ea  mov     [rdi+38h], r12
0x1800478ee  mov     [rdi+40h], r12
0x1800478f2  mov     [rdi+48h], r12
0x1800478f6  mov     [rdi+50h], r12
0x1800478fa  mov     [rdi+58h], r12
0x1800478fe  mov     [rdi+60h], r12
0x180047902  mov     [rdi+68h], r12
0x180047906  lea     rdx, [rsp+0D8h+Reply]; Reply
0x18004790e  mov     rcx, rsi; pAsync
0x180047911  call    cs:__imp_RpcAsyncCompleteCall
0x180047917  mov     ebx, [rsp+0D8h+Reply]
0x18004791e  mov     eax, 507h
0x180047923  test    ebx, ebx
0x180047925  cmovz   ebx, eax
0x180047928  lea     rax, WPP_GLOBAL_Control
0x18004792f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047936  cmp     rcx, rax
0x180047939  jz      short loc_180047962
0x18004793b  test    dword ptr [rcx+1Ch], 100h
0x180047942  jz      short loc_180047962
0x180047944  cmp     byte ptr [rcx+19h], 2
0x180047948  jb      short loc_180047962
0x18004794a  mov     edx, 1Dh
0x18004794f  mov     r9d, ebx
0x180047952  lea     r8, WPP_939241f3766634594ecc55fb100debfa_Traceguids
0x180047959  mov     rcx, [rcx+10h]
0x18004795d  call    WPP_SF_d
0x180047962  xorps   xmm0, xmm0
0x180047965  movdqu  [rsp+0D8h+pExceptionObject], xmm0
0x18004796b  mov     [rsp+0D8h+var_50], r12
0x180047973  mov     [rsp+0D8h+var_48], ebx
0x18004797a  mov     [rsp+0D8h+var_44], 0FFFFFFFFh
0x180047985  mov     [rsp+0D8h+var_40], 3ABh
0x180047990  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180047997  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18004799c  call    _CxxThrowException_0
```
