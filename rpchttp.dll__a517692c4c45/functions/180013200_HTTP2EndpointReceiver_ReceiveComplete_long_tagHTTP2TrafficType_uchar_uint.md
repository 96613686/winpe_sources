# HTTP2EndpointReceiver::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)

- ea: `0x180013200`
- end: `0x18001361d`
- name: `?ReceiveComplete@HTTP2EndpointReceiver@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z`
- size: `1053`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005428`
- `0x1800054b8`
- `0x180005634`
- `0x1800056b8`
- `0x180009d58`
- `0x180011c70`
- `0x180013200`
- `0x1800167d0`
- `0x180016df8`
- `0x18001e91c`
- `0x18001eb1c`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800133a8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800133a8`
- `ntdll!RtlEnterCriticalSection` at `0x18001324c`
- `ntdll!RtlEnterCriticalSection` at `0x18001324c`
- `RPCRT4!I_RpcLogEvent` at `0x18001323f`
- `RPCRT4!I_RpcLogEvent` at `0x18001345f`
- `RPCRT4!I_RpcLogEvent` at `0x180013557`
- `RPCRT4!I_RpcLogEvent` at `0x1800135fd`
- `RPCRT4!I_RpcLogEvent` at `0x18001323f`
- `RPCRT4!I_RpcLogEvent` at `0x18001345f`
- `RPCRT4!I_RpcLogEvent` at `0x180013557`
- `RPCRT4!I_RpcLogEvent` at `0x1800135fd`

## pseudocode

```c
__int64 __fastcall HTTP2EndpointReceiver::ReceiveComplete(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _BYTE *a4,
        unsigned int a5)
{
  int v5; // edi
  unsigned int v7; // esi
  __int64 v8; // rbx
  __int64 v9; // r8
  unsigned int v10; // r12d
  int v11; // r13d
  unsigned int v12; // r15d
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // ebp
  int v16; // eax
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v20; // edi
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned int v26; // edi
  HTTP2Channel **v27; // r14
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned int v30; // r14d
  unsigned int v31; // esi
  int v32; // [rsp+20h] [rbp-68h]
  unsigned int v33[18]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v34; // [rsp+90h] [rbp+8h] BYREF
  int v35; // [rsp+98h] [rbp+10h] BYREF

  v5 = 0;
  v7 = a2;
  v8 = a1;
  v32 = a2;
  v9 = a1;
  LOBYTE(a2) = 111;
  v33[0] = 0;
  v34 = 0;
  LOBYTE(a1) = 50;
  v10 = 0;
  I_RpcLogEvent(a1, a2, v9, 17039369, v32, 0, 0);
  v11 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v8 + 112));
  v12 = a5;
  v13 = 1;
  v14 = 2;
  if ( !v7 )
  {
    *(_DWORD *)(v8 + 196) += a5;
    if ( a4[2] == 20 )
    {
      v15 = 1;
LABEL_4:
      v16 = *(_DWORD *)(v8 + 184);
      if ( ((unsigned __int8)v16 & (unsigned __int8)v13) != 0 )
      {
        v10 = v13 ^ v16;
        *(_DWORD *)(v8 + 184) = v13 ^ v16;
        goto LABEL_26;
      }
      *(_DWORD *)(v8 + 188) = v13;
      goto LABEL_11;
    }
    v15 = 2;
    v7 = HTTP2GenericReceiver::BytesReceivedNotification((HTTP2GenericReceiver *)v8, v12);
    if ( !v7 )
      goto LABEL_14;
  }
  v15 = *(_DWORD *)(v8 + 184);
  if ( v15 == 3 )
  {
    v15 = v14;
  }
  else
  {
LABEL_14:
    if ( v15 == v13 )
      goto LABEL_4;
    if ( v15 - v13 != v13 )
    {
      v35 = 0;
      if ( v15 != v14 )
        goto LABEL_26;
      goto LABEL_19;
    }
  }
  v17 = *(_DWORD *)(v8 + 184);
  if ( ((unsigned __int8)v17 & (unsigned __int8)v14) == 0 )
  {
    *(_DWORD *)(v8 + 188) = v14;
LABEL_11:
    if ( (unsigned int)QUEUE::PutOnQueue((QUEUE *)(v8 + 32), a4, v12) )
    {
      v5 = 1;
      (*((void (__fastcall **)(_BYTE *))pRuntimeImportTable + 1))(a4);
    }
    v11 = 1;
    goto LABEL_26;
  }
  v35 = 0;
  v10 = v14 ^ v17;
  *(_DWORD *)(v8 + 184) = v14 ^ v17;
LABEL_19:
  if ( !v7 )
  {
    HTTP2GenericReceiver::BytesConsumedNotification((HTTP2GenericReceiver *)v8, v12, v13, &v35, v33, &v34);
    if ( v35 )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v8 + 24) + 104LL))(
              *(_QWORD *)(v8 + 24),
              v33[0],
              v34);
      if ( v18 )
      {
        v7 = v18;
        if ( v18 == -1073606646 )
          v7 = -1073606647;
      }
    }
  }
LABEL_26:
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v8 + 112));
  if ( v5 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v8 + 24) + 136LL))(*(_QWORD *)(v8 + 24), 14);
    return 3221360681LL;
  }
  if ( v11 )
  {
    v20 = HTTP2Channel::BeginSubmitAsync(*(HTTP2Channel **)(v8 + 24));
    if ( !v20 )
    {
      v20 = HTTP2TransportChannel::Receive(v8, 4);
      HTTP2Channel::FinishSubmitAsync(*(HTTP2Channel **)(v8 + 24));
      if ( !v20 )
      {
LABEL_34:
        LOBYTE(v21) = 111;
        LOBYTE(v22) = 50;
        I_RpcLogEvent(v22, v21, v8, 262153, -1073606615, 0, 0);
        return 3221360681LL;
      }
      HTTP2Channel::RemoveReference(*(HTTP2Channel **)(v8 + 24));
    }
    v23 = HTTP2TransportChannel::ReceiveComplete(v8, v20, *(unsigned int *)(v8 + 184), 0, 0);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v8 + 24) + 136LL))(*(_QWORD *)(v8 + 24), v23);
    goto LABEL_34;
  }
  v26 = HTTP2TransportChannel::ReceiveComplete(v8, v7, v15, a4, v12);
  if ( v10 )
  {
    v27 = (HTTP2Channel **)(v8 + 24);
    if ( v7
      || (v7 = HTTP2Channel::BeginSimpleSubmitAsync(*v27)) != 0
      || (v7 = HTTP2TransportChannel::Receive(v8, 4), HTTP2Channel::FinishSubmitAsync(*v27), v7) )
    {
      v7 = HTTP2TransportChannel::ReceiveComplete(v8, v7, v10, 0, 0);
      if ( v10 != 2 || v26 != -1073606615 )
        HTTP2Channel::RemoveReference(*v27);
    }
    if ( v15 == 2 )
    {
      v30 = v26;
    }
    else
    {
      v30 = v7;
      v7 = v26;
    }
    if ( v30 )
    {
      if ( v7 )
      {
        if ( v7 != -1073606615 )
          goto LABEL_50;
        if ( v15 != 2 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v8 + 24) + 136LL))(*(_QWORD *)(v8 + 24), v30);
          v31 = -1073606615;
          if ( v30 == -1073606615 )
          {
            HTTP2Channel::RemoveReference(*(HTTP2Channel **)(v8 + 24));
          }
          else
          {
            *(_DWORD *)(v8 + 192) = v30;
            RPC_THREAD_POOL::TrySubmitWork((PTP_SIMPLE_CALLBACK)HTTP2EpRecvFailed, (PVOID)v8);
          }
          goto LABEL_54;
        }
      }
      v26 = v30;
    }
    else
    {
      if ( !v7 )
      {
        v31 = 0;
LABEL_54:
        LOBYTE(v28) = 111;
        LOBYTE(v29) = 50;
        I_RpcLogEvent(v29, v28, v8, 262153, v31, 0, 0);
        return v31;
      }
      if ( v7 == -1073606615 )
        v26 = v15 != 2 ? 0xC0021029 : 0;
      else
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v8 + 24) + 136LL))(*(_QWORD *)(v8 + 24), v7);
    }
LABEL_50:
    if ( ((v26 + 1073606648) & 0xFFFFFFF5) == 0 && v26 != -1073606640 || (v31 = v26, v26 == 14) )
      v31 = -1073606647;
    goto LABEL_54;
  }
  if ( v15 == 1 )
    v26 = -1073606615;
  LOBYTE(v24) = 111;
  LOBYTE(v25) = 50;
  I_RpcLogEvent(v25, v24, v8, 262153, v26, 0, 0);
  return v26;
}

```

## disassembly

```asm
0x180013200  mov     rax, rsp
0x180013203  mov     [rax+18h], rbx
0x180013207  push    rbp
0x180013208  push    rsi
0x180013209  push    rdi
0x18001320a  push    r12
0x18001320c  push    r13
0x18001320e  push    r14
0x180013210  push    r15
0x180013212  sub     rsp, 50h
0x180013216  xor     edi, edi
0x180013218  mov     r14, r9
0x18001321b  mov     [rax-58h], edi
0x18001321e  mov     esi, edx
0x180013220  mov     [rax-60h], edi
0x180013223  mov     rbx, rcx
0x180013226  mov     [rax-68h], edx
0x180013229  mov     r8, rcx
0x18001322c  mov     dl, 6Fh ; 'o'
0x18001322e  mov     [rax-48h], edi
0x180013231  mov     r9d, 1040009h
0x180013237  mov     [rax+8], edi
0x18001323a  mov     cl, 32h ; '2'
0x18001323c  mov     r12d, edi
0x18001323f  call    cs:__imp_I_RpcLogEvent
0x180013245  lea     rcx, [rbx+70h]; CriticalSection
0x180013249  mov     r13d, edi
0x18001324c  call    cs:__imp_RtlEnterCriticalSection
0x180013252  mov     r15d, [rsp+88h+arg_20]
0x18001325a  lea     r8d, [rdi+1]
0x18001325e  lea     r9d, [rdi+2]
0x180013262  test    esi, esi
0x180013264  jnz     short loc_1800132A3
0x180013266  add     [rbx+0C4h], r15d
0x18001326d  cmp     byte ptr [r14+2], 14h
0x180013272  jnz     short loc_18001328F
0x180013274  mov     ebp, r8d
0x180013277  mov     eax, [rbx+0B8h]
0x18001327d  test    r8b, al
0x180013280  jnz     loc_180013397
0x180013286  mov     [rbx+0BCh], r8d
0x18001328d  jmp     short loc_1800132C3
0x18001328f  mov     edx, r15d; unsigned int
0x180013292  mov     rcx, rbx; this
0x180013295  mov     ebp, r9d
0x180013298  call    ?BytesReceivedNotification@HTTP2GenericReceiver@@QEAAJK@Z; HTTP2GenericReceiver::BytesReceivedNotification(ulong)
0x18001329d  mov     esi, eax
0x18001329f  test    eax, eax
0x1800132a1  jz      short loc_1800132F9
0x1800132a3  mov     ebp, [rbx+0B8h]
0x1800132a9  cmp     ebp, 3
0x1800132ac  jnz     short loc_1800132F9
0x1800132ae  mov     ebp, r9d
0x1800132b1  mov     eax, [rbx+0B8h]
0x1800132b7  test    r9b, al
0x1800132ba  jnz     short loc_18001331B
0x1800132bc  mov     [rbx+0BCh], r9d
0x1800132c3  lea     rcx, [rbx+20h]; this
0x1800132c7  mov     r8d, r15d; unsigned int
0x1800132ca  mov     rdx, r14; void *
0x1800132cd  call    ?PutOnQueue@QUEUE@@QEAAHPEAXI@Z; QUEUE::PutOnQueue(void *,uint)
0x1800132d2  test    eax, eax
0x1800132d4  jz      short loc_1800132EE
0x1800132d6  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800132dd  mov     rcx, r14
0x1800132e0  mov     edi, 1
0x1800132e5  mov     rax, [rax+8]
0x1800132e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132ee  mov     r13d, 1
0x1800132f4  jmp     loc_1800133A4
0x1800132f9  mov     ecx, ebp
0x1800132fb  sub     ecx, r8d
0x1800132fe  jz      loc_180013277
0x180013304  cmp     ecx, r8d
0x180013307  jz      short loc_1800132B1
0x180013309  mov     [rsp+88h+arg_8], edi
0x180013310  cmp     ebp, r9d
0x180013313  jnz     loc_1800133A4
0x180013319  jmp     short loc_18001332F
0x18001331b  mov     r12d, eax
0x18001331e  mov     [rsp+88h+arg_8], edi
0x180013325  xor     r12d, r9d
0x180013328  mov     [rbx+0B8h], r12d
0x18001332f  test    esi, esi
0x180013331  jnz     short loc_1800133A4
0x180013333  lea     rax, [rsp+88h+arg_0]
0x18001333b  mov     edx, r15d; unsigned int
0x18001333e  mov     [rsp+88h+var_60], rax; unsigned int *
0x180013343  lea     r9, [rsp+88h+arg_8]; int *
0x18001334b  lea     rax, [rsp+88h+var_48]
0x180013350  mov     rcx, rbx; this
0x180013353  mov     [rsp+88h+var_68], rax; unsigned int *
0x180013358  call    ?BytesConsumedNotification@HTTP2GenericReceiver@@QEAAXKHPEAHPEAK1@Z; HTTP2GenericReceiver::BytesConsumedNotification(ulong,int,int *,ulong *,ulong *)
0x18001335d  cmp     [rsp+88h+arg_8], edi
0x180013364  jz      short loc_1800133A4
0x180013366  mov     rcx, [rbx+18h]
0x18001336a  mov     r8d, [rsp+88h+arg_0]
0x180013372  mov     edx, [rsp+88h+var_48]
0x180013376  mov     rax, [rcx]
0x180013379  mov     rax, [rax+68h]
0x18001337d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013382  test    eax, eax
0x180013384  jz      short loc_1800133A4
0x180013386  mov     esi, eax
0x180013388  cmp     eax, 0C002100Ah
0x18001338d  mov     eax, 0C0021009h
0x180013392  cmovz   esi, eax
0x180013395  jmp     short loc_1800133A4
0x180013397  mov     r12d, eax
0x18001339a  xor     r12d, r8d
0x18001339d  mov     [rbx+0B8h], r12d
0x1800133a4  lea     rcx, [rbx+70h]; CriticalSection
0x1800133a8  call    cs:__imp_RtlLeaveCriticalSection
0x1800133ae  test    edi, edi
0x1800133b0  jz      short loc_1800133D4
0x1800133b2  mov     rcx, [rbx+18h]
0x1800133b6  mov     edx, 0Eh
0x1800133bb  mov     rax, [rcx]
0x1800133be  mov     rax, [rax+88h]
0x1800133c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133ca  mov     eax, 0C0021029h
0x1800133cf  jmp     loc_180013605
0x1800133d4  test    r13d, r13d
0x1800133d7  jz      loc_18001346A
0x1800133dd  mov     rcx, [rbx+18h]; this
0x1800133e1  call    ?BeginSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSubmitAsync(void)
0x1800133e6  xor     esi, esi
0x1800133e8  mov     edi, eax
0x1800133ea  test    eax, eax
0x1800133ec  jnz     short loc_180013411
0x1800133ee  lea     edx, [rax+4]
0x1800133f1  mov     rcx, rbx
0x1800133f4  call    ?Receive@HTTP2TransportChannel@@UEAAJW4tagHTTP2TrafficType@@@Z; HTTP2TransportChannel::Receive(tagHTTP2TrafficType)
0x1800133f9  mov     rcx, [rbx+18h]; this
0x1800133fd  mov     edi, eax
0x1800133ff  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x180013404  test    edi, edi
0x180013406  jz      short loc_180013442
0x180013408  mov     rcx, [rbx+18h]; this
0x18001340c  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x180013411  mov     r8d, [rbx+0B8h]
0x180013418  xor     r9d, r9d
0x18001341b  mov     edx, edi
0x18001341d  mov     dword ptr [rsp+88h+var_68], esi
0x180013421  mov     rcx, rbx
0x180013424  call    ?ReceiveComplete@HTTP2TransportChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z; HTTP2TransportChannel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)
0x180013429  mov     rcx, [rbx+18h]
0x18001342d  mov     r8d, eax
0x180013430  mov     rdx, [rcx]
0x180013433  mov     rax, [rdx+88h]
0x18001343a  mov     edx, r8d
0x18001343d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013442  mov     [rsp+88h+var_58], esi
0x180013446  mov     r9d, 40009h
0x18001344c  mov     dword ptr [rsp+88h+var_60], esi
0x180013450  mov     r8, rbx
0x180013453  mov     dl, 6Fh ; 'o'
0x180013455  mov     dword ptr [rsp+88h+var_68], 0C0021029h
0x18001345d  mov     cl, 32h ; '2'
0x18001345f  call    cs:__imp_I_RpcLogEvent
0x180013465  jmp     loc_1800133CA
0x18001346a  mov     r9, r14
0x18001346d  mov     dword ptr [rsp+88h+var_68], r15d
0x180013472  mov     r8d, ebp
0x180013475  mov     edx, esi
0x180013477  mov     rcx, rbx
0x18001347a  call    ?ReceiveComplete@HTTP2TransportChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z; HTTP2TransportChannel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)
0x18001347f  xor     r13d, r13d
0x180013482  mov     edi, eax
0x180013484  test    r12d, r12d
0x180013487  jz      loc_1800135D7
0x18001348d  lea     r14, [rbx+18h]
0x180013491  mov     r15d, 0C0021029h
0x180013497  test    esi, esi
0x180013499  jnz     short loc_1800134C2
0x18001349b  mov     rcx, [r14]; this
0x18001349e  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x1800134a3  mov     esi, eax
0x1800134a5  test    eax, eax
0x1800134a7  jnz     short loc_1800134C2
0x1800134a9  lea     edx, [rax+4]
0x1800134ac  mov     rcx, rbx
0x1800134af  call    ?Receive@HTTP2TransportChannel@@UEAAJW4tagHTTP2TrafficType@@@Z; HTTP2TransportChannel::Receive(tagHTTP2TrafficType)
0x1800134b4  mov     rcx, [r14]; this
0x1800134b7  mov     esi, eax
0x1800134b9  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x1800134be  test    esi, esi
0x1800134c0  jz      short loc_1800134EC
0x1800134c2  xor     r9d, r9d
0x1800134c5  mov     dword ptr [rsp+88h+var_68], r13d
0x1800134ca  mov     r8d, r12d
0x1800134cd  mov     edx, esi
0x1800134cf  mov     rcx, rbx
0x1800134d2  call    ?ReceiveComplete@HTTP2TransportChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z; HTTP2TransportChannel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)
0x1800134d7  mov     esi, eax
0x1800134d9  cmp     r12d, 2
0x1800134dd  jnz     short loc_1800134E4
0x1800134df  cmp     edi, r15d
0x1800134e2  jz      short loc_1800134EC
0x1800134e4  mov     rcx, [r14]; this
0x1800134e7  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x1800134ec  cmp     ebp, 2
0x1800134ef  jnz     short loc_1800134F6
0x1800134f1  mov     r14d, edi
0x1800134f4  jmp     short loc_1800134FB
0x1800134f6  mov     r14d, esi
0x1800134f9  mov     esi, edi
0x1800134fb  test    r14d, r14d
0x1800134fe  jnz     short loc_18001357B
0x180013500  test    esi, esi
0x180013502  jnz     short loc_180013509
0x180013504  mov     esi, r13d
0x180013507  jmp     short loc_18001353C
0x180013509  cmp     esi, r15d
0x18001350c  jnz     short loc_180013564
0x18001350e  sub     ebp, 2
0x180013511  neg     ebp
0x180013513  sbb     edi, edi
0x180013515  and     edi, 0C0021029h
0x18001351b  lea     eax, [rdi+3FFDEFF8h]
0x180013521  test    eax, 0FFFFFFF5h
0x180013526  jnz     short loc_180013530
0x180013528  cmp     edi, 0C0021010h
0x18001352e  jnz     short loc_180013537
0x180013530  mov     esi, edi
0x180013532  cmp     edi, 0Eh
0x180013535  jnz     short loc_18001353C
0x180013537  mov     esi, 0C0021009h
0x18001353c  mov     [rsp+88h+var_58], r13d
0x180013541  mov     r9d, 40009h
0x180013547  mov     dword ptr [rsp+88h+var_60], r13d
0x18001354c  mov     r8, rbx
0x18001354f  mov     dl, 6Fh ; 'o'
0x180013551  mov     dword ptr [rsp+88h+var_68], esi
0x180013555  mov     cl, 32h ; '2'
0x180013557  call    cs:__imp_I_RpcLogEvent
0x18001355d  mov     eax, esi
0x18001355f  jmp     loc_180013605
0x180013564  mov     rcx, [rbx+18h]
0x180013568  mov     edx, esi
0x18001356a  mov     rax, [rcx]
0x18001356d  mov     rax, [rax+88h]
0x180013574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013579  jmp     short loc_18001351B
0x18001357b  test    esi, esi
0x18001357d  jz      short loc_180013589
0x18001357f  cmp     esi, r15d
0x180013582  jnz     short loc_18001351B
0x180013584  cmp     ebp, 2
0x180013587  jnz     short loc_18001358E
0x180013589  mov     edi, r14d
0x18001358c  jmp     short loc_18001351B
0x18001358e  mov     rcx, [rbx+18h]
0x180013592  mov     edx, r14d
0x180013595  mov     rax, [rcx]
0x180013598  mov     rax, [rax+88h]
0x18001359f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135a4  mov     esi, 0C0021029h
0x1800135a9  cmp     r14d, r15d
0x1800135ac  jz      short loc_1800135C9
0x1800135ae  mov     rdx, rbx; pv
0x1800135b1  mov     [rbx+0C0h], r14d
0x1800135b8  lea     rcx, ?HTTP2EpRecvFailed@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x1800135bf  call    ?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x1800135c4  jmp     loc_18001353C
0x1800135c9  mov     rcx, [rbx+18h]; this
0x1800135cd  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x1800135d2  jmp     loc_18001353C
0x1800135d7  cmp     ebp, 1
0x1800135da  mov     [rsp+88h+var_58], r13d
0x1800135df  mov     esi, 0C0021029h
0x1800135e4  mov     dword ptr [rsp+88h+var_60], r13d
0x1800135e9  cmovz   edi, esi
0x1800135ec  mov     r9d, 40009h
0x1800135f2  mov     r8, rbx
0x1800135f5  mov     dword ptr [rsp+88h+var_68], edi
0x1800135f9  mov     dl, 6Fh ; 'o'
0x1800135fb  mov     cl, 32h ; '2'
0x1800135fd  call    cs:__imp_I_RpcLogEvent
0x180013603  mov     eax, edi
0x180013605  mov     rbx, [rsp+88h+arg_10]
0x18001360d  add     rsp, 50h
0x180013611  pop     r15
0x180013613  pop     r14
0x180013615  pop     r13
0x180013617  pop     r12
0x180013619  pop     rdi
0x18001361a  pop     rsi
0x18001361b  pop     rbp
0x18001361c  retn
```
